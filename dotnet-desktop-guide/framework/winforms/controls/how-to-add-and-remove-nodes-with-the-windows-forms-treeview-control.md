---
title: TreeView コントロールを使用してノードを追加および削除する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], removing nodes
- tree nodes in TreeView control
- TreeView control [Windows Forms], adding nodes
ms.assetid: de1b82db-4905-449a-9f59-af271a6b6673
ms.openlocfilehash: f1e74e6d2f827167c32a6955b3010b59cb2f85b8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981008"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control"></a><span data-ttu-id="86b63-102">方法: Windows フォーム TreeView コントロールでノードを追加および削除する</span><span class="sxs-lookup"><span data-stu-id="86b63-102">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>
<span data-ttu-id="86b63-103">Windows フォームコントロールは、 <xref:System.Windows.Forms.TreeView> 最上位レベルのノードをコレクションに格納し <xref:System.Windows.Forms.TreeView.Nodes%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="86b63-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control stores the top-level nodes in its <xref:System.Windows.Forms.TreeView.Nodes%2A> collection.</span></span> <span data-ttu-id="86b63-104">各 <xref:System.Windows.Forms.TreeNode> には、 <xref:System.Windows.Forms.TreeNode.Nodes%2A> 子ノードを格納するための独自のコレクションもあります。</span><span class="sxs-lookup"><span data-stu-id="86b63-104">Each <xref:System.Windows.Forms.TreeNode> also has its own <xref:System.Windows.Forms.TreeNode.Nodes%2A> collection to store its child nodes.</span></span> <span data-ttu-id="86b63-105">両方のコレクションプロパティは型 <xref:System.Windows.Forms.TreeNodeCollection> であり、ノード階層の1つのレベルでノードを追加、削除、および再配置できるようにする標準のコレクションメンバーを提供します。</span><span class="sxs-lookup"><span data-stu-id="86b63-105">Both collection properties are of type <xref:System.Windows.Forms.TreeNodeCollection>, which provides standard collection members that enable you to add, remove, and rearrange the nodes at a single level of the node hierarchy.</span></span>  
  
### <a name="to-add-nodes-programmatically"></a><span data-ttu-id="86b63-106">プログラムによってノードを追加するには</span><span class="sxs-lookup"><span data-stu-id="86b63-106">To add nodes programmatically</span></span>  
  
1. <span data-ttu-id="86b63-107"><xref:System.Windows.Forms.TreeNodeCollection.Add%2A>ツリービューのプロパティのメソッドを使用し <xref:System.Windows.Forms.TreeView.Nodes%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="86b63-107">Use the <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> method of the tree view's <xref:System.Windows.Forms.TreeView.Nodes%2A> property.</span></span>  
  
    ```vb  
    ' Adds new node as a child node of the currently selected node.  
    Dim newNode As TreeNode = New TreeNode("Text for new node")  
    TreeView1.SelectedNode.Nodes.Add(newNode)  
    ```  
  
    ```csharp  
    // Adds new node as a child node of the currently selected node.  
    TreeNode newNode = new TreeNode("Text for new node");  
    treeView1.SelectedNode.Nodes.Add(newNode);  
    ```  
  
    ```cpp  
    // Adds new node as a child node of the currently selected node.  
    TreeNode ^ newNode = new TreeNode("Text for new node");  
    treeView1->SelectedNode->Nodes->Add(newNode);  
    ```  
  
### <a name="to-remove-nodes-programmatically"></a><span data-ttu-id="86b63-108">プログラムによってノードを削除するには</span><span class="sxs-lookup"><span data-stu-id="86b63-108">To remove nodes programmatically</span></span>  
  
1. <span data-ttu-id="86b63-109"><xref:System.Windows.Forms.TreeNodeCollection.Remove%2A>ツリービューのプロパティのメソッドを使用して、 <xref:System.Windows.Forms.TreeView.Nodes%2A> 1 つのノードを削除するか、メソッドを使用して <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> すべてのノードをクリアします。</span><span class="sxs-lookup"><span data-stu-id="86b63-109">Use the <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> method of the tree view's <xref:System.Windows.Forms.TreeView.Nodes%2A> property to remove a single node, or the <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> method to clear all nodes.</span></span>  
  
    ```vb  
    ' Removes currently selected node, or root if nothing is selected.  
    TreeView1.Nodes.Remove(TreeView1.SelectedNode)  
    ' Clears all nodes.  
    TreeView1.Nodes.Clear()  
    ```  
  
    ```csharp  
    // Removes currently selected node, or root if nothing
    // is selected.  
    treeView1.Nodes.Remove(treeView1.SelectedNode);  
    // Clears all nodes.  
    TreeView1.Nodes.Clear();  
    ```  
  
    ```cpp  
    // Removes currently selected node, or root if nothing  
    // is selected.  
    treeView1->Nodes->Remove(treeView1->SelectedNode);  
    // Clears all nodes.  
    treeView1->Nodes->Clear();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="86b63-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="86b63-110">See also</span></span>

- [<span data-ttu-id="86b63-111">TreeView コントロール</span><span class="sxs-lookup"><span data-stu-id="86b63-111">TreeView Control</span></span>](treeview-control-windows-forms.md)
- [<span data-ttu-id="86b63-112">TreeView コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="86b63-112">TreeView Control Overview</span></span>](treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="86b63-113">方法: Windows フォーム TreeView コントロールのアイコンを設定する</span><span class="sxs-lookup"><span data-stu-id="86b63-113">How to: Set Icons for the Windows Forms TreeView Control</span></span>](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="86b63-114">方法: Windows フォーム TreeView コントロールのすべてのノードを反復処理する</span><span class="sxs-lookup"><span data-stu-id="86b63-114">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [<span data-ttu-id="86b63-115">方法: クリックされた TreeView ノードを判別する</span><span class="sxs-lookup"><span data-stu-id="86b63-115">How to: Determine Which TreeView Node Was Clicked</span></span>](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [<span data-ttu-id="86b63-116">方法: TreeView コントロールまたは ListView コントロール (Windows フォーム) にカスタム情報を追加する</span><span class="sxs-lookup"><span data-stu-id="86b63-116">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
