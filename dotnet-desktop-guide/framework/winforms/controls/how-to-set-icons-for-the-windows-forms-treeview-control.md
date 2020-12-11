---
title: TreeView コントロールのアイコンを設定する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], node icons
- ImageList component [Windows Forms], adding images
- icons [Windows Forms], setting for TreeView control
- tree nodes in TreeView control [Windows Forms], icons
ms.assetid: c14ddcc0-e5a6-4c21-a2d5-6799fd491781
ms.openlocfilehash: e3d7fc35c6d9f70822cdd0b69dd12f3d469f4ffa
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980290"
---
# <a name="how-to-set-icons-for-the-windows-forms-treeview-control"></a><span data-ttu-id="f2f26-102">方法: Windows フォーム TreeView コントロールのアイコンを設定する</span><span class="sxs-lookup"><span data-stu-id="f2f26-102">How to: Set Icons for the Windows Forms TreeView Control</span></span>
<span data-ttu-id="f2f26-103">Windows フォームコントロールでは、 <xref:System.Windows.Forms.TreeView> 各ノードの横にアイコンを表示できます。</span><span class="sxs-lookup"><span data-stu-id="f2f26-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control can display icons next to each node.</span></span> <span data-ttu-id="f2f26-104">アイコンがノードテキストのすぐ左に配置されます。</span><span class="sxs-lookup"><span data-stu-id="f2f26-104">The icons are positioned to the immediate left of the node text.</span></span> <span data-ttu-id="f2f26-105">これらのアイコンを表示するには、ツリービューをコントロールに関連付ける必要があり <xref:System.Windows.Forms.ImageList> ます。</span><span class="sxs-lookup"><span data-stu-id="f2f26-105">To display these icons, you must associate the tree view with an <xref:System.Windows.Forms.ImageList> control.</span></span> <span data-ttu-id="f2f26-106">イメージリストの詳細については、「 [Imagelist コンポーネント](imagelist-component-windows-forms.md) 」および「 [方法: Windows フォーム imagelist コンポーネントを使用してイメージを追加または削除する](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2f26-106">For more information about image lists, see [ImageList Component](imagelist-component-windows-forms.md) and [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f2f26-107">Microsoft .NET Framework バージョン1.1 のバグにより、アプリケーションがを呼び出すときに、イメージがノードに表示されないようにすることができ <xref:System.Windows.Forms.TreeView> <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> ます。</span><span class="sxs-lookup"><span data-stu-id="f2f26-107">A bug in Microsoft .NET Framework version 1.1 prevents images from appearing on <xref:System.Windows.Forms.TreeView> nodes when your application calls <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f2f26-108">このバグを回避するには、を <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> `Main` 呼び出した直後にメソッドでを呼び出し <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="f2f26-108">To work around this bug, call <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> in your `Main` method immediately after calling <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>.</span></span> <span data-ttu-id="f2f26-109">このバグは .NET Framework 2.0 で修正されています。</span><span class="sxs-lookup"><span data-stu-id="f2f26-109">This bug is fixed in .NET Framework 2.0.</span></span>  
  
### <a name="to-display-images-in-a-tree-view"></a><span data-ttu-id="f2f26-110">ツリービューでイメージを表示するには</span><span class="sxs-lookup"><span data-stu-id="f2f26-110">To display images in a tree view</span></span>  
  
1. <span data-ttu-id="f2f26-111"><xref:System.Windows.Forms.TreeView>コントロールのプロパティを、 <xref:System.Windows.Forms.TreeView.ImageList%2A> 使用する既存のコントロールに設定し <xref:System.Windows.Forms.ImageList> ます。</span><span class="sxs-lookup"><span data-stu-id="f2f26-111">Set the <xref:System.Windows.Forms.TreeView> control's <xref:System.Windows.Forms.TreeView.ImageList%2A> property to the existing <xref:System.Windows.Forms.ImageList> control you wish to use.</span></span>  
  
     <span data-ttu-id="f2f26-112">これらのプロパティは、デザイナーでプロパティウィンドウまたはコードで設定できます。</span><span class="sxs-lookup"><span data-stu-id="f2f26-112">These properties can be set in the designer with the Properties window, or in code.</span></span>  
  
    ```vb  
    TreeView1.ImageList = ImageList1  
    ```  
  
    ```csharp  
    treeView1.ImageList = imageList1;  
    ```  
  
    ```cpp  
    treeView1->ImageList = imageList1;  
    ```  
  
2. <span data-ttu-id="f2f26-113">ノードの <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> プロパティとプロパティを設定し <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="f2f26-113">Set the node's <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> and <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> properties.</span></span> <span data-ttu-id="f2f26-114">プロパティは、 <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> ノードの通常の状態と展開された状態に表示されるイメージを決定し、 <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> プロパティはノードの選択された状態に表示されるイメージを決定します。</span><span class="sxs-lookup"><span data-stu-id="f2f26-114">The <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> property determines the image displayed for the node's normal and expanded states, and the <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> property determines the image displayed for the node's selected state.</span></span>  
  
     <span data-ttu-id="f2f26-115">これらのプロパティは、コードで設定することも、TreeNode エディター内で設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="f2f26-115">These properties can be set in code, or within the TreeNode Editor.</span></span> <span data-ttu-id="f2f26-116">TreeNode エディターを開くには、 ![ ](./media/visual-studio-ellipsis-button.png) プロパティウィンドウのプロパティの横にある省略記号ボタン ([...] プロパティウィンドウ) をクリックします。 <xref:System.Windows.Forms.TreeView.Nodes%2A></span><span class="sxs-lookup"><span data-stu-id="f2f26-116">To open the TreeNode Editor, click the ellipsis button ( ![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.TreeView.Nodes%2A> property on the Properties window.</span></span>  
  
    ```vb  
    ' (Assumes that ImageList1 contains at least two images and  
    ' the TreeView control contains a selected image.)  
    TreeView1.SelectedNode.ImageIndex = 0  
    TreeView1.SelectedNode.SelectedImageIndex = 1  
    ```  
  
    ```csharp  
    // (Assumes that imageList1 contains at least two images and  
    // the TreeView control contains a selected image.)  
    treeView1.SelectedNode.ImageIndex = 0;  
    treeView1.SelectedNode.SelectedImageIndex = 1;  
    ```  
  
    ```cpp  
    // (Assumes that imageList1 contains at least two images and  
    // the TreeView control contains a selected image.)  
    treeView1->SelectedNode->ImageIndex = 0;  
    treeView1->SelectedNode->SelectedImageIndex = 1;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f2f26-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="f2f26-117">See also</span></span>

- [<span data-ttu-id="f2f26-118">TreeView コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="f2f26-118">TreeView Control Overview</span></span>](treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="f2f26-119">方法: Windows フォーム TreeView コントロールでノードを追加および削除する</span><span class="sxs-lookup"><span data-stu-id="f2f26-119">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="f2f26-120">方法: Windows フォーム TreeView コントロールのすべてのノードを反復処理する</span><span class="sxs-lookup"><span data-stu-id="f2f26-120">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [<span data-ttu-id="f2f26-121">方法: クリックされた TreeView ノードを判別する</span><span class="sxs-lookup"><span data-stu-id="f2f26-121">How to: Determine Which TreeView Node Was Clicked</span></span>](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [<span data-ttu-id="f2f26-122">方法: TreeView コントロールまたは ListView コントロール (Windows フォーム) にカスタム情報を追加する</span><span class="sxs-lookup"><span data-stu-id="f2f26-122">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
