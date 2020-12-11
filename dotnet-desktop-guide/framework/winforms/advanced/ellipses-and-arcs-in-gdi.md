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
# <a name="ellipses-and-arcs-in-gdi"></a>GDI+ での楕円および円弧
<xref:System.Drawing.Graphics.DrawEllipse%2A>クラスのメソッドとメソッドを使用して、省略記号と円弧を簡単に描画でき <xref:System.Drawing.Graphics.DrawArc%2A> <xref:System.Drawing.Graphics> ます。  
  
## <a name="drawing-an-ellipse"></a>楕円の描画  
 楕円を描画するには、 <xref:System.Drawing.Graphics> オブジェクトとオブジェクトが必要 <xref:System.Drawing.Pen> です。 <xref:System.Drawing.Graphics>オブジェクトはメソッドを提供し、 <xref:System.Drawing.Graphics.DrawEllipse%2A> オブジェクトは、楕円の <xref:System.Drawing.Pen> 描画に使用される線の幅や色などの属性を格納します。 <xref:System.Drawing.Pen>オブジェクトは、引数の1つとしてメソッドに渡され <xref:System.Drawing.Graphics.DrawEllipse%2A> ます。 メソッドに渡される残りの引数は、 <xref:System.Drawing.Graphics.DrawEllipse%2A> 楕円の外接する四角形を指定します。 次の図は、外接する四角形と共に楕円を示しています。  
  
 ![省略記号と円弧](./media/aboutgdip02-art05.gif "Aboutgdip02_art05")  
  
 楕円を描画する例を次に示します。外接する四角形の幅は80、高さは40、の左上隅 (100、50) です。  
  
 [!code-csharp[LinesCurvesAndShapes#51](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#51)]
 [!code-vb[LinesCurvesAndShapes#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#51)]  
  
 <xref:System.Drawing.Graphics.DrawEllipse%2A> はクラスのオーバーロードされたメソッドである <xref:System.Drawing.Graphics> ため、複数の方法で引数を指定できます。 たとえば、を構築し、を <xref:System.Drawing.Rectangle> <xref:System.Drawing.Rectangle> <xref:System.Drawing.Graphics.DrawEllipse%2A> 引数としてメソッドに渡すことができます。  
  
 [!code-csharp[LinesCurvesAndShapes#52](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#52)]
 [!code-vb[LinesCurvesAndShapes#52](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#52)]  
  
## <a name="drawing-an-arc"></a>円弧の描画  
 弧は、楕円の一部です。 円弧を描画するには、 <xref:System.Drawing.Graphics.DrawArc%2A> クラスのメソッドを呼び出し <xref:System.Drawing.Graphics> ます。 メソッドのパラメーターは、 <xref:System.Drawing.Graphics.DrawArc%2A> <xref:System.Drawing.Graphics.DrawEllipse%2A> <xref:System.Drawing.Graphics.DrawArc%2A> 開始角度とスイープ角度を必要とする点を除いて、メソッドのパラメーターと同じです。 次の例では、開始角度が30°で、スイープ角度が180度の円弧を描画します。  
  
 [!code-csharp[LinesCurvesAndShapes#53](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#53)]
 [!code-vb[LinesCurvesAndShapes#53](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#53)]  
  
 次の図は、円弧、楕円、および外接する四角形を示しています。  
  
 ![省略記号と円弧](./media/aboutgdip02-art06.gif "Aboutgdip02_art06")  
  
## <a name="see-also"></a>関連項目

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [直線、曲線、および図形](lines-curves-and-shapes.md)
- [方法: 描画する Graphics オブジェクトを作成する](how-to-create-graphics-objects-for-drawing.md)
- [方法: ペンを作成する](how-to-create-a-pen.md)
- [方法: 形状のアウトラインを描画する](how-to-draw-an-outlined-shape.md)
