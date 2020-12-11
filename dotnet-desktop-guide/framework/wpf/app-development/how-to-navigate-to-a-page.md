---
title: '方法: ページに移動する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pages [WPF], navigating to
- navigation [WPF], to page
ms.assetid: 2a556fc0-748b-417f-a58a-0d05a7afb66f
ms.openlocfilehash: 25a0dbbc609c7b6f8f2878d2068e61e492a59c7e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985852"
---
# <a name="how-to-navigate-to-a-page"></a><span data-ttu-id="36979-102">方法: ページに移動する</span><span class="sxs-lookup"><span data-stu-id="36979-102">How to: Navigate to a Page</span></span>
<span data-ttu-id="36979-103">この例では、<xref:System.Windows.Navigation.NavigationWindow> からページに移動するいくつかの方法を示します。</span><span class="sxs-lookup"><span data-stu-id="36979-103">This example illustrates several ways in which a page can be navigated to from a <xref:System.Windows.Navigation.NavigationWindow>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36979-104">例</span><span class="sxs-lookup"><span data-stu-id="36979-104">Example</span></span>  
 <span data-ttu-id="36979-105">次のいずれかを使用して、<xref:System.Windows.Navigation.NavigationWindow> からページに移動できます。</span><span class="sxs-lookup"><span data-stu-id="36979-105">It is possible for a <xref:System.Windows.Navigation.NavigationWindow> to navigate to a page using one of the following:</span></span>  
  
- <span data-ttu-id="36979-106"><xref:System.Windows.Navigation.NavigationWindow.Source%2A> プロパティ。</span><span class="sxs-lookup"><span data-stu-id="36979-106">The <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property.</span></span>  
  
- <span data-ttu-id="36979-107"><xref:System.Windows.Navigation.NavigationWindow.Navigate%2A> メソッド。</span><span class="sxs-lookup"><span data-stu-id="36979-107">The <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A> method.</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateToPageCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/MainWindow.xaml.cs#navigatetopagecode)]
 [!code-vb[HOWTONavigationSnippets#NavigateToPageCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/mainwindow.xaml.vb#navigatetopagecode)]  
  
> [!NOTE]
> <span data-ttu-id="36979-108">Uniform Resource Identifier (URI) は、相対または絶対で指定できます。</span><span class="sxs-lookup"><span data-stu-id="36979-108">Uniform resource identifiers (URIs) can be either relative or absolute.</span></span> <span data-ttu-id="36979-109">詳細については、「[WPF におけるパック URI](pack-uris-in-wpf.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36979-109">For more information, see [Pack URIs in WPF](pack-uris-in-wpf.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36979-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="36979-110">See also</span></span>

- <xref:System.Windows.Controls.Frame>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Navigation.NavigationService>
