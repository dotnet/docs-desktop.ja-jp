---
title: '方法: 反復サイクル中にアニメーション値を累積する'
ms.date: 03/30/2017
helpviewer_keywords:
- accumulating animation values across repeating cycles [WPF]
- animation [WPF], accumulating values across repeating cycles
ms.assetid: 548df369-c7cc-4dab-b569-08b95ced2e7e
ms.openlocfilehash: bccdc9b7bf2d5a0ea476e39e8d54107854db7ae3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984872"
---
# <a name="how-to-accumulate-animation-values-during-repeat-cycles"></a><span data-ttu-id="0ce8e-102">方法: 反復サイクル中にアニメーション値を累積する</span><span class="sxs-lookup"><span data-stu-id="0ce8e-102">How to: Accumulate Animation Values During Repeat Cycles</span></span>
<span data-ttu-id="0ce8e-103">この例では、<xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> プロパティを使用して、反復サイクルでアニメーション値を累積する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0ce8e-103">This example shows how to use the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to accumulate animation values across repeating cycles.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ce8e-104">例</span><span class="sxs-lookup"><span data-stu-id="0ce8e-104">Example</span></span>  
 <span data-ttu-id="0ce8e-105"><xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> プロパティを使用して、反復サイクル中のアニメーションの基本値を累積します。</span><span class="sxs-lookup"><span data-stu-id="0ce8e-105">Use the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to accumulate base values of an animation across repeating cycles.</span></span> <span data-ttu-id="0ce8e-106">たとえば、アニメーションを 9 回繰り返す (<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> = "9x") ように設定し、10 から 15 (From = 10 To = 15) の間でアニメーション化するようにプロパティを設定した場合、プロパティは、最初のサイクルで 10 から 15 まで、2 番目のサイクルで 15 から 20 まで、3 番目のサイクルで 20 から 25 まで (以下同様) アニメーション化されます。</span><span class="sxs-lookup"><span data-stu-id="0ce8e-106">For example, if you set an animation to repeat 9 times (<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> = "9x") and you set the property to animate between 10 and 15 (From = 10 To = 15), the property animates from 10 to 15 during the first cycle, from 15 to 20 during the second cycle, from 20 to 25 during the third cycle, and so on.</span></span> <span data-ttu-id="0ce8e-107">したがって、各アニメーション サイクルでは、前のアニメーション サイクルの終了アニメーション値が基本値として使用されます。</span><span class="sxs-lookup"><span data-stu-id="0ce8e-107">Hence, each animation cycle uses the ending animation value from the previous animation cycle as its base value.</span></span>  
  
 <span data-ttu-id="0ce8e-108">ほとんどの基本的なアニメーションと、ほとんどのキー フレーム アニメーションでは、`IsCumulative` プロパティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0ce8e-108">You can use the `IsCumulative` property with most basic animations and most key frame animations.</span></span> <span data-ttu-id="0ce8e-109">詳細については、「[アニメーションの概要](animation-overview.md)」と「[キーフレーム アニメーションの概要](key-frame-animations-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ce8e-109">For more information, see [Animation Overview](animation-overview.md) and [Key-Frame Animations Overview](key-frame-animations-overview.md).</span></span>  
  
 <span data-ttu-id="0ce8e-110">次の例では、4 つの四角形の幅をアニメーション化することで、この動作を示しています。</span><span class="sxs-lookup"><span data-stu-id="0ce8e-110">The following example shows this behavior by animating the width of four rectangles.</span></span> <span data-ttu-id="0ce8e-111">この例では、次の処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="0ce8e-111">The example:</span></span>  
  
- <span data-ttu-id="0ce8e-112">最初の四角形を <xref:System.Windows.Media.Animation.DoubleAnimation> でアニメーション化し、<xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> プロパティを `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="0ce8e-112">Animates the first rectangle with <xref:System.Windows.Media.Animation.DoubleAnimation> and sets the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to `true`.</span></span>  
  
- <span data-ttu-id="0ce8e-113"><xref:System.Windows.Media.Animation.DoubleAnimation> で 2 番目の四角形をアニメーション化し、<xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> プロパティを `false` の既定値に設定します。</span><span class="sxs-lookup"><span data-stu-id="0ce8e-113">Animates the second rectangle with <xref:System.Windows.Media.Animation.DoubleAnimation> and sets the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to the default value of `false`.</span></span>  
  
- <span data-ttu-id="0ce8e-114">3 番目の四角形を <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> でアニメーション化し、<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> プロパティを `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="0ce8e-114">Animates the third rectangle with <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> and sets the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> property to `true`.</span></span>  
  
- <span data-ttu-id="0ce8e-115">最後の四角形を <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> でアニメーション化し、<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> プロパティを `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="0ce8e-115">Animates the last rectangle with <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> and sets the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> property to `false`.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#IsCumulativeWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsCumulativeExample.xaml#iscumulativewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="0ce8e-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="0ce8e-116">See also</span></span>

- [<span data-ttu-id="0ce8e-117">アニメーションの出力値をアニメーションの開始値に追加する</span><span class="sxs-lookup"><span data-stu-id="0ce8e-117">Add an Animation Output Value to an Animation Starting Value</span></span>](how-to-add-an-animation-output-value-to-an-animation-starting-value.md)
- [<span data-ttu-id="0ce8e-118">アニメーションを反復する</span><span class="sxs-lookup"><span data-stu-id="0ce8e-118">Repeat an Animation</span></span>](how-to-repeat-an-animation.md)
- [<span data-ttu-id="0ce8e-119">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="0ce8e-119">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="0ce8e-120">キー フレーム アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="0ce8e-120">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="0ce8e-121">方法トピック</span><span class="sxs-lookup"><span data-stu-id="0ce8e-121">How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
