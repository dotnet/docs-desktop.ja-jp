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
# <a name="how-to-display-print-preview-in-windows-forms-applications"></a><span data-ttu-id="59624-102">方法: Windows フォーム アプリケーションに印刷プレビューを表示する</span><span class="sxs-lookup"><span data-stu-id="59624-102">How to: Display Print Preview in Windows Forms Applications</span></span>
<span data-ttu-id="59624-103">コントロールを使用すると、ユーザーがドキュメントを印刷する前に頻繁に表示することができ <xref:System.Windows.Forms.PrintPreviewDialog> ます。</span><span class="sxs-lookup"><span data-stu-id="59624-103">You can use the <xref:System.Windows.Forms.PrintPreviewDialog> control to enable users to display a document, often before it is to be printed.</span></span>  
  
 <span data-ttu-id="59624-104">これを行うには、クラスのインスタンスを指定する必要があります。 <xref:System.Drawing.Printing.PrintDocument> これは、印刷するドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="59624-104">To do this, you need to specify an instance of the <xref:System.Drawing.Printing.PrintDocument> class; this is the document to be printed.</span></span> <span data-ttu-id="59624-105">コンポーネントで印刷プレビューを使用する方法の詳細については <xref:System.Drawing.Printing.PrintDocument> 、「印刷 [プレビューを使用して Windows フォームで](../advanced/how-to-print-in-windows-forms-using-print-preview.md)印刷する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59624-105">For more information about using print preview with the <xref:System.Drawing.Printing.PrintDocument> component, see [How to: Print in Windows Forms Using Print Preview](../advanced/how-to-print-in-windows-forms-using-print-preview.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="59624-106">実行時にコントロールを使用するに <xref:System.Windows.Forms.PrintPreviewDialog> は、ローカルまたはネットワーク経由でコンピューターにプリンターがインストールされている必要があります。これは、 <xref:System.Windows.Forms.PrintPreviewDialog> 印刷時のドキュメントの外観をコンポーネントが決定する方法の一部であるためです。</span><span class="sxs-lookup"><span data-stu-id="59624-106">To use the <xref:System.Windows.Forms.PrintPreviewDialog> control at run time, users must have a printer installed on their computer, either locally or through a network, as this is partly how the <xref:System.Windows.Forms.PrintPreviewDialog> component determines how a document will look when printed.</span></span>  
  
 <span data-ttu-id="59624-107"><xref:System.Windows.Forms.PrintPreviewDialog>コントロールはクラスを使用し <xref:System.Drawing.Printing.PrinterSettings> ます。</span><span class="sxs-lookup"><span data-stu-id="59624-107">The <xref:System.Windows.Forms.PrintPreviewDialog> control uses the <xref:System.Drawing.Printing.PrinterSettings> class.</span></span> <span data-ttu-id="59624-108">さらに、 <xref:System.Windows.Forms.PrintPreviewDialog> コンポーネントと同じように、コントロールは <xref:System.Drawing.Printing.PageSettings> クラスを使用し <xref:System.Windows.Forms.PrintPreviewDialog> ます。</span><span class="sxs-lookup"><span data-stu-id="59624-108">Additionally, the <xref:System.Windows.Forms.PrintPreviewDialog> control uses the <xref:System.Drawing.Printing.PageSettings> class, just as the <xref:System.Windows.Forms.PrintPreviewDialog> component does.</span></span> <span data-ttu-id="59624-109">コントロールのプロパティで指定された印刷ドキュメントは、 <xref:System.Windows.Forms.PrintPreviewDialog> <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> クラスとクラスの両方のインスタンスを参照 <xref:System.Drawing.Printing.PrinterSettings> <xref:System.Drawing.Printing.PageSettings> します。これらは、ドキュメントをプレビューウィンドウに表示するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="59624-109">The print document specified in the <xref:System.Windows.Forms.PrintPreviewDialog> control's <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> property refers to instances of both the <xref:System.Drawing.Printing.PrinterSettings> and <xref:System.Drawing.Printing.PageSettings> classes, and these are used to render the document in the preview window.</span></span>  
  
### <a name="to-view-pages-using-the-printpreviewdialog-control"></a><span data-ttu-id="59624-110">Printプレビューダイアログコントロールを使用してページを表示するには</span><span class="sxs-lookup"><span data-stu-id="59624-110">To view pages using the PrintPreviewDialog control</span></span>  
  
- <span data-ttu-id="59624-111"><xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> メソッドを使用してダイアログ ボックスを表示し、使用する <xref:System.Drawing.Printing.PrintDocument> を指定します。</span><span class="sxs-lookup"><span data-stu-id="59624-111">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box, specifying the <xref:System.Drawing.Printing.PrintDocument> to use.</span></span>  
  
     <span data-ttu-id="59624-112">次のコード例では、コントロールの <xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.Control.Click> イベントハンドラーがコントロールのインスタンスを開き <xref:System.Windows.Forms.PrintPreviewDialog> ます。</span><span class="sxs-lookup"><span data-stu-id="59624-112">In the following code example, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens an instance of the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span> <span data-ttu-id="59624-113">印刷ドキュメントはプロパティで指定され <xref:System.Windows.Forms.PrintDialog.Document%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="59624-113">The print document is specified in the <xref:System.Windows.Forms.PrintDialog.Document%2A> property.</span></span> <span data-ttu-id="59624-114">次の例では、印刷ドキュメントが指定されていません。</span><span class="sxs-lookup"><span data-stu-id="59624-114">In the example below, no print document is specified.</span></span>  
  
     <span data-ttu-id="59624-115">この例では、フォームに <xref:System.Windows.Forms.Button> コントロール、と <xref:System.Drawing.Printing.PrintDocument> いう名前のコンポーネント、およびコントロールが含まれている必要があり `myDocument` <xref:System.Windows.Forms.PrintPreviewDialog> ます。</span><span class="sxs-lookup"><span data-stu-id="59624-115">The example requires that your form has a <xref:System.Windows.Forms.Button> control, a <xref:System.Drawing.Printing.PrintDocument> component named `myDocument`, and a <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span>  
  
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
  
     <span data-ttu-id="59624-116">(Visual C#、Visual C++)フォームのコンストラクターに次のコードを配置して、イベントハンドラーを登録します。</span><span class="sxs-lookup"><span data-stu-id="59624-116">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="59624-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="59624-117">See also</span></span>

- [<span data-ttu-id="59624-118">PrintDocument コンポーネント</span><span class="sxs-lookup"><span data-stu-id="59624-118">PrintDocument Component</span></span>](printdocument-component-windows-forms.md)
- [<span data-ttu-id="59624-119">PrintPreviewDialog コントロール</span><span class="sxs-lookup"><span data-stu-id="59624-119">PrintPreviewDialog Control</span></span>](printpreviewdialog-control-windows-forms.md)
- [<span data-ttu-id="59624-120">Windows フォームにおける印刷のサポート</span><span class="sxs-lookup"><span data-stu-id="59624-120">Windows Forms Print Support</span></span>](../advanced/windows-forms-print-support.md)
- [<span data-ttu-id="59624-121">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="59624-121">Windows Forms</span></span>](../index.yml)
