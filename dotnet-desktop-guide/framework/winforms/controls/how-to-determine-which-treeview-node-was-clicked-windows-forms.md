---
title: '方法: クリックされた TreeView ノードを判別する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- TreeNode
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- tree nodes in TreeView control [Windows Forms], determining node clicked
- TreeView control [Windows Forms], determining node clicked
ms.assetid: 06a4a191-d918-42af-9f49-956c93eff261
ms.openlocfilehash: d960eaae2aa479e0be74e9a5e4fdbfec8ff411c1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982140"
---
# <a name="how-to-determine-which-treeview-node-was-clicked-windows-forms"></a><span data-ttu-id="70e08-102">方法 : クリックされた TreeView ノード (Windows フォーム) を判別する</span><span class="sxs-lookup"><span data-stu-id="70e08-102">How to: Determine Which TreeView Node Was Clicked (Windows Forms)</span></span>
<span data-ttu-id="70e08-103">Windows フォームコントロールを使用する場合の <xref:System.Windows.Forms.TreeView> 一般的なタスクは、どのノードがクリックされたかを判断し、適切に対応することです。</span><span class="sxs-lookup"><span data-stu-id="70e08-103">When working with the Windows Forms <xref:System.Windows.Forms.TreeView> control, a common task is to determine which node was clicked, and respond appropriately.</span></span>  
  
### <a name="to-determine-which-treeview-node-was-clicked"></a><span data-ttu-id="70e08-104">クリックされた TreeView ノードを確認するには</span><span class="sxs-lookup"><span data-stu-id="70e08-104">To determine which TreeView node was clicked</span></span>  
  
1. <span data-ttu-id="70e08-105">オブジェクトを使用して、クリックされた <xref:System.EventArgs> ノードオブジェクトへの参照を返します。</span><span class="sxs-lookup"><span data-stu-id="70e08-105">Use the <xref:System.EventArgs> object to return a reference to the clicked node object.</span></span>  
  
2. <span data-ttu-id="70e08-106"><xref:System.Windows.Forms.TreeViewEventArgs>イベントに関連するデータを含むクラスを確認して、どのノードがクリックされたかを確認します。</span><span class="sxs-lookup"><span data-stu-id="70e08-106">Determine which node was clicked by checking the <xref:System.Windows.Forms.TreeViewEventArgs> class, which contains data related to the event.</span></span>  
  
    ```vb  
    Private Sub TreeView1_AfterSelect(ByVal sender As System.Object, _  
    ByVal e As System.Windows.Forms.TreeViewEventArgs) Handles TreeView1.AfterSelect  
       ' Determine by checking the Node property of the TreeViewEventArgs.  
       MessageBox.Show(e.Node.Text)  
    End Sub  
    ```  
  
    ```csharp  
    protected void treeView1_AfterSelect (object sender,
    System.Windows.Forms.TreeViewEventArgs e)  
    {  
       // Determine by checking the Text property.  
       MessageBox.Show(e.Node.Text);  
    }  
    ```  
  
    ```cpp  
    private:  
       void treeView1_AfterSelect(System::Object ^  sender,  
          System::Windows::Forms::TreeViewEventArgs ^  e)  
       {  
          // Determine by checking the Text property.  
          MessageBox::Show(e->Node->Text);  
       }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="70e08-107">別の方法として、 <xref:System.Windows.Forms.MouseEventArgs> イベントまたはイベントのを使用して、クリックが発生し <xref:System.Windows.Forms.Control.MouseDown> たの <xref:System.Windows.Forms.Control.MouseUp> 座標値を取得することもでき <xref:System.Drawing.Point.X%2A> <xref:System.Drawing.Point.Y%2A> <xref:System.Drawing.Point> ます。</span><span class="sxs-lookup"><span data-stu-id="70e08-107">As an alternative, you can use the <xref:System.Windows.Forms.MouseEventArgs> of the <xref:System.Windows.Forms.Control.MouseDown> or <xref:System.Windows.Forms.Control.MouseUp> event to get the <xref:System.Drawing.Point.X%2A> and <xref:System.Drawing.Point.Y%2A> coordinate values of the <xref:System.Drawing.Point> where the click occurred.</span></span> <span data-ttu-id="70e08-108">次に、コントロールのメソッドを使用して、 <xref:System.Windows.Forms.TreeView> <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> どのノードがクリックされたかを確認します。</span><span class="sxs-lookup"><span data-stu-id="70e08-108">Then, use the <xref:System.Windows.Forms.TreeView> control's <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> method to determine which node was clicked.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70e08-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="70e08-109">See also</span></span>

- [<span data-ttu-id="70e08-110">TreeView コントロール</span><span class="sxs-lookup"><span data-stu-id="70e08-110">TreeView Control</span></span>](treeview-control-windows-forms.md)
