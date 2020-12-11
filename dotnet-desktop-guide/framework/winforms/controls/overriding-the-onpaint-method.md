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
# <a name="overriding-the-onpaint-method"></a><span data-ttu-id="ee88f-102">OnPaint メソッドのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="ee88f-102">Overriding the OnPaint Method</span></span>

<span data-ttu-id="ee88f-103">.NET Framework で定義されているイベントを上書きするための基本的な手順は同じであり、次の一覧にまとめられています。</span><span class="sxs-lookup"><span data-stu-id="ee88f-103">The basic steps for overriding any event defined in the .NET Framework are identical and are summarized in the following list.</span></span>  
  
#### <a name="to-override-an-inherited-event"></a><span data-ttu-id="ee88f-104">継承されたイベントをオーバーライドするには</span><span class="sxs-lookup"><span data-stu-id="ee88f-104">To override an inherited event</span></span>  
  
1. <span data-ttu-id="ee88f-105">Protected `On` *EventName* メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="ee88f-105">Override the protected `On`*EventName* method.</span></span>  
  
2. <span data-ttu-id="ee88f-106">`On`オーバーライドされた eventname メソッドから基本クラスの *EventName* メソッドを呼び出して `On`  、登録されているデリゲートがイベントを受け取るようにします。</span><span class="sxs-lookup"><span data-stu-id="ee88f-106">Call the `On`*EventName* method of the base class from the overridden `On`*EventName* method, so that registered delegates receive the event.</span></span>  
  
 <span data-ttu-id="ee88f-107"><xref:System.Windows.Forms.Control.Paint>このイベントの詳細については、すべての Windows フォームコントロールが、継承元のイベントをオーバーライドする必要があるため、ここで詳しく説明 <xref:System.Windows.Forms.Control.Paint> <xref:System.Windows.Forms.Control> します。</span><span class="sxs-lookup"><span data-stu-id="ee88f-107">The <xref:System.Windows.Forms.Control.Paint> event is discussed in detail here because every Windows Forms control must override the <xref:System.Windows.Forms.Control.Paint> event that it inherits from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="ee88f-108">基底クラスは、 <xref:System.Windows.Forms.Control> 派生コントロールを描画する必要があるかどうかを認識しないため、メソッドに描画ロジックを提供しません <xref:System.Windows.Forms.Control.OnPaint%2A> 。</span><span class="sxs-lookup"><span data-stu-id="ee88f-108">The base <xref:System.Windows.Forms.Control> class does not know how a derived control needs to be drawn and does not provide any painting logic in the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="ee88f-109"><xref:System.Windows.Forms.Control.OnPaint%2A>のメソッドは、 <xref:System.Windows.Forms.Control> イベントを <xref:System.Windows.Forms.Control.Paint> 登録されたイベントレシーバーに単にディスパッチします。</span><span class="sxs-lookup"><span data-stu-id="ee88f-109">The <xref:System.Windows.Forms.Control.OnPaint%2A> method of <xref:System.Windows.Forms.Control> simply dispatches the <xref:System.Windows.Forms.Control.Paint> event to registered event receivers.</span></span>  
  
 <span data-ttu-id="ee88f-110">[「方法: 単純な Windows フォームコントロールを開発](how-to-develop-a-simple-windows-forms-control.md)する」のサンプルを使用した場合は、メソッドをオーバーライドする例を見てきました <xref:System.Windows.Forms.Control.OnPaint%2A> 。</span><span class="sxs-lookup"><span data-stu-id="ee88f-110">If you worked through the sample in [How to: Develop a Simple Windows Forms Control](how-to-develop-a-simple-windows-forms-control.md), you have seen an example of overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="ee88f-111">次のコードは、そのサンプルから抜粋したものです。</span><span class="sxs-lookup"><span data-stu-id="ee88f-111">The following code fragment is taken from that sample.</span></span>  
  
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
  
 <span data-ttu-id="ee88f-112">クラスには <xref:System.Windows.Forms.PaintEventArgs> 、イベントのデータが含まれてい <xref:System.Windows.Forms.Control.Paint> ます。</span><span class="sxs-lookup"><span data-stu-id="ee88f-112">The <xref:System.Windows.Forms.PaintEventArgs> class contains data for the <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="ee88f-113">次のコードに示すように、2つのプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="ee88f-113">It has two properties, as shown in the following code.</span></span>  
  
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
  
 <span data-ttu-id="ee88f-114"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> は描画される四角形で、プロパティは <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> オブジェクトを参照し <xref:System.Drawing.Graphics> ます。</span><span class="sxs-lookup"><span data-stu-id="ee88f-114"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> is the rectangle to be painted, and the <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> property refers to a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="ee88f-115">名前空間のクラス <xref:System.Drawing?displayProperty=nameWithType> は、新しい Windows グラフィックスライブラリである GDI + の機能へのアクセスを提供するマネージクラスです。</span><span class="sxs-lookup"><span data-stu-id="ee88f-115">The classes in the <xref:System.Drawing?displayProperty=nameWithType> namespace are managed classes that provide access to the functionality of GDI+, the new Windows graphics library.</span></span> <span data-ttu-id="ee88f-116"><xref:System.Drawing.Graphics>オブジェクトには、ポイント、文字列、線、円弧、楕円、およびその他の多くの図形を描画するメソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="ee88f-116">The <xref:System.Drawing.Graphics> object has methods to draw points, strings, lines, arcs, ellipses, and many other shapes.</span></span>  
  
 <span data-ttu-id="ee88f-117">コントロールは、 <xref:System.Windows.Forms.Control.OnPaint%2A> ビジュアル表示を変更する必要があるときに、そのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ee88f-117">A control invokes its <xref:System.Windows.Forms.Control.OnPaint%2A> method whenever it needs to change its visual display.</span></span> <span data-ttu-id="ee88f-118">このメソッドは、イベントを発生させ <xref:System.Windows.Forms.Control.Paint> ます。</span><span class="sxs-lookup"><span data-stu-id="ee88f-118">This method in turn raises the <xref:System.Windows.Forms.Control.Paint> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee88f-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="ee88f-119">See also</span></span>

- [<span data-ttu-id="ee88f-120">イベント</span><span class="sxs-lookup"><span data-stu-id="ee88f-120">Events</span></span>](/dotnet/standard/events/index)
- [<span data-ttu-id="ee88f-121">Windows フォーム コントロールのレンダリング</span><span class="sxs-lookup"><span data-stu-id="ee88f-121">Rendering a Windows Forms Control</span></span>](rendering-a-windows-forms-control.md)
- [<span data-ttu-id="ee88f-122">イベントの定義</span><span class="sxs-lookup"><span data-stu-id="ee88f-122">Defining an Event</span></span>](defining-an-event-in-windows-forms-controls.md)
