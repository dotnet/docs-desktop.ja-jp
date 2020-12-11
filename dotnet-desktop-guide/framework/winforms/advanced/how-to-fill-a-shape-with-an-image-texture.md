---
title: '方法: イメージ テクスチャによって図形を塗りつぶす'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], using with brushes
- bitmaps [Windows Forms], using texture
- shapes [Windows Forms], filling with images
ms.assetid: 508da5a6-2433-4d2b-9680-eaeae4e96e3b
ms.openlocfilehash: 42c456137f84c6fa657ba5a09727eae052a45376
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981851"
---
# <a name="how-to-fill-a-shape-with-an-image-texture"></a>方法: イメージ テクスチャによって図形を塗りつぶす
クラスとクラスを使用して、閉じた図形にテクスチャを埋め込むことができ <xref:System.Drawing.Image> <xref:System.Drawing.TextureBrush> ます。  
  
## <a name="example"></a>例  
 次の例では、楕円にイメージを塗りつぶします。 このコードは、 <xref:System.Drawing.Image> オブジェクトを構築し、そのオブジェクトのアドレスを <xref:System.Drawing.Image> 引数としてコンストラクターに渡し <xref:System.Drawing.TextureBrush.%23ctor%2A> ます。 3番目のステートメントはイメージをスケーリングし、4番目のステートメントは、拡大縮小されたイメージの繰り返しコピーを楕円に入力します。  
  
 次のコードでは、プロパティには、 <xref:System.Drawing.TextureBrush.Transform%2A> イメージが描画される前に適用される変換が含まれています。 元のイメージの幅が640ピクセル、高さが480ピクセルであると仮定します。 変換は、水平方向と垂直方向のスケーリング値を設定することによって、イメージを75×75に縮小します。  
  
> [!NOTE]
> 次の例では、イメージのサイズは75×75、楕円のサイズは150×250です。 画像は塗りつぶされている楕円より小さいため、楕円は画像で並べられています。 タイルは、図形の境界に到達するまで、画像が水平方向および垂直方向に繰り返されることを意味します。 タイルの詳細については、「 [方法: イメージを使用して図形を並べ](how-to-tile-a-shape-with-an-image.md)て表示する」を参照してください。  
  
 [!code-csharp[System.Drawing.UsingABrush#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingABrush#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。  
  
## <a name="see-also"></a>関連項目

- [ブラシを使用した図形の塗りつぶし](using-a-brush-to-fill-shapes.md)
