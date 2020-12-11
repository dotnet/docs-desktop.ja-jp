---
title: '方法: GeometryDrawing を作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], renderable
- renderable shapes [WPF]
- graphics [WPF], GeometryDrawing class
- classes [WPF], GeometryDrawing
ms.assetid: 11d3c096-91ba-4d41-9bba-aeac0db70f97
ms.openlocfilehash: f5cdcfdb68ad8030bcbd6c689f45a8baddd000e1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984732"
---
# <a name="how-to-create-a-geometrydrawing"></a><span data-ttu-id="20e5a-102">方法: GeometryDrawing を作成する</span><span class="sxs-lookup"><span data-stu-id="20e5a-102">How to: Create a GeometryDrawing</span></span>
<span data-ttu-id="20e5a-103">この例では、<xref:System.Windows.Media.GeometryDrawing> を作成し、表示する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="20e5a-103">This example shows how to create and display a <xref:System.Windows.Media.GeometryDrawing>.</span></span> <span data-ttu-id="20e5a-104"><xref:System.Windows.Media.GeometryDrawing> を利用すると、<xref:System.Windows.Media.Pen> と <xref:System.Windows.Media.Brush> を <xref:System.Windows.Media.Geometry> に関連付け、塗りつぶしと枠線で図形を作成できます。</span><span class="sxs-lookup"><span data-stu-id="20e5a-104">A <xref:System.Windows.Media.GeometryDrawing> enables you to create shape with a fill and an outline by associating a <xref:System.Windows.Media.Pen> and a <xref:System.Windows.Media.Brush> with a <xref:System.Windows.Media.Geometry>.</span></span> <span data-ttu-id="20e5a-105"><xref:System.Windows.Media.GeometryDrawing.Geometry%2A> によって図形の構造が説明され、<xref:System.Windows.Media.GeometryDrawing.Brush%2A> によって図形の塗りつぶしが説明され、<xref:System.Windows.Media.GeometryDrawing.Pen%2A> によって図形の枠線が説明されます。</span><span class="sxs-lookup"><span data-stu-id="20e5a-105">The <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> describes the shape's structure, the <xref:System.Windows.Media.GeometryDrawing.Brush%2A> describes the shape's fill, and the <xref:System.Windows.Media.GeometryDrawing.Pen%2A> describes the shape's outline.</span></span>  
  
## <a name="example"></a><span data-ttu-id="20e5a-106">例</span><span class="sxs-lookup"><span data-stu-id="20e5a-106">Example</span></span>  
 <span data-ttu-id="20e5a-107">次の例では、<xref:System.Windows.Media.GeometryDrawing> を使用して図形を表現します。</span><span class="sxs-lookup"><span data-stu-id="20e5a-107">The following example uses a <xref:System.Windows.Media.GeometryDrawing> to render a shape.</span></span> <span data-ttu-id="20e5a-108">この図形は 1 つの <xref:System.Windows.Media.GeometryGroup> オブジェクトと 2 つの <xref:System.Windows.Media.EllipseGeometry> オブジェクトによって説明されます。</span><span class="sxs-lookup"><span data-stu-id="20e5a-108">The shape is described by a <xref:System.Windows.Media.GeometryGroup> and two <xref:System.Windows.Media.EllipseGeometry> objects.</span></span> <span data-ttu-id="20e5a-109">図形の内側は <xref:System.Windows.Media.LinearGradientBrush> で塗りつぶされ、その枠線は <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen> で描かれます。</span><span class="sxs-lookup"><span data-stu-id="20e5a-109">The shape's interior is painted with a <xref:System.Windows.Media.LinearGradientBrush> and its outline is drawn with a <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>.</span></span> <span data-ttu-id="20e5a-110"><xref:System.Windows.Media.GeometryDrawing> は、<xref:System.Windows.Media.ImageDrawing> と <xref:System.Windows.Controls.Image> 要素を使用して表示されます。</span><span class="sxs-lookup"><span data-stu-id="20e5a-110">The <xref:System.Windows.Media.GeometryDrawing> is displayed using an <xref:System.Windows.Media.ImageDrawing> and an <xref:System.Windows.Controls.Image> element.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexamplewholepage)]  
  
 <span data-ttu-id="20e5a-111">結果的に生成される <xref:System.Windows.Media.GeometryDrawing> を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="20e5a-111">The following illustration shows the resulting <xref:System.Windows.Media.GeometryDrawing>.</span></span>  
  
 <span data-ttu-id="20e5a-112">![2 つの楕円の GeometryDrawing](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span><span class="sxs-lookup"><span data-stu-id="20e5a-112">![A GeometryDrawing of two ellipses](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span></span>  
  
 <span data-ttu-id="20e5a-113">もっと複雑な描画を作成するには、<xref:System.Windows.Media.DrawingGroup> を利用し、複数の描画オブジェクトを組み合わせて 1 つの描画に複合できます。</span><span class="sxs-lookup"><span data-stu-id="20e5a-113">To create more complex drawings, you can combine multiple drawing objects into a single composite drawing using a <xref:System.Windows.Media.DrawingGroup>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20e5a-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="20e5a-114">See also</span></span>

- <xref:System.Windows.Media.DrawingGroup>
- [<span data-ttu-id="20e5a-115">Drawing オブジェクトの概要</span><span class="sxs-lookup"><span data-stu-id="20e5a-115">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="20e5a-116">ジオメトリの概要</span><span class="sxs-lookup"><span data-stu-id="20e5a-116">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="20e5a-117">複合描画を作成する</span><span class="sxs-lookup"><span data-stu-id="20e5a-117">Create a Composite Drawing</span></span>](how-to-create-a-composite-drawing.md)
