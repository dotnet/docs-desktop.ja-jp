---
title: '方法: 複合描画を作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], composite
- composite drawings [WPF]
- graphics [WPF], composite drawings
ms.assetid: 066eb0ab-5f0e-439d-85c6-dca60af269fc
ms.openlocfilehash: 0af7fbca593627ebe8cd102a02617a27eac50aa5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985967"
---
# <a name="how-to-create-a-composite-drawing"></a><span data-ttu-id="16627-102">方法: 複合描画を作成する</span><span class="sxs-lookup"><span data-stu-id="16627-102">How to: Create a Composite Drawing</span></span>
<span data-ttu-id="16627-103">この例では、<xref:System.Windows.Media.DrawingGroup> を使用し、複数の <xref:System.Windows.Media.Drawing> オブジェクトを組み合わせて 1 つの描画を合成することで複雑な描画を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="16627-103">This example shows how to use a <xref:System.Windows.Media.DrawingGroup> to create complex drawings by combining multiple <xref:System.Windows.Media.Drawing> objects into a single composite drawing.</span></span>  
  
## <a name="example"></a><span data-ttu-id="16627-104">例</span><span class="sxs-lookup"><span data-stu-id="16627-104">Example</span></span>  
 <span data-ttu-id="16627-105">次の例では、<xref:System.Windows.Media.DrawingGroup> を使用し、<xref:System.Windows.Media.GeometryDrawing> オブジェクトと <xref:System.Windows.Media.ImageDrawing> オブジェクトから複合描画を作成します。</span><span class="sxs-lookup"><span data-stu-id="16627-105">The following example uses a <xref:System.Windows.Media.DrawingGroup> to create a composite drawing from the <xref:System.Windows.Media.GeometryDrawing> and <xref:System.Windows.Media.ImageDrawing> objects.</span></span> <span data-ttu-id="16627-106">次の図は、この例で生成される出力を示しています。</span><span class="sxs-lookup"><span data-stu-id="16627-106">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="16627-107">![複数の描画を含む DrawingGroup](./media/graphicsmm-simple.jpg "graphicsmm_simple")</span><span class="sxs-lookup"><span data-stu-id="16627-107">![A DrawingGroup with multiple drawings](./media/graphicsmm-simple.jpg "graphicsmm_simple")</span></span>  
<span data-ttu-id="16627-108">DrawingGroup を利用して作成された複合描画</span><span class="sxs-lookup"><span data-stu-id="16627-108">A composite drawing that is created by using DrawingGroup</span></span>  
  
 <span data-ttu-id="16627-109">描画の境界を示す灰色の枠線に注目してください。</span><span class="sxs-lookup"><span data-stu-id="16627-109">Note the gray border, which shows the bounds of the drawing.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 <span data-ttu-id="16627-110"><xref:System.Windows.Media.DrawingGroup> を使用し、<xref:System.Windows.Media.DrawingGroup.Transform%2A>、<xref:System.Windows.Media.DrawingGroup.Opacity%2A> 設定、<xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>、<xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>、<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>、または <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> をそれが含まれる描画に適用できます。</span><span class="sxs-lookup"><span data-stu-id="16627-110">You can use a <xref:System.Windows.Media.DrawingGroup> to apply a <xref:System.Windows.Media.DrawingGroup.Transform%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A> setting, <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, or <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> to the drawings it contains.</span></span> <span data-ttu-id="16627-111"><xref:System.Windows.Media.DrawingGroup> は <xref:System.Windows.Media.Drawing> でもあるため、他の <xref:System.Windows.Media.DrawingGroup> オブジェクトを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="16627-111">Because a <xref:System.Windows.Media.DrawingGroup> is also a <xref:System.Windows.Media.Drawing>, it can contain other <xref:System.Windows.Media.DrawingGroup> objects.</span></span>  
  
 <span data-ttu-id="16627-112">次の例は前の例に似ていますが、追加の <xref:System.Windows.Media.DrawingGroup> オブジェクトを使用し、その描画の一部にビットマップ効果と不透明度マスクを適用する点が異なっています。</span><span class="sxs-lookup"><span data-stu-id="16627-112">The following example is similar to the preceding example, except that it uses additional <xref:System.Windows.Media.DrawingGroup> objects to apply bitmap effects and an opacity mask to some of its drawings.</span></span> <span data-ttu-id="16627-113">次の図は、この例で生成される出力を示しています。</span><span class="sxs-lookup"><span data-stu-id="16627-113">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="16627-114">![複数の描画を含む DrawingGroup](./media/graphicsmm-multiple.jpg "graphicsmm_multiple")</span><span class="sxs-lookup"><span data-stu-id="16627-114">![A DrawingGroup with multiple drawings](./media/graphicsmm-multiple.jpg "graphicsmm_multiple")</span></span>  
<span data-ttu-id="16627-115">DrawingGroup オブジェクトが複数ある複合描画</span><span class="sxs-lookup"><span data-stu-id="16627-115">Composite drawing that has multiple DrawingGroup objects</span></span>  
  
 <span data-ttu-id="16627-116">描画の境界を示す灰色の枠線に注目してください。</span><span class="sxs-lookup"><span data-stu-id="16627-116">Note the gray border, which shows the bounds of the drawing.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmmultipledrawinggroupsexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmmultipledrawinggroupsexample)]  
  
 <span data-ttu-id="16627-117"><xref:System.Windows.Media.Drawing> オブジェクトの詳細については、「[Drawing オブジェクトの概要](drawing-objects-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16627-117">For more information about <xref:System.Windows.Media.Drawing> objects, see [Drawing Objects Overview](drawing-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16627-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="16627-118">See also</span></span>

- <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>
- <xref:System.Windows.Media.DrawingGroup.Transform%2A>
- <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>
- <xref:System.Windows.Media.DrawingGroup.Opacity%2A>
- <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>
- <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>
- [<span data-ttu-id="16627-119">Drawing オブジェクトの概要</span><span class="sxs-lookup"><span data-stu-id="16627-119">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
