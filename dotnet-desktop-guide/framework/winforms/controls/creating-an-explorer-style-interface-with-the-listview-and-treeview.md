---
title: 'チュートリアル: デザイナーを使用した、ListView コントロールと TreeView コントロールを含むエクスプローラー スタイルのインターフェイスの作成'
description: デザイナーを使用して Windows フォーム ListView コントロールと TreeView コントロールを含むエクスプローラースタイルのインターフェイスを作成する方法について説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Explorer-style applications [Windows Forms], walkthroughs
- TreeView control [Windows Forms], ListView controls used with
- ListView control [Windows Forms], TreeView controls used with
- Explorer-style applications
- TreeView control [Windows Forms], using for explorer-style interface
- ListView control [Windows Forms], explorer style interface
- ListView control [Windows Forms], explorer-style interface
ms.assetid: 9e5e7721-19e2-4890-b273-a43589fe99ff
ms.openlocfilehash: 44d4db1ef3da85dbf411498f486882b86a05c140
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974249"
---
# <a name="walkthrough-creating-an-explorer-style-interface-with-the-listview-and-treeview-controls-using-the-designer"></a><span data-ttu-id="fc7fb-103">チュートリアル: デザイナーを使用した、ListView コントロールと TreeView コントロールを含むエクスプローラー スタイルのインターフェイスの作成</span><span class="sxs-lookup"><span data-stu-id="fc7fb-103">Walkthrough: Creating an Explorer Style Interface with the ListView and TreeView Controls Using the Designer</span></span>

<span data-ttu-id="fc7fb-104">Visual Studio の利点の1つは、プロフェッショナルな外観の Windows フォームアプリケーションを短時間で作成できることです。</span><span class="sxs-lookup"><span data-stu-id="fc7fb-104">One of the benefits of Visual Studio is the ability to create professional-looking Windows Forms applications in a short of amount of time.</span></span> <span data-ttu-id="fc7fb-105">一般的なシナリオでは、 <xref:System.Windows.Forms.ListView> <xref:System.Windows.Forms.TreeView> windows オペレーティングシステムの windows エクスプローラー機能に似たコントロールとコントロールを使用して、ユーザーインターフェイス (UI) を作成します。</span><span class="sxs-lookup"><span data-stu-id="fc7fb-105">A common scenario is creating a user interface (UI) with <xref:System.Windows.Forms.ListView> and <xref:System.Windows.Forms.TreeView> controls that resembles the Windows Explorer feature of Windows operating systems.</span></span> <span data-ttu-id="fc7fb-106">エクスプローラーには、ユーザーのコンピューター上のファイルとフォルダーの階層構造が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fc7fb-106">Windows Explorer displays a hierarchical structure of the files and folders on a user's computer.</span></span>

### <a name="to-create-the-form-containing-a-listview-and-treeview-control"></a><span data-ttu-id="fc7fb-107">ListView コントロールと TreeView コントロールを含むフォームを作成するには</span><span class="sxs-lookup"><span data-stu-id="fc7fb-107">To create the form containing a ListView and TreeView control</span></span>

