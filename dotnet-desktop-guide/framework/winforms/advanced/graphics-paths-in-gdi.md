---
title: GDI+ でのグラフィックス パス
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], paths
- GDI+, drawing paths
- paths [Windows Forms], drawing
- drawing [Windows Forms], paths
ms.assetid: a5500dec-666c-41fd-9da3-2169dd89c5eb
ms.openlocfilehash: 8e06032d145eb8c1aaf9bfcd1f205f8c6583634a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974435"
---
# <a name="graphics-paths-in-gdi"></a><span data-ttu-id="2ea31-102">GDI+ でのグラフィックス パス</span><span class="sxs-lookup"><span data-stu-id="2ea31-102">Graphics Paths in GDI+</span></span>
<span data-ttu-id="2ea31-103">パスは、直線、四角形、および単純な曲線を組み合わせることによって形成されます。</span><span class="sxs-lookup"><span data-stu-id="2ea31-103">Paths are formed by combining lines, rectangles, and simple curves.</span></span> <span data-ttu-id="2ea31-104">[ベクターグラフィックスの概要](vector-graphics-overview.md)からは、次の基本的な構成要素が、画像を描画するうえで最も役に立つことが実証されていることを思い出してください。</span><span class="sxs-lookup"><span data-stu-id="2ea31-104">Recall from the [Vector Graphics Overview](vector-graphics-overview.md) that the following basic building blocks have proven to be the most useful for drawing pictures:</span></span>  
  
- <span data-ttu-id="2ea31-105">路線</span><span class="sxs-lookup"><span data-stu-id="2ea31-105">Lines</span></span>  
  
- <span data-ttu-id="2ea31-106">四角形</span><span class="sxs-lookup"><span data-stu-id="2ea31-106">Rectangles</span></span>  
  
- <span data-ttu-id="2ea31-107">楕円</span><span class="sxs-lookup"><span data-stu-id="2ea31-107">Ellipses</span></span>  
  
- <span data-ttu-id="2ea31-108">アーク</span><span class="sxs-lookup"><span data-stu-id="2ea31-108">Arcs</span></span>  
  
- <span data-ttu-id="2ea31-109">多角形</span><span class="sxs-lookup"><span data-stu-id="2ea31-109">Polygons</span></span>  
  
- <span data-ttu-id="2ea31-110">カーディナルスプライン</span><span class="sxs-lookup"><span data-stu-id="2ea31-110">Cardinal splines</span></span>  
  
- <span data-ttu-id="2ea31-111">ベジエスプライン</span><span class="sxs-lookup"><span data-stu-id="2ea31-111">Bézier splines</span></span>  
  
 <span data-ttu-id="2ea31-112">GDI + では、オブジェクトを使用して、 <xref:System.Drawing.Drawing2D.GraphicsPath> これらの構成要素のシーケンスを1つの単位にまとめることができます。</span><span class="sxs-lookup"><span data-stu-id="2ea31-112">In GDI+, the <xref:System.Drawing.Drawing2D.GraphicsPath> object allows you to collect a sequence of these building blocks into a single unit.</span></span> <span data-ttu-id="2ea31-113">その後、クラスのメソッドを1回呼び出して、直線、四角形、多角形、および曲線のシーケンス全体を描画でき <xref:System.Drawing.Graphics.DrawPath%2A> <xref:System.Drawing.Graphics> ます。</span><span class="sxs-lookup"><span data-stu-id="2ea31-113">The entire sequence of lines, rectangles, polygons, and curves can then be drawn with one call to the <xref:System.Drawing.Graphics.DrawPath%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="2ea31-114">次の図は、直線、円弧、ベジエスプライン、およびカーディナルスプラインを組み合わせることによって作成されるパスを示しています。</span><span class="sxs-lookup"><span data-stu-id="2ea31-114">The following illustration shows a path created by combining a line, an arc, a Bézier spline, and a cardinal spline.</span></span>  
  
 <span data-ttu-id="2ea31-115">![パス](./media/aboutgdip02-art14.gif "Aboutgdip02_art14")</span><span class="sxs-lookup"><span data-stu-id="2ea31-115">![Path](./media/aboutgdip02-art14.gif "Aboutgdip02_art14")</span></span>  
  
