---
title: '方法: FlowDocument の列区切り属性を使用する'
ms.date: 03/30/2017
helpviewer_keywords:
- FlowDocument column-separating attributes
- column-separating attributes
- documents [WPF], FlowDocument column-separating attributes
ms.assetid: c7a822f8-aeca-45bd-a258-2852ff28005c
ms.openlocfilehash: 27491b21da587fa198061ba52d8daed5d3f28de3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985196"
---
# <a name="how-to-use-flowdocument-column-separating-attributes"></a><span data-ttu-id="5dc8b-102">方法: FlowDocument の列区切り属性を使用する</span><span class="sxs-lookup"><span data-stu-id="5dc8b-102">How to: Use FlowDocument Column-Separating Attributes</span></span>
<span data-ttu-id="5dc8b-103">この例では、<xref:System.Windows.Documents.FlowDocument> の列区切り機能を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5dc8b-103">This example shows how to use the column-separating features of a <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5dc8b-104">例</span><span class="sxs-lookup"><span data-stu-id="5dc8b-104">Example</span></span>  
 <span data-ttu-id="5dc8b-105">次の例では、<xref:System.Windows.Documents.FlowDocument> が定義され、<xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>、<xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>、<xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> という属性が設定されます。</span><span class="sxs-lookup"><span data-stu-id="5dc8b-105">The following example defines a <xref:System.Windows.Documents.FlowDocument>, and sets the <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, and <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> attributes.</span></span>  <span data-ttu-id="5dc8b-106"><xref:System.Windows.Documents.FlowDocument> には、サンプル コンテンツの段落が 1 つ含まれます。</span><span class="sxs-lookup"><span data-stu-id="5dc8b-106">The <xref:System.Windows.Documents.FlowDocument> contains a single paragraph of sample content.</span></span>  
  
 [!code-xaml[FlowDocumentSnippets#_FlowDocumentColumnStuffXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml#_flowdocumentcolumnstuffxaml)]  
  
 <span data-ttu-id="5dc8b-107">次の画像では、レンダリングされた <xref:System.Windows.Documents.FlowDocument> での属性 <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>、<xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>、<xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> の効果を示します。</span><span class="sxs-lookup"><span data-stu-id="5dc8b-107">The following figure shows the effects of the <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, and <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> attributes in a rendered <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 ![FlowDocument Intra Column 属性を示すスクリーンショット](./media/how-to-use-flowdocument-column-separating-attributes/flowdocument-intra-column.png)
