---
title: '方法: 色を回転させる'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], rotating
- examples [Windows Forms], rotating colors
ms.assetid: e2e4c300-159c-4f4a-9b56-103b0f7cbc05
ms.openlocfilehash: 8d2717dd7b819e963126072279b361fda02188bc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981792"
---
# <a name="how-to-rotate-colors"></a>方法: 色を回転させる
4次元の色空間での回転は、視覚化するのが困難です。 色のコンポーネントの1つを固定したままにして、回転を簡単に視覚化できるようにすることができます。 アルファコンポーネントを 1 (完全に不透明) に固定したままにすることに同意したとします。 次の図に示すように、赤、緑、および青の軸を持つ3次元の色空間を視覚化できます。  
  
 ![赤、緑、および青の軸を使用した回転を示す図。](./media/how-to-rotate-colors/rotation-red-green-blue-axes.gif)  
  
 色は、3D 空間のポイントと考えることができます。 たとえば、空間のポイント (1, 0, 0) は赤を表し、空間のポイント (0, 1, 0) は緑を表します。  
  
 次の図は、Red-Green 平面で60度の角度を使用して、色 (1, 0, 0) を回転させる意味を示しています。 平面内の回転は、Red-Green 平面と平行していて、青の軸についての回転と考えることができます。  
  
 ![青色の軸についての回転を示す図。](./media/how-to-rotate-colors/rotation-about-blue-axis.gif)  
  
 次の図は、カラー行列を初期化して、3つの座標軸 (赤、緑、青) のそれぞれに対して回転を実行する方法を示しています。  
  
 ![カラー行列を初期化して、3つの軸についての回転を実行します。](./media/how-to-rotate-colors/rotation-about-three-axes.gif)  
  
## <a name="example"></a>例  
 次の例では、1つの色 (1、0、0.6) のイメージを取得し、青の軸について60度回転を適用します。 回転の角度は、赤と緑の平面に平行した平面でスイープされます。  
  
 次の図は、左側の元の画像と右側のカラー回転画像を示しています。  
  
 ![元の画像とカラー回転した画像を示す図。](./media/how-to-rotate-colors/original-color-rotated-images.png)  
  
 次の図は、次のコードで実行されるカラー回転の視覚化を示しています。
  
 ![色の回転の視覚化を示す図。](./media/how-to-rotate-colors/visualization-color-rotation.gif)  
  
 [!code-csharp[System.Drawing.RotateColors#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。 `RotationInput.bmp`システムで有効なイメージファイル名とパスで置き換えます。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [Windows フォームにおけるグラフィックスと描画](graphics-and-drawing-in-windows-forms.md)
- [イメージの色の変更](recoloring-images.md)
