---
title: '方法: PathGeometry を使用して図形を作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], creating with PathGeometry class
- graphics [WPF], shapes
ms.assetid: 49a4a8b7-e738-45be-8dac-b54a6d8f5b21
ms.openlocfilehash: bdf3c937bfff1780a72e8743bc86a3c3dad2558d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984548"
---
# <a name="how-to-create-a-shape-by-using-a-pathgeometry"></a><span data-ttu-id="2c010-102">方法: PathGeometry を使用して図形を作成する</span><span class="sxs-lookup"><span data-stu-id="2c010-102">How to: Create a Shape by Using a PathGeometry</span></span>
<span data-ttu-id="2c010-103">次の例は、<xref:System.Windows.Media.PathGeometry> クラスを使用して図形を作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="2c010-103">This example shows how to create a shape using the <xref:System.Windows.Media.PathGeometry> class.</span></span> <span data-ttu-id="2c010-104"><xref:System.Windows.Media.PathGeometry> オブジェクトは、1 つまたは複数の <xref:System.Windows.Media.PathFigure> オブジェクトで構成されます。各 <xref:System.Windows.Media.PathFigure> は、別個の "図" または図形を表します。</span><span class="sxs-lookup"><span data-stu-id="2c010-104"><xref:System.Windows.Media.PathGeometry> objects are composed of one or more <xref:System.Windows.Media.PathFigure> objects; each <xref:System.Windows.Media.PathFigure> represents a different "figure" or shape.</span></span> <span data-ttu-id="2c010-105">各 <xref:System.Windows.Media.PathFigure> は、それぞれが図または図形の結合部分を表す 1 つ以上の <xref:System.Windows.Media.PathSegment> オブジェクトで構成されています。</span><span class="sxs-lookup"><span data-stu-id="2c010-105">Each <xref:System.Windows.Media.PathFigure> is itself composed of one or more <xref:System.Windows.Media.PathSegment> objects, each representing a connected portion of the figure or shape.</span></span> <span data-ttu-id="2c010-106">セグメントの種類には、<xref:System.Windows.Media.LineSegment>、<xref:System.Windows.Media.ArcSegment>、<xref:System.Windows.Media.BezierSegment> があります。</span><span class="sxs-lookup"><span data-stu-id="2c010-106">Segment types include <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>, and <xref:System.Windows.Media.BezierSegment>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c010-107">例</span><span class="sxs-lookup"><span data-stu-id="2c010-107">Example</span></span>  
 <span data-ttu-id="2c010-108">次の例では、<xref:System.Windows.Media.PathGeometry> を使用して三角形を作成します。</span><span class="sxs-lookup"><span data-stu-id="2c010-108">The following example uses a <xref:System.Windows.Media.PathGeometry> to create a triangle.</span></span> <span data-ttu-id="2c010-109"><xref:System.Windows.Media.PathGeometry> は、<xref:System.Windows.Shapes.Path> 要素を使用して表示されます。</span><span class="sxs-lookup"><span data-stu-id="2c010-109">The  <xref:System.Windows.Media.PathGeometry> is displayed using a <xref:System.Windows.Shapes.Path> element.</span></span>  
  
 [!code-xaml[GeometrySample#49](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#49)]  
  
 <span data-ttu-id="2c010-110">前の例で作成した図を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2c010-110">The following illustration shows the shape created in the previous example.</span></span>  
  
 <span data-ttu-id="2c010-111">![PathGeometry](./media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")</span><span class="sxs-lookup"><span data-stu-id="2c010-111">![A PathGeometry](./media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")</span></span>  
<span data-ttu-id="2c010-112">PathGeometry を使用して作成された三角形</span><span class="sxs-lookup"><span data-stu-id="2c010-112">A triangle created with a PathGeometry</span></span>  
  
 <span data-ttu-id="2c010-113">前の例では、比較的単純な図形である三角形を作成する方法を紹介しました。</span><span class="sxs-lookup"><span data-stu-id="2c010-113">The previous example showed how to create a relatively simple shape, a triangle.</span></span> <span data-ttu-id="2c010-114"><xref:System.Windows.Media.PathGeometry> を使用して、円弧や曲線など、より複雑な図形を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="2c010-114">A <xref:System.Windows.Media.PathGeometry> can also be used to create more complex shapes, including arcs and curves.</span></span> <span data-ttu-id="2c010-115">例については、「[楕円の円弧を作成する](how-to-create-an-elliptical-arc.md)」、「[3 次ベジエ曲線を作成する](how-to-create-a-cubic-bezier-curve.md)」、「[2 次ベジエ曲線を作成する](how-to-create-a-quadratic-bezier-curve.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2c010-115">For examples, see [Create an Elliptical Arc](how-to-create-an-elliptical-arc.md), [Create a Cubic Bezier Curve](how-to-create-a-cubic-bezier-curve.md), and [Create a Quadratic Bezier Curve](how-to-create-a-quadratic-bezier-curve.md).</span></span>  
  
 <span data-ttu-id="2c010-116">この例は、より大きなサンプルの一部です。完全なサンプルについては、「[ジオメトリのサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c010-116">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c010-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="2c010-117">See also</span></span>

- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.GeometryDrawing>
- [<span data-ttu-id="2c010-118">ジオメトリの概要</span><span class="sxs-lookup"><span data-stu-id="2c010-118">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="2c010-119">ジオメトリのサンプル</span><span class="sxs-lookup"><span data-stu-id="2c010-119">Geometries Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)
