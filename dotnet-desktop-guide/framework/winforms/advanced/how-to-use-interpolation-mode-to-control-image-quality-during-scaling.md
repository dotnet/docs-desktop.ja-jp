---
title: '方法: 補間モードを使用してスケーリング時の画質を制御する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interpolation mode [Windows Forms], controlling image quality
- images [Windows Forms], scaling
- images [Windows Forms], controlling quality
ms.assetid: fde9bccf-8aa5-4b0d-ba4b-788740627b02
ms.openlocfilehash: ab0ff93b3ee26467c0de448efd31b698167f95c2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981720"
---
# <a name="how-to-use-interpolation-mode-to-control-image-quality-during-scaling"></a>方法: 補間モードを使用してスケーリング時の画質を制御する
オブジェクトの補間モードは、 <xref:System.Drawing.Graphics> GDI + によるイメージのスケーリング (拡大と縮小) に影響します。 <xref:System.Drawing.Drawing2D.InterpolationMode>列挙体は、次の一覧に示すように、複数の補間モードを定義します。  
  
- <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor>  
  
- <xref:System.Drawing.Drawing2D.InterpolationMode.Bilinear>  
  
- <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBilinear>  
  
- <xref:System.Drawing.Drawing2D.InterpolationMode.Bicubic>  
  
- <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic>  
  
 画像を拡大するには、元のイメージ内の各ピクセルが、大きな画像のピクセルのグループにマップされている必要があります。 イメージを圧縮するには、元のイメージのピクセルグループを小さいイメージの1ピクセルにマップする必要があります。 これらのマッピングを実行するアルゴリズムの効果によって、スケーリングされたイメージの品質が決まります。 高品質のスケーリングされたイメージを生成するアルゴリズムでは、より多くの処理時間が必要になる傾向があります。 上記の一覧で <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor> は、は最も品質の低いモードで、 <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic> は最高品質モードです。  
  
 補間モードを設定するには、列挙体のいずれかのメンバーを <xref:System.Drawing.Drawing2D.InterpolationMode> <xref:System.Drawing.Graphics.InterpolationMode%2A> オブジェクトのプロパティに割り当て <xref:System.Drawing.Graphics> ます。  
  
## <a name="example"></a>例  
 次の例では、イメージを描画し、3つの異なる補間モードでイメージを縮小します。  
  
 次の図は、元のイメージと、3つの小さいイメージを示しています。  
  
 ![さまざまな補間設定のイメージを示すスクリーンショット。](./media/how-to-use-interpolation-mode-to-control-image-quality-during-scaling/varied-interpolation-settings.png)  
  
 [!code-csharp[System.Drawing.WorkingWithImages#81](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#81)]
 [!code-vb[System.Drawing.WorkingWithImages#81](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#81)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。  
  
## <a name="see-also"></a>関連項目

- [イメージ、ビットマップ、およびメタファイル](images-bitmaps-and-metafiles.md)
- [イメージ、ビットマップ、アイコン、およびメタファイルの操作](working-with-images-bitmaps-icons-and-metafiles.md)
