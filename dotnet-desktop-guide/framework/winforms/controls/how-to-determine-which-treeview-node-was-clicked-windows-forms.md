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
# <a name="how-to-determine-which-treeview-node-was-clicked-windows-forms"></a>方法 : クリックされた TreeView ノード (Windows フォーム) を判別する
Windows フォームコントロールを使用する場合の <xref:System.Windows.Forms.TreeView> 一般的なタスクは、どのノードがクリックされたかを判断し、適切に対応することです。  
  
### <a name="to-determine-which-treeview-node-was-clicked"></a>クリックされた TreeView ノードを確認するには  
  
1. オブジェクトを使用して、クリックされた <xref:System.EventArgs> ノードオブジェクトへの参照を返します。  
  
2. <xref:System.Windows.Forms.TreeViewEventArgs>イベントに関連するデータを含むクラスを確認して、どのノードがクリックされたかを確認します。  
  
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
    > 別の方法として、 <xref:System.Windows.Forms.MouseEventArgs> イベントまたはイベントのを使用して、クリックが発生し <xref:System.Windows.Forms.Control.MouseDown> たの <xref:System.Windows.Forms.Control.MouseUp> 座標値を取得することもでき <xref:System.Drawing.Point.X%2A> <xref:System.Drawing.Point.Y%2A> <xref:System.Drawing.Point> ます。 次に、コントロールのメソッドを使用して、 <xref:System.Windows.Forms.TreeView> <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> どのノードがクリックされたかを確認します。  
  
## <a name="see-also"></a>関連項目

- [TreeView コントロール](treeview-control-windows-forms.md)
