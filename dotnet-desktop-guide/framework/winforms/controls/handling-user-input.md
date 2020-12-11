---
title: ユーザーの入力の処理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], user input using code
- custom controls [Windows Forms], keyboard events using code
- custom controls [Windows Forms], mouse events using code
ms.assetid: d9b12787-86f6-4022-8e0f-e12d312c4af2
ms.openlocfilehash: a977061ab64dbecd5782645aa6929a77803b18c9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981043"
---
# <a name="handling-user-input"></a><span data-ttu-id="a55fd-102">ユーザーの入力の処理</span><span class="sxs-lookup"><span data-stu-id="a55fd-102">Handling User Input</span></span>

<span data-ttu-id="a55fd-103">このトピックでは、によって提供される主なキーボードイベントとマウスイベントについて説明し <xref:System.Windows.Forms.Control?displayProperty=nameWithType> ます。</span><span class="sxs-lookup"><span data-stu-id="a55fd-103">This topic describes the main keyboard and mouse events provided by <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span> <span data-ttu-id="a55fd-104">イベントを処理するときに、コントロール作成者はイベントにデリゲートを結び付けるのではなく、保護された `On`*EventName* メソッドをオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a55fd-104">When handling an event, control authors should override the protected `On`*EventName* method rather than attaching a delegate to the event.</span></span> <span data-ttu-id="a55fd-105">イベントのレビューについては、「[コンポーネントからのイベントの生成](/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a55fd-105">For a review of events, see [Raising Events from a Component](/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120)).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a55fd-106">イベントに関連付けられているデータがない場合は、基底クラスのインスタンス <xref:System.EventArgs> が引数として `On` *EventName* メソッドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="a55fd-106">If there is no data associated with an event, an instance of the base class <xref:System.EventArgs> is passed as an argument to the `On`*EventName* method.</span></span>  
  
## <a name="keyboard-events"></a><span data-ttu-id="a55fd-107">キーボード イベント</span><span class="sxs-lookup"><span data-stu-id="a55fd-107">Keyboard Events</span></span>  

 <span data-ttu-id="a55fd-108">コントロールで処理できる一般的なキーボードイベントは <xref:System.Windows.Forms.Control.KeyDown> 、、、 <xref:System.Windows.Forms.Control.KeyPress> および <xref:System.Windows.Forms.Control.KeyUp> です。</span><span class="sxs-lookup"><span data-stu-id="a55fd-108">The common keyboard events that your control can handle are <xref:System.Windows.Forms.Control.KeyDown>, <xref:System.Windows.Forms.Control.KeyPress>, and <xref:System.Windows.Forms.Control.KeyUp>.</span></span>  
  
