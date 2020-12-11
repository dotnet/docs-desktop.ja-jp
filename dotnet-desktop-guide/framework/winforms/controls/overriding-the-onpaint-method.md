---
title: OnPaint メソッドのオーバーライド
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Paint event [Windows Forms], handling in Windows Forms custom control
- OnPaint method [Windows Forms], overriding in Windows Forms custom controls
ms.assetid: e9ca2723-0107-4540-bb21-4f5ffb4a9906
ms.openlocfilehash: 140c3e880300f8b1428dd23d946f25d095189fb3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982915"
---
# <a name="overriding-the-onpaint-method"></a>OnPaint メソッドのオーバーライド

.NET Framework で定義されているイベントを上書きするための基本的な手順は同じであり、次の一覧にまとめられています。  
  
#### <a name="to-override-an-inherited-event"></a>継承されたイベントをオーバーライドするには  
  
1. Protected `On` *EventName* メソッドをオーバーライドします。  
  
2. `On`オーバーライドされた eventname メソッドから基本クラスの *EventName* メソッドを呼び出して `On`  、登録されているデリゲートがイベントを受け取るようにします。  
  
 <xref:System.Windows.Forms.Control.Paint>このイベントの詳細については、すべての Windows フォームコントロールが、継承元のイベントをオーバーライドする必要があるため、ここで詳しく説明 <xref:System.Windows.Forms.Control.Paint> <xref:System.Windows.Forms.Control> します。 基底クラスは、 <xref:System.Windows.Forms.Control> 派生コントロールを描画する必要があるかどうかを認識しないため、メソッドに描画ロジックを提供しません <xref:System.Windows.Forms.Control.OnPaint%2A> 。 <xref:System.Windows.Forms.Control.OnPaint%2A>のメソッドは、 <xref:System.Windows.Forms.Control> イベントを <xref:System.Windows.Forms.Control.Paint> 登録されたイベントレシーバーに単にディスパッチします。  
  
 [「方法: 単純な Windows フォームコントロールを開発](how-to-develop-a-simple-windows-forms-control.md)する」のサンプルを使用した場合は、メソッドをオーバーライドする例を見てきました <xref:System.Windows.Forms.Control.OnPaint%2A> 。 次のコードは、そのサンプルから抜粋したものです。  
  
```vb  
Public Class FirstControl  
   Inherits Control  
  
   Public Sub New()  
   End Sub  
  
   Protected Overrides Sub OnPaint(e As PaintEventArgs)  
      ' Call the OnPaint method of the base class.  
      MyBase.OnPaint(e)  
      ' Call methods of the System.Drawing.Graphics object.  
      e.Graphics.DrawString(Text, Font, New SolidBrush(ForeColor), RectangleF.op_Implicit(ClientRectangle))  
   End Sub  
End Class
```  
  
```csharp  
public class FirstControl : Control {  
   public FirstControl() {}  
   protected override void OnPaint(PaintEventArgs e) {  
      // Call the OnPaint method of the base class.  
      base.OnPaint(e);  
      // Call methods of the System.Drawing.Graphics object.  
      e.Graphics.DrawString(Text, Font, new SolidBrush(ForeColor), ClientRectangle);  
   }
}
```  
  
 クラスには <xref:System.Windows.Forms.PaintEventArgs> 、イベントのデータが含まれてい <xref:System.Windows.Forms.Control.Paint> ます。 次のコードに示すように、2つのプロパティがあります。  
  
```vb  
Public Class PaintEventArgs  
   Inherits EventArgs  
   ...  
   Public ReadOnly Property ClipRectangle() As System.Drawing.Rectangle  
      ...  
   End Property  
  
   Public ReadOnly Property Graphics() As System.Drawing.Graphics  
      ...  
   End Property
   ...  
End Class  
```  
  
```csharp  
public class PaintEventArgs : EventArgs {  
...  
    public System.Drawing.Rectangle ClipRectangle {}  
    public System.Drawing.Graphics Graphics {}  
...  
}  
```  
  
 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> は描画される四角形で、プロパティは <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> オブジェクトを参照し <xref:System.Drawing.Graphics> ます。 名前空間のクラス <xref:System.Drawing?displayProperty=nameWithType> は、新しい Windows グラフィックスライブラリである GDI + の機能へのアクセスを提供するマネージクラスです。 <xref:System.Drawing.Graphics>オブジェクトには、ポイント、文字列、線、円弧、楕円、およびその他の多くの図形を描画するメソッドがあります。  
  
 コントロールは、 <xref:System.Windows.Forms.Control.OnPaint%2A> ビジュアル表示を変更する必要があるときに、そのメソッドを呼び出します。 このメソッドは、イベントを発生させ <xref:System.Windows.Forms.Control.Paint> ます。  
  
## <a name="see-also"></a>関連項目

- [イベント](/dotnet/standard/events/index)
- [Windows フォーム コントロールのレンダリング](rendering-a-windows-forms-control.md)
- [イベントの定義](defining-an-event-in-windows-forms-controls.md)
