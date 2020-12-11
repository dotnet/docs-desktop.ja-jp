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
# <a name="defining-a-property-in-windows-forms-controls"></a><span data-ttu-id="f0303-102">Windows フォーム コントロールのプロパティの定義</span><span class="sxs-lookup"><span data-stu-id="f0303-102">Defining a Property in Windows Forms Controls</span></span>

<span data-ttu-id="f0303-103">プロパティの概要については、「[プロパティの概要](/previous-versions/visualstudio/visual-studio-2013/65zdfbdt(v=vs.120))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0303-103">For an overview of properties, see [Properties Overview](/previous-versions/visualstudio/visual-studio-2013/65zdfbdt(v=vs.120)).</span></span> <span data-ttu-id="f0303-104">プロパティを定義するときには、いくつかの重要な考慮事項があります。</span><span class="sxs-lookup"><span data-stu-id="f0303-104">There are a few important considerations when defining a property:</span></span>  
  
- <span data-ttu-id="f0303-105">定義するプロパティに属性を適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0303-105">You must apply attributes to the properties you define.</span></span> <span data-ttu-id="f0303-106">属性によって、デザイナーでプロパティがどのように表示されるかが指定されます。</span><span class="sxs-lookup"><span data-stu-id="f0303-106">Attributes specify how the designer should display a property.</span></span> <span data-ttu-id="f0303-107">詳細については、「[コンポーネントのデザイン時属性](/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0303-107">For details, see [Design-Time Attributes for Components](/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120)).</span></span>  
  
- <span data-ttu-id="f0303-108">プロパティを変更してコントロールのビジュアル表示に影響を与える場合は、 <xref:System.Windows.Forms.Control.Invalidate%2A> アクセサーから (コントロールが継承する) メソッドを呼び出し <xref:System.Windows.Forms.Control> `set` ます。</span><span class="sxs-lookup"><span data-stu-id="f0303-108">If changing the property affects the visual display of the control, call the <xref:System.Windows.Forms.Control.Invalidate%2A> method (that your control inherits from <xref:System.Windows.Forms.Control>) from the `set` accessor.</span></span> <span data-ttu-id="f0303-109"><xref:System.Windows.Forms.Control.Invalidate%2A> さらに、 <xref:System.Windows.Forms.Control.OnPaint%2A> メソッドを呼び出して、コントロールを再描画します。</span><span class="sxs-lookup"><span data-stu-id="f0303-109"><xref:System.Windows.Forms.Control.Invalidate%2A> in turn calls the <xref:System.Windows.Forms.Control.OnPaint%2A> method, which redraws the control.</span></span> <span data-ttu-id="f0303-110">を複数回呼び出すと <xref:System.Windows.Forms.Control.Invalidate%2A> 、 <xref:System.Windows.Forms.Control.OnPaint%2A> 効率が向上します。</span><span class="sxs-lookup"><span data-stu-id="f0303-110">Multiple calls to <xref:System.Windows.Forms.Control.Invalidate%2A> result in a single call to <xref:System.Windows.Forms.Control.OnPaint%2A> for efficiency.</span></span>  
  
