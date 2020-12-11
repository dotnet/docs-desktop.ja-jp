---
title: '方法: LineGeometry を使用して線を作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], lines
ms.assetid: 41231b22-1f74-4c26-a8e7-a55b29f8f6bd
ms.openlocfilehash: f8c334a54f78aec7af91064a447fd18f23dcfbdc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984335"
---
# <a name="how-to-create-a-line-using-a-linegeometry"></a><span data-ttu-id="9a09d-102">方法: LineGeometry を使用して線を作成する</span><span class="sxs-lookup"><span data-stu-id="9a09d-102">How to: Create a Line Using a LineGeometry</span></span>
<span data-ttu-id="9a09d-103">この例では、<xref:System.Windows.Media.LineGeometry> クラスを使用して線を表す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9a09d-103">This example shows how to use the <xref:System.Windows.Media.LineGeometry> class to describe a line.</span></span> <span data-ttu-id="9a09d-104"><xref:System.Windows.Media.LineGeometry> は開始点と終了点によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="9a09d-104">A <xref:System.Windows.Media.LineGeometry> is defined by its start and end points.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a09d-105">例</span><span class="sxs-lookup"><span data-stu-id="9a09d-105">Example</span></span>  
 <span data-ttu-id="9a09d-106">次の例では、<xref:System.Windows.Media.LineGeometry> を作成してレンダリングする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9a09d-106">The following example shows how to create and render a <xref:System.Windows.Media.LineGeometry>.</span></span>  <span data-ttu-id="9a09d-107"><xref:System.Windows.Shapes.Path> 要素は、線をレンダリングする目的で使用されています。</span><span class="sxs-lookup"><span data-stu-id="9a09d-107">A <xref:System.Windows.Shapes.Path> element is used to render the line.</span></span>  <span data-ttu-id="9a09d-108">線には領域がないため、<xref:System.Windows.Shapes.Path> オブジェクトの <xref:System.Windows.Shapes.Shape.Fill%2A> は指定されていません。その代わり、<xref:System.Windows.Shapes.Shape.Stroke%2A> プロパティと <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> プロパティが使用されています。</span><span class="sxs-lookup"><span data-stu-id="9a09d-108">Since a line has no area, the <xref:System.Windows.Shapes.Path> object's <xref:System.Windows.Shapes.Shape.Fill%2A> is not specified; instead the <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties are used.</span></span>  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 <span data-ttu-id="9a09d-109">![LineGeometry](./media/graphicsmm-line.gif "graphicsmm_line")</span><span class="sxs-lookup"><span data-stu-id="9a09d-109">![A LineGeometry](./media/graphicsmm-line.gif "graphicsmm_line")</span></span>  
<span data-ttu-id="9a09d-110">(10,20) から (100,130) まで描画された LineGeometry</span><span class="sxs-lookup"><span data-stu-id="9a09d-110">A LineGeometry drawn from (10,20) to (100,130)</span></span>  
  
 <span data-ttu-id="9a09d-111">その他の単純なジオメトリ クラスには <xref:System.Windows.Media.LineGeometry> と <xref:System.Windows.Media.EllipseGeometry> が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9a09d-111">Other simple geometry classes include <xref:System.Windows.Media.LineGeometry> and <xref:System.Windows.Media.EllipseGeometry>.</span></span> <span data-ttu-id="9a09d-112">これらのジオメトリも、もっと複雑なジオメトリも、<xref:System.Windows.Media.PathGeometry> または <xref:System.Windows.Media.StreamGeometry> を利用して作成できます。</span><span class="sxs-lookup"><span data-stu-id="9a09d-112">These geometries, as well as more complex ones, can also be created using a <xref:System.Windows.Media.PathGeometry> or <xref:System.Windows.Media.StreamGeometry>.</span></span> <span data-ttu-id="9a09d-113">詳細については、「[ジオメトリの概要](geometry-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a09d-113">For more information, see the [Geometry Overview](geometry-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a09d-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="9a09d-114">See also</span></span>

- [<span data-ttu-id="9a09d-115">ジオメトリの概要</span><span class="sxs-lookup"><span data-stu-id="9a09d-115">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="9a09d-116">複合図形を作成する</span><span class="sxs-lookup"><span data-stu-id="9a09d-116">Create a Composite Shape</span></span>](how-to-create-a-composite-shape.md)
- [<span data-ttu-id="9a09d-117">PathGeometry を使用して図形を作成する</span><span class="sxs-lookup"><span data-stu-id="9a09d-117">Create a Shape by Using a PathGeometry</span></span>](how-to-create-a-shape-by-using-a-pathgeometry.md)
