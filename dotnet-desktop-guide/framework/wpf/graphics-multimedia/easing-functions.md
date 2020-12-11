---
title: イージング関数
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- applying mathematical formulas to animations [WPF]
- applying easing functions to animations [WPF]
- mathematical formulas [WPF], applying to animations
- animations [WPF], realistic movement
- easing functions [WPF]
- customizing easing functions [WPF]
- easing functions [WPF], definition
- easing functions [WPF], customizing
- animations [WPF], applying
ms.assetid: 075b9c2b-82c4-43fa-b3cd-de0b6236eb38
ms.openlocfilehash: a25bde5098af853c3906a174a189fc35f33f0525
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984564"
---
# <a name="easing-functions"></a><span data-ttu-id="d70a5-102">イージング関数</span><span class="sxs-lookup"><span data-stu-id="d70a5-102">Easing Functions</span></span>
<span data-ttu-id="d70a5-103">イージング関数を使うと、独自の数式をアニメーションに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="d70a5-103">Easing functions allow you to apply custom mathematical formulas to your animations.</span></span> <span data-ttu-id="d70a5-104">たとえば、オブジェクトをリアルにバウンドさせたり、バネに乗っているように動作させたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="d70a5-104">For example, you may want an object to realistically bounce or behave as though it were on a spring.</span></span> <span data-ttu-id="d70a5-105">キー フレーム アニメーションや From/To/By アニメーションを使ってこれらの効果を近似することもできますが、大量の作業が必要であり、アニメーションは数式を使うほど正確ではありません。</span><span class="sxs-lookup"><span data-stu-id="d70a5-105">You could use Key-Frame or even From/To/By animations to approximate these effects but it would take a significant amount of work and the animation would be less accurate than using a mathematical formula.</span></span>  
  
 <span data-ttu-id="d70a5-106"><xref:System.Windows.Media.Animation.EasingFunctionBase> から継承することによって独自のカスタム イージング関数を作成するだけでなく、ランタイムによって提供されるいくつかのイージング関数の 1 つを使用して一般的な効果を作成できます。</span><span class="sxs-lookup"><span data-stu-id="d70a5-106">Besides creating your own custom easing function by inheriting from <xref:System.Windows.Media.Animation.EasingFunctionBase>, you can use one of several easing functions provided by the runtime to create common effects.</span></span>  
  
- <span data-ttu-id="d70a5-107"><xref:System.Windows.Media.Animation.BackEase>:示されているパスでアニメーション化を開始する直前に、アニメーションの動作を逆行させます。</span><span class="sxs-lookup"><span data-stu-id="d70a5-107"><xref:System.Windows.Media.Animation.BackEase>: Retracts the motion of an animation slightly before it begins to animate in the path indicated.</span></span>  
  
- <span data-ttu-id="d70a5-108"><xref:System.Windows.Media.Animation.BounceEase>:バウンス効果を作成します。</span><span class="sxs-lookup"><span data-stu-id="d70a5-108"><xref:System.Windows.Media.Animation.BounceEase>: Creates a bouncing effect.</span></span>  
  
- <span data-ttu-id="d70a5-109"><xref:System.Windows.Media.Animation.CircleEase>:円関数を使って加速や減速するアニメーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="d70a5-109"><xref:System.Windows.Media.Animation.CircleEase>: Creates an animation that accelerates and/or decelerates using a circular function.</span></span>  
  
- <span data-ttu-id="d70a5-110"><xref:System.Windows.Media.Animation.CubicEase>:数式 *f*(*t*) = *t*<sup>3</sup> を使用して、加速や減速するアニメーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="d70a5-110"><xref:System.Windows.Media.Animation.CubicEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>3</sup>.</span></span>  
  
- <span data-ttu-id="d70a5-111"><xref:System.Windows.Media.Animation.ElasticEase>:静止するまで前後に振れるバネのようなアニメーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="d70a5-111"><xref:System.Windows.Media.Animation.ElasticEase>: Creates an animation that resembles a spring oscillating back and forth until it comes to rest.</span></span>  
  
- <span data-ttu-id="d70a5-112"><xref:System.Windows.Media.Animation.ExponentialEase>:指数式を使って、加速や減速するアニメーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="d70a5-112"><xref:System.Windows.Media.Animation.ExponentialEase>: Creates an animation that accelerates and/or decelerates using an exponential formula.</span></span>  
  
