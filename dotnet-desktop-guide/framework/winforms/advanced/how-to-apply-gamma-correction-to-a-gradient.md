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
# <a name="how-to-apply-gamma-correction-to-a-gradient"></a><span data-ttu-id="6bf33-102">方法: グラデーションに対してガンマ補正を適用する</span><span class="sxs-lookup"><span data-stu-id="6bf33-102">How to: Apply Gamma Correction to a Gradient</span></span>
<span data-ttu-id="6bf33-103">ブラシのプロパティをに設定することにより、線状グラデーションブラシのガンマ補正を有効にでき <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> `true` ます。</span><span class="sxs-lookup"><span data-stu-id="6bf33-103">You can enable gamma correction for a linear gradient brush by setting the brush's <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> property to `true`.</span></span> <span data-ttu-id="6bf33-104">ガンマ補正を無効にするには、 <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> プロパティをに設定し `false` ます。</span><span class="sxs-lookup"><span data-stu-id="6bf33-104">You can disable gamma correction by setting the <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> property to `false`.</span></span> <span data-ttu-id="6bf33-105">ガンマ補正は、既定では無効になっています。</span><span class="sxs-lookup"><span data-stu-id="6bf33-105">Gamma correction is disabled by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6bf33-106">例</span><span class="sxs-lookup"><span data-stu-id="6bf33-106">Example</span></span>  

<span data-ttu-id="6bf33-107">次の例は、コントロールのイベントハンドラーから呼び出されるメソッドです <xref:System.Windows.Forms.Control.Paint> 。</span><span class="sxs-lookup"><span data-stu-id="6bf33-107">The following example is a method that is called from a control's <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="6bf33-108">この例では、線状グラデーションブラシを作成し、そのブラシを使用して2つの四角形を塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="6bf33-108">The example creates a linear gradient brush and uses that brush to fill two rectangles.</span></span> <span data-ttu-id="6bf33-109">最初の四角形はガンマ補正なしで塗りつぶされ、2番目の四角形はガンマ補正付きで塗りつぶされます。</span><span class="sxs-lookup"><span data-stu-id="6bf33-109">The first rectangle is filled without gamma correction, and the second rectangle is filled with gamma correction.</span></span>  
  
 <span data-ttu-id="6bf33-110">次の図は、2つの塗りつぶされた四角形を示しています。</span><span class="sxs-lookup"><span data-stu-id="6bf33-110">The following illustration shows the two filled rectangles.</span></span> <span data-ttu-id="6bf33-111">上部の四角形は、ガンマ補正が適用されていないため、途中で暗く見えます。</span><span class="sxs-lookup"><span data-stu-id="6bf33-111">The top rectangle, which does not have gamma correction, appears dark in the middle.</span></span> <span data-ttu-id="6bf33-112">ガンマ補正が適用されている下の四角形は、より均一な輝度を持つように見えます。</span><span class="sxs-lookup"><span data-stu-id="6bf33-112">The bottom rectangle, which has gamma correction, appears to have more uniform intensity.</span></span>  
  
 ![グラデーションで塗りつぶされた2つの四角形。ガンマ補正はありません。](./media/how-to-apply-gamma-correction-to-a-gradient/two-rectangles-gamma-gradient.png)  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6bf33-114">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="6bf33-114">Compiling the Code</span></span>  
 <span data-ttu-id="6bf33-115">前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。</span><span class="sxs-lookup"><span data-stu-id="6bf33-115">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bf33-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="6bf33-116">See also</span></span>

- <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>
- [<span data-ttu-id="6bf33-117">グラデーション ブラシを使用した図形の塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="6bf33-117">Using a Gradient Brush to Fill Shapes</span></span>](using-a-gradient-brush-to-fill-shapes.md)
