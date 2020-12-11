---
title: Windows フォームアプリで印刷プレビューを表示する
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print preview [Windows Forms], displaying
- printing [Windows Forms], print preview
- examples [Windows Forms], print preview
ms.assetid: e394134c-0886-4517-bd8d-edc4a3749eb5
ms.openlocfilehash: 7737cd06001f9acfde5eb44fdff9aaa880f23e79
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980835"
---
# <a name="how-to-display-print-preview-in-windows-forms-applications"></a>方法: Windows フォーム アプリケーションに印刷プレビューを表示する
コントロールを使用すると、ユーザーがドキュメントを印刷する前に頻繁に表示することができ <xref:System.Windows.Forms.PrintPreviewDialog> ます。  
  
 これを行うには、クラスのインスタンスを指定する必要があります。 <xref:System.Drawing.Printing.PrintDocument> これは、印刷するドキュメントです。 コンポーネントで印刷プレビューを使用する方法の詳細については <xref:System.Drawing.Printing.PrintDocument> 、「印刷 [プレビューを使用して Windows フォームで](../advanced/how-to-print-in-windows-forms-using-print-preview.md)印刷する方法」を参照してください。  
  
> [!NOTE]
> 実行時にコントロールを使用するに <xref:System.Windows.Forms.PrintPreviewDialog> は、ローカルまたはネットワーク経由でコンピューターにプリンターがインストールされている必要があります。これは、 <xref:System.Windows.Forms.PrintPreviewDialog> 印刷時のドキュメントの外観をコンポーネントが決定する方法の一部であるためです。  
  
 <xref:System.Windows.Forms.PrintPreviewDialog>コントロールはクラスを使用し <xref:System.Drawing.Printing.PrinterSettings> ます。 さらに、 <xref:System.Windows.Forms.PrintPreviewDialog> コンポーネントと同じように、コントロールは <xref:System.Drawing.Printing.PageSettings> クラスを使用し <xref:System.Windows.Forms.PrintPreviewDialog> ます。 コントロールのプロパティで指定された印刷ドキュメントは、 <xref:System.Windows.Forms.PrintPreviewDialog> <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> クラスとクラスの両方のインスタンスを参照 <xref:System.Drawing.Printing.PrinterSettings> <xref:System.Drawing.Printing.PageSettings> します。これらは、ドキュメントをプレビューウィンドウに表示するために使用されます。  
  
### <a name="to-view-pages-using-the-printpreviewdialog-control"></a>Printプレビューダイアログコントロールを使用してページを表示するには  
  
- <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> メソッドを使用してダイアログ ボックスを表示し、使用する <xref:System.Drawing.Printing.PrintDocument> を指定します。  
  
     次のコード例では、コントロールの <xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.Control.Click> イベントハンドラーがコントロールのインスタンスを開き <xref:System.Windows.Forms.PrintPreviewDialog> ます。 印刷ドキュメントはプロパティで指定され <xref:System.Windows.Forms.PrintDialog.Document%2A> ます。 次の例では、印刷ドキュメントが指定されていません。  
  
     この例では、フォームに <xref:System.Windows.Forms.Button> コントロール、と <xref:System.Drawing.Printing.PrintDocument> いう名前のコンポーネント、およびコントロールが含まれている必要があり `myDocument` <xref:System.Windows.Forms.PrintPreviewDialog> ます。  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       ' The print document 'myDocument' used below  
       ' is merely for an example.  
       ' You will have to specify your own print document.  
       PrintPreviewDialog1.Document = myDocument  
       PrintPreviewDialog1.ShowDialog()  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       // The print document 'myDocument' used below  
       // is merely for an example.  
       // You will have to specify your own print document.  
       printPreviewDialog1.Document = myDocument;  
       printPreviewDialog1.ShowDialog();  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // The print document 'myDocument' used below  
          // is merely for an example.  
          // You will have to specify your own print document.  
          printPreviewDialog1->Document = myDocument;  
          printPreviewDialog1->ShowDialog();  
       }  
    ```  
  
     (Visual C#、Visual C++)フォームのコンストラクターに次のコードを配置して、イベントハンドラーを登録します。  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>関連項目

- [PrintDocument コンポーネント](printdocument-component-windows-forms.md)
- [PrintPreviewDialog コントロール](printpreviewdialog-control-windows-forms.md)
- [Windows フォームにおける印刷のサポート](../advanced/windows-forms-print-support.md)
- [Windows フォーム](../index.yml)
