---
title: '方法: ページ関数を呼び出す'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- calling page functions [WPF]
- page functions [WPF], calling
- functions [WPF], calling
ms.assetid: a4808397-c6d5-406a-83e0-0091f0c15ae4
ms.openlocfilehash: 0370fe0bcbdf5105ae1b65bb90346663b2786a63
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983771"
---
# <a name="how-to-call-a-page-function"></a><span data-ttu-id="8f659-102">方法: ページ関数を呼び出す</span><span class="sxs-lookup"><span data-stu-id="8f659-102">How to: Call a Page Function</span></span>
<span data-ttu-id="8f659-103">この例では、[!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] ページからページ関数を呼び出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8f659-103">This example shows how to call a page function from a [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] page.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f659-104">例</span><span class="sxs-lookup"><span data-stu-id="8f659-104">Example</span></span>  
 <span data-ttu-id="8f659-105">ページに移動するときと同様、Uniform Resource Identifier (URI) を使用してページ関数に移動することができます。</span><span class="sxs-lookup"><span data-stu-id="8f659-105">You can navigate to a page function using a uniform resource identifier (URI), just as you can when you navigate to a page.</span></span> <span data-ttu-id="8f659-106">これを次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="8f659-106">This is shown in the following example.</span></span>  
  
 [!code-csharp[HOWTOPageFunctionSnippets#NavigateToAPageFunctionLikeAPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml.cs#navigatetoapagefunctionlikeapagecodebehind)]
 [!code-vb[HOWTOPageFunctionSnippets#NavigateToAPageFunctionLikeAPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/VisualBasic/CallingPage.xaml.vb#navigatetoapagefunctionlikeapagecodebehind)]  
  
 <span data-ttu-id="8f659-107">ページ関数にデータを渡す必要がある場合は、インスタンスを作成し、プロパティを設定することによってデータを渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="8f659-107">If you need to pass data to the page function, you can create an instance of it and pass the data by setting a property.</span></span> <span data-ttu-id="8f659-108">または、次の例に示すように、パラメーターなしのコンストラクターを使用してデータを渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="8f659-108">Or, as the following example shows, you can pass the data using a non-parameterless constructor.</span></span>  
  
 [!code-xaml[HOWTOPageFunctionSnippets#CallAPageFunctionXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml#callapagefunctionxaml)]  
  
 [!code-csharp[HOWTOPageFunctionSnippets#CallAPageFunctionCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml.cs#callapagefunctioncodebehind)]
 [!code-vb[HOWTOPageFunctionSnippets#CallAPageFunctionCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/VisualBasic/CallingPage.xaml.vb#callapagefunctioncodebehind)]  
  
## <a name="see-also"></a><span data-ttu-id="8f659-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="8f659-109">See also</span></span>

- <xref:System.Windows.Navigation.PageFunction%601>
