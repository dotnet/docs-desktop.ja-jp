---
title: '方法: ライン キャップを使用した直線を描画する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drawing [Windows Forms], lines
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
- drawing lines [Windows Forms], line caps
ms.assetid: eb68c3e1-c400-4886-8a04-76978a429cb6
ms.openlocfilehash: 34abfc86e980a24ebb835cfd88d2522f8372c68d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981411"
---
# <a name="how-to-draw-a-line-with-line-caps"></a>方法: ライン キャップを使用した直線を描画する
直線キャップと呼ばれる複数の図形のいずれかで、行の先頭または末尾を描画できます。 GDI + では、丸い、正方形、ひし形、矢じりいった複数のラインキャップがサポートされています。  
  
## <a name="example"></a>例  
 線の始点 (始点のキャップ)、直線の端 (端のキャップ)、または破線の破線 (ダッシュキャップ) を指定することができます。  
  
 次の例では、一方の端の矢印ともう一方の端に丸いキャップを持つ線を描画します。 この図は、結果として得られる行を示しています。  
  
 ![丸いキャップの線を示す図。](./media/how-to-draw-a-line-with-line-caps/line-cap-arrowhead-example.gif)  
  
 [!code-csharp[System.Drawing.UsingAPen#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.UsingAPen#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
  
- Windows フォームを作成し、フォームのイベントを処理し <xref:System.Windows.Forms.Control.Paint> ます。 コード例を <xref:System.Windows.Forms.Control.Paint> として渡すイベントハンドラーに貼り付け `e` <xref:System.Windows.Forms.PaintEventArgs> ます。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- <xref:System.Drawing.Drawing2D.LineCap?displayProperty=nameWithType>
- [Windows フォームにおけるグラフィックスと描画](graphics-and-drawing-in-windows-forms.md)
- [ペンを使用した直線と図形の描画](using-a-pen-to-draw-lines-and-shapes.md)
