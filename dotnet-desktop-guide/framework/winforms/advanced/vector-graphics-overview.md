---
title: ベクター グラフィックスの概要
ms.date: 03/30/2017
ms.topic: overview
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inclusive-inclusive endpoints
- coordinate systems
- graphics [Windows Forms], vector graphics
ms.assetid: 0195df81-66be-452d-bb53-5a582ebfdc09
ms.openlocfilehash: 6f405f5ffc67a0cdb13fe83f4dd36b70769a4cd9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981176"
---
# <a name="vector-graphics-overview"></a><span data-ttu-id="f9271-102">ベクター グラフィックスの概要</span><span class="sxs-lookup"><span data-stu-id="f9271-102">Vector Graphics Overview</span></span>
<span data-ttu-id="f9271-103">GDI + 座標系に線、四角形、およびその他の図形を描画します。</span><span class="sxs-lookup"><span data-stu-id="f9271-103">GDI+ draws lines, rectangles, and other shapes on a coordinate system.</span></span> <span data-ttu-id="f9271-104">さまざまな座標系から選択することができますが、既定の座標系では、左上隅に原点があり、x 軸は右を指し、y 軸は下向きになっています。</span><span class="sxs-lookup"><span data-stu-id="f9271-104">You can choose from a variety of coordinate systems, but the default coordinate system has the origin in the upper-left corner with the x-axis pointing to the right and the y-axis pointing down.</span></span> <span data-ttu-id="f9271-105">既定の座標系の測定単位はピクセルです。</span><span class="sxs-lookup"><span data-stu-id="f9271-105">The unit of measure in the default coordinate system is the pixel.</span></span>  
  
## <a name="the-building-blocks-of-gdi"></a><span data-ttu-id="f9271-106">GDI + の構成要素</span><span class="sxs-lookup"><span data-stu-id="f9271-106">The Building Blocks of GDI+</span></span>  
 <span data-ttu-id="f9271-107">![ベクター グラフィックス](./media/aboutgdip02-art01.gif "AboutGdip02_Art01")</span><span class="sxs-lookup"><span data-stu-id="f9271-107">![Vector graphic](./media/aboutgdip02-art01.gif "AboutGdip02_Art01")</span></span>  
  
 <span data-ttu-id="f9271-108">コンピューターモニターは、ピクチャ要素またはピクセルと呼ばれる四角形のドットの配列に表示を作成します。</span><span class="sxs-lookup"><span data-stu-id="f9271-108">A computer monitor creates its display on a rectangular array of dots called picture elements or pixels.</span></span> <span data-ttu-id="f9271-109">画面に表示されるピクセルの数は、モニターごとに異なります。また、個々のモニターに表示されるピクセルの数は、通常、ユーザーが一定の範囲で構成できます。</span><span class="sxs-lookup"><span data-stu-id="f9271-109">The number of pixels that appear on the screen varies from one monitor to the next, and the number of pixels that appear on an individual monitor can usually be configured to some extent by the user.</span></span>  
  
 <span data-ttu-id="f9271-110">![ベクター グラフィックス](./media/aboutgdip02-art02.gif "AboutGdip02_Art02")</span><span class="sxs-lookup"><span data-stu-id="f9271-110">![Vector graphic](./media/aboutgdip02-art02.gif "AboutGdip02_Art02")</span></span>  
  
 <span data-ttu-id="f9271-111">GDI + を使用して線、四角形、または曲線を描画する場合は、描画される項目に関する特定のキー情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="f9271-111">When you use GDI+ to draw a line, rectangle, or curve, you provide certain key information about the item to be drawn.</span></span> <span data-ttu-id="f9271-112">たとえば、2つの点を提供して線を指定したり、ポイント、高さ、および幅を指定して四角形を指定したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="f9271-112">For example, you can specify a line by providing two points, and you can specify a rectangle by providing a point, a height, and a width.</span></span> <span data-ttu-id="f9271-113">GDI + は、ディスプレイドライバーソフトウェアと連携して、線、四角形、または曲線を表示するためにオンにする必要があるピクセルを判別します。</span><span class="sxs-lookup"><span data-stu-id="f9271-113">GDI+ works in conjunction with the display driver software to determine which pixels must be turned on to show the line, rectangle, or curve.</span></span> <span data-ttu-id="f9271-114">次の図は、ポイント (4, 2) からポイント (12, 8) までの線を表示するためにオンになっているピクセルを示しています。</span><span class="sxs-lookup"><span data-stu-id="f9271-114">The following illustration shows the pixels that are turned on to display a line from the point (4, 2) to the point (12, 8).</span></span>  
  
 <span data-ttu-id="f9271-115">![ベクター グラフィックス](./media/aboutgdip02-art03.gif "AboutGdip02_Art03")</span><span class="sxs-lookup"><span data-stu-id="f9271-115">![Vector graphic](./media/aboutgdip02-art03.gif "AboutGdip02_Art03")</span></span>  
  
 <span data-ttu-id="f9271-116">時間の経過と共に、いくつかの基本的な構成要素は、2次元の画像を作成するのに最も役に立つことが実証されています。</span><span class="sxs-lookup"><span data-stu-id="f9271-116">Over time, certain basic building blocks have proven to be the most useful for creating two-dimensional pictures.</span></span> <span data-ttu-id="f9271-117">GDI + でサポートされているこれらの構成要素は、次の一覧に示されています。</span><span class="sxs-lookup"><span data-stu-id="f9271-117">These building blocks, which are all supported by GDI+, are given in the following list:</span></span>  
  
