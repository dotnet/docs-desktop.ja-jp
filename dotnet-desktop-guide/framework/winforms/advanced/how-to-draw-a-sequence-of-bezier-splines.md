---
title: '方法: 一連の B&#233;ベジエスプラインを描画する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- splines [Windows Forms], drawing Bezier
- Bezier splines [Windows Forms], drawing sequence of
ms.assetid: 37a0bedb-20c2-4cf0-91fa-a5509e826b30
ms.openlocfilehash: 976787f5830282a581d05a9c24d1f83dceca4b25
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981403"
---
# <a name="how-to-draw-a-sequence-of-b233zier-splines"></a><span data-ttu-id="6fe8e-102">方法: 一連の B&#233;ベジエスプラインを描画する</span><span class="sxs-lookup"><span data-stu-id="6fe8e-102">How to: Draw a Sequence of B&#233;zier Splines</span></span>
<span data-ttu-id="6fe8e-103"><xref:System.Drawing.Graphics.DrawBeziers%2A>クラスのメソッドを使用し <xref:System.Drawing.Graphics> て、接続された一連のベジエスプラインを描画できます。</span><span class="sxs-lookup"><span data-stu-id="6fe8e-103">You can use the <xref:System.Drawing.Graphics.DrawBeziers%2A> method of the <xref:System.Drawing.Graphics> class to draw a sequence of connected Bézier splines.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6fe8e-104">例</span><span class="sxs-lookup"><span data-stu-id="6fe8e-104">Example</span></span>  
 <span data-ttu-id="6fe8e-105">次の例では、2つの接続されたベジエスプラインで構成される曲線を描画します。</span><span class="sxs-lookup"><span data-stu-id="6fe8e-105">The following example draws a curve that consists of two connected Bézier splines.</span></span> <span data-ttu-id="6fe8e-106">最初のベジエスプラインのエンドポイントは、2番目のベジエスプラインの始点です。</span><span class="sxs-lookup"><span data-stu-id="6fe8e-106">The endpoint of the first Bézier spline is the start point of the second Bézier spline.</span></span>  
  
 <span data-ttu-id="6fe8e-107">次の図は、接続されたスプラインと7つの点を示しています。</span><span class="sxs-lookup"><span data-stu-id="6fe8e-107">The following illustration shows the connected splines along with the seven points:</span></span>  
  
 ![接続されたスプラインと7つの点を示すグラフィック。](./media/how-to-draw-a-sequence-of-bezier-splines/bezier-spline-seven-points.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6fe8e-109">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="6fe8e-109">Compiling the Code</span></span>  
 <span data-ttu-id="6fe8e-110">前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。</span><span class="sxs-lookup"><span data-stu-id="6fe8e-110">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fe8e-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="6fe8e-111">See also</span></span>

- [<span data-ttu-id="6fe8e-112">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="6fe8e-112">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="6fe8e-113">GDI+ でのベジエ スプライン</span><span class="sxs-lookup"><span data-stu-id="6fe8e-113">Bézier Splines in GDI+</span></span>](bezier-splines-in-gdi.md)
- [<span data-ttu-id="6fe8e-114">曲線の作成と描画</span><span class="sxs-lookup"><span data-stu-id="6fe8e-114">Constructing and Drawing Curves</span></span>](constructing-and-drawing-curves.md)