- <span data-ttu-id="f0303-111">.NET Framework クラス ライブラリでは、整数、10 進数、ブール値など、一般的なデータ型に対応する型コンバーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f0303-111">The .NET Framework class library provides type converters for common data types such as integers, decimal numbers, Boolean values, and others.</span></span> <span data-ttu-id="f0303-112">型コンバーターは、一般に文字列から値への変換を行うために使用されます (文字列データから他のデータ型に変換)。</span><span class="sxs-lookup"><span data-stu-id="f0303-112">The purpose of a type converter is generally to provide string-to-value conversion (from string data to other data types).</span></span> <span data-ttu-id="f0303-113">一般的なデータ型は、値を文字列に変換し、文字列を適切なデータ型に変換する既定の型コンバーターに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="f0303-113">Common data types are associated with default type converters that convert values into strings and strings into the appropriate data types.</span></span> <span data-ttu-id="f0303-114">カスタム (つまり、非標準的な) データ型であるプロパティを定義する場合、そのプロパティに関連付けられる型コンバーターを指定する属性を適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0303-114">If you define a property that is a custom (that is, nonstandard) data type, you will have to apply an attribute that specifies the type converter to associate with that property.</span></span> <span data-ttu-id="f0303-115">また、属性を使用してカスタム UI 型エディターとプロパティを関連付けることもできます。</span><span class="sxs-lookup"><span data-stu-id="f0303-115">You can also use an attribute to associate a custom UI type editor with a property.</span></span> <span data-ttu-id="f0303-116">UI 型エディターには、プロパティやデータ型を編集するためのユーザー インターフェイスが備わっています。</span><span class="sxs-lookup"><span data-stu-id="f0303-116">A UI type editor provides a user interface for editing a property or data type.</span></span> <span data-ttu-id="f0303-117">たとえば、カラー ピッカーなどの UI 型エディターがあります。</span><span class="sxs-lookup"><span data-stu-id="f0303-117">A color picker is an example of a UI type editor.</span></span> <span data-ttu-id="f0303-118">属性の例は、このトピックの最後に記載されています。</span><span class="sxs-lookup"><span data-stu-id="f0303-118">Examples of attributes are given at the end of this topic.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="f0303-119">型コンバーターまたは UI 型エディターをカスタム プロパティに使用できない場合、「[デザイン時サポートの拡張](/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))」に示されているものを実装できます。</span><span class="sxs-lookup"><span data-stu-id="f0303-119">If a type converter or a UI type editor is not available for your custom property, you can implement one as described in [Extending Design-Time Support](/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120)).</span></span>  
  
 <span data-ttu-id="f0303-120">次のコード フラグメントは、カスタム コントロール `FlashTrackBar` に対して `EndColor` という名前のカスタム プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="f0303-120">The following code fragment defines a custom property named `EndColor` for the custom control `FlashTrackBar`.</span></span>  
  
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
  
 <span data-ttu-id="f0303-121">次のコード フラグメントは、型コンバーターと UI 型エディターをプロパティ `Value` に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="f0303-121">The following code fragment associates a type converter and a UI type editor with the property `Value`.</span></span> <span data-ttu-id="f0303-122">この場合、 `Value` は整数であり、既定の型コンバーターを持ちますが、属性は、 <xref:System.ComponentModel.TypeConverterAttribute> `FlashTrackBarValueConverter` デザイナーがパーセンテージとして表示できるようにするカスタム型コンバーター () を適用します。</span><span class="sxs-lookup"><span data-stu-id="f0303-122">In this case `Value` is an integer and has a default type converter, but the <xref:System.ComponentModel.TypeConverterAttribute> attribute applies a custom type converter (`FlashTrackBarValueConverter`) that enables the designer to display it as a percentage.</span></span> <span data-ttu-id="f0303-123">UI 型エディター `FlashTrackBarValueEditor` により、そのパーセントを視覚的に表示できます。</span><span class="sxs-lookup"><span data-stu-id="f0303-123">The UI type editor, `FlashTrackBarValueEditor`, allows the percentage to be displayed visually.</span></span> <span data-ttu-id="f0303-124">また、この例では、または属性で指定された型コンバーターまたはエディターが既定のコンバーターをオーバーライドしていることも示して <xref:System.ComponentModel.TypeConverterAttribute> <xref:System.ComponentModel.EditorAttribute> います。</span><span class="sxs-lookup"><span data-stu-id="f0303-124">This example also shows that the type converter or editor specified by the <xref:System.ComponentModel.TypeConverterAttribute> or <xref:System.ComponentModel.EditorAttribute> attribute overrides the default converter.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f0303-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="f0303-125">See also</span></span>

- [<span data-ttu-id="f0303-126">Windows フォーム コントロールのプロパティ</span><span class="sxs-lookup"><span data-stu-id="f0303-126">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
- [<span data-ttu-id="f0303-127">ShouldSerialize メソッドと Reset メソッドによる既定値の定義</span><span class="sxs-lookup"><span data-stu-id="f0303-127">Defining Default Values with the ShouldSerialize and Reset Methods</span></span>](defining-default-values-with-the-shouldserialize-and-reset-methods.md)
- [<span data-ttu-id="f0303-128">プロパティ変更イベント</span><span class="sxs-lookup"><span data-stu-id="f0303-128">Property-Changed Events</span></span>](property-changed-events.md)
- [<span data-ttu-id="f0303-129">Windows フォーム コントロールの属性</span><span class="sxs-lookup"><span data-stu-id="f0303-129">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)
