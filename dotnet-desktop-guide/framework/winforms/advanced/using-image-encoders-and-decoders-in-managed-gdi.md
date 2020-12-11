---
title: マネージド GDI+ でのイメージ エンコーダーおよびイメージ デコーダーの使用
ms.date: 03/30/2017
helpviewer_keywords:
- image encoders [Windows Forms], using
- image decoders [Windows Forms], using
ms.assetid: 0e838ea1-4e7e-4334-b882-ab25df607b8b
ms.openlocfilehash: 8cd66f3ce3da462867da9e23c38b3f6d877c058c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981187"
---
# <a name="using-image-encoders-and-decoders-in-managed-gdi"></a>マネージド GDI+ でのイメージ エンコーダーおよびイメージ デコーダーの使用
名前空間には、 <xref:System.Drawing> <xref:System.Drawing.Image> イメージを <xref:System.Drawing.Bitmap> 格納および操作するためのクラスとクラスが用意されています。 GDI + でイメージエンコーダーを使用すると、イメージをメモリからディスクに書き込むことができます。 GDI + でイメージデコーダーを使用すると、ディスクからメモリにイメージを読み込むことができます。 エンコーダーは、オブジェクトまたはオブジェクト内のデータを、 <xref:System.Drawing.Image> <xref:System.Drawing.Bitmap> 指定されたディスクファイル形式に変換します。 デコーダーは、ディスクファイル内のデータを、オブジェクトおよびオブジェクトが必要とする形式に変換し <xref:System.Drawing.Image> <xref:System.Drawing.Bitmap> ます。  
  
 GDI + には、次のファイルの種類をサポートするエンコーダーとデコーダーが組み込まれています。  
  
- BMP  
  
- GIF  
  
- JPEG  
  
- PNG  
  
- TIFF  
  
 GDI + には、次のファイルの種類をサポートする組み込みのデコーダーもあります。  
  
- WMF  
  
- EMF  
  
- ICON  
  
 次のトピックでは、エンコーダーとデコーダーについてさらに詳しく説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [方法: インストールされたエンコーダーの一覧](how-to-list-installed-encoders.md)  
 コンピューターで使用可能なエンコーダーを一覧表示する方法について説明します。  
  
 [方法: インストールされたデコーダーの一覧](how-to-list-installed-decoders.md)  
 コンピューターで使用可能なデコーダーを一覧表示する方法について説明します。  
  
 [方法: エンコーダーがサポートするパラメーターの確認](how-to-determine-the-parameters-supported-by-an-encoder.md)  
 エンコーダーによってサポートされるの一覧を表示する方法について説明し <xref:System.Drawing.Imaging.EncoderParameters> ます。  
  
 [方法: BMP イメージから PNG イメージへの変換](how-to-convert-a-bmp-image-to-a-png-image.md)  
 イメージを別のイメージ形式で保存する方法について説明します。  
  
 [方法: JPEG 圧縮レベルの設定](how-to-set-jpeg-compression-level.md)  
 イメージの品質レベルを変更する方法について説明します。  
  
## <a name="reference"></a>関連項目  
 <xref:System.Drawing.Image>  
  
 <xref:System.Drawing.Bitmap>  
  
 <xref:System.Drawing.Imaging.ImageCodecInfo>  
  
 <xref:System.Drawing.Imaging.EncoderParameter>  
  
 <xref:System.Drawing.Imaging.Encoder>  
  
## <a name="related-sections"></a>関連項目  
 [GDI+ マネージド コードについて](about-gdi-managed-code.md)  
  
 [イメージ、ビットマップ、およびメタファイル](images-bitmaps-and-metafiles.md)
