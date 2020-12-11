---
title: 'チュートリアル: メニューのマージと ToolStrip コントロールのある MDI フォームを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripPanel control [Windows Forms]
- MDI [Windows Forms], creating forms
- multiple document interface forms
- MDI forms
- ToolStrip control [Windows Forms]
- MDI forms [Windows Forms], creating
- MDI forms [Windows Forms], walkthroughs
ms.assetid: fbab4221-74af-42d0-bbf4-3c97f7b2e544
ms.openlocfilehash: d71534bed0af142ff71ba9a0c01207b2c72a6d6a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983443"
---
# <a name="walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a><span data-ttu-id="c8c3a-102">チュートリアル: メニューのマージと ToolStrip コントロールのある MDI フォームを作成する</span><span class="sxs-lookup"><span data-stu-id="c8c3a-102">Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls</span></span>

<span data-ttu-id="c8c3a-103"><xref:System.Windows.Forms?displayProperty=nameWithType> 名前空間は、マルチ ドキュメント インターフェイス (MDI) アプリケーションをサポートし、<xref:System.Windows.Forms.MenuStrip> コントロールはメニューの結合をサポートします。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-103">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace supports multiple document interface (MDI) applications, and the <xref:System.Windows.Forms.MenuStrip> control supports menu merging.</span></span> <span data-ttu-id="c8c3a-104">MDI フォームは、<xref:System.Windows.Forms.ToolStrip> コントロールもサポートします。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-104">MDI forms can also <xref:System.Windows.Forms.ToolStrip> controls.</span></span>

<span data-ttu-id="c8c3a-105">このチュートリアル <xref:System.Windows.Forms.ToolStripPanel> では、MDI フォームでコントロールを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-105">This walkthrough demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls with an MDI form.</span></span> <span data-ttu-id="c8c3a-106">フォームは、子メニューをマージするメニューもサポートしています。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-106">The form also supports menu merging with child menus.</span></span> <span data-ttu-id="c8c3a-107">このチュートリアルでは、次のタスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-107">The following tasks are illustrated in this walkthrough:</span></span>

- <span data-ttu-id="c8c3a-108">Windows フォームプロジェクトを作成しています。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-108">Creating a Windows Forms project.</span></span>

- <span data-ttu-id="c8c3a-109">フォームのメインメニューを作成します。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-109">Creating the main menu for your form.</span></span> <span data-ttu-id="c8c3a-110">メニューの実際の名前は異なります。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-110">The actual name of the menu will vary.</span></span>

- <span data-ttu-id="c8c3a-111"><xref:System.Windows.Forms.ToolStripPanel>**ツールボックス** にコントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-111">Adding the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox**.</span></span>

- <span data-ttu-id="c8c3a-112">子フォームを作成する。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-112">Creating a child form.</span></span>

- <span data-ttu-id="c8c3a-113"><xref:System.Windows.Forms.ToolStripPanel>コントロールを z オーダーによって配置する。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-113">Arranging <xref:System.Windows.Forms.ToolStripPanel> controls by z-order.</span></span>

<span data-ttu-id="c8c3a-114">終了すると、メニューのマージと移動可能なコントロールをサポートする MDI フォームが作成され <xref:System.Windows.Forms.ToolStrip> ます。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-114">When you are finished, you will have an MDI form that supports menu merging and movable <xref:System.Windows.Forms.ToolStrip> controls.</span></span>

