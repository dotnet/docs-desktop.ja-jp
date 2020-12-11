---
title: '方法: ページからウィンドウのタイトルを設定する'
ms.date: 03/30/2017
helpviewer_keywords:
- windows [WPF], setting title from a page
- title of window [WPF], setting from a page
- pages [WPF], setting window title from
ms.assetid: fecf0d19-3eb6-4f8c-a44f-ff1b6f2b34b3
ms.openlocfilehash: 0f618af89965822b0df96a264997dabd9cae7608
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974332"
---
# <a name="how-to-set-the-title-of-a-window-from-a-page"></a><span data-ttu-id="5b1ef-102">方法: ページからウィンドウのタイトルを設定する</span><span class="sxs-lookup"><span data-stu-id="5b1ef-102">How to: Set the Title of a Window from a Page</span></span>
<span data-ttu-id="5b1ef-103">この例では、<xref:System.Windows.Controls.Page> がホストされているウィンドウのタイトルを設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5b1ef-103">This example shows how to set the title of the window in which a <xref:System.Windows.Controls.Page> is hosted.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b1ef-104">例</span><span class="sxs-lookup"><span data-stu-id="5b1ef-104">Example</span></span>  
 <span data-ttu-id="5b1ef-105">ページでは、次のように <xref:System.Windows.Controls.Page.WindowTitle%2A> プロパティを設定することにより、そのページをホストしているウィンドウのタイトルを変更できます。</span><span class="sxs-lookup"><span data-stu-id="5b1ef-105">A page can change the title of the window that is hosting it by setting the <xref:System.Windows.Controls.Page.WindowTitle%2A> property, like so:</span></span>  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowTitleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowTitlePage.xaml#setpagewindowtitlexaml)]  
  
> [!NOTE]
> <span data-ttu-id="5b1ef-106">ページの <xref:System.Windows.Controls.Page.Title%2A> プロパティを設定しても、ウィンドウのタイトルの値は変更されません。</span><span class="sxs-lookup"><span data-stu-id="5b1ef-106">Setting the <xref:System.Windows.Controls.Page.Title%2A> property of a page does not change the value of the window title.</span></span> <span data-ttu-id="5b1ef-107"><xref:System.Windows.Controls.Page.Title%2A> で指定されているのは、ナビゲーション履歴でのページ エントリの名前です。</span><span class="sxs-lookup"><span data-stu-id="5b1ef-107">Instead, <xref:System.Windows.Controls.Page.Title%2A> specifies the name of a page entry in navigation history.</span></span>
