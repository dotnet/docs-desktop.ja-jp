---
title: '方法: ポリライン要素を使用してポリラインを描画する'
ms.date: 03/30/2017
helpviewer_keywords:
- connected lines [WPF]
- polylines [WPF], drawing
- graphics [WPF], polylines
- lines [WPF], connected (see polylines)
- drawing [WPF], polylines
ms.assetid: 65db8935-d047-4295-87c4-b427ff3ad293
ms.openlocfilehash: 4871d357d81ec80b63e69e6af133ae10b4e08b15
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985908"
---
# <a name="how-to-draw-a-polyline-by-using-the-polyline-element"></a><span data-ttu-id="073dc-102">方法: ポリライン要素を使用してポリラインを描画する</span><span class="sxs-lookup"><span data-stu-id="073dc-102">How to: Draw a Polyline by Using the Polyline Element</span></span>
<span data-ttu-id="073dc-103">この例では、<xref:System.Windows.Shapes.Polyline> 要素を使用してポリラインを描画する方法を示します。ポリラインは、接続された一連の線です。</span><span class="sxs-lookup"><span data-stu-id="073dc-103">This example shows how to draw a polyline, which is a series of connected lines, by using the <xref:System.Windows.Shapes.Polyline> element.</span></span>  
  
 <span data-ttu-id="073dc-104">ポリラインを描画するには、<xref:System.Windows.Shapes.Polyline> 要素を作成し、その <xref:System.Windows.Shapes.Polyline.Points%2A> プロパティを使用して図形の頂点を指定します。</span><span class="sxs-lookup"><span data-stu-id="073dc-104">To draw a polyline, create a <xref:System.Windows.Shapes.Polyline> element and use its <xref:System.Windows.Shapes.Polyline.Points%2A> property to specify the shape vertices.</span></span> <span data-ttu-id="073dc-105">最後に、<xref:System.Windows.Shapes.Shape.Stroke%2A> および <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> プロパティを使用してポリラインの輪郭を記述します。ストロークのない線は表示されないためです。</span><span class="sxs-lookup"><span data-stu-id="073dc-105">Finally, use the <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties to describe the polyline outline because a line without a stroke is invisible.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="073dc-106"><xref:System.Windows.Shapes.Polyline> 要素は閉じた図形ではないため、図形の輪郭を意図的に閉じた場合でも、<xref:System.Windows.Shapes.Shape.Fill%2A> プロパティに効力はありません。</span><span class="sxs-lookup"><span data-stu-id="073dc-106">Because the <xref:System.Windows.Shapes.Polyline> element is not a closed shape, the <xref:System.Windows.Shapes.Shape.Fill%2A> property has no effect, even if you deliberately close the shape outline.</span></span> <span data-ttu-id="073dc-107"><xref:System.Windows.Shapes.Shape.Fill%2A> で閉じた図形を作成するには、<xref:System.Windows.Shapes.Polygon> 要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="073dc-107">To create a closed shape with a <xref:System.Windows.Shapes.Shape.Fill%2A>, use a <xref:System.Windows.Shapes.Polygon> element.</span></span>  
  
 <span data-ttu-id="073dc-108">次の例では、<xref:System.Windows.Controls.Canvas> 内に 2 つの <xref:System.Windows.Shapes.Polyline> 要素を描画しています。</span><span class="sxs-lookup"><span data-stu-id="073dc-108">The following example draws two <xref:System.Windows.Shapes.Polyline> elements inside a <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="073dc-109">例</span><span class="sxs-lookup"><span data-stu-id="073dc-109">Example</span></span>  
 <span data-ttu-id="073dc-110">[!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] では、ポイントを表す有効な構文は、コンマで区切られた x と y の座標ペアのスペース区切りリストです。</span><span class="sxs-lookup"><span data-stu-id="073dc-110">In [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)], valid syntax for points is a space-delimited list of comma-separated x- and y-coordinate pairs.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#PolylineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 <span data-ttu-id="073dc-111">この例では、<xref:System.Windows.Controls.Canvas> を使用してポリラインを格納していますが、テキスト以外のコンテンツをサポートする <xref:System.Windows.Controls.Panel> または <xref:System.Windows.Controls.Control> があるポリライン要素 (およびその他のすべての図形要素) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="073dc-111">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the polylines, you can use polyline elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="073dc-112">この例は、大規模なサンプルの一部です。完全なサンプルについては、「[Shape 要素のサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="073dc-112">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="073dc-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="073dc-113">See also</span></span>

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Shapes.Polygon>
- <xref:System.Windows.Shapes.Shape>
- [<span data-ttu-id="073dc-114">Shape 要素のサンプル</span><span class="sxs-lookup"><span data-stu-id="073dc-114">Shape Elements Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
- [<span data-ttu-id="073dc-115">WPF での図形と基本描画の概要</span><span class="sxs-lookup"><span data-stu-id="073dc-115">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