## <a name="using-a-path"></a><span data-ttu-id="2ea31-116">パスの使用</span><span class="sxs-lookup"><span data-stu-id="2ea31-116">Using a Path</span></span>  
 <span data-ttu-id="2ea31-117">クラスには <xref:System.Drawing.Drawing2D.GraphicsPath> 、描画される項目のシーケンスを作成するための次のメソッドが用意されています。 <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> 、、、、 <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangle%2A> <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A> <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> <xref:System.Drawing.Drawing2D.GraphicsPath.AddPolygon%2A> 、 <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> (カーディナルスプラインの場合)、および <xref:System.Drawing.Drawing2D.GraphicsPath.AddBezier%2A> 。</span><span class="sxs-lookup"><span data-stu-id="2ea31-117">The <xref:System.Drawing.Drawing2D.GraphicsPath> class provides the following methods for creating a sequence of items to be drawn: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangle%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddPolygon%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> (for cardinal splines), and <xref:System.Drawing.Drawing2D.GraphicsPath.AddBezier%2A>.</span></span> <span data-ttu-id="2ea31-118">これらのメソッドはそれぞれオーバーロードされます。つまり、各メソッドはいくつかの異なるパラメーターリストをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="2ea31-118">Each of these methods is overloaded; that is, each method supports several different parameter lists.</span></span> <span data-ttu-id="2ea31-119">たとえば、メソッドの1つのバリエーションが4つの <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> 整数を受け取り、メソッドの別のバリエーションが <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> 2 つのオブジェクトを受け取り <xref:System.Drawing.Point> ます。</span><span class="sxs-lookup"><span data-stu-id="2ea31-119">For example, one variation of the <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> method receives four integers, and another variation of the <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> method receives two <xref:System.Drawing.Point> objects.</span></span>  
  
 <span data-ttu-id="2ea31-120">パスに線、四角形、およびベジエスプラインを追加する方法には、1回の呼び出しで複数の項目をパスに追加する複数形のコンパニオンメソッドがあります。 <xref:System.Drawing.Drawing2D.GraphicsPath.AddLines%2A> 、、 <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangles%2A> および <xref:System.Drawing.Drawing2D.GraphicsPath.AddBeziers%2A> です。</span><span class="sxs-lookup"><span data-stu-id="2ea31-120">The methods for adding lines, rectangles, and Bézier splines to a path have plural companion methods that add several items to the path in a single call: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLines%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangles%2A>, and <xref:System.Drawing.Drawing2D.GraphicsPath.AddBeziers%2A>.</span></span> <span data-ttu-id="2ea31-121">また、 <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> メソッドとメソッドには、 <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> 終了し <xref:System.Drawing.Drawing2D.GraphicsPath.AddClosedCurve%2A> <xref:System.Drawing.Drawing2D.GraphicsPath.AddPie%2A> た曲線または円をパスに追加するコンパニオンメソッドとがあります。</span><span class="sxs-lookup"><span data-stu-id="2ea31-121">Also, the <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> and <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> methods have companion methods, <xref:System.Drawing.Drawing2D.GraphicsPath.AddClosedCurve%2A> and <xref:System.Drawing.Drawing2D.GraphicsPath.AddPie%2A>, that add a closed curve or pie to the path.</span></span>  
  
 <span data-ttu-id="2ea31-122">パスを描画するには、 <xref:System.Drawing.Graphics> オブジェクト、オブジェクト、 <xref:System.Drawing.Pen> およびオブジェクトが必要 <xref:System.Drawing.Drawing2D.GraphicsPath> です。</span><span class="sxs-lookup"><span data-stu-id="2ea31-122">To draw a path, you need a <xref:System.Drawing.Graphics> object, a <xref:System.Drawing.Pen> object, and a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="2ea31-123"><xref:System.Drawing.Graphics>オブジェクトはメソッドを提供し、 <xref:System.Drawing.Graphics.DrawPath%2A> <xref:System.Drawing.Pen> オブジェクトはパスを表示するために使用される線の属性 (幅や色など) を格納します。</span><span class="sxs-lookup"><span data-stu-id="2ea31-123">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawPath%2A> method, and the <xref:System.Drawing.Pen> object stores attributes, such as width and color, of the line used to render the path.</span></span> <span data-ttu-id="2ea31-124">オブジェクトは、 <xref:System.Drawing.Drawing2D.GraphicsPath> パスを構成する直線と曲線のシーケンスを格納します。</span><span class="sxs-lookup"><span data-stu-id="2ea31-124">The <xref:System.Drawing.Drawing2D.GraphicsPath> object stores the sequence of lines and curves that make up the path.</span></span> <span data-ttu-id="2ea31-125"><xref:System.Drawing.Pen>オブジェクトとオブジェクトは、 <xref:System.Drawing.Drawing2D.GraphicsPath> 引数としてメソッドに渡され <xref:System.Drawing.Graphics.DrawPath%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="2ea31-125">The <xref:System.Drawing.Pen> object and the <xref:System.Drawing.Drawing2D.GraphicsPath> object are passed as arguments to the <xref:System.Drawing.Graphics.DrawPath%2A> method.</span></span> <span data-ttu-id="2ea31-126">次の例では、直線、楕円、およびベジエスプラインで構成されるパスを描画します。</span><span class="sxs-lookup"><span data-stu-id="2ea31-126">The following example draws a path that consists of a line, an ellipse, and a Bézier spline:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#101](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#101)]
 [!code-vb[LinesCurvesAndShapes#101](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#101)]  
  
 <span data-ttu-id="2ea31-127">パスを次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="2ea31-127">The following illustration shows the path.</span></span>  
  
 <span data-ttu-id="2ea31-128">![パス](./media/aboutgdip02-art15.gif "Aboutgdip02_art15")</span><span class="sxs-lookup"><span data-stu-id="2ea31-128">![Path](./media/aboutgdip02-art15.gif "Aboutgdip02_art15")</span></span>  
  
 <span data-ttu-id="2ea31-129">パスに線、四角形、曲線を追加するだけでなく、パスをパスに追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="2ea31-129">In addition to adding lines, rectangles, and curves to a path, you can add paths to a path.</span></span> <span data-ttu-id="2ea31-130">これにより、既存のパスを組み合わせて、大規模で複雑なパスを形成することができます。</span><span class="sxs-lookup"><span data-stu-id="2ea31-130">This allows you to combine existing paths to form large, complex paths.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#102](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#102)]
 [!code-vb[LinesCurvesAndShapes#102](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#102)]  
  
 <span data-ttu-id="2ea31-131">パスには、文字列とパイという2つの項目を追加できます。</span><span class="sxs-lookup"><span data-stu-id="2ea31-131">There are two other items you can add to a path: strings and pies.</span></span> <span data-ttu-id="2ea31-132">円は、楕円の内部の一部です。</span><span class="sxs-lookup"><span data-stu-id="2ea31-132">A pie is a portion of the interior of an ellipse.</span></span> <span data-ttu-id="2ea31-133">次の例では、弧、カーディナルスプライン、文字列、および円からパスを作成します。</span><span class="sxs-lookup"><span data-stu-id="2ea31-133">The following example creates a path from an arc, a cardinal spline, a string, and a pie:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#103](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#103)]
 [!code-vb[LinesCurvesAndShapes#103](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#103)]  
  
 <span data-ttu-id="2ea31-134">パスを次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="2ea31-134">The following illustration shows the path.</span></span> <span data-ttu-id="2ea31-135">パスは接続する必要がないことに注意してください。円弧、カーディナルスプライン、文字列、および円が分離されます。</span><span class="sxs-lookup"><span data-stu-id="2ea31-135">Note that a path does not have to be connected; the arc, cardinal spline, string, and pie are separated.</span></span>  
  
 <span data-ttu-id="2ea31-136">![パス](./media/aboutgdip02-art16.gif "Aboutgdip02_Art16")</span><span class="sxs-lookup"><span data-stu-id="2ea31-136">![Paths](./media/aboutgdip02-art16.gif "Aboutgdip02_Art16")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ea31-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ea31-137">See also</span></span>

- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- <xref:System.Drawing.Point?displayProperty=nameWithType>
- [<span data-ttu-id="2ea31-138">直線、曲線、および図形</span><span class="sxs-lookup"><span data-stu-id="2ea31-138">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="2ea31-139">方法: 描画する Graphics オブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="2ea31-139">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="2ea31-140">パスの作成および描画</span><span class="sxs-lookup"><span data-stu-id="2ea31-140">Constructing and Drawing Paths</span></span>](constructing-and-drawing-paths.md)
