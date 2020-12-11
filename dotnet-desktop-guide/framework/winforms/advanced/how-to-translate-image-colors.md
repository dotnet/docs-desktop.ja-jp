---
title: '方法: イメージの色を変換する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [Windows Forms], changing colors
- images [Windows Forms], changing colors
- image colors [Windows Forms]
ms.assetid: 2106fb9a-4d60-4dcf-9220-9f189a6c4d19
ms.openlocfilehash: fb9ec30c06740214b8dc6b65d32eba4e2920c89b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981740"
---
# <a name="how-to-translate-image-colors"></a>方法: イメージの色を変換する
変換では、4つのカラーコンポーネントの1つ以上に値が追加されます。 次の表は、翻訳を表すカラーマトリックスエントリを示しています。  
  
|変換するコンポーネント|マトリックスエントリ|  
|--------------------------------|------------------|  
|[赤]|[4][0]|  
|[緑]|[4][1]|  
|青|[4][2]|  
|[アルファ]|[4][3]|  
  
## <a name="example"></a>例  
 次の例では、 <xref:System.Drawing.Image> ファイル ColorBars.bmp からオブジェクトを構築します。 次に、コードは、イメージ内の各ピクセルの赤の部分に0.75 を追加します。 元のイメージは、変換されたイメージと共に描画されます。  
  
 次の図は、左側にある元のイメージと、右側の変換されたイメージを示しています。  
  
 ![元のイメージと変換されたイメージのスクリーンショット。](./media/how-to-translate-image-colors/original-image-translate-colors.png)  
  
 次の表は、赤の平行移動の前後の4つのバーの色ベクトルを示しています。 色成分の最大値は1であるため、2番目の行の赤の成分は変化しないことに注意してください。 (同様に、カラーコンポーネントの最小値は0です)。  
  
|変更元|変換後|  
|--------------|----------------|  
|黒 (0、0、0、1)|(0.75, 0, 0, 1)|  
|赤 (1、0、0、1)|(1, 0, 0, 1)|  
|緑 (0、1、0、1)|(0.75, 1, 0, 1)|  
|Blue (0, 0, 1, 1)|(0.75, 0, 1, 1)|  
  
 [!code-csharp[System.Drawing.RecoloringImages#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.RecoloringImages#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。 を、 `ColorBars.bmp` システムで有効なイメージファイル名とパスに置き換えます。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [Windows フォームにおけるグラフィックスと描画](graphics-and-drawing-in-windows-forms.md)
- [イメージの色の変更](recoloring-images.md)
