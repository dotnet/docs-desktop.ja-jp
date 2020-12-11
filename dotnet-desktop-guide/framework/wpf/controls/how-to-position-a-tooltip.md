---
title: '方法: ToolTip を配置する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolTip control [WPF], positioning
- positioning ToolTip controls [WPF]
ms.assetid: cddf3757-9e5f-4ce3-a6eb-44489cf3804a
ms.openlocfilehash: 851dc3c07e0abb4c7772f55f79900f1852b41232
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985836"
---
# <a name="how-to-position-a-tooltip"></a><span data-ttu-id="8c3b5-102">方法: ToolTip を配置する</span><span class="sxs-lookup"><span data-stu-id="8c3b5-102">How to: Position a ToolTip</span></span>
<span data-ttu-id="8c3b5-103">この例では、画面上のツールヒントの位置を指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8c3b5-103">This example shows how to specify the position of a tooltip on the screen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c3b5-104">例</span><span class="sxs-lookup"><span data-stu-id="8c3b5-104">Example</span></span>  
 <span data-ttu-id="8c3b5-105">ツールヒントを配置するには、<xref:System.Windows.Controls.ToolTip> クラスと <xref:System.Windows.Controls.ToolTipService> クラスの両方で定義されている 5 つのプロパティのセットを使用します。</span><span class="sxs-lookup"><span data-stu-id="8c3b5-105">You can position a tooltip by using a set of five properties that are defined in both the <xref:System.Windows.Controls.ToolTip> and <xref:System.Windows.Controls.ToolTipService> classes.</span></span> <span data-ttu-id="8c3b5-106">次の表では、これら 5 つのプロパティの 2 つのセットを示し、クラスに対応したリファレンス ドキュメントへのリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="8c3b5-106">The following table shows these two sets of five properties and provides links to their reference documentation according to class.</span></span>  
  
### <a name="corresponding-tooltip-properties-according-to-class"></a><span data-ttu-id="8c3b5-107">クラスに応じた対応するツールヒント プロパティ</span><span class="sxs-lookup"><span data-stu-id="8c3b5-107">Corresponding tooltip properties according to class</span></span>  
  
