---
title: GDI+ でのペン、直線、および四角形
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines
- GDI+, lines
- drawing [Windows Forms], rectangles
- rectangles
- drawing [Windows Forms], lines
- GDI+, pens
- examples [Windows Forms], drawing lines and shapes
- examples [Windows Forms], pens
- GDI+, rectangles
- examples [Windows Forms], GDI+
- lines [Windows Forms], dashed
ms.assetid: 30b25aae-e3eb-4479-bdb8-187cf651fc84
ms.openlocfilehash: 06d2351ffa7d7f009d7b049f4689df7038b4d202
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981660"
---
# <a name="pens-lines-and-rectangles-in-gdi"></a><span data-ttu-id="99f50-102">GDI+ でのペン、直線、および四角形</span><span class="sxs-lookup"><span data-stu-id="99f50-102">Pens, Lines, and Rectangles in GDI+</span></span>
<span data-ttu-id="99f50-103">GDI + を使用して線を描画するには、オブジェクトとオブジェクトを作成する必要があり <xref:System.Drawing.Graphics> <xref:System.Drawing.Pen> ます。</span><span class="sxs-lookup"><span data-stu-id="99f50-103">To draw lines with GDI+ you need to create a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="99f50-104">オブジェクトは、 <xref:System.Drawing.Graphics> 実際に描画を行うメソッドを提供し、 <xref:System.Drawing.Pen> オブジェクトは、線の色、幅、スタイルなどの属性を格納します。</span><span class="sxs-lookup"><span data-stu-id="99f50-104">The <xref:System.Drawing.Graphics> object provides the methods that actually do the drawing, and the <xref:System.Drawing.Pen> object stores attributes, such as line color, width, and style.</span></span>  
  
