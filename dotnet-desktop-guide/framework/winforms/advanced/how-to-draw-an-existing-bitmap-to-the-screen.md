---
title: '方法: 既存のビットマップを画面に描画する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [Windows Forms], displaying in Windows Forms
- bitmaps [Windows Forms], loading in Windows Forms applications
- images [Windows Forms], displaying on Windows Forms
ms.assetid: 5bc558d7-b326-4050-a834-b8600da0de95
ms.openlocfilehash: 90511adf9caffe7952e270d6fe32dd85162a29d7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981391"
---
# <a name="how-to-draw-an-existing-bitmap-to-the-screen"></a>方法: 既存のビットマップを画面に描画する
画面には、既存のイメージを簡単に描画できます。 まず <xref:System.Drawing.Bitmap> 、ファイル名を受け取るビットマップコンストラクターを使用して、オブジェクトを作成する必要があり <xref:System.Drawing.Bitmap.%23ctor%28System.String%29> ます。 このコンストラクターは、BMP、GIF、JPEG、PNG、TIFF など、いくつかの異なるファイル形式のイメージを受け入れます。 オブジェクトを作成したら <xref:System.Drawing.Bitmap> 、そのオブジェクトを <xref:System.Drawing.Bitmap> <xref:System.Drawing.Graphics.DrawImage%2A> オブジェクトのメソッドに渡し <xref:System.Drawing.Graphics> ます。  
  
## <a name="example"></a>例  
 この例では、 <xref:System.Drawing.Bitmap> JPEG ファイルからオブジェクトを作成し、(60, 10) の左上隅にビットマップを描画します。  
  
 次の図は、指定した位置に描画されたビットマップを示しています。  
  
 ![指定された位置にあるイメージを示すスクリーンショット。](./media/how-to-draw-an-existing-bitmap-to-the-screen/bitmap-specified-position.png)  
  
 [!code-csharp[System.Drawing.WorkingWithImages#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.WorkingWithImages#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。  
  
## <a name="see-also"></a>関連項目

- [Windows フォームにおけるグラフィックスと描画](graphics-and-drawing-in-windows-forms.md)
- [イメージ、ビットマップ、アイコン、およびメタファイルの操作](working-with-images-bitmaps-icons-and-metafiles.md)
