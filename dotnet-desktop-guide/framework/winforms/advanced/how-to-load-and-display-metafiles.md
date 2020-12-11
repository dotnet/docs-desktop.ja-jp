---
title: '方法: メタファイルを読み込んで表示する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], metafiles
- metafiles [Windows Forms], displaying
ms.assetid: 60af1714-f148-4d85-a739-0557965ffa73
ms.openlocfilehash: 6c17e0b2d023ccf80b0d32301b7ee6765edcae9f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981323"
---
# <a name="how-to-load-and-display-metafiles"></a>方法: メタファイルを読み込んで表示する
クラスを <xref:System.Drawing.Imaging.Metafile> 継承するクラスには、 <xref:System.Drawing.Image> ベクターイメージの記録、表示、および検査を行うためのメソッドが用意されています。  
  
## <a name="example"></a>例  
 ベクターイメージ (メタファイル) を画面に表示するには、 <xref:System.Drawing.Imaging.Metafile> オブジェクトとオブジェクトが必要 <xref:System.Drawing.Graphics> です。 ファイル (またはストリーム) の名前をコンストラクターに渡し <xref:System.Drawing.Imaging.Metafile> ます。 オブジェクトを作成したら <xref:System.Drawing.Imaging.Metafile> 、そのオブジェクトを <xref:System.Drawing.Imaging.Metafile> <xref:System.Drawing.Graphics.DrawImage%2A> オブジェクトのメソッドに渡し <xref:System.Drawing.Graphics> ます。  
  
 この例では、 <xref:System.Drawing.Imaging.Metafile> EMF (拡張メタファイル) ファイルからオブジェクトを作成し、(60, 10) の左上隅でイメージを描画します。  
  
 次の図は、指定した位置に描画されたメタファイルを示しています。  
  
 ![画像の位置を示すスクリーンショット。](./media/how-to-load-and-display-metafiles/metafile-drawn-specified-location.png "imageposition2")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.WorkingWithImages#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。  
  
## <a name="see-also"></a>関連項目

- [イメージ、ビットマップ、アイコン、およびメタファイルの操作](working-with-images-bitmaps-icons-and-metafiles.md)
