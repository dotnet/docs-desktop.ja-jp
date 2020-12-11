---
title: '方法: 自動スケーリングを解除してパフォーマンスを向上させる'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- automatic scaling
- images [Windows Forms], improving performance
- images [Windows Forms], using without automatic scaling
- performance [Windows Forms], improving image
ms.assetid: 5fe2c95d-8653-4d55-bf0d-e5afa28f223b
ms.openlocfilehash: dd1a1545dce33de1ce11938db8495ebf311dadda
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981332"
---
# <a name="how-to-improve-performance-by-avoiding-automatic-scaling"></a>方法: 自動スケーリングを解除してパフォーマンスを向上させる
GDI + では、イメージを描画するときに自動的にスケーリングするため、パフォーマンスが低下する可能性があります。 または、変換先の四角形の大きさをメソッドに渡すことによって、イメージのスケーリングを制御でき <xref:System.Drawing.Graphics.DrawImage%2A> ます。  
  
 たとえば、メソッドの次の呼び出しでは、 <xref:System.Drawing.Graphics.DrawImage%2A> (50, 30) の左上隅を指定しますが、変換先の四角形は指定しません。  
  
 [!code-csharp[System.Drawing.WorkingWithImages#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.WorkingWithImages#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#31)]  
  
 これは必須の引数の数に関して最も簡単な方法ですが、必ずしも効率的であるとは <xref:System.Drawing.Graphics.DrawImage%2A> 限りません。 GDI + によって使用される解像度 (通常は、1インチあたり96ドット) がオブジェクトに格納されている解像度と異なる場合は、 <xref:System.Drawing.Image> メソッドによって <xref:System.Drawing.Graphics.DrawImage%2A> イメージが拡大縮小されます。 たとえば、 <xref:System.Drawing.Image> オブジェクトの幅が216ピクセルで、格納されている水平解像度の値が72ドット/インチであるとします。 216/72 は3であるため、 <xref:System.Drawing.Graphics.DrawImage%2A> 解像度が96ドット/インチの解像度では、幅が3インチになるようにイメージをスケーリングします。 つまり、に <xref:System.Drawing.Graphics.DrawImage%2A> よって、幅が 96x3 = 288 ピクセルのイメージが表示されます。  
  
 画面の解像度が96ドット/インチと異なる場合でも、GDI + は、画面の解像度が96ドット/インチであるかのようにイメージを拡大縮小することがあります。 これは、GDI + <xref:System.Drawing.Graphics> オブジェクトがデバイスコンテキストに関連付けられており、GDI + によってデバイスコンテキストに対して画面の解像度が照会される場合、実際の画面解像度に関係なく、通常は96です。 メソッドでターゲットの四角形を指定することによって、自動スケーリングを回避でき <xref:System.Drawing.Graphics.DrawImage%2A> ます。  
  
## <a name="example"></a>例  
 次の例では、同じイメージを2回描画します。 最初のケースでは、コピー先の四角形の幅と高さが指定されていないため、イメージは自動的に拡大縮小されます。 2番目のケースでは、コピー先の四角形の幅と高さ (ピクセル単位) は、元のイメージの幅と高さと同じになるように指定されています。 次の図は、2回レンダリングされるイメージを示しています。  
  
 ![テクスチャがスケーリングされたイメージを表示するスクリーンショット。](./media/how-to-improve-performance-by-avoiding-automatic-scaling/two-scaled-texture-images.png)  
  
 [!code-csharp[System.Drawing.WorkingWithImages#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.WorkingWithImages#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#32)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。 Texture.jpg を、システムで有効なイメージ名とパスに置き換えます。  
  
## <a name="see-also"></a>関連項目

- [イメージ、ビットマップ、およびメタファイル](images-bitmaps-and-metafiles.md)
- [イメージ、ビットマップ、アイコン、およびメタファイルの操作](working-with-images-bitmaps-icons-and-metafiles.md)
