---
title: '方法: カラー リマップ テーブルを使用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- color tables [Windows Forms], remapping colors with
- custom colors [Windows Forms], creating with color remap table
- color remap tables [Windows Forms], using
ms.assetid: 977df1ce-8665-42d4-9fb1-ef7f0ff63419
ms.openlocfilehash: 360ec30563ee5001d784dc7c4ccdb50563867c29
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981236"
---
# <a name="how-to-use-a-color-remap-table"></a>方法: カラー リマップ テーブルを使用する
再マップとは、カラーリマップテーブルに従ってイメージの色を変換するプロセスです。 カラーリマップテーブルは、オブジェクトの配列です <xref:System.Drawing.Imaging.ColorMap> 。 <xref:System.Drawing.Imaging.ColorMap>配列内の各オブジェクトには、 <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> プロパティとプロパティがあり <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> ます。  
  
 GDI + でイメージを描画すると、イメージの各ピクセルが古い色の配列と比較されます。 ピクセルの色が古い色と一致する場合、色は対応する新しい色に変更されます。 色はレンダリングの場合にのみ変更されます。イメージ自体の色の値 ( <xref:System.Drawing.Image> またはオブジェクトに格納され <xref:System.Drawing.Bitmap> ます) は変更されません。  
  
 リマップされたイメージを描画するには、オブジェクトの配列を初期化し <xref:System.Drawing.Imaging.ColorMap> ます。 オブジェクトのメソッドにその配列を渡し <xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A> <xref:System.Drawing.Imaging.ImageAttributes> 、オブジェクト <xref:System.Drawing.Imaging.ImageAttributes> のメソッドにオブジェクトを渡し <xref:System.Drawing.Graphics.DrawImage%2A> <xref:System.Drawing.Graphics> ます。  
  
## <a name="example"></a>例  
 次の例では、 <xref:System.Drawing.Image> ファイル RemapInput.bmp からオブジェクトを作成します。 このコードでは、1つのオブジェクトで構成されるカラーリマップテーブルを作成し <xref:System.Drawing.Imaging.ColorMap> ます。 <xref:System.Drawing.Imaging.ColorMap.OldColor%2A>オブジェクトのプロパティは `ColorRemap` 赤、 <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> プロパティは青色です。 イメージは再マップせずに1回だけ描画され、再マップされます。 再マッププロセスでは、赤のすべてのピクセルが青に変わります。  
  
 次の図は、左側にある元のイメージと右側に再マップされたイメージを示しています。  
  
 ![元のイメージと再マップされたイメージを示すスクリーンショット。](./media/how-to-use-a-color-remap-table/original-image-remap-colors.png)  
  
 [!code-csharp[System.Drawing.RecoloringImages#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.RecoloringImages#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。  
  
## <a name="see-also"></a>関連項目

- [イメージの色の変更](recoloring-images.md)
- [イメージ、ビットマップ、およびメタファイル](images-bitmaps-and-metafiles.md)
