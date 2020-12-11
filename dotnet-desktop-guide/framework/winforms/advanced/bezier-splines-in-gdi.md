---
title: B GDI + でのベジエスプラインの&#233;
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Bezier splines
- splines [Windows Forms], Bezier
- GDI+, Bezier splines
ms.assetid: 5774ce1e-87d4-4bc7-88c4-4862052781b8
ms.openlocfilehash: ff4e9eb18610b70c88e057d3d44020321bbb9f4f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974460"
---
# <a name="b233zier-splines-in-gdi"></a><span data-ttu-id="328e8-102">B GDI + でのベジエスプラインの&#233;</span><span class="sxs-lookup"><span data-stu-id="328e8-102">B&#233;zier Splines in GDI+</span></span>
<span data-ttu-id="328e8-103">ベジエスプラインは、2つのエンドポイント (p1 および p2) と2つの制御点 (c1 および c2) で指定された曲線です。</span><span class="sxs-lookup"><span data-stu-id="328e8-103">A Bézier spline is a curve specified by four points: two end points (p1 and p2) and two control points (c1 and c2).</span></span> <span data-ttu-id="328e8-104">曲線は p1 で始まり、p2 で終了します。</span><span class="sxs-lookup"><span data-stu-id="328e8-104">The curve begins at p1 and ends at p2.</span></span> <span data-ttu-id="328e8-105">曲線は制御点を通過しませんが、コントロールポイントは磁石として機能し、特定の方向に曲線を引き出し、曲線の曲がり方に影響を与えることになります。</span><span class="sxs-lookup"><span data-stu-id="328e8-105">The curve does not pass through the control points, but the control points act as magnets, pulling the curve in certain directions and influencing the way the curve bends.</span></span> <span data-ttu-id="328e8-106">次の図は、ベジエ曲線とそのエンドポイントおよびコントロールポイントを示しています。</span><span class="sxs-lookup"><span data-stu-id="328e8-106">The following illustration shows a Bézier curve along with its endpoints and control points.</span></span>  
  
 <span data-ttu-id="328e8-107">![ベジエスプライン](./media/aboutgdip02-art11a.gif "Aboutgdip02_art11a")</span><span class="sxs-lookup"><span data-stu-id="328e8-107">![Bezier Splines](./media/aboutgdip02-art11a.gif "Aboutgdip02_art11a")</span></span>  
  
 <span data-ttu-id="328e8-108">この曲線は p1 で開始され、コントロールポイント c1 に移動します。</span><span class="sxs-lookup"><span data-stu-id="328e8-108">The curve starts at p1 and moves toward the control point c1.</span></span> <span data-ttu-id="328e8-109">P1 の曲線の接線は、p1 から c1 に描画される直線です。</span><span class="sxs-lookup"><span data-stu-id="328e8-109">The tangent line to the curve at p1 is the line drawn from p1 to c1.</span></span> <span data-ttu-id="328e8-110">エンドポイント p2 の接線は、c2 から p2 の線です。</span><span class="sxs-lookup"><span data-stu-id="328e8-110">The tangent line at the endpoint p2 is the line drawn from c2 to p2.</span></span>  
  
