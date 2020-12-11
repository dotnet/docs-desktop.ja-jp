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
# <a name="how-to-create-a-linear-gradient"></a><span data-ttu-id="01123-102">方法: 線形グラデーションを作成する</span><span class="sxs-lookup"><span data-stu-id="01123-102">How to: Create a Linear Gradient</span></span>
<span data-ttu-id="01123-103">GDI + は、水平方向、垂直方向、および斜線の線状グラデーションを提供します。</span><span class="sxs-lookup"><span data-stu-id="01123-103">GDI+ provides horizontal, vertical, and diagonal linear gradients.</span></span> <span data-ttu-id="01123-104">既定では、線状グラデーションの色は一様に変化します。</span><span class="sxs-lookup"><span data-stu-id="01123-104">By default, the color in a linear gradient changes uniformly.</span></span> <span data-ttu-id="01123-105">ただし、線状グラデーションをカスタマイズして、色が一様でない方法で変化するようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="01123-105">However, you can customize a linear gradient so that the color changes in a non-uniform fashion.</span></span>  

> [!NOTE]
> <span data-ttu-id="01123-106">この記事の例は、コントロールのイベントハンドラーから呼び出されるメソッドです <xref:System.Windows.Forms.Control.Paint> 。</span><span class="sxs-lookup"><span data-stu-id="01123-106">The examples in this article are methods that are called from a control's <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  

<span data-ttu-id="01123-107">次の例では、水平方向の線状グラデーションブラシを使用して、直線、楕円、および四角形を塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="01123-107">The following example fills a line, an ellipse, and a rectangle with a horizontal linear gradient brush.</span></span>  
  
<span data-ttu-id="01123-108">コンストラクターは4つの <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> 引数を受け取ります。2つの点と2つの色です。</span><span class="sxs-lookup"><span data-stu-id="01123-108">The <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> constructor receives four arguments: two points and two colors.</span></span> <span data-ttu-id="01123-109">最初のポイント (0, 10) は最初の色 (赤) に関連付けられ、2番目のポイント (200, 10) は2番目の色 (青) に関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="01123-109">The first point (0, 10) is associated with the first color (red), and the second point (200, 10) is associated with the second color (blue).</span></span> <span data-ttu-id="01123-110">予想どおり、(0, 10) から (200, 10) に引かれた直線は、赤から青に徐々に変化します。</span><span class="sxs-lookup"><span data-stu-id="01123-110">As you would expect, the line drawn from (0, 10) to (200, 10) changes gradually from red to blue.</span></span>  
  
 <span data-ttu-id="01123-111">ポイント (0, 10) と (200, 10) の10秒は重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="01123-111">The 10s in the points (0, 10) and (200, 10) are not important.</span></span> <span data-ttu-id="01123-112">重要なのは、2つの点の2番目の座標が同じであり、線が横方向に接続していることです。</span><span class="sxs-lookup"><span data-stu-id="01123-112">What is important is that the two points have the same second coordinate — the line connecting them is horizontal.</span></span> <span data-ttu-id="01123-113">楕円と四角形も、水平座標が 0 ~ 200 の範囲で赤から青に徐々に変化します。</span><span class="sxs-lookup"><span data-stu-id="01123-113">The ellipse and the rectangle also change gradually from red to blue as the horizontal coordinate goes from 0 to 200.</span></span>  
  
 <span data-ttu-id="01123-114">次の図は、線、楕円、および四角形を示しています。</span><span class="sxs-lookup"><span data-stu-id="01123-114">The following illustration shows the line, the ellipse, and the rectangle.</span></span> <span data-ttu-id="01123-115">水平方向の座標が200を超えると色のグラデーションが繰り返されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="01123-115">Note that the color gradient repeats itself as the horizontal coordinate increases beyond 200.</span></span>  
  
 ![線、楕円、および色のグラデーションで塗りつぶされた四角形。](./media/how-to-create-a-linear-gradient/gradient-line-ellipse-rectangle.png)  
  
