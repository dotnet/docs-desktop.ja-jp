---
title: '方法: AnimationClock を使用してプロパティをアニメーション化する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], properties [WPF], with AnimationClocks
- AnimationClocks [WPF]
ms.assetid: e6542021-714c-4675-9567-04f1c7380834
ms.openlocfilehash: 13d91e8589c40d84ba374ffc613388e24407796a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974930"
---
# <a name="how-to-animate-a-property-by-using-an-animationclock"></a><span data-ttu-id="f3782-102">方法: AnimationClock を使用してプロパティをアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="f3782-102">How to: Animate a Property by Using an AnimationClock</span></span>
<span data-ttu-id="f3782-103">この例からは、<xref:System.Windows.Media.Animation.Clock> オブジェクトを使用してプロパティをアニメーション化する方法がわかります。</span><span class="sxs-lookup"><span data-stu-id="f3782-103">This example shows how to use <xref:System.Windows.Media.Animation.Clock> objects to animate a property.</span></span>  
  
 <span data-ttu-id="f3782-104">依存関係プロパティをアニメーション化するには次の 3 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="f3782-104">There are three ways to animate a dependency property:</span></span>  
  
- <span data-ttu-id="f3782-105"><xref:System.Windows.Media.Animation.AnimationTimeline> を作成し、それを <xref:System.Windows.Media.Animation.Storyboard> を使用してプロパティと関連付けます。</span><span class="sxs-lookup"><span data-stu-id="f3782-105">Create an <xref:System.Windows.Media.Animation.AnimationTimeline> and associate it with that property by using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
- <span data-ttu-id="f3782-106">オブジェクトの <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> メソッドを使用して、ターゲット プロパティに 1 つの <xref:System.Windows.Media.Animation.AnimationTimeline> を適用します。</span><span class="sxs-lookup"><span data-stu-id="f3782-106">Use the object's <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method to apply a single <xref:System.Windows.Media.Animation.AnimationTimeline> to a target property.</span></span>  
  
- <span data-ttu-id="f3782-107"><xref:System.Windows.Media.Animation.AnimationTimeline> から <xref:System.Windows.Media.Animation.AnimationClock> を作成して、それをプロパティに適用します。</span><span class="sxs-lookup"><span data-stu-id="f3782-107">Create an <xref:System.Windows.Media.Animation.AnimationClock> from an <xref:System.Windows.Media.Animation.AnimationTimeline> and apply it to a property.</span></span>  
  
 <span data-ttu-id="f3782-108"><xref:System.Windows.Media.Animation.Storyboard> オブジェクトと <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> メソッドを使用すると、クロックを直接作成して配布しなくても、プロパティをアニメーション化できます (例については、「[ストーリーボードを使ってプロパティをアニメーション化する](how-to-animate-a-property-by-using-a-storyboard.md)」と「[ストーリーボードを使用せずにプロパティをアニメーション化する](how-to-animate-a-property-without-using-a-storyboard.md)」を参照してください)。つまり、クロックは自動的に作成されて配布されます。</span><span class="sxs-lookup"><span data-stu-id="f3782-108"><xref:System.Windows.Media.Animation.Storyboard> objects and the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method enable you to animate properties without directly creating and distributing clocks (for examples, see [Animate a Property by Using a Storyboard](how-to-animate-a-property-by-using-a-storyboard.md) and [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md)); clocks are created and distributed for you automatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3782-109">例</span><span class="sxs-lookup"><span data-stu-id="f3782-109">Example</span></span>  
 <span data-ttu-id="f3782-110">次の例は、<xref:System.Windows.Media.Animation.AnimationClock> を作成して、それを 2 つの類似したプロパティに適用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f3782-110">The following example shows how to create an <xref:System.Windows.Media.Animation.AnimationClock> and apply it to two similar properties.</span></span>  
  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/AnimationClockExample.cs#graphicsmmcreateanimationclockwholeclass)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/animationclockexample.vb#graphicsmmcreateanimationclockwholeclass)]  
  
 <span data-ttu-id="f3782-111"><xref:System.Windows.Media.Animation.Clock> の開始後にこれを対話的に制御する方法の例については、「[クロックを対話的に制御する](how-to-interactively-control-a-clock.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3782-111">For an example showing how to interactively control a <xref:System.Windows.Media.Animation.Clock> after it starts, see [Interactively Control a Clock](how-to-interactively-control-a-clock.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3782-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="f3782-112">See also</span></span>

- [<span data-ttu-id="f3782-113">ストーリーボードを使ってプロパティをアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="f3782-113">Animate a Property by Using a Storyboard</span></span>](how-to-animate-a-property-by-using-a-storyboard.md)
- [<span data-ttu-id="f3782-114">ストーリーボードを使用せずにプロパティをアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="f3782-114">Animate a Property Without Using a Storyboard</span></span>](how-to-animate-a-property-without-using-a-storyboard.md)
- [<span data-ttu-id="f3782-115">プロパティ アニメーションの手法の概要</span><span class="sxs-lookup"><span data-stu-id="f3782-115">Property Animation Techniques Overview</span></span>](property-animation-techniques-overview.md)
