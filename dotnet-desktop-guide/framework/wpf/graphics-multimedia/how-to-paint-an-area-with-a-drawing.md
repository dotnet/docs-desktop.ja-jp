---
title: '方法: 描画を使用して領域を塗りつぶす'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with drawings
- painting [WPF], with drawings
- drawings [WPF], painting with
ms.assetid: c10dc4b1-09b1-41e8-ad14-456b5fb377df
ms.openlocfilehash: 6b204ae631912181333e2559ebadcdc37e7693b7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985888"
---
# <a name="how-to-paint-an-area-with-a-drawing"></a><span data-ttu-id="409ea-102">方法: 描画を使用して領域を塗りつぶす</span><span class="sxs-lookup"><span data-stu-id="409ea-102">How to: Paint an Area with a Drawing</span></span>
<span data-ttu-id="409ea-103">この例では、描画を使用して領域を塗りつぶす方法を示します。</span><span class="sxs-lookup"><span data-stu-id="409ea-103">This example shows how to paint an area with a drawing.</span></span> <span data-ttu-id="409ea-104">描画を使用して領域を塗りつぶすには、<xref:System.Windows.Media.DrawingBrush> と、1 つ以上の <xref:System.Windows.Media.Drawing> オブジェクトを使用します。</span><span class="sxs-lookup"><span data-stu-id="409ea-104">To paint an area with a drawing, you use a <xref:System.Windows.Media.DrawingBrush> and one or more <xref:System.Windows.Media.Drawing> objects.</span></span>   <span data-ttu-id="409ea-105">次の例では、<xref:System.Windows.Media.DrawingBrush> を使用して 2 つの楕円の描画でオブジェクトを塗りつぶす方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="409ea-105">The following example uses a <xref:System.Windows.Media.DrawingBrush> to paint an object with a drawing of two ellipses.</span></span>  
  
## <a name="example"></a><span data-ttu-id="409ea-106">例</span><span class="sxs-lookup"><span data-stu-id="409ea-106">Example</span></span>  
 [!code-xaml[drawingbrush_snip#DrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_snip/CS/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 [!code-csharp[drawingbrush_procedural_snip#DrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_procedural_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-vb[drawingbrush_procedural_snip#DrawingBrushExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/drawingbrush_procedural_snip/VisualBasic/DrawingBrushExample.vb#drawingbrushexamplewholepage)]  
  
 <span data-ttu-id="409ea-107">この例の出力を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="409ea-107">The following illustration shows the example's output.</span></span>  
  
 <span data-ttu-id="409ea-108">![DrawingBrush からの出力](./media/graphicsmm-drawingbrush-simple.png "graphicsmm_drawingbrush_simple")</span><span class="sxs-lookup"><span data-stu-id="409ea-108">![Output from a DrawingBrush](./media/graphicsmm-drawingbrush-simple.png "graphicsmm_drawingbrush_simple")</span></span>  
  
 <span data-ttu-id="409ea-109">(図形の中心が白い理由は、「[複合図形の塗りつぶしを制御する](how-to-control-the-fill-of-a-composite-shape.md)」に説明されています。)</span><span class="sxs-lookup"><span data-stu-id="409ea-109">(The center of the shape is white for reasons described in     [Control the Fill of a Composite Shape](how-to-control-the-fill-of-a-composite-shape.md).)</span></span>  
  
 <span data-ttu-id="409ea-110"><xref:System.Windows.Media.DrawingBrush> オブジェクトの <xref:System.Windows.Media.TileBrush.Viewport%2A> と <xref:System.Windows.Media.TileBrush.TileMode%2A> プロパティを設定すると、繰り返しパターンを作成できます。</span><span class="sxs-lookup"><span data-stu-id="409ea-110">By setting a <xref:System.Windows.Media.DrawingBrush> object's <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.TileMode%2A> properties, you can create a repeating pattern.</span></span> <span data-ttu-id="409ea-111">2 つの楕円の描画から作成されるパターンで、オブジェクトを塗りつぶす例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="409ea-111">The following example paints an object with a pattern created from a drawing of two ellipses.</span></span>  
  
 [!code-xaml[drawingbrush_snip#TiledDrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_snip/CS/TiledDrawingBrushExample.xaml#tileddrawingbrushexamplewholepage)]  
  
 [!code-csharp[drawingbrush_procedural_snip#TiledDrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_procedural_snip/CSharp/TiledDrawingBrushExample.cs#tileddrawingbrushexamplewholepage)]
 [!code-vb[drawingbrush_procedural_snip#TiledDrawingBrushExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/drawingbrush_procedural_snip/VisualBasic/TiledDrawingBrushExample.vb#tileddrawingbrushexamplewholepage)]  
  
 <span data-ttu-id="409ea-112">並べて表示された <xref:System.Windows.Media.DrawingBrush> の出力を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="409ea-112">The following illustration shows the tiled <xref:System.Windows.Media.DrawingBrush> output.</span></span>  
  
 <span data-ttu-id="409ea-113">![DrawingBrush からの並べて表示される出力](./media/graphicsmm-drawingbrush-tiled.png "graphicsmm_drawingbrush_tiled")</span><span class="sxs-lookup"><span data-stu-id="409ea-113">![Tiled output from a DrawingBrush](./media/graphicsmm-drawingbrush-tiled.png "graphicsmm_drawingbrush_tiled")</span></span>  
  
 <span data-ttu-id="409ea-114">描画ブラシの詳細については、「[イメージ、描画、およびビジュアルによる塗りつぶし](painting-with-images-drawings-and-visuals.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="409ea-114">For more information about drawing brushes, see [Painting with Images, Drawings, and Visuals](painting-with-images-drawings-and-visuals.md).</span></span> <span data-ttu-id="409ea-115"><xref:System.Windows.Media.Drawing> オブジェクトの詳細については、「[Drawing オブジェクトの概要](drawing-objects-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="409ea-115">For more information about <xref:System.Windows.Media.Drawing> objects, see the [Drawing Objects Overview](drawing-objects-overview.md).</span></span>
