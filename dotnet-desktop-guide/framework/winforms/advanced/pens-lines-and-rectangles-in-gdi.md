---
title: GDI+ でのペン、直線、および四角形
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines
- GDI+, lines
- drawing [Windows Forms], rectangles
- rectangles
- drawing [Windows Forms], lines
- GDI+, pens
- examples [Windows Forms], drawing lines and shapes
- examples [Windows Forms], pens
- GDI+, rectangles
- examples [Windows Forms], GDI+
- lines [Windows Forms], dashed
ms.assetid: 30b25aae-e3eb-4479-bdb8-187cf651fc84
ms.openlocfilehash: 06d2351ffa7d7f009d7b049f4689df7038b4d202
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981660"
---
# <a name="pens-lines-and-rectangles-in-gdi"></a>GDI+ でのペン、直線、および四角形
GDI + を使用して線を描画するには、オブジェクトとオブジェクトを作成する必要があり <xref:System.Drawing.Graphics> <xref:System.Drawing.Pen> ます。 オブジェクトは、 <xref:System.Drawing.Graphics> 実際に描画を行うメソッドを提供し、 <xref:System.Drawing.Pen> オブジェクトは、線の色、幅、スタイルなどの属性を格納します。  
  
## <a name="drawing-a-line"></a>直線の描画  
 線を描画するには、 <xref:System.Drawing.Graphics.DrawLine%2A> オブジェクトのメソッドを呼び出し <xref:System.Drawing.Graphics> ます。 <xref:System.Drawing.Pen>オブジェクトは、引数の1つとしてメソッドに渡され <xref:System.Drawing.Graphics.DrawLine%2A> ます。 次の例では、点 (4, 2) から点 (12、6) までの線を描画します。  
  
 [!code-csharp[LinesCurvesAndShapes#41](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#41)]
 [!code-vb[LinesCurvesAndShapes#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#41)]  
  
 <xref:System.Drawing.Graphics.DrawLine%2A> はクラスのオーバーロードされたメソッドである <xref:System.Drawing.Graphics> ため、複数の方法で引数を指定できます。 たとえば、2つのオブジェクトを作成 <xref:System.Drawing.Point> し、その <xref:System.Drawing.Point> オブジェクトを引数としてメソッドに渡すことができ <xref:System.Drawing.Graphics.DrawLine%2A> ます。  
  
 [!code-csharp[LinesCurvesAndShapes#42](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#42)]
 [!code-vb[LinesCurvesAndShapes#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#42)]  
  
## <a name="constructing-a-pen"></a>ペンの構築  
 オブジェクトを構築するときに、特定の属性を指定でき <xref:System.Drawing.Pen> ます。 たとえば、1つの `Pen` コンストラクターで色と幅を指定できます。 次の例では、幅2の青い線を (0, 0) から (60, 30) に描画します。  
  
 [!code-csharp[LinesCurvesAndShapes#43](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#43)]
 [!code-vb[LinesCurvesAndShapes#43](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#43)]  
  
## <a name="dashed-lines-and-line-caps"></a>破線と線のキャップ  
 オブジェクトは、など <xref:System.Drawing.Pen> のプロパティも公開します。このプロパティを使用して、 <xref:System.Drawing.Pen.DashStyle%2A> 線の機能を指定できます。 次の例では、(100, 50) から (300, 80) の破線を描画します。  
  
 [!code-csharp[LinesCurvesAndShapes#44](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#44)]
 [!code-vb[LinesCurvesAndShapes#44](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#44)]  
  
 オブジェクトのプロパティを使用して、その <xref:System.Drawing.Pen> 他の多くの属性を設定することができます。 <xref:System.Drawing.Pen.StartCap%2A>プロパティと <xref:System.Drawing.Pen.EndCap%2A> プロパティは、線の端の外観を指定します。端は、平面、正方形、丸み、三角形、またはカスタム図形にすることができます。 <xref:System.Drawing.Pen.LineJoin%2A>プロパティを使用すると、接続された線をマイタ (鋭い角で結合)、傾斜、丸み、またはクリップするかどうかを指定できます。 次の図は、さまざまなキャップと結合スタイルを持つ線を示しています。  
  
 ![路線](./media/aboutgdip02-art04.gif "Aboutgdip02_art04")  
  
## <a name="drawing-a-rectangle"></a>四角形の描画  
 GDI + を使用した四角形の描画は、描画線に似ています。 四角形を描画するには、 <xref:System.Drawing.Graphics> オブジェクトとオブジェクトが必要 <xref:System.Drawing.Pen> です。 <xref:System.Drawing.Graphics>オブジェクトはメソッドを提供 <xref:System.Drawing.Graphics.DrawRectangle%2A> し、オブジェクトは、線の <xref:System.Drawing.Pen> 幅や色などの属性を格納します。 <xref:System.Drawing.Pen>オブジェクトは、引数の1つとしてメソッドに渡され <xref:System.Drawing.Graphics.DrawRectangle%2A> ます。 次の例では、左上隅が (100、50)、幅が80、高さが40の四角形を描画します。  
  
 [!code-csharp[LinesCurvesAndShapes#45](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#45)]
 [!code-vb[LinesCurvesAndShapes#45](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#45)]  
  
 <xref:System.Drawing.Graphics.DrawRectangle%2A> はクラスのオーバーロードされたメソッドである <xref:System.Drawing.Graphics> ため、複数の方法で引数を指定できます。 たとえば、オブジェクトを構築し、その <xref:System.Drawing.Rectangle> <xref:System.Drawing.Rectangle> オブジェクトを <xref:System.Drawing.Graphics.DrawRectangle%2A> 引数としてメソッドに渡すことができます。  
  
 [!code-csharp[LinesCurvesAndShapes#46](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#46)]
 [!code-vb[LinesCurvesAndShapes#46](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#46)]  
  
 <xref:System.Drawing.Rectangle>オブジェクトには、四角形に関する情報を操作および収集するためのメソッドとプロパティがあります。 たとえば、 <xref:System.Drawing.Rectangle.Inflate%2A> メソッドとメソッドは、 <xref:System.Drawing.Rectangle.Offset%2A> 四角形のサイズと位置を変更します。 メソッドは、 <xref:System.Drawing.Rectangle.IntersectsWith%2A> 四角形が別の指定された四角形と交差するかどうかを示し、メソッドは、 <xref:System.Drawing.Rectangle.Contains%2A> 指定された点が四角形内にあるかどうかを示します。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- <xref:System.Drawing.Rectangle?displayProperty=nameWithType>
- [方法: ペンを作成する](how-to-create-a-pen.md)
- [方法: Windows フォームに直線を描画する](how-to-draw-a-line-on-a-windows-form.md)
- [方法: 形状のアウトラインを描画する](how-to-draw-an-outlined-shape.md)
