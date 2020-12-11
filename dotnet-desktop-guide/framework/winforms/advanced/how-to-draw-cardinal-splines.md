---
title: '方法: カーディナル スプラインを描画する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cardinal splines [Windows Forms], drawing
- drawing [Windows Forms], cardinal splines
- graphics [Windows Forms], cardinal splines
ms.assetid: a4a41e80-4461-4b47-b6bd-2c5e68881994
ms.openlocfilehash: 12e938567d529b33ead93e081d380a650a803f23
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981380"
---
# <a name="how-to-draw-cardinal-splines"></a><span data-ttu-id="daee3-102">方法: カーディナル スプラインを描画する</span><span class="sxs-lookup"><span data-stu-id="daee3-102">How to: Draw Cardinal Splines</span></span>
<span data-ttu-id="daee3-103">カーディナルスプラインは、指定された点のセットをスムーズに通過する曲線です。</span><span class="sxs-lookup"><span data-stu-id="daee3-103">A cardinal spline is a curve that passes smoothly through a given set of points.</span></span> <span data-ttu-id="daee3-104">カーディナルスプラインを描画するには、 <xref:System.Drawing.Graphics> オブジェクトを作成し、ポイントの配列のアドレスをメソッドに渡し <xref:System.Drawing.Graphics.DrawCurve%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="daee3-104">To draw a cardinal spline, create a <xref:System.Drawing.Graphics> object and pass the address of an array of points to the <xref:System.Drawing.Graphics.DrawCurve%2A> method.</span></span>  
  
### <a name="drawing-a-bell-shaped-cardinal-spline"></a><span data-ttu-id="daee3-105">Bell-Shaped カーディナルスプラインの描画</span><span class="sxs-lookup"><span data-stu-id="daee3-105">Drawing a Bell-Shaped Cardinal Spline</span></span>  
  
- <span data-ttu-id="daee3-106">次の例では、指定された5つのポイントを通過する釣鐘型のカーディナルスプラインを描画します。</span><span class="sxs-lookup"><span data-stu-id="daee3-106">The following example draws a bell-shaped cardinal spline that passes through five designated points.</span></span> <span data-ttu-id="daee3-107">次の図は、曲線と5つの点を示しています。</span><span class="sxs-lookup"><span data-stu-id="daee3-107">The following illustration shows the curve and five points.</span></span>  
  
     ![ベルの形をしたカーディナルスプラインを示す図。](./media/how-to-draw-cardinal-splines/bell-shaped-cardinal-spline.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#21)]  
  
### <a name="drawing-a-closed-cardinal-spline"></a><span data-ttu-id="daee3-109">閉じたカーディナルスプラインを描画する</span><span class="sxs-lookup"><span data-stu-id="daee3-109">Drawing a Closed Cardinal Spline</span></span>  
  
- <span data-ttu-id="daee3-110">クラスのメソッドを使用して、 <xref:System.Drawing.Graphics.DrawClosedCurve%2A> <xref:System.Drawing.Graphics> 閉じたカーディナルスプラインを描画します。</span><span class="sxs-lookup"><span data-stu-id="daee3-110">Use the <xref:System.Drawing.Graphics.DrawClosedCurve%2A> method of the <xref:System.Drawing.Graphics> class to draw a closed cardinal spline.</span></span> <span data-ttu-id="daee3-111">閉じたカーディナルスプラインでは、曲線は配列の最後の点を通過し、配列内の最初の点と接続します。</span><span class="sxs-lookup"><span data-stu-id="daee3-111">In a closed cardinal spline, the curve continues through the last point in the array and connects with the first point in the array.</span></span> <span data-ttu-id="daee3-112">次の例では、指定された6つのポイントを通過する閉じたカーディナルスプラインを描画します。</span><span class="sxs-lookup"><span data-stu-id="daee3-112">The following example draws a closed cardinal spline that passes through six designated points.</span></span> <span data-ttu-id="daee3-113">次の図は、閉じたスプラインと6つの点を示しています。</span><span class="sxs-lookup"><span data-stu-id="daee3-113">The following illustration shows the closed spline along with the six points:</span></span>  
  
 ![閉じたカーディナルスプラインを示す図。](./media/how-to-draw-cardinal-splines/closed-cardinal-spine.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#22)]  
  
### <a name="changing-the-bend-of-a-cardinal-spline"></a><span data-ttu-id="daee3-115">カーディナルスプラインのベンドの変更</span><span class="sxs-lookup"><span data-stu-id="daee3-115">Changing the Bend of a Cardinal Spline</span></span>  
  
- <span data-ttu-id="daee3-116">メソッドにテンション引数を渡すことで、カーディナルスプラインの曲がり方を変更し <xref:System.Drawing.Graphics.DrawCurve%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="daee3-116">Change the way a cardinal spline bends by passing a tension argument to the <xref:System.Drawing.Graphics.DrawCurve%2A> method.</span></span> <span data-ttu-id="daee3-117">次の例では、同じ点のセットを通過する3つのカーディナルスプラインを描画します。</span><span class="sxs-lookup"><span data-stu-id="daee3-117">The following example draws three cardinal splines that pass through the same set of points.</span></span> <span data-ttu-id="daee3-118">次の図は、3つのスプラインとそのテンション値を示しています。</span><span class="sxs-lookup"><span data-stu-id="daee3-118">The following illustration shows the three splines along with their tension values.</span></span> <span data-ttu-id="daee3-119">テンションが0の場合、ポイントは直線で結ばれていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="daee3-119">Note that when the tension is 0, the points are connected by straight lines.</span></span>  
  
 ![3つのカーディナルスプラインを示す図。](./media/how-to-draw-cardinal-splines/three-cardinal-splines.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#23)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="daee3-121">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="daee3-121">Compiling the Code</span></span>  
 <span data-ttu-id="daee3-122">前の例は、Windows フォームで使用するように設計されており <xref:System.Windows.Forms.PaintEventArgs> `e` 、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。</span><span class="sxs-lookup"><span data-stu-id="daee3-122">The preceding examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daee3-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="daee3-123">See also</span></span>

- [<span data-ttu-id="daee3-124">直線、曲線、および図形</span><span class="sxs-lookup"><span data-stu-id="daee3-124">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="daee3-125">曲線の作成と描画</span><span class="sxs-lookup"><span data-stu-id="daee3-125">Constructing and Drawing Curves</span></span>](constructing-and-drawing-curves.md)
