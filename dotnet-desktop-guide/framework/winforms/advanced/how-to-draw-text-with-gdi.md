---
title: '方法: GDI を使用してテキストを描画する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI [Windows Forms], drawing text [Windows Forms]
- text [Windows Forms], drawing with TextRenderer
- drawing [Windows Forms], text
- Windows Forms, drawing text with GDI
ms.assetid: 2a19fe5d-2ace-451c-94db-01cb1118ef7b
ms.openlocfilehash: 3ed2b5c94e4a38a5873a34e61287c4038cab5cbb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981367"
---
# <a name="how-to-draw-text-with-gdi"></a>方法: GDI を使用してテキストを描画する
クラスの <xref:System.Windows.Forms.TextRenderer.DrawText%2A> メソッドを使用 <xref:System.Windows.Forms.TextRenderer> すると、フォームまたはコントロールにテキストを描画するための GDI 機能にアクセスできます。 GDI テキストレンダリングでは、通常、GDI + よりもパフォーマンスが向上し、より正確なテキスト測定が提供されます。  
  
> [!NOTE]
> <xref:System.Windows.Forms.TextRenderer.DrawText%2A>クラスのメソッドは <xref:System.Windows.Forms.TextRenderer> 印刷がサポートされていません。 印刷時には、常に <xref:System.Drawing.Graphics.DrawString%2A> クラスのメソッドを使用し <xref:System.Drawing.Graphics> ます。  
  
## <a name="example"></a>例  
 次のコード例は、メソッドを使用して、四角形内の複数の行にテキストを描画する方法を示して <xref:System.Windows.Forms.TextRenderer.DrawText%2A> います。  
  
 [!code-csharp[System.Windows.Forms.TextRendererExamples#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/CS/Form1.cs#7)]
 [!code-vb[System.Windows.Forms.TextRendererExamples#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/VB/Form1.vb#7)]  
  
 クラスを使用してテキストを表示するには、となどの、 <xref:System.Windows.Forms.TextRenderer> <xref:System.Drawing.IDeviceContext> <xref:System.Drawing.Graphics> <xref:System.Drawing.Font> テキストを描画する場所、および描画する色を必要とします。 必要に応じて、列挙を使用してテキストの書式を指定することもでき <xref:System.Windows.Forms.TextFormatFlags> ます。  
  
 の取得の詳細については <xref:System.Drawing.Graphics> 、「 [方法: 描画用のグラフィックスオブジェクトを作成する](how-to-create-graphics-objects-for-drawing.md)」を参照してください。 の構築の詳細については <xref:System.Drawing.Font> 、「 [方法: フォントファミリとフォントを作成する](how-to-construct-font-families-and-fonts.md)」を参照してください。  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 上記のコード例は、Windows フォームで使用するように設計されており、のパラメーターであるを必要とし <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.PaintEventHandler> ます。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.TextRenderer>
- <xref:System.Drawing.Font>
- <xref:System.Drawing.Color>
- [フォントとテキストの使用](using-fonts-and-text.md)
