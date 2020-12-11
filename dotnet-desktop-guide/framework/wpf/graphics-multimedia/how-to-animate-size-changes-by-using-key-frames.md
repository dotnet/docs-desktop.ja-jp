---
title: '方法: キー フレームを使用してサイズの変更をアニメーション化する'
ms.date: 03/30/2017
helpviewer_keywords:
- key frames [WPF], animating size changes with
- animation [WPF], size changes with key frames
- size changes [WPF], animating with key frames
ms.assetid: 86bd2950-d4c9-4ec4-aa8d-7dc3ccadded4
ms.openlocfilehash: 42cecfc9df4304be4033ea39edc0517016de4a92
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980212"
---
# <a name="how-to-animate-size-changes-by-using-key-frames"></a><span data-ttu-id="7dd8b-102">方法: キー フレームを使用してサイズの変更をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="7dd8b-102">How to: Animate Size Changes by Using Key Frames</span></span>
<span data-ttu-id="7dd8b-103">この例では、キー フレームを使用してサイズの変更をアニメーション化する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7dd8b-103">This example shows how to animate size changes by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7dd8b-104">例</span><span class="sxs-lookup"><span data-stu-id="7dd8b-104">Example</span></span>  
 <span data-ttu-id="7dd8b-105">次の例では、<xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames> クラスを使用して、<xref:System.Windows.Media.ArcSegment> の <xref:System.Windows.Media.ArcSegment.Size%2A> プロパティをアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="7dd8b-105">The following example uses the <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.ArcSegment.Size%2A> property of an <xref:System.Windows.Media.ArcSegment>.</span></span> <span data-ttu-id="7dd8b-106">このアニメーションは、次の方法で 3 つのキー フレームを使用します。</span><span class="sxs-lookup"><span data-stu-id="7dd8b-106">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="7dd8b-107">アニメーションの最初の 0.5 秒間は、<xref:System.Windows.Media.Animation.LinearSizeKeyFrame> クラスのインスタンスを使用して、円弧のサイズを徐々に大きくします。<xref:System.Windows.Media.Animation.LinearSizeKeyFrame> のような線形キー フレームは、ある値から次の値への滑らかで直線的な遷移を作成します。</span><span class="sxs-lookup"><span data-stu-id="7dd8b-107">During the first half second of the animation, uses an instance of the <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> class to gradually increase the size of the arc. Linear key frames like <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> create a smooth linear transition between values.</span></span>  
  
2. <span data-ttu-id="7dd8b-108">次の 0.5 秒間の終わりに、<xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> クラスのインスタンスを使用して、円弧のサイズを突然大きくします。<xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> のような不連続キー フレームは、ある値から次の値への突然の変化を作成します。つまり、サイズが滑らかに変化するのではなく、急に変化します。</span><span class="sxs-lookup"><span data-stu-id="7dd8b-108">At the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> class to suddenly increase the size of the arc. Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> create sudden jumps between values, that is, the size changes occur suddenly and are not subtle.</span></span>  
  
3. <span data-ttu-id="7dd8b-109">最後の 2 秒間は、<xref:System.Windows.Media.Animation.SplineSizeKeyFrame> クラスのインスタンスを使用して、円弧のサイズを大きくします。<xref:System.Windows.Media.Animation.SplineSizeKeyFrame> のようなスプライン キー フレームは、<xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A> プロパティの値に従って、ある値から次の値への可変遷移を作成します。</span><span class="sxs-lookup"><span data-stu-id="7dd8b-109">Over the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> class to increase the size of the arc. Spline key frames like <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="7dd8b-110">この例では、円弧のサイズは最初はゆっくり大きくなりますが、時間セグメントの終点に向かって急激に大きくなります。</span><span class="sxs-lookup"><span data-stu-id="7dd8b-110">In this example, the size of the arc increases slowly at first and then increases exponentially toward the end of the time segment.</span></span>  
  
 [!code-xaml[keyframes_snip#SizeAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/SizeAnimationUsingKeyFramesExample.xaml#sizeanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="7dd8b-111">サンプル全体については、「[キーフレーム アニメーションのサンプル](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7dd8b-111">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dd8b-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="7dd8b-112">See also</span></span>

- <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>
- <xref:System.Windows.Media.ArcSegment.Size%2A>
- <xref:System.Windows.Media.ArcSegment>
- <xref:System.Windows.Media.Animation.LinearSizeKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>
- <xref:System.Windows.Media.Animation.SplineSizeKeyFrame>
- [<span data-ttu-id="7dd8b-113">キー フレーム アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="7dd8b-113">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="7dd8b-114">キー フレームに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="7dd8b-114">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
