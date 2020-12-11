---
title: 変換を使用した色のスケーリング
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], for scaling colors
- colors [Windows Forms], scaling
ms.assetid: df23c887-7fd6-4b15-ad94-e30b5bd4b849
ms.openlocfilehash: 81c0ddf5b937d604559a9eb1a8b598885546c97f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981179"
---
# <a name="using-transformations-to-scale-colors"></a>変換を使用した色のスケーリング
スケーリング変換は、4つの色のコンポーネントの1つ以上を数値で乗算します。 スケーリングを表すカラーマトリックスのエントリを次の表に示します。  
  
|スケールするコンポーネント|マトリックスエントリ|  
|----------------------------|------------------|  
|[赤]|[0][0]|  
|[緑]|[1][1]|  
|青|[2][2]|  
|[アルファ]|[3][3]|  
  
## <a name="scaling-one-color"></a>1色のスケーリング  
 次の例では、 <xref:System.Drawing.Image> ファイル ColorBars2.bmp からオブジェクトを構築します。 次に、このコードでは、イメージ内の各ピクセルの青の要素を2倍の量でスケーリングします。 元のイメージは、変換されたイメージと共に描画されます。  
  
 [!code-csharp[System.Drawing.RecoloringImages#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.RecoloringImages#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#41)]  
  
 次の図は、左側にある元のイメージと右側の拡大縮小されたイメージを示しています。  
  
 ![元の色とスケーリングされた色を比較するスクリーンショット。](./media/using-transformations-to-scale-colors/four-bar-scale-one-color.png)  
  
 次の表は、青のスケーリングの前後に4つのバーの色ベクトルを示しています。 4番目のカラーバーの青のコンポーネントが0.8 から0.6 になりました。 これは、GDI + によって結果の小数部のみが保持されるためです。 たとえば、(2) (0.8) = 1.6、1.6 の小数部は0.6 です。 小数部のみを保持すると、結果は常に [0, 1] の範囲内になります。  
  
|変更元|位取り|  
|--------------|------------|  
|(0.4, 0.4, 0.4, 1)|(0.4, 0.4, 0.8, 1)|  
|(0.4, 0.2, 0.2, 1)|(0.4, 0.2, 0.4, 1)|  
|(0.2, 0.4, 0.2, 1)|(0.2, 0.4, 0.4, 1)|  
|(0.4, 0.4, 0.8, 1)|(0.4, 0.4, 0.6, 1)|  
  
## <a name="scaling-multiple-colors"></a>複数の色のスケーリング  
 次の例では、 <xref:System.Drawing.Image> ファイル ColorBars2.bmp からオブジェクトを構築します。 次に、イメージ内の各ピクセルの赤、緑、および青のコンポーネントをスケーリングします。 赤のコンポーネントは25% スケールダウンされ、緑のコンポーネントは35% にスケールダウンされ、青のコンポーネントは50% にスケールダウンされます。  
  
 [!code-csharp[System.Drawing.RecoloringImages#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.RecoloringImages#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#42)]  
  
 次の図は、左側にある元のイメージと右側の拡大縮小されたイメージを示しています。  
  
 ![元の色とスケーリングされた色を比較するスクリーンショット。](./media/using-transformations-to-scale-colors/four-bar-scale-multiple-colors.png)  
  
 次の表は、赤、緑、および青のスケーリングの前後に4つのバーの色ベクトルを示しています。  
  
|変更元|位取り|  
|--------------|------------|  
|(0.6, 0.6, 0.6, 1)|(0.45, 0.39, 0.3, 1)|  
|(0, 1, 1, 1)|(0, 0.65, 0.5, 1)|  
|(1, 1, 0, 1)|(0.75, 0.65, 0, 1)|  
|(1, 0, 1, 1)|(0.75, 0, 0.5, 1)|  
  
## <a name="see-also"></a>関連項目

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [Windows フォームにおけるグラフィックスと描画](graphics-and-drawing-in-windows-forms.md)
- [イメージの色の変更](recoloring-images.md)
