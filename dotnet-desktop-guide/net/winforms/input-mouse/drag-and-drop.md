---
title: ドラッグ アンド ドロップによるマウスの動作
description: マウスを使ってドラッグ アンド ドロップを実行する方法など、Windows フォーム上のドラッグ アンド ドロップの動作について説明します。
ms.date: 10/26/2020
ms.topic: conceptual
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag and drop [Windows Forms], Windows Forms
- Windows Forms, drag and drop
ms.openlocfilehash: d434b0f0e80c610fffeea26a6fff44b43ca07fed
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96942162"
---
# <a name="drag-and-drop-mouse-behavior-overview-windows-forms-net"></a><span data-ttu-id="f1850-103">ドラッグ アンド ドロップによるマウス動作の概要 (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="f1850-103">Drag-and-drop mouse behavior overview (Windows Forms .NET)</span></span>

<span data-ttu-id="f1850-104">Windows フォームには、ドラッグ アンド ドロップの動作を実装する一連のメソッド、イベント、およびクラスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f1850-104">Windows Forms includes a set of methods, events, and classes that implement drag-and-drop behavior.</span></span> <span data-ttu-id="f1850-105">このトピックでは、Windows フォームでのドラッグ アンド ドロップのサポートの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="f1850-105">This topic provides an overview of the drag-and-drop support in Windows Forms.</span></span><!-- TODO Also see [Drag-and-Drop Operations and Clipboard Support](./advanced/drag-and-drop-operations-and-clipboard-support.md).-->

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="drag-and-drop-events"></a><span data-ttu-id="f1850-106">ドラッグ アンド ドロップのイベント</span><span class="sxs-lookup"><span data-stu-id="f1850-106">Drag-and-drop events</span></span>

<span data-ttu-id="f1850-107">ドラッグ アンド ドロップ操作のイベントには、ドラッグ アンド ドロップ操作の現在のターゲットで発生するイベントと、ドラッグ アンド ドロップ操作のソースで発生するイベントの 2 つのカテゴリがあります。</span><span class="sxs-lookup"><span data-stu-id="f1850-107">There are two categories of events in a drag and drop operation: events that occur on the current target of the drag-and-drop operation, and events that occur on the source of the drag and drop operation.</span></span> <span data-ttu-id="f1850-108">ドラッグ アンド ドロップ操作を実行するには、これらのイベントを処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1850-108">To perform drag-and-drop operations, you must handle these events.</span></span> <span data-ttu-id="f1850-109">これらのイベントのイベント引数で使用できる情報を操作することにより、ドラッグ アンド ドロップ操作を簡単に容易にすることができます。</span><span class="sxs-lookup"><span data-stu-id="f1850-109">By working with the information available in the event arguments of these events, you can easily facilitate drag-and-drop operations.</span></span>

## <a name="events-on-the-current-drop-target"></a><span data-ttu-id="f1850-110">現在のドロップ ターゲットのイベント</span><span class="sxs-lookup"><span data-stu-id="f1850-110">Events on the current drop target</span></span>

<span data-ttu-id="f1850-111">次の表は、ドラッグ アンド ドロップ操作の現在のターゲットで発生するイベントを示します。</span><span class="sxs-lookup"><span data-stu-id="f1850-111">The following table shows the events that occur on the current target of a drag-and-drop operation.</span></span>

| <span data-ttu-id="f1850-112">マウス イベント</span><span class="sxs-lookup"><span data-stu-id="f1850-112">Mouse Event</span></span>                                   | <span data-ttu-id="f1850-113">説明</span><span class="sxs-lookup"><span data-stu-id="f1850-113">Description</span></span>                                                                                                                                                                                            |
|-----------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <xref:System.Windows.Forms.Control.DragEnter> | <span data-ttu-id="f1850-114">このイベントは、オブジェクトがコントロールの境界内にドラッグされると発生します。</span><span class="sxs-lookup"><span data-stu-id="f1850-114">This event occurs when an object is dragged into the control's bounds.</span></span> <span data-ttu-id="f1850-115">このイベントのハンドラーは、型 <xref:System.Windows.Forms.DragEventArgs> の引数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="f1850-115">The handler for this event receives an argument of type <xref:System.Windows.Forms.DragEventArgs>.</span></span>                              |
| <xref:System.Windows.Forms.Control.DragOver>  | <span data-ttu-id="f1850-116">このイベントは、マウス ポインターがコントロールの境界内にある間にオブジェクトがドラッグされるときに発生します。</span><span class="sxs-lookup"><span data-stu-id="f1850-116">This event occurs when an object is dragged while the mouse pointer is within the control's bounds.</span></span> <span data-ttu-id="f1850-117">このイベントのハンドラーは、型 <xref:System.Windows.Forms.DragEventArgs> の引数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="f1850-117">The handler for this event receives an argument of type <xref:System.Windows.Forms.DragEventArgs>.</span></span> |
| <xref:System.Windows.Forms.Control.DragDrop>  | <span data-ttu-id="f1850-118">このイベントは、ドラッグ アンド ドロップ操作が完了したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="f1850-118">This event occurs when a drag-and-drop operation is completed.</span></span> <span data-ttu-id="f1850-119">このイベントのハンドラーは、型 <xref:System.Windows.Forms.DragEventArgs> の引数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="f1850-119">The handler for this event receives an argument of type <xref:System.Windows.Forms.DragEventArgs>.</span></span>                                      |
| <xref:System.Windows.Forms.Control.DragLeave> | <span data-ttu-id="f1850-120">このイベントは、オブジェクトがコントロールの境界外にドラッグされたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="f1850-120">This event occurs when an object is dragged out of the control's bounds.</span></span> <span data-ttu-id="f1850-121">このイベントのハンドラーは、型 <xref:System.EventArgs> の引数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="f1850-121">The handler for this event receives an argument of type <xref:System.EventArgs>.</span></span>                                              |

