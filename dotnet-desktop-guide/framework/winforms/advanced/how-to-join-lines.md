---
title: '方法: 直線を接合する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- miter line join style
- bevel line join style
- line join
- drawing [Windows Forms], joining lines
- GraphicsPath object
- round line join style
- lines [Windows Forms], joining
- graphics [Windows Forms], joining lines
ms.assetid: 9fc480c2-3c75-4fd1-8ab5-296a99e820e2
ms.openlocfilehash: 362ce0c701d6e5f640fecd143a60cf471045629c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981831"
---
# <a name="how-to-join-lines"></a>方法: 直線を接合する
線結合は、2つの行で構成される共通領域で、両端が一致しているか、重複しています。 GDI + には、3つの線の結合スタイル (マイタ、ベベル、round) が用意されています。 線の結合スタイルは、クラスのプロパティ <xref:System.Drawing.Pen> です。 オブジェクトの線の結合スタイルを指定すると <xref:System.Drawing.Pen> 、その結合スタイルは、 <xref:System.Drawing.Drawing2D.GraphicsPath> そのペンを使用して描画されたオブジェクト内のすべての接続線に適用されます。  
  
 次の図は、傾斜線結合の例の結果を示しています。  
  
 ![結合された直線を示す図。](./media/how-to-join-lines/joined-beveled-lines.gif)  
  
## <a name="example"></a>例  
 線の結合スタイルは、クラスのプロパティを使用して指定でき <xref:System.Drawing.Pen.LineJoin%2A> <xref:System.Drawing.Pen> ます。 この例は、水平線と垂直線の間のベベル線結合を示しています。 次のコードで <xref:System.Drawing.Drawing2D.LineJoin.Bevel> は、プロパティに割り当てられた値 <xref:System.Drawing.Pen.LineJoin%2A> は列挙体のメンバーです <xref:System.Drawing.Drawing2D.LineJoin> 。 列挙体の他のメンバー <xref:System.Drawing.Drawing2D.LineJoin> は、 <xref:System.Drawing.Drawing2D.LineJoin.Miter> と <xref:System.Drawing.Drawing2D.LineJoin.Round> です。  
  
 [!code-csharp[System.Drawing.UsingAPen#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingAPen#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。  
  
## <a name="see-also"></a>関連項目

- [ペンを使用した直線と図形の描画](using-a-pen-to-draw-lines-and-shapes.md)
