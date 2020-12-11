---
title: イベント ハンドラーの概要
ms.date: 03/30/2017
ms.topic: overview
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, event handling
- event handling [Windows Forms], Windows Forms
- event handlers [Windows Forms], about event handlers
ms.assetid: 228112e1-1711-42ee-8ffa-ff3555bffe66
ms.openlocfilehash: ec8bc23ce8aba36ad456114ec645d4f0799f107f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981903"
---
# <a name="event-handlers-overview-windows-forms"></a><span data-ttu-id="67b03-102">イベント ハンドラーの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="67b03-102">Event Handlers Overview (Windows Forms)</span></span>
<span data-ttu-id="67b03-103">イベントハンドラーは、イベントにバインドされているメソッドです。</span><span class="sxs-lookup"><span data-stu-id="67b03-103">An event handler is a method that is bound to an event.</span></span> <span data-ttu-id="67b03-104">イベントが発生すると、イベントハンドラー内のコードが実行されます。</span><span class="sxs-lookup"><span data-stu-id="67b03-104">When the event is raised, the code within the event handler is executed.</span></span> <span data-ttu-id="67b03-105">各イベントハンドラーには、イベントを適切に処理できる2つのパラメーターが用意されています。</span><span class="sxs-lookup"><span data-stu-id="67b03-105">Each event handler provides two parameters that allow you to handle the event properly.</span></span> <span data-ttu-id="67b03-106">次の例は、コントロールのイベントのイベントハンドラーを示して <xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.Control.Click> います。</span><span class="sxs-lookup"><span data-stu-id="67b03-106">The following example shows an event handler for a <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event.</span></span>  
  
```vb  
Private Sub button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles button1.Click  
  
End Sub  
```  
  
```csharp  
private void button1_Click(object sender, System.EventArgs e)
{  
  
}  
```  
  
```cpp  
private:  
  void button1_Click(System::Object ^ sender,  
    System::EventArgs ^ e)  
  {  
  
  }  
```  
  
 <span data-ttu-id="67b03-107">最初のパラメーターであるは、 `sender` イベントを発生させたオブジェクトへの参照を提供します。</span><span class="sxs-lookup"><span data-stu-id="67b03-107">The first parameter,`sender`, provides a reference to the object that raised the event.</span></span> <span data-ttu-id="67b03-108">上の例の2番目のパラメーターは、 `e` 処理されるイベントに固有のオブジェクトを渡します。</span><span class="sxs-lookup"><span data-stu-id="67b03-108">The second parameter, `e`, in the example above, passes an object specific to the event that is being handled.</span></span> <span data-ttu-id="67b03-109">オブジェクトのプロパティ (および場合によってはメソッド) を参照することにより、ドラッグアンドドロップイベントでマウスイベントや転送されるデータの場所などの情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="67b03-109">By referencing the object's properties (and, sometimes, its methods), you can obtain information such as the location of the mouse for mouse events or data being transferred in drag-and-drop events.</span></span>  
  
 <span data-ttu-id="67b03-110">通常、各イベントは、2番目のパラメーターに対して異なるイベントオブジェクトの種類を持つイベントハンドラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="67b03-110">Typically each event produces an event handler with a different event-object type for the second parameter.</span></span> <span data-ttu-id="67b03-111">イベントおよびイベントのイベントハンドラーの中には、 <xref:System.Windows.Forms.Control.MouseDown> <xref:System.Windows.Forms.Control.MouseUp> 2 番目のパラメーターと同じオブジェクト型を持つものもあります。</span><span class="sxs-lookup"><span data-stu-id="67b03-111">Some event handlers, such as those for the <xref:System.Windows.Forms.Control.MouseDown> and <xref:System.Windows.Forms.Control.MouseUp> events, have the same object type for their second parameter.</span></span> <span data-ttu-id="67b03-112">これらの種類のイベントでは、同じイベントハンドラーを使用して両方のイベントを処理できます。</span><span class="sxs-lookup"><span data-stu-id="67b03-112">For these types of events, you can use the same event handler to handle both events.</span></span>  
  
 <span data-ttu-id="67b03-113">また、同じイベントハンドラーを使用して、さまざまなコントロールに対して同じイベントを処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="67b03-113">You can also use the same event handler to handle the same event for different controls.</span></span> <span data-ttu-id="67b03-114">たとえば、フォームにコントロールのグループがある場合は、 <xref:System.Windows.Forms.RadioButton> イベントの1つのイベントハンドラーを作成し、 <xref:System.Windows.Forms.Control.Click> 各コントロールの <xref:System.Windows.Forms.Control.Click> イベントを1つのイベントハンドラーにバインドすることができます。</span><span class="sxs-lookup"><span data-stu-id="67b03-114">For example, if you have a group of <xref:System.Windows.Forms.RadioButton> controls on a form, you could create a single event handler for the <xref:System.Windows.Forms.Control.Click> event and have each control's <xref:System.Windows.Forms.Control.Click> event bound to the single event handler.</span></span> <span data-ttu-id="67b03-115">詳細については、「 [方法: Windows フォームの1つのイベントハンドラーに複数のイベントを接続](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67b03-115">For more information, see [How to: Connect Multiple Events to a Single Event Handler in Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67b03-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="67b03-116">See also</span></span>

- [<span data-ttu-id="67b03-117">Windows フォーム内でのイベント ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="67b03-117">Creating Event Handlers in Windows Forms</span></span>](creating-event-handlers-in-windows-forms.md)
- [<span data-ttu-id="67b03-118">イベントの概要</span><span class="sxs-lookup"><span data-stu-id="67b03-118">Events Overview</span></span>](events-overview-windows-forms.md)
