---
title: '方法: イメージを回転、反転、および傾斜させる'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], reflecting
- images [Windows Forms], rotating
- images [Windows Forms], skewing
ms.assetid: a3bf97eb-63ed-425a-ba07-dcc65efb567c
ms.openlocfilehash: 80ac92d545d9be7a4a611038eaaadbbdbe2e8ecf
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981287"
---
# <a name="how-to-rotate-reflect-and-skew-images"></a>方法: イメージを回転、反転、および傾斜させる
イメージの回転、反転、および傾斜を行うには、元のイメージの左上、右上、左下の各コーナーのコピー先のポイントを指定します。 3つのコピー先のポイントは、元の四角形のイメージを平行四辺形にマップするアフィン変換を決定します。  
  
## <a name="example"></a>例  
 たとえば、元の画像が左上隅が (0, 0)、右上隅が (100, 0)、左下隅 (0, 50) の四角形であるとします。 ここで、次のように3つの点をターゲットポイントにマップするとします。  
  
|元のポイント|コピー先のポイント|  
|--------------------|-----------------------|  
|左上 (0, 0)|(200, 20)|  
|右上 (100、0)|(110, 100)|  
|左下 (0, 50)|(250, 30)|  
  
 次の図は、元のイメージと平行四辺形にマップされているイメージを示しています。 元のイメージは、傾斜、反射、回転、および翻訳されています。 元のイメージの上端に沿った x 軸は、(200, 20) と (110, 100) を介して実行される行にマップされます。 元のイメージの左端に沿った y 軸は、(200, 20) と (250, 30) を介して実行される行にマップされます。  
  
 ![平行四辺形にマップされた元のイメージとイメージ。](./media/how-to-rotate-reflect-and-skew-images/reflected-skewed-rotated-illustration.gif)  
  
 次の図は、写真イメージに適用される同様の変換を示しています。  
  
 ![平行四辺形にマップされているクライマと画像の画像。](./media/how-to-rotate-reflect-and-skew-images/reflected-skewed-rotated-photo.png)  
  
 次の図は、メタファイルに適用される同様の変換を示しています。  
  
 ![平行四辺形にマップされた図形とテキストの図。](./media/how-to-rotate-reflect-and-skew-images/reflected-skewed-rotated-metafile.png)  
  
 次の例では、最初の図に示されているイメージを生成します。  
  
 [!code-csharp[System.Drawing.WorkingWithImages#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.WorkingWithImages#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。 `Stripes.bmp`は、システムで有効なイメージへのパスに置き換えてください。  
  
## <a name="see-also"></a>関連項目

- [イメージ、ビットマップ、アイコン、およびメタファイルの操作](working-with-images-bitmaps-icons-and-metafiles.md)