|<span data-ttu-id="8c3b5-108"><xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType> クラスのプロパティ</span><span class="sxs-lookup"><span data-stu-id="8c3b5-108"><xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType> class properties</span></span>|<span data-ttu-id="8c3b5-109"><xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType> クラスのプロパティ</span><span class="sxs-lookup"><span data-stu-id="8c3b5-109"><xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType> class properties</span></span>|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.ToolTip.Placement%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.Placement%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementTarget%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementTarget%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementRectangle%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementRectangle%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.HorizontalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.HorizontalOffset%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.VerticalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.VerticalOffset%2A?displayProperty=nameWithType>|  
  
 <span data-ttu-id="8c3b5-110"><xref:System.Windows.Controls.ToolTip> オブジェクトを使用してツールヒントの内容を定義する場合は、どちらのクラスのプロパティでも使用できます。ただし、<xref:System.Windows.Controls.ToolTipService> のプロパティが優先されます。</span><span class="sxs-lookup"><span data-stu-id="8c3b5-110">If you define the contents of a tooltip by using a <xref:System.Windows.Controls.ToolTip> object, you can use the properties of either class; however, the <xref:System.Windows.Controls.ToolTipService> properties take precedence.</span></span> <span data-ttu-id="8c3b5-111"><xref:System.Windows.Controls.ToolTip> オブジェクトとして定義されないツールヒントには、<xref:System.Windows.Controls.ToolTipService> のプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="8c3b5-111">Use the <xref:System.Windows.Controls.ToolTipService> properties for tooltips that are not defined as <xref:System.Windows.Controls.ToolTip> objects.</span></span>  
  
 <span data-ttu-id="8c3b5-112">次の図では、これらのプロパティを使用してツールヒントを配置する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8c3b5-112">The following illustrations show how to position a tooltip by using these properties.</span></span> <span data-ttu-id="8c3b5-113">これらの図の [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] の例では、<xref:System.Windows.Controls.ToolTip> クラスによって定義されているプロパティを設定する方法が示されていますが、<xref:System.Windows.Controls.ToolTipService> クラスの対応するプロパティも同じレイアウト規則に従います。</span><span class="sxs-lookup"><span data-stu-id="8c3b5-113">Although, the [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] examples in these illustrations show how to set the properties that are defined by the <xref:System.Windows.Controls.ToolTip> class, the corresponding properties of the <xref:System.Windows.Controls.ToolTipService> class follow the same layout rules.</span></span> <span data-ttu-id="8c3b5-114">Placement プロパティに使用できる値の詳細については、「[ポップアップの配置動作](popup-placement-behavior.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c3b5-114">For more information about the possible values for the Placement property, see [Popup Placement Behavior](popup-placement-behavior.md).</span></span>  

 <span data-ttu-id="8c3b5-115">次の図では、Placement プロパティを使用したツールヒントの配置を示します。</span><span class="sxs-lookup"><span data-stu-id="8c3b5-115">The following image shows tooltip placement by using the Placement property:</span></span>  
  
 ![Placement プロパティを使用したツールヒントの配置を示す図。](./media/how-to-position-a-tooltip/tooltip-placement-property.png)

 <span data-ttu-id="8c3b5-117">次の図では、Placement プロパティと PlacementRectangle プロパティを使用したツールヒントの配置を示します。</span><span class="sxs-lookup"><span data-stu-id="8c3b5-117">The following image shows tooltip placement by using the Placement and PlacementRectangle properties:</span></span>

 ![PlacementRectangle プロパティを使用したツールヒントの配置を示す図。](./media/how-to-position-a-tooltip/tooltip-placement-rectangle-property.png)  

 <span data-ttu-id="8c3b5-119">次の図では、Placement、PlacementRectangle、Offset の各プロパティを使用したツールヒントの配置を示します。</span><span class="sxs-lookup"><span data-stu-id="8c3b5-119">The following image shows tooltip placement by using the Placement, PlacementRectangle, and Offset properties:</span></span>
  
 ![Offset プロパティを使用したツールヒントの配置を示す図。](./media/how-to-position-a-tooltip/tooltip-placement-offset-property.png)

 <span data-ttu-id="8c3b5-121">次の例では、<xref:System.Windows.Controls.ToolTip> プロパティを使用して、内容が <xref:System.Windows.Controls.ToolTip> オブジェクトであるツールヒントの位置を指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8c3b5-121">The following example shows how to use the <xref:System.Windows.Controls.ToolTip> properties to specify the position of a tooltip whose content is a <xref:System.Windows.Controls.ToolTip> object.</span></span>  
  
 [!code-xaml[ToolTipService#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
 [!code-csharp[ToolTipService#ToolTipCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#tooltipcode)]
 [!code-vb[ToolTipService#ToolTipCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#tooltipcode)]  
  
 <span data-ttu-id="8c3b5-122">次の例では、<xref:System.Windows.Controls.ToolTipService> プロパティを使用して、内容が <xref:System.Windows.Controls.ToolTip> オブジェクトではないツールヒントの位置を指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8c3b5-122">The following example shows how to use the <xref:System.Windows.Controls.ToolTipService> properties to specify the position of a tooltip whose content is not a <xref:System.Windows.Controls.ToolTip> object.</span></span>  
  
 [!code-xaml[ToolTipService#NoToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
 [!code-csharp[ToolTipService#NoToolTipCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#notooltipcode)]
 [!code-vb[ToolTipService#NoToolTipCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#notooltipcode)]  
  
## <a name="see-also"></a><span data-ttu-id="8c3b5-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="8c3b5-123">See also</span></span>

- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [<span data-ttu-id="8c3b5-124">方法トピック</span><span class="sxs-lookup"><span data-stu-id="8c3b5-124">How-to Topics</span></span>](tooltip-how-to-topics.md)
- [<span data-ttu-id="8c3b5-125">ToolTip の概要</span><span class="sxs-lookup"><span data-stu-id="8c3b5-125">ToolTip Overview</span></span>](tooltip-overview.md)