<span data-ttu-id="c8c3a-115">このトピックのコードを単一のリストとしてコピーする方法については、「 [方法: メニューのマージと ToolStrip コントロールを使用して MDI フォームを作成](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-115">To copy the code in this topic as a single listing, see [How to: Create an MDI Form with Menu Merging and ToolStrip Controls](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c8c3a-116">前提条件</span><span class="sxs-lookup"><span data-stu-id="c8c3a-116">Prerequisites</span></span>

<span data-ttu-id="c8c3a-117">このチュートリアルを完了するには、Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-117">You'll need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="c8c3a-118">プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="c8c3a-118">Create the project</span></span>

1. <span data-ttu-id="c8c3a-119">Visual Studio で、 **system.windows.forms.toolstrip.mdiform** という名前の Windows アプリケーションプロジェクトを作成します ([**ファイル**] [  >  **新しい**  >  **プロジェクト**] [  >  **Visual C#** ] または [ **Visual Basic**  >  **クラシックデスクトップ**  >  **Windows フォームアプリケーション**])。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-119">In Visual Studio, create a Windows Application project called **MdiForm** (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="c8c3a-120">[Windows フォームデザイナーで、フォームを選択します。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-120">In the Windows Forms Designer, select the form.</span></span>

3. <span data-ttu-id="c8c3a-121">プロパティウィンドウで、の値をに設定し <xref:System.Windows.Forms.Form.IsMdiContainer%2A> `true` ます。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-121">In the Properties window, set the value of the <xref:System.Windows.Forms.Form.IsMdiContainer%2A> to `true`.</span></span>

## <a name="create-the-main-menu"></a><span data-ttu-id="c8c3a-122">メインメニューを作成する</span><span class="sxs-lookup"><span data-stu-id="c8c3a-122">Create the main menu</span></span>

<span data-ttu-id="c8c3a-123">親 MDI フォームには、メインメニューが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-123">The parent MDI form contains the main menu.</span></span> <span data-ttu-id="c8c3a-124">メインメニューには、 **Window** という名前のメニュー項目が1つあります。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-124">The main menu has one menu item named **Window**.</span></span> <span data-ttu-id="c8c3a-125">[ **ウィンドウ** ] メニュー項目を使用すると、子フォームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-125">With the **Window** menu item, you can create child forms.</span></span> <span data-ttu-id="c8c3a-126">子フォームのメニュー項目は、メインメニューにマージされます。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-126">Menu items from child forms are merged into the main menu.</span></span>

1. <span data-ttu-id="c8c3a-127">[ **ツールボックス**] から <xref:System.Windows.Forms.MenuStrip> コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-127">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the form.</span></span>

2. <span data-ttu-id="c8c3a-128"><xref:System.Windows.Forms.ToolStripMenuItem>コントロールにを追加 <xref:System.Windows.Forms.MenuStrip> し、**ウィンドウ** に名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-128">Add a <xref:System.Windows.Forms.ToolStripMenuItem> to the <xref:System.Windows.Forms.MenuStrip> control and name it **Window**.</span></span>

3. <span data-ttu-id="c8c3a-129"><xref:System.Windows.Forms.MenuStrip> コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-129">Select the <xref:System.Windows.Forms.MenuStrip> control.</span></span>

4. <span data-ttu-id="c8c3a-130">[プロパティ] ウィンドウで、<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> プロパティの値を `ToolStripMenuItem1` に設定します。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-130">In the Properties window, set the value of the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property to `ToolStripMenuItem1`.</span></span>

5. <span data-ttu-id="c8c3a-131">[ウィンドウ] メニュー項目にサブ項目を追加し、サブ項目に「 **New** **」** という名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-131">Add a subitem to the **Window** menu item, and then name the subitem **New**.</span></span>

6. <span data-ttu-id="c8c3a-132">[プロパティ] ウィンドウで、**[イベント]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-132">In the Properties window, click **Events**.</span></span>

7. <span data-ttu-id="c8c3a-133"><xref:System.Windows.Forms.ToolStripItem.Click> イベントをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-133">Double-click the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>

     <span data-ttu-id="c8c3a-134">Windows フォームデザイナーは、イベントのイベントハンドラーを生成し <xref:System.Windows.Forms.ToolStripItem.Click> ます。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-134">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>

8. <span data-ttu-id="c8c3a-135">イベントハンドラーに次のコードを挿入します。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-135">Insert the following code into the event handler.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#2)]

## <a name="add-the-toolstrippanel-control-to-the-toolbox"></a><span data-ttu-id="c8c3a-136">ToolStripPanel コントロールをツールボックスに追加する</span><span class="sxs-lookup"><span data-stu-id="c8c3a-136">Add the ToolStripPanel control to the Toolbox</span></span>

<span data-ttu-id="c8c3a-137">コントロールを MDI フォームで使用する場合は <xref:System.Windows.Forms.MenuStrip> 、コントロールが必要 <xref:System.Windows.Forms.ToolStripPanel> です。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-137">When you use <xref:System.Windows.Forms.MenuStrip> controls with an MDI form you must have the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="c8c3a-138"><xref:System.Windows.Forms.ToolStripPanel>Windows フォームデザイナーで MDI フォームをビルドするには、コントロールを **ツールボックス** に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-138">You must add the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox** to build your MDI form in the Windows Forms Designer.</span></span>

1. <span data-ttu-id="c8c3a-139">[ **ツールボックス**] を開き、[ **すべての Windows フォーム** ] タブをクリックして、使用可能な Windows フォームコントロールを表示します。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-139">Open the **Toolbox**, and then click the **All Windows Forms** tab to show the available Windows Forms controls.</span></span>

2. <span data-ttu-id="c8c3a-140">右クリックしてショートカットメニューを開き、[ **項目の選択**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-140">Right-click to open the shortcut menu, and select **Choose Items**.</span></span>

3. <span data-ttu-id="c8c3a-141">[**ツールボックスアイテムの選択**] ダイアログボックスで、 **ToolStripPanel** が表示されるまで [**名前**] 列を下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-141">In the **Choose Toolbox Items** dialog box, scroll down the **Name** column until you find **ToolStripPanel**.</span></span>

4. <span data-ttu-id="c8c3a-142">**ToolStripPanel** のチェックボックスをオンにして、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-142">Select the check box by **ToolStripPanel**, and then click **OK**.</span></span>

     <span data-ttu-id="c8c3a-143"><xref:System.Windows.Forms.ToolStripPanel>コントロールが **ツールボックス** に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-143">The <xref:System.Windows.Forms.ToolStripPanel> control appears in the **Toolbox**.</span></span>

## <a name="create-a-child-form"></a><span data-ttu-id="c8c3a-144">子フォームを作成する</span><span class="sxs-lookup"><span data-stu-id="c8c3a-144">Create a child form</span></span>

<span data-ttu-id="c8c3a-145">この手順では、独自のコントロールを持つ別の子フォームクラスを定義し <xref:System.Windows.Forms.MenuStrip> ます。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-145">In this procedure, you will define a separate child form class that has its own <xref:System.Windows.Forms.MenuStrip> control.</span></span> <span data-ttu-id="c8c3a-146">このフォームのメニュー項目は、親フォームのメニュー項目とマージされます。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-146">The menu items for this form are merged with those of the parent form.</span></span>

1. <span data-ttu-id="c8c3a-147">という名前の新しいフォームを `ChildForm` プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-147">Add a new form named `ChildForm` to the project.</span></span>

     <span data-ttu-id="c8c3a-148">詳細については、「 [方法: プロジェクトに Windows フォームを追加](/previous-versions/visualstudio/visual-studio-2010/y2xxdce3(v=vs.100))する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-148">For more information, see [How to: Add Windows Forms to a Project](/previous-versions/visualstudio/visual-studio-2010/y2xxdce3(v=vs.100)).</span></span>

2. <span data-ttu-id="c8c3a-149">[ **ツールボックス**] から <xref:System.Windows.Forms.MenuStrip> コントロールを子フォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-149">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the child form.</span></span>

3. <span data-ttu-id="c8c3a-150"><xref:System.Windows.Forms.MenuStrip>コントロールの [デザイナーアクション] グリフ ( ![ 小さい黒い矢印 ](./media/designer-actions-glyph.gif) ) をクリックし、[**アイテムの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-150">Click the <xref:System.Windows.Forms.MenuStrip> control's designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)), and then select **Edit Items**.</span></span>

4. <span data-ttu-id="c8c3a-151">[ **項目コレクションエディター** ] ダイアログボックスで、 <xref:System.Windows.Forms.ToolStripMenuItem> 子メニューに新しい名前付き **childmenuitem** を追加します。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-151">In the **Items Collection Editor** dialog box, add a new <xref:System.Windows.Forms.ToolStripMenuItem> named **ChildMenuItem** to the child menu.</span></span>

     <span data-ttu-id="c8c3a-152">詳細については、「 [ToolStrip Items コレクションエディター](/previous-versions/visualstudio/visual-studio-2010/ms233643(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-152">For more information, see [ToolStrip Items Collection Editor](/previous-versions/visualstudio/visual-studio-2010/ms233643(v=vs.100)).</span></span>

## <a name="test-the-form"></a><span data-ttu-id="c8c3a-153">フォームをテストする</span><span class="sxs-lookup"><span data-stu-id="c8c3a-153">Test the form</span></span>

1. <span data-ttu-id="c8c3a-154">**F5** キーを押して、フォームをコンパイルして実行します。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-154">Press **F5** to compile and run your form.</span></span>

2. <span data-ttu-id="c8c3a-155">[ **ウィンドウ** ] メニュー項目をクリックしてメニューを開き、[ **新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-155">Click the **Window** menu item to open the menu, and then click **New**.</span></span>

     <span data-ttu-id="c8c3a-156">フォームの MDI クライアント領域に新しい子フォームが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-156">A new child form is created in the form's MDI client area.</span></span> <span data-ttu-id="c8c3a-157">子フォームのメニューがメインメニューにマージされます。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-157">The child form's menu is merged with the main menu.</span></span>

3. <span data-ttu-id="c8c3a-158">子フォームを閉じます。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-158">Close the child form.</span></span>

     <span data-ttu-id="c8c3a-159">子フォームのメニューがメインメニューから削除されます。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-159">The child form's menu is removed from the main menu.</span></span>

4. <span data-ttu-id="c8c3a-160">[ **新規** ] を数回クリックします。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-160">Click **New** several times.</span></span>

     <span data-ttu-id="c8c3a-161"> <xref:System.Windows.Forms.MenuStrip> コントロールの <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> プロパティが割り当てられているため、子フォームは [ウィンドウ] メニュー項目の下に自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-161">The child forms are automatically listed under the **Window** menu item because the <xref:System.Windows.Forms.MenuStrip> control's <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property is assigned.</span></span>

## <a name="add-toolstrip-support"></a><span data-ttu-id="c8c3a-162">ToolStrip サポートの追加</span><span class="sxs-lookup"><span data-stu-id="c8c3a-162">Add ToolStrip support</span></span>

<span data-ttu-id="c8c3a-163">この手順では、 <xref:System.Windows.Forms.ToolStrip> MDI 親フォームに4つのコントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-163">In this procedure, you will add four <xref:System.Windows.Forms.ToolStrip> controls to the MDI parent form.</span></span> <span data-ttu-id="c8c3a-164">各 <xref:System.Windows.Forms.ToolStrip> コントロールは、 <xref:System.Windows.Forms.ToolStripPanel> フォームの端にドッキングされるコントロール内に追加されます。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-164">Each <xref:System.Windows.Forms.ToolStrip> control is added inside a <xref:System.Windows.Forms.ToolStripPanel> control, which is docked to the edge of the form.</span></span>

1. <span data-ttu-id="c8c3a-165">[ **ツールボックス**] から <xref:System.Windows.Forms.ToolStripPanel> コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-165">From the **Toolbox**, drag a <xref:System.Windows.Forms.ToolStripPanel> control onto the form.</span></span>

2. <span data-ttu-id="c8c3a-166">コントロールを選択した状態で <xref:System.Windows.Forms.ToolStripPanel> 、 <xref:System.Windows.Forms.ToolStrip> **ツールボックス** のコントロールをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-166">With the <xref:System.Windows.Forms.ToolStripPanel> control selected, double-click the <xref:System.Windows.Forms.ToolStrip> control in the **Toolbox**.</span></span>

     <span data-ttu-id="c8c3a-167">コントロール <xref:System.Windows.Forms.ToolStrip> にコントロールが作成され <xref:System.Windows.Forms.ToolStripPanel> ます。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-167">A <xref:System.Windows.Forms.ToolStrip> control is created in the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>

3. <span data-ttu-id="c8c3a-168"><xref:System.Windows.Forms.ToolStripPanel> コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-168">Select the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>

4. <span data-ttu-id="c8c3a-169">プロパティウィンドウで、コントロールのプロパティの値 <xref:System.Windows.Forms.Control.Dock%2A> をに変更し <xref:System.Windows.Forms.DockStyle.Left> ます。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-169">In the Properties window, change the value of the control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Left>.</span></span>

     <span data-ttu-id="c8c3a-170">コントロールは、 <xref:System.Windows.Forms.ToolStripPanel> メインメニューの下にあるフォームの左側にドッキングされます。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-170">The <xref:System.Windows.Forms.ToolStripPanel> control docks to the left side of the form, underneath the main menu.</span></span> <span data-ttu-id="c8c3a-171">コントロールに合わせて MDI クライアント領域のサイズが変更され <xref:System.Windows.Forms.ToolStripPanel> ます。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-171">The MDI client area resizes to fit the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>

5. <span data-ttu-id="c8c3a-172">手順 1. ~ 4. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-172">Repeat steps 1 through 4.</span></span>

     <span data-ttu-id="c8c3a-173"><xref:System.Windows.Forms.ToolStripPanel>フォームの上部に新しいコントロールをドッキングします。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-173">Dock the new <xref:System.Windows.Forms.ToolStripPanel> control to the top of the form.</span></span>

     <span data-ttu-id="c8c3a-174"><xref:System.Windows.Forms.ToolStripPanel>コントロールはメインメニューの下にドッキングされますが、最初のコントロールの右側にドッキングされ <xref:System.Windows.Forms.ToolStripPanel> ます。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-174">The <xref:System.Windows.Forms.ToolStripPanel> control is docked underneath the main menu, but to the right of the first <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="c8c3a-175">この手順では、正しく配置されたコントロールの z オーダーの重要性について説明し <xref:System.Windows.Forms.ToolStripPanel> ます。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-175">This step illustrates the importance of z-order in correctly positioning <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>

6. <span data-ttu-id="c8c3a-176">さらに2つのコントロールについて、手順 1. ~ 4. を繰り返し <xref:System.Windows.Forms.ToolStripPanel> ます。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-176">Repeat steps 1 through 4 for two more <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>

     <span data-ttu-id="c8c3a-177"><xref:System.Windows.Forms.ToolStripPanel>フォームの右端と下端に新しいコントロールをドッキングします。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-177">Dock the new <xref:System.Windows.Forms.ToolStripPanel> controls to the right and bottom of the form.</span></span>

## <a name="arrange-toolstrippanel-controls-by-z-order"></a><span data-ttu-id="c8c3a-178">ToolStripPanel コントロールを Z オーダーで整列する</span><span class="sxs-lookup"><span data-stu-id="c8c3a-178">Arrange ToolStripPanel controls by Z-order</span></span>

<span data-ttu-id="c8c3a-179">MDI フォーム上のドッキングされたコントロールの位置 <xref:System.Windows.Forms.ToolStripPanel> は、コントロールの z オーダーでの位置によって決まります。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-179">The position of a docked <xref:System.Windows.Forms.ToolStripPanel> control on your MDI form is determined by the control's position in the z-order.</span></span> <span data-ttu-id="c8c3a-180">[ドキュメントアウトライン] ウィンドウでは、コントロールの z オーダーを簡単に配置できます。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-180">You can easily arrange the z-order of your controls in the Document Outline window.</span></span>

1. <span data-ttu-id="c8c3a-181">[ **表示** ] メニューの [ **その他のウィンドウ**] をクリックし、[ **ドキュメントアウトライン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-181">In the **View** menu, click **Other Windows**, and then click **Document Outline**.</span></span>

     <span data-ttu-id="c8c3a-182">前の手順で作成したコントロールの配置 <xref:System.Windows.Forms.ToolStripPanel> は非標準です。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-182">The arrangement of your <xref:System.Windows.Forms.ToolStripPanel> controls from the previous procedure is nonstandard.</span></span> <span data-ttu-id="c8c3a-183">これは、z オーダーが正しくないためです。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-183">This is because the z-order is not correct.</span></span> <span data-ttu-id="c8c3a-184">[ドキュメントアウトライン] ウィンドウを使用すると、コントロールの z オーダーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-184">Use the Document Outline window to change the z-order of the controls.</span></span>

2. <span data-ttu-id="c8c3a-185">[ドキュメントアウトライン] ウィンドウで、[ **ToolStripPanel4**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-185">In the Document Outline window, select **ToolStripPanel4**.</span></span>

3. <span data-ttu-id="c8c3a-186">**ToolStripPanel4** が一覧の一番下に表示されるまで、下向きの矢印ボタンを繰り返しクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-186">Click the down-arrow button repeatedly, until **ToolStripPanel4** is at the bottom of the list.</span></span>

     <span data-ttu-id="c8c3a-187">**ToolStripPanel4** コントロールは、他のコントロールの下にあるフォームの下部にドッキングされます。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-187">The **ToolStripPanel4** control is docked to the bottom of the form, underneath the other controls.</span></span>

4. <span data-ttu-id="c8c3a-188">[ **ToolStripPanel2**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-188">Select **ToolStripPanel2**.</span></span>

5. <span data-ttu-id="c8c3a-189">下向き矢印ボタンを1回クリックして、コントロールを一覧の3番目に配置します。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-189">Click the down-arrow button one time to position the control third in the list.</span></span>

     <span data-ttu-id="c8c3a-190">**ToolStripPanel2** コントロールは、メインメニューの下、他のコントロールの上にあるフォームの上部にドッキングされます。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-190">The **ToolStripPanel2** control is docked to the top of the form, underneath the main menu and above the other controls.</span></span>

6. <span data-ttu-id="c8c3a-191">[ **ドキュメントアウトライン** ] ウィンドウでさまざまなコントロールを選択し、z オーダーの別の位置に移動します。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-191">Select various controls in the **Document Outline** window and move them to different positions in the z-order.</span></span> <span data-ttu-id="c8c3a-192">ドッキングされたコントロールの配置に対する z オーダーの効果に注意してください。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-192">Note the effect of the z-order on the placement of docked controls.</span></span> <span data-ttu-id="c8c3a-193">[**編集**] メニューの CTRL + Z または **元に戻す** を使用して、変更を元に戻します。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-193">Use CTRL-Z or **Undo** on the **Edit** menu to undo your changes.</span></span>

## <a name="checkpoint---test-your-form"></a><span data-ttu-id="c8c3a-194">チェックポイント-フォームのテスト</span><span class="sxs-lookup"><span data-stu-id="c8c3a-194">Checkpoint - test your form</span></span>

1. <span data-ttu-id="c8c3a-195">**F5** キーを押して、フォームをコンパイルして実行します。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-195">Press **F5** to compile and run your form.</span></span>

2. <span data-ttu-id="c8c3a-196">コントロールのグリップをクリックし、 <xref:System.Windows.Forms.ToolStrip> フォーム上の別の位置にコントロールをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-196">Click the grip of a <xref:System.Windows.Forms.ToolStrip> control and drag the control to different positions on the form.</span></span>

     <span data-ttu-id="c8c3a-197">コントロールを <xref:System.Windows.Forms.ToolStrip> 1 つのコントロールから別のコントロールにドラッグすることができ <xref:System.Windows.Forms.ToolStripPanel> ます。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-197">You can drag a <xref:System.Windows.Forms.ToolStrip> control from one <xref:System.Windows.Forms.ToolStripPanel> control to another.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c8c3a-198">次のステップ</span><span class="sxs-lookup"><span data-stu-id="c8c3a-198">Next steps</span></span>

<span data-ttu-id="c8c3a-199">このチュートリアルでは、コントロールとメニューのマージを使用して、MDI 親フォームを作成しました <xref:System.Windows.Forms.ToolStrip> 。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-199">In this walkthrough, you have created an MDI parent form with <xref:System.Windows.Forms.ToolStrip> controls and menu merging.</span></span> <span data-ttu-id="c8c3a-200">コントロールファミリは、 <xref:System.Windows.Forms.ToolStrip> 他のさまざまな用途に使用できます。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-200">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>

- <span data-ttu-id="c8c3a-201">を使用して、コントロールのショートカットメニューを作成 <xref:System.Windows.Forms.ContextMenuStrip> します。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-201">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="c8c3a-202">詳細については、「 [ContextMenu コンポーネントの概要](contextmenu-component-overview-windows-forms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-202">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>

- <span data-ttu-id="c8c3a-203">自動的に設定された標準メニューを使用してフォームを作成しました。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-203">Created a form with an automatically populated standard menu.</span></span> <span data-ttu-id="c8c3a-204">詳細については、「 [チュートリアル: フォームに標準メニュー項目を提供する](walkthrough-providing-standard-menu-items-to-a-form.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-204">For more information, see [Walkthrough: Providing Standard Menu Items to a Form](walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>

- <span data-ttu-id="c8c3a-205">コントロールに <xref:System.Windows.Forms.ToolStrip> プロフェッショナルな外観を与えます。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-205">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="c8c3a-206">詳細については、「 [方法: アプリケーションの ToolStrip レンダラーを設定する](how-to-set-the-toolstrip-renderer-for-an-application.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8c3a-206">For more information, see [How to: Set the ToolStrip Renderer for an Application](how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c8c3a-207">関連項目</span><span class="sxs-lookup"><span data-stu-id="c8c3a-207">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="c8c3a-208">方法: MDI 親フォームを作成する</span><span class="sxs-lookup"><span data-stu-id="c8c3a-208">How to: Create MDI Parent Forms</span></span>](../advanced/how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="c8c3a-209">方法: MDI 子フォームを作成する</span><span class="sxs-lookup"><span data-stu-id="c8c3a-209">How to: Create MDI Child Forms</span></span>](../advanced/how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="c8c3a-210">方法: MDI ドロップダウン メニューに MenuStrip を挿入する</span><span class="sxs-lookup"><span data-stu-id="c8c3a-210">How to: Insert a MenuStrip into an MDI Drop-Down Menu</span></span>](how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms.md)
- [<span data-ttu-id="c8c3a-211">ToolStrip コントロール</span><span class="sxs-lookup"><span data-stu-id="c8c3a-211">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
