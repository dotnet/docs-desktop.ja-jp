---
title: '方法: 色を傾斜する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], transforming with color matrices
- colors [Windows Forms], shearing
ms.assetid: 0a424171-5b8b-45c4-afef-e9720a6c3e22
ms.openlocfilehash: 825e5a90ebb0d9df3b894ce7bd353e917b676939
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981271"
---
# <a name="how-to-shear-colors"></a>方法: 色を傾斜する
傾斜を設定すると、別のカラーコンポーネントに比例してカラーコンポーネントが拡大または縮小されます。 たとえば、赤の成分が青のコンポーネントの半分の値になるような変換を考えてみます。 このような変換では、色 (0.2、0.5、1) が (0.7、0.5、1) になります。 新しい赤の成分は 0.2 + (1/2) (1) = 0.7 です。  
  
## <a name="example"></a>例  
 次の例では、 <xref:System.Drawing.Image> ファイル ColorBars4.bmp からオブジェクトを構築します。 次に、前の段落で説明されている傾斜変換をイメージ内の各ピクセルに適用します。  
  
 次の図は、左側にある元のイメージと右側の傾斜されたイメージを示しています。
  
 ![元のイメージと傾斜したイメージを並べて並べた、色付きのストライプを含む2つの四角形。](./media/how-to-shear-colors/original-image-sheared-image.png)  
  
 次の表は、傾斜変換の前後に4つのバーの色ベクトルを示しています。  
  
|変更元|変形|  
|--------------|-------------|  
|(0, 0, 1, 1)|(0.5, 0, 1, 1)|  
|(0.5, 1, 0.5, 1)|(0.75, 1, 0.5, 1)|  
|(1, 1, 0, 1)|(1, 1, 0, 1)|  
|(0.4, 0.4, 0.4, 1)|(0.6, 0.4, 0.4, 1)|  
  
 [!code-csharp[System.Drawing.Misc3#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Misc3/CS/Form1.cs#9)]
 [!code-vb[System.Drawing.Misc3#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Misc3/VB/Form1.vb#9)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。 `ColorBars.bmp`システムで有効なイメージ名とパスで置き換えます。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [Windows フォームにおけるグラフィックスと描画](graphics-and-drawing-in-windows-forms.md)
- [イメージの色の変更](recoloring-images.md)
