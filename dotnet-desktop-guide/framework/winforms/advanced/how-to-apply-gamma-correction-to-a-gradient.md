---
title: '方法: グラデーションに対してガンマ補正を適用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- gradient brushes [Windows Forms], gamma correction
- gradients [Windows Forms], gamma correction
ms.assetid: da4690e7-5fac-4fd2-b3f0-5cb35c165b92
ms.openlocfilehash: e812e441233c1d29a67dac639048e20a659549f0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980086"
---
# <a name="how-to-apply-gamma-correction-to-a-gradient"></a>方法: グラデーションに対してガンマ補正を適用する
ブラシのプロパティをに設定することにより、線状グラデーションブラシのガンマ補正を有効にでき <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> `true` ます。 ガンマ補正を無効にするには、 <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> プロパティをに設定し `false` ます。 ガンマ補正は、既定では無効になっています。  
  
## <a name="example"></a>例  

次の例は、コントロールのイベントハンドラーから呼び出されるメソッドです <xref:System.Windows.Forms.Control.Paint> 。 この例では、線状グラデーションブラシを作成し、そのブラシを使用して2つの四角形を塗りつぶします。 最初の四角形はガンマ補正なしで塗りつぶされ、2番目の四角形はガンマ補正付きで塗りつぶされます。  
  
 次の図は、2つの塗りつぶされた四角形を示しています。 上部の四角形は、ガンマ補正が適用されていないため、途中で暗く見えます。 ガンマ補正が適用されている下の四角形は、より均一な輝度を持つように見えます。  
  
 ![グラデーションで塗りつぶされた2つの四角形。ガンマ補正はありません。](./media/how-to-apply-gamma-correction-to-a-gradient/two-rectangles-gamma-gradient.png)  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>
- [グラデーション ブラシを使用した図形の塗りつぶし](using-a-gradient-brush-to-fill-shapes.md)