## <a name="drawing-bzier-splines"></a><span data-ttu-id="328e8-111">ベジエスプラインの描画</span><span class="sxs-lookup"><span data-stu-id="328e8-111">Drawing Bézier Splines</span></span>  
 <span data-ttu-id="328e8-112">ベジエスプラインを描画するには、クラスのインスタンスとが必要 <xref:System.Drawing.Graphics> <xref:System.Drawing.Pen> です。</span><span class="sxs-lookup"><span data-stu-id="328e8-112">To draw a Bézier spline, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Pen>.</span></span> <span data-ttu-id="328e8-113">クラスのインスタンスは <xref:System.Drawing.Graphics> メソッドを提供 <xref:System.Drawing.Graphics.DrawBezier%2A> し、は <xref:System.Drawing.Pen> 曲線の描画に使用される線の属性 (幅や色など) を格納します。</span><span class="sxs-lookup"><span data-stu-id="328e8-113">The instance of the <xref:System.Drawing.Graphics> class provides the <xref:System.Drawing.Graphics.DrawBezier%2A> method, and the <xref:System.Drawing.Pen> stores attributes, such as width and color, of the line used to render the curve.</span></span> <span data-ttu-id="328e8-114">は、 <xref:System.Drawing.Pen> 引数の1つとしてメソッドに渡され <xref:System.Drawing.Graphics.DrawBezier%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="328e8-114">The <xref:System.Drawing.Pen> is passed as one of the arguments to the <xref:System.Drawing.Graphics.DrawBezier%2A> method.</span></span> <span data-ttu-id="328e8-115">メソッドに渡される残りの引数 <xref:System.Drawing.Graphics.DrawBezier%2A> は、エンドポイントとコントロールポイントです。</span><span class="sxs-lookup"><span data-stu-id="328e8-115">The remaining arguments passed to the <xref:System.Drawing.Graphics.DrawBezier%2A> method are the endpoints and the control points.</span></span> <span data-ttu-id="328e8-116">次の例では、開始点 (0, 0)、制御点 (40、20 150 80)、および終了点 (100、10) を使用してベジエスプラインを描画します。</span><span class="sxs-lookup"><span data-stu-id="328e8-116">The following example draws a Bézier spline with starting point (0, 0), control points (40, 20) and (80, 150), and ending point (100, 10):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#71](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#71)]
 [!code-vb[LinesCurvesAndShapes#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#71)]  
  
 <span data-ttu-id="328e8-117">次の図は、曲線、コントロールポイント、および2つの接線を示しています。</span><span class="sxs-lookup"><span data-stu-id="328e8-117">The following illustration shows the curve, the control points, and two tangent lines.</span></span>  
  
 <span data-ttu-id="328e8-118">![ベジエスプライン](./media/aboutgdip02-art12.gif "Aboutgdip02_art12")</span><span class="sxs-lookup"><span data-stu-id="328e8-118">![Bezier Splines](./media/aboutgdip02-art12.gif "Aboutgdip02_art12")</span></span>  
  
 <span data-ttu-id="328e8-119">ベジエスプラインは、もともと、自動車業界で設計されたピエールベジェによって開発されました。</span><span class="sxs-lookup"><span data-stu-id="328e8-119">Bézier splines were originally developed by Pierre Bézier for design in the automotive industry.</span></span> <span data-ttu-id="328e8-120">これらは、多くの種類のコンピューター支援設計で役立つことが実証されたため、フォントのアウトラインを定義するためにも使用されています。</span><span class="sxs-lookup"><span data-stu-id="328e8-120">They have since proven to be useful in many types of computer-aided design and are also used to define the outlines of fonts.</span></span> <span data-ttu-id="328e8-121">ベジエスプラインは、次の図に示すように、さまざまな図形を生成することができます。</span><span class="sxs-lookup"><span data-stu-id="328e8-121">Bézier splines can yield a wide variety of shapes, some of which are shown in the following illustration.</span></span>  
  
 <span data-ttu-id="328e8-122">![パス](./media/aboutgdip02-art13.gif "Aboutgdip02_art13")</span><span class="sxs-lookup"><span data-stu-id="328e8-122">![Paths](./media/aboutgdip02-art13.gif "Aboutgdip02_art13")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="328e8-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="328e8-123">See also</span></span>

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [<span data-ttu-id="328e8-124">直線、曲線、および図形</span><span class="sxs-lookup"><span data-stu-id="328e8-124">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="328e8-125">曲線の作成と描画</span><span class="sxs-lookup"><span data-stu-id="328e8-125">Constructing and Drawing Curves</span></span>](constructing-and-drawing-curves.md)
- [<span data-ttu-id="328e8-126">方法: 描画する Graphics オブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="328e8-126">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="328e8-127">方法: ペンを作成する</span><span class="sxs-lookup"><span data-stu-id="328e8-127">How to: Create a Pen</span></span>](how-to-create-a-pen.md)
