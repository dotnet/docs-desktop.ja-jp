---
title: 'チュートリアル: 標準メニュー項目をフォームに用意する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- menu items [Windows Forms], standard
- toolbars [Windows Forms], walkthroughs
- StatusStrip control [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: dac37d98-589e-4d6d-9673-6437e8943122
ms.openlocfilehash: ee80aad445c00bb4b98b49c80495fa512150bcef
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982708"
---
# <a name="walkthrough-providing-standard-menu-items-to-a-form"></a><span data-ttu-id="84017-102">チュートリアル: 標準メニュー項目をフォームに用意する</span><span class="sxs-lookup"><span data-stu-id="84017-102">Walkthrough: Providing Standard Menu Items to a Form</span></span>

<span data-ttu-id="84017-103">フォームの標準のメニューを <xref:System.Windows.Forms.MenuStrip> コントロールに提供できます。</span><span class="sxs-lookup"><span data-stu-id="84017-103">You can provide a standard menu for your forms with the <xref:System.Windows.Forms.MenuStrip> control.</span></span>

<span data-ttu-id="84017-104">このチュートリアルでは、コントロールを使用して標準メニューを作成する方法について説明 <xref:System.Windows.Forms.MenuStrip> します。</span><span class="sxs-lookup"><span data-stu-id="84017-104">This walkthrough demonstrates how to use a <xref:System.Windows.Forms.MenuStrip> control to create a standard menu.</span></span> <span data-ttu-id="84017-105">フォームは、ユーザーがメニュー項目を選択したときにも応答します。</span><span class="sxs-lookup"><span data-stu-id="84017-105">The form also responds when a user selects a menu item.</span></span> <span data-ttu-id="84017-106">このチュートリアルでは、次のタスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="84017-106">The following tasks are illustrated in this walkthrough:</span></span>

- <span data-ttu-id="84017-107">Windows フォームプロジェクトを作成しています。</span><span class="sxs-lookup"><span data-stu-id="84017-107">Creating a Windows Forms project.</span></span>

- <span data-ttu-id="84017-108">標準メニューを作成する。</span><span class="sxs-lookup"><span data-stu-id="84017-108">Creating a standard menu.</span></span>

- <span data-ttu-id="84017-109">コントロールを作成する <xref:System.Windows.Forms.StatusStrip> 。</span><span class="sxs-lookup"><span data-stu-id="84017-109">Creating a <xref:System.Windows.Forms.StatusStrip> control.</span></span>

- <span data-ttu-id="84017-110">メニュー項目の選択を処理しています。</span><span class="sxs-lookup"><span data-stu-id="84017-110">Handling menu item selection.</span></span>

<span data-ttu-id="84017-111">完了すると、コントロールにメニュー項目の選択項目を表示する標準メニューを持つフォームが作成され <xref:System.Windows.Forms.StatusStrip> ます。</span><span class="sxs-lookup"><span data-stu-id="84017-111">When you are finished, you will have a form with a standard menu that displays menu item selections in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>

<span data-ttu-id="84017-112">このトピックのコードを単一のリストとしてコピーする方法については、「 [方法: フォームに標準メニュー項目を提供](how-to-provide-standard-menu-items-to-a-form.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84017-112">To copy the code in this topic as a single listing, see [How to: Provide Standard Menu Items to a Form](how-to-provide-standard-menu-items-to-a-form.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="84017-113">前提条件</span><span class="sxs-lookup"><span data-stu-id="84017-113">Prerequisites</span></span>

<span data-ttu-id="84017-114">このチュートリアルを完了するには、Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="84017-114">You'll need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="84017-115">プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="84017-115">Create the project</span></span>

1. <span data-ttu-id="84017-116">Visual Studio で、 **standardmenuform** という名前の Windows アプリケーションプロジェクトを作成します ([**ファイル**] [  >  **新しい**  >  **プロジェクト**] [  >  **Visual C#** ] または [ **Visual Basic**  >  **クラシックデスクトップ**  >  **Windows フォームアプリケーション**])。</span><span class="sxs-lookup"><span data-stu-id="84017-116">In Visual Studio, create a Windows application project called **StandardMenuForm** (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="84017-117">[Windows フォームデザイナーで、フォームを選択します。</span><span class="sxs-lookup"><span data-stu-id="84017-117">In the Windows Forms Designer, select the form.</span></span>

## <a name="create-a-standard-menu"></a><span data-ttu-id="84017-118">標準メニューを作成する</span><span class="sxs-lookup"><span data-stu-id="84017-118">Create a standard menu</span></span>

<span data-ttu-id="84017-119">Windows フォームデザイナーでは、標準の <xref:System.Windows.Forms.MenuStrip> メニュー項目を使用してコントロールを自動的に設定できます。</span><span class="sxs-lookup"><span data-stu-id="84017-119">The Windows Forms Designer can automatically populate a <xref:System.Windows.Forms.MenuStrip> control with standard menu items.</span></span>

1. <span data-ttu-id="84017-120">[ **ツールボックス**] から <xref:System.Windows.Forms.MenuStrip> コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="84017-120">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto your form.</span></span>

2. <span data-ttu-id="84017-121"><xref:System.Windows.Forms.MenuStrip>コントロールの [デザイナーアクション] グリフ ( ![ 小さい黒い矢印 ](./media/designer-actions-glyph.gif) ) をクリックし、[**標準項目の挿入**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="84017-121">Click the <xref:System.Windows.Forms.MenuStrip> control's designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) and select **Insert Standard Items**.</span></span>

     <span data-ttu-id="84017-122"><xref:System.Windows.Forms.MenuStrip>コントロールには、標準のメニュー項目が設定されます。</span><span class="sxs-lookup"><span data-stu-id="84017-122">The <xref:System.Windows.Forms.MenuStrip> control is populated with the standard menu items.</span></span>

3. <span data-ttu-id="84017-123">既定のメニュー項目と対応するアイコンを表示するには、[ **ファイル** ] メニュー項目をクリックします。</span><span class="sxs-lookup"><span data-stu-id="84017-123">Click the **File** menu item to see its default menu items and corresponding icons.</span></span>

## <a name="create-a-statusstrip-control"></a><span data-ttu-id="84017-124">StatusStrip コントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="84017-124">Create a StatusStrip control</span></span>

<span data-ttu-id="84017-125">コントロールを使用し <xref:System.Windows.Forms.StatusStrip> て、Windows フォームアプリケーションの状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="84017-125">Use the <xref:System.Windows.Forms.StatusStrip> control to display status for your Windows Forms applications.</span></span> <span data-ttu-id="84017-126">現在の例では、ユーザーが選択したメニュー項目がコントロールに表示され <xref:System.Windows.Forms.StatusStrip> ます。</span><span class="sxs-lookup"><span data-stu-id="84017-126">In the current example, menu items selected by the user are displayed in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>

1. <span data-ttu-id="84017-127">[ **ツールボックス**] から <xref:System.Windows.Forms.StatusStrip> コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="84017-127">From the **Toolbox**, drag a <xref:System.Windows.Forms.StatusStrip> control onto your form.</span></span>

     <span data-ttu-id="84017-128">コントロールは、 <xref:System.Windows.Forms.StatusStrip> フォームの下部に自動的にドッキングされます。</span><span class="sxs-lookup"><span data-stu-id="84017-128">The <xref:System.Windows.Forms.StatusStrip> control automatically docks to the bottom of the form.</span></span>

2. <span data-ttu-id="84017-129">コントロール <xref:System.Windows.Forms.StatusStrip> のドロップダウンボタンをクリックし、[ **statuslabel** ] を選択してコントロールをコントロールに追加し <xref:System.Windows.Forms.ToolStripStatusLabel> <xref:System.Windows.Forms.StatusStrip> ます。</span><span class="sxs-lookup"><span data-stu-id="84017-129">Click the <xref:System.Windows.Forms.StatusStrip> control's drop-down button and select **StatusLabel** to add a <xref:System.Windows.Forms.ToolStripStatusLabel> control to the <xref:System.Windows.Forms.StatusStrip> control.</span></span>

## <a name="handle-item-selection"></a><span data-ttu-id="84017-130">項目の選択の処理</span><span class="sxs-lookup"><span data-stu-id="84017-130">Handle item selection</span></span>

<span data-ttu-id="84017-131"><xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked>ユーザーがメニュー項目を選択したときに応答するイベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="84017-131">Handle the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event to respond when the user selects a menu item.</span></span>

1. <span data-ttu-id="84017-132">「標準メニューの作成」セクションで作成した [ **ファイル** ] メニュー項目をクリックします。</span><span class="sxs-lookup"><span data-stu-id="84017-132">Click the **File** menu item that you created in the Creating a Standard Menu section.</span></span>

2. <span data-ttu-id="84017-133">**[プロパティ]** ウィンドウで、**[イベント]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="84017-133">In the **Properties** window, click **Events**.</span></span>

3. <span data-ttu-id="84017-134"><xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> イベントをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="84017-134">Double-click the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>

     <span data-ttu-id="84017-135">Windows フォームデザイナーは、イベントのイベントハンドラーを生成し <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> ます。</span><span class="sxs-lookup"><span data-stu-id="84017-135">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>

4. <span data-ttu-id="84017-136">イベントハンドラーに次のコードを挿入します。</span><span class="sxs-lookup"><span data-stu-id="84017-136">Insert the following code into the event handler.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]

5. <span data-ttu-id="84017-137">`UpdateStatus`ユーティリティメソッドの定義をフォームに挿入します。</span><span class="sxs-lookup"><span data-stu-id="84017-137">Insert the `UpdateStatus` utility method definition into the form.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]

## <a name="checkpoint--test-your-form"></a><span data-ttu-id="84017-138">チェックポイント-フォームのテスト</span><span class="sxs-lookup"><span data-stu-id="84017-138">Checkpoint -test your form</span></span>

1. <span data-ttu-id="84017-139">**F5** キーを押して、フォームをコンパイルして実行します。</span><span class="sxs-lookup"><span data-stu-id="84017-139">Press **F5** to compile and run your form.</span></span>

2. <span data-ttu-id="84017-140">[ **ファイル** ] メニュー項目をクリックして、メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="84017-140">Click the **File** menu item to open the menu.</span></span>

3. <span data-ttu-id="84017-141">[ **ファイル** ] メニューのいずれかの項目をクリックして選択します。</span><span class="sxs-lookup"><span data-stu-id="84017-141">On the **File** menu, click one of the items to select it.</span></span>

     <span data-ttu-id="84017-142">コントロールには、 <xref:System.Windows.Forms.StatusStrip> 選択した項目が表示されます。</span><span class="sxs-lookup"><span data-stu-id="84017-142">The <xref:System.Windows.Forms.StatusStrip> control displays the selected item.</span></span>

## <a name="next-steps"></a><span data-ttu-id="84017-143">次のステップ</span><span class="sxs-lookup"><span data-stu-id="84017-143">Next steps</span></span>

<span data-ttu-id="84017-144">このチュートリアルでは、標準メニューを使用してフォームを作成しました。</span><span class="sxs-lookup"><span data-stu-id="84017-144">In this walkthrough, you have created a form with a standard menu.</span></span> <span data-ttu-id="84017-145">コントロールファミリは、 <xref:System.Windows.Forms.ToolStrip> 他のさまざまな用途に使用できます。</span><span class="sxs-lookup"><span data-stu-id="84017-145">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>

- <span data-ttu-id="84017-146">を使用して、コントロールのショートカットメニューを作成 <xref:System.Windows.Forms.ContextMenuStrip> します。</span><span class="sxs-lookup"><span data-stu-id="84017-146">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="84017-147">詳細については、「 [ContextMenu コンポーネントの概要](contextmenu-component-overview-windows-forms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84017-147">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>

- <span data-ttu-id="84017-148">ドッキングコントロールを使用して、マルチドキュメントインターフェイス (MDI) フォームを作成 <xref:System.Windows.Forms.ToolStrip> します。</span><span class="sxs-lookup"><span data-stu-id="84017-148">Create a multiple document interface (MDI) form with docking <xref:System.Windows.Forms.ToolStrip> controls.</span></span> <span data-ttu-id="84017-149">詳細については、「 [チュートリアル: メニューのマージと ToolStrip コントロールを使用した MDI フォームの作成](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84017-149">For more information, see [Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>

- <span data-ttu-id="84017-150">コントロールに <xref:System.Windows.Forms.ToolStrip> プロフェッショナルな外観を与えます。</span><span class="sxs-lookup"><span data-stu-id="84017-150">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="84017-151">詳細については、「 [方法: アプリケーションの ToolStrip レンダラーを設定する](how-to-set-the-toolstrip-renderer-for-an-application.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84017-151">For more information, see [How to: Set the ToolStrip Renderer for an Application](how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="84017-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="84017-152">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="84017-153">MenuStrip コントロール</span><span class="sxs-lookup"><span data-stu-id="84017-153">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