<span data-ttu-id="f1850-122"><xref:System.Windows.Forms.DragEventArgs> クラスは、マウスのポインターの場所、マウス ボタンとキーボードの修飾子キーの現在の状態、ドラッグされているデータ、およびドラッグ イベントのソースによって許可される操作と操作に対するターゲットのドロップの効果を指定する <xref:System.Windows.Forms.DragDropEffects> の値を提供します。</span><span class="sxs-lookup"><span data-stu-id="f1850-122">The <xref:System.Windows.Forms.DragEventArgs> class provides the location of the mouse pointer, the current state of the mouse buttons and modifier keys of the keyboard, the data being dragged, and <xref:System.Windows.Forms.DragDropEffects> values that specify the operations allowed by the source of the drag event and the target drop effect for the operation.</span></span>

## <a name="events-on-the-drop-source"></a><span data-ttu-id="f1850-123">ドロップ ソースのイベント</span><span class="sxs-lookup"><span data-stu-id="f1850-123">Events on the drop source</span></span>

<span data-ttu-id="f1850-124">次の表は、ドラッグ アンド ドロップ操作のソースで発生するイベントを示します。</span><span class="sxs-lookup"><span data-stu-id="f1850-124">The following table shows the events that occur on the source of the drag-and-drop operation.</span></span>

|<span data-ttu-id="f1850-125">マウス イベント</span><span class="sxs-lookup"><span data-stu-id="f1850-125">Mouse Event</span></span>|<span data-ttu-id="f1850-126">説明</span><span class="sxs-lookup"><span data-stu-id="f1850-126">Description</span></span>|
|-----------------|-----------------|
|<xref:System.Windows.Forms.Control.GiveFeedback>|<span data-ttu-id="f1850-127">このイベントは、ドラッグ操作中に発生します。</span><span class="sxs-lookup"><span data-stu-id="f1850-127">This event occurs during a drag operation.</span></span> <span data-ttu-id="f1850-128">マウス ポインターを変更するなど、ドラッグ アンド ドロップ操作が実行されていることを示す視覚上の手掛かりをユーザーに示す機会を提供します。</span><span class="sxs-lookup"><span data-stu-id="f1850-128">It provides an opportunity to give a visual cue to the user that the drag-and-drop operation is occurring, such as changing the mouse pointer.</span></span> <span data-ttu-id="f1850-129">このイベントのハンドラーは、型 <xref:System.Windows.Forms.GiveFeedbackEventArgs> の引数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="f1850-129">The handler for this event receives an argument of type <xref:System.Windows.Forms.GiveFeedbackEventArgs>.</span></span>|
|<xref:System.Windows.Forms.Control.QueryContinueDrag>|<span data-ttu-id="f1850-130">このイベントは、ドラッグ アンド ドロップ操作中に発生し、ドラッグ ソースがドラッグ アンド ドロップ操作をキャンセルする必要があるかどうかを決定できるようにします。</span><span class="sxs-lookup"><span data-stu-id="f1850-130">This event is raised during a drag-and-drop operation and enables the drag source to determine whether the drag-and-drop operation should be canceled.</span></span> <span data-ttu-id="f1850-131">このイベントのハンドラーは、型 <xref:System.Windows.Forms.QueryContinueDragEventArgs> の引数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="f1850-131">The handler for this event receives an argument of type <xref:System.Windows.Forms.QueryContinueDragEventArgs>.</span></span>|

<span data-ttu-id="f1850-132"><xref:System.Windows.Forms.QueryContinueDragEventArgs> クラスは、マウス ボタンとキーボードの修飾子キーの現在の状態、ESC キーを押したかどうかを指定する値、およびドラッグ アンド ドロップ操作を続行するかどうかを指定するために設定できる <xref:System.Windows.Forms.DragAction> の値を提供します。</span><span class="sxs-lookup"><span data-stu-id="f1850-132">The <xref:System.Windows.Forms.QueryContinueDragEventArgs> class provides the current state of the mouse buttons and modifier keys of the keyboard, a value specifying whether the ESC key was pressed, and a <xref:System.Windows.Forms.DragAction> value that can be set to specify whether the drag-and-drop operation should continue.</span></span>