|<span data-ttu-id="a55fd-109">イベント名</span><span class="sxs-lookup"><span data-stu-id="a55fd-109">Event Name</span></span>|<span data-ttu-id="a55fd-110">オーバーライドするメソッド</span><span class="sxs-lookup"><span data-stu-id="a55fd-110">Method to Override</span></span>|<span data-ttu-id="a55fd-111">イベントの説明</span><span class="sxs-lookup"><span data-stu-id="a55fd-111">Description of Event</span></span>|  
|----------------|------------------------|--------------------------|  
|`KeyDown`|`void OnKeyDown(KeyEventArgs)`|<span data-ttu-id="a55fd-112">キーが最初に押されたときにのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="a55fd-112">Raised only when a key is initially pressed.</span></span>|  
|`KeyPress`|`void OnKeyPress`<br /><br /> `(KeyPressEventArgs)`|<span data-ttu-id="a55fd-113">キーが押されるたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="a55fd-113">Raised every time a key is pressed.</span></span> <span data-ttu-id="a55fd-114">キーが保持されている場合は、 <xref:System.Windows.Forms.Control.KeyPress> オペレーティングシステムで定義されている繰り返し速度でイベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="a55fd-114">If a key is held down, a <xref:System.Windows.Forms.Control.KeyPress> event is raised at the repeat rate defined by the operating system.</span></span>|  
|`KeyUp`|`void OnKeyUp(KeyEventArgs)`|<span data-ttu-id="a55fd-115">キーが離されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="a55fd-115">Raised when a key is released.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="a55fd-116">キーボード入力の処理は、前の表のイベントをオーバーライドするよりもかなり複雑であり、このトピックでは触れていません。</span><span class="sxs-lookup"><span data-stu-id="a55fd-116">Handling keyboard input is considerably more complex than overriding the events in the preceding table and is beyond the scope of this topic.</span></span> <span data-ttu-id="a55fd-117">詳細については、「 [Windows フォームでのユーザー入力](../user-input-in-windows-forms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a55fd-117">For more information, see [User Input in Windows Forms](../user-input-in-windows-forms.md).</span></span>  
  
## <a name="mouse-events"></a><span data-ttu-id="a55fd-118">マウス イベント</span><span class="sxs-lookup"><span data-stu-id="a55fd-118">Mouse Events</span></span>  

 <span data-ttu-id="a55fd-119">コントロールが処理できるマウスイベントは、、、、、、 <xref:System.Windows.Forms.Control.MouseDown> <xref:System.Windows.Forms.Control.MouseEnter> <xref:System.Windows.Forms.Control.MouseHover> <xref:System.Windows.Forms.Control.MouseLeave> <xref:System.Windows.Forms.Control.MouseMove> および <xref:System.Windows.Forms.Control.MouseUp> です。</span><span class="sxs-lookup"><span data-stu-id="a55fd-119">The mouse events that your control can handle are <xref:System.Windows.Forms.Control.MouseDown>, <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseHover>, <xref:System.Windows.Forms.Control.MouseLeave>, <xref:System.Windows.Forms.Control.MouseMove>, and <xref:System.Windows.Forms.Control.MouseUp>.</span></span>  
  
|<span data-ttu-id="a55fd-120">イベント名</span><span class="sxs-lookup"><span data-stu-id="a55fd-120">Event Name</span></span>|<span data-ttu-id="a55fd-121">オーバーライドするメソッド</span><span class="sxs-lookup"><span data-stu-id="a55fd-121">Method to Override</span></span>|<span data-ttu-id="a55fd-122">イベントの説明</span><span class="sxs-lookup"><span data-stu-id="a55fd-122">Description of Event</span></span>|  
|----------------|------------------------|--------------------------|  
|`MouseDown`|`void OnMouseDown(MouseEventArgs)`|<span data-ttu-id="a55fd-123">ポインターがコントロール上にある状態でマウス ボタンが押されると発生します。</span><span class="sxs-lookup"><span data-stu-id="a55fd-123">Raised when the mouse button is pressed while the pointer is over the control.</span></span>|  
|`MouseEnter`|`void OnMouseEnter(EventArgs)`|<span data-ttu-id="a55fd-124">ポインターがコントロールの領域に初めて入ったときに発生します。</span><span class="sxs-lookup"><span data-stu-id="a55fd-124">Raised when the pointer first enters the region of the control.</span></span>|  
|`MouseHover`|`void OnMouseHover(EventArgs)`|<span data-ttu-id="a55fd-125">ポインターがコントロールの上に置かれたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="a55fd-125">Raised when the pointer hovers over the control.</span></span>|  
|`MouseLeave`|`void OnMouseLeave(EventArgs)`|<span data-ttu-id="a55fd-126">ポインターがコントロールの領域から離れると発生します。</span><span class="sxs-lookup"><span data-stu-id="a55fd-126">Raised when the pointer leaves the region of the control.</span></span>|  
|`MouseMove`|`void OnMouseMove(MouseEventArgs)`|<span data-ttu-id="a55fd-127">ポインターがコントロールの領域内で移動すると発生します。</span><span class="sxs-lookup"><span data-stu-id="a55fd-127">Raised when the pointer moves in the region of the control.</span></span>|  
|`MouseUp`|`void OnMouseUp(MouseEventArgs)`|<span data-ttu-id="a55fd-128">ポインターがコントロールの上にある状態でマウス ボタンが離されるか、ポインターがコントロールの領域から離れると発生します。</span><span class="sxs-lookup"><span data-stu-id="a55fd-128">Raised when the mouse button is released while the pointer is over the control or the pointer leaves the region of the control.</span></span>|  
  
 <span data-ttu-id="a55fd-129">次のコードフラグメントは、イベントをオーバーライドする例を示して <xref:System.Windows.Forms.Control.MouseDown> います。</span><span class="sxs-lookup"><span data-stu-id="a55fd-129">The following code fragment shows an example of overriding the <xref:System.Windows.Forms.Control.MouseDown> event.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#7)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#7)]  
  
 <span data-ttu-id="a55fd-130">次のコードフラグメントは、イベントをオーバーライドする例を示して <xref:System.Windows.Forms.Control.MouseMove> います。</span><span class="sxs-lookup"><span data-stu-id="a55fd-130">The following code fragment shows an example of overriding the <xref:System.Windows.Forms.Control.MouseMove> event.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#8](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#8)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#8](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#8)]  
  
 <span data-ttu-id="a55fd-131">次のコードフラグメントは、イベントをオーバーライドする例を示して <xref:System.Windows.Forms.Control.MouseUp> います。</span><span class="sxs-lookup"><span data-stu-id="a55fd-131">The following code fragment shows an example of overriding the <xref:System.Windows.Forms.Control.MouseUp> event.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#9)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#9)]  
  
 <span data-ttu-id="a55fd-132">`FlashTrackBar` サンプルの完全なソース コードについては、「[方法 : 進行状況を示す Windows フォーム コントロールを作成する](how-to-create-a-windows-forms-control-that-shows-progress.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a55fd-132">For the complete source code for the `FlashTrackBar` sample, see [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a55fd-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="a55fd-133">See also</span></span>

- [<span data-ttu-id="a55fd-134">Windows フォーム コントロールのイベント</span><span class="sxs-lookup"><span data-stu-id="a55fd-134">Events in Windows Forms Controls</span></span>](events-in-windows-forms-controls.md)
- [<span data-ttu-id="a55fd-135">イベントの定義</span><span class="sxs-lookup"><span data-stu-id="a55fd-135">Defining an Event</span></span>](defining-an-event-in-windows-forms-controls.md)
- [<span data-ttu-id="a55fd-136">イベント</span><span class="sxs-lookup"><span data-stu-id="a55fd-136">Events</span></span>](/dotnet/standard/events/index)
- [<span data-ttu-id="a55fd-137">Windows フォームでのユーザー入力</span><span class="sxs-lookup"><span data-stu-id="a55fd-137">User Input in Windows Forms</span></span>](../user-input-in-windows-forms.md)
