---
title: '方法: RectangleGeometry を使用して四角形を定義する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], rectangles
- rectangles [WPF], creating with RectangleGeometry class
ms.assetid: e40b8a8e-54b8-416b-a9f2-be6dca9fdf0b
ms.openlocfilehash: 146ca7017ee38ad5c1065e59662ac441e7bfbfe2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984332"
---
# <a name="how-to-define-a-rectangle-using-a-rectanglegeometry"></a><span data-ttu-id="7945e-102">方法: RectangleGeometry を使用して四角形を定義する</span><span class="sxs-lookup"><span data-stu-id="7945e-102">How to: Define a Rectangle Using a RectangleGeometry</span></span>
<span data-ttu-id="7945e-103">この例では、<xref:System.Windows.Media.RectangleGeometry> クラスを使用して四角形を記述する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7945e-103">This example describes how to use the <xref:System.Windows.Media.RectangleGeometry> class to describe a rectangle.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7945e-104">例</span><span class="sxs-lookup"><span data-stu-id="7945e-104">Example</span></span>  
 <span data-ttu-id="7945e-105">次の例では、<xref:System.Windows.Media.RectangleGeometry> を作成してレンダリングする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7945e-105">The following example shows how to create and render a <xref:System.Windows.Media.RectangleGeometry>.</span></span>  <span data-ttu-id="7945e-106">四角形の相対位置と大きさは、<xref:System.Windows.Rect> 構造体によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="7945e-106">The relative position and the dimensions of the rectangle are defined by a <xref:System.Windows.Rect> structure.</span></span> <span data-ttu-id="7945e-107">相対位置は `50,50`、高さと幅は両方とも `25` で、正方形が作成されます。</span><span class="sxs-lookup"><span data-stu-id="7945e-107">The relative position is `50,50` and the height and the width are both `25` creating a square.</span></span> <span data-ttu-id="7945e-108">四角形の内部は、<xref:System.Windows.Media.Brushes.LemonChiffon%2A> ブラシで塗りつぶされ、輪郭は `1` の太さの <xref:System.Windows.Media.Brushes.Black%2A> ストロークで描かれます。</span><span class="sxs-lookup"><span data-stu-id="7945e-108">The rectangle's interior is painted with a <xref:System.Windows.Media.Brushes.LemonChiffon%2A> brush and its outline is painted with a <xref:System.Windows.Media.Brushes.Black%2A> stroke with a thickness of `1`.</span></span>  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 <span data-ttu-id="7945e-109">![RectangleGeometry](./media/graphicsmm-rectangle.gif "graphicsmm_rectangle")</span><span class="sxs-lookup"><span data-stu-id="7945e-109">![A RectangleGeometry](./media/graphicsmm-rectangle.gif "graphicsmm_rectangle")</span></span>  
<span data-ttu-id="7945e-110">RectangleGeometry</span><span class="sxs-lookup"><span data-stu-id="7945e-110">RectangleGeometry</span></span>  
  
 <span data-ttu-id="7945e-111">この例では、<xref:System.Windows.Shapes.Path> 要素を使用して、<xref:System.Windows.Media.RectangleGeometry> をレンダリングしていますが、<xref:System.Windows.Media.RectangleGeometry> オブジェクトを使用する方法は他にも多数あります。</span><span class="sxs-lookup"><span data-stu-id="7945e-111">Although this example used a <xref:System.Windows.Shapes.Path> element to render the <xref:System.Windows.Media.RectangleGeometry>, there are many other ways to use <xref:System.Windows.Media.RectangleGeometry> objects.</span></span> <span data-ttu-id="7945e-112">たとえば、<xref:System.Windows.Media.RectangleGeometry> を使用して、<xref:System.Windows.UIElement> の <xref:System.Windows.UIElement.Clip%2A>、または <xref:System.Windows.Media.GeometryDrawing> の <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="7945e-112">For example, a <xref:System.Windows.Media.RectangleGeometry> can be used to specify the <xref:System.Windows.UIElement.Clip%2A> of a <xref:System.Windows.UIElement> or the <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> of a <xref:System.Windows.Media.GeometryDrawing>.</span></span>  
  
 <span data-ttu-id="7945e-113">その他の単純なジオメトリ クラスには <xref:System.Windows.Media.LineGeometry> と <xref:System.Windows.Media.EllipseGeometry> が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7945e-113">Other simple geometry classes include <xref:System.Windows.Media.LineGeometry> and <xref:System.Windows.Media.EllipseGeometry>.</span></span> <span data-ttu-id="7945e-114">これらのジオメトリも、もっと複雑なジオメトリも、<xref:System.Windows.Media.PathGeometry> または <xref:System.Windows.Media.StreamGeometry> を利用して作成できます。</span><span class="sxs-lookup"><span data-stu-id="7945e-114">These geometries, as well as more complex ones, can also be created using a <xref:System.Windows.Media.PathGeometry> or <xref:System.Windows.Media.StreamGeometry>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7945e-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="7945e-115">See also</span></span>

- [<span data-ttu-id="7945e-116">ジオメトリの概要</span><span class="sxs-lookup"><span data-stu-id="7945e-116">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="7945e-117">複合図形を作成する</span><span class="sxs-lookup"><span data-stu-id="7945e-117">Create a Composite Shape</span></span>](how-to-create-a-composite-shape.md)
- [<span data-ttu-id="7945e-118">PathGeometry を使用して図形を作成する</span><span class="sxs-lookup"><span data-stu-id="7945e-118">Create a Shape by Using a PathGeometry</span></span>](how-to-create-a-shape-by-using-a-pathgeometry.md)
