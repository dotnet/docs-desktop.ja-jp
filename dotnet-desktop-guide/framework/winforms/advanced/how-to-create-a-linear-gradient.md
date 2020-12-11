---
title: '方法: 線形グラデーションを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- linear gradients [Windows Forms], creating
- gradients [Windows Forms], creating linear
- colors [Windows Forms], creating linear gradients
- gradients
ms.assetid: 6c88e1cc-1217-4399-ac12-cb37592b9f01
ms.openlocfilehash: e55d27b454579268658192ae56daa52e0b28bb83
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974989"
---
# <a name="how-to-create-a-linear-gradient"></a>方法: 線形グラデーションを作成する
GDI + は、水平方向、垂直方向、および斜線の線状グラデーションを提供します。 既定では、線状グラデーションの色は一様に変化します。 ただし、線状グラデーションをカスタマイズして、色が一様でない方法で変化するようにすることができます。  

> [!NOTE]
> この記事の例は、コントロールのイベントハンドラーから呼び出されるメソッドです <xref:System.Windows.Forms.Control.Paint> 。  

次の例では、水平方向の線状グラデーションブラシを使用して、直線、楕円、および四角形を塗りつぶします。  
  
コンストラクターは4つの <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> 引数を受け取ります。2つの点と2つの色です。 最初のポイント (0, 10) は最初の色 (赤) に関連付けられ、2番目のポイント (200, 10) は2番目の色 (青) に関連付けられます。 予想どおり、(0, 10) から (200, 10) に引かれた直線は、赤から青に徐々に変化します。  
  
 ポイント (0, 10) と (200, 10) の10秒は重要ではありません。 重要なのは、2つの点の2番目の座標が同じであり、線が横方向に接続していることです。 楕円と四角形も、水平座標が 0 ~ 200 の範囲で赤から青に徐々に変化します。  
  
 次の図は、線、楕円、および四角形を示しています。 水平方向の座標が200を超えると色のグラデーションが繰り返されることに注意してください。  
  
 ![線、楕円、および色のグラデーションで塗りつぶされた四角形。](./media/how-to-create-a-linear-gradient/gradient-line-ellipse-rectangle.png)  
  
## <a name="to-use-horizontal-linear-gradients"></a>水平方向の線状グラデーションを使用するには  
  
- 3番目と4番目の引数として、不透明な赤と不透明な青をそれぞれ渡します。  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#21)]
     [!code-vb[System.Drawing.UsingaGradientBrush#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#21)]  
  
 前の例では、0の水平方向の座標から200の水平方向の座標に移動したときに、カラーコンポーネントが直線的に変化します。 たとえば、最初の座標が 0 ~ 200 の中間にある点には、0から255の中間にある青のコンポーネントがあります。  
  
 GDI + を使用すると、グラデーションのある端から別の端に色が変化する方法を調整できます。 次の表に従って、黒から赤に変化するグラデーションブラシを作成するとします。  
  
|水平方向の座標|RGB コンポーネント|  
|---------------------------|--------------------|  
|0|(0, 0, 0)|  
|40|(128, 0, 0)|  
|200|(255, 0, 0)|  
  
 水平方向の座標が 0 ~ 200 のうち20% である場合は、赤の成分が半分の輝度であることに注意してください。  
  
 次の例では、3つの相対 <xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A?displayProperty=nameWithType> 輝度を3つの相対位置に関連付けるように、プロパティを設定しています。 前の表のように、相対輝度0.5 は0.2 の相対位置に関連付けられています。 このコードによって、楕円と四角形がグラデーションブラシで塗りつぶされます。  
  
 次の図は、結果として得られる楕円と四角形を示しています。  
  
 ![楕円と、水平色グラデーションで塗りつぶされた四角形。](./media/how-to-create-a-linear-gradient/gradient-ellipse-rectangle.png)  

## <a name="to-customize-linear-gradients"></a>線状グラデーションをカスタマイズするには  
  
- 不透明な黒と不透明な赤をそれぞれ3番目と4番目の引数として渡します。  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#22)]
     [!code-vb[System.Drawing.UsingaGradientBrush#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#22)]  
  
 前の例のグラデーションは水平になっています。つまり、水平線に沿って移動すると、色が徐々に変化します。 また、縦方向のグラデーションおよび斜線グラデーションを定義することもできます。  
  
 次の例では、ポイント (0, 0) と (200, 100) を <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> コンストラクターに渡します。 青色は (0, 0) に関連付けられており、緑色は (200, 100) に関連付けられています。 直線 (ペンの幅が 10) と楕円が線状グラデーションブラシで塗りつぶされます。  
  
 次の図は、直線と楕円を示しています。 この楕円の色は、(0, 0) および (200, 100) を通過する直線に平行して移動すると、徐々に変化することに注意してください。  
  
 ![線と、斜線 (色のグラデーション) で塗りつぶされた楕円。](./media/how-to-create-a-linear-gradient/gradient-line-ellipse.png)  
  
## <a name="to-create-diagonal-linear-gradients"></a>対角線方向の線形グラデーションを作成するには  
  
- 3番目と4番目の引数として、不透明な青と不透明な緑をそれぞれ渡します。  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#23)]
     [!code-vb[System.Drawing.UsingaGradientBrush#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#23)]  
  
## <a name="see-also"></a>関連項目

- [グラデーション ブラシを使用した図形の塗りつぶし](using-a-gradient-brush-to-fill-shapes.md)
- [Windows フォームにおけるグラフィックスと描画](graphics-and-drawing-in-windows-forms.md)
