---
title: '方法: 段落間の間隔を調整する'
ms.date: 03/30/2017
helpviewer_keywords:
- spacing between paragraphs [WPF]
- paragraphs [WPF], spacing between
- documents [WPF], adjusting spacing between paragraphs
ms.assetid: 7cd2f2ac-0e19-4587-bfb6-7f5b18c9536e
ms.openlocfilehash: e2a6ba34e3ab15eb316671fef7c11bea03d53c73
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982652"
---
# <a name="how-to-adjust-spacing-between-paragraphs"></a><span data-ttu-id="2021e-102">方法: 段落間の間隔を調整する</span><span class="sxs-lookup"><span data-stu-id="2021e-102">How to: Adjust Spacing Between Paragraphs</span></span>
<span data-ttu-id="2021e-103">この例では、フロー コンテンツ内の段落間の間隔を調整または削除する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="2021e-103">This example shows how to adjust or eliminate spacing between paragraphs in flow content.</span></span>  
  
 <span data-ttu-id="2021e-104">フロー コンテンツでは、段落に設定した余白に応じて、段落間に余分なスペースが表示されます。つまり、それらの段落間の間隔を調整することで、段落間の間隔を制御できます。</span><span class="sxs-lookup"><span data-stu-id="2021e-104">In flow content, extra space that appears between paragraphs is the result of margins set on these paragraphs; thus, the spacing between paragraphs can be controlled by adjusting the margins on those paragraphs.</span></span>  <span data-ttu-id="2021e-105">2 つの段落間の余分なスペースを全体でなくすには、段落の余白を **0** に設定します。</span><span class="sxs-lookup"><span data-stu-id="2021e-105">To eliminate extra spacing between two paragraphs altogether, set the margins for the paragraphs to **0**.</span></span>  <span data-ttu-id="2021e-106"><xref:System.Windows.Documents.FlowDocument> 全体で段落間の間隔を同じにするには、スタイルを使用して、<xref:System.Windows.Documents.FlowDocument> 内のすべての段落に同じ余白値を設定します。</span><span class="sxs-lookup"><span data-stu-id="2021e-106">To achieve uniform spacing between paragraphs throughout an entire <xref:System.Windows.Documents.FlowDocument>, use styling to set a uniform margin value for all paragraphs in the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 <span data-ttu-id="2021e-107">2 つの隣接する段落の余白は、倍になるのではなく、2 つの余白の大きい方に "折りたたまれる" という点にご注意ください。</span><span class="sxs-lookup"><span data-stu-id="2021e-107">It is important to note that the margins for two adjacent paragraphs will "collapse" to the larger of the two margins, rather than doubling up.</span></span> <span data-ttu-id="2021e-108">つまり、2 つの隣接する段落の余白がそれぞれ 20 ピクセルと 40 ピクセルであった場合、段落間の間隔は 2 つの余白の大きい方の 40 ピクセルになります。</span><span class="sxs-lookup"><span data-stu-id="2021e-108">So, if two adjacent paragraphs have margins of 20 pixels and 40 pixels respectively, the resulting space between the paragraphs is 40 pixels, the larger of the two margin values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2021e-109">例</span><span class="sxs-lookup"><span data-stu-id="2021e-109">Example</span></span>  
 <span data-ttu-id="2021e-110">次の例では、スタイルを使用して、<xref:System.Windows.Documents.FlowDocument> 内のすべての <xref:System.Windows.Documents.Paragraph> 要素の余白を **0** に設定しています。これにより、<xref:System.Windows.Documents.FlowDocument> の段落間の余分な間隔は実質的になくなります。</span><span class="sxs-lookup"><span data-stu-id="2021e-110">The following example uses styling to set the margin for all <xref:System.Windows.Documents.Paragraph> elements in a <xref:System.Windows.Documents.FlowDocument> to **0**, which effectively eliminates extra spacing between paragraphs in the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-xaml[BlockSnippets#_ParagraphSpacingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/BlockSnippets/CSharp/Window1.xaml#_paragraphspacingxaml)]
