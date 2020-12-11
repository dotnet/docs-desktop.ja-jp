---
title: '方法: 四角形内にテキストを折り返して描画する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drawing text in a rectangle
- text [Windows Forms], drawing in a rectangle
- strings [Windows Forms], drawing in a rectangle
ms.assetid: e1fb432a-dc90-48b5-9b6b-acc14507133d
ms.openlocfilehash: ace79e45737a3ce26d8bdcd603e923c1e6040d4d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981348"
---
# <a name="how-to-draw-wrapped-text-in-a-rectangle"></a>方法: 四角形内にテキストを折り返して描画する
<xref:System.Drawing.Graphics.DrawString%2A> <xref:System.Drawing.Graphics> またはパラメーターを受け取るクラスのオーバーロードされたメソッドを使用することにより、ラップされたテキストを四角形で描画でき <xref:System.Drawing.Rectangle> <xref:System.Drawing.RectangleF> ます。 また、とを使用し <xref:System.Drawing.Brush> <xref:System.Drawing.Font> ます。  
  
 およびパラメーターを受け取るのオーバーロードされたメソッドを使用して、四角形内にラップされたテキストを描画することもでき <xref:System.Windows.Forms.TextRenderer.DrawText%2A> <xref:System.Windows.Forms.TextRenderer> <xref:System.Drawing.Rectangle> <xref:System.Windows.Forms.TextFormatFlags> ます。 また、とを使用し <xref:System.Drawing.Color> <xref:System.Drawing.Font> ます。  
  
 次の図は、メソッドを使用するときに四角形に描画されるテキストの出力を示してい <xref:System.Drawing.Graphics.DrawString%2A> ます。
  
 ![DrawString メソッドを使用した場合の出力を示すスクリーンショット。](./media/how-to-draw-wrapped-text-in-a-rectangle/drawstring-method-font-text.png)  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a>GDI + を使用して四角形内にラップされたテキストを描画するには  
  
1. オーバーロードされたメソッドを使用して、 <xref:System.Drawing.Graphics.DrawString%2A> 必要なテキスト、 <xref:System.Drawing.Rectangle> または <xref:System.Drawing.RectangleF> を渡し <xref:System.Drawing.Font> <xref:System.Drawing.Brush> ます。  
  
     [!code-csharp[System.Drawing.AlignDrawnText#50](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#50)]
     [!code-vb[System.Drawing.AlignDrawnText#50](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#50)]  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a>GDI を使用して四角形内にラップされたテキストを描画するには  
  
1. 列挙値を使用して、 <xref:System.Windows.Forms.TextFormatFlags> オーバーロードされたメソッドでテキストをラップすることを指定し <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 、必要なテキスト、 <xref:System.Drawing.Rectangle> 、およびを渡し <xref:System.Drawing.Font> <xref:System.Drawing.Color> ます。  
  
     [!code-csharp[System.Drawing.AlignDrawnText#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#60)]
     [!code-vb[System.Drawing.AlignDrawnText#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#60)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 前の例では、次のものが必要です。  
  
- <xref:System.Windows.Forms.PaintEventArgs>`e`。これはのパラメーターです <xref:System.Windows.Forms.PaintEventHandler> 。  
  
## <a name="see-also"></a>関連項目

- [方法: GDI を使用してテキストを描画する](how-to-draw-text-with-gdi.md)
- [フォントとテキストの使用](using-fonts-and-text.md)
- [方法: フォント ファミリとフォントを作成する](how-to-construct-font-families-and-fonts.md)
- [方法: テキストを指定の位置に描画する](how-to-draw-text-at-a-specified-location.md)
