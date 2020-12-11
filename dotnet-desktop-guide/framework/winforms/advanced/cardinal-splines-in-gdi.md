---
title: GDI+ でのカーディナル スプライン
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- splines [Windows Forms], cardinal
- GDI+, cardinal splines
- cardinal splines
ms.assetid: 09b3797a-6294-422d-9adf-a5a0a7695c0c
ms.openlocfilehash: 4588f6f606f0f479aeae1d143f23175ec4be32a5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96975061"
---
# <a name="cardinal-splines-in-gdi"></a>GDI+ でのカーディナル スプライン
カーディナルスプラインは、より大きな曲線を形成するために結合された個々の曲線のシーケンスです。 スプラインは、点の配列とテンションパラメーターによって指定されます。 カーディナルスプラインは、配列内の各点をスムーズに通過します。鋭い角はなく、曲線の tightness には急激な変化はありません。 次の図は、一連の点と、セット内の各点を通過するカーディナルスプラインを示しています。  
  
 ![カーディナル スプライン](./media/aboutgdip02-art09.gif "Aboutgdip02_art09")  
  
## <a name="physical-and-mathematical-splines"></a>物理的なスプラインと数学的なスプライン  
 物理的なスプラインは、木やその他の柔軟な素材の薄い部分です。 数学的なスプラインが登場する前に、デザイナーは物理的なスプラインを使用して曲線を描画していました。 デザイナーは、1つの用紙にスプラインを置き、特定の点のセットにアンカーを固定します。 その後、スプラインにペンや鉛筆で描画することによって、曲線を作成できます。 特定の点のセットによって、物理的なスプラインのプロパティに応じて、さまざまな曲線が生成される可能性があります。 たとえば、曲げに高い抵抗を持つスプラインでは、非常に柔軟なスプラインとは異なる曲線が生成されます。  
  
 数学的なスプラインの数式は、柔軟な rods のプロパティに基づいているため、数学的スプラインによって生成される曲線は、物理的なスプラインによって生成された曲線に似ています。 異なるテンションの物理的なスプラインが特定の点のセットを使用して異なる曲線を生成するのと同じように、テンションパラメーターの値が異なる数学スプラインでは、特定の点のセットによって異なる曲線が生成されます。 次の図は、同じ点のセットを通過する4つのカーディナルスプラインを示しています。 各スプラインのテンションが表示されます。 テンションが0の場合は、無限の物理的なテンションに相当します。これにより、曲線は、点の間の最短の方向 (直線) になります。 テンション1は物理的なテンションなしに対応し、スプラインは最小ベンドのパスを取得できます。 テンション値が1より大きい場合、曲線は圧縮された spring のように動作し、長いパスを取得するためにプッシュされます。  
  
 ![カーディナル スプライン](./media/aboutgdip02-art10.gif "Aboutgdip02_art10")  
  
 上の図の4つのスプラインは、開始点で同じ接線を共有します。 タンジェントは、曲線に沿って開始点から次の点まで描画される直線です。 同様に、終了点の共有タンジェントは、終了点から曲線上の前の点まで描画された直線です。  
  
 カーディナルスプラインを描画するには、クラスのインスタンス、 <xref:System.Drawing.Graphics> <xref:System.Drawing.Pen> 、およびオブジェクトの配列が必要です <xref:System.Drawing.Point> 。このクラスのインスタンスは、 <xref:System.Drawing.Graphics> <xref:System.Drawing.Graphics.DrawCurve%2A> スプラインを描画するメソッドを提供し、 <xref:System.Drawing.Pen> スプラインの属性 (線の幅や色など) を格納します。 オブジェクトの配列は、 <xref:System.Drawing.Point> 曲線が通過する点を格納します。 次のコード例は、の点を通過するカーディナルスプラインを描画する方法を示して `myPointArray` います。 3番目のパラメーターは、テンションです。  
  
 [!code-csharp[LinesCurvesAndShapes#31](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#31)]
 [!code-vb[LinesCurvesAndShapes#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#31)]  
  
## <a name="see-also"></a>関連項目

- [直線、曲線、および図形](lines-curves-and-shapes.md)
- [曲線の作成と描画](constructing-and-drawing-curves.md)
