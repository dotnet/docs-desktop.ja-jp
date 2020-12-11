---
title: '方法: 実行時に PrintDialog のユーザー入力をキャプチャする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print options [Windows Forms], changing at run time
- printing [Windows Forms], options
- print options
- run time [Windows Forms], changing print options
ms.assetid: 438501d8-9a70-4fb3-aae6-e46579aba0c6
ms.openlocfilehash: 2aaf988f362baf9cd80eb16e4a08f7f65a5077bb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980083"
---
# <a name="how-to-capture-user-input-from-a-printdialog-at-run-time"></a><span data-ttu-id="68b04-102">方法: 実行時に PrintDialog のユーザー入力をキャプチャする</span><span class="sxs-lookup"><span data-stu-id="68b04-102">How to: Capture User Input from a PrintDialog at Run Time</span></span>
<span data-ttu-id="68b04-103">デザイン時に印刷に関連するオプションを設定することもできますが、ユーザーによって選択される可能性があるため、実行時にこれらのオプションを変更することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="68b04-103">While you can set options related to printing at design time, you will sometimes want to change these options at run time, most likely because of choices made by the user.</span></span> <span data-ttu-id="68b04-104">およびコンポーネントを使用して、ドキュメントを印刷するためのユーザー入力をキャプチャでき <xref:System.Windows.Forms.PrintDialog> <xref:System.Drawing.Printing.PrintDocument> ます。</span><span class="sxs-lookup"><span data-stu-id="68b04-104">You can capture user input for printing a document using the <xref:System.Windows.Forms.PrintDialog> and the <xref:System.Drawing.Printing.PrintDocument> components.</span></span>  
  
### <a name="to-change-print-options-programmatically"></a><span data-ttu-id="68b04-105">印刷オプションをプログラムで変更するには</span><span class="sxs-lookup"><span data-stu-id="68b04-105">To change print options programmatically</span></span>  
  
1. <span data-ttu-id="68b04-106"><xref:System.Windows.Forms.PrintDialog> <xref:System.Drawing.Printing.PrintDocument> フォームにおよびコンポーネントを追加します。</span><span class="sxs-lookup"><span data-stu-id="68b04-106">Add a <xref:System.Windows.Forms.PrintDialog> and a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2. <span data-ttu-id="68b04-107">のプロパティを、 <xref:System.Windows.Forms.PrintDialog.Document%2A> <xref:System.Windows.Forms.PrintDialog> <xref:System.Drawing.Printing.PrintDocument> フォームに追加されたに設定します。</span><span class="sxs-lookup"><span data-stu-id="68b04-107">Set the <xref:System.Windows.Forms.PrintDialog.Document%2A> property of the <xref:System.Windows.Forms.PrintDialog> to the <xref:System.Drawing.Printing.PrintDocument> added to the form.</span></span>  
  
    ```vb  
    PrintDialog1.Document = PrintDocument1  
    ```  
  
    ```csharp  
    printDialog1.Document = PrintDocument1;  
    ```  
  
    ```cpp  
    printDialog1->Document = PrintDocument1;  
    ```  
  
3. <span data-ttu-id="68b04-108"><xref:System.Windows.Forms.PrintDialog>メソッドを使用して、コンポーネントを表示し <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="68b04-108">Display the <xref:System.Windows.Forms.PrintDialog> component by using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
    ```vb  
    PrintDialog1.ShowDialog()  
    ```  
  
    ```csharp  
    printDialog1.ShowDialog();  
    ```  
  
    ```cpp  
    printDialog1->ShowDialog();  
    ```  
  
4. <span data-ttu-id="68b04-109">ダイアログからのユーザーの印刷オプションは、 <xref:System.Drawing.Printing.PrinterSettings> コンポーネントのプロパティにコピーされ <xref:System.Drawing.Printing.PrintDocument> ます。</span><span class="sxs-lookup"><span data-stu-id="68b04-109">The user's printing choices from the dialog will be copied to the <xref:System.Drawing.Printing.PrinterSettings> property of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68b04-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="68b04-110">See also</span></span>

- [<span data-ttu-id="68b04-111">方法: Windows フォームで複数ページのテキスト ファイルを印刷する</span><span class="sxs-lookup"><span data-stu-id="68b04-111">How to: Print a Multi-Page Text File in Windows Forms</span></span>](how-to-print-a-multi-page-text-file-in-windows-forms.md)
- [<span data-ttu-id="68b04-112">Windows フォームにおける印刷のサポート</span><span class="sxs-lookup"><span data-stu-id="68b04-112">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
