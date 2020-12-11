---
title: '方法: テクスチャを使用して塗りつぶした直線を描画する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drawing [Windows Forms], lines
- lines [Windows Forms], texture
- drawing lines [Windows Forms], texture
ms.assetid: dc9118cc-f3c2-42e5-8173-f46d41d18fd5
ms.openlocfilehash: c0f90c298f48aeb96893bb09241faddc08d8a49d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981427"
---
# <a name="how-to-draw-a-line-filled-with-a-texture"></a>方法: テクスチャを使用して塗りつぶした直線を描画する
純色で線を描画する代わりに、テクスチャを使用して線を描画することもできます。 テクスチャで線と曲線を描画するには、 <xref:System.Drawing.TextureBrush> オブジェクトを作成し、その <xref:System.Drawing.TextureBrush> オブジェクトをコンストラクターに渡し <xref:System.Drawing.Pen.%23ctor%2A> ます。 テクスチャブラシに関連付けられているビットマップを使用して平面を並べて表示します (非表示)。また、ペンが直線または曲線を描画すると、ペンのストロークによって、タイル化されたテクスチャの特定のピクセルが明らかになります。  
  
## <a name="example"></a>例  
 次の例では、 <xref:System.Drawing.Bitmap> ファイルからオブジェクトを作成し `Texture1.jpg` ます。 そのビットマップを使用してオブジェクトを作成し、オブジェクトを使用してオブジェクトを <xref:System.Drawing.TextureBrush> <xref:System.Drawing.TextureBrush> 構築し <xref:System.Drawing.Pen> ます。 を呼び出すと、 <xref:System.Drawing.Graphics.DrawImage%2A> ビットマップが左上隅 ((0, 0)) で描画されます。 への呼び出しは、オブジェクトを使用して、 <xref:System.Drawing.Graphics.DrawEllipse%2A> <xref:System.Drawing.Pen> テクスチャ楕円を描画します。  
  
 次の図は、ビットマップとテクスチャ楕円を示しています。  
  
 ![ビットマップとテクスチャ楕円を示すスクリーンショット。](./media/how-to-draw-a-line-filled-with-a-texture/bitmap-textured-ellipse.png)  
  
 [!code-csharp[System.Drawing.UsingAPen#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.UsingAPen#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 Windows フォームを作成し、フォームのイベントを処理し <xref:System.Windows.Forms.Control.Paint> ます。 前のコードをイベントハンドラーに貼り付け <xref:System.Windows.Forms.Control.Paint> ます。 `Texture.jpg`システムで有効なイメージで置き換えます。  
  
## <a name="see-also"></a>関連項目

- [ペンを使用した直線と図形の描画](using-a-pen-to-draw-lines-and-shapes.md)
- [Windows フォームにおけるグラフィックスと描画](graphics-and-drawing-in-windows-forms.md)
