---
title: GDI+ でのイメージの描画、配置、およびクローン作成
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- raster images [Windows Forms]
- images [Windows Forms], positioning
- drawing [Windows Forms], images
- drawing [Windows Forms], raster images
- images [Windows Forms], cloning
- images [Windows Forms], drawing
- GDI+, drawing images
- GDI+, cloning images
- GDI+, positioning images
ms.assetid: 09f0c07a-19c0-43b4-90a2-862a10545ce8
ms.openlocfilehash: b5f98e7bdef9ff8ed0a4cd0e040cb92a31f30503
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96979843"
---
# <a name="drawing-positioning-and-cloning-images-in-gdi"></a>GDI+ でのイメージの描画、配置、およびクローン作成
クラスを使用して、ラスターイメージを読み込んで表示することができ <xref:System.Drawing.Bitmap> ます。また、クラスを使用して、 <xref:System.Drawing.Imaging.Metafile> ベクターイメージを読み込んで表示することもできます。 <xref:System.Drawing.Bitmap>クラスと <xref:System.Drawing.Imaging.Metafile> クラスは、クラスから継承され <xref:System.Drawing.Image> ます。 ベクターイメージを表示するには、クラスのインスタンスとが必要 <xref:System.Drawing.Graphics> <xref:System.Drawing.Imaging.Metafile> です。 ラスターイメージを表示するには、クラスのインスタンスとが必要 <xref:System.Drawing.Graphics> <xref:System.Drawing.Bitmap> です。 クラスのインスタンスに <xref:System.Drawing.Graphics> <xref:System.Drawing.Graphics.DrawImage%2A> <xref:System.Drawing.Imaging.Metafile> は、引数としてまたはを受け取るメソッドが用意されて <xref:System.Drawing.Bitmap> います。  
  
## <a name="file-types-and-cloning"></a>ファイルの種類と複製  
 次のコード例では、Climber.jpg ファイルからを構築し、ビットマップを表示する方法を示し <xref:System.Drawing.Bitmap> ます。 イメージの左上隅の宛先ポイント (10, 10) は、2番目と3番目のパラメーターで指定します。  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#11)]  
  
 次の図は、イメージを示しています。  
  
 ![イメージ サンプル](./media/aboutgdip03-art04.gif "AboutGdip03_Art04")  
  
 オブジェクトは、 <xref:System.Drawing.Bitmap> さまざまなグラフィックスファイル形式 (BMP、GIF、JPEG、EXIF、PNG、TIFF、ICON) から構築できます。  
  
 次のコード例は、さまざまな <xref:System.Drawing.Bitmap> 種類のファイルからオブジェクトを作成し、ビットマップを表示する方法を示しています。  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#12)]  
  
 クラスには、 <xref:System.Drawing.Bitmap> <xref:System.Drawing.Bitmap.Clone%2A> 既存ののコピーを作成するために使用できるメソッドが用意されて <xref:System.Drawing.Bitmap> います。 <xref:System.Drawing.Bitmap.Clone%2A>メソッドには、コピーする元のビットマップの部分を指定するために使用できるソース四角形パラメーターがあります。 次のコード例では、 <xref:System.Drawing.Bitmap> 既存のの上半分を複製してを作成する方法を示し <xref:System.Drawing.Bitmap> ます。 次に、両方のイメージが描画されます。  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#13)]  
  
 次の図は、2つのイメージを示しています。  
  
 ![トリミング](./media/aboutgdip03-art05.gif "AboutGdip03_Art05")  
  
## <a name="see-also"></a>関連項目

- [イメージ、ビットマップ、およびメタファイル](images-bitmaps-and-metafiles.md)
- [方法: 描画する Graphics オブジェクトを作成する](how-to-create-graphics-objects-for-drawing.md)
- [イメージ、ビットマップ、アイコン、およびメタファイルの操作](working-with-images-bitmaps-icons-and-metafiles.md)
