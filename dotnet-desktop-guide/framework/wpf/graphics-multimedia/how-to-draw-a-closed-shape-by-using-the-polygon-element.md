---
title: '方法: 多角形要素を使用して、閉じた図形を描画する'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], Polygon elements
- closed shapes [WPF], drawing with Polygon elements
- Polygon elements [WPF]
- drawing [WPF], closed shapes with Polygon elements
ms.assetid: 4b0ca008-29ce-48dd-8bc3-f3a20ffca6a6
ms.openlocfilehash: 53359d05555a572796961a82c7b5e95f14ebddc3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985911"
---
# <a name="how-to-draw-a-closed-shape-by-using-the-polygon-element"></a><span data-ttu-id="3845d-102">方法: 多角形要素を使用して、閉じた図形を描画する</span><span class="sxs-lookup"><span data-stu-id="3845d-102">How to: Draw a Closed Shape by Using the Polygon Element</span></span>
<span data-ttu-id="3845d-103">この例では、<xref:System.Windows.Shapes.Polygon> 要素を使用して閉じた図形を描画する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3845d-103">This example shows how to draw a closed shape by using the <xref:System.Windows.Shapes.Polygon> element.</span></span> <span data-ttu-id="3845d-104">閉じた図形を描画するには、<xref:System.Windows.Shapes.Polygon> 要素を作成し、その <xref:System.Windows.Shapes.Polygon.Points%2A> プロパティを使用して図形の頂点を指定します。</span><span class="sxs-lookup"><span data-stu-id="3845d-104">To draw a closed shape, create a <xref:System.Windows.Shapes.Polygon> element and use its <xref:System.Windows.Shapes.Polygon.Points%2A> property to specify the vertices of a shape.</span></span> <span data-ttu-id="3845d-105">最初と最後の点をつなぐ線が自動的に描画されます。</span><span class="sxs-lookup"><span data-stu-id="3845d-105">A line is automatically drawn that connects the first and last points.</span></span> <span data-ttu-id="3845d-106">最後に、<xref:System.Windows.Shapes.Shape.Fill%2A>、<xref:System.Windows.Shapes.Shape.Stroke%2A>、またはその両方を指定します。</span><span class="sxs-lookup"><span data-stu-id="3845d-106">Finally, specify a <xref:System.Windows.Shapes.Shape.Fill%2A>, a <xref:System.Windows.Shapes.Shape.Stroke%2A>, or both.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3845d-107">例</span><span class="sxs-lookup"><span data-stu-id="3845d-107">Example</span></span>  
 <span data-ttu-id="3845d-108">[!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] では、ポイントを表す有効な構文は、コンマで区切られた x と y の座標ペアのスペース区切りリストです。</span><span class="sxs-lookup"><span data-stu-id="3845d-108">In [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)], valid syntax for points is a space-delimited list of comma-separated x- and y-coordinate pairs.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#PolygonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polygonexample.xaml#polygonexample1)]  
  
 <span data-ttu-id="3845d-109">この例では、<xref:System.Windows.Controls.Canvas> を使用して多角形を格納していますが、テキスト以外のコンテンツをサポートする <xref:System.Windows.Controls.Panel> または <xref:System.Windows.Controls.Control> がある多角形要素 (およびその他のすべての図形要素) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3845d-109">Although the example uses a <xref:System.Windows.Controls.Canvas> to contain the polygons, you can use polygon elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="3845d-110">この例は、より大きなサンプルの一部です。サンプル全体については、「[Shape 要素のサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3845d-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>
