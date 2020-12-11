---
title: '方法: PrintTickets を検証およびマージする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- merging PrintTickets [WPF]
- PrintTicket [WPF], merging
- validation of PrintTickets [WPF]
- PrintTicket [WPF], validation
ms.assetid: 4fe2d501-d0b0-4fef-86af-6ffe6c162532
ms.openlocfilehash: bd7f399555b343a52ec6f36aa3b8c706747d8b06
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985191"
---
# <a name="how-to-validate-and-merge-printtickets"></a><span data-ttu-id="85393-102">方法: PrintTickets を検証およびマージする</span><span class="sxs-lookup"><span data-stu-id="85393-102">How to: Validate and Merge PrintTickets</span></span>
<span data-ttu-id="85393-103">Microsoft Windows の[印刷スキーマ](/windows/win32/printdocs/printschema)には、柔軟で拡張可能な <xref:System.Printing.PrintCapabilities> および <xref:System.Printing.PrintTicket> 要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="85393-103">The Microsoft Windows [Print Schema](/windows/win32/printdocs/printschema) includes the flexible and extensible <xref:System.Printing.PrintCapabilities> and <xref:System.Printing.PrintTicket> elements.</span></span> <span data-ttu-id="85393-104">前者では、印刷デバイスの機能の明細を示し、後者では、ドキュメントの特定のシーケンス、個々のドキュメント、または個々のページに関してそれらの機能をデバイスでどのように使用するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="85393-104">The former itemizes the capabilities of a print device and the latter specifies how the device should use those capabilities with respect to a particular sequence of documents, individual document, or individual page.</span></span>  
  
 <span data-ttu-id="85393-105">印刷をサポートするアプリケーションの一般的なタスク シーケンスは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="85393-105">A typical sequence of tasks for an application that supports printing would be as follows.</span></span>  
  
1. <span data-ttu-id="85393-106">プリンターの機能を確認します。</span><span class="sxs-lookup"><span data-stu-id="85393-106">Determine a printer's capabilities.</span></span>  
  
2. <span data-ttu-id="85393-107">それらの機能を使用するように <xref:System.Printing.PrintTicket> を構成します。</span><span class="sxs-lookup"><span data-stu-id="85393-107">Configure a <xref:System.Printing.PrintTicket> to use those capabilities.</span></span>  
  
3. <span data-ttu-id="85393-108"><xref:System.Printing.PrintTicket> を検証します。</span><span class="sxs-lookup"><span data-stu-id="85393-108">Validate the <xref:System.Printing.PrintTicket>.</span></span>  
  
 <span data-ttu-id="85393-109">この記事では、この実行方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="85393-109">This article shows how to do this.</span></span>  
  
## <a name="example"></a><span data-ttu-id="85393-110">例</span><span class="sxs-lookup"><span data-stu-id="85393-110">Example</span></span>  
 <span data-ttu-id="85393-111">以下の簡単な例では、プリンターが両面印刷をサポートできるかどうかにのみ関心があります。</span><span class="sxs-lookup"><span data-stu-id="85393-111">In the simple example below, we are interested only in whether a printer can support duplexing — two-sided printing.</span></span> <span data-ttu-id="85393-112">主な手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="85393-112">The major steps are as follows.</span></span>  
  
1. <span data-ttu-id="85393-113"><xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> メソッドを使用して <xref:System.Printing.PrintCapabilities> オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="85393-113">Get a <xref:System.Printing.PrintCapabilities> object with the <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> method.</span></span>  
  
2. <span data-ttu-id="85393-114">必要な機能があるかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="85393-114">Test for the presence of the capability you want.</span></span> <span data-ttu-id="85393-115">以下の例では、<xref:System.Printing.PrintCapabilities> オブジェクトの <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> プロパティをテストして、用紙の長辺に沿って "ページめくり" を行って用紙の両面に印刷できるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="85393-115">In the example below, we test the <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> property of the <xref:System.Printing.PrintCapabilities> object for the presence of the capability of printing on both sides of a sheet of paper with the "page turning" along the long side of the sheet.</span></span> <span data-ttu-id="85393-116"><xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> はコレクションなので、<xref:System.Collections.ObjectModel.ReadOnlyCollection%601> の `Contains` メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="85393-116">Since <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> is a collection, we use the `Contains` method of <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="85393-117">これは厳密には必要ありません。</span><span class="sxs-lookup"><span data-stu-id="85393-117">This step is not strictly necessary.</span></span> <span data-ttu-id="85393-118">以下で使用されている <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> メソッドによって、<xref:System.Printing.PrintTicket> の各要求がプリンターの機能と照合されます。</span><span class="sxs-lookup"><span data-stu-id="85393-118">The <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> method used below will check each request in the <xref:System.Printing.PrintTicket> against the capabilities of the printer.</span></span> <span data-ttu-id="85393-119">要求された機能がプリンターでサポートされていない場合、プリンター ドライバーによって、メソッドから返された <xref:System.Printing.PrintTicket> の代替要求が置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="85393-119">If the requested capability is not supported by printer, the printer driver will substitute an alternative request in the <xref:System.Printing.PrintTicket> returned by the method.</span></span>  
  
