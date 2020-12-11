---
title: '方法: ペンの幅と配置を設定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pens [Windows Forms], setting width
- pens [Windows Forms], setting alignment
ms.assetid: a202af36-4d31-4401-a126-b232f51db581
ms.openlocfilehash: 1f1ea6e8ef0b94aa46a4bf8177d59e59297d6e3f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981775"
---
# <a name="how-to-set-pen-width-and-alignment"></a>方法: ペンの幅と配置を設定する
を作成するときに、 <xref:System.Drawing.Pen> コンストラクターの引数の1つとしてペンの幅を指定できます。 また、クラスのプロパティを使用して、ペンの幅を変更することもでき <xref:System.Drawing.Pen.Width%2A> <xref:System.Drawing.Pen> ます。  
  
 理論上の線の幅は0です。 幅が1ピクセルの線を描画すると、そのピクセルは理論上の線の中央に配置されます。 幅が1ピクセルを超える線を描画する場合、ピクセルは理論上の線の中央に配置されるか、理論的な線の片側に表示されます。 のペンの配置プロパティを設定して、 <xref:System.Drawing.Pen> そのペンで描画されたピクセルを理論上の線に対して相対的に配置する方法を決定できます。  
  
 次の <xref:System.Drawing.Drawing2D.PenAlignment.Center> <xref:System.Drawing.Drawing2D.PenAlignment.Outset> コード例に示されている、、の値は、 <xref:System.Drawing.Drawing2D.PenAlignment.Inset> 列挙体のメンバーです <xref:System.Drawing.Drawing2D.PenAlignment> 。  
  
 次のコード例では、1行を2回描画します。1回は幅1の黒のペン、もう1回は幅10の緑色のペンを使用します。  
  
### <a name="to-vary-the-width-of-a-pen"></a>ペンの幅を変更するには  
  
- プロパティの値 <xref:System.Drawing.Pen.Alignment%2A> を (既定値) に設定して、 <xref:System.Drawing.Drawing2D.PenAlignment.Center> 緑色のペンで描画されたピクセルを理論上の線の中央に配置するように指定します。 次の図は、結果として得られる行を示しています。  
  
     ![緑の強調表示の黒い細い線。](./media/how-to-set-pen-width-and-alignment/green-pixels-centered-line.gif)  
  
     次のコード例では、四角形を2回描画します。1回は幅1の黒のペン、もう1回は幅10の緑色のペンを使用します。  
  
     [!code-csharp[System.Drawing.UsingAPen#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#41)]
     [!code-vb[System.Drawing.UsingAPen#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#41)]  
  
### <a name="to-change-the-alignment-of-a-pen"></a>ペンの配置を変更するには  
  
- プロパティの値をに設定して、 <xref:System.Drawing.Pen.Alignment%2A> <xref:System.Drawing.Drawing2D.PenAlignment.Center> 緑色のペンで描画されたピクセルを四角形の境界の中央に配置するように指定します。  
  
     次の図は、結果として得られる四角形を示しています。
  
     ![黒い細い線が緑色の強調表示された四角形。](./media/how-to-set-pen-width-and-alignment/green-pixels-centered-rectangle.gif)  
  
     [!code-csharp[System.Drawing.UsingAPen#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#42)]
     [!code-vb[System.Drawing.UsingAPen#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#42)]  
  
### <a name="to-create-an-inset-pen"></a>インセットペンを作成するには  
  
- 前のコード例の3番目のステートメントを次のように変更して、緑色のペンの配置を変更します。  
  
     [!code-csharp[System.Drawing.UsingAPen#43](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#43)]
     [!code-vb[System.Drawing.UsingAPen#43](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#43)]  
  
     これで、次の図に示すように、緑色のワイド線のピクセルが四角形の内側に表示されます。
  
     ![黒色の線で囲まれた四角形。内部には、幅の広い緑色の線が付きます。](./media/how-to-set-pen-width-and-alignment/green-pixels-inside-rectangle.gif)  
  
## <a name="see-also"></a>関連項目

- [ペンを使用した直線と図形の描画](using-a-pen-to-draw-lines-and-shapes.md)
- [Windows フォームにおけるグラフィックスと描画](graphics-and-drawing-in-windows-forms.md)
