---
title: '方法: 描画テキストを配置する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], aligning
- Windows Forms, aligning drawn text
ms.assetid: 83c10a81-1a90-4b5c-98aa-2c6c4b280079
ms.openlocfilehash: 3a569284a1c4b43fa7264e0354934436f95b8dc3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974431"
---
# <a name="how-to-align-drawn-text"></a>方法: 描画テキストを配置する
カスタム描画を実行する場合、フォームまたはコントロールに描画テキストの中心を設定することがよくあります。 <xref:System.Drawing.Graphics.DrawString%2A> <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 正しい書式設定オブジェクトを作成し、適切な書式フラグを設定することにより、メソッドまたはメソッドを使用して描画されたテキストを簡単に配置できます。  
  
### <a name="to-draw-centered-text-with-gdi-drawstring"></a>GDI + を使用して中央揃えのテキストを描画するには (DrawString)  
  
1. <xref:System.Drawing.StringFormat>中央揃えのテキストを指定するには、適切なメソッドと共にを使用し <xref:System.Drawing.Graphics.DrawString%2A> ます。  
  
     [!code-csharp[System.Drawing.AlignDrawnText#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#10)]
     [!code-vb[System.Drawing.AlignDrawnText#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#10)]  
  
### <a name="to-draw-centered-text-with-gdi-drawtext"></a>GDI (DrawText) を使用して中央揃えのテキストを描画するには  
  
1. 列挙体を使用して、 <xref:System.Windows.Forms.TextFormatFlags> 適切なメソッドを使用して、テキストを垂直方向および水平方向に折り返し <xref:System.Windows.Forms.TextRenderer.DrawText%2A> ます。  
  
     [!code-csharp[System.Drawing.AlignDrawnText#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#20)]
     [!code-vb[System.Drawing.AlignDrawnText#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#20)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 上記のコード例は、Windows フォームで使用するように設計されており、のパラメーターであるを必要とし <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.PaintEventHandler> ます。  
  
## <a name="see-also"></a>関連項目

- [方法: GDI を使用してテキストを描画する](how-to-draw-text-with-gdi.md)
- [フォントとテキストの使用](using-fonts-and-text.md)
- [方法: フォント ファミリとフォントを作成する](how-to-construct-font-families-and-fonts.md)
