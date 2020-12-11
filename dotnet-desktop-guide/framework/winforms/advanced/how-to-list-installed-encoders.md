---
title: '方法: インストールされたエンコーダーの一覧'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image codecs [Windows Forms], listing
- image encoders [Windows Forms], listing
ms.assetid: 49e8e4e9-7a67-42d9-86bf-08821cdc282e
ms.openlocfilehash: 2634dd96b3aa5edcecde092919eb328b7f3dadc3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981828"
---
# <a name="how-to-list-installed-encoders"></a>方法: インストールされたエンコーダーの一覧
アプリケーションが特定のイメージファイル形式に保存できるかどうかを判断するために、コンピューターで使用可能なイメージエンコーダーを一覧表示することができます。 クラスには静的メソッドが用意されて <xref:System.Drawing.Imaging.ImageCodecInfo> <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> いるため、使用できるイメージエンコーダーを特定できます。 <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> オブジェクトの配列を返し <xref:System.Drawing.Imaging.ImageCodecInfo> ます。  
  
## <a name="example"></a>例  
 次のコード例では、インストールされているエンコーダーとそのプロパティ値の一覧を出力します。  
  
 [!code-csharp[UsingImageEncodersDecoders#1](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#1)]
 [!code-vb[UsingImageEncodersDecoders#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 この例で必要な要素は次のとおりです。  
  
- Windows フォーム アプリケーション  
  
- <xref:System.Windows.Forms.PaintEventArgs>のパラメーターである <xref:System.Windows.Forms.PaintEventHandler> 。  
  
## <a name="see-also"></a>関連項目

- [方法: インストールされたデコーダーの一覧](how-to-list-installed-decoders.md)
- [マネージド GDI+ でのイメージ エンコーダーおよびイメージ デコーダーの使用](using-image-encoders-and-decoders-in-managed-gdi.md)
