---
title: '方法: TreeView コントロールまたは ListView コントロールにカスタム情報を追加する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- ListItem
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- examples [Windows Forms], ListView control
- ListView control [Windows Forms], adding custom information
- TreeView control [Windows Forms], adding custom information
ms.assetid: 68be11de-1d5b-430e-901f-cfbe48d14b19
ms.openlocfilehash: 284bd666d236b765821139a76decd8fedc29b760
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96975157"
---
# <a name="how-to-add-custom-information-to-a-treeview-or-listview-control-windows-forms"></a>方法: TreeView コントロールまたは ListView コントロール (Windows フォーム) にカスタム情報を追加する

派生ノードは、Windows フォーム <xref:System.Windows.Forms.TreeView> コントロールまたはコントロールの派生した項目で作成でき <xref:System.Windows.Forms.ListView> ます。 派生により、必要なフィールドだけではなく、それらを処理するためのカスタム メソッドやコンストラクターも追加できます。 この機能を使用して、顧客オブジェクトを各ツリー ノードや各リスト項目にアタッチすることもできます。 ここでの例はコントロールを対象としてい <xref:System.Windows.Forms.TreeView> ますが、同じアプローチをコントロールに使用することもでき <xref:System.Windows.Forms.ListView> ます。  
  
### <a name="to-derive-a-tree-node"></a>ツリー ノードを派生するには  
  
- クラスから派生した新しいノードクラスを作成します。このクラスには、 <xref:System.Windows.Forms.TreeNode> ファイルパスを記録するカスタムフィールドがあります。  
  
    ```vb  
    Class myTreeNode  
       Inherits TreeNode  
  
       Public FilePath As String  
  
       Sub New(ByVal fp As String)  
          MyBase.New()  
          FilePath = fp  
          Me.Text = fp.Substring(fp.LastIndexOf("\"))  
       End Sub  
    End Class  
    ```  
  
    ```csharp  
    class myTreeNode : TreeNode  
    {  
       public string FilePath;  
  
       public myTreeNode(string fp)  
       {  
          FilePath = fp;  
          this.Text = fp.Substring(fp.LastIndexOf("\\"));  
       }  
    }  
    ```  
  
    ```cpp  
    ref class myTreeNode : public TreeNode  
    {  
    public:  
       System::String ^ FilePath;  
  
       myTreeNode(System::String ^ fp)  
       {  
          FilePath = fp;  
          this->Text = fp->Substring(fp->LastIndexOf("\\"));  
       }  
    };  
    ```  
  
### <a name="to-use-a-derived-tree-node"></a>派生されたツリー ノードを使用するには  
  
1. 新たに派生されたツリー ノードは、関数呼び出しに対するパラメーターとして使用できます。  
  
     次の例では、テキスト ファイルの場所に設定されているパスは My Documents フォルダーです。 このように設定できるのは、Windows オペレーティング システムを実行しているほとんどのコンピューターにこのディレクトリが含まれていると想定できるからです。 また、このようにすることで、最小限のシステム アクセス レベルしか持たないユーザーもアプリケーションを安全に実行できるようになります。  
  
    ```vb  
    ' You should replace the bold text file
    ' in the sample below with a text file of your own choosing.  
    TreeView1.Nodes.Add(New myTreeNode (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\ TextFile.txt ") )  
    ```  
  
    ```csharp  
    // You should replace the bold text file
    // in the sample below with a text file of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    treeView1.Nodes.Add(new myTreeNode(System.Environment.GetFolderPath
       (System.Environment.SpecialFolder.Personal)
       + @"\TextFile.txt") );  
    ```  
  
    ```cpp  
    // You should replace the bold text file
    // in the sample below with a text file of your own choosing.  
    treeView1->Nodes->Add(new myTreeNode(String::Concat(  
       System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::Personal),  
       "\\TextFile.txt")));  
    ```  
  
2. ツリーノードが渡され、それがクラスとして型指定されている場合は、 <xref:System.Windows.Forms.TreeNode> 派生クラスにキャストする必要があります。 キャストとは、ある型のオブジェクトから別の型のオブジェクトに明示的に変換することです。 キャストの詳細については、「 [暗黙的な変換と明示的な変換](/dotnet/visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions) (Visual Basic)」、「 [キャストと型変換](/dotnet/csharp/programming-guide/types/casting-and-type-conversions) (Visual C#)」、または「 [キャスト演算子: ()](/cpp/cpp/cast-operator-parens) (Visual C++)」を参照してください。  
  
    ```vb  
    Public Sub TreeView1_AfterSelect(ByVal sender As Object, ByVal e As System.Windows.Forms.TreeViewEventArgs) Handles TreeView1.AfterSelect  
       Dim mynode As myTreeNode  
       mynode = CType(e.node, myTreeNode)  
       MessageBox.Show("Node selected is " & mynode.filepath)  
    End Sub  
    ```  
  
    ```csharp  
    protected void treeView1_AfterSelect (object sender,  
    System.Windows.Forms.TreeViewEventArgs e)  
    {  
       myTreeNode myNode = (myTreeNode)e.Node;  
       MessageBox.Show("Node selected is " + myNode.FilePath);  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void treeView1_AfterSelect(System::Object ^  sender,  
          System::Windows::Forms::TreeViewEventArgs ^  e)  
       {  
          myTreeNode ^ myNode = safe_cast<myTreeNode^>(e->Node);  
          MessageBox::Show(String::Concat("Node selected is ",
             myNode->FilePath));  
       }  
    ```  
  
## <a name="see-also"></a>関連項目

- [TreeView コントロール](treeview-control-windows-forms.md)
- [ListView コントロール](listview-control-windows-forms.md)