- <span data-ttu-id="d70a5-113"><xref:System.Windows.Media.Animation.PowerEase>:数式 *f*(*t*) = *t*<sup>p</sup> (この場合、p は <xref:System.Windows.Media.Animation.PowerEase.Power%2A> プロパティと等しい) を使用して、加速や減速するアニメーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="d70a5-113"><xref:System.Windows.Media.Animation.PowerEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>p</sup> where p is equal to the <xref:System.Windows.Media.Animation.PowerEase.Power%2A> property.</span></span>  
  
- <span data-ttu-id="d70a5-114"><xref:System.Windows.Media.Animation.QuadraticEase>:数式 *f*(*t*) = *t*<sup>2</sup> を使用して、加速や減速するアニメーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="d70a5-114"><xref:System.Windows.Media.Animation.QuadraticEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>2</sup>.</span></span>  
  
- <span data-ttu-id="d70a5-115"><xref:System.Windows.Media.Animation.QuarticEase>:数式 *f*(*t*) = *t*<sup>4</sup> を使用して、加速や減速するアニメーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="d70a5-115"><xref:System.Windows.Media.Animation.QuarticEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>4</sup>.</span></span>  
  
- <span data-ttu-id="d70a5-116"><xref:System.Windows.Media.Animation.QuinticEase>:数式 *f*(*t*) = *t*<sup>5</sup> を使用して、加速や減速するアニメーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="d70a5-116"><xref:System.Windows.Media.Animation.QuinticEase>: Create an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>5</sup>.</span></span>  
  
