---
title: '方法: 描画に GuidelineSet を適用する'
ms.date: 03/30/2017
helpviewer_keywords:
- GuidelineSet property [WPF], applying to drawings
- graphics [WPF], GuidelineSet property
ms.assetid: 45f3e0b4-8820-45a7-b865-b8ea5b17b0c8
ms.openlocfilehash: 134236c5beca806b747d45f20764cc82ddd8a4e8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985048"
---
# <a name="how-to-apply-a-guidelineset-to-a-drawing"></a><span data-ttu-id="15f62-102">方法: 描画に GuidelineSet を適用する</span><span class="sxs-lookup"><span data-stu-id="15f62-102">How to: Apply a GuidelineSet to a Drawing</span></span>
<span data-ttu-id="15f62-103">この例では、<xref:System.Windows.Media.GuidelineSet> を <xref:System.Windows.Media.DrawingGroup> に適用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="15f62-103">This example shows how to apply a <xref:System.Windows.Media.GuidelineSet> to a <xref:System.Windows.Media.DrawingGroup>.</span></span>  
  
 <span data-ttu-id="15f62-104"><xref:System.Windows.Media.DrawingGroup> クラスは、<xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> プロパティを持つ唯一の <xref:System.Windows.Media.Drawing> 型です。</span><span class="sxs-lookup"><span data-stu-id="15f62-104">The <xref:System.Windows.Media.DrawingGroup> class is the only type of <xref:System.Windows.Media.Drawing> that has a <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> property.</span></span> <span data-ttu-id="15f62-105">別の <xref:System.Windows.Media.Drawing> 型に <xref:System.Windows.Media.GuidelineSet> を適用するには、それを <xref:System.Windows.Media.DrawingGroup> に追加し、<xref:System.Windows.Media.GuidelineSet> を <xref:System.Windows.Media.DrawingGroup> に適用します。</span><span class="sxs-lookup"><span data-stu-id="15f62-105">To apply a <xref:System.Windows.Media.GuidelineSet> to another type of <xref:System.Windows.Media.Drawing>, add it to a <xref:System.Windows.Media.DrawingGroup> and then apply the <xref:System.Windows.Media.GuidelineSet> to your <xref:System.Windows.Media.DrawingGroup>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15f62-106">例</span><span class="sxs-lookup"><span data-stu-id="15f62-106">Example</span></span>  
 <span data-ttu-id="15f62-107">次の例では、ほとんど同じである 2 つの <xref:System.Windows.Media.DrawingGroup> オブジェクトが作成されます。唯一の違いは、2 つ目の <xref:System.Windows.Media.DrawingGroup> に <xref:System.Windows.Media.GuidelineSet> があり、1 つ目にはそれがないことです。</span><span class="sxs-lookup"><span data-stu-id="15f62-107">The following example creates two <xref:System.Windows.Media.DrawingGroup> objects that are almost identical; the only difference is: the second <xref:System.Windows.Media.DrawingGroup> has a <xref:System.Windows.Media.GuidelineSet> and the first does not.</span></span>  
  
 <span data-ttu-id="15f62-108">この例からの出力を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="15f62-108">The following illustration shows the output from the example.</span></span> <span data-ttu-id="15f62-109">2 つの <xref:System.Windows.Media.DrawingGroup> オブジェクトではレンダリングの違いが微妙であるため、図の一部を拡大してあります。</span><span class="sxs-lookup"><span data-stu-id="15f62-109">Because the rendering difference between the two <xref:System.Windows.Media.DrawingGroup> objects is so subtle, portions of the drawings are enlarged.</span></span>  
  
 <span data-ttu-id="15f62-110">![GuidelineSet がある (またはない) DrawingGroup](./media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")</span><span class="sxs-lookup"><span data-stu-id="15f62-110">![A DrawingGroup with and without a GuidelineSet](./media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupGuidelineSetExample.cs#graphicsmmdrawinggroupguidelinesetexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupGuidelineSetExample.xaml#graphicsmmdrawinggroupguidelinesetexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="15f62-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="15f62-111">See also</span></span>

- <xref:System.Windows.Media.DrawingGroup>
- <xref:System.Windows.Media.GuidelineSet>
- [<span data-ttu-id="15f62-112">Drawing オブジェクトの概要</span><span class="sxs-lookup"><span data-stu-id="15f62-112">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
