---
title: 印刷ジョブの完了
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print jobs [Windows Forms], completing in Windows Forms
- printing [Windows Forms], print jobs
ms.assetid: 23ec74f7-34c5-4710-82a0-ee2914518548
ms.openlocfilehash: 62f67002bfbaf46e73bae06fdaff26efde865c06
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96975013"
---
# <a name="how-to-complete-windows-forms-print-jobs"></a><span data-ttu-id="1c706-102">方法: Windows フォームの印刷ジョブを完了する</span><span class="sxs-lookup"><span data-stu-id="1c706-102">How to: Complete Windows Forms Print Jobs</span></span>
<span data-ttu-id="1c706-103">多くの場合、印刷を伴うワードプロセッサやその他のアプリケーションには、印刷ジョブが完了したことをユーザーに示すオプションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="1c706-103">Frequently, word processors and other applications that involve printing will provide the option to display a message to users that a print job is complete.</span></span> <span data-ttu-id="1c706-104">コンポーネントのイベントを処理することによって、この機能を Windows フォームに提供でき <xref:System.Drawing.Printing.PrintDocument.EndPrint> <xref:System.Drawing.Printing.PrintDocument> ます。</span><span class="sxs-lookup"><span data-stu-id="1c706-104">You can provide this functionality in your Windows Forms by handling the <xref:System.Drawing.Printing.PrintDocument.EndPrint> event of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
 <span data-ttu-id="1c706-105">次の手順では、windows ベースのアプリケーションからの印刷を有効にするための標準的な方法であるコンポーネントを含む Windows ベースのアプリケーションを作成しておく必要があり <xref:System.Drawing.Printing.PrintDocument> ます。</span><span class="sxs-lookup"><span data-stu-id="1c706-105">The following procedure requires that you have created a Windows-based application with a <xref:System.Drawing.Printing.PrintDocument> component on it, which is the standard way of enabling printing from a Windows-based application.</span></span> <span data-ttu-id="1c706-106">コンポーネントを使用した Windows フォームからの印刷の詳細につい <xref:System.Drawing.Printing.PrintDocument> ては、「 [方法: 標準 Windows フォーム印刷ジョブを作成](how-to-create-standard-windows-forms-print-jobs.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c706-106">For more information about printing from Windows Forms using the <xref:System.Drawing.Printing.PrintDocument> component, see [How to: Create Standard Windows Forms Print Jobs](how-to-create-standard-windows-forms-print-jobs.md).</span></span>  
  
### <a name="to-complete-a-print-job"></a><span data-ttu-id="1c706-107">印刷ジョブを完了するには</span><span class="sxs-lookup"><span data-stu-id="1c706-107">To complete a print job</span></span>  
  
1. <span data-ttu-id="1c706-108"><xref:System.Drawing.Printing.PrintDocument.DocumentName%2A>コンポーネントのプロパティを設定 <xref:System.Drawing.Printing.PrintDocument> します。</span><span class="sxs-lookup"><span data-stu-id="1c706-108">Set the <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> property of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
    ```vb  
    PrintDocument1.DocumentName = "MyTextFile"  
    ```  
  
    ```csharp  
    printDocument1.DocumentName = "MyTextFile";  
    ```  
  
    ```cpp  
    printDocument1->DocumentName = "MyTextFile";  
    ```  
  
2. <span data-ttu-id="1c706-109"><xref:System.Drawing.Printing.PrintDocument.EndPrint> イベントを処理するコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="1c706-109">Write code to handle the <xref:System.Drawing.Printing.PrintDocument.EndPrint> event.</span></span>  
  
     <span data-ttu-id="1c706-110">次のコード例では、ドキュメントの印刷が完了したことを示すメッセージボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1c706-110">In the following code example, a message box is displayed, indicating that the document has finished printing.</span></span>  
  
    ```vb  
    Private Sub PrintDocument1_EndPrint(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintEventArgs) Handles PrintDocument1.EndPrint  
       MessageBox.Show(PrintDocument1.DocumentName + " has finished printing.")  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_EndPrint(object sender,
    System.Drawing.Printing.PrintEventArgs e)  
    {  
       MessageBox.Show(printDocument1.DocumentName +
          " has finished printing.");  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_EndPrint(System::Object ^ sender,  
          System::Drawing::Printing::PrintEventArgs ^ e)  
       {  
          MessageBox::Show(String::Concat(printDocument1->DocumentName,  
             " has finished printing."));  
       }  
    ```  
  
     <span data-ttu-id="1c706-111">(Visual C# および Visual C++)フォームのコンストラクターに次のコードを配置して、イベントハンドラーを登録します。</span><span class="sxs-lookup"><span data-stu-id="1c706-111">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.printDocument1.EndPrint += new  
       System.Drawing.Printing.PrintEventHandler  
       (this.printDocument1_EndPrint);  
    ```  
  
    ```cpp  
    this->printDocument1->EndPrint += gcnew  
       System::Drawing::Printing::PrintEventHandler  
       (this, &Form1::printDocument1_EndPrint);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1c706-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="1c706-112">See also</span></span>

- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="1c706-113">Windows フォームにおける印刷のサポート</span><span class="sxs-lookup"><span data-stu-id="1c706-113">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
