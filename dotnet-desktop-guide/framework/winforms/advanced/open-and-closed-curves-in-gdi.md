---
title: GDI+ での開いた曲線と閉じた曲線
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- curves [Windows Forms], filling
- GDI+, curves
- curves [Windows Forms], drawing
- curves
ms.assetid: 08d2cc9a-dc9d-4eed-bcbb-2c8e2ca5d3ae
ms.openlocfilehash: 06afdc4549f7c3c9b0636e5c7052dcca87a153f1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981663"
---
# <a name="open-and-closed-curves-in-gdi"></a>GDI+ での開いた曲線と閉じた曲線
次の図は、開いている曲線と閉じた曲線の2つの曲線を示しています。  
  
 ![& 閉じた曲線を開く](./media/aboutgdip02-art24.gif "Aboutgdip02_art24")  
  
## <a name="managed-interface-for-curves"></a>曲線のマネージインターフェイス  
 閉じた曲線には内部があるため、ブラシで塗りつぶすことができます。 <xref:System.Drawing.Graphics>Gdi + のクラスは、閉じられた図形および曲線を塗りつぶすために、、、、、、、およびの各メソッドを提供します <xref:System.Drawing.Graphics.FillRectangle%2A> <xref:System.Drawing.Graphics.FillEllipse%2A> <xref:System.Drawing.Graphics.FillPie%2A> <xref:System.Drawing.Graphics.FillPolygon%2A> <xref:System.Drawing.Graphics.FillClosedCurve%2A> <xref:System.Drawing.Graphics.FillPath%2A> <xref:System.Drawing.Graphics.FillRegion%2A> 。 これらのメソッドのいずれかを呼び出す場合は常に、特定のブラシの種類 ( <xref:System.Drawing.SolidBrush> 、、 <xref:System.Drawing.Drawing2D.HatchBrush> <xref:System.Drawing.TextureBrush> 、 <xref:System.Drawing.Drawing2D.LinearGradientBrush> 、または) のいずれかを <xref:System.Drawing.Drawing2D.PathGradientBrush> 引数として渡す必要があります。  
  
 メソッドは、メソッドに関連してい <xref:System.Drawing.Graphics.FillPie%2A> <xref:System.Drawing.Graphics.DrawArc%2A> ます。 <xref:System.Drawing.Graphics.DrawArc%2A>メソッドが楕円の輪郭の一部を描画するのと同様に、 <xref:System.Drawing.Graphics.FillPie%2A> メソッドは楕円の内部の一部を塗りつぶします。 次の例では、円弧を描画し、楕円の内部の対応する部分を塗りつぶします。  
  
 [!code-csharp[LinesCurvesAndShapes#21](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#21)]
 [!code-vb[LinesCurvesAndShapes#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#21)]  
  
 次の図は、円弧と塗りつぶされた円グラフを示しています。  
  
 ![& 閉じた曲線を開く](./media/aboutgdip02-art25.gif "Aboutgdip02_art25")  
  
 メソッドは、メソッドに関連してい <xref:System.Drawing.Graphics.FillClosedCurve%2A> <xref:System.Drawing.Graphics.DrawClosedCurve%2A> ます。 どちらのメソッドも、終了点を開始位置に接続することによって、曲線を自動的に閉じます。 次の例では、(0, 0)、(60, 20)、および (40, 50) を通過する曲線を描画します。 次に、曲線は、(40, 50) を開始点 (0, 0) に接続することによって自動的に閉じられ、内部は純色で塗りつぶされます。  
  
 [!code-csharp[LinesCurvesAndShapes#22](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#22)]
 [!code-vb[LinesCurvesAndShapes#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#22)]  
  
 メソッドは、 <xref:System.Drawing.Graphics.FillPath%2A> パスの各部分の内部を塗りつぶします。 パスの一部が閉じた曲線または形状を形成しない場合、メソッドは、 <xref:System.Drawing.Graphics.FillPath%2A> そのパスを埋める前にその部分を自動的に閉じます。 次の例では、円弧、カーディナルスプライン、文字列、および円で構成されるパスを描画し、塗りつぶします。  
  
 [!code-csharp[LinesCurvesAndShapes#23](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#23)]
 [!code-vb[LinesCurvesAndShapes#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#23)]  
  
 次の図は、純色の塗りつぶしなしのパスを示しています。 文字列内のテキストは、メソッドによってアウトライン表示されていますが、塗りつぶされていないことに注意して <xref:System.Drawing.Graphics.DrawPath%2A> ください。 これは、 <xref:System.Drawing.Graphics.FillPath%2A> 文字列内の文字の内部を描画するメソッドです。  
  
 ![パスの文字列](./media/aboutgdip02-art26.gif "Aboutgdip02_art26")  
  
## <a name="see-also"></a>関連項目

- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- <xref:System.Drawing.Point?displayProperty=nameWithType>
- [直線、曲線、および図形](lines-curves-and-shapes.md)
- [方法: 描画する Graphics オブジェクトを作成する](how-to-create-graphics-objects-for-drawing.md)
- [パスの作成および描画](constructing-and-drawing-paths.md)
