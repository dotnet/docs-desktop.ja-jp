---
title: GDI+ での多角形
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- polygons
- drawing [Windows Forms], polygons
- GDI+, polygons
ms.assetid: a72213d2-d69a-4c2b-a75c-be7b20390c13
ms.openlocfilehash: 2b1e3d387e4d056d9187c54dcef560544206c370
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96979732"
---
# <a name="polygons-in-gdi"></a><span data-ttu-id="307d8-102">GDI+ での多角形</span><span class="sxs-lookup"><span data-stu-id="307d8-102">Polygons in GDI+</span></span>
<span data-ttu-id="307d8-103">多角形は、3つ以上の直線を持つ閉じた図形です。</span><span class="sxs-lookup"><span data-stu-id="307d8-103">A polygon is a closed shape with three or more straight sides.</span></span> <span data-ttu-id="307d8-104">たとえば、三角形は3辺の多角形で、四角形は4辺の多角形で、五角形は5辺の多角形です。</span><span class="sxs-lookup"><span data-stu-id="307d8-104">For example, a triangle is a polygon with three sides, a rectangle is a polygon with four sides, and a pentagon is a polygon with five sides.</span></span> <span data-ttu-id="307d8-105">次の図は、いくつかのポリゴンを示しています。</span><span class="sxs-lookup"><span data-stu-id="307d8-105">The following illustration shows several polygons.</span></span>  
  
 <span data-ttu-id="307d8-106">![多角形](./media/aboutgdip02-art07.gif "Aboutgdip02_art07")</span><span class="sxs-lookup"><span data-stu-id="307d8-106">![Polygons](./media/aboutgdip02-art07.gif "Aboutgdip02_art07")</span></span>  
  
## <a name="drawing-a-polygon"></a><span data-ttu-id="307d8-107">多角形の描画</span><span class="sxs-lookup"><span data-stu-id="307d8-107">Drawing a Polygon</span></span>  
 <span data-ttu-id="307d8-108">多角形を描画するには、 <xref:System.Drawing.Graphics> オブジェクト、 <xref:System.Drawing.Pen> オブジェクト、および <xref:System.Drawing.Point> (または) オブジェクトの配列が必要 <xref:System.Drawing.PointF> です。</span><span class="sxs-lookup"><span data-stu-id="307d8-108">To draw a polygon, you need a <xref:System.Drawing.Graphics> object, a <xref:System.Drawing.Pen> object, and an array of <xref:System.Drawing.Point> (or <xref:System.Drawing.PointF>) objects.</span></span> <span data-ttu-id="307d8-109">オブジェクトは、 <xref:System.Drawing.Graphics> メソッドを提供し <xref:System.Drawing.Graphics.DrawPolygon%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="307d8-109">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawPolygon%2A> method.</span></span> <span data-ttu-id="307d8-110">オブジェクトは、 <xref:System.Drawing.Pen> 多角形のレンダリングに使用される線の幅や色などの属性を格納します。また、オブジェクトの配列は、 <xref:System.Drawing.Point> 直線によって接続される点を格納します。</span><span class="sxs-lookup"><span data-stu-id="307d8-110">The <xref:System.Drawing.Pen> object stores attributes, such as width and color, of the line used to render the polygon, and the array of <xref:System.Drawing.Point> objects stores the points to be connected by straight lines.</span></span> <span data-ttu-id="307d8-111"><xref:System.Drawing.Pen>オブジェクトとオブジェクトの配列は、 <xref:System.Drawing.Point> 引数としてメソッドに渡され <xref:System.Drawing.Graphics.DrawPolygon%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="307d8-111">The <xref:System.Drawing.Pen> object and the array of <xref:System.Drawing.Point> objects are passed as arguments to the <xref:System.Drawing.Graphics.DrawPolygon%2A> method.</span></span> <span data-ttu-id="307d8-112">次の例では、3つの辺を描画します。</span><span class="sxs-lookup"><span data-stu-id="307d8-112">The following example draws a three-sided polygon.</span></span> <span data-ttu-id="307d8-113">には、 `myPointArray` (0, 0)、(50, 30)、および (30, 60) の3つのポイントしか存在しないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="307d8-113">Note that there are only three points in `myPointArray`: (0, 0), (50, 30), and (30, 60).</span></span> <span data-ttu-id="307d8-114">メソッドは、 <xref:System.Drawing.Graphics.DrawPolygon%2A> (30, 60) から開始点 (0, 0) までの線を描画して、多角形を自動的に閉じます。</span><span class="sxs-lookup"><span data-stu-id="307d8-114">The <xref:System.Drawing.Graphics.DrawPolygon%2A> method automatically closes the polygon by drawing a line from (30, 60) back to the starting point (0, 0).</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#111](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#111)]
 [!code-vb[LinesCurvesAndShapes#111](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#111)]  
  
 <span data-ttu-id="307d8-115">次の図は、多角形を示しています。</span><span class="sxs-lookup"><span data-stu-id="307d8-115">The following illustration shows the polygon.</span></span>  
  
 <span data-ttu-id="307d8-116">![Polygon](./media/aboutgdip02-art08.gif "Aboutgdip02_art08")</span><span class="sxs-lookup"><span data-stu-id="307d8-116">![Polygon](./media/aboutgdip02-art08.gif "Aboutgdip02_art08")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="307d8-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="307d8-117">See also</span></span>

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [<span data-ttu-id="307d8-118">直線、曲線、および図形</span><span class="sxs-lookup"><span data-stu-id="307d8-118">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="307d8-119">方法: ペンを作成する</span><span class="sxs-lookup"><span data-stu-id="307d8-119">How to: Create a Pen</span></span>](how-to-create-a-pen.md)