## <a name="performing-drag-and-drop"></a><span data-ttu-id="f1850-133">ドラッグ アンド ドロップの実行</span><span class="sxs-lookup"><span data-stu-id="f1850-133">Performing drag-and-drop</span></span>

<span data-ttu-id="f1850-134">ドラッグ アンド ドロップ操作には、**ドラッグ ソース** と **ドロップ ターゲット** という 2 つのコンポーネントが常に含まれています。</span><span class="sxs-lookup"><span data-stu-id="f1850-134">Drag-and-drop operations always involve two components, the **drag source** and the **drop target**.</span></span> <span data-ttu-id="f1850-135">ドラッグ アンド ドロップ操作を開始するには、コントロールをソースとして指定し、<xref:System.Windows.Forms.Control.MouseDown> イベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="f1850-135">To start a drag-and-drop operation, designate a control as the source and handle the <xref:System.Windows.Forms.Control.MouseDown> event.</span></span> <span data-ttu-id="f1850-136">イベント ハンドラーで、ドロップに関連付けられたデータと <xref:System.Windows.DragDropEffects> 値を指定して <xref:System.Windows.DragDrop.DoDragDrop%2A> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f1850-136">In the event handler, call the <xref:System.Windows.DragDrop.DoDragDrop%2A> method providing the data associated with the drop and the a <xref:System.Windows.DragDropEffects> value.</span></span>

<span data-ttu-id="f1850-137">ターゲット コントロールの <xref:System.Windows.Forms.Control.AllowDrop> プロパティを `true` に設定して、そのコントロールでドラッグ アンド ドロップ操作を受け入れることができるようにします。</span><span class="sxs-lookup"><span data-stu-id="f1850-137">Set the target control's <xref:System.Windows.Forms.Control.AllowDrop> property set to `true` to allow that control to accept a drag-and-drop operation.</span></span> <span data-ttu-id="f1850-138">ターゲットによって 2 つのイベントが処理されます。1 つ目は、<xref:System.Windows.Forms.Control.DragOver> など、コントロールに対して行われているドラッグに応答するイベントです。</span><span class="sxs-lookup"><span data-stu-id="f1850-138">The target handles two events, first an event in response to the drag being over the control, such as <xref:System.Windows.Forms.Control.DragOver>.</span></span> <span data-ttu-id="f1850-139">また、2 つ目は、ドロップ アクション自体のイベントです (<xref:System.Windows.Forms.Control.DragDrop>)。</span><span class="sxs-lookup"><span data-stu-id="f1850-139">And a second event which is the drop action itself, <xref:System.Windows.Forms.Control.DragDrop>.</span></span>

<span data-ttu-id="f1850-140">次の例は、<xref:System.Windows.Forms.Label> コントロールから <xref:System.Windows.Forms.TextBox> へのドラッグを示しています。</span><span class="sxs-lookup"><span data-stu-id="f1850-140">The following example demonstrates a drag from a <xref:System.Windows.Forms.Label> control to a <xref:System.Windows.Forms.TextBox>.</span></span> <span data-ttu-id="f1850-141">ドラッグが完了すると、`TextBox` は、ラベルのテキストを自身に割り当てることで応答します。</span><span class="sxs-lookup"><span data-stu-id="f1850-141">When the drag is completed, the `TextBox` responds by assigning the label's text to itself.</span></span>

```csharp
// Initiate the drag
private void label1_MouseDown(object sender, MouseEventArgs e) =>
    DoDragDrop(((Label)sender).Text, DragDropEffects.All);

// Set the effect filter and allow the drop on this control
private void textBox1_DragOver(object sender, DragEventArgs e) =>
    e.Effect = DragDropEffects.All;

// React to the drop on this control
private void textBox1_DragDrop(object sender, DragEventArgs e) =>
    textBox1.Text = (string)e.Data.GetData(typeof(string));
```

```vb
' Initiate the drag
Private Sub Label1_MouseDown(sender As Object, e As MouseEventArgs)
    DoDragDrop(DirectCast(sender, Label).Text, DragDropEffects.All)
End Sub

' Set the effect filter and allow the drop on this control
Private Sub TextBox1_DragOver(sender As Object, e As DragEventArgs)
    e.Effect = DragDropEffects.All
End Sub

' React to the drop on this control
Private Sub TextBox1_DragDrop(sender As Object, e As DragEventArgs)
    TextBox1.Text = e.Data.GetData(GetType(String))
End Sub
```

<span data-ttu-id="f1850-142">ドラッグの効果の詳細については、<xref:System.Windows.Forms.DragEventArgs.Data%2A> と <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A> に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1850-142">For more information about the drag effects, see <xref:System.Windows.Forms.DragEventArgs.Data%2A> and <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.</span></span>

## <a name="see-also"></a><span data-ttu-id="f1850-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1850-143">See also</span></span>

- [<span data-ttu-id="f1850-144">マウスの使用の概要 (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="f1850-144">Overview of using the mouse (Windows Forms .NET)</span></span>](overview.md)
- <xref:System.Windows.Forms.Control.DragDrop?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.DragEnter?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.DragLeave?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.DragOver?displayProperty=nameWithType>
