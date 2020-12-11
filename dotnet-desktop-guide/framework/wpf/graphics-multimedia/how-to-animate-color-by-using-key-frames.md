---
title: '方法: キー フレームを使用して色をアニメーション化する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [WPF], animating with key frames
- animation [WPF], colors with key frames
- key frames [WPF], animating colors with
ms.assetid: ab04ffa6-4de9-4d5b-a3b4-4e35d5b2ef35
ms.openlocfilehash: 8a444706f7541b52722ab8257a88e76c3e1b0938
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984800"
---
# <a name="how-to-animate-color-by-using-key-frames"></a><span data-ttu-id="e8ad5-102">方法: キー フレームを使用して色をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="e8ad5-102">How to: Animate Color by Using Key Frames</span></span>
<span data-ttu-id="e8ad5-103">この例では、キー フレームを使用して <xref:System.Windows.Media.SolidColorBrush> の <xref:System.Windows.Media.SolidColorBrush.Color%2A> をアニメーション化する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e8ad5-103">This example shows how to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> of a <xref:System.Windows.Media.SolidColorBrush> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8ad5-104">例</span><span class="sxs-lookup"><span data-stu-id="e8ad5-104">Example</span></span>  
 <span data-ttu-id="e8ad5-105">次の例では、<xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> クラスを使用して、<xref:System.Windows.Media.SolidColorBrush> の <xref:System.Windows.Media.SolidColorBrush.Color%2A> プロパティをアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="e8ad5-105">The following example uses the <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> property of a <xref:System.Windows.Media.SolidColorBrush>.</span></span> <span data-ttu-id="e8ad5-106">このアニメーションは、次の方法で 3 つのキー フレームを使用します。</span><span class="sxs-lookup"><span data-stu-id="e8ad5-106">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="e8ad5-107">最初の 2 秒間は、<xref:System.Windows.Media.Animation.LinearColorKeyFrame> クラスのインスタンスを使用して、緑から赤へ徐々に色を変化させます。</span><span class="sxs-lookup"><span data-stu-id="e8ad5-107">During the first two seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearColorKeyFrame> class to gradually change the color from green to red.</span></span> <span data-ttu-id="e8ad5-108"><xref:System.Windows.Media.Animation.LinearColorKeyFrame> のような線形キー フレームは、ある値から次の値への滑らかで直線的な遷移を作成します。</span><span class="sxs-lookup"><span data-stu-id="e8ad5-108">Linear key frames like <xref:System.Windows.Media.Animation.LinearColorKeyFrame> create a smooth linear transition between values.</span></span>  
  
2. <span data-ttu-id="e8ad5-109">次の 0.5 秒間の後わりに、<xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> クラスのインスタンスを使用して、赤から黄色へすばやく色を変化させます。</span><span class="sxs-lookup"><span data-stu-id="e8ad5-109">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> class to quickly change the color from red to yellow.</span></span> <span data-ttu-id="e8ad5-110"><xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> のような不連続キー フレームは、ある値から次の値への突然の変化を作成します。つまり、この部分のアニメーションの色の変化は急速に行われ、滑らかではありません。</span><span class="sxs-lookup"><span data-stu-id="e8ad5-110">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> create sudden changes between values, that is, the color change in this part of the animation occurs quickly and is not subtle.</span></span>  
  
3. <span data-ttu-id="e8ad5-111">最後の 2 秒間は、<xref:System.Windows.Media.Animation.SplineColorKeyFrame> クラスのインスタンスを使用して、色を再度変更します (この例では黄色から緑へ戻ります)。</span><span class="sxs-lookup"><span data-stu-id="e8ad5-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineColorKeyFrame> class to change the color again—this time from yellow back to green.</span></span> <span data-ttu-id="e8ad5-112"><xref:System.Windows.Media.Animation.SplineColorKeyFrame> のようなスプライン キー フレームは、<xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> プロパティの値に従って、ある値から次の値への可変遷移を作成します。</span><span class="sxs-lookup"><span data-stu-id="e8ad5-112">Spline key frames like <xref:System.Windows.Media.Animation.SplineColorKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="e8ad5-113">この例では、色の変化は最初はゆっくりしていますが、時間セグメントの終点に向かって急激に速くなります。</span><span class="sxs-lookup"><span data-stu-id="e8ad5-113">In this example, the change in color begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/ColorAnimationUsingKeyFramesExample.cs#coloranimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/coloranimationusingkeyframesexample.vb#coloranimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ColorAnimationUsingKeyFramesExample.xaml#coloranimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="e8ad5-114">サンプル全体については、「[キーフレーム アニメーションのサンプル](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8ad5-114">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8ad5-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="e8ad5-115">See also</span></span>

- <xref:System.Windows.Media.SolidColorBrush.Color%2A>
- <xref:System.Windows.Media.SolidColorBrush>
- <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>
- [<span data-ttu-id="e8ad5-116">キー フレーム アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="e8ad5-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="e8ad5-117">キー フレームに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="e8ad5-117">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
