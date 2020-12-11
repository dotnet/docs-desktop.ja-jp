---
title: '方法: 印刷キューのサブセットを列挙する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- enumerating [WPF], subset of print queues
- print queues [WPF], enumerating subset of
ms.assetid: cc4a1b5b-d46f-4c5e-bc26-22c226e4bee0
ms.openlocfilehash: aae41931f012f6d34fc057fdd6ee9fc9baab6e7b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984604"
---
# <a name="how-to-enumerate-a-subset-of-print-queues"></a><span data-ttu-id="d17a2-102">方法: 印刷キューのサブセットを列挙する</span><span class="sxs-lookup"><span data-stu-id="d17a2-102">How to: Enumerate a Subset of Print Queues</span></span>
<span data-ttu-id="d17a2-103">企業全体にわたるプリンター セットを管理する情報技術 (IT) プロフェッショナルが直面する一般的な状況は、特定の特性を持つプリンターの一覧を生成することです。</span><span class="sxs-lookup"><span data-stu-id="d17a2-103">A common situation faced by information technology (IT) professionals managing a company-wide set of printers is to generate a list of printers having certain characteristics.</span></span> <span data-ttu-id="d17a2-104">この機能は、<xref:System.Printing.PrintServer> オブジェクトの <xref:System.Printing.PrintServer.GetPrintQueues%2A> メソッドと <xref:System.Printing.EnumeratedPrintQueueTypes> 列挙体によって提供されています。</span><span class="sxs-lookup"><span data-stu-id="d17a2-104">This functionality is provided by the <xref:System.Printing.PrintServer.GetPrintQueues%2A> method of a <xref:System.Printing.PrintServer> object and the <xref:System.Printing.EnumeratedPrintQueueTypes> enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d17a2-105">例</span><span class="sxs-lookup"><span data-stu-id="d17a2-105">Example</span></span>  
 <span data-ttu-id="d17a2-106">次の例では、一覧表示する印刷キューの特性を指定するフラグの配列を作成することからコードが始まります。</span><span class="sxs-lookup"><span data-stu-id="d17a2-106">In the example below, the code begins by creating an array of flags that specify the characteristics of the print queues we want to list.</span></span> <span data-ttu-id="d17a2-107">この例では、プリント サーバーのローカルにインストールされ、共有されている印刷キューを探しています。</span><span class="sxs-lookup"><span data-stu-id="d17a2-107">In this example, we are looking for print queues that are installed locally on the print server and are shared.</span></span> <span data-ttu-id="d17a2-108"><xref:System.Printing.EnumeratedPrintQueueTypes> 列挙体には、他にも多くの可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d17a2-108">The <xref:System.Printing.EnumeratedPrintQueueTypes> enumeration provides many other possibilities.</span></span>  
  
 <span data-ttu-id="d17a2-109">このコードでは、次に、<xref:System.Printing.PrintServer> から派生したクラスである <xref:System.Printing.LocalPrintServer> オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d17a2-109">The code then creates a <xref:System.Printing.LocalPrintServer> object, a class derived from <xref:System.Printing.PrintServer>.</span></span> <span data-ttu-id="d17a2-110">ローカル プリント サーバーは、アプリケーションが実行されているコンピューターです。</span><span class="sxs-lookup"><span data-stu-id="d17a2-110">The local print server is the computer on which the application is running.</span></span>  
  
 <span data-ttu-id="d17a2-111">最後の重要な手順は、配列を <xref:System.Printing.PrintServer.GetPrintQueues%2A> メソッドに渡すことです。</span><span class="sxs-lookup"><span data-stu-id="d17a2-111">The last significant step is to pass the array to the <xref:System.Printing.PrintServer.GetPrintQueues%2A> method.</span></span>  
  
 <span data-ttu-id="d17a2-112">最後に、結果がユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d17a2-112">Finally, the results are presented to the user.</span></span>  
  
 [!code-cpp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/cpp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CPP/Program.cpp#listsubsetofprintqueues)]
 [!code-csharp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/csharp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CSharp/Program.cs#listsubsetofprintqueues)]
 [!code-vb[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/visualbasic/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/visualbasic/program.vb#listsubsetofprintqueues)]  
  
 <span data-ttu-id="d17a2-113">各印刷キューをステップ実行する `foreach` ループで、さらにスクリーニングを行うようにこの例を拡張することができます。</span><span class="sxs-lookup"><span data-stu-id="d17a2-113">You could extend this example by having the `foreach` loop that steps through each print queue do further screening.</span></span> <span data-ttu-id="d17a2-114">たとえば、ループで各印刷キューの <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> メソッドを呼び出して、両面印刷がサポートされていないプリンターを除外し、両面印刷の有無について返された値をテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="d17a2-114">For example, you could screen out printers that do not support two-sided printing by having the loop call each print queue's <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> method and test the returned value for the presence of duplexing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d17a2-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="d17a2-115">See also</span></span>

- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [<span data-ttu-id="d17a2-116">WPF のドキュメント</span><span class="sxs-lookup"><span data-stu-id="d17a2-116">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="d17a2-117">印刷の概要</span><span class="sxs-lookup"><span data-stu-id="d17a2-117">Printing Overview</span></span>](printing-overview.md)
- [<span data-ttu-id="d17a2-118">Microsoft XPS Document Writer</span><span class="sxs-lookup"><span data-stu-id="d17a2-118">Microsoft XPS Document Writer</span></span>](/windows/win32/printdocs/microsoft-xps-document-writer)
