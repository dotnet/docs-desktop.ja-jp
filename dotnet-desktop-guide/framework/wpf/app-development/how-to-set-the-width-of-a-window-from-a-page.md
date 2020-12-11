---
title: '方法: ページからウィンドウの幅を設定する'
ms.date: 03/30/2017
helpviewer_keywords:
- width of windows [WPF], setting from a page
- windows [WPF], setting width from a page
- pages [WPF], setting window width from
ms.assetid: 31601c92-7889-472a-b07e-bf675ad21c92
ms.openlocfilehash: 1e16b75ecb85550facdf24a5b9e341cf0c061178
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974331"
---
# <a name="how-to-set-the-width-of-a-window-from-a-page"></a><span data-ttu-id="47831-102">方法: ページからウィンドウの幅を設定する</span><span class="sxs-lookup"><span data-stu-id="47831-102">How to: Set the Width of a Window from a Page</span></span>
<span data-ttu-id="47831-103">この例では、<xref:System.Windows.Controls.Page> からウィンドウの幅を設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="47831-103">This example illustrates how to set the width of the window from a <xref:System.Windows.Controls.Page>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="47831-104">例</span><span class="sxs-lookup"><span data-stu-id="47831-104">Example</span></span>  
 <span data-ttu-id="47831-105"><xref:System.Windows.Controls.Page> では、<xref:System.Windows.Controls.Page.WindowWidth%2A> を設定することによって、そのホスト ウィンドウの幅を設定できます。</span><span class="sxs-lookup"><span data-stu-id="47831-105">A <xref:System.Windows.Controls.Page> can set the width of its host window by setting <xref:System.Windows.Controls.Page.WindowWidth%2A>.</span></span> <span data-ttu-id="47831-106">このプロパティを使用すると、<xref:System.Windows.Controls.Page> では、それをホストするウィンドウの種類を明示的に知っていなくてもかまいません。</span><span class="sxs-lookup"><span data-stu-id="47831-106">This property allows the <xref:System.Windows.Controls.Page> to not have explicit knowledge of the type of window that hosts it.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="47831-107"><xref:System.Windows.Controls.Page.WindowWidth%2A> を使用してウィンドウの幅を設定するには、<xref:System.Windows.Controls.Page> がウィンドウの子である必要があります。</span><span class="sxs-lookup"><span data-stu-id="47831-107">To set the width of a window using <xref:System.Windows.Controls.Page.WindowWidth%2A>, a <xref:System.Windows.Controls.Page> must be the child of a window.</span></span>  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowWidthXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowWidthPage.xaml#setpagewindowwidthxaml)]