## <a name="to-use-horizontal-linear-gradients"></a><span data-ttu-id="01123-117">水平方向の線状グラデーションを使用するには</span><span class="sxs-lookup"><span data-stu-id="01123-117">To use horizontal linear gradients</span></span>  
  
- <span data-ttu-id="01123-118">3番目と4番目の引数として、不透明な赤と不透明な青をそれぞれ渡します。</span><span class="sxs-lookup"><span data-stu-id="01123-118">Pass in the opaque red and opaque blue as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#21)]
     [!code-vb[System.Drawing.UsingaGradientBrush#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#21)]  
  
 <span data-ttu-id="01123-119">前の例では、0の水平方向の座標から200の水平方向の座標に移動したときに、カラーコンポーネントが直線的に変化します。</span><span class="sxs-lookup"><span data-stu-id="01123-119">In the preceding example, the color components change linearly as you move from a horizontal coordinate of 0 to a horizontal coordinate of 200.</span></span> <span data-ttu-id="01123-120">たとえば、最初の座標が 0 ~ 200 の中間にある点には、0から255の中間にある青のコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="01123-120">For example, a point whose first coordinate is halfway between 0 and 200 will have a blue component that is halfway between 0 and 255.</span></span>  
  
 <span data-ttu-id="01123-121">GDI + を使用すると、グラデーションのある端から別の端に色が変化する方法を調整できます。</span><span class="sxs-lookup"><span data-stu-id="01123-121">GDI+ allows you to adjust the way a color varies from one edge of a gradient to the other.</span></span> <span data-ttu-id="01123-122">次の表に従って、黒から赤に変化するグラデーションブラシを作成するとします。</span><span class="sxs-lookup"><span data-stu-id="01123-122">Suppose you want to create a gradient brush that changes from black to red according to the following table.</span></span>  
  
|<span data-ttu-id="01123-123">水平方向の座標</span><span class="sxs-lookup"><span data-stu-id="01123-123">Horizontal coordinate</span></span>|<span data-ttu-id="01123-124">RGB コンポーネント</span><span class="sxs-lookup"><span data-stu-id="01123-124">RGB components</span></span>|  
|---------------------------|--------------------|  
|<span data-ttu-id="01123-125">0</span><span class="sxs-lookup"><span data-stu-id="01123-125">0</span></span>|<span data-ttu-id="01123-126">(0, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="01123-126">(0, 0, 0)</span></span>|  
|<span data-ttu-id="01123-127">40</span><span class="sxs-lookup"><span data-stu-id="01123-127">40</span></span>|<span data-ttu-id="01123-128">(128, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="01123-128">(128, 0, 0)</span></span>|  
|<span data-ttu-id="01123-129">200</span><span class="sxs-lookup"><span data-stu-id="01123-129">200</span></span>|<span data-ttu-id="01123-130">(255, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="01123-130">(255, 0, 0)</span></span>|  
  
 <span data-ttu-id="01123-131">水平方向の座標が 0 ~ 200 のうち20% である場合は、赤の成分が半分の輝度であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="01123-131">Note that the red component is at half intensity when the horizontal coordinate is only 20 percent of the way from 0 to 200.</span></span>  
  
 <span data-ttu-id="01123-132">次の例では、3つの相対 <xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A?displayProperty=nameWithType> 輝度を3つの相対位置に関連付けるように、プロパティを設定しています。</span><span class="sxs-lookup"><span data-stu-id="01123-132">The following example sets the <xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A?displayProperty=nameWithType> property to associate three relative intensities with three relative positions.</span></span> <span data-ttu-id="01123-133">前の表のように、相対輝度0.5 は0.2 の相対位置に関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="01123-133">As in the preceding table, a relative intensity of 0.5 is associated with a relative position of 0.2.</span></span> <span data-ttu-id="01123-134">このコードによって、楕円と四角形がグラデーションブラシで塗りつぶされます。</span><span class="sxs-lookup"><span data-stu-id="01123-134">The code fills an ellipse and a rectangle with the gradient brush.</span></span>  
  
 <span data-ttu-id="01123-135">次の図は、結果として得られる楕円と四角形を示しています。</span><span class="sxs-lookup"><span data-stu-id="01123-135">The following illustration shows the resulting ellipse and rectangle.</span></span>  
  
 ![楕円と、水平色グラデーションで塗りつぶされた四角形。](./media/how-to-create-a-linear-gradient/gradient-ellipse-rectangle.png)  

## <a name="to-customize-linear-gradients"></a><span data-ttu-id="01123-137">線状グラデーションをカスタマイズするには</span><span class="sxs-lookup"><span data-stu-id="01123-137">To customize linear gradients</span></span>  
  
- <span data-ttu-id="01123-138">不透明な黒と不透明な赤をそれぞれ3番目と4番目の引数として渡します。</span><span class="sxs-lookup"><span data-stu-id="01123-138">Pass in the opaque black and opaque red as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#22)]
     [!code-vb[System.Drawing.UsingaGradientBrush#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#22)]  
  
 <span data-ttu-id="01123-139">前の例のグラデーションは水平になっています。つまり、水平線に沿って移動すると、色が徐々に変化します。</span><span class="sxs-lookup"><span data-stu-id="01123-139">The gradients in the preceding examples have been horizontal; that is, the color changes gradually as you move along any horizontal line.</span></span> <span data-ttu-id="01123-140">また、縦方向のグラデーションおよび斜線グラデーションを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="01123-140">You can also define vertical gradients and diagonal gradients.</span></span>  
  
 <span data-ttu-id="01123-141">次の例では、ポイント (0, 0) と (200, 100) を <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> コンストラクターに渡します。</span><span class="sxs-lookup"><span data-stu-id="01123-141">The following example passes the points (0, 0) and (200, 100) to a <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> constructor.</span></span> <span data-ttu-id="01123-142">青色は (0, 0) に関連付けられており、緑色は (200, 100) に関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="01123-142">The color blue is associated with (0, 0), and the color green is associated with (200, 100).</span></span> <span data-ttu-id="01123-143">直線 (ペンの幅が 10) と楕円が線状グラデーションブラシで塗りつぶされます。</span><span class="sxs-lookup"><span data-stu-id="01123-143">A line (with pen width 10) and an ellipse are filled with the linear gradient brush.</span></span>  
  
 <span data-ttu-id="01123-144">次の図は、直線と楕円を示しています。</span><span class="sxs-lookup"><span data-stu-id="01123-144">The following illustration shows the line and the ellipse.</span></span> <span data-ttu-id="01123-145">この楕円の色は、(0, 0) および (200, 100) を通過する直線に平行して移動すると、徐々に変化することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="01123-145">Note that the color in the ellipse changes gradually as you move along any line that is parallel to the line passing through (0, 0) and (200, 100).</span></span>  
  
 ![線と、斜線 (色のグラデーション) で塗りつぶされた楕円。](./media/how-to-create-a-linear-gradient/gradient-line-ellipse.png)  
  
## <a name="to-create-diagonal-linear-gradients"></a><span data-ttu-id="01123-147">対角線方向の線形グラデーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="01123-147">To create diagonal linear gradients</span></span>  
  
- <span data-ttu-id="01123-148">3番目と4番目の引数として、不透明な青と不透明な緑をそれぞれ渡します。</span><span class="sxs-lookup"><span data-stu-id="01123-148">Pass in the opaque blue and opaque green as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#23)]
     [!code-vb[System.Drawing.UsingaGradientBrush#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="01123-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="01123-149">See also</span></span>

- [<span data-ttu-id="01123-150">グラデーション ブラシを使用した図形の塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="01123-150">Using a Gradient Brush to Fill Shapes</span></span>](using-a-gradient-brush-to-fill-shapes.md)
- [<span data-ttu-id="01123-151">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="01123-151">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
