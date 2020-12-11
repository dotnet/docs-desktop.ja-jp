---
title: 直線と曲線のアンチエイリアシング
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- antialiasing
- antialiasing [Windows Forms], smoothing modes
- GDI+, antialiasing
ms.assetid: 810da1a4-c136-4abf-88df-68e49efdd8d4
ms.openlocfilehash: 871c5cb3cd9356f677633acb04fe82021a9787c5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974898"
---
# <a name="antialiasing-with-lines-and-curves"></a>直線と曲線のアンチエイリアシング
GDI + を使用して線を描画する場合は、線の開始点と終了点を指定しますが、行の個々のピクセルに関する情報を指定する必要はありません。 GDI + は、ディスプレイドライバーソフトウェアと連携して、特定のディスプレイデバイスの線を表示するためにオンにするピクセルを決定します。  
  
## <a name="aliasing"></a>エイリアス化  
 ポイント (4, 2) からポイント (16, 10) までの直線の赤い線を考えてみます。 座標系の原点が左上隅にあり、測定単位がピクセルであるとします。 また、x 軸が右を指し、y 軸が下向きであることを想定しています。 次の図は、色付きの背景で描画された赤い線の拡大ビューを示しています。  
  
 ![線 (アンチエイリアシングなし)](./media/aboutgdip02-art33.gif "AboutGdip02_Art33")  
  
 線を描画するために使用される赤いピクセルは不透明です。 行には、部分的に透明なピクセルはありません。 この種類の線レンダリングでは、線がギザギザの形になり、線は階段状のように見えます。 階段のある線を表すこの方法は、エイリアスと呼ばれます。階段は、理論上の線のエイリアスです。  
  
## <a name="antialiasing"></a>アンチエイリアシング  
 線を描画するためのより高度な手法として、部分的に透明なピクセルを不透明ピクセルと共に使用することがあります。 ピクセルは、直線に近いかどうかに応じて、純粋な赤または赤と背景色のブレンドに設定されます。 この種類のレンダリングはアンチエイリアシングと呼ばれ、人間の目がより滑らかになる線になります。 次の図は、アンチエイリアシングされた線を生成するために、特定のピクセルと背景をブレンドする方法を示しています。  
  
 ![アンチエイリアシング線](./media/aboutgdip02-art34.gif "AboutGdip02_Art34")  
  
 アンチエイリアシング (スムージングとも呼ばれます) を曲線に適用することもできます。 次の図は、スムージングされた楕円の拡大表示を示しています。  
  
 ![アンチエイリアシング曲線](./media/aboutgdip02-art35.gif "AboutGdip02_Art35")  
  
 次の図は、実際のサイズにおける同じ楕円を示しています。この楕円は、アンチエイリアシングを使用せず、アンチエイリアシングを使用して1回です。  
  
 ![アンチエイリアシング例](./media/aboutgdip02-art36.gif "AboutGdip02_Art36")  
  
 アンチエイリアシングを使用する直線と曲線を描画するには、クラスのインスタンスを作成 <xref:System.Drawing.Graphics> し、その <xref:System.Drawing.Graphics.SmoothingMode%2A> プロパティをまたはに設定し <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> <xref:System.Drawing.Drawing2D.SmoothingMode.HighQuality> ます。 次に、同じクラスの描画メソッドの1つを呼び出し <xref:System.Drawing.Graphics> ます。  
  
 [!code-csharp[LinesCurvesAndShapes#81](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#81)]
 [!code-vb[LinesCurvesAndShapes#81](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#81)]  
  
## <a name="see-also"></a>関連項目

- <xref:System.Drawing.Drawing2D.SmoothingMode?displayProperty=nameWithType>
- [直線、曲線、および図形](lines-curves-and-shapes.md)
- [方法: テキストでのアンチエイリアシングの使用](how-to-use-antialiasing-with-text.md)
