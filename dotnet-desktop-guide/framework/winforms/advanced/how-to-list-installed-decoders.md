---
title: '方法: インストールされたデコーダーの一覧'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image codecs [Windows Forms], listing
- image decoders [Windows Forms], listing
ms.assetid: 11417191-8c95-40ca-8024-779e61706fb6
ms.openlocfilehash: 961862d6212b7e76812fc222d3a99f08528d9a16
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981327"
---
# <a name="how-to-list-installed-decoders"></a>方法: インストールされたデコーダーの一覧
コンピューターで使用可能なイメージデコーダーを一覧表示して、アプリケーションが特定のイメージファイル形式を読み取ることができるかどうかを判断することができます。 クラスは、 <xref:System.Drawing.Imaging.ImageCodecInfo> <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> 使用可能なイメージデコーダーを判別できるように、静的メソッドを提供します。 <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> オブジェクトの配列を返し <xref:System.Drawing.Imaging.ImageCodecInfo> ます。  
  
## <a name="example"></a>例  
 次のコード例では、インストールされているデコーダーとそのプロパティ値の一覧を出力します。  
  
 [!code-csharp[UsingImageEncodersDecoders#2](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#2)]
 [!code-vb[UsingImageEncodersDecoders#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#2)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 この例で必要な要素は次のとおりです。  
  
- Windows フォーム アプリケーション  
  
- <xref:System.Windows.Forms.PaintEventArgs>のパラメーターである <xref:System.Windows.Forms.PaintEventHandler> 。  
  
## <a name="see-also"></a>関連項目

- [方法: インストールされたエンコーダーの一覧](how-to-list-installed-encoders.md)
- [マネージド GDI+ でのイメージ エンコーダーおよびイメージ デコーダーの使用](using-image-encoders-and-decoders-in-managed-gdi.md)
