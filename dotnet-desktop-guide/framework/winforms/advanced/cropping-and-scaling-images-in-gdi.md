---
title: GDI+ でのイメージのトリミングおよびスケーリング
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, scaling images
- GDI+, cropping images
- images [Windows Forms], cropping
- compressing data [Windows Forms], images
- images [Windows Forms], expansion
- images [Windows Forms], scaling
- rectangles [Windows Forms], source
- rectangles [Windows Forms], destination
- images [Windows Forms], compression
ms.assetid: ad5daf26-005f-45bc-a2af-e0e97777a21a
ms.openlocfilehash: c3cdb06e99770808461f9266fb5f07df9074149b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96975038"
---
# <a name="cropping-and-scaling-images-in-gdi"></a>GDI+ でのイメージのトリミングおよびスケーリング
<xref:System.Drawing.Graphics.DrawImage%2A>クラスのメソッドを使用し <xref:System.Drawing.Graphics> て、ベクターイメージとラスターイメージを描画し、配置することができます。 <xref:System.Drawing.Graphics.DrawImage%2A> はオーバーロードされたメソッドであるため、いくつかの方法で引数を指定できます。  
  
## <a name="drawimage-variations"></a>DrawImage のバリエーション  
 メソッドの1つのバリエーション <xref:System.Drawing.Graphics.DrawImage%2A> は、とを受け取り <xref:System.Drawing.Bitmap> <xref:System.Drawing.Rectangle> ます。 四角形は、描画操作の対象を指定します。つまり、イメージを描画する四角形を指定します。 コピー先の四角形のサイズが元のイメージのサイズと異なる場合、イメージはコピー先の四角形に合わせて拡大縮小されます。 次のコード例は、同じイメージを3回描画する方法を示しています。1回はスケーリングせず、1回は拡張を、もう1回は圧縮を使用します。  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#31)]  
  
 次の図は、3つの画像を示しています。  
  
 ![スケーリング](./media/aboutgdip03-art06.gif "AboutGdip03_Art06")  
  
 メソッドの一部のバリエーションには、 <xref:System.Drawing.Graphics.DrawImage%2A> 変換元の四角形のパラメーターと、変換先の四角形のパラメーターがあります。 Source 四角形パラメーターは、描画する元のイメージの部分を指定します。 コピー先の四角形は、イメージのその部分を描画する四角形を指定します。 コピー先の四角形のサイズがコピー元の四角形のサイズと異なる場合、画像はコピー先の四角形に合わせて拡大縮小されます。  
  
 ファイル Runner.jpg からを構築する方法を次のコード例に示し <xref:System.Drawing.Bitmap> ます。 イメージ全体が、(0, 0) にスケーリングなしで描画されます。 次に、イメージの小さな部分が2回描画されます。1回は圧縮を、もう1回は拡張です。  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#32)]  
  
 次の図は、スケールされていないイメージと、圧縮されたイメージ部分と展開されたイメージ部分を示しています。  
  
 ![トリミングとスケーリング](./media/aboutgdip03-art07.gif "AboutGdip03_Art07")  
  
## <a name="see-also"></a>関連項目

- [イメージ、ビットマップ、およびメタファイル](images-bitmaps-and-metafiles.md)
- [イメージ、ビットマップ、アイコン、およびメタファイルの操作](working-with-images-bitmaps-icons-and-metafiles.md)
