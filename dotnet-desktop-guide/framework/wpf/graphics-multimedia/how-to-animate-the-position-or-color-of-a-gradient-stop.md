---
title: '方法: グラデーション ストップの位置または色をアニメーション化する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- position [WPF], animating
- animation [WPF], position of GradientStop objects
- GradientStop objects [WPF], animating color of
- colors [WPF], animating
- animation [WPF], color of GradientStop objects
- GradientStop objects [WPF], animating position of
ms.assetid: 6f5b8b47-6c32-4b8e-98ee-fdf6515ec843
ms.openlocfilehash: aeae33f5f3c8016808988f58d61969e9b6f05039
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96979963"
---
# <a name="how-to-animate-the-position-or-color-of-a-gradient-stop"></a><span data-ttu-id="ea08d-102">方法: グラデーション ストップの位置または色をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="ea08d-102">How to: Animate the Position or Color of a Gradient Stop</span></span>
<span data-ttu-id="ea08d-103">この例では、<xref:System.Windows.Media.GradientStop> オブジェクトの <xref:System.Windows.Media.GradientStop.Color%2A> と <xref:System.Windows.Media.GradientStop.Offset%2A> をアニメーション化する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ea08d-103">This example shows how to animate the <xref:System.Windows.Media.GradientStop.Color%2A> and <xref:System.Windows.Media.GradientStop.Offset%2A> of <xref:System.Windows.Media.GradientStop> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea08d-104">例</span><span class="sxs-lookup"><span data-stu-id="ea08d-104">Example</span></span>  
 <span data-ttu-id="ea08d-105">次の例では、<xref:System.Windows.Media.LinearGradientBrush> 内の 3 つのグラデーション境界をアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="ea08d-105">The following example animates three gradient stops inside a <xref:System.Windows.Media.LinearGradientBrush>.</span></span> <span data-ttu-id="ea08d-106">この例では、3 つのアニメーションを使用して、それぞれ異なるグラデーション境界をアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="ea08d-106">The example uses three animations, each of which animates a different gradient stop:</span></span>  
  
- <span data-ttu-id="ea08d-107">1 番目のアニメーション (<xref:System.Windows.Media.Animation.DoubleAnimation>) では、アニメーション化で 1 番目のグラデーション境界の <xref:System.Windows.Media.GradientStop.Offset%2A> を 0.0 から 1.0 まで移動し、次に 0.0 に戻します。</span><span class="sxs-lookup"><span data-stu-id="ea08d-107">The first animation, a <xref:System.Windows.Media.Animation.DoubleAnimation>, animates the first gradient stop's <xref:System.Windows.Media.GradientStop.Offset%2A> from 0.0 to 1.0 and then back to 0.0.</span></span> <span data-ttu-id="ea08d-108">その結果、グラデーションの最初の色が四角形の左側から右側に移動し、次に左側に戻ります。</span><span class="sxs-lookup"><span data-stu-id="ea08d-108">As a result, the first color in the gradient shifts from the left side to the right side of the rectangle and then back to the left side.</span></span>  
  
- <span data-ttu-id="ea08d-109">2 番目のアニメーション (<xref:System.Windows.Media.Animation.ColorAnimation>) では、アニメーション化で 2 番目のグラデーション境界の <xref:System.Windows.Media.GradientStop.Color%2A> を <xref:System.Windows.Media.Colors.Purple%2A> から <xref:System.Windows.Media.Colors.Yellow%2A> まで変え、次に <xref:System.Windows.Media.Colors.Purple%2A> に戻します。</span><span class="sxs-lookup"><span data-stu-id="ea08d-109">The second animation, a <xref:System.Windows.Media.Animation.ColorAnimation>, animates the second gradient stop's <xref:System.Windows.Media.GradientStop.Color%2A> from <xref:System.Windows.Media.Colors.Purple%2A> to <xref:System.Windows.Media.Colors.Yellow%2A> and then back to <xref:System.Windows.Media.Colors.Purple%2A>.</span></span> <span data-ttu-id="ea08d-110">その結果、グラデーションの中間色が紫色から黄色に変わり、紫色に戻ります。</span><span class="sxs-lookup"><span data-stu-id="ea08d-110">As a result, the middle color in the gradient changes from purple to yellow and back to purple.</span></span>  
  
- <span data-ttu-id="ea08d-111">3 番目のアニメーション (これも <xref:System.Windows.Media.Animation.ColorAnimation>) では、アニメーション化で 3 番目のグラデーション境界の <xref:System.Windows.Media.GradientStop.Color%2A> の不透明度を 1 減らし、次に元に戻します。</span><span class="sxs-lookup"><span data-stu-id="ea08d-111">The third animation, another <xref:System.Windows.Media.Animation.ColorAnimation>, animates the opacity of the third gradient stop's <xref:System.Windows.Media.GradientStop.Color%2A> by -1 and then back.</span></span> <span data-ttu-id="ea08d-112">その結果、グラデーションの 3 番目の色が薄くなり、その後、不透明に戻ります。</span><span class="sxs-lookup"><span data-stu-id="ea08d-112">As a result, the third color in the gradient fades away and then becomes opaque again.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/GradientStopAnimationExample.cs#graphicsmmgradientanimationexampleswholepage)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/gradientstopanimationexample.vb#graphicsmmgradientanimationexampleswholepage)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/GradientStopAnimationExample.xaml#graphicsmmgradientanimationexampleswholepage)]  
  
 <span data-ttu-id="ea08d-113">この例では <xref:System.Windows.Media.LinearGradientBrush> を使用していますが、プロセスは <xref:System.Windows.Media.RadialGradientBrush> 内の <xref:System.Windows.Media.GradientStop> オブジェクトをアニメーション化する場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="ea08d-113">Although this example uses a <xref:System.Windows.Media.LinearGradientBrush>, the process is the same for animating <xref:System.Windows.Media.GradientStop> objects inside a <xref:System.Windows.Media.RadialGradientBrush>.</span></span>  
  
 <span data-ttu-id="ea08d-114">その他の例については、「[ブラシのサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ea08d-114">For additional examples, see the [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea08d-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="ea08d-115">See also</span></span>

- <xref:System.Windows.Media.GradientStop>
- [<span data-ttu-id="ea08d-116">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="ea08d-116">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="ea08d-117">ストーリーボードの概要</span><span class="sxs-lookup"><span data-stu-id="ea08d-117">Storyboards Overview</span></span>](storyboards-overview.md)
