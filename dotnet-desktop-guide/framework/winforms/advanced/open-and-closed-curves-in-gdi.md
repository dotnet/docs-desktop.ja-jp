---
title: GDI+ での開いた曲線と閉じた曲線
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- curves [Windows Forms], filling
- GDI+, curves
- curves [Windows Forms], drawing
- curves
ms.assetid: 08d2cc9a-dc9d-4eed-bcbb-2c8e2ca5d3ae
ms.openlocfilehash: 06afdc4549f7c3c9b0636e5c7052dcca87a153f1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981663"
---
# <a name="open-and-closed-curves-in-gdi"></a><span data-ttu-id="b188d-102">GDI+ での開いた曲線と閉じた曲線</span><span class="sxs-lookup"><span data-stu-id="b188d-102">Open and Closed Curves in GDI+</span></span>
<span data-ttu-id="b188d-103">次の図は、開いている曲線と閉じた曲線の2つの曲線を示しています。</span><span class="sxs-lookup"><span data-stu-id="b188d-103">The following illustration shows two curves: one open and one closed.</span></span>  
  
 <span data-ttu-id="b188d-104">![& 閉じた曲線を開く](./media/aboutgdip02-art24.gif "Aboutgdip02_art24")</span><span class="sxs-lookup"><span data-stu-id="b188d-104">![Open & Closed curves](./media/aboutgdip02-art24.gif "Aboutgdip02_art24")</span></span>  
  
