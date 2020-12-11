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
# <a name="how-to-draw-a-single-b233zier-spline"></a>方法: 1 つの B&#233;ベジエスプラインを描画する
ベジエスプラインは、始点、2つの制御点、およびエンドポイントの4つの点によって定義されます。  
  
## <a name="example"></a>例  
 次の例では、開始点 (10、100) とエンドポイント (200、100) を使用してベジエスプラインを描画します。 制御ポイントは、(100, 10) と (150, 150) です。  
  
 次の図は、結果として得られるベジエスプラインと、その始点、制御点、およびエンドポイントを示しています。 また、この図にはスプラインの凸曲線ハルも示されています。これは、4つの点を直線に接続することによって形成される多角形です。  
  
 ![ベジエスプラインの図。](./media/how-to-draw-a-single-bezier-spline/bezier-spline-illustration.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Drawing.Graphics.DrawBezier%2A>
- [GDI+ でのベジエ スプライン](bezier-splines-in-gdi.md)
- [方法: 一連のベジエ スプラインを描画する](how-to-draw-a-sequence-of-bezier-splines.md)
