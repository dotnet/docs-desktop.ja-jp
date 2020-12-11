---
title: '方法: 純色で図形を塗りつぶす'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], adding to shapes
- shapes [Windows Forms], filling
ms.assetid: 06088b31-bac9-4ef3-9ebe-06c2c764d6df
ms.openlocfilehash: d6fe7a252029ff80f21d99f7342fabb1d29fbe24
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981336"
---
# <a name="how-to-fill-a-shape-with-a-solid-color"></a>方法: 純色で図形を塗りつぶす
純色で図形を塗りつぶすには、オブジェクトを作成 <xref:System.Drawing.SolidBrush> し、その <xref:System.Drawing.SolidBrush> オブジェクトを引数としてクラスの fill メソッドの1つに渡し <xref:System.Drawing.Graphics> ます。 次の例では、楕円に赤の色を入力する方法を示します。  
  
## <a name="example"></a>例  
 次のコードでは、 <xref:System.Drawing.SolidBrush.%23ctor%2A> コンストラクターは <xref:System.Drawing.Color> オブジェクトを唯一の引数として受け取ります。 メソッドによって使用される値は、 <xref:System.Drawing.Color.FromArgb%2A> 色のアルファ、赤、緑、および青のコンポーネントを表します。 これらの値はそれぞれ 0 ~ 255 の範囲で指定する必要があります。 最初の255は、色が完全に不透明であることを示します。2番目の255は、赤のコンポーネントの輝度が完全であることを示します。 2つの0は、緑と青のコンポーネントの両方の輝度が0であることを示します。  
  
 メソッドに渡される4つの数値 (0、0、100、60) は、 <xref:System.Drawing.Graphics.FillEllipse%2A> 楕円の外接する四角形の位置とサイズを指定します。 四角形には、(0, 0) の左上隅、幅100、および高さ60があります。  
  
 [!code-csharp[System.Drawing.UsingABrush#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingABrush#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。  
  
## <a name="see-also"></a>関連項目

- [ブラシを使用した図形の塗りつぶし](using-a-brush-to-fill-shapes.md)