- <span data-ttu-id="d70a5-117"><xref:System.Windows.Media.Animation.SineEase>:正弦公式を使用して、加速または減速するアニメーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="d70a5-117"><xref:System.Windows.Media.Animation.SineEase>: Creates an animation that accelerates and/or decelerates using a sine formula.</span></span>  
  
 <span data-ttu-id="d70a5-118">アニメーションにイージング関数を適用するには、アニメーションの `EasingFunction` プロパティを使って、アニメーションに適用するイージング関数を指定します。</span><span class="sxs-lookup"><span data-stu-id="d70a5-118">To apply an easing function to an animation, use the `EasingFunction` property of the animation specify the easing function to apply to the animation.</span></span> <span data-ttu-id="d70a5-119">次の例は、<xref:System.Windows.Media.Animation.BounceEase> イージング関数を <xref:System.Windows.Media.Animation.DoubleAnimation> に適用して、バウンス効果を作成します。</span><span class="sxs-lookup"><span data-stu-id="d70a5-119">The following example applies a <xref:System.Windows.Media.Animation.BounceEase> easing function to a <xref:System.Windows.Media.Animation.DoubleAnimation> to create a bouncing effect.</span></span>  
  
 [!code-xaml[BounceEase_snippet#BounceEase](~/samples/snippets/csharp/VS_Snippets_Wpf/bounceease_snippet/CS/window1.xaml#bounceease)]  
  
 <span data-ttu-id="d70a5-120">前の例では、イージング関数を From/To/By アニメーションに適用しました。</span><span class="sxs-lookup"><span data-stu-id="d70a5-120">In the previous example, the easing function was applied to a From/To/By animation.</span></span> <span data-ttu-id="d70a5-121">キー フレーム アニメーションにこれらのイージング関数を適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="d70a5-121">You can also apply these easing functions to Key-Frame animations.</span></span> <span data-ttu-id="d70a5-122">次の例では、キー フレームとそれらに関連付けられたイージング関数を使って、四角形が上方に縮まり、遅くなり、下方に延び (落下するように)、停止するアニメーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="d70a5-122">The following example shows how to use key frames with easing functions associated with them to create an animation of a rectangle that contracts upward, slows down, then expands downward (as though falling) and then bounces to a stop.</span></span>  
  
 [!code-xaml[EasingFunctionDoubleKeyFrame_snippet#EasingFunctionDoubleKeyFrame](~/samples/snippets/csharp/VS_Snippets_Wpf/easingfunctiondoublekeyframe_snippet/CS/window1.xaml#easingfunctiondoublekeyframe)]  
  
 <span data-ttu-id="d70a5-123"><xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> プロパティを使用して、イージング関数の動作を変更する、つまり、アニメーションの補間方法を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="d70a5-123">You can use the <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> property to alter how the easing function behaves, that is, change how the animation interpolates.</span></span> <span data-ttu-id="d70a5-124"><xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> に指定できる値は次の 3 つです。</span><span class="sxs-lookup"><span data-stu-id="d70a5-124">There are three possible values you can give for <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:</span></span>  
  
- <span data-ttu-id="d70a5-125"><xref:System.Windows.Media.Animation.EasingMode.EaseIn>:補間は、イージング関数に関連付けられている数式に従います。</span><span class="sxs-lookup"><span data-stu-id="d70a5-125"><xref:System.Windows.Media.Animation.EasingMode.EaseIn>: Interpolation follows the mathematical formula associated with the easing function.</span></span>  
  
- <span data-ttu-id="d70a5-126"><xref:System.Windows.Media.Animation.EasingMode.EaseOut>:補間は、100% の補間から、イージング関数に関連付けられている数式の出力を引いた値に従います。</span><span class="sxs-lookup"><span data-stu-id="d70a5-126"><xref:System.Windows.Media.Animation.EasingMode.EaseOut>: Interpolation follows 100% interpolation minus the output of the formula associated with the easing function.</span></span>  
  
- <span data-ttu-id="d70a5-127"><xref:System.Windows.Media.Animation.EasingMode.EaseInOut>:補間は、アニメーションの最初の半分には <xref:System.Windows.Media.Animation.EasingMode.EaseIn> を使用し、残りの半分には <xref:System.Windows.Media.Animation.EasingMode.EaseOut> を使用します。</span><span class="sxs-lookup"><span data-stu-id="d70a5-127"><xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: Interpolation uses <xref:System.Windows.Media.Animation.EasingMode.EaseIn> for the first half of the animation and <xref:System.Windows.Media.Animation.EasingMode.EaseOut> for the second half.</span></span>  
  
 <span data-ttu-id="d70a5-128">次のグラフは、<xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> のさまざまな値を示しています。*f*(*x*) はアニメーションの進行状況を表し、*t* は時間を表します。</span><span class="sxs-lookup"><span data-stu-id="d70a5-128">The graphs below demonstrate the different values of <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> where *f*(*x*) represents the animation progress and *t* represents time.</span></span>  
  
 <xref:System.Windows.Media.Animation.BackEase>  
  
 <span data-ttu-id="d70a5-129">![BackEase EasingMode のグラフ。](./media/backease-graph.png "BackEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="d70a5-129">![BackEase EasingMode graphs.](./media/backease-graph.png "BackEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.BounceEase>  
  
 <span data-ttu-id="d70a5-130">![BounceEase EasingMode のグラフ。](./media/bounceease-graph.png "BounceEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="d70a5-130">![BounceEase EasingMode graphs.](./media/bounceease-graph.png "BounceEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.CircleEase>  
  
 <span data-ttu-id="d70a5-131">![CircleEase EasingMode のグラフ。](./media/circleease-graph.png "CircleEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="d70a5-131">![CircleEase EasingMode graphs.](./media/circleease-graph.png "CircleEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.CubicEase>  
  
 <span data-ttu-id="d70a5-132">![CubicEase EasingMode のグラフ。](./media/cubicease-graph.png "CubicEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="d70a5-132">![CubicEase EasingMode graphs.](./media/cubicease-graph.png "CubicEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.ElasticEase>  
  
 <span data-ttu-id="d70a5-133">![さまざまな easingmode のグラフでの ElasticEase。](./media/elasticease-graph.png "ElasticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="d70a5-133">![ElasticEase with graphs of different easingmodes.](./media/elasticease-graph.png "ElasticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.ExponentialEase>  
  
 <span data-ttu-id="d70a5-134">![さまざまな easingmode のグラフでの ExponentialEase。](./media/exponentialease-graph.png "ExponentialEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="d70a5-134">![ExponentialEase graphs of different easingmodes.](./media/exponentialease-graph.png "ExponentialEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.PowerEase>  
  
 <span data-ttu-id="d70a5-135">![さまざまな easingmode のグラフでの QuarticEase。](./media/quarticease-graph.png "QuarticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="d70a5-135">![QuarticEase with graphs of different easingmodes.](./media/quarticease-graph.png "QuarticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuadraticEase>  
  
 <span data-ttu-id="d70a5-136">![さまざまな easingmode のグラフでの QuadraticEase](./media/quadraticease-graph.png "QuadraticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="d70a5-136">![QuadraticEase with graphs of different easingmodes](./media/quadraticease-graph.png "QuadraticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuarticEase>  
  
 <span data-ttu-id="d70a5-137">![さまざまな easingmode のグラフでの QuarticEase。](./media/quarticease-graph.png "QuarticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="d70a5-137">![QuarticEase with graphs of different easingmodes.](./media/quarticease-graph.png "QuarticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuinticEase>  
  
 <span data-ttu-id="d70a5-138">![さまざまな easingmode のグラフでの QuinticEase。](./media/quinticease-graph.png "QuinticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="d70a5-138">![QuinticEase with graphs of different easingmodes.](./media/quinticease-graph.png "QuinticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.SineEase>  
  
 <span data-ttu-id="d70a5-139">![さまざまな EasingMode 値での SineEase](./media/sineease-graph.png "SineEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="d70a5-139">![SineEase for different EasingMode values](./media/sineease-graph.png "SineEase_Graph")</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d70a5-140"><xref:System.Windows.Media.Animation.PowerEase> を使用すると、<xref:System.Windows.Media.Animation.PowerEase.Power%2A> プロパティを使って <xref:System.Windows.Media.Animation.CubicEase>、<xref:System.Windows.Media.Animation.QuadraticEase>、<xref:System.Windows.Media.Animation.QuarticEase>、および <xref:System.Windows.Media.Animation.QuinticEase> と同じ動作を作成できます。</span><span class="sxs-lookup"><span data-stu-id="d70a5-140">You can use <xref:System.Windows.Media.Animation.PowerEase> to create the same behavior as <xref:System.Windows.Media.Animation.CubicEase>, <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase>, and <xref:System.Windows.Media.Animation.QuinticEase> by using the <xref:System.Windows.Media.Animation.PowerEase.Power%2A> property.</span></span> <span data-ttu-id="d70a5-141">たとえば、<xref:System.Windows.Media.Animation.PowerEase> を使用して <xref:System.Windows.Media.Animation.CubicEase> を置き換える場合は、<xref:System.Windows.Media.Animation.PowerEase.Power%2A> 値 3 を指定します。</span><span class="sxs-lookup"><span data-stu-id="d70a5-141">For example, if you want to use <xref:System.Windows.Media.Animation.PowerEase> to substitute for <xref:System.Windows.Media.Animation.CubicEase>, specify a <xref:System.Windows.Media.Animation.PowerEase.Power%2A> value of 3.</span></span>  
  
 <span data-ttu-id="d70a5-142">ランタイムに含まれるイージング関数を使うだけでなく、<xref:System.Windows.Media.Animation.EasingFunctionBase> から継承することによって独自のイージング関数を作成できます。</span><span class="sxs-lookup"><span data-stu-id="d70a5-142">In addition to using the easing functions included in the run-time, you can create your own custom easing functions by inheriting from <xref:System.Windows.Media.Animation.EasingFunctionBase>.</span></span> <span data-ttu-id="d70a5-143">次の例では、簡単なカスタム イージング関数を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d70a5-143">The following example demonstrates how to create a simple custom easing function.</span></span> <span data-ttu-id="d70a5-144"><xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> メソッドをオーバーライドすることにより、イージング関数の動作について独自の数学ロジックを追加できます。</span><span class="sxs-lookup"><span data-stu-id="d70a5-144">You can add your own mathematical logic for how the easing function behaves by overriding the <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> method.</span></span>
  
 [!code-csharp[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/customlog10easingfunction.cs#customeasingfunction)]
 [!code-vb[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/visualbasic/VS_Snippets_Wpf/customeasingfunction/visualbasic/customlog10easingfunction.vb#customeasingfunction)]
 [!code-xaml[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/window1.xaml#customeasingfunction)]