- <span data-ttu-id="f9271-118">路線</span><span class="sxs-lookup"><span data-stu-id="f9271-118">Lines</span></span>  
  
- <span data-ttu-id="f9271-119">四角形</span><span class="sxs-lookup"><span data-stu-id="f9271-119">Rectangles</span></span>  
  
- <span data-ttu-id="f9271-120">楕円</span><span class="sxs-lookup"><span data-stu-id="f9271-120">Ellipses</span></span>  
  
- <span data-ttu-id="f9271-121">アーク</span><span class="sxs-lookup"><span data-stu-id="f9271-121">Arcs</span></span>  
  
- <span data-ttu-id="f9271-122">多角形</span><span class="sxs-lookup"><span data-stu-id="f9271-122">Polygons</span></span>  
  
- <span data-ttu-id="f9271-123">カーディナルスプライン</span><span class="sxs-lookup"><span data-stu-id="f9271-123">Cardinal splines</span></span>  
  
- <span data-ttu-id="f9271-124">ベジエ スプライン</span><span class="sxs-lookup"><span data-stu-id="f9271-124">Bezier splines</span></span>  
  
## <a name="methods-for-drawing-with-a-graphics-object"></a><span data-ttu-id="f9271-125">グラフィックスオブジェクトを使用して描画するためのメソッド</span><span class="sxs-lookup"><span data-stu-id="f9271-125">Methods For Drawing with a Graphics Object</span></span>  
 <span data-ttu-id="f9271-126"><xref:System.Drawing.Graphics>Gdi + のクラスは、、、 <xref:System.Drawing.Graphics.DrawLine%2A> <xref:System.Drawing.Graphics.DrawRectangle%2A> 、、 <xref:System.Drawing.Graphics.DrawEllipse%2A> <xref:System.Drawing.Graphics.DrawPolygon%2A> <xref:System.Drawing.Graphics.DrawArc%2A> 、 <xref:System.Drawing.Graphics.DrawCurve%2A> (カーディナルスプラインの場合)、および <xref:System.Drawing.Graphics.DrawBezier%2A> の各項目を描画するための次のメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="f9271-126">The <xref:System.Drawing.Graphics> class in GDI+ provides the following methods for drawing the items in the previous list: <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawRectangle%2A>, <xref:System.Drawing.Graphics.DrawEllipse%2A>, <xref:System.Drawing.Graphics.DrawPolygon%2A>, <xref:System.Drawing.Graphics.DrawArc%2A>, <xref:System.Drawing.Graphics.DrawCurve%2A> (for cardinal splines), and <xref:System.Drawing.Graphics.DrawBezier%2A>.</span></span> <span data-ttu-id="f9271-127">これらのメソッドはそれぞれオーバーロードされます。つまり、各メソッドはいくつかの異なるパラメーターリストをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="f9271-127">Each of these methods is overloaded; that is, each method supports several different parameter lists.</span></span> <span data-ttu-id="f9271-128">たとえば、メソッドの1つのバリエーションが <xref:System.Drawing.Graphics.DrawLine%2A> <xref:System.Drawing.Pen> オブジェクトと4つの整数を受け取り、メソッドの別のバリエーションが <xref:System.Drawing.Graphics.DrawLine%2A> <xref:System.Drawing.Pen> オブジェクトと2つのオブジェクトを受け取り <xref:System.Drawing.Point> ます。</span><span class="sxs-lookup"><span data-stu-id="f9271-128">For example, one variation of the <xref:System.Drawing.Graphics.DrawLine%2A> method receives a <xref:System.Drawing.Pen> object and four integers, while another variation of the <xref:System.Drawing.Graphics.DrawLine%2A> method receives a <xref:System.Drawing.Pen> object and two <xref:System.Drawing.Point> objects.</span></span>  
  
 <span data-ttu-id="f9271-129">線、四角形、およびベジエスプラインを描画するためのメソッドには、1回の呼び出しで複数の項目を描画する複数の関連メソッドがあります。 <xref:System.Drawing.Graphics.DrawLines%2A> 、、 <xref:System.Drawing.Graphics.DrawRectangles%2A> および <xref:System.Drawing.Graphics.DrawBeziers%2A> です。</span><span class="sxs-lookup"><span data-stu-id="f9271-129">The methods for drawing lines, rectangles, and Bézier splines have plural companion methods that draw several items in a single call: <xref:System.Drawing.Graphics.DrawLines%2A>, <xref:System.Drawing.Graphics.DrawRectangles%2A>, and <xref:System.Drawing.Graphics.DrawBeziers%2A>.</span></span> <span data-ttu-id="f9271-130">また、この <xref:System.Drawing.Graphics.DrawCurve%2A> メソッドには、 <xref:System.Drawing.Graphics.DrawClosedCurve%2A> 曲線の終了点を開始点に接続することによって曲線を閉じる、関連するメソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="f9271-130">Also, the <xref:System.Drawing.Graphics.DrawCurve%2A> method has a companion method, <xref:System.Drawing.Graphics.DrawClosedCurve%2A>, that closes a curve by connecting the ending point of the curve to the starting point.</span></span>  
  
 <span data-ttu-id="f9271-131">クラスのすべての描画メソッドは、 <xref:System.Drawing.Graphics> オブジェクトと連携して動作 <xref:System.Drawing.Pen> します。</span><span class="sxs-lookup"><span data-stu-id="f9271-131">All of the drawing methods of the <xref:System.Drawing.Graphics> class work in conjunction with a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="f9271-132">任意のオブジェクトを描画するには、オブジェクトとオブジェクトの2つ以上のオブジェクトを作成する必要があり <xref:System.Drawing.Graphics> <xref:System.Drawing.Pen> ます。</span><span class="sxs-lookup"><span data-stu-id="f9271-132">To draw anything, you must create at least two objects: a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="f9271-133">オブジェクトは、 <xref:System.Drawing.Pen> 描画される項目の線の幅や色などの属性を格納します。</span><span class="sxs-lookup"><span data-stu-id="f9271-133">The <xref:System.Drawing.Pen> object stores attributes, such as line width and color, of the item to be drawn.</span></span> <span data-ttu-id="f9271-134"><xref:System.Drawing.Pen>オブジェクトは、引数の1つとして描画メソッドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="f9271-134">The <xref:System.Drawing.Pen> object is passed as one of the arguments to the drawing method.</span></span> <span data-ttu-id="f9271-135">たとえば、次の例に示すように、メソッドの1つのバリエーションでは、 <xref:System.Drawing.Graphics.DrawLine%2A> <xref:System.Drawing.Pen> オブジェクトと4つの整数を受け取ります。この例では、幅100、高さ50、およびの左上隅 (20, 10) の四角形を描画します。</span><span class="sxs-lookup"><span data-stu-id="f9271-135">For example, one variation of the <xref:System.Drawing.Graphics.DrawLine%2A> method receives a <xref:System.Drawing.Pen> object and four integers as shown in the following example, which draws a rectangle with a width of 100, a height of 50 and an upper-left corner of (20, 10):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#11](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#11)]
 [!code-vb[LinesCurvesAndShapes#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="f9271-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="f9271-136">See also</span></span>

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [<span data-ttu-id="f9271-137">直線、曲線、および図形</span><span class="sxs-lookup"><span data-stu-id="f9271-137">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="f9271-138">方法: 描画する Graphics オブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="f9271-138">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
