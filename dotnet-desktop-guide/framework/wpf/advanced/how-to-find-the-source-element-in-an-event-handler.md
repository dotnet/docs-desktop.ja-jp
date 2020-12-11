---
title: '方法: イベント ハンドラーでソース要素を検索する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- source element in event handlers [WPF]
- event handlers [WPF], finding source element in
ms.assetid: 85f71c5a-b714-4c65-9711-7d905c2bbe98
ms.openlocfilehash: 9a49878c9ad8313903df4506796998fd43e2e749
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984667"
---
# <a name="how-to-find-the-source-element-in-an-event-handler"></a><span data-ttu-id="1fb08-102">方法: イベント ハンドラーでソース要素を検索する</span><span class="sxs-lookup"><span data-stu-id="1fb08-102">How to: Find the Source Element in an Event Handler</span></span>
<span data-ttu-id="1fb08-103">この例からは、イベント ハンドラーでソース要素を検索する方法がわかります。</span><span class="sxs-lookup"><span data-stu-id="1fb08-103">This example shows how to find the source element in an event handler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1fb08-104">例</span><span class="sxs-lookup"><span data-stu-id="1fb08-104">Example</span></span>  
 <span data-ttu-id="1fb08-105">次の例では、分離コード ファイルで宣言されている <xref:System.Windows.Controls.Primitives.ButtonBase.Click> イベント ハンドラーを示します。</span><span class="sxs-lookup"><span data-stu-id="1fb08-105">The following example shows a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler that is declared in a code-behind file.</span></span> <span data-ttu-id="1fb08-106">ハンドラーが添付されているボタンをユーザーがクリックすると、ハンドラーのプロパティ値が変わります。</span><span class="sxs-lookup"><span data-stu-id="1fb08-106">When a user clicks the button that the handler is attached to, the handler changes a property value.</span></span> <span data-ttu-id="1fb08-107">ハンドラー コードでは、イベント引数で報告されるルーティング イベントの <xref:System.Windows.RoutedEventArgs.Source%2A> プロパティを使用し、<xref:System.Windows.RoutedEventArgs.Source%2A> 要素の <xref:System.Windows.FrameworkElement.Width%2A> プロパティ値を変更します。</span><span class="sxs-lookup"><span data-stu-id="1fb08-107">The handler code uses the <xref:System.Windows.RoutedEventArgs.Source%2A> property of the routed event data that is reported in the event arguments to change the <xref:System.Windows.FrameworkElement.Width%2A> property value on the <xref:System.Windows.RoutedEventArgs.Source%2A> element.</span></span>  
  
 [!code-xaml[RoutedEventSource#XAMLHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml#xamlhandler)]  
  
 [!code-csharp[RoutedEventSource#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventSource#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventSource/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a><span data-ttu-id="1fb08-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="1fb08-108">See also</span></span>

- <xref:System.Windows.RoutedEventArgs>
- [<span data-ttu-id="1fb08-109">ルーティング イベントの概要</span><span class="sxs-lookup"><span data-stu-id="1fb08-109">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="1fb08-110">方法トピック</span><span class="sxs-lookup"><span data-stu-id="1fb08-110">How-to Topics</span></span>](events-how-to-topics.md)
