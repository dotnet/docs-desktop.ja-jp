---
title: '方法: 垂直方向のテキストを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing vertical
- Windows Forms, drawing vertical text
- strings [Windows Forms], drawing vertical
- vertical text [Windows Forms], drawing
ms.assetid: 50c69046-4188-47d9-b949-cc2610ffd337
ms.openlocfilehash: 86401342625f593945b801f7619ef9ca9681317c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974410"
---
# <a name="how-to-create-vertical-text"></a>方法: 垂直方向のテキストを作成する
オブジェクトを使用すると、 <xref:System.Drawing.StringFormat> テキストを水平方向ではなく垂直方向に描画するように指定できます。  
  
## <a name="example"></a>例  
 次の例では、 <xref:System.Drawing.StringFormatFlags.DirectionVertical> オブジェクトのプロパティに値を代入し <xref:System.Drawing.StringFormat.FormatFlags%2A> <xref:System.Drawing.StringFormat> ます。 その <xref:System.Drawing.StringFormat> オブジェクトは <xref:System.Drawing.Graphics.DrawString%2A> 、クラスのメソッドに渡され <xref:System.Drawing.Graphics> ます。 値は <xref:System.Drawing.StringFormatFlags.DirectionVertical> 列挙体のメンバーです <xref:System.Drawing.StringFormatFlags> 。  
  
 次の図は、縦のテキストを示しています。
  
 ![縦書きのフォントテキストを示すグラフィック。](./media/how-to-create-vertical-text/vertical-font-text-graphic.png)  
  
 [!code-csharp[System.Drawing.FontsAndText#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.FontsAndText#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
  
- 前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、のパラメーターであるを必要とし <xref:System.Windows.Forms.PaintEventHandler> ます。  
  
## <a name="see-also"></a>関連項目

- [方法: GDI を使用してテキストを描画する](how-to-draw-text-with-gdi.md)
