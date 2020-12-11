---
title: '方法: テキストを指定の位置に描画する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing at specified locations [Windows Forms]
- drawing text
- drawing text [Windows Forms], specified locations [Windows Forms]
- Windows Forms, drawing text at a specified location
ms.assetid: 60816423-1c38-465e-980d-2c2b64d74086
ms.openlocfilehash: 0c36b00e4f6f71f0ecf8042853bb8e99e57854da
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981372"
---
# <a name="how-to-draw-text-at-a-specified-location"></a>方法: テキストを指定の位置に描画する
カスタム描画を実行すると、指定したポイントから始まる1本の水平線にテキストを描画できます。 <xref:System.Drawing.Graphics.DrawString%2A> <xref:System.Drawing.Graphics> またはパラメーターを受け取るクラスのオーバーロードされたメソッドを使用して、この方法でテキストを描画でき <xref:System.Drawing.Point> <xref:System.Drawing.PointF> ます。 また、この <xref:System.Drawing.Graphics.DrawString%2A> メソッドにはとが必要です。 <xref:System.Drawing.Brush><xref:System.Drawing.Font>  
  
 を受け取るのオーバーロードされたメソッドを使用することもでき <xref:System.Windows.Forms.TextRenderer.DrawText%2A> <xref:System.Windows.Forms.TextRenderer> <xref:System.Drawing.Point> ます。 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> また、にはとが必要です <xref:System.Drawing.Color> <xref:System.Drawing.Font> 。  
  
 次の図は、オーバーロードされたメソッドを使用する場合に、指定したポイントで描画されるテキストの出力を示して <xref:System.Drawing.Graphics.DrawString%2A> います。  
  
 ![指定したポイントのテキストの出力を示すスクリーンショット。](./media/how-to-draw-text-at-a-specified-location/font-text-specified-point.png)  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a>GDI + を使用してテキストの行を描画するには  
  
1. メソッドを使用して、 <xref:System.Drawing.Graphics.DrawString%2A> 必要なテキストを渡し <xref:System.Drawing.Point> ます。または、、、およびを渡し <xref:System.Drawing.PointF> <xref:System.Drawing.Font> <xref:System.Drawing.Brush> ます。  
  
     [!code-csharp[System.Drawing.AlignDrawnText#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#30)]
     [!code-vb[System.Drawing.AlignDrawnText#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#30)]  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a>GDI を使用してテキスト行を描画するには  
  
1. メソッドを使用して、必要なテキスト、、、を <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 渡し <xref:System.Drawing.Point> <xref:System.Drawing.Font> <xref:System.Drawing.Color> ます。  
  
     [!code-csharp[System.Drawing.AlignDrawnText#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#40)]
     [!code-vb[System.Drawing.AlignDrawnText#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#40)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 前の例では、次のものが必要です。  
  
- <xref:System.Windows.Forms.PaintEventArgs>  `e`。これはのパラメーターです <xref:System.Windows.Forms.PaintEventHandler> 。  
  
## <a name="see-also"></a>関連項目

- [方法: GDI を使用してテキストを描画する](how-to-draw-text-with-gdi.md)
- [フォントとテキストの使用](using-fonts-and-text.md)
- [方法: フォント ファミリとフォントを作成する](how-to-construct-font-families-and-fonts.md)
- [方法: 四角形内にテキストを折り返して描画する](how-to-draw-wrapped-text-in-a-rectangle.md)
