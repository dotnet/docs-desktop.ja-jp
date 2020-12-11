---
title: 印刷のサポート
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- forms [Windows Forms], printing (using designer)
- printing [Windows Forms], Windows Forms, support
- printing [Windows Forms], print support
ms.assetid: a4a2960c-eb70-48e2-b641-cfb222704e46
ms.openlocfilehash: d6e8f60db7afe2f1b04eaae6fe71aa93e5c22cae
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981135"
---
# <a name="windows-forms-print-support"></a><span data-ttu-id="4ef73-102">Windows フォームにおける印刷のサポート</span><span class="sxs-lookup"><span data-stu-id="4ef73-102">Windows Forms Print Support</span></span>
<span data-ttu-id="4ef73-103">Windows フォームでの印刷は、主に [PrintDocument コンポーネント](../controls/printdocument-component-windows-forms.md) コンポーネントを使用してユーザーを印刷できるようにし、 [printPageSetupDialog dialog Control](../controls/printpreviewdialog-control-windows-forms.md) コントロール、 [PrintDialog コンポーネント](../controls/printdialog-component-windows-forms.md) 、および [コンポーネント](../controls/pagesetupdialog-component-windows-forms.md) コンポーネントを使用して、Windows オペレーティングシステムに慣れているユーザーに使い慣れたグラフィカルインターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="4ef73-103">Printing in Windows Forms consists primarily of using the [PrintDocument Component](../controls/printdocument-component-windows-forms.md) component to enable the user to print, and the [PrintPreviewDialog Control](../controls/printpreviewdialog-control-windows-forms.md) control, [PrintDialog Component](../controls/printdialog-component-windows-forms.md) and [PageSetupDialog Component](../controls/pagesetupdialog-component-windows-forms.md) components to provide a familiar graphical interface to users accustomed to the Windows operating system.</span></span>  
  
 <span data-ttu-id="4ef73-104">通常は、コンポーネントの新しいインスタンスを作成し <xref:System.Drawing.Printing.PrintDocument> 、クラスとクラスを使用して、印刷する内容を示すプロパティを設定 <xref:System.Drawing.Printing.PrinterSettings> <xref:System.Drawing.Printing.PageSettings> します。次に、メソッドを呼び出して、 <xref:System.Drawing.Printing.PrintDocument.Print%2A> ドキュメントを実際に印刷します。</span><span class="sxs-lookup"><span data-stu-id="4ef73-104">Typically, you create a new instance of the <xref:System.Drawing.Printing.PrintDocument> component, set the properties that describe what to print using the <xref:System.Drawing.Printing.PrinterSettings> and <xref:System.Drawing.Printing.PageSettings> classes, and call the <xref:System.Drawing.Printing.PrintDocument.Print%2A> method to actually print the document.</span></span>  
  
 <span data-ttu-id="4ef73-105">Windows ベースのアプリケーションから印刷する過程で、コンポーネントには、印刷 <xref:System.Drawing.Printing.PrintDocument> が行われていること、および印刷ジョブをキャンセルできることをユーザーに通知する [中止印刷] ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4ef73-105">During the course of printing from a Windows-based application, the <xref:System.Drawing.Printing.PrintDocument> component will show an abort print dialog box to alert users to the fact that printing is occurring and to allow the print job to be canceled.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4ef73-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4ef73-106">In This Section</span></span>  
 [<span data-ttu-id="4ef73-107">方法: 標準の Windows フォーム印刷ジョブを作成する</span><span class="sxs-lookup"><span data-stu-id="4ef73-107">How to: Create Standard Windows Forms Print Jobs</span></span>](how-to-create-standard-windows-forms-print-jobs.md)  
 <span data-ttu-id="4ef73-108">コンポーネントを使用して Windows フォームから印刷する方法について説明し <xref:System.Drawing.Printing.PrintDocument> ます。</span><span class="sxs-lookup"><span data-stu-id="4ef73-108">Explains how to use the <xref:System.Drawing.Printing.PrintDocument> component to print from a Windows Form.</span></span>  
  
 [<span data-ttu-id="4ef73-109">方法: 実行時に PrintDialog のユーザー入力をキャプチャする</span><span class="sxs-lookup"><span data-stu-id="4ef73-109">How to: Capture User Input from a PrintDialog at Run Time</span></span>](how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 <span data-ttu-id="4ef73-110">コンポーネントを使用して、選択した印刷オプションをプログラムで変更する方法について説明し <xref:System.Windows.Forms.PrintDialog> ます。</span><span class="sxs-lookup"><span data-stu-id="4ef73-110">Explains how to modify selected print options programmatically using the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
 [<span data-ttu-id="4ef73-111">方法: Windows フォームでユーザーのコンピューターに接続されたプリンターを選択する</span><span class="sxs-lookup"><span data-stu-id="4ef73-111">How to: Choose the Printers Attached to a User's Computer in Windows Forms</span></span>](how-to-choose-the-printers-attached-to-user-computer-in-windows-forms.md)  
 <span data-ttu-id="4ef73-112">実行時にコンポーネントを使用して印刷するようにプリンターを変更する方法について説明し <xref:System.Windows.Forms.PrintDialog> ます。</span><span class="sxs-lookup"><span data-stu-id="4ef73-112">Describes changing the printer to print to using the <xref:System.Windows.Forms.PrintDialog> component at run time.</span></span>  
  
 [<span data-ttu-id="4ef73-113">方法: Windows フォームでグラフィックスを印刷する</span><span class="sxs-lookup"><span data-stu-id="4ef73-113">How to: Print Graphics in Windows Forms</span></span>](how-to-print-graphics-in-windows-forms.md)  
 <span data-ttu-id="4ef73-114">プリンターへのグラフィックスの送信について説明します。</span><span class="sxs-lookup"><span data-stu-id="4ef73-114">Describes sending graphics to the printer.</span></span>  
  
 [<span data-ttu-id="4ef73-115">方法: Windows フォームで複数ページのテキスト ファイルを印刷する</span><span class="sxs-lookup"><span data-stu-id="4ef73-115">How to: Print a Multi-Page Text File in Windows Forms</span></span>](how-to-print-a-multi-page-text-file-in-windows-forms.md)  
 <span data-ttu-id="4ef73-116">プリンターにテキストを送信する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4ef73-116">Describes sending text to the printer.</span></span>  
  
 [<span data-ttu-id="4ef73-117">方法: Windows フォームの印刷ジョブを完了する</span><span class="sxs-lookup"><span data-stu-id="4ef73-117">How to: Complete Windows Forms Print Jobs</span></span>](how-to-complete-windows-forms-print-jobs.md)  
 <span data-ttu-id="4ef73-118">印刷ジョブの完了をユーザーに通知する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4ef73-118">Explains how to alert users to the completion of a print job.</span></span>  
  
 [<span data-ttu-id="4ef73-119">方法: Windows フォームを印刷する</span><span class="sxs-lookup"><span data-stu-id="4ef73-119">How to: Print a Windows Form</span></span>](how-to-print-a-windows-form.md)  
 <span data-ttu-id="4ef73-120">現在のフォームのコピーを印刷する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4ef73-120">Shows how to print a copy of the current form.</span></span>  
  
 [<span data-ttu-id="4ef73-121">方法: Windows フォームで印刷プレビューを使用して印刷する</span><span class="sxs-lookup"><span data-stu-id="4ef73-121">How to: Print in Windows Forms Using Print Preview</span></span>](how-to-print-in-windows-forms-using-print-preview.md)  
 <span data-ttu-id="4ef73-122">を使用してドキュメントを印刷する方法について説明し <xref:System.Windows.Forms.PrintPreviewDialog> ます。</span><span class="sxs-lookup"><span data-stu-id="4ef73-122">Shows how to use a <xref:System.Windows.Forms.PrintPreviewDialog> for printing a document.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4ef73-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="4ef73-123">Related Sections</span></span>  
 [<span data-ttu-id="4ef73-124">PrintDocument コンポーネント</span><span class="sxs-lookup"><span data-stu-id="4ef73-124">PrintDocument Component</span></span>](../controls/printdocument-component-windows-forms.md)  
 <span data-ttu-id="4ef73-125">コンポーネントの使用方法について説明 <xref:System.Drawing.Printing.PrintDocument> します。</span><span class="sxs-lookup"><span data-stu-id="4ef73-125">Explains usage of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
 [<span data-ttu-id="4ef73-126">PrintDialog コンポーネント</span><span class="sxs-lookup"><span data-stu-id="4ef73-126">PrintDialog Component</span></span>](../controls/printdialog-component-windows-forms.md)  
 <span data-ttu-id="4ef73-127">コンポーネントの使用方法について説明 <xref:System.Windows.Forms.PrintDialog> します。</span><span class="sxs-lookup"><span data-stu-id="4ef73-127">Explains usage of the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
 [<span data-ttu-id="4ef73-128">PrintPreviewDialog コントロール</span><span class="sxs-lookup"><span data-stu-id="4ef73-128">PrintPreviewDialog Control</span></span>](../controls/printpreviewdialog-control-windows-forms.md)  
 <span data-ttu-id="4ef73-129">コントロールの使用方法について説明 <xref:System.Windows.Forms.PrintPreviewDialog> します。</span><span class="sxs-lookup"><span data-stu-id="4ef73-129">Explains usage of the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span>  
  
 [<span data-ttu-id="4ef73-130">PageSetupDialog コンポーネント</span><span class="sxs-lookup"><span data-stu-id="4ef73-130">PageSetupDialog Component</span></span>](../controls/pagesetupdialog-component-windows-forms.md)  
 <span data-ttu-id="4ef73-131">コンポーネントの使用方法について説明 <xref:System.Windows.Forms.PageSetupDialog> します。</span><span class="sxs-lookup"><span data-stu-id="4ef73-131">Explains usage of the <xref:System.Windows.Forms.PageSetupDialog> component.</span></span>  
  
 <xref:System.Drawing.Printing>  
 <span data-ttu-id="4ef73-132">名前空間のクラスについて説明し <xref:System.Drawing.Printing> ます。</span><span class="sxs-lookup"><span data-stu-id="4ef73-132">Describes the classes in the <xref:System.Drawing.Printing> namespace.</span></span>