## <a name="drawing-a-line"></a><span data-ttu-id="99f50-105">直線の描画</span><span class="sxs-lookup"><span data-stu-id="99f50-105">Drawing a Line</span></span>  
 <span data-ttu-id="99f50-106">線を描画するには、 <xref:System.Drawing.Graphics.DrawLine%2A> オブジェクトのメソッドを呼び出し <xref:System.Drawing.Graphics> ます。</span><span class="sxs-lookup"><span data-stu-id="99f50-106">To draw a line, call the <xref:System.Drawing.Graphics.DrawLine%2A> method of the <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="99f50-107"><xref:System.Drawing.Pen>オブジェクトは、引数の1つとしてメソッドに渡され <xref:System.Drawing.Graphics.DrawLine%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="99f50-107">The <xref:System.Drawing.Pen> object is passed as one of the arguments to the <xref:System.Drawing.Graphics.DrawLine%2A> method.</span></span> <span data-ttu-id="99f50-108">次の例では、点 (4, 2) から点 (12、6) までの線を描画します。</span><span class="sxs-lookup"><span data-stu-id="99f50-108">The following example draws a line from the point (4, 2) to the point (12, 6):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#41](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#41)]
 [!code-vb[LinesCurvesAndShapes#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#41)]  
  
 <span data-ttu-id="99f50-109"><xref:System.Drawing.Graphics.DrawLine%2A> はクラスのオーバーロードされたメソッドである <xref:System.Drawing.Graphics> ため、複数の方法で引数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="99f50-109"><xref:System.Drawing.Graphics.DrawLine%2A> is an overloaded method of the <xref:System.Drawing.Graphics> class, so there are several ways you can supply it with arguments.</span></span> <span data-ttu-id="99f50-110">たとえば、2つのオブジェクトを作成 <xref:System.Drawing.Point> し、その <xref:System.Drawing.Point> オブジェクトを引数としてメソッドに渡すことができ <xref:System.Drawing.Graphics.DrawLine%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="99f50-110">For example, you can construct two <xref:System.Drawing.Point> objects and pass the <xref:System.Drawing.Point> objects as arguments to the <xref:System.Drawing.Graphics.DrawLine%2A> method:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#42](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#42)]
 [!code-vb[LinesCurvesAndShapes#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#42)]  
  
## <a name="constructing-a-pen"></a><span data-ttu-id="99f50-111">ペンの構築</span><span class="sxs-lookup"><span data-stu-id="99f50-111">Constructing a Pen</span></span>  
 <span data-ttu-id="99f50-112">オブジェクトを構築するときに、特定の属性を指定でき <xref:System.Drawing.Pen> ます。</span><span class="sxs-lookup"><span data-stu-id="99f50-112">You can specify certain attributes when you construct a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="99f50-113">たとえば、1つの `Pen` コンストラクターで色と幅を指定できます。</span><span class="sxs-lookup"><span data-stu-id="99f50-113">For example, one `Pen` constructor allows you to specify color and width.</span></span> <span data-ttu-id="99f50-114">次の例では、幅2の青い線を (0, 0) から (60, 30) に描画します。</span><span class="sxs-lookup"><span data-stu-id="99f50-114">The following example draws a blue line of width 2 from (0, 0) to (60, 30):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#43](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#43)]
 [!code-vb[LinesCurvesAndShapes#43](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#43)]  
  
## <a name="dashed-lines-and-line-caps"></a><span data-ttu-id="99f50-115">破線と線のキャップ</span><span class="sxs-lookup"><span data-stu-id="99f50-115">Dashed Lines and Line Caps</span></span>  
 <span data-ttu-id="99f50-116">オブジェクトは、など <xref:System.Drawing.Pen> のプロパティも公開します。このプロパティを使用して、 <xref:System.Drawing.Pen.DashStyle%2A> 線の機能を指定できます。</span><span class="sxs-lookup"><span data-stu-id="99f50-116">The <xref:System.Drawing.Pen> object also exposes properties, such as <xref:System.Drawing.Pen.DashStyle%2A>, that you can use to specify features of the line.</span></span> <span data-ttu-id="99f50-117">次の例では、(100, 50) から (300, 80) の破線を描画します。</span><span class="sxs-lookup"><span data-stu-id="99f50-117">The following example draws a dashed line from (100, 50) to (300, 80):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#44](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#44)]
 [!code-vb[LinesCurvesAndShapes#44](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#44)]  
  
 <span data-ttu-id="99f50-118">オブジェクトのプロパティを使用して、その <xref:System.Drawing.Pen> 他の多くの属性を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="99f50-118">You can use the properties of the <xref:System.Drawing.Pen> object to set many more attributes of the line.</span></span> <span data-ttu-id="99f50-119"><xref:System.Drawing.Pen.StartCap%2A>プロパティと <xref:System.Drawing.Pen.EndCap%2A> プロパティは、線の端の外観を指定します。端は、平面、正方形、丸み、三角形、またはカスタム図形にすることができます。</span><span class="sxs-lookup"><span data-stu-id="99f50-119">The <xref:System.Drawing.Pen.StartCap%2A> and <xref:System.Drawing.Pen.EndCap%2A> properties specify the appearance of the ends of the line; the ends can be flat, square, rounded, triangular, or a custom shape.</span></span> <span data-ttu-id="99f50-120"><xref:System.Drawing.Pen.LineJoin%2A>プロパティを使用すると、接続された線をマイタ (鋭い角で結合)、傾斜、丸み、またはクリップするかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="99f50-120">The <xref:System.Drawing.Pen.LineJoin%2A> property lets you specify whether connected lines are mitered (joined with sharp corners), beveled, rounded, or clipped.</span></span> <span data-ttu-id="99f50-121">次の図は、さまざまなキャップと結合スタイルを持つ線を示しています。</span><span class="sxs-lookup"><span data-stu-id="99f50-121">The following illustration shows lines with various cap and join styles.</span></span>  
  
 <span data-ttu-id="99f50-122">![路線](./media/aboutgdip02-art04.gif "Aboutgdip02_art04")</span><span class="sxs-lookup"><span data-stu-id="99f50-122">![Lines](./media/aboutgdip02-art04.gif "Aboutgdip02_art04")</span></span>  
  
## <a name="drawing-a-rectangle"></a><span data-ttu-id="99f50-123">四角形の描画</span><span class="sxs-lookup"><span data-stu-id="99f50-123">Drawing a Rectangle</span></span>  
 <span data-ttu-id="99f50-124">GDI + を使用した四角形の描画は、描画線に似ています。</span><span class="sxs-lookup"><span data-stu-id="99f50-124">Drawing rectangles with GDI+ is similar to drawing lines.</span></span> <span data-ttu-id="99f50-125">四角形を描画するには、 <xref:System.Drawing.Graphics> オブジェクトとオブジェクトが必要 <xref:System.Drawing.Pen> です。</span><span class="sxs-lookup"><span data-stu-id="99f50-125">To draw a rectangle, you need a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="99f50-126"><xref:System.Drawing.Graphics>オブジェクトはメソッドを提供 <xref:System.Drawing.Graphics.DrawRectangle%2A> し、オブジェクトは、線の <xref:System.Drawing.Pen> 幅や色などの属性を格納します。</span><span class="sxs-lookup"><span data-stu-id="99f50-126">The <xref:System.Drawing.Graphics> object provides a <xref:System.Drawing.Graphics.DrawRectangle%2A> method, and the <xref:System.Drawing.Pen> object stores attributes, such as line width and color.</span></span> <span data-ttu-id="99f50-127"><xref:System.Drawing.Pen>オブジェクトは、引数の1つとしてメソッドに渡され <xref:System.Drawing.Graphics.DrawRectangle%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="99f50-127">The <xref:System.Drawing.Pen> object is passed as one of the arguments to the <xref:System.Drawing.Graphics.DrawRectangle%2A> method.</span></span> <span data-ttu-id="99f50-128">次の例では、左上隅が (100、50)、幅が80、高さが40の四角形を描画します。</span><span class="sxs-lookup"><span data-stu-id="99f50-128">The following example draws a rectangle with its upper-left corner at (100, 50), a width of 80, and a height of 40:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#45](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#45)]
 [!code-vb[LinesCurvesAndShapes#45](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#45)]  
  
 <span data-ttu-id="99f50-129"><xref:System.Drawing.Graphics.DrawRectangle%2A> はクラスのオーバーロードされたメソッドである <xref:System.Drawing.Graphics> ため、複数の方法で引数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="99f50-129"><xref:System.Drawing.Graphics.DrawRectangle%2A> is an overloaded method of the <xref:System.Drawing.Graphics> class, so there are several ways you can supply it with arguments.</span></span> <span data-ttu-id="99f50-130">たとえば、オブジェクトを構築し、その <xref:System.Drawing.Rectangle> <xref:System.Drawing.Rectangle> オブジェクトを <xref:System.Drawing.Graphics.DrawRectangle%2A> 引数としてメソッドに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="99f50-130">For example, you can construct a <xref:System.Drawing.Rectangle> object and pass the <xref:System.Drawing.Rectangle> object to the <xref:System.Drawing.Graphics.DrawRectangle%2A> method as an argument:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#46](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#46)]
 [!code-vb[LinesCurvesAndShapes#46](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#46)]  
  
 <span data-ttu-id="99f50-131"><xref:System.Drawing.Rectangle>オブジェクトには、四角形に関する情報を操作および収集するためのメソッドとプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="99f50-131">A <xref:System.Drawing.Rectangle> object has methods and properties for manipulating and gathering information about the rectangle.</span></span> <span data-ttu-id="99f50-132">たとえば、 <xref:System.Drawing.Rectangle.Inflate%2A> メソッドとメソッドは、 <xref:System.Drawing.Rectangle.Offset%2A> 四角形のサイズと位置を変更します。</span><span class="sxs-lookup"><span data-stu-id="99f50-132">For example, the <xref:System.Drawing.Rectangle.Inflate%2A> and <xref:System.Drawing.Rectangle.Offset%2A> methods change the size and position of the rectangle.</span></span> <span data-ttu-id="99f50-133">メソッドは、 <xref:System.Drawing.Rectangle.IntersectsWith%2A> 四角形が別の指定された四角形と交差するかどうかを示し、メソッドは、 <xref:System.Drawing.Rectangle.Contains%2A> 指定された点が四角形内にあるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="99f50-133">The <xref:System.Drawing.Rectangle.IntersectsWith%2A> method tells you whether the rectangle intersects another given rectangle, and the <xref:System.Drawing.Rectangle.Contains%2A> method tells you whether a given point is inside the rectangle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99f50-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="99f50-134">See also</span></span>

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- <xref:System.Drawing.Rectangle?displayProperty=nameWithType>
- [<span data-ttu-id="99f50-135">方法: ペンを作成する</span><span class="sxs-lookup"><span data-stu-id="99f50-135">How to: Create a Pen</span></span>](how-to-create-a-pen.md)
- [<span data-ttu-id="99f50-136">方法: Windows フォームに直線を描画する</span><span class="sxs-lookup"><span data-stu-id="99f50-136">How to: Draw a Line on a Windows Form</span></span>](how-to-draw-a-line-on-a-windows-form.md)
- [<span data-ttu-id="99f50-137">方法: 形状のアウトラインを描画する</span><span class="sxs-lookup"><span data-stu-id="99f50-137">How to: Draw an Outlined Shape</span></span>](how-to-draw-an-outlined-shape.md)
