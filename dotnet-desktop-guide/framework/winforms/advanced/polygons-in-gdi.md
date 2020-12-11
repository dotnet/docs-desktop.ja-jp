---
title: GDI+ での多角形
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- polygons
- drawing [Windows Forms], polygons
- GDI+, polygons
ms.assetid: a72213d2-d69a-4c2b-a75c-be7b20390c13
ms.openlocfilehash: 2b1e3d387e4d056d9187c54dcef560544206c370
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96979732"
---
# <a name="polygons-in-gdi"></a>GDI+ での多角形
多角形は、3つ以上の直線を持つ閉じた図形です。 たとえば、三角形は3辺の多角形で、四角形は4辺の多角形で、五角形は5辺の多角形です。 次の図は、いくつかのポリゴンを示しています。  
  
 ![多角形](./media/aboutgdip02-art07.gif "Aboutgdip02_art07")  
  
## <a name="drawing-a-polygon"></a>多角形の描画  
 多角形を描画するには、 <xref:System.Drawing.Graphics> オブジェクト、 <xref:System.Drawing.Pen> オブジェクト、および <xref:System.Drawing.Point> (または) オブジェクトの配列が必要 <xref:System.Drawing.PointF> です。 オブジェクトは、 <xref:System.Drawing.Graphics> メソッドを提供し <xref:System.Drawing.Graphics.DrawPolygon%2A> ます。 オブジェクトは、 <xref:System.Drawing.Pen> 多角形のレンダリングに使用される線の幅や色などの属性を格納します。また、オブジェクトの配列は、 <xref:System.Drawing.Point> 直線によって接続される点を格納します。 <xref:System.Drawing.Pen>オブジェクトとオブジェクトの配列は、 <xref:System.Drawing.Point> 引数としてメソッドに渡され <xref:System.Drawing.Graphics.DrawPolygon%2A> ます。 次の例では、3つの辺を描画します。 には、 `myPointArray` (0, 0)、(50, 30)、および (30, 60) の3つのポイントしか存在しないことに注意してください。 メソッドは、 <xref:System.Drawing.Graphics.DrawPolygon%2A> (30, 60) から開始点 (0, 0) までの線を描画して、多角形を自動的に閉じます。  
  
 [!code-csharp[LinesCurvesAndShapes#111](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#111)]
 [!code-vb[LinesCurvesAndShapes#111](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#111)]  
  
 次の図は、多角形を示しています。  
  
 ![Polygon](./media/aboutgdip02-art08.gif "Aboutgdip02_art08")  
  
## <a name="see-also"></a>関連項目

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [直線、曲線、および図形](lines-curves-and-shapes.md)
- [方法: ペンを作成する](how-to-create-a-pen.md)
