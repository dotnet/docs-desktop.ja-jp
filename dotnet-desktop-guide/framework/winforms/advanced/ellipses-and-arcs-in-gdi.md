---
title: GDI+ での楕円および円弧
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- arcs
- GDI+, arcs
- drawing [Windows Forms], ellipses
- GDI+, ellipses
- ellipses
- drawing [Windows Forms], arcs
ms.assetid: 34f35133-a835-4ca4-81f6-0dfedee8b683
ms.openlocfilehash: 8bbc2eda6450128eac55576259880e83f07099ab
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96979801"
---
# <a name="ellipses-and-arcs-in-gdi"></a><span data-ttu-id="de4b3-102">GDI+ での楕円および円弧</span><span class="sxs-lookup"><span data-stu-id="de4b3-102">Ellipses and Arcs in GDI+</span></span>
<span data-ttu-id="de4b3-103"><xref:System.Drawing.Graphics.DrawEllipse%2A>クラスのメソッドとメソッドを使用して、省略記号と円弧を簡単に描画でき <xref:System.Drawing.Graphics.DrawArc%2A> <xref:System.Drawing.Graphics> ます。</span><span class="sxs-lookup"><span data-stu-id="de4b3-103">You can easily draw ellipses and arcs using the <xref:System.Drawing.Graphics.DrawEllipse%2A> and <xref:System.Drawing.Graphics.DrawArc%2A> methods of the <xref:System.Drawing.Graphics> class.</span></span>  
  
