---
title: ベクター グラフィックスの概要
ms.date: 03/30/2017
ms.topic: overview
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inclusive-inclusive endpoints
- coordinate systems
- graphics [Windows Forms], vector graphics
ms.assetid: 0195df81-66be-452d-bb53-5a582ebfdc09
ms.openlocfilehash: 6f405f5ffc67a0cdb13fe83f4dd36b70769a4cd9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981176"
---
# <a name="vector-graphics-overview"></a>ベクター グラフィックスの概要
GDI + 座標系に線、四角形、およびその他の図形を描画します。 さまざまな座標系から選択することができますが、既定の座標系では、左上隅に原点があり、x 軸は右を指し、y 軸は下向きになっています。 既定の座標系の測定単位はピクセルです。  
  
## <a name="the-building-blocks-of-gdi"></a>GDI + の構成要素  
 ![ベクター グラフィックス](./media/aboutgdip02-art01.gif "AboutGdip02_Art01")  
  
 コンピューターモニターは、ピクチャ要素またはピクセルと呼ばれる四角形のドットの配列に表示を作成します。 画面に表示されるピクセルの数は、モニターごとに異なります。また、個々のモニターに表示されるピクセルの数は、通常、ユーザーが一定の範囲で構成できます。  
  
 ![ベクター グラフィックス](./media/aboutgdip02-art02.gif "AboutGdip02_Art02")  
  
 GDI + を使用して線、四角形、または曲線を描画する場合は、描画される項目に関する特定のキー情報を指定します。 たとえば、2つの点を提供して線を指定したり、ポイント、高さ、および幅を指定して四角形を指定したりすることができます。 GDI + は、ディスプレイドライバーソフトウェアと連携して、線、四角形、または曲線を表示するためにオンにする必要があるピクセルを判別します。 次の図は、ポイント (4, 2) からポイント (12, 8) までの線を表示するためにオンになっているピクセルを示しています。  
  
 ![ベクター グラフィックス](./media/aboutgdip02-art03.gif "AboutGdip02_Art03")  
  
 時間の経過と共に、いくつかの基本的な構成要素は、2次元の画像を作成するのに最も役に立つことが実証されています。 GDI + でサポートされているこれらの構成要素は、次の一覧に示されています。  
  
- 路線  
  
- 四角形  
  
- 楕円  
  
- アーク  
  
- 多角形  
  
- カーディナルスプライン  
  
- ベジエ スプライン  
  
## <a name="methods-for-drawing-with-a-graphics-object"></a>グラフィックスオブジェクトを使用して描画するためのメソッド  
 <xref:System.Drawing.Graphics>Gdi + のクラスは、、、 <xref:System.Drawing.Graphics.DrawLine%2A> <xref:System.Drawing.Graphics.DrawRectangle%2A> 、、 <xref:System.Drawing.Graphics.DrawEllipse%2A> <xref:System.Drawing.Graphics.DrawPolygon%2A> <xref:System.Drawing.Graphics.DrawArc%2A> 、 <xref:System.Drawing.Graphics.DrawCurve%2A> (カーディナルスプラインの場合)、および <xref:System.Drawing.Graphics.DrawBezier%2A> の各項目を描画するための次のメソッドを提供します。 これらのメソッドはそれぞれオーバーロードされます。つまり、各メソッドはいくつかの異なるパラメーターリストをサポートしています。 たとえば、メソッドの1つのバリエーションが <xref:System.Drawing.Graphics.DrawLine%2A> <xref:System.Drawing.Pen> オブジェクトと4つの整数を受け取り、メソッドの別のバリエーションが <xref:System.Drawing.Graphics.DrawLine%2A> <xref:System.Drawing.Pen> オブジェクトと2つのオブジェクトを受け取り <xref:System.Drawing.Point> ます。  
  
 線、四角形、およびベジエスプラインを描画するためのメソッドには、1回の呼び出しで複数の項目を描画する複数の関連メソッドがあります。 <xref:System.Drawing.Graphics.DrawLines%2A> 、、 <xref:System.Drawing.Graphics.DrawRectangles%2A> および <xref:System.Drawing.Graphics.DrawBeziers%2A> です。 また、この <xref:System.Drawing.Graphics.DrawCurve%2A> メソッドには、 <xref:System.Drawing.Graphics.DrawClosedCurve%2A> 曲線の終了点を開始点に接続することによって曲線を閉じる、関連するメソッドがあります。  
  
 クラスのすべての描画メソッドは、 <xref:System.Drawing.Graphics> オブジェクトと連携して動作 <xref:System.Drawing.Pen> します。 任意のオブジェクトを描画するには、オブジェクトとオブジェクトの2つ以上のオブジェクトを作成する必要があり <xref:System.Drawing.Graphics> <xref:System.Drawing.Pen> ます。 オブジェクトは、 <xref:System.Drawing.Pen> 描画される項目の線の幅や色などの属性を格納します。 <xref:System.Drawing.Pen>オブジェクトは、引数の1つとして描画メソッドに渡されます。 たとえば、次の例に示すように、メソッドの1つのバリエーションでは、 <xref:System.Drawing.Graphics.DrawLine%2A> <xref:System.Drawing.Pen> オブジェクトと4つの整数を受け取ります。この例では、幅100、高さ50、およびの左上隅 (20, 10) の四角形を描画します。  
  
 [!code-csharp[LinesCurvesAndShapes#11](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#11)]
 [!code-vb[LinesCurvesAndShapes#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#11)]  
  
## <a name="see-also"></a>関連項目

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [直線、曲線、および図形](lines-curves-and-shapes.md)
- [方法: 描画する Graphics オブジェクトを作成する](how-to-create-graphics-objects-for-drawing.md)
