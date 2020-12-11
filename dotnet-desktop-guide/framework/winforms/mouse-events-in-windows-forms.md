---
title: マウス イベント
description: マウスイベントからマウスの位置を取得し、Windows フォームコントロールでマウスクリックイベントが発生する順序を理解する方法について説明します。
ms.date: 03/30/2017
helpviewer_keywords:
- MouseLeave event [Windows Forms]
- events [Windows Forms], mouse
- Click event [Windows Forms], raising order
- Windows Forms controls, click events
- MouseDoubleClick event [Windows Forms]
- MouseEnter event [Windows Forms]
- MouseHover event [Windows Forms]
- MouseDown event [Windows Forms]
- MouseClick event [Windows Forms]
- MouseMove event [Windows Forms]
- mouse [Windows Forms], events
- MouseUp event
ms.assetid: 8cf0070d-793b-4876-b09e-d20d28280fab
ms.openlocfilehash: 640448109961ea5fdf3600ef9e72d7d10e8c9e49
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983167"
---
# <a name="mouse-events-in-windows-forms"></a><span data-ttu-id="9eafb-103">Windows フォームにおけるマウス イベント</span><span class="sxs-lookup"><span data-stu-id="9eafb-103">Mouse Events in Windows Forms</span></span>

<span data-ttu-id="9eafb-104">マウス入力を処理する場合、通常はマウスのポインターの位置とマウス ボタンの状態を確認しようとします。</span><span class="sxs-lookup"><span data-stu-id="9eafb-104">When you handle mouse input, you usually want to know the location of the mouse pointer and the state of the mouse buttons.</span></span> <span data-ttu-id="9eafb-105">このトピックでは、マウスのイベントからこの情報を取得する方法について詳しく説明し、Windows フォーム コントロールでマウス クリック イベントが発生する順序について説明します。</span><span class="sxs-lookup"><span data-stu-id="9eafb-105">This topic provides details on how to get this information from mouse events, and explains the order in which mouse click events are raised in Windows Forms controls.</span></span> <span data-ttu-id="9eafb-106">すべてのマウスイベントの一覧と説明については、「 [Windows フォームでのマウス入力のしくみ](how-mouse-input-works-in-windows-forms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9eafb-106">For a list and description of all of the mouse events, see [How Mouse Input Works in Windows Forms](how-mouse-input-works-in-windows-forms.md).</span></span>  <span data-ttu-id="9eafb-107">「 [イベントハンドラーの概要」 (Windows フォーム)](event-handlers-overview-windows-forms.md) と「イベントの [概要」 (Windows フォーム)](events-overview-windows-forms.md)も参照してください。</span><span class="sxs-lookup"><span data-stu-id="9eafb-107">Also see [Event Handlers Overview (Windows Forms)](event-handlers-overview-windows-forms.md) and [Events Overview (Windows Forms)](events-overview-windows-forms.md).</span></span>

## <a name="mouse-information"></a><span data-ttu-id="9eafb-108">マウスの情報</span><span class="sxs-lookup"><span data-stu-id="9eafb-108">Mouse Information</span></span>

<span data-ttu-id="9eafb-109"><xref:System.Windows.Forms.MouseEventArgs> は、マウス ボタンのクリック、およびマウスの動きの追跡に関連するマウス イベントのハンドラーに送信します。</span><span class="sxs-lookup"><span data-stu-id="9eafb-109">A <xref:System.Windows.Forms.MouseEventArgs> is sent to the handlers of mouse events related to clicking a mouse button and tracking mouse movements.</span></span> <span data-ttu-id="9eafb-110"><xref:System.Windows.Forms.MouseEventArgs> は、マウスのボタンが押された、およびマウスのホイールがスクロールされたといった、クライアント座標のマウス ポインターの場所を含む、マウスの現在の状態に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="9eafb-110"><xref:System.Windows.Forms.MouseEventArgs> provides information about the current state of the mouse, including the location of the mouse pointer in client coordinates, which mouse buttons are pressed, and whether the mouse wheel has scrolled.</span></span> <span data-ttu-id="9eafb-111">マウス ポインターがコントロールの境界内に入った、または境界から出たときの通知など、いくつかのマウスイベントは、それ以上の情報はなしで <xref:System.EventArgs> をイベント ハンドラーに送信します。</span><span class="sxs-lookup"><span data-stu-id="9eafb-111">Several mouse events, such as those that simply notify when the mouse pointer has entered or left the bounds of a control, send an <xref:System.EventArgs> to the event handler with no further information.</span></span>

<span data-ttu-id="9eafb-112">マウス ボタン、または、マウス ポインターの位置の現在の状態を確認して、マウス イベントの処理を回避する場合は、<xref:System.Windows.Forms.Control> クラスの <xref:System.Windows.Forms.Control.MouseButtons%2A> プロパティと <xref:System.Windows.Forms.Control.MousePosition%2A> プロパティも使用できます。</span><span class="sxs-lookup"><span data-stu-id="9eafb-112">If you want to know the current state of the mouse buttons or the location of the mouse pointer, and you want to avoid handling a mouse event, you can also use the <xref:System.Windows.Forms.Control.MouseButtons%2A> and <xref:System.Windows.Forms.Control.MousePosition%2A> properties of the <xref:System.Windows.Forms.Control> class.</span></span> <span data-ttu-id="9eafb-113"><xref:System.Windows.Forms.Control.MouseButtons%2A> は現在押されているマウス ボタンに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="9eafb-113"><xref:System.Windows.Forms.Control.MouseButtons%2A> returns information about which mouse buttons are currently pressed.</span></span> <span data-ttu-id="9eafb-114"><xref:System.Windows.Forms.Control.MousePosition%2A> はマウス ポインターの画面の座標を返しますが、<xref:System.Windows.Forms.Cursor.Position%2A> によって返される値と同じです。</span><span class="sxs-lookup"><span data-stu-id="9eafb-114">The <xref:System.Windows.Forms.Control.MousePosition%2A> returns the screen coordinates of the mouse pointer and is equivalent to the value returned by <xref:System.Windows.Forms.Cursor.Position%2A>.</span></span>

## <a name="converting-between-screen-and-client-coordinates"></a><span data-ttu-id="9eafb-115">画面の座標とクライアント座標の間の変換</span><span class="sxs-lookup"><span data-stu-id="9eafb-115">Converting Between Screen and Client Coordinates</span></span>

<span data-ttu-id="9eafb-116">マウスの位置情報は、クライアント座標の場合と画面の座標の場合があるため、ポインターの座標システムの変換が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="9eafb-116">Because some mouse location information is in client coordinates and some is in screen coordinates, you may need to convert a point from one coordinate system to the other.</span></span> <span data-ttu-id="9eafb-117">これは、<xref:System.Windows.Forms.Control> クラスで利用できる <xref:System.Windows.Forms.Control.PointToClient%2A> メソッドと <xref:System.Windows.Forms.Control.PointToScreen%2A> メソッドを使用して簡単に実行できます。</span><span class="sxs-lookup"><span data-stu-id="9eafb-117">You can do this easily by using the <xref:System.Windows.Forms.Control.PointToClient%2A> and <xref:System.Windows.Forms.Control.PointToScreen%2A> methods available on the <xref:System.Windows.Forms.Control> class.</span></span>

## <a name="standard-click-event-behavior"></a><span data-ttu-id="9eafb-118">標準のクリック イベントの動作</span><span class="sxs-lookup"><span data-stu-id="9eafb-118">Standard Click Event Behavior</span></span>

<span data-ttu-id="9eafb-119">マウスのクリック イベントを適切な順序で処理する場合は、Windows フォーム コントロールでクリック イベントが発生した順序を知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="9eafb-119">If you want to handle mouse click events in the proper order, you need to know the order in which click events are raised in Windows Forms controls.</span></span> <span data-ttu-id="9eafb-120">Windows フォームのコントロールは、すべて、(どちらのマウス ボタンかは関係なく) マウス ボタンを押したときと離したときに同じ順序でクリック イベントを発生させますが、各コントロールについて、次のリストに記載する例外があります。</span><span class="sxs-lookup"><span data-stu-id="9eafb-120">All Windows Forms controls raise click events in the same order when a mouse button is pressed and released (regardless of which mouse button), except where noted in the following list for individual controls.</span></span> <span data-ttu-id="9eafb-121">マウス ボタンのシングル クリックに対して発生したイベントの順序を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9eafb-121">The following list shows the order of events raised for a single mouse-button click:</span></span>

1. <span data-ttu-id="9eafb-122"><xref:System.Windows.Forms.Control.MouseDown> イベント。</span><span class="sxs-lookup"><span data-stu-id="9eafb-122"><xref:System.Windows.Forms.Control.MouseDown> event.</span></span>

2. <span data-ttu-id="9eafb-123"><xref:System.Windows.Forms.Control.Click> イベント。</span><span class="sxs-lookup"><span data-stu-id="9eafb-123"><xref:System.Windows.Forms.Control.Click> event.</span></span>

3. <span data-ttu-id="9eafb-124"><xref:System.Windows.Forms.Control.MouseClick> イベント。</span><span class="sxs-lookup"><span data-stu-id="9eafb-124"><xref:System.Windows.Forms.Control.MouseClick> event.</span></span>

4. <span data-ttu-id="9eafb-125"><xref:System.Windows.Forms.Control.MouseUp> イベント。</span><span class="sxs-lookup"><span data-stu-id="9eafb-125"><xref:System.Windows.Forms.Control.MouseUp> event.</span></span>

<span data-ttu-id="9eafb-126">マウスボタンをダブルクリックしたときに発生するイベントの順序は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9eafb-126">The following is the order of events raised for a double mouse-button click:</span></span>

1. <span data-ttu-id="9eafb-127"><xref:System.Windows.Forms.Control.MouseDown> イベント。</span><span class="sxs-lookup"><span data-stu-id="9eafb-127"><xref:System.Windows.Forms.Control.MouseDown> event.</span></span>

2. <span data-ttu-id="9eafb-128"><xref:System.Windows.Forms.Control.Click> イベント。</span><span class="sxs-lookup"><span data-stu-id="9eafb-128"><xref:System.Windows.Forms.Control.Click> event.</span></span>

3. <span data-ttu-id="9eafb-129"><xref:System.Windows.Forms.Control.MouseClick> イベント。</span><span class="sxs-lookup"><span data-stu-id="9eafb-129"><xref:System.Windows.Forms.Control.MouseClick> event.</span></span>

4. <span data-ttu-id="9eafb-130"><xref:System.Windows.Forms.Control.MouseUp> イベント。</span><span class="sxs-lookup"><span data-stu-id="9eafb-130"><xref:System.Windows.Forms.Control.MouseUp> event.</span></span>

5. <span data-ttu-id="9eafb-131"><xref:System.Windows.Forms.Control.MouseDown> イベント。</span><span class="sxs-lookup"><span data-stu-id="9eafb-131"><xref:System.Windows.Forms.Control.MouseDown> event.</span></span>

6. <span data-ttu-id="9eafb-132"><xref:System.Windows.Forms.Control.DoubleClick> イベント。</span><span class="sxs-lookup"><span data-stu-id="9eafb-132"><xref:System.Windows.Forms.Control.DoubleClick> event.</span></span> <span data-ttu-id="9eafb-133">(これは、問題のコントロールで <xref:System.Windows.Forms.ControlStyles.StandardDoubleClick> スタイルのビットが `true` に設定されているかどうかに応じて異なる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9eafb-133">(This can vary, depending on whether the control in question has the <xref:System.Windows.Forms.ControlStyles.StandardDoubleClick> style bit set to `true`.</span></span> <span data-ttu-id="9eafb-134"><xref:System.Windows.Forms.ControlStyles> のビットの設定方法の詳細については、<xref:System.Windows.Forms.Control.SetStyle%2A> メソッドを参照してください。)</span><span class="sxs-lookup"><span data-stu-id="9eafb-134">For more information about how to set a <xref:System.Windows.Forms.ControlStyles> bit, see the <xref:System.Windows.Forms.Control.SetStyle%2A> method.)</span></span>

7. <span data-ttu-id="9eafb-135"><xref:System.Windows.Forms.Control.MouseDoubleClick> イベント。</span><span class="sxs-lookup"><span data-stu-id="9eafb-135"><xref:System.Windows.Forms.Control.MouseDoubleClick> event.</span></span>

8. <span data-ttu-id="9eafb-136"><xref:System.Windows.Forms.Control.MouseUp> イベント。</span><span class="sxs-lookup"><span data-stu-id="9eafb-136"><xref:System.Windows.Forms.Control.MouseUp> event.</span></span>

<span data-ttu-id="9eafb-137">マウスクリックイベントの順序を示すコード例については、「 [方法: Windows フォームコントロールでユーザー入力イベントを処理する](how-to-handle-user-input-events-in-windows-forms-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9eafb-137">For a code example that demonstrates the order of the mouse click events, see [How to: Handle User Input Events in Windows Forms Controls](how-to-handle-user-input-events-in-windows-forms-controls.md).</span></span>

### <a name="individual-controls"></a><span data-ttu-id="9eafb-138">個別のコントロール</span><span class="sxs-lookup"><span data-stu-id="9eafb-138">Individual Controls</span></span>

<span data-ttu-id="9eafb-139">次のコントロールは、標準のマウス クリック イベントの動作に準拠していません。</span><span class="sxs-lookup"><span data-stu-id="9eafb-139">The following controls do not conform to the standard mouse click event behavior:</span></span>

- <xref:System.Windows.Forms.Button>
- <xref:System.Windows.Forms.CheckBox>
- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.RadioButton>

  > [!NOTE]
  > <span data-ttu-id="9eafb-140"><xref:System.Windows.Forms.ComboBox> コントロールについて、ユーザーが編集フィールド、ボタン、またはリスト内の項目をクリックすると、後述するイベントの動作が発生します。</span><span class="sxs-lookup"><span data-stu-id="9eafb-140">For the <xref:System.Windows.Forms.ComboBox> control, the event behavior detailed later occurs if the user clicks on the edit field, the button, or on an item within the list.</span></span>

  - <span data-ttu-id="9eafb-141">左クリック : <xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="9eafb-141">Left click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>

  - <span data-ttu-id="9eafb-142">右クリック : クリック イベントは発生しません</span><span class="sxs-lookup"><span data-stu-id="9eafb-142">Right click: No click events raised</span></span>

  - <span data-ttu-id="9eafb-143">左ダブルクリック : <xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick>、<xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="9eafb-143">Left double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>

  - <span data-ttu-id="9eafb-144">右ダブルクリック : クリック イベントは発生しません</span><span class="sxs-lookup"><span data-stu-id="9eafb-144">Right double-click: No click events raised</span></span>

- <span data-ttu-id="9eafb-145"><xref:System.Windows.Forms.TextBox>、<xref:System.Windows.Forms.RichTextBox>、<xref:System.Windows.Forms.ListBox>、<xref:System.Windows.Forms.MaskedTextBox> および <xref:System.Windows.Forms.CheckedListBox> の各コントロール</span><span class="sxs-lookup"><span data-stu-id="9eafb-145"><xref:System.Windows.Forms.TextBox>, <xref:System.Windows.Forms.RichTextBox>, <xref:System.Windows.Forms.ListBox>, <xref:System.Windows.Forms.MaskedTextBox>, and <xref:System.Windows.Forms.CheckedListBox> controls</span></span>

  > [!NOTE]
  > <span data-ttu-id="9eafb-146">ユーザーがこれらのコントロール内で任意の場所をクリックすると、後述するイベントの動作が発生します。</span><span class="sxs-lookup"><span data-stu-id="9eafb-146">The event behavior detailed later occurs when the user clicks anywhere within these controls.</span></span>

  - <span data-ttu-id="9eafb-147">左クリック : <xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="9eafb-147">Left click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>

  - <span data-ttu-id="9eafb-148">右クリック : クリック イベントは発生しません</span><span class="sxs-lookup"><span data-stu-id="9eafb-148">Right click: No click events raised</span></span>

  - <span data-ttu-id="9eafb-149">左ダブルクリック : <xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick>、<xref:System.Windows.Forms.Control.DoubleClick>、<xref:System.Windows.Forms.Control.MouseDoubleClick></span><span class="sxs-lookup"><span data-stu-id="9eafb-149">Left double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>, <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span></span>

  - <span data-ttu-id="9eafb-150">右ダブルクリック : クリック イベントは発生しません</span><span class="sxs-lookup"><span data-stu-id="9eafb-150">Right double-click: No click events raised</span></span>

- <span data-ttu-id="9eafb-151"><xref:System.Windows.Forms.ListView> コントロール</span><span class="sxs-lookup"><span data-stu-id="9eafb-151"><xref:System.Windows.Forms.ListView> control</span></span>

  > [!NOTE]
  > <span data-ttu-id="9eafb-152">ユーザーが <xref:System.Windows.Forms.ListView> コントロールの項目をクリックした場合のみ、後述するイベントの動作が発生します。</span><span class="sxs-lookup"><span data-stu-id="9eafb-152">The event behavior detailed later occurs only when the user clicks on the items in the <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="9eafb-153">コントロールのその他の場所をクリックした場合、イベントは発生しません。</span><span class="sxs-lookup"><span data-stu-id="9eafb-153">No events are raised for clicks anywhere else on the control.</span></span> <span data-ttu-id="9eafb-154">後述するイベントに加えて、<xref:System.Windows.Forms.ListView.BeforeLabelEdit> と <xref:System.Windows.Forms.ListView.AfterLabelEdit> のイベントがあり、<xref:System.Windows.Forms.ListView> コントロールによる検証を使用する場合のためにまとめておきます。</span><span class="sxs-lookup"><span data-stu-id="9eafb-154">In addition to the events described later, there are the <xref:System.Windows.Forms.ListView.BeforeLabelEdit> and <xref:System.Windows.Forms.ListView.AfterLabelEdit> events, which may be of interest to you if you want to use validation with the <xref:System.Windows.Forms.ListView> control.</span></span>

  - <span data-ttu-id="9eafb-155">左クリック : <xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="9eafb-155">Left click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>

  - <span data-ttu-id="9eafb-156">右クリック : <xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="9eafb-156">Right click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>

  - <span data-ttu-id="9eafb-157">左ダブルクリック : <xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick>、<xref:System.Windows.Forms.Control.DoubleClick>、<xref:System.Windows.Forms.Control.MouseDoubleClick></span><span class="sxs-lookup"><span data-stu-id="9eafb-157">Left double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span></span>

  - <span data-ttu-id="9eafb-158">右ダブルクリック : <xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick>、<xref:System.Windows.Forms.Control.DoubleClick>、<xref:System.Windows.Forms.Control.MouseDoubleClick></span><span class="sxs-lookup"><span data-stu-id="9eafb-158">Right double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span></span>

- <span data-ttu-id="9eafb-159"><xref:System.Windows.Forms.TreeView> コントロール</span><span class="sxs-lookup"><span data-stu-id="9eafb-159"><xref:System.Windows.Forms.TreeView> control</span></span>

  > [!NOTE]
  > <span data-ttu-id="9eafb-160">ユーザーが項目自体をクリックするか、<xref:System.Windows.Forms.TreeView> コントロールの項目の右側をクリックした場合にのみ、後述するイベントの動作が発生します。</span><span class="sxs-lookup"><span data-stu-id="9eafb-160">The event behavior detailed later occurs only when the user clicks on the items themselves or to the right of the items in the <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="9eafb-161">コントロールのその他の場所をクリックした場合、イベントは発生しません。</span><span class="sxs-lookup"><span data-stu-id="9eafb-161">No events are raised for clicks anywhere else on the control.</span></span> <span data-ttu-id="9eafb-162">後述するイベントに加えて、<xref:System.Windows.Forms.TreeView.BeforeCheck>、<xref:System.Windows.Forms.TreeView.BeforeSelect>、<xref:System.Windows.Forms.TreeView.BeforeLabelEdit>、<xref:System.Windows.Forms.TreeView.AfterSelect>、<xref:System.Windows.Forms.TreeView.AfterCheck>、および <xref:System.Windows.Forms.TreeView.AfterLabelEdit> の各イベントがあり、<xref:System.Windows.Forms.TreeView> コントロールを持つ検証を使用する場合のためにまとめておきます。</span><span class="sxs-lookup"><span data-stu-id="9eafb-162">In addition to those described later, there are the <xref:System.Windows.Forms.TreeView.BeforeCheck>, <xref:System.Windows.Forms.TreeView.BeforeSelect>, <xref:System.Windows.Forms.TreeView.BeforeLabelEdit>, <xref:System.Windows.Forms.TreeView.AfterSelect>, <xref:System.Windows.Forms.TreeView.AfterCheck>, and <xref:System.Windows.Forms.TreeView.AfterLabelEdit> events, which may be of interest to you if you want to use validation with the <xref:System.Windows.Forms.TreeView> control.</span></span>

  - <span data-ttu-id="9eafb-163">左クリック : <xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="9eafb-163">Left click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>

  - <span data-ttu-id="9eafb-164">右クリック : <xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="9eafb-164">Right click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>

  - <span data-ttu-id="9eafb-165">左ダブルクリック : <xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick>、<xref:System.Windows.Forms.Control.DoubleClick>、<xref:System.Windows.Forms.Control.MouseDoubleClick></span><span class="sxs-lookup"><span data-stu-id="9eafb-165">Left double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span></span>

  - <span data-ttu-id="9eafb-166">右ダブルクリック : <xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick>、<xref:System.Windows.Forms.Control.DoubleClick>、<xref:System.Windows.Forms.Control.MouseDoubleClick></span><span class="sxs-lookup"><span data-stu-id="9eafb-166">Right double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span></span>

### <a name="painting-behavior-of-toggle-controls"></a><span data-ttu-id="9eafb-167">トグルコントロールの描画動作</span><span class="sxs-lookup"><span data-stu-id="9eafb-167">Painting behavior of toggle controls</span></span>

<span data-ttu-id="9eafb-168"><xref:System.Windows.Forms.ButtonBase> クラスから派生するコントロールなど、切り替えコントロールには、次のようなマウス クリック イベントと組み合わせた独自の描画の動作があります。</span><span class="sxs-lookup"><span data-stu-id="9eafb-168">Toggle controls, such as the controls deriving from the <xref:System.Windows.Forms.ButtonBase> class, have the following distinctive painting behavior in combination with mouse click events:</span></span>

1. <span data-ttu-id="9eafb-169">ユーザーがマウス ボタンを押します。</span><span class="sxs-lookup"><span data-stu-id="9eafb-169">The user presses the mouse button.</span></span>

2. <span data-ttu-id="9eafb-170">押された状態で、コントロールが描画します。</span><span class="sxs-lookup"><span data-stu-id="9eafb-170">The control paints in the pressed state.</span></span>

3. <span data-ttu-id="9eafb-171"><xref:System.Windows.Forms.Control.MouseDown> イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="9eafb-171">The <xref:System.Windows.Forms.Control.MouseDown> event is raised.</span></span>

4. <span data-ttu-id="9eafb-172">ユーザーがマウス ボタンを離します。</span><span class="sxs-lookup"><span data-stu-id="9eafb-172">The user releases the mouse button.</span></span>

5. <span data-ttu-id="9eafb-173">離した状態でコントロールが描画します。</span><span class="sxs-lookup"><span data-stu-id="9eafb-173">The control paints in the raised state.</span></span>

6. <span data-ttu-id="9eafb-174"><xref:System.Windows.Forms.Control.Click> イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="9eafb-174">The <xref:System.Windows.Forms.Control.Click> event is raised.</span></span>

7. <span data-ttu-id="9eafb-175"><xref:System.Windows.Forms.Control.MouseClick> イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="9eafb-175">The <xref:System.Windows.Forms.Control.MouseClick> event is raised.</span></span>

8. <span data-ttu-id="9eafb-176"><xref:System.Windows.Forms.Control.MouseUp> イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="9eafb-176">The <xref:System.Windows.Forms.Control.MouseUp> event is raised.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9eafb-177">マウス ボタンが押されているときにユーザーがポインターを切り替えコントロールの外に移動した (例 : <xref:System.Windows.Forms.Button> コントロールを押しているときにマウスを移動した) 場合、離された状態で切り替えコントロールが描画し、<xref:System.Windows.Forms.Control.MouseUp> イベントのみが発生します。</span><span class="sxs-lookup"><span data-stu-id="9eafb-177">If the user moves the pointer out of the toggle control while the mouse button is down (such as moving the mouse off the <xref:System.Windows.Forms.Button> control while it is pressed), the toggle control will paint in the raised state and only the <xref:System.Windows.Forms.Control.MouseUp> event occurs.</span></span> <span data-ttu-id="9eafb-178"><xref:System.Windows.Forms.Control.Click> イベントまたは <xref:System.Windows.Forms.Control.MouseClick> イベントは、このような状況では発生しません。</span><span class="sxs-lookup"><span data-stu-id="9eafb-178">The <xref:System.Windows.Forms.Control.Click> or <xref:System.Windows.Forms.Control.MouseClick> events will not occur in this situation.</span></span>

## <a name="see-also"></a><span data-ttu-id="9eafb-179">関連項目</span><span class="sxs-lookup"><span data-stu-id="9eafb-179">See also</span></span>

- [<span data-ttu-id="9eafb-180">Windows フォーム アプリケーションにおけるマウス入力</span><span class="sxs-lookup"><span data-stu-id="9eafb-180">Mouse Input in a Windows Forms Application</span></span>](mouse-input-in-a-windows-forms-application.md)
