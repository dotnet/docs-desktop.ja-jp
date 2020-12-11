---
title: '方法: イメージをトリミングおよびスケーリングする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], cropping
- images [Windows Forms], scaling
ms.assetid: 053e3360-bca0-4b25-9afa-0e77a6f17b03
ms.openlocfilehash: 4257431881565f9160f45795111d374cc680dedd
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974409"
---
# <a name="how-to-crop-and-scale-images"></a>方法: イメージをトリミングおよびスケーリングする
<xref:System.Drawing.Graphics>クラスにはいくつかのメソッドが用意されて <xref:System.Drawing.Graphics.DrawImage%2A> います。一部のメソッドには、イメージのトリミングとスケーリングに使用できる変換元と変換先の四角形のパラメーターがあります。  
  
## <a name="example"></a>例  
 次の例では、 <xref:System.Drawing.Image> Apple.gif ディスクファイルからオブジェクトを構築します。 このコードは、apple イメージ全体を元のサイズで描画します。 次に、オブジェクトのメソッドを呼び出して、 <xref:System.Drawing.Graphics.DrawImage%2A> <xref:System.Drawing.Graphics> apple イメージの一部を、元の apple イメージよりも大きいコピー先の四角形に描画します。  
  
 メソッドは、 <xref:System.Drawing.Graphics.DrawImage%2A> ソースの四角形を調べることで、apple のどの部分を描画するかを決定します。これは、3番目、4番目、5番目、および6番目の引数で指定されます。 この場合、apple は幅の75% と高さの75% にトリミングされます。  
  
 メソッドは、 <xref:System.Drawing.Graphics.DrawImage%2A> 2 番目の引数で指定されたコピー先の四角形を確認することにより、トリミングされた apple の描画場所とトリミングされた apple のサイズを決定します。 この場合、コピー先の四角形は、元のイメージよりも30% 広く、30% の高さになります。  
  
 次の図は、オリジナルの apple と、スケーリングされた、トリミングされた apple を示しています。  
  
 ![元のイメージとトリミングされた同じイメージのスクリーンショット。](./media/how-to-crop-and-scale-images/original-image-cropped-image.png)  
  
 [!code-csharp[System.Drawing.WorkingWithImages#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.WorkingWithImages#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。 `Apple.gif`は、システムで有効なイメージファイル名とパスに置き換えてください。  
  
## <a name="see-also"></a>関連項目

- [イメージ、ビットマップ、およびメタファイル](images-bitmaps-and-metafiles.md)
- [イメージ、ビットマップ、アイコン、およびメタファイルの操作](working-with-images-bitmaps-icons-and-metafiles.md)