## <a name="drawing-an-ellipse"></a><span data-ttu-id="de4b3-104">楕円の描画</span><span class="sxs-lookup"><span data-stu-id="de4b3-104">Drawing an Ellipse</span></span>  
 <span data-ttu-id="de4b3-105">楕円を描画するには、 <xref:System.Drawing.Graphics> オブジェクトとオブジェクトが必要 <xref:System.Drawing.Pen> です。</span><span class="sxs-lookup"><span data-stu-id="de4b3-105">To draw an ellipse, you need a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="de4b3-106"><xref:System.Drawing.Graphics>オブジェクトはメソッドを提供し、 <xref:System.Drawing.Graphics.DrawEllipse%2A> オブジェクトは、楕円の <xref:System.Drawing.Pen> 描画に使用される線の幅や色などの属性を格納します。</span><span class="sxs-lookup"><span data-stu-id="de4b3-106">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawEllipse%2A> method, and the <xref:System.Drawing.Pen> object stores attributes, such as width and color, of the line used to render the ellipse.</span></span> <span data-ttu-id="de4b3-107"><xref:System.Drawing.Pen>オブジェクトは、引数の1つとしてメソッドに渡され <xref:System.Drawing.Graphics.DrawEllipse%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="de4b3-107">The <xref:System.Drawing.Pen> object is passed as one of the arguments to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method.</span></span> <span data-ttu-id="de4b3-108">メソッドに渡される残りの引数は、 <xref:System.Drawing.Graphics.DrawEllipse%2A> 楕円の外接する四角形を指定します。</span><span class="sxs-lookup"><span data-stu-id="de4b3-108">The remaining arguments passed to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method specify the bounding rectangle for the ellipse.</span></span> <span data-ttu-id="de4b3-109">次の図は、外接する四角形と共に楕円を示しています。</span><span class="sxs-lookup"><span data-stu-id="de4b3-109">The following illustration shows an ellipse along with its bounding rectangle.</span></span>  
  
 <span data-ttu-id="de4b3-110">![省略記号と円弧](./media/aboutgdip02-art05.gif "Aboutgdip02_art05")</span><span class="sxs-lookup"><span data-stu-id="de4b3-110">![Ellipses and arcs](./media/aboutgdip02-art05.gif "Aboutgdip02_art05")</span></span>  
  
 <span data-ttu-id="de4b3-111">楕円を描画する例を次に示します。外接する四角形の幅は80、高さは40、の左上隅 (100、50) です。</span><span class="sxs-lookup"><span data-stu-id="de4b3-111">The following example draws an ellipse; the bounding rectangle has a width of 80, a height of 40, and an upper-left corner of (100, 50):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#51](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#51)]
 [!code-vb[LinesCurvesAndShapes#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#51)]  
  
 <span data-ttu-id="de4b3-112"><xref:System.Drawing.Graphics.DrawEllipse%2A> はクラスのオーバーロードされたメソッドである <xref:System.Drawing.Graphics> ため、複数の方法で引数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="de4b3-112"><xref:System.Drawing.Graphics.DrawEllipse%2A> is an overloaded method of the <xref:System.Drawing.Graphics> class, so there are several ways you can supply it with arguments.</span></span> <span data-ttu-id="de4b3-113">たとえば、を構築し、を <xref:System.Drawing.Rectangle> <xref:System.Drawing.Rectangle> <xref:System.Drawing.Graphics.DrawEllipse%2A> 引数としてメソッドに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="de4b3-113">For example, you can construct a <xref:System.Drawing.Rectangle> and pass the <xref:System.Drawing.Rectangle> to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method as an argument:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#52](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#52)]
 [!code-vb[LinesCurvesAndShapes#52](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#52)]  
  
## <a name="drawing-an-arc"></a><span data-ttu-id="de4b3-114">円弧の描画</span><span class="sxs-lookup"><span data-stu-id="de4b3-114">Drawing an Arc</span></span>  
 <span data-ttu-id="de4b3-115">弧は、楕円の一部です。</span><span class="sxs-lookup"><span data-stu-id="de4b3-115">An arc is a portion of an ellipse.</span></span> <span data-ttu-id="de4b3-116">円弧を描画するには、 <xref:System.Drawing.Graphics.DrawArc%2A> クラスのメソッドを呼び出し <xref:System.Drawing.Graphics> ます。</span><span class="sxs-lookup"><span data-stu-id="de4b3-116">To draw an arc, you call the <xref:System.Drawing.Graphics.DrawArc%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="de4b3-117">メソッドのパラメーターは、 <xref:System.Drawing.Graphics.DrawArc%2A> <xref:System.Drawing.Graphics.DrawEllipse%2A> <xref:System.Drawing.Graphics.DrawArc%2A> 開始角度とスイープ角度を必要とする点を除いて、メソッドのパラメーターと同じです。</span><span class="sxs-lookup"><span data-stu-id="de4b3-117">The parameters of the <xref:System.Drawing.Graphics.DrawArc%2A> method are the same as the parameters of the <xref:System.Drawing.Graphics.DrawEllipse%2A> method, except that <xref:System.Drawing.Graphics.DrawArc%2A> requires a starting angle and sweep angle.</span></span> <span data-ttu-id="de4b3-118">次の例では、開始角度が30°で、スイープ角度が180度の円弧を描画します。</span><span class="sxs-lookup"><span data-stu-id="de4b3-118">The following example draws an arc with a starting angle of 30 degrees and a sweep angle of 180 degrees:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#53](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#53)]
 [!code-vb[LinesCurvesAndShapes#53](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#53)]  
  
 <span data-ttu-id="de4b3-119">次の図は、円弧、楕円、および外接する四角形を示しています。</span><span class="sxs-lookup"><span data-stu-id="de4b3-119">The following illustration shows the arc, the ellipse, and the bounding rectangle.</span></span>  
  
 <span data-ttu-id="de4b3-120">![省略記号と円弧](./media/aboutgdip02-art06.gif "Aboutgdip02_art06")</span><span class="sxs-lookup"><span data-stu-id="de4b3-120">![Ellipses and arcs](./media/aboutgdip02-art06.gif "Aboutgdip02_art06")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de4b3-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="de4b3-121">See also</span></span>

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [<span data-ttu-id="de4b3-122">直線、曲線、および図形</span><span class="sxs-lookup"><span data-stu-id="de4b3-122">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="de4b3-123">方法: 描画する Graphics オブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="de4b3-123">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="de4b3-124">方法: ペンを作成する</span><span class="sxs-lookup"><span data-stu-id="de4b3-124">How to: Create a Pen</span></span>](how-to-create-a-pen.md)
- [<span data-ttu-id="de4b3-125">方法: 形状のアウトラインを描画する</span><span class="sxs-lookup"><span data-stu-id="de4b3-125">How to: Draw an Outlined Shape</span></span>](how-to-draw-an-outlined-shape.md)
