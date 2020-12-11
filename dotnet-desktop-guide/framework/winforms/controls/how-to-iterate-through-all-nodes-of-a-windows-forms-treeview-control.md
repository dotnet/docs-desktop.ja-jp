---
title: TreeView コントロールのすべてのノードを反復処理する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], iterating through nodes
- tree nodes in TreeView control [Windows Forms], iterating through
ms.assetid: 427f8928-ebcf-4beb-887f-695b905d5134
ms.openlocfilehash: fd3d8c4659f0dad3b9566cc7946f35957a19f6f9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982744"
---
# <a name="how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control"></a><span data-ttu-id="01647-102">方法: Windows フォーム TreeView コントロールのすべてのノードを反復処理する</span><span class="sxs-lookup"><span data-stu-id="01647-102">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>

<span data-ttu-id="01647-103"><xref:System.Windows.Forms.TreeView>ノード値に対して計算を実行するために、Windows フォームコントロール内のすべてのノードを調べると便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="01647-103">It is sometimes useful to examine every node in a Windows Forms <xref:System.Windows.Forms.TreeView> control in order to perform some calculation on the node values.</span></span> <span data-ttu-id="01647-104">この操作は、ツリーの各コレクションの各ノードを反復処理する再帰プロシージャ (C# および C++ の場合は再帰メソッド) を使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="01647-104">This operation can be done using a recursive procedure (recursive method in C# and C++) that iterates through each node in each collection of the tree.</span></span>  
  
 <span data-ttu-id="01647-105"><xref:System.Windows.Forms.TreeNode>ツリービュー内の各オブジェクトには、ツリービュー内を移動するために使用できるプロパティがあります。 <xref:System.Windows.Forms.TreeNode.FirstNode%2A> 、、、、 <xref:System.Windows.Forms.TreeNode.LastNode%2A> <xref:System.Windows.Forms.TreeNode.NextNode%2A> <xref:System.Windows.Forms.TreeNode.PrevNode%2A> および <xref:System.Windows.Forms.TreeNode.Parent%2A> です。</span><span class="sxs-lookup"><span data-stu-id="01647-105">Each <xref:System.Windows.Forms.TreeNode> object in a tree view has properties that you can use to navigate the tree view: <xref:System.Windows.Forms.TreeNode.FirstNode%2A>, <xref:System.Windows.Forms.TreeNode.LastNode%2A>, <xref:System.Windows.Forms.TreeNode.NextNode%2A>, <xref:System.Windows.Forms.TreeNode.PrevNode%2A>, and <xref:System.Windows.Forms.TreeNode.Parent%2A>.</span></span> <span data-ttu-id="01647-106">プロパティの値 <xref:System.Windows.Forms.TreeNode.Parent%2A> は、現在のノードの親ノードです。</span><span class="sxs-lookup"><span data-stu-id="01647-106">The value of the <xref:System.Windows.Forms.TreeNode.Parent%2A> property is the parent node of the current node.</span></span> <span data-ttu-id="01647-107">現在のノードの子ノード (存在する場合) は、そのプロパティに一覧表示され <xref:System.Windows.Forms.TreeNode.Nodes%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="01647-107">The child nodes of the current node, if there are any, are listed in its <xref:System.Windows.Forms.TreeNode.Nodes%2A> property.</span></span> <span data-ttu-id="01647-108"><xref:System.Windows.Forms.TreeView>コントロール自体には、 <xref:System.Windows.Forms.TreeView.TopNode%2A> ツリービュー全体のルートノードであるプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="01647-108">The <xref:System.Windows.Forms.TreeView> control itself has the <xref:System.Windows.Forms.TreeView.TopNode%2A> property, which is the root node of the entire tree view.</span></span>  
  
### <a name="to-iterate-through-all-nodes-of-the-treeview-control"></a><span data-ttu-id="01647-109">TreeView コントロールのすべてのノードを反復処理するには</span><span class="sxs-lookup"><span data-stu-id="01647-109">To iterate through all nodes of the TreeView control</span></span>  
  
1. <span data-ttu-id="01647-110">各ノードをテストする再帰プロシージャ (C# および C++ における再帰メソッド) を作成します。</span><span class="sxs-lookup"><span data-stu-id="01647-110">Create a recursive procedure (recursive method in C# and C++) that tests each node.</span></span>  
  
2. <span data-ttu-id="01647-111">プロシージャを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="01647-111">Call the procedure.</span></span>  
  
     <span data-ttu-id="01647-112">次の例は、各オブジェクトのプロパティを印刷する方法を示してい <xref:System.Windows.Forms.TreeNode> <xref:System.Windows.Forms.TreeNode.Text%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="01647-112">The following example shows how to print each <xref:System.Windows.Forms.TreeNode> object's <xref:System.Windows.Forms.TreeNode.Text%2A> property:</span></span>  
  
    ```vb  
    Private Sub PrintRecursive(ByVal n As TreeNode)  
       System.Diagnostics.Debug.WriteLine(n.Text)  
       MessageBox.Show(n.Text)  
       Dim aNode As TreeNode  
       For Each aNode In n.Nodes  
          PrintRecursive(aNode)  
       Next  
    End Sub  
  
    ' Call the procedure using the top nodes of the treeview.  
    Private Sub CallRecursive(ByVal aTreeView As TreeView)  
       Dim n As TreeNode  
       For Each n In aTreeView.Nodes  
          PrintRecursive(n)  
       Next  
    End Sub  
    ```  
  
    ```csharp  
    private void PrintRecursive(TreeNode treeNode)  
    {  
       // Print the node.  
       System.Diagnostics.Debug.WriteLine(treeNode.Text);  
       MessageBox.Show(treeNode.Text);  
       // Print each node recursively.  
       foreach (TreeNode tn in treeNode.Nodes)  
       {  
          PrintRecursive(tn);  
       }  
    }  
  
    // Call the procedure using the TreeView.  
    private void CallRecursive(TreeView treeView)  
    {  
       // Print each node recursively.  
       TreeNodeCollection nodes = treeView.Nodes;  
       foreach (TreeNode n in nodes)  
       {  
          PrintRecursive(n);  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void PrintRecursive( TreeNode^ treeNode )  
       {  
          // Print the node.  
          System::Diagnostics::Debug::WriteLine( treeNode->Text );  
          MessageBox::Show( treeNode->Text );  
  
          // Print each node recursively.  
          System::Collections::IEnumerator^ myNodes = (safe_cast<System::Collections::IEnumerable^>(treeNode->Nodes))->GetEnumerator();  
          try  
          {  
             while ( myNodes->MoveNext() )  
             {  
                TreeNode^ tn = safe_cast<TreeNode^>(myNodes->Current);  
                PrintRecursive( tn );  
             }  
          }  
          finally  
          {  
             IDisposable^ disposable = dynamic_cast<System::IDisposable^>(myNodes);  
             if ( disposable != nullptr )  
                      disposable->Dispose();  
          }  
       }  
  
       // Call the procedure using the TreeView.  
       void CallRecursive( TreeView^ treeView )  
       {  
          // Print each node recursively.  
          TreeNodeCollection^ nodes = treeView->Nodes;  
          System::Collections::IEnumerator^ myNodes = (safe_cast<System::Collections::IEnumerable^>(nodes))->GetEnumerator();  
          try  
          {  
             while ( myNodes->MoveNext() )  
             {  
                TreeNode^ n = safe_cast<TreeNode^>(myNodes->Current);  
                PrintRecursive( n );  
             }  
          }  
          finally  
          {  
             IDisposable^ disposable = dynamic_cast<System::IDisposable^>(myNodes);  
             if ( disposable != nullptr )  
                      disposable->Dispose();  
          }  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="01647-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="01647-113">See also</span></span>

- [<span data-ttu-id="01647-114">TreeView コントロール</span><span class="sxs-lookup"><span data-stu-id="01647-114">TreeView Control</span></span>](treeview-control-windows-forms.md)
- [<span data-ttu-id="01647-115">再帰プロシージャ</span><span class="sxs-lookup"><span data-stu-id="01647-115">Recursive Procedures</span></span>](/dotnet/visual-basic/programming-guide/language-features/procedures/recursive-procedures)
