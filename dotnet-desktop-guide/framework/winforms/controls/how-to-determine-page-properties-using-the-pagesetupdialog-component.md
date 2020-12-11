---
title: '方法: PageSetupDialog コンポーネントを使用してページのプロパティを決定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- page properties
- page setup
- PageSetupDialog component
ms.assetid: 6dae05bc-c0fd-4357-bb93-841a1631d98f
ms.openlocfilehash: 8a015c199193dfd9c43bec53cc93cbf9dc201413
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980851"
---
# <a name="how-to-determine-page-properties-using-the-pagesetupdialog-component"></a>方法: PageSetupDialog コンポーネントを使用してページのプロパティを決定する
[PageSetupDialog](pagesetupdialog-component-windows-forms.md) コンポーネントは、レイアウト、用紙サイズ、およびその他のページ レイアウトの選択肢をドキュメントのユーザーに示します。  
  
 <xref:System.Drawing.Printing.PrintDocument> クラスのインスタンスを指定する必要があります。これは、印刷するドキュメントです。 さらに、ユーザーはコンピューターにローカル プリンターまたはネットワーク プリンターをインストールしておく必要があります。これを基にして、 <xref:System.Windows.Forms.PageSetupDialog> コンポーネントはユーザーに示すページ書式設定選択肢の一部を決定します。  
  
 <xref:System.Windows.Forms.PageSetupDialog> コンポーネントを使用するときに重要なことは、 <xref:System.Drawing.Printing.PageSettings> クラスとの対話方法です。 <xref:System.Drawing.Printing.PageSettings> クラスは、用紙の向き、ページのサイズ、余白など、ページの印刷方法を変更する設定の指定に使用されます。 これらの各設定は、 <xref:System.Drawing.Printing.PageSettings> クラスのプロパティとして表されます。 <xref:System.Windows.Forms.PageSetupDialog> クラスは、ドキュメントに関連付けられている (そして、 <xref:System.Drawing.Printing.PageSettings> プロパティとして表されている) <xref:System.Drawing.Printing.PrintDocument.DefaultPageSettings%2A> クラスの特定のインスタンスに対するこれらのプロパティ値を変更します。  
  
### <a name="to-set-page-properties-using-the-pagesetupdialog-component"></a>PageSetupDialog コンポーネントを使用してページのプロパティを設定するには  
  
1. <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> メソッドを使用してダイアログ ボックスを表示し、使用する <xref:System.Drawing.Printing.PrintDocument> を指定します。  
  
     次の例では、 <xref:System.Windows.Forms.Button> コントロールの <xref:System.Windows.Forms.Control.Click> イベント ハンドラーが、 <xref:System.Windows.Forms.PageSetupDialog> コンポーネントのインスタンスを開きます。 既存のドキュメントは <xref:System.Windows.Forms.PageSetupDialog.Document%2A> プロパティで指定され、その <xref:System.Drawing.Printing.PageSettings.Color%2A?displayProperty=nameWithType> プロパティは `false`に設定されます。  
  
     この例では、フォームに <xref:System.Windows.Forms.Button> コントロール、と <xref:System.Drawing.Printing.PrintDocument> いう名前のコンポーネント、およびコンポーネントがあることを前提としてい `myDocument` <xref:System.Windows.Forms.PageSetupDialog> ます。  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles Button1.Click  
       ' The print document 'myDocument' used below  
       ' is merely for an example.  
       'You will have to specify your own print document.  
       PageSetupDialog1.Document = myDocument  
       ' Sets the print document's color setting to false,  
       ' so that the page will not be printed in color.  
       PageSetupDialog1.Document.DefaultPageSettings.Color = False  
       PageSetupDialog1.ShowDialog()  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       // The print document 'myDocument' used below  
       // is merely for an example.  
       // You will have to specify your own print document.  
       pageSetupDialog1.Document = myDocument;  
       // Sets the print document's color setting to false,  
       // so that the page will not be printed in color.  
       pageSetupDialog1.Document.DefaultPageSettings.Color = false;  
       pageSetupDialog1.ShowDialog();  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void button1_Click(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          // The print document 'myDocument' used below  
          // is merely for an example.  
          // You will have to specify your own print document.  
          pageSetupDialog1->Document = myDocument;  
          // Sets the print document's color setting to false,  
          // so that the page will not be printed in color.  
          pageSetupDialog1->Document->DefaultPageSettings->Color = false;  
          pageSetupDialog1->ShowDialog();  
       }  
    ```  
  
     (Visual C# および Visual C++)フォームのコンストラクターに次のコードを配置して、イベントハンドラーを登録します。  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.PageSetupDialog>
- [方法: 標準の Windows フォーム印刷ジョブを作成する](../advanced/how-to-create-standard-windows-forms-print-jobs.md)
- [PageSetupDialog コンポーネント](pagesetupdialog-component-windows-forms.md)
