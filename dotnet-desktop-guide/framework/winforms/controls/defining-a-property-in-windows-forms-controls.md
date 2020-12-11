---
title: コントロールのプロパティを定義する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties [Windows Forms], defining in code
- custom controls [Windows Forms], defining properties in code
ms.assetid: c2eb8277-a842-4d99-89a9-647b901a0434
ms.openlocfilehash: ef81818123e78c50ade9f700a3acdbea1c5551b4
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974200"
---
# <a name="defining-a-property-in-windows-forms-controls"></a>Windows フォーム コントロールのプロパティの定義

プロパティの概要については、「[プロパティの概要](/previous-versions/visualstudio/visual-studio-2013/65zdfbdt(v=vs.120))」を参照してください。 プロパティを定義するときには、いくつかの重要な考慮事項があります。  
  
- 定義するプロパティに属性を適用する必要があります。 属性によって、デザイナーでプロパティがどのように表示されるかが指定されます。 詳細については、「[コンポーネントのデザイン時属性](/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120))」を参照してください。  
  
- プロパティを変更してコントロールのビジュアル表示に影響を与える場合は、 <xref:System.Windows.Forms.Control.Invalidate%2A> アクセサーから (コントロールが継承する) メソッドを呼び出し <xref:System.Windows.Forms.Control> `set` ます。 <xref:System.Windows.Forms.Control.Invalidate%2A> さらに、 <xref:System.Windows.Forms.Control.OnPaint%2A> メソッドを呼び出して、コントロールを再描画します。 を複数回呼び出すと <xref:System.Windows.Forms.Control.Invalidate%2A> 、 <xref:System.Windows.Forms.Control.OnPaint%2A> 効率が向上します。  
  
- .NET Framework クラス ライブラリでは、整数、10 進数、ブール値など、一般的なデータ型に対応する型コンバーターを使用できます。 型コンバーターは、一般に文字列から値への変換を行うために使用されます (文字列データから他のデータ型に変換)。 一般的なデータ型は、値を文字列に変換し、文字列を適切なデータ型に変換する既定の型コンバーターに関連付けられています。 カスタム (つまり、非標準的な) データ型であるプロパティを定義する場合、そのプロパティに関連付けられる型コンバーターを指定する属性を適用する必要があります。 また、属性を使用してカスタム UI 型エディターとプロパティを関連付けることもできます。 UI 型エディターには、プロパティやデータ型を編集するためのユーザー インターフェイスが備わっています。 たとえば、カラー ピッカーなどの UI 型エディターがあります。 属性の例は、このトピックの最後に記載されています。  
  
    > [!NOTE]
    > 型コンバーターまたは UI 型エディターをカスタム プロパティに使用できない場合、「[デザイン時サポートの拡張](/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))」に示されているものを実装できます。  
  
 次のコード フラグメントは、カスタム コントロール `FlashTrackBar` に対して `EndColor` という名前のカスタム プロパティを定義します。  
  
```vb  
Public Class FlashTrackBar  
   Inherits Control  
   ...  
   ' Private data member that backs the EndColor property.  
   Private _endColor As Color = Color.LimeGreen  
  
   ' The Category attribute tells the designer to display  
   ' it in the Flash grouping.
   ' The Description attribute provides a description of  
   ' the property.
   <Category("Flash"), _  
   Description("The ending color of the bar.")>  _  
   Public Property EndColor() As Color  
      ' The public property EndColor accesses _endColor.  
      Get  
         Return _endColor  
      End Get  
      Set  
         _endColor = value  
         If Not (baseBackground Is Nothing) And showGradient Then  
            baseBackground.Dispose()  
            baseBackground = Nothing  
         End If  
         ' The Invalidate method calls the OnPaint method, which redraws
         ' the control.  
         Invalidate()  
      End Set  
   End Property  
   ...  
End Class  
```  
  
```csharp  
public class FlashTrackBar : Control {  
   ...  
   // Private data member that backs the EndColor property.  
   private Color endColor = Color.LimeGreen;  
   // The Category attribute tells the designer to display  
   // it in the Flash grouping.
   // The Description attribute provides a description of  
   // the property.
   [  
   Category("Flash"),  
   Description("The ending color of the bar.")  
   ]  
   // The public property EndColor accesses endColor.  
   public Color EndColor {  
      get {  
         return endColor;  
      }  
      set {  
         endColor = value;  
         if (baseBackground != null && showGradient) {  
            baseBackground.Dispose();  
            baseBackground = null;  
         }  
         // The Invalidate method calls the OnPaint method, which redraws
         // the control.  
         Invalidate();  
      }  
   }  
   ...  
}  
```  
  
 次のコード フラグメントは、型コンバーターと UI 型エディターをプロパティ `Value` に関連付けます。 この場合、 `Value` は整数であり、既定の型コンバーターを持ちますが、属性は、 <xref:System.ComponentModel.TypeConverterAttribute> `FlashTrackBarValueConverter` デザイナーがパーセンテージとして表示できるようにするカスタム型コンバーター () を適用します。 UI 型エディター `FlashTrackBarValueEditor` により、そのパーセントを視覚的に表示できます。 また、この例では、または属性で指定された型コンバーターまたはエディターが既定のコンバーターをオーバーライドしていることも示して <xref:System.ComponentModel.TypeConverterAttribute> <xref:System.ComponentModel.EditorAttribute> います。  
  
```vb  
<Category("Flash"), _  
TypeConverter(GetType(FlashTrackBarValueConverter)), _  
Editor(GetType(FlashTrackBarValueEditor), _  
GetType(UITypeEditor)), _  
Description("The current value of the track bar.  You can enter an actual value or a percentage.")>  _  
Public ReadOnly Property Value() As Integer  
...  
End Property  
```  
  
```csharp  
[  
Category("Flash"),
TypeConverter(typeof(FlashTrackBarValueConverter)),  
Editor(typeof(FlashTrackBarValueEditor), typeof(UITypeEditor)),  
Description("The current value of the track bar.  You can enter an actual value or a percentage.")  
]  
public int Value {  
...  
}  
```  
  
## <a name="see-also"></a>関連項目

- [Windows フォーム コントロールのプロパティ](properties-in-windows-forms-controls.md)
- [ShouldSerialize メソッドと Reset メソッドによる既定値の定義](defining-default-values-with-the-shouldserialize-and-reset-methods.md)
- [プロパティ変更イベント](property-changed-events.md)
- [Windows フォーム コントロールの属性](attributes-in-windows-forms-controls.md)
