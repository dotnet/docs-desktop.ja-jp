---
title: '方法: エンコーダーがサポートするパラメーターの確認'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encoder parameters [Windows Forms], determining supported
ms.assetid: f47ae459-e3ce-4d41-a140-2f6c6aea3f44
ms.openlocfilehash: 3e5345180e0ff3321b9ef0b885b836d3e9456f28
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974407"
---
# <a name="how-to-determine-the-parameters-supported-by-an-encoder"></a>方法: エンコーダーがサポートするパラメーターの確認
画質や圧縮レベルなどのイメージパラメーターを調整できますが、特定のイメージエンコーダーでサポートされているパラメーターを把握しておく必要があります。 クラスは、 <xref:System.Drawing.Image> <xref:System.Drawing.Image.GetEncoderParameterList%2A> 特定のエンコーダーでサポートされているイメージパラメーターを判別できるように、メソッドを提供します。 エンコーダーには GUID を指定します。 メソッドは、 <xref:System.Drawing.Image.GetEncoderParameterList%2A> オブジェクトの配列を返し <xref:System.Drawing.Imaging.EncoderParameter> ます。  
  
## <a name="example"></a>例  
 次のコード例では、JPEG エンコーダーでサポートされているパラメーターを出力します。 クラスの概要でパラメーターカテゴリと関連付けられている Guid の一覧を使用して、 <xref:System.Drawing.Imaging.Encoder> 各パラメーターのカテゴリを決定します。  
  
 [!code-csharp[UsingImageEncodersDecoders#3](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#3)]
 [!code-vb[UsingImageEncodersDecoders#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 この例で必要な要素は次のとおりです。  
  
- Windows フォーム アプリケーション  
  
- <xref:System.Windows.Forms.PaintEventArgs>のパラメーターである <xref:System.Windows.Forms.PaintEventHandler> 。  
  
## <a name="see-also"></a>関連項目

- [方法: インストールされたエンコーダーの一覧](how-to-list-installed-encoders.md)
- [ビットマップの種類](types-of-bitmaps.md)
- [マネージド GDI+ でのイメージ エンコーダーおよびイメージ デコーダーの使用](using-image-encoders-and-decoders-in-managed-gdi.md)
