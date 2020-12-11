---
title: 標準の印刷ジョブを作成する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- printing [Windows Forms]
- printing [Windows Forms], creating print jobs
- printing [Visual Basic], in Windows applications
ms.assetid: 03342b90-9cfe-40b2-838b-b479a13c5dea
ms.openlocfilehash: d9607de7c74132e0d7dce605b16d62c79b7dbccb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96979768"
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a><span data-ttu-id="5ace5-102">方法: 標準の Windows フォーム印刷ジョブを作成する</span><span class="sxs-lookup"><span data-stu-id="5ace5-102">How to: Create Standard Windows Forms Print Jobs</span></span>
<span data-ttu-id="5ace5-103">Windows フォームでの印刷の基礎は、 <xref:System.Drawing.Printing.PrintDocument> 特にイベントであるコンポーネントです <xref:System.Drawing.Printing.PrintDocument.PrintPage> 。</span><span class="sxs-lookup"><span data-stu-id="5ace5-103">The foundation of printing in Windows Forms is the <xref:System.Drawing.Printing.PrintDocument> component—more specifically, the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span> <span data-ttu-id="5ace5-104">イベントを処理するコードを記述することによって <xref:System.Drawing.Printing.PrintDocument.PrintPage> 、印刷する内容と印刷方法を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5ace5-104">By writing code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event, you can specify what to print and how to print it.</span></span>  
  
### <a name="to-create-a-print-job"></a><span data-ttu-id="5ace5-105">印刷ジョブを作成するには</span><span class="sxs-lookup"><span data-stu-id="5ace5-105">To create a print job</span></span>  
  
1. <span data-ttu-id="5ace5-106">コンポーネントを <xref:System.Drawing.Printing.PrintDocument> フォームに追加します。</span><span class="sxs-lookup"><span data-stu-id="5ace5-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2. <span data-ttu-id="5ace5-107"><xref:System.Drawing.Printing.PrintDocument.PrintPage> イベントを処理するコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="5ace5-107">Write code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>  
  
     <span data-ttu-id="5ace5-108">独自の印刷ロジックをコーディングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ace5-108">You will have to code your own printing logic.</span></span> <span data-ttu-id="5ace5-109">また、印刷する素材を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ace5-109">Additionally, you will have to specify the material to be printed.</span></span>  
  
     <span data-ttu-id="5ace5-110">次のコード例では、赤い四角形の形状のサンプルグラフィックがイベントハンドラーに作成され、 <xref:System.Drawing.Printing.PrintDocument.PrintPage> 印刷される素材として機能します。</span><span class="sxs-lookup"><span data-stu-id="5ace5-110">In the following code example, a sample graphic in the shape of a red rectangle is created in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler to act as material to be printed.</span></span>  
  
    ```vb  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillRectangle(Brushes.Red, New Rectangle(500, 500, 500, 500))  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_PrintPage(object sender,
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Red,
         new Rectangle(500, 500, 500, 500));  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Red,  
             Rectangle(500, 500, 500, 500));  
       }  
    ```  
  
     <span data-ttu-id="5ace5-111">(Visual C# および Visual C++)フォームのコンストラクターに次のコードを配置して、イベントハンドラーを登録します。</span><span class="sxs-lookup"><span data-stu-id="5ace5-111">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
    ```  
  
    ```cpp  
    printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    ```  
  
     <span data-ttu-id="5ace5-112">また、イベントおよびイベントのコードを記述することもできます。たとえば、 <xref:System.Drawing.Printing.PrintDocument.BeginPrint> <xref:System.Drawing.Printing.PrintDocument.EndPrint> 印刷するページの総数を表す整数を含め、各ページが印刷するたびにデクリメントします。</span><span class="sxs-lookup"><span data-stu-id="5ace5-112">You may also want to write code for the <xref:System.Drawing.Printing.PrintDocument.BeginPrint> and <xref:System.Drawing.Printing.PrintDocument.EndPrint> events, perhaps including an integer representing the total number of pages to print that is decremented as each page prints.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="5ace5-113">フォームにコンポーネントを追加して、 <xref:System.Windows.Forms.PrintDialog> ユーザーに対してクリーンで効率的なユーザーインターフェイス (UI) を提供できます。</span><span class="sxs-lookup"><span data-stu-id="5ace5-113">You can add a <xref:System.Windows.Forms.PrintDialog> component to your form to provide a clean and efficient user interface (UI) to your users.</span></span> <span data-ttu-id="5ace5-114"><xref:System.Windows.Forms.PrintDialog.Document%2A>コンポーネントのプロパティを設定 <xref:System.Windows.Forms.PrintDialog> すると、フォーム上で作業している印刷ドキュメントに関連するプロパティを設定できます。</span><span class="sxs-lookup"><span data-stu-id="5ace5-114">Setting the <xref:System.Windows.Forms.PrintDialog.Document%2A> property of the <xref:System.Windows.Forms.PrintDialog> component enables you to set properties related to the print document you are working with on your form.</span></span> <span data-ttu-id="5ace5-115">コンポーネントの詳細については <xref:System.Windows.Forms.PrintDialog> 、「 [PrintDialog コンポーネント](../controls/printdialog-component-windows-forms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ace5-115">For more information about the <xref:System.Windows.Forms.PrintDialog> component, see [PrintDialog Component](../controls/printdialog-component-windows-forms.md).</span></span>  
  
     <span data-ttu-id="5ace5-116">プログラムで印刷ジョブを作成する方法など、Windows フォーム印刷ジョブの詳細については、「」を参照してください <xref:System.Drawing.Printing.PrintPageEventArgs> 。</span><span class="sxs-lookup"><span data-stu-id="5ace5-116">For more information about the specifics of Windows Forms print jobs, including how to create a print job programmatically, see <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ace5-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="5ace5-117">See also</span></span>

- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="5ace5-118">Windows フォームにおける印刷のサポート</span><span class="sxs-lookup"><span data-stu-id="5ace5-118">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
