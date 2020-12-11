---
title: '方法: ポップアップのカスタム位置を指定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Popup control [WPF], specifying custom position
ms.assetid: 28c24f39-d3aa-4ee2-b950-384b4a5dab92
ms.openlocfilehash: b48dedc044b418062642af5c5bb40afab78a3c97
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984571"
---
# <a name="how-to-specify-a-custom-popup-position"></a><span data-ttu-id="33071-102">方法: ポップアップのカスタム位置を指定する</span><span class="sxs-lookup"><span data-stu-id="33071-102">How to: Specify a Custom Popup Position</span></span>
<span data-ttu-id="33071-103">この例では、<xref:System.Windows.Controls.Primitives.Popup.Placement%2A> プロパティが <xref:System.Windows.Controls.Primitives.PlacementMode.Custom> に設定されているときに、<xref:System.Windows.Controls.Primitives.Popup> コントロールのカスタム位置を指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="33071-103">This example shows how to specify a custom position for a <xref:System.Windows.Controls.Primitives.Popup> control when the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property is set to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33071-104">例</span><span class="sxs-lookup"><span data-stu-id="33071-104">Example</span></span>  
 <span data-ttu-id="33071-105"><xref:System.Windows.Controls.Primitives.Popup.Placement%2A> プロパティが <xref:System.Windows.Controls.Primitives.PlacementMode.Custom> に設定されていると、<xref:System.Windows.Controls.Primitives.Popup> では定義されている <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> デリゲートのインスタンスが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="33071-105">When the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property is set to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>, the <xref:System.Windows.Controls.Primitives.Popup> calls a defined instance of the <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegate.</span></span> <span data-ttu-id="33071-106">このデリゲートでは、ターゲット領域の左上隅と <xref:System.Windows.Controls.Primitives.Popup> の左上隅を基準として、一連の可能なポイントが返されます。</span><span class="sxs-lookup"><span data-stu-id="33071-106">This delegate returns a set of possible points that are relative to the top-left corner of the target area and the top-left corner of the <xref:System.Windows.Controls.Primitives.Popup>.</span></span> <span data-ttu-id="33071-107"><xref:System.Windows.Controls.Primitives.Popup> は、視認性が最もよい場所に配置されます。</span><span class="sxs-lookup"><span data-stu-id="33071-107">The <xref:System.Windows.Controls.Primitives.Popup> placement occurs at the point that provides the best visibility.</span></span>  
  
 <span data-ttu-id="33071-108">次の例では、<xref:System.Windows.Controls.Primitives.Popup.Placement%2A> プロパティを <xref:System.Windows.Controls.Primitives.PlacementMode.Custom> に設定することで <xref:System.Windows.Controls.Primitives.Popup> の位置を定義する方法が示されています。</span><span class="sxs-lookup"><span data-stu-id="33071-108">The following example shows how to define the position of a <xref:System.Windows.Controls.Primitives.Popup> by setting the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span></span> <span data-ttu-id="33071-109">また、<xref:System.Windows.Controls.Primitives.Popup> を配置するために <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> デリゲートを作成して割り当てる方法も示されています。</span><span class="sxs-lookup"><span data-stu-id="33071-109">It also shows how to create and assign a <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegate in order to position the <xref:System.Windows.Controls.Primitives.Popup>.</span></span>  <span data-ttu-id="33071-110">コールバック デリゲートでは、2 つの <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> オブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="33071-110">The callback delegate returns two <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> objects.</span></span>  <span data-ttu-id="33071-111">最初の位置では <xref:System.Windows.Controls.Primitives.Popup> が画面の端で見えなくなる場合、<xref:System.Windows.Controls.Primitives.Popup> は 2 番目の位置に配置されます。</span><span class="sxs-lookup"><span data-stu-id="33071-111">If the <xref:System.Windows.Controls.Primitives.Popup> is hidden by a screen edge at the first position, the <xref:System.Windows.Controls.Primitives.Popup> is placed at the second position.</span></span>  
  
 [!code-xaml[PopupCustomPlacement#CustomPlacement](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml#customplacement)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateInstance](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegateinstance)]
 [!code-vb[PopupCustomPlacement#DelegateInstance](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegateinstance)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegatedefinition)]
 [!code-vb[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegatedefinition)]  
  
 <span data-ttu-id="33071-112">サンプル全体については、[ポップアップ配置のサンプル](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33071-112">For the complete sample, see [Popup Placement Sample](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33071-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="33071-113">See also</span></span>

- <xref:System.Windows.Controls.Primitives.Popup>
- [<span data-ttu-id="33071-114">ポップアップの概要</span><span class="sxs-lookup"><span data-stu-id="33071-114">Popup overview</span></span>](popup-overview.md)
- [<span data-ttu-id="33071-115">ハウツー記事</span><span class="sxs-lookup"><span data-stu-id="33071-115">How-to articles</span></span>](popup-how-to-topics.md)
