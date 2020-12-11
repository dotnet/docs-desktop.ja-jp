---
title: '方法: キー フレームを使用して境界線の太さをアニメーション化する'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], border thickness with key frames
- key frames [WPF], animating border thickness with
- border thickness [WPF], animating with key frames
ms.assetid: 3a9cb463-0a63-407d-aae7-3fbb1a559947
ms.openlocfilehash: 884b62e88c347449ae39caa9c028d09db39b9f4b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96979951"
---
# <a name="how-to-animate-the-thickness-of-a-border-by-using-key-frames"></a><span data-ttu-id="2661f-102">方法: キー フレームを使用して境界線の太さをアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="2661f-102">How to: Animate the Thickness of a Border by Using Key Frames</span></span>
<span data-ttu-id="2661f-103">この例では、<xref:System.Windows.Controls.Border> の <xref:System.Windows.Controls.Control.BorderThickness%2A> プロパティをアニメーション化する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2661f-103">This example shows how to animate the <xref:System.Windows.Controls.Control.BorderThickness%2A> property of a <xref:System.Windows.Controls.Border>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2661f-104">例</span><span class="sxs-lookup"><span data-stu-id="2661f-104">Example</span></span>  
 <span data-ttu-id="2661f-105">次の例では、<xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> クラスを使用して、<xref:System.Windows.Controls.Border> の <xref:System.Windows.Controls.Control.BorderThickness%2A> プロパティをアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="2661f-105">The following example uses the <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Controls.Control.BorderThickness%2A> property of a <xref:System.Windows.Controls.Border>.</span></span> <span data-ttu-id="2661f-106">このアニメーションは、次の方法で 3 つのキー フレームを使用します。</span><span class="sxs-lookup"><span data-stu-id="2661f-106">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="2661f-107">最初の 0.5 秒間は、<xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> クラスのインスタンスを使用して、境界線の太さを徐々に太くします。</span><span class="sxs-lookup"><span data-stu-id="2661f-107">During the first half second, uses an instance of the <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> class to gradually increase the thickness of the border.</span></span> <span data-ttu-id="2661f-108">この例では、<xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> を使用して、値と値の間に滑らかな線形増加を作成します。</span><span class="sxs-lookup"><span data-stu-id="2661f-108">The example uses <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> to create a smooth linear increase between values.</span></span>  
  
2. <span data-ttu-id="2661f-109">次の 0.5 秒間の終わりに、<xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> クラスのインスタンスを使用して、境界線の太さを突然太くします。</span><span class="sxs-lookup"><span data-stu-id="2661f-109">At the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> class to suddenly increase the thickness of the border.</span></span> <span data-ttu-id="2661f-110"><xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> から派生するような不連続キー フレームによって、ある値から次の値への突然の変化が作成されます。つまり、アニメーションの動きがぎくしゃくします。</span><span class="sxs-lookup"><span data-stu-id="2661f-110">Discrete key frames like those derived from <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
3. <span data-ttu-id="2661f-111">最後の 2 秒間は、<xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> クラスのインスタンスを使用して、境界線の太さを細くします。</span><span class="sxs-lookup"><span data-stu-id="2661f-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> class to decrease the thickness of the border.</span></span> <span data-ttu-id="2661f-112"><xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> から派生するようなスプライン キー フレームは、<xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A> プロパティの値に従って、ある値から次の値への可変遷移を作成します。</span><span class="sxs-lookup"><span data-stu-id="2661f-112">Spline key frames like those derived from <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="2661f-113">このキー フレームでは、アニメーションはゆっくりと始まりますが、時間セグメントの終点に向かって急激に速くなります。</span><span class="sxs-lookup"><span data-stu-id="2661f-113">In this key frame, the animation starts off slow and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-xaml[keyframes_snip#ThicknessAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ThicknessAnimationUsingKeyFramesExample.xaml#thicknessanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="2661f-114">サンプル全体については、「[キーフレーム アニメーションのサンプル](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2661f-114">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2661f-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="2661f-115">See also</span></span>

- <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>
- [<span data-ttu-id="2661f-116">キー フレーム アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="2661f-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="2661f-117">キー フレームに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="2661f-117">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
- [<span data-ttu-id="2661f-118">BorderThickness 値をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="2661f-118">Animate a BorderThickness Value</span></span>](../controls/how-to-animate-a-borderthickness-value.md)