3. <span data-ttu-id="85393-120">プリンターで両面印刷がサポートされている場合、このサンプル コードでは両面印刷を要求する <xref:System.Printing.PrintTicket> が作成されます。</span><span class="sxs-lookup"><span data-stu-id="85393-120">If the printer supports duplexing, the sample code creates a <xref:System.Printing.PrintTicket> that asks for duplexing.</span></span> <span data-ttu-id="85393-121">ただし、アプリケーションによって、<xref:System.Printing.PrintTicket> 要素で使用可能なすべてのプリンター設定が指定されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="85393-121">But the application does not specify every possible printer setting available in the <xref:System.Printing.PrintTicket> element.</span></span> <span data-ttu-id="85393-122">これは、プログラマとプログラム時間の両方の点で無駄です。</span><span class="sxs-lookup"><span data-stu-id="85393-122">That would be wasteful of both programmer and program time.</span></span> <span data-ttu-id="85393-123">代わりに、コードで両面印刷要求のみを設定し、この <xref:System.Printing.PrintTicket> を、既存の完全に構成済みで検証済みの <xref:System.Printing.PrintTicket> (この場合はユーザーの既定値の <xref:System.Printing.PrintTicket>) とマージします。</span><span class="sxs-lookup"><span data-stu-id="85393-123">Instead, the code sets only the duplexing request and then merges this <xref:System.Printing.PrintTicket> with an existing, fully configured and validated, <xref:System.Printing.PrintTicket>, in this case, the user's default <xref:System.Printing.PrintTicket>.</span></span>  
  
4. <span data-ttu-id="85393-124">そのため、このサンプルでは、<xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> メソッドを呼び出し、新しい最小の <xref:System.Printing.PrintTicket> をユーザーの既定値の <xref:System.Printing.PrintTicket> とマージします。</span><span class="sxs-lookup"><span data-stu-id="85393-124">Accordingly, the sample calls the <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> method to merge the new, minimal, <xref:System.Printing.PrintTicket> with the user's default <xref:System.Printing.PrintTicket>.</span></span> <span data-ttu-id="85393-125">その結果、プロパティの 1 つとして新しい <xref:System.Printing.PrintTicket> を含む <xref:System.Printing.ValidationResult> が返されます。</span><span class="sxs-lookup"><span data-stu-id="85393-125">This returns a <xref:System.Printing.ValidationResult> that includes the new <xref:System.Printing.PrintTicket> as one of its properties.</span></span>  
  
5. <span data-ttu-id="85393-126">次に、このサンプルでは、新しい <xref:System.Printing.PrintTicket> で両面印刷が要求されることをテストします。</span><span class="sxs-lookup"><span data-stu-id="85393-126">The sample then tests that the new <xref:System.Printing.PrintTicket> requests duplexing.</span></span> <span data-ttu-id="85393-127">行われる場合、サンプルでは、それがユーザーの新しい既定の印刷チケットになります。</span><span class="sxs-lookup"><span data-stu-id="85393-127">If it does, then the sample makes it the new default print ticket for the user.</span></span> <span data-ttu-id="85393-128">上記の手順 2 が省略され、プリンターが長辺に沿った両面印刷をサポートしていない場合、テストの結果は `false` になります</span><span class="sxs-lookup"><span data-stu-id="85393-128">If step 2 above had been left out and the printer did not support duplexing along the long side, then the test would have resulted in `false`.</span></span> <span data-ttu-id="85393-129">(上記の注を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="85393-129">(See the note above.)</span></span>  
  
6. <span data-ttu-id="85393-130">最後の重要な手順は、<xref:System.Printing.PrintQueue> の <xref:System.Printing.PrintQueue.UserPrintTicket%2A> プロパティへの変更を <xref:System.Printing.PrintQueue.Commit%2A> メソッドを使用してコミットすることです。</span><span class="sxs-lookup"><span data-stu-id="85393-130">The last significant step is to commit the change to the <xref:System.Printing.PrintQueue.UserPrintTicket%2A> property of the <xref:System.Printing.PrintQueue> with the <xref:System.Printing.PrintQueue.Commit%2A> method.</span></span>  
  
 [!code-csharp[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#usingmergeandvalidate)]
 [!code-vb[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#usingmergeandvalidate)]  
  
 <span data-ttu-id="85393-131">この例をすぐにテストできるように、残りの部分を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="85393-131">So that you can quickly test this example, the remainder of it is presented below.</span></span> <span data-ttu-id="85393-132">プロジェクトと名前空間を作成してから、この記事の両方のコード スニペットを名前空間ブロックに貼り付けてください。</span><span class="sxs-lookup"><span data-stu-id="85393-132">Create a project and a namespace and then paste both the code snippets in this article into the namespace block.</span></span>  
  
 [!code-csharp[PrintTicketManagment#UIForMergeAndValidatePTUtility](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#uiformergeandvalidateptutility)]
 [!code-vb[PrintTicketManagment#UIForMergeAndValidatePTUtility](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#uiformergeandvalidateptutility)]  
  
## <a name="see-also"></a><span data-ttu-id="85393-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="85393-133">See also</span></span>

- <xref:System.Printing.PrintCapabilities>
- <xref:System.Printing.PrintTicket>
- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [<span data-ttu-id="85393-134">WPF のドキュメント</span><span class="sxs-lookup"><span data-stu-id="85393-134">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="85393-135">印刷の概要</span><span class="sxs-lookup"><span data-stu-id="85393-135">Printing Overview</span></span>](printing-overview.md)
- [<span data-ttu-id="85393-136">印刷スキーマ</span><span class="sxs-lookup"><span data-stu-id="85393-136">Print Schema</span></span>](/windows/win32/printdocs/printschema)
