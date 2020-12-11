---
title: '方法: プログラムでテキストに要素を挿入する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Text Animation sample [WPF]
- elements [WPF], inserting into text
- inserting elements into text [WPF]
- TextPointer objects [WPF]
- text [WPF], inserting elements
ms.assetid: 97bd950a-25ac-4e42-a311-94b6420d4136
ms.openlocfilehash: ea9850c8490ec37032d4565c6b3375e3116d4313
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984111"
---
# <a name="how-to-insert-an-element-into-text-programmatically"></a><span data-ttu-id="c51cd-102">方法: プログラムでテキストに要素を挿入する</span><span class="sxs-lookup"><span data-stu-id="c51cd-102">How to: Insert an Element Into Text Programmatically</span></span>
<span data-ttu-id="c51cd-103">次の例では、<xref:System.Windows.Documents.TextPointer> オブジェクトを 2 つ使用し、<xref:System.Windows.Documents.Span> 要素の適用対象とする範囲をテキスト内で指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c51cd-103">The following example shows how to use two <xref:System.Windows.Documents.TextPointer> objects to specify a range within text to apply a <xref:System.Windows.Documents.Span> element to.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c51cd-104">例</span><span class="sxs-lookup"><span data-stu-id="c51cd-104">Example</span></span>  
 [!code-csharp[FlowMiscSnippets_procedural_snip#InsertInlineIntoTextExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowMiscSnippets_procedural_snip/CSharp/InsertInlineIntoTextExample.cs#insertinlineintotextexamplewholepage)]
 [!code-vb[FlowMiscSnippets_procedural_snip#InsertInlineIntoTextExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowMiscSnippets_procedural_snip/VisualBasic/InsertInlineIntoTextExample.vb#insertinlineintotextexamplewholepage)]  
  
 <span data-ttu-id="c51cd-105">次の図は、この例の結果を示したものです。</span><span class="sxs-lookup"><span data-stu-id="c51cd-105">The illustration below shows what this example looks like.</span></span>  
  
 <span data-ttu-id="c51cd-106">![テキストの範囲に適用される Span 要素](./media/flow-insertelementintotextprogrammatically.png "Flow_InsertElementIntoTextProgrammatically")</span><span class="sxs-lookup"><span data-stu-id="c51cd-106">![A Span element applied to a range of text](./media/flow-insertelementintotextprogrammatically.png "Flow_InsertElementIntoTextProgrammatically")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c51cd-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="c51cd-107">See also</span></span>

- [<span data-ttu-id="c51cd-108">フロー ドキュメントの概要</span><span class="sxs-lookup"><span data-stu-id="c51cd-108">Flow Document Overview</span></span>](flow-document-overview.md)
