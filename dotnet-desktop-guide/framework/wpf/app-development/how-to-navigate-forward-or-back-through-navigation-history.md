---
title: '方法: 移動履歴の前後への移動'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- history [WPF], navigating forward
- navigation [WPF], through navigation history (forward)
ms.assetid: 5939d574-5f53-469e-85f5-1f2b13607caa
ms.openlocfilehash: 76a78debdce14123cc465ac9abf4db906fe0a2df
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984299"
---
# <a name="how-to-navigate-forward-or-back-through-navigation-history"></a><span data-ttu-id="51770-102">方法: 移動履歴の前後への移動</span><span class="sxs-lookup"><span data-stu-id="51770-102">How to: Navigate Forward or Back Through Navigation History</span></span>
<span data-ttu-id="51770-103">この例では、ナビゲーション履歴内のエントリ間を前方または後方に移動する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="51770-103">This example illustrates how to navigate forward or back to entries in navigation history.</span></span>  
  
## <a name="example"></a><span data-ttu-id="51770-104">例</span><span class="sxs-lookup"><span data-stu-id="51770-104">Example</span></span>  
 <span data-ttu-id="51770-105">次のホストのコンテンツから実行されたコードでは、ナビゲーション履歴内を、一度に 1 エントリずつ、前方または後方に移動できます。</span><span class="sxs-lookup"><span data-stu-id="51770-105">Code that runs from content in the following hosts can navigate forward or back through navigation history, one entry at a time.</span></span>  
  
- <span data-ttu-id="51770-106"><xref:System.Windows.Navigation.NavigationService> を使用する <xref:System.Windows.Navigation.NavigationWindow></span><span class="sxs-lookup"><span data-stu-id="51770-106"><xref:System.Windows.Navigation.NavigationWindow> using <xref:System.Windows.Navigation.NavigationService></span></span>  
  
- <span data-ttu-id="51770-107"><xref:System.Windows.Navigation.NavigationService> を使用する <xref:System.Windows.Controls.Frame></span><span class="sxs-lookup"><span data-stu-id="51770-107"><xref:System.Windows.Controls.Frame> using <xref:System.Windows.Navigation.NavigationService></span></span>  
  
- <span data-ttu-id="51770-108">Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="51770-108">Internet Explorer</span></span>  
  
 <span data-ttu-id="51770-109">1 つ前方のエントリに移動するには、その前にまず、**CanGoForward** プロパティを調べて、ナビゲーション履歴で前方にエントリがあることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51770-109">Before you can navigate forward one entry, you must first check that there are entries in forward navigation history by inspecting the **CanGoForward** property.</span></span> <span data-ttu-id="51770-110">1 つ前方のエントリに移動するには、**GoForward** メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="51770-110">To navigate forward one entry, you call the **GoForward** method.</span></span> <span data-ttu-id="51770-111">これを次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="51770-111">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigateforwardcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigateforwardcode)]  
  
 <span data-ttu-id="51770-112">1 つ後方のエントリに移動するには、その前にまず、**CanGoBack** プロパティを調べて、ナビゲーション履歴で後方にエントリがあることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51770-112">Before you can navigate back one entry, you must first check that there are entries in back navigation history by inspecting the **CanGoBack** property.</span></span> <span data-ttu-id="51770-113">1 つ後方のエントリに移動するには、**GoBack** メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="51770-113">To navigate back one entry, you call the **GoBack** method.</span></span> <span data-ttu-id="51770-114">これを次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="51770-114">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 <span data-ttu-id="51770-115">**CanGoForward**、**GoForward**、**CanGoBack**、**GoBack** は、<xref:System.Windows.Navigation.NavigationWindow>、<xref:System.Windows.Controls.Frame>、<xref:System.Windows.Navigation.NavigationService> によって実装されています。</span><span class="sxs-lookup"><span data-stu-id="51770-115">**CanGoForward**, **GoForward**, **CanGoBack**, and **GoBack** are implemented by <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, and <xref:System.Windows.Navigation.NavigationService>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="51770-116">**GoForward** を呼び出して、ナビゲーション履歴の前方にエントリがない場合、または **GoBack** を呼び出して、ナビゲーション履歴の後方にエントリがない場合は、<xref:System.InvalidOperationException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="51770-116">If you call **GoForward**, and there are no entries in forward navigation history, or if you call **GoBack**, and there are no entries in back navigation history, an <xref:System.InvalidOperationException> is thrown.</span></span>
