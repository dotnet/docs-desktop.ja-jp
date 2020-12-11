---
title: GDI+ でのグラフィックス パス
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], paths
- GDI+, drawing paths
- paths [Windows Forms], drawing
- drawing [Windows Forms], paths
ms.assetid: a5500dec-666c-41fd-9da3-2169dd89c5eb
ms.openlocfilehash: 8e06032d145eb8c1aaf9bfcd1f205f8c6583634a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974435"
---
# <a name="graphics-paths-in-gdi"></a>GDI+ でのグラフィックス パス
パスは、直線、四角形、および単純な曲線を組み合わせることによって形成されます。 [ベクターグラフィックスの概要](vector-graphics-overview.md)からは、次の基本的な構成要素が、画像を描画するうえで最も役に立つことが実証されていることを思い出してください。  
  
- 路線  
  
- 四角形  
  
- 楕円  
  
- アーク  
  
- 多角形  
  
- カーディナルスプライン  
  
- ベジエスプライン  
  
 GDI + では、オブジェクトを使用して、 <xref:System.Drawing.Drawing2D.GraphicsPath> これらの構成要素のシーケンスを1つの単位にまとめることができます。 その後、クラスのメソッドを1回呼び出して、直線、四角形、多角形、および曲線のシーケンス全体を描画でき <xref:System.Drawing.Graphics.DrawPath%2A> <xref:System.Drawing.Graphics> ます。 次の図は、直線、円弧、ベジエスプライン、およびカーディナルスプラインを組み合わせることによって作成されるパスを示しています。  
  
 ![パス](./media/aboutgdip02-art14.gif "Aboutgdip02_art14")  
  
## <a name="using-a-path"></a>パスの使用  
 クラスには <xref:System.Drawing.Drawing2D.GraphicsPath> 、描画される項目のシーケンスを作成するための次のメソッドが用意されています。 <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> 、、、、 <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangle%2A> <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A> <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> <xref:System.Drawing.Drawing2D.GraphicsPath.AddPolygon%2A> 、 <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> (カーディナルスプラインの場合)、および <xref:System.Drawing.Drawing2D.GraphicsPath.AddBezier%2A> 。 これらのメソッドはそれぞれオーバーロードされます。つまり、各メソッドはいくつかの異なるパラメーターリストをサポートしています。 たとえば、メソッドの1つのバリエーションが4つの <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> 整数を受け取り、メソッドの別のバリエーションが <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> 2 つのオブジェクトを受け取り <xref:System.Drawing.Point> ます。  
  
 パスに線、四角形、およびベジエスプラインを追加する方法には、1回の呼び出しで複数の項目をパスに追加する複数形のコンパニオンメソッドがあります。 <xref:System.Drawing.Drawing2D.GraphicsPath.AddLines%2A> 、、 <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangles%2A> および <xref:System.Drawing.Drawing2D.GraphicsPath.AddBeziers%2A> です。 また、 <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> メソッドとメソッドには、 <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> 終了し <xref:System.Drawing.Drawing2D.GraphicsPath.AddClosedCurve%2A> <xref:System.Drawing.Drawing2D.GraphicsPath.AddPie%2A> た曲線または円をパスに追加するコンパニオンメソッドとがあります。  
  
 パスを描画するには、 <xref:System.Drawing.Graphics> オブジェクト、オブジェクト、 <xref:System.Drawing.Pen> およびオブジェクトが必要 <xref:System.Drawing.Drawing2D.GraphicsPath> です。 <xref:System.Drawing.Graphics>オブジェクトはメソッドを提供し、 <xref:System.Drawing.Graphics.DrawPath%2A> <xref:System.Drawing.Pen> オブジェクトはパスを表示するために使用される線の属性 (幅や色など) を格納します。 オブジェクトは、 <xref:System.Drawing.Drawing2D.GraphicsPath> パスを構成する直線と曲線のシーケンスを格納します。 <xref:System.Drawing.Pen>オブジェクトとオブジェクトは、 <xref:System.Drawing.Drawing2D.GraphicsPath> 引数としてメソッドに渡され <xref:System.Drawing.Graphics.DrawPath%2A> ます。 次の例では、直線、楕円、およびベジエスプラインで構成されるパスを描画します。  
  
 [!code-csharp[LinesCurvesAndShapes#101](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#101)]
 [!code-vb[LinesCurvesAndShapes#101](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#101)]  
  
 パスを次の図に示します。  
  
 ![パス](./media/aboutgdip02-art15.gif "Aboutgdip02_art15")  
  
 パスに線、四角形、曲線を追加するだけでなく、パスをパスに追加することもできます。 これにより、既存のパスを組み合わせて、大規模で複雑なパスを形成することができます。  
  
 [!code-csharp[LinesCurvesAndShapes#102](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#102)]
 [!code-vb[LinesCurvesAndShapes#102](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#102)]  
  
 パスには、文字列とパイという2つの項目を追加できます。 円は、楕円の内部の一部です。 次の例では、弧、カーディナルスプライン、文字列、および円からパスを作成します。  
  
 [!code-csharp[LinesCurvesAndShapes#103](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#103)]
 [!code-vb[LinesCurvesAndShapes#103](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#103)]  
  
 パスを次の図に示します。 パスは接続する必要がないことに注意してください。円弧、カーディナルスプライン、文字列、および円が分離されます。  
  
 ![パス](./media/aboutgdip02-art16.gif "Aboutgdip02_Art16")  
  
## <a name="see-also"></a>関連項目

- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- <xref:System.Drawing.Point?displayProperty=nameWithType>
- [直線、曲線、および図形](lines-curves-and-shapes.md)
- [方法: 描画する Graphics オブジェクトを作成する](how-to-create-graphics-objects-for-drawing.md)
- [パスの作成および描画](constructing-and-drawing-paths.md)
