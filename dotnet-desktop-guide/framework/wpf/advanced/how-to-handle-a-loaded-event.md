---
title: '方法 : 読み込まれたイベントを処理する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XAML [WPF], Loaded events
- events [WPF], Loaded
- Loaded events [WPF]
ms.assetid: 0cf8d003-8441-4df4-807a-6db09347e829
ms.openlocfilehash: 7ca95e195792f8fb4789c481e84dda51f2910434
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982091"
---
# <a name="how-to-handle-a-loaded-event"></a><span data-ttu-id="b0fa9-102">方法 : 読み込まれたイベントを処理する</span><span class="sxs-lookup"><span data-stu-id="b0fa9-102">How to: Handle a Loaded Event</span></span>
<span data-ttu-id="b0fa9-103">この例では、イベントを処理する方法 <xref:System.Windows.FrameworkElement.Loaded?displayProperty=nameWithType> と、そのイベントを処理するための適切なシナリオを示します。</span><span class="sxs-lookup"><span data-stu-id="b0fa9-103">This example shows how to handle the <xref:System.Windows.FrameworkElement.Loaded?displayProperty=nameWithType> event, and an appropriate scenario for handling that event.</span></span> <span data-ttu-id="b0fa9-104">ハンドラーは、 <xref:System.Windows.Controls.Button> ページが読み込まれるときにを作成します。</span><span class="sxs-lookup"><span data-stu-id="b0fa9-104">The handler  creates a <xref:System.Windows.Controls.Button> when the page loads.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0fa9-105">例</span><span class="sxs-lookup"><span data-stu-id="b0fa9-105">Example</span></span>  
 <span data-ttu-id="b0fa9-106">次の例では、 [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 分離コードファイルと共にを使用します。</span><span class="sxs-lookup"><span data-stu-id="b0fa9-106">The following example uses [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] together with a code-behind file.</span></span>  
  
 [!code-xaml[FELoaded#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[FELoaded#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml.cs#handler)]
 [!code-vb[FELoaded#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FELoaded/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a><span data-ttu-id="b0fa9-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="b0fa9-107">See also</span></span>

- <xref:System.Windows.FrameworkElement>
- [<span data-ttu-id="b0fa9-108">オブジェクトの有効期間イベント</span><span class="sxs-lookup"><span data-stu-id="b0fa9-108">Object Lifetime Events</span></span>](object-lifetime-events.md)
- [<span data-ttu-id="b0fa9-109">ルーティング イベントの概要</span><span class="sxs-lookup"><span data-stu-id="b0fa9-109">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="b0fa9-110">方法トピック</span><span class="sxs-lookup"><span data-stu-id="b0fa9-110">How-to Topics</span></span>](base-elements-how-to-topics.md)
