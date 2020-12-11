---
title: '方法: ペンを使用して四角形を描画する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- rectangles [Windows Forms], drawing
- pens [Windows Forms], drawing rectangles
ms.assetid: 54a7fa14-3ad8-4d64-b424-2a12005b250c
ms.openlocfilehash: cd5d965f8b92d15cdeb3049330d9b3cc0de893b2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981228"
---
# <a name="how-to-use-a-pen-to-draw-rectangles"></a>方法: ペンを使用して四角形を描画する
四角形を描画するには、 <xref:System.Drawing.Graphics> オブジェクトとオブジェクトが必要 <xref:System.Drawing.Pen> です。 <xref:System.Drawing.Graphics>オブジェクトはメソッドを提供し、 <xref:System.Drawing.Graphics.DrawRectangle%2A> <xref:System.Drawing.Pen> オブジェクトは色や幅などの線の機能を格納します。  
  
## <a name="example"></a>例  
 次の例では、左上隅に (10, 10) の四角形を描画します。 四角形の幅は100、高さは50です。 コンストラクターに渡される2番目の引数は、 <xref:System.Drawing.Pen.%23ctor%2A> ペンの幅が5ピクセルであることを示します。  
  
 四角形が描画されると、ペンは四角形の境界の中央に配置されます。 ペンの幅は5であるため、四角形の辺は5ピクセル幅で描画されます。これにより、境界自体に1ピクセルが描画され、2ピクセルが内側に描画され、2ピクセルが外側に描画されます。 ペンの配置の詳細については、「 [方法: ペンの幅と配置を設定する](how-to-set-pen-width-and-alignment.md)」を参照してください。  
  
 次の図は、結果として得られる四角形を示しています。 点線は、ペンの幅が1ピクセルの場合に四角形が描画された場所を示しています。 四角形の左上隅の拡大表示は、太い黒い線がそれらの点線の中央に配置されていることを示しています。  
  
 ![黒と点線で描画された四角形を示すスクリーンショット。](./media/how-to-use-a-pen-to-draw-rectangles/drawn-rectangle-black-lines-dotted-lines.gif)  
  
 [!code-csharp[System.Drawing.UsingAPen#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingAPen#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。  
  
## <a name="see-also"></a>関連項目

- [ペンを使用した直線と図形の描画](using-a-pen-to-draw-lines-and-shapes.md)
