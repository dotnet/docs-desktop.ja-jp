---
title: '方法: MenuStrip を使用して MDI ウィンドウの一覧を作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MDI [Windows Forms], creating window lists
- MenuStrip control [Windows Forms], creating window lists
ms.assetid: 04fb414b-811f-4a83-aab6-b4a24646dec5
ms.openlocfilehash: f013c3df2ab5783a22fe2c34402dc53a328cafa2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980891"
---
# <a name="how-to-create-an-mdi-window-list-with-menustrip-windows-forms"></a>方法 : MenuStrip を使用して MDI ウィンドウの一覧を作成する (Windows フォーム)
マルチドキュメントインターフェイス (MDI) を使用して、複数のドキュメントを同時に開くことができるアプリケーションを作成し、ドキュメント間でコンテンツをコピーして貼り付けることができます。  
  
 この手順では、親の [ウィンドウ] メニューにあるすべてのアクティブな子フォームの一覧を作成する方法について説明します。  
  
### <a name="to-create-an-mdi-window-list-on-a-menustrip"></a>MenuStrip で MDI ウィンドウの一覧を作成するには  
  
1. フォームを作成し、その <xref:System.Windows.Forms.Form.IsMdiContainer%2A> プロパティを `true` に設定します。  
  
2. フォームに <xref:System.Windows.Forms.MenuStrip> を追加します。  
  
3. トップレベルの2つのメニュー項目をに追加 <xref:System.Windows.Forms.MenuStrip> し、それらのプロパティを <xref:System.Windows.Forms.Control.Text%2A> とに設定し `&File` `&Window` ます。  
  
4. サブメニュー項目を `&File` メニュー項目に追加し、その <xref:System.Windows.Forms.ToolStripItem.Text%2A> プロパティを「`&Open`」に設定します。  
  
5. の <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> プロパティ <xref:System.Windows.Forms.MenuStrip> をに設定し `&Window` <xref:System.Windows.Forms.ToolStripMenuItem> ます。  
  
6. プロジェクトにフォームを追加し、必要なコントロールを追加します (別のコントロールなど) <xref:System.Windows.Forms.MenuStrip> 。  
  
7. <xref:System.Windows.Forms.ToolStripMenuItem> の `&New` の <xref:System.Windows.Forms.Control.Click> イベントにイベント ハンドラーを作成します。  
  
8. イベントハンドラー内で、次のようなコードを挿入して、の新しいインスタンスを `Form2` の MDI 子として作成および表示し `Form1` ます。  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(ByVal sender As _  
    System.Object, ByVal e As System.EventArgs) Handles _  
    openToolStripMenuItem.Click  
        Dim NewMDIChild As New Form2()  
        'Set the parent form of the child window.  
            NewMDIChild.MdiParent = Me  
        'Display the new form.  
            NewMDIChild.Show()  
    End Sub  
    ```  
  
    ```csharp  
    private void newToolStripMenuItem_Click(object sender, EventArgs e)  
    {  
        Form2 newMDIChild = new Form2();  
        // Set the parent form of the child window.  
            newMDIChild.MdiParent = this;  
        // Display the new form.  
            newMDIChild.Show();  
    }  
    ```  
  
9. イベントハンドラーを登録するには、次のようなコードをに配置し `&New` <xref:System.Windows.Forms.ToolStripMenuItem> ます。  
  
    ```vb  
    Private Sub newToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles newToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.newToolStripMenuItem.Click += new System.EventHandler(this.newToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 この例で必要な要素は次のとおりです。  
  
- `Form1` と `Form2` という名前の 2 つの <xref:System.Windows.Forms.Form> コントロール。  
  
- `Form1` 上の `menuStrip1` という名前の <xref:System.Windows.Forms.MenuStrip> コントロールと、`Form2` 上の `menuStrip2` という名前の <xref:System.Windows.Forms.MenuStrip> コントロール。  
  
- <xref:System?displayProperty=nameWithType> アセンブリおよび <xref:System.Windows.Forms?displayProperty=nameWithType> アセンブリへの参照。  
  
## <a name="see-also"></a>関連項目

- [方法: MDI 親フォームを作成する](../advanced/how-to-create-mdi-parent-forms.md)
- [方法: MDI 子フォームを作成する](../advanced/how-to-create-mdi-child-forms.md)
- [MenuStrip コントロール](menustrip-control-windows-forms.md)
