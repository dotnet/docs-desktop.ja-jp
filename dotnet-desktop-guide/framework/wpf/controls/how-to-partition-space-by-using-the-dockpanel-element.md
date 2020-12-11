---
title: '方法: DockPanel 要素を使用して領域を分割する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [WPF], DockPanel
- DockPanel control [WPF], partitioning space
- partitioning space [WPF]
ms.assetid: a219b9e5-b205-4438-89b5-0a137ac463ab
ms.openlocfilehash: 3682acc559e4e8740b97f781b6f927eac1e380d7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985839"
---
# <a name="how-to-partition-space-by-using-the-dockpanel-element"></a><span data-ttu-id="05774-102">方法: DockPanel 要素を使用して領域を分割する</span><span class="sxs-lookup"><span data-stu-id="05774-102">How to: Partition Space by Using the DockPanel Element</span></span>
<span data-ttu-id="05774-103">次の例では、<xref:System.Windows.Controls.DockPanel> 要素を使用して、単純なユーザー インターフェイス (UI)[!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] フレームワークを作成します。</span><span class="sxs-lookup"><span data-stu-id="05774-103">The following example creates a simple [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] framework using a <xref:System.Windows.Controls.DockPanel> element.</span></span> <span data-ttu-id="05774-104"><xref:System.Windows.Controls.DockPanel> は、子要素に使用可能な領域を分割します。</span><span class="sxs-lookup"><span data-stu-id="05774-104">The <xref:System.Windows.Controls.DockPanel> partitions available space to its child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="05774-105">例</span><span class="sxs-lookup"><span data-stu-id="05774-105">Example</span></span>  
 <span data-ttu-id="05774-106">この例では、添付プロパティである <xref:System.Windows.Controls.DockPanel.Dock%2A> プロパティを使用して、分割された領域の <xref:System.Windows.Controls.Dock.Top> に、2 つの同一の <xref:System.Windows.Controls.Border> 要素をドッキングします。</span><span class="sxs-lookup"><span data-stu-id="05774-106">This example uses the <xref:System.Windows.Controls.DockPanel.Dock%2A> property, which is an attached property, to dock two identical <xref:System.Windows.Controls.Border> elements at the <xref:System.Windows.Controls.Dock.Top> of the partitioned space.</span></span> <span data-ttu-id="05774-107">3 番目の <xref:System.Windows.Controls.Border> 要素は、<xref:System.Windows.Controls.Dock.Left> にドッキングされ、幅は 200 ピクセルに設定されます。</span><span class="sxs-lookup"><span data-stu-id="05774-107">A third <xref:System.Windows.Controls.Border> element is docked to the <xref:System.Windows.Controls.Dock.Left>, with its width set to 200 pixels.</span></span> <span data-ttu-id="05774-108">4 番目の <xref:System.Windows.Controls.Border> は、画面の <xref:System.Windows.Controls.Dock.Bottom> にドッキングされます。</span><span class="sxs-lookup"><span data-stu-id="05774-108">A fourth <xref:System.Windows.Controls.Border> is docked to the <xref:System.Windows.Controls.Dock.Bottom> of the screen.</span></span> <span data-ttu-id="05774-109">最後の <xref:System.Windows.Controls.Border> 要素は、残りの領域を自動的に塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="05774-109">The last <xref:System.Windows.Controls.Border> element automatically fills the remaining space.</span></span>  
  
 [!code-cpp[DockPanelOvwSample#1](~/samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
> [!NOTE]
> <span data-ttu-id="05774-110">既定では、<xref:System.Windows.Controls.DockPanel> 要素の最後の子が、残りの未割り当て領域を塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="05774-110">By default, the last child of a <xref:System.Windows.Controls.DockPanel> element fills the remaining unallocated space.</span></span> <span data-ttu-id="05774-111">この動作にしない場合は、`LastChildFill="False"`を設定します。</span><span class="sxs-lookup"><span data-stu-id="05774-111">If you do not want this behavior, set `LastChildFill="False"`.</span></span>  
  
 <span data-ttu-id="05774-112">コンパイル済みのアプリケーションでは、次のような新しい UI を生成します。</span><span class="sxs-lookup"><span data-stu-id="05774-112">The compiled application yields a new UI that looks like this.</span></span>  
  
 <span data-ttu-id="05774-113">![一般的な DockPanel のシナリオ。](./media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")</span><span class="sxs-lookup"><span data-stu-id="05774-113">![A typical DockPanel scenario.](./media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05774-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="05774-114">See also</span></span>

- <xref:System.Windows.Controls.DockPanel>
- [<span data-ttu-id="05774-115">パネルの概要</span><span class="sxs-lookup"><span data-stu-id="05774-115">Panels Overview</span></span>](panels-overview.md)
