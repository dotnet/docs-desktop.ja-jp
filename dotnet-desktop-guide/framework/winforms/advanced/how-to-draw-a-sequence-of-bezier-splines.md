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
# <a name="how-to-draw-a-sequence-of-b233zier-splines"></a>方法: 一連の B&#233;ベジエスプラインを描画する
<xref:System.Drawing.Graphics.DrawBeziers%2A>クラスのメソッドを使用し <xref:System.Drawing.Graphics> て、接続された一連のベジエスプラインを描画できます。  
  
## <a name="example"></a>例  
 次の例では、2つの接続されたベジエスプラインで構成される曲線を描画します。 最初のベジエスプラインのエンドポイントは、2番目のベジエスプラインの始点です。  
  
 次の図は、接続されたスプラインと7つの点を示しています。  
  
 ![接続されたスプラインと7つの点を示すグラフィック。](./media/how-to-draw-a-sequence-of-bezier-splines/bezier-spline-seven-points.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。  
  
## <a name="see-also"></a>関連項目

- [Windows フォームにおけるグラフィックスと描画](graphics-and-drawing-in-windows-forms.md)
- [GDI+ でのベジエ スプライン](bezier-splines-in-gdi.md)
- [曲線の作成と描画](constructing-and-drawing-curves.md)
