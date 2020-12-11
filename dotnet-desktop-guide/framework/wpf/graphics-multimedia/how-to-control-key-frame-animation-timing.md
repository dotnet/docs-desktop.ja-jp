---
title: '方法: キー フレーム アニメーションのタイミングを制御する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], timing
- timing key-frame animation
ms.assetid: b059216f-7d4b-4ca8-a019-bc287ee7bf16
ms.openlocfilehash: 8cfd2be0bbc526ed92a5fb1b558a5a41dc9c3113
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984780"
---
# <a name="how-to-control-key-frame-animation-timing"></a><span data-ttu-id="82977-102">方法: キー フレーム アニメーションのタイミングを制御する</span><span class="sxs-lookup"><span data-stu-id="82977-102">How to: Control Key-Frame Animation Timing</span></span>

<span data-ttu-id="82977-103">この例では、キー フレーム アニメーション内のキー フレームのタイミングを制御する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="82977-103">This example shows how to control the timing of key frames within a key-frame animation.</span></span> <span data-ttu-id="82977-104">他のアニメーションと同様に、キー フレーム アニメーションには <xref:System.Windows.Media.Animation.Timeline.Duration%2A> プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="82977-104">Like other animations, key-frame animations have a <xref:System.Windows.Media.Animation.Timeline.Duration%2A> property.</span></span> <span data-ttu-id="82977-105">アニメーションの継続時間を指定するだけでなく、その継続時間のどの部分を各キー フレームに割り当てるかを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82977-105">In addition to specifying the duration of an animation, you need to specify what part of that duration is allotted to each of its key frames.</span></span> <span data-ttu-id="82977-106">時間を割り当てるには、アニメーションの各キーフ レームに <xref:System.Windows.Media.Animation.KeyTime> を指定します。</span><span class="sxs-lookup"><span data-stu-id="82977-106">To allot the time, you specify a <xref:System.Windows.Media.Animation.KeyTime> for each key frame in the animation.</span></span>

<span data-ttu-id="82977-107">各キー フレームの <xref:System.Windows.Media.Animation.KeyTime> では、キーフ レームの終了時点を指定します (キー フレームの再生時間の長さを指定するわけではありません)。</span><span class="sxs-lookup"><span data-stu-id="82977-107">The <xref:System.Windows.Media.Animation.KeyTime> for each key frame specifies when a key frame ends (it does not specify the length of time a key frame plays).</span></span> <span data-ttu-id="82977-108"><xref:System.Windows.Media.Animation.KeyTime> は、<xref:System.TimeSpan> 値として、パーセントとして、<xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> または <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> 特殊値として指定できます。</span><span class="sxs-lookup"><span data-stu-id="82977-108">You can specify a <xref:System.Windows.Media.Animation.KeyTime> as a <xref:System.TimeSpan> value, as a percentage, or as the <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> or <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> special value.</span></span>

## <a name="example"></a><span data-ttu-id="82977-109">例</span><span class="sxs-lookup"><span data-stu-id="82977-109">Example</span></span>

<span data-ttu-id="82977-110">次の例では、<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> を使用して画面全体で四角形をアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="82977-110">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> to animate a rectangle across the screen.</span></span> <span data-ttu-id="82977-111">キー フレームのキー時間は <xref:System.TimeSpan> 値で設定します。</span><span class="sxs-lookup"><span data-stu-id="82977-111">The key frames' key times are set with <xref:System.TimeSpan> values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimestimespanexample)]
[!code-vb[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimestimespanexample)]
[!code-xaml[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimestimespanexample)]

<span data-ttu-id="82977-112">次の図は、各キー フレームの値に到達したことを示しています。</span><span class="sxs-lookup"><span data-stu-id="82977-112">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="82977-113">![キー値は 3 秒、4 秒、10 秒です](./media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")</span><span class="sxs-lookup"><span data-stu-id="82977-113">![Key values are reached at 3, 4, and 10 seconds](./media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")</span></span>

<span data-ttu-id="82977-114">次の例は同一のアニメーションを示していますが、キー フレームのキー時間にパーセント値が設定されている点が異なります。</span><span class="sxs-lookup"><span data-stu-id="82977-114">The next example shows an animation that is identical, except that the key frames' key times are set with percentage values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespercentageexample)]
[!code-vb[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespercentageexample)]
[!code-xaml[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespercentageexample)]

<span data-ttu-id="82977-115">次の図は、各キー フレームの値に到達したことを示しています。</span><span class="sxs-lookup"><span data-stu-id="82977-115">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="82977-116">![キー値は 3 秒、4 秒、10 秒です](./media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")</span><span class="sxs-lookup"><span data-stu-id="82977-116">![Key values are reached at 3, 4, and 10 seconds](./media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")</span></span>

<span data-ttu-id="82977-117">次の例では <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> キー時間値を使用しています。</span><span class="sxs-lookup"><span data-stu-id="82977-117">The next example uses <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> key time values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimesuniformexample)]
[!code-vb[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimesuniformexample)]
[!code-xaml[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimesuniformexample)]

<span data-ttu-id="82977-118">次の図は、各キー フレームの値に到達したことを示しています。</span><span class="sxs-lookup"><span data-stu-id="82977-118">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="82977-119">![キー値は 3.3 秒、6.6 秒、9.9 秒です](./media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")</span><span class="sxs-lookup"><span data-stu-id="82977-119">![Key values are reached at 3.3,6.6, and 9.9 seconds](./media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")</span></span>

<span data-ttu-id="82977-120">最後の例では <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> キー時間値を使用しています。</span><span class="sxs-lookup"><span data-stu-id="82977-120">The final example uses <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> key time values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespacedexample)]
[!code-vb[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespacedexample)]
[!code-xaml[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespacedexample)]

<span data-ttu-id="82977-121">次の図は、各キー フレームの値に到達したことを示しています。</span><span class="sxs-lookup"><span data-stu-id="82977-121">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="82977-122">![キー値は 0 秒、5 秒、10 秒です](./media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")</span><span class="sxs-lookup"><span data-stu-id="82977-122">![Key values are reached at 0, 5, and 10 seconds](./media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")</span></span>

<span data-ttu-id="82977-123">わかりやすくするために、この例のコード バージョンではストーリーボードではなくローカル アニメーションを使用しています。1 つのプロパティに適用されるのが 1 つのアニメーションだけであるためです。ただし、この例は、代わりにストーリーボードを使用するように変更できます。</span><span class="sxs-lookup"><span data-stu-id="82977-123">For simplicity, the code versions of this example use local animations, not storyboards, because only a single animation is being applied to a single property, but the examples may be modified to use storyboards instead.</span></span> <span data-ttu-id="82977-124">コードでストーリーボードを宣言する方法を示す例については、「[ストーリーボードを使ってプロパティをアニメーション化する](how-to-animate-a-property-by-using-a-storyboard.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82977-124">For an example showing how to declare a storyboard in code, see [Animate a Property by Using a Storyboard](how-to-animate-a-property-by-using-a-storyboard.md).</span></span>

<span data-ttu-id="82977-125">サンプル全体については、「[キーフレーム アニメーションのサンプル](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82977-125">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span> <span data-ttu-id="82977-126">キー フレーム アニメーションの詳細については、「[キー フレーム アニメーションの概要](key-frame-animations-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82977-126">For more information about key frame animations, see the [Key-Frame Animations Overview](key-frame-animations-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="82977-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="82977-127">See also</span></span>

- [<span data-ttu-id="82977-128">キー フレーム アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="82977-128">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="82977-129">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="82977-129">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="82977-130">方法トピック</span><span class="sxs-lookup"><span data-stu-id="82977-130">How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
