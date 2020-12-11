---
title: '方法: ページの読み込みを停止する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pages [WPF], stopping from loading
- methods [WPF], Stoploading
- events [WPF], NavigationStopped
- NavigationStopped properties [WPF]
- stopping pages from loading [WPF]
- loading [WPF], stopping
ms.assetid: e2b695b0-517e-462c-8ccf-90cc8d6ba864
ms.openlocfilehash: c5694bb2cb6c618cd84bad3dc893ae3855e44892
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974328"
---
# <a name="how-to-stop-a-page-from-loading"></a><span data-ttu-id="737df-102">方法: ページの読み込みを停止する</span><span class="sxs-lookup"><span data-stu-id="737df-102">How to: Stop a Page from Loading</span></span>
<span data-ttu-id="737df-103">この例では、<xref:System.Windows.Navigation.NavigationWindow.StopLoading%2A> メソッドを呼び出して、ダウンロードが完了する前にコンテンツへのナビゲーションを停止する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="737df-103">This example shows how to call the <xref:System.Windows.Navigation.NavigationWindow.StopLoading%2A> method to stop navigation to content before it has finished being downloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="737df-104">例</span><span class="sxs-lookup"><span data-stu-id="737df-104">Example</span></span>  
 <span data-ttu-id="737df-105"><xref:System.Windows.Navigation.NavigationWindow.StopLoading%2A> では要求されたコンテンツのダウンロードが停止されて、それにより <xref:System.Windows.Navigation.NavigationWindow.NavigationStopped> イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="737df-105"><xref:System.Windows.Navigation.NavigationWindow.StopLoading%2A> stops the download of the requested content, and causes the <xref:System.Windows.Navigation.NavigationWindow.NavigationStopped> event to be raised.</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateStopLoadingCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/MainWindow.xaml.cs#navigatestoploadingcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateStopLoadingCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/mainwindow.xaml.vb#navigatestoploadingcode)]
