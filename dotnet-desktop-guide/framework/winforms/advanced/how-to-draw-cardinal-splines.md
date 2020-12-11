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
# <a name="how-to-draw-cardinal-splines"></a>方法: カーディナル スプラインを描画する
カーディナルスプラインは、指定された点のセットをスムーズに通過する曲線です。 カーディナルスプラインを描画するには、 <xref:System.Drawing.Graphics> オブジェクトを作成し、ポイントの配列のアドレスをメソッドに渡し <xref:System.Drawing.Graphics.DrawCurve%2A> ます。  
  
### <a name="drawing-a-bell-shaped-cardinal-spline"></a>Bell-Shaped カーディナルスプラインの描画  
  
- 次の例では、指定された5つのポイントを通過する釣鐘型のカーディナルスプラインを描画します。 次の図は、曲線と5つの点を示しています。  
  
     ![ベルの形をしたカーディナルスプラインを示す図。](./media/how-to-draw-cardinal-splines/bell-shaped-cardinal-spline.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#21)]  
  
### <a name="drawing-a-closed-cardinal-spline"></a>閉じたカーディナルスプラインを描画する  
  
- クラスのメソッドを使用して、 <xref:System.Drawing.Graphics.DrawClosedCurve%2A> <xref:System.Drawing.Graphics> 閉じたカーディナルスプラインを描画します。 閉じたカーディナルスプラインでは、曲線は配列の最後の点を通過し、配列内の最初の点と接続します。 次の例では、指定された6つのポイントを通過する閉じたカーディナルスプラインを描画します。 次の図は、閉じたスプラインと6つの点を示しています。  
  
 ![閉じたカーディナルスプラインを示す図。](./media/how-to-draw-cardinal-splines/closed-cardinal-spine.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#22)]  
  
### <a name="changing-the-bend-of-a-cardinal-spline"></a>カーディナルスプラインのベンドの変更  
  
- メソッドにテンション引数を渡すことで、カーディナルスプラインの曲がり方を変更し <xref:System.Drawing.Graphics.DrawCurve%2A> ます。 次の例では、同じ点のセットを通過する3つのカーディナルスプラインを描画します。 次の図は、3つのスプラインとそのテンション値を示しています。 テンションが0の場合、ポイントは直線で結ばれていることに注意してください。  
  
 ![3つのカーディナルスプラインを示す図。](./media/how-to-draw-cardinal-splines/three-cardinal-splines.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#23)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 前の例は、Windows フォームで使用するように設計されており <xref:System.Windows.Forms.PaintEventArgs> `e` 、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。  
  
## <a name="see-also"></a>関連項目

- [直線、曲線、および図形](lines-curves-and-shapes.md)
- [曲線の作成と描画](constructing-and-drawing-curves.md)