## <a name="managed-interface-for-curves"></a><span data-ttu-id="b188d-105">曲線のマネージインターフェイス</span><span class="sxs-lookup"><span data-stu-id="b188d-105">Managed Interface for Curves</span></span>  
 <span data-ttu-id="b188d-106">閉じた曲線には内部があるため、ブラシで塗りつぶすことができます。</span><span class="sxs-lookup"><span data-stu-id="b188d-106">Closed curves have an interior and therefore can be filled with a brush.</span></span> <span data-ttu-id="b188d-107"><xref:System.Drawing.Graphics>Gdi + のクラスは、閉じられた図形および曲線を塗りつぶすために、、、、、、、およびの各メソッドを提供します <xref:System.Drawing.Graphics.FillRectangle%2A> <xref:System.Drawing.Graphics.FillEllipse%2A> <xref:System.Drawing.Graphics.FillPie%2A> <xref:System.Drawing.Graphics.FillPolygon%2A> <xref:System.Drawing.Graphics.FillClosedCurve%2A> <xref:System.Drawing.Graphics.FillPath%2A> <xref:System.Drawing.Graphics.FillRegion%2A> 。</span><span class="sxs-lookup"><span data-stu-id="b188d-107">The <xref:System.Drawing.Graphics> class in GDI+ provides the following methods for filling closed shapes and curves: <xref:System.Drawing.Graphics.FillRectangle%2A>, <xref:System.Drawing.Graphics.FillEllipse%2A>, <xref:System.Drawing.Graphics.FillPie%2A>, <xref:System.Drawing.Graphics.FillPolygon%2A>, <xref:System.Drawing.Graphics.FillClosedCurve%2A>, <xref:System.Drawing.Graphics.FillPath%2A>, and <xref:System.Drawing.Graphics.FillRegion%2A>.</span></span> <span data-ttu-id="b188d-108">これらのメソッドのいずれかを呼び出す場合は常に、特定のブラシの種類 ( <xref:System.Drawing.SolidBrush> 、、 <xref:System.Drawing.Drawing2D.HatchBrush> <xref:System.Drawing.TextureBrush> 、 <xref:System.Drawing.Drawing2D.LinearGradientBrush> 、または) のいずれかを <xref:System.Drawing.Drawing2D.PathGradientBrush> 引数として渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="b188d-108">Whenever you call one of these methods, you must pass one of the specific brush types (<xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, or <xref:System.Drawing.Drawing2D.PathGradientBrush>) as an argument.</span></span>  
  
 <span data-ttu-id="b188d-109">メソッドは、メソッドに関連してい <xref:System.Drawing.Graphics.FillPie%2A> <xref:System.Drawing.Graphics.DrawArc%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="b188d-109">The <xref:System.Drawing.Graphics.FillPie%2A> method is a companion to the <xref:System.Drawing.Graphics.DrawArc%2A> method.</span></span> <span data-ttu-id="b188d-110"><xref:System.Drawing.Graphics.DrawArc%2A>メソッドが楕円の輪郭の一部を描画するのと同様に、 <xref:System.Drawing.Graphics.FillPie%2A> メソッドは楕円の内部の一部を塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="b188d-110">Just as the <xref:System.Drawing.Graphics.DrawArc%2A> method draws a portion of the outline of an ellipse, the <xref:System.Drawing.Graphics.FillPie%2A> method fills a portion of the interior of an ellipse.</span></span> <span data-ttu-id="b188d-111">次の例では、円弧を描画し、楕円の内部の対応する部分を塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="b188d-111">The following example draws an arc and fills the corresponding portion of the interior of the ellipse:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#21](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#21)]
 [!code-vb[LinesCurvesAndShapes#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#21)]  
  
 <span data-ttu-id="b188d-112">次の図は、円弧と塗りつぶされた円グラフを示しています。</span><span class="sxs-lookup"><span data-stu-id="b188d-112">The following illustration shows the arc and the filled pie.</span></span>  
  
 <span data-ttu-id="b188d-113">![& 閉じた曲線を開く](./media/aboutgdip02-art25.gif "Aboutgdip02_art25")</span><span class="sxs-lookup"><span data-stu-id="b188d-113">![Open & Closed curves](./media/aboutgdip02-art25.gif "Aboutgdip02_art25")</span></span>  
  
 <span data-ttu-id="b188d-114">メソッドは、メソッドに関連してい <xref:System.Drawing.Graphics.FillClosedCurve%2A> <xref:System.Drawing.Graphics.DrawClosedCurve%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="b188d-114">The <xref:System.Drawing.Graphics.FillClosedCurve%2A> method is a companion to the <xref:System.Drawing.Graphics.DrawClosedCurve%2A> method.</span></span> <span data-ttu-id="b188d-115">どちらのメソッドも、終了点を開始位置に接続することによって、曲線を自動的に閉じます。</span><span class="sxs-lookup"><span data-stu-id="b188d-115">Both methods automatically close the curve by connecting the ending point to the starting point.</span></span> <span data-ttu-id="b188d-116">次の例では、(0, 0)、(60, 20)、および (40, 50) を通過する曲線を描画します。</span><span class="sxs-lookup"><span data-stu-id="b188d-116">The following example draws a curve that passes through (0, 0), (60, 20), and (40, 50).</span></span> <span data-ttu-id="b188d-117">次に、曲線は、(40, 50) を開始点 (0, 0) に接続することによって自動的に閉じられ、内部は純色で塗りつぶされます。</span><span class="sxs-lookup"><span data-stu-id="b188d-117">Then, the curve is automatically closed by connecting (40, 50) to the starting point (0, 0), and the interior is filled with a solid color.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#22](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#22)]
 [!code-vb[LinesCurvesAndShapes#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#22)]  
  
 <span data-ttu-id="b188d-118">メソッドは、 <xref:System.Drawing.Graphics.FillPath%2A> パスの各部分の内部を塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="b188d-118">The <xref:System.Drawing.Graphics.FillPath%2A> method fills the interiors of the separate pieces of a path.</span></span> <span data-ttu-id="b188d-119">パスの一部が閉じた曲線または形状を形成しない場合、メソッドは、 <xref:System.Drawing.Graphics.FillPath%2A> そのパスを埋める前にその部分を自動的に閉じます。</span><span class="sxs-lookup"><span data-stu-id="b188d-119">If a piece of a path doesn't form a closed curve or shape, the <xref:System.Drawing.Graphics.FillPath%2A> method automatically closes that piece of the path before filling it.</span></span> <span data-ttu-id="b188d-120">次の例では、円弧、カーディナルスプライン、文字列、および円で構成されるパスを描画し、塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="b188d-120">The following example draws and fills a path that consists of an arc, a cardinal spline, a string, and a pie:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#23](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#23)]
 [!code-vb[LinesCurvesAndShapes#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#23)]  
  
 <span data-ttu-id="b188d-121">次の図は、純色の塗りつぶしなしのパスを示しています。</span><span class="sxs-lookup"><span data-stu-id="b188d-121">The following illustration shows the path with and without the solid fill.</span></span> <span data-ttu-id="b188d-122">文字列内のテキストは、メソッドによってアウトライン表示されていますが、塗りつぶされていないことに注意して <xref:System.Drawing.Graphics.DrawPath%2A> ください。</span><span class="sxs-lookup"><span data-stu-id="b188d-122">Note that the text in the string is outlined, but not filled, by the <xref:System.Drawing.Graphics.DrawPath%2A> method.</span></span> <span data-ttu-id="b188d-123">これは、 <xref:System.Drawing.Graphics.FillPath%2A> 文字列内の文字の内部を描画するメソッドです。</span><span class="sxs-lookup"><span data-stu-id="b188d-123">It is the <xref:System.Drawing.Graphics.FillPath%2A> method that paints the interiors of the characters in the string.</span></span>  
  
 <span data-ttu-id="b188d-124">![パスの文字列](./media/aboutgdip02-art26.gif "Aboutgdip02_art26")</span><span class="sxs-lookup"><span data-stu-id="b188d-124">![String in a path](./media/aboutgdip02-art26.gif "Aboutgdip02_art26")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b188d-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="b188d-125">See also</span></span>

- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- <xref:System.Drawing.Point?displayProperty=nameWithType>
- [<span data-ttu-id="b188d-126">直線、曲線、および図形</span><span class="sxs-lookup"><span data-stu-id="b188d-126">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="b188d-127">方法: 描画する Graphics オブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="b188d-127">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="b188d-128">パスの作成および描画</span><span class="sxs-lookup"><span data-stu-id="b188d-128">Constructing and Drawing Paths</span></span>](constructing-and-drawing-paths.md)
