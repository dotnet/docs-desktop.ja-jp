---
title: '方法: 曲線のパスを直線に平坦化する'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], flattening curves into lines
- curves [Windows Forms], flattening
- GraphicsPath object
- paths [Windows Forms], flattening
- drawing [Windows Forms], flattening curves
ms.assetid: e654b8de-25f4-4735-9208-42e4514a589c
ms.openlocfilehash: d59a802618ddd5080c651e822ed4c09641f7f170
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981843"
---
# <a name="how-to-flatten-a-curved-path-into-a-line"></a>方法: 曲線のパスを直線に平坦化する
オブジェクトは、一連 <xref:System.Drawing.Drawing2D.GraphicsPath> の行とベジエスプラインを格納します。 パスにはいくつかの種類の曲線 (楕円、円弧、カーディナルスプライン) を追加できますが、パスに格納される前に各曲線がベジエスプラインに変換されます。 パスのフラット化では、パス内の各ベジエスプラインを直線のシーケンスに変換します。 次の図は、フラット化の前後のパスを示しています。  
  
 ![直線と曲線](./media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")  
  
### <a name="to-flatten-a-path"></a>パスを平坦化するには  
  
- <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A>オブジェクトのメソッドを呼び出し <xref:System.Drawing.Drawing2D.GraphicsPath> ます。 メソッドは、フラット化された <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> パスと元のパスの間の最大距離を指定する平坦化引数を受け取ります。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- [直線、曲線、および図形](lines-curves-and-shapes.md)
- [パスの作成および描画](constructing-and-drawing-paths.md)