1. <span data-ttu-id="fc7fb-108">**[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc7fb-108">On the **File** menu, point to **New**, and then click **Project**.</span></span>

2. <span data-ttu-id="fc7fb-109">**[新しいプロジェクト]** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="fc7fb-109">In the **New Project** dialog box, do the following:</span></span>

    1. <span data-ttu-id="fc7fb-110">[カテゴリ] で、[ **Visual Basic** ] または [ **Visual C#**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fc7fb-110">In the categories, choose either **Visual Basic** or **Visual C#**.</span></span>

    2. <span data-ttu-id="fc7fb-111">テンプレートの一覧で、[ **Windows フォームアプリケーション**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fc7fb-111">In the list of templates, choose **Windows Forms Application**.</span></span>

3. <span data-ttu-id="fc7fb-112">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc7fb-112">Click **OK**.</span></span> <span data-ttu-id="fc7fb-113">新しい Windows フォームプロジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="fc7fb-113">A new Windows Forms project is created.</span></span>

4. <span data-ttu-id="fc7fb-114"><xref:System.Windows.Forms.SplitContainer>フォームにコントロールを追加し、その <xref:System.Windows.Forms.SplitContainer.Dock%2A> プロパティをに設定し <xref:System.Windows.Forms.DockStyle.Fill> ます。</span><span class="sxs-lookup"><span data-stu-id="fc7fb-114">Add a <xref:System.Windows.Forms.SplitContainer> control to the form and set its <xref:System.Windows.Forms.SplitContainer.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

5. <span data-ttu-id="fc7fb-115"><xref:System.Windows.Forms.ImageList>という名前 `imageList1` のをフォームに追加し、プロパティウィンドウを使用して2つのイメージ (フォルダーイメージとドキュメントイメージ) をこの順序で追加します。</span><span class="sxs-lookup"><span data-stu-id="fc7fb-115">Add an <xref:System.Windows.Forms.ImageList> named `imageList1` to the form and use the Properties window to add two images: a folder image and a document image, in that order.</span></span>

6. <span data-ttu-id="fc7fb-116"><xref:System.Windows.Forms.TreeView>という名前のコントロールを `treeview1` フォームに追加し、コントロールの左側に配置し <xref:System.Windows.Forms.SplitContainer> ます。</span><span class="sxs-lookup"><span data-stu-id="fc7fb-116">Add a <xref:System.Windows.Forms.TreeView> control named `treeview1` to the form, and position it on the left side of the <xref:System.Windows.Forms.SplitContainer> control.</span></span> <span data-ttu-id="fc7fb-117">のプロパティウィンドウで、 `treeView1` 次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="fc7fb-117">In the Properties window for `treeView1` do the following:</span></span>

    1. <span data-ttu-id="fc7fb-118"><xref:System.Windows.Forms.Control.Dock%2A> プロパティを <xref:System.Windows.Forms.DockStyle.Fill>に設定します。</span><span class="sxs-lookup"><span data-stu-id="fc7fb-118">Set the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

    2. <span data-ttu-id="fc7fb-119"><xref:System.Windows.Forms.TreeView.ImageList%2A> プロパティを `imagelist1.` に設定します。</span><span class="sxs-lookup"><span data-stu-id="fc7fb-119">Set the <xref:System.Windows.Forms.TreeView.ImageList%2A> property to `imagelist1.`</span></span>

7. <span data-ttu-id="fc7fb-120"><xref:System.Windows.Forms.ListView>という名前のコントロールを `listView1` フォームに追加し、コントロールの右側に配置し <xref:System.Windows.Forms.SplitContainer> ます。</span><span class="sxs-lookup"><span data-stu-id="fc7fb-120">Add a <xref:System.Windows.Forms.ListView> control named `listView1` to the form, and position it on the right side of the <xref:System.Windows.Forms.SplitContainer> control.</span></span> <span data-ttu-id="fc7fb-121">のプロパティウィンドウで、 `listview1` 次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="fc7fb-121">In the Properties window for `listview1` do the following:</span></span>

    1. <span data-ttu-id="fc7fb-122"><xref:System.Windows.Forms.Control.Dock%2A> プロパティを <xref:System.Windows.Forms.DockStyle.Fill> に設定します。</span><span class="sxs-lookup"><span data-stu-id="fc7fb-122">Set the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

    2. <span data-ttu-id="fc7fb-123"><xref:System.Windows.Forms.ListView.View%2A> プロパティを <xref:System.Windows.Forms.View.Details> に設定します。</span><span class="sxs-lookup"><span data-stu-id="fc7fb-123">Set the <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Details>.</span></span>

    3. <span data-ttu-id="fc7fb-124">[] プロパティの省略記号 ( ![ 省略記号ボタン ([...] プロパティウィンドウ) をクリックして、ColumnHeader コレクションエディターを ](./media/visual-studio-ellipsis-button.png) <xref:System.Windows.Forms.ListView.Columns%2A> **開きます**。</span><span class="sxs-lookup"><span data-stu-id="fc7fb-124">Open the ColumnHeader Collection Editor by clicking the ellipses (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) in the <xref:System.Windows.Forms.ListView.Columns%2A> property **.**</span></span> <span data-ttu-id="fc7fb-125">3つの列を追加し、 <xref:System.Windows.Forms.ColumnHeader.Text%2A> それぞれのプロパティを、、およびにそれぞれ設定し `Name` `Type` `Last Modified` ます。</span><span class="sxs-lookup"><span data-stu-id="fc7fb-125">Add three columns and set their <xref:System.Windows.Forms.ColumnHeader.Text%2A> property to `Name`, `Type`, and `Last Modified`, respectively.</span></span> <span data-ttu-id="fc7fb-126">**[OK]** をクリックしてダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="fc7fb-126">Click **OK** to close the dialog box.</span></span>

    4. <span data-ttu-id="fc7fb-127"><xref:System.Windows.Forms.ListView.SmallImageList%2A> プロパティを `imageList1.` に設定します。</span><span class="sxs-lookup"><span data-stu-id="fc7fb-127">Set the <xref:System.Windows.Forms.ListView.SmallImageList%2A> property to `imageList1.`</span></span>

8. <span data-ttu-id="fc7fb-128">ノードとサブノードをに設定するコードを実装し <xref:System.Windows.Forms.TreeView> ます。</span><span class="sxs-lookup"><span data-stu-id="fc7fb-128">Implement the code to populate the <xref:System.Windows.Forms.TreeView> with nodes and subnodes.</span></span> <span data-ttu-id="fc7fb-129">`Form1` クラスに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="fc7fb-129">Add this code to the `Form1` class.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#1)]

9. <span data-ttu-id="fc7fb-130">前のコードでは System.IO 名前空間を使用しているため、フォームの先頭に適切な using ステートメントまたは import ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="fc7fb-130">Since the previous code uses the System.IO namespace, add the appropriate using or import statement at the top of the form.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#4)]

10. <span data-ttu-id="fc7fb-131">フォームのコンストラクターまたはイベント処理メソッドで、前の手順の設定メソッドを呼び出し <xref:System.Windows.Forms.Form.Load> ます。</span><span class="sxs-lookup"><span data-stu-id="fc7fb-131">Call the set-up method from the previous step in the form's constructor or <xref:System.Windows.Forms.Form.Load> event-handling method.</span></span> <span data-ttu-id="fc7fb-132">このコードをフォームコンストラクターに追加します。</span><span class="sxs-lookup"><span data-stu-id="fc7fb-132">Add this code to the form constructor.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#2)]

11. <span data-ttu-id="fc7fb-133"><xref:System.Windows.Forms.TreeView.NodeMouseClick>のイベントを処理 `treeview1` し、 `listview1` ノードがクリックされたときにノードの内容を設定するコードを実装します。</span><span class="sxs-lookup"><span data-stu-id="fc7fb-133">Handle the <xref:System.Windows.Forms.TreeView.NodeMouseClick> event for `treeview1`**,** and implement the code to populate `listview1` with a node's contents when a node is clicked.</span></span> <span data-ttu-id="fc7fb-134">`Form1` クラスに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="fc7fb-134">Add this code to the `Form1` class.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#3)]

     <span data-ttu-id="fc7fb-135">C# を使用する場合は、イベント <xref:System.Windows.Forms.TreeView.NodeMouseClick> 処理メソッドにイベントが関連付けられていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="fc7fb-135">If you are using C#, make sure you have the <xref:System.Windows.Forms.TreeView.NodeMouseClick> event associated with its event-handling method.</span></span> <span data-ttu-id="fc7fb-136">このコードをフォームコンストラクターに追加します。</span><span class="sxs-lookup"><span data-stu-id="fc7fb-136">Add this code to the form constructor.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#5)]

## <a name="testing-the-application"></a><span data-ttu-id="fc7fb-137">アプリケーションのテスト</span><span class="sxs-lookup"><span data-stu-id="fc7fb-137">Testing the Application</span></span>

<span data-ttu-id="fc7fb-138">フォームをテストして、期待どおりに動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="fc7fb-138">You can now test the form to make sure it behaves as expected.</span></span>

#### <a name="to-test-the-form"></a><span data-ttu-id="fc7fb-139">フォームをテストするには</span><span class="sxs-lookup"><span data-stu-id="fc7fb-139">To test the form</span></span>

- <span data-ttu-id="fc7fb-140">F5 キーを押してアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="fc7fb-140">Press F5 to run the application.</span></span>

     <span data-ttu-id="fc7fb-141"><xref:System.Windows.Forms.TreeView>左側にプロジェクトディレクトリを表示するコントロールと、右側に3つの列があるコントロールを含む分割フォームが表示され <xref:System.Windows.Forms.ListView> ます。</span><span class="sxs-lookup"><span data-stu-id="fc7fb-141">You will see a split form containing a <xref:System.Windows.Forms.TreeView> control that displays your project directory on the left side, and a <xref:System.Windows.Forms.ListView> control on the right side with three columns.</span></span> <span data-ttu-id="fc7fb-142">を走査するには、 <xref:System.Windows.Forms.TreeView> ディレクトリノードを選択し <xref:System.Windows.Forms.ListView> ます。には、選択したディレクトリの内容が設定されます。</span><span class="sxs-lookup"><span data-stu-id="fc7fb-142">You can traverse the <xref:System.Windows.Forms.TreeView> by selecting directory nodes, and the <xref:System.Windows.Forms.ListView> is populated with the contents of the selected directory.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fc7fb-143">次の手順</span><span class="sxs-lookup"><span data-stu-id="fc7fb-143">Next Steps</span></span>

<span data-ttu-id="fc7fb-144">このアプリケーションでは、を使用して制御する方法の例を示し <xref:System.Windows.Forms.TreeView> て <xref:System.Windows.Forms.ListView> います。</span><span class="sxs-lookup"><span data-stu-id="fc7fb-144">This application gives you an example of a way you can use <xref:System.Windows.Forms.TreeView> and <xref:System.Windows.Forms.ListView> controls together.</span></span> <span data-ttu-id="fc7fb-145">これらのコントロールの詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc7fb-145">For more information on these controls, see the following topics:</span></span>

- [<span data-ttu-id="fc7fb-146">方法: TreeView コントロールまたは ListView コントロール (Windows フォーム) にカスタム情報を追加する</span><span class="sxs-lookup"><span data-stu-id="fc7fb-146">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)

- [<span data-ttu-id="fc7fb-147">方法: ListView コントロールに検索機能を追加する</span><span class="sxs-lookup"><span data-stu-id="fc7fb-147">How to: Add Search Capabilities to a ListView Control</span></span>](how-to-add-search-capabilities-to-a-listview-control.md)

- [<span data-ttu-id="fc7fb-148">方法: ショートカット メニューを TreeView ノードに追加する</span><span class="sxs-lookup"><span data-stu-id="fc7fb-148">How to: Attach a ShortCut Menu to a TreeView Node</span></span>](how-to-attach-a-shortcut-menu-to-a-treeview-node.md)

## <a name="see-also"></a><span data-ttu-id="fc7fb-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="fc7fb-149">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.TreeView>
- [<span data-ttu-id="fc7fb-150">ListView コントロール</span><span class="sxs-lookup"><span data-stu-id="fc7fb-150">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="fc7fb-151">方法: Windows フォーム TreeView コントロールでノードを追加および削除する</span><span class="sxs-lookup"><span data-stu-id="fc7fb-151">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="fc7fb-152">方法: Windows フォーム ListView コントロールで項目を追加および削除する</span><span class="sxs-lookup"><span data-stu-id="fc7fb-152">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="fc7fb-153">方法: Windows フォーム ListView コントロールに列を追加する</span><span class="sxs-lookup"><span data-stu-id="fc7fb-153">How to: Add Columns to the Windows Forms ListView Control</span></span>](how-to-add-columns-to-the-windows-forms-listview-control.md)
