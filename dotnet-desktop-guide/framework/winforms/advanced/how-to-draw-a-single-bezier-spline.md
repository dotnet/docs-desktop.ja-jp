---
title: '方法: 1 つの B&#233;ベジエスプラインを描画する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Bezier splines [Windows Forms], drawing
- drawing [Windows Forms], Bezier splines
ms.assetid: f4f3fe30-f0a6-4743-ac91-11310cebea9f
ms.openlocfilehash: ebb53e7df979a553ed4a44deba34345c9ecac772
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981400"
---
# <a name="how-to-draw-a-single-b233zier-spline"></a><span data-ttu-id="d64f4-102">方法: 1 つの B&#233;ベジエスプラインを描画する</span><span class="sxs-lookup"><span data-stu-id="d64f4-102">How to: Draw a Single B&#233;zier Spline</span></span>
<span data-ttu-id="d64f4-103">ベジエスプラインは、始点、2つの制御点、およびエンドポイントの4つの点によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="d64f4-103">A Bézier spline is defined by four points: a start point, two control points, and an endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d64f4-104">例</span><span class="sxs-lookup"><span data-stu-id="d64f4-104">Example</span></span>  
 <span data-ttu-id="d64f4-105">次の例では、開始点 (10、100) とエンドポイント (200、100) を使用してベジエスプラインを描画します。</span><span class="sxs-lookup"><span data-stu-id="d64f4-105">The following example draws a Bézier spline with start point (10, 100) and endpoint (200, 100).</span></span> <span data-ttu-id="d64f4-106">制御ポイントは、(100, 10) と (150, 150) です。</span><span class="sxs-lookup"><span data-stu-id="d64f4-106">The control points are (100, 10) and (150, 150).</span></span>  
  
 <span data-ttu-id="d64f4-107">次の図は、結果として得られるベジエスプラインと、その始点、制御点、およびエンドポイントを示しています。</span><span class="sxs-lookup"><span data-stu-id="d64f4-107">The following illustration shows the resulting Bézier spline along with its start point, control points, and endpoint.</span></span> <span data-ttu-id="d64f4-108">また、この図にはスプラインの凸曲線ハルも示されています。これは、4つの点を直線に接続することによって形成される多角形です。</span><span class="sxs-lookup"><span data-stu-id="d64f4-108">The illustration also shows the spline's convex hull, which is a polygon formed by connecting the four points with straight lines.</span></span>  
  
 ![ベジエスプラインの図。](./media/how-to-draw-a-single-bezier-spline/bezier-spline-illustration.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d64f4-110">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="d64f4-110">Compiling the Code</span></span>  
 <span data-ttu-id="d64f4-111">前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。</span><span class="sxs-lookup"><span data-stu-id="d64f4-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d64f4-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="d64f4-112">See also</span></span>

- <xref:System.Drawing.Graphics.DrawBezier%2A>
- [<span data-ttu-id="d64f4-113">GDI+ でのベジエ スプライン</span><span class="sxs-lookup"><span data-stu-id="d64f4-113">Bézier Splines in GDI+</span></span>](bezier-splines-in-gdi.md)
- [<span data-ttu-id="d64f4-114">方法: 一連のベジエ スプラインを描画する</span><span class="sxs-lookup"><span data-stu-id="d64f4-114">How to: Draw a Sequence of Bézier Splines</span></span>](how-to-draw-a-sequence-of-bezier-splines.md)
