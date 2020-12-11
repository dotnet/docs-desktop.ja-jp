---
title: B GDI + でのベジエスプラインの&#233;
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Bezier splines
- splines [Windows Forms], Bezier
- GDI+, Bezier splines
ms.assetid: 5774ce1e-87d4-4bc7-88c4-4862052781b8
ms.openlocfilehash: ff4e9eb18610b70c88e057d3d44020321bbb9f4f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974460"
---
# <a name="b233zier-splines-in-gdi"></a>B GDI + でのベジエスプラインの&#233;
ベジエスプラインは、2つのエンドポイント (p1 および p2) と2つの制御点 (c1 および c2) で指定された曲線です。 曲線は p1 で始まり、p2 で終了します。 曲線は制御点を通過しませんが、コントロールポイントは磁石として機能し、特定の方向に曲線を引き出し、曲線の曲がり方に影響を与えることになります。 次の図は、ベジエ曲線とそのエンドポイントおよびコントロールポイントを示しています。  
  
 ![ベジエスプライン](./media/aboutgdip02-art11a.gif "Aboutgdip02_art11a")  
  
 この曲線は p1 で開始され、コントロールポイント c1 に移動します。 P1 の曲線の接線は、p1 から c1 に描画される直線です。 エンドポイント p2 の接線は、c2 から p2 の線です。  
  
## <a name="drawing-bzier-splines"></a>ベジエスプラインの描画  
 ベジエスプラインを描画するには、クラスのインスタンスとが必要 <xref:System.Drawing.Graphics> <xref:System.Drawing.Pen> です。 クラスのインスタンスは <xref:System.Drawing.Graphics> メソッドを提供 <xref:System.Drawing.Graphics.DrawBezier%2A> し、は <xref:System.Drawing.Pen> 曲線の描画に使用される線の属性 (幅や色など) を格納します。 は、 <xref:System.Drawing.Pen> 引数の1つとしてメソッドに渡され <xref:System.Drawing.Graphics.DrawBezier%2A> ます。 メソッドに渡される残りの引数 <xref:System.Drawing.Graphics.DrawBezier%2A> は、エンドポイントとコントロールポイントです。 次の例では、開始点 (0, 0)、制御点 (40、20 150 80)、および終了点 (100、10) を使用してベジエスプラインを描画します。  
  
 [!code-csharp[LinesCurvesAndShapes#71](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#71)]
 [!code-vb[LinesCurvesAndShapes#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#71)]  
  
 次の図は、曲線、コントロールポイント、および2つの接線を示しています。  
  
 ![ベジエスプライン](./media/aboutgdip02-art12.gif "Aboutgdip02_art12")  
  
 ベジエスプラインは、もともと、自動車業界で設計されたピエールベジェによって開発されました。 これらは、多くの種類のコンピューター支援設計で役立つことが実証されたため、フォントのアウトラインを定義するためにも使用されています。 ベジエスプラインは、次の図に示すように、さまざまな図形を生成することができます。  
  
 ![パス](./media/aboutgdip02-art13.gif "Aboutgdip02_art13")  
  
## <a name="see-also"></a>関連項目

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [直線、曲線、および図形](lines-curves-and-shapes.md)
- [曲線の作成と描画](constructing-and-drawing-curves.md)
- [方法: 描画する Graphics オブジェクトを作成する](how-to-create-graphics-objects-for-drawing.md)
- [方法: ペンを作成する](how-to-create-a-pen.md)
