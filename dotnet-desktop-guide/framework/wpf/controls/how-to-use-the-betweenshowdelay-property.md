---
title: '方法: BetweenShowDelay プロパティを使用する'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolTip control [WPF], BetweenShowDelay time property
- BetweenShowDelay time property [WPF]
ms.assetid: 984ea76d-f2a2-4326-a02e-f97ec3d036d6
ms.openlocfilehash: 9b63675ec21294496117860aa5b58af132c4284a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982639"
---
# <a name="how-to-use-the-betweenshowdelay-property"></a><span data-ttu-id="e731c-102">方法: BetweenShowDelay プロパティを使用する</span><span class="sxs-lookup"><span data-stu-id="e731c-102">How to: Use the BetweenShowDelay Property</span></span>
<span data-ttu-id="e731c-103">この例では、<xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> の時間プロパティを使用して、ユーザーがマウス ポインターをあるツールヒントから別のツールヒントに直接移動したときにそのツールヒントをすばやく (遅延なし、またはほとんどなく) 表示させる方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e731c-103">This example shows how to use the <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> time property so that tooltips appear quickly—with little or no delay—when a user moves the mouse pointer from one tooltip directly to another.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e731c-104">例</span><span class="sxs-lookup"><span data-stu-id="e731c-104">Example</span></span>  
 <span data-ttu-id="e731c-105">次の例では、<xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> プロパティが 1 秒 (1,000 ミリ秒) に設定され、<xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> は両方の <xref:System.Windows.Shapes.Ellipse> コントロールのツールヒントで 2 秒 (2,000 ミリ秒) に設定されています。</span><span class="sxs-lookup"><span data-stu-id="e731c-105">In the following example, the <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> property is set to one second (1000 milliseconds) and the <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> is set to two seconds (2000 milliseconds) for the tooltips of both <xref:System.Windows.Shapes.Ellipse> controls.</span></span> <span data-ttu-id="e731c-106">いずれかの省略記号のツールヒントを表示し、2 秒以内にマウス ポインターを別の省略記号に移動して一時停止すると、2 番目の省略記号のツールヒントがすぐに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e731c-106">If you display the tooltip for one of the ellipses and then move the mouse pointer to another ellipse within two seconds and pause on it, the tooltip of the second ellipse displays immediately.</span></span>  
  
 <span data-ttu-id="e731c-107">次のいずれのシナリオでも、<xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> が適用され、2 番目の省略記号のツールヒントが 1 秒間待機してから表示されます。</span><span class="sxs-lookup"><span data-stu-id="e731c-107">In either of the following scenarios, the <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> applies, which causes the tooltip for the second ellipse to wait one second before it appears:</span></span>  
  
- <span data-ttu-id="e731c-108">2 番目のボタンへの移動にかかる時間が 2 秒を超えている場合。</span><span class="sxs-lookup"><span data-stu-id="e731c-108">If the time it takes to move to the second button is more than two seconds.</span></span>  
  
- <span data-ttu-id="e731c-109">最初の省略記号の時間間隔の開始時にツールヒントが表示されない場合。</span><span class="sxs-lookup"><span data-stu-id="e731c-109">If the tooltip is not visible at the beginning of the time interval for the first ellipse.</span></span>  
  
 [!code-xaml[ToolTipService#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
[!code-xaml[ToolTipService#NoToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
## <a name="see-also"></a><span data-ttu-id="e731c-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="e731c-110">See also</span></span>

- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [<span data-ttu-id="e731c-111">方法トピック</span><span class="sxs-lookup"><span data-stu-id="e731c-111">How-to Topics</span></span>](tooltip-how-to-topics.md)
- [<span data-ttu-id="e731c-112">ToolTip の概要</span><span class="sxs-lookup"><span data-stu-id="e731c-112">ToolTip Overview</span></span>](tooltip-overview.md)
