---
title: '方法: キー フレームを使用して点をアニメーション化する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], animating Points with
- Points [WPF], animating with key frames
- animation [WPF], Points with key frames
ms.assetid: d2e2ef10-0773-4133-856e-d41c09f60ded
ms.openlocfilehash: edcba36644cf78d6e98f934d9bd8b593af38b328
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984144"
---
# <a name="how-to-animate-a-point-by-using-key-frames"></a><span data-ttu-id="c8f71-102">方法: キー フレームを使用して点をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="c8f71-102">How to: Animate a Point by Using Key Frames</span></span>
<span data-ttu-id="c8f71-103">この例では、<xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> クラスを使用して <xref:System.Windows.Point> をアニメーション化する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c8f71-103">This example shows how to use the <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> class to animate a <xref:System.Windows.Point>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8f71-104">例</span><span class="sxs-lookup"><span data-stu-id="c8f71-104">Example</span></span>  
 <span data-ttu-id="c8f71-105">次の例では、三角形のパスに沿って楕円を移動します。</span><span class="sxs-lookup"><span data-stu-id="c8f71-105">The following example moves an ellipse along a triangular path.</span></span> <span data-ttu-id="c8f71-106">この例では、<xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> クラスを使用して、<xref:System.Windows.Media.EllipseGeometry> の <xref:System.Windows.Media.EllipseGeometry.Center%2A> プロパティをアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="c8f71-106">The example uses the <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.EllipseGeometry.Center%2A> property of an <xref:System.Windows.Media.EllipseGeometry>.</span></span> <span data-ttu-id="c8f71-107">このアニメーションは、次の方法で 3 つのキー フレームを使用します。</span><span class="sxs-lookup"><span data-stu-id="c8f71-107">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="c8f71-108">最初の 0.5 秒間は、<xref:System.Windows.Media.Animation.LinearPointKeyFrame> クラスのインスタンスを使用して、楕円を開始位置からパスに沿って一定の速度で移動します。</span><span class="sxs-lookup"><span data-stu-id="c8f71-108">During the first half second, uses an instance of the <xref:System.Windows.Media.Animation.LinearPointKeyFrame> class to move the ellipse along a path at a steady rate from its starting position.</span></span> <span data-ttu-id="c8f71-109"><xref:System.Windows.Media.Animation.LinearPointKeyFrame> のような線形キー フレームは、ある値から次の値への滑らかな線状補間を作成します。</span><span class="sxs-lookup"><span data-stu-id="c8f71-109">Linear key frames like <xref:System.Windows.Media.Animation.LinearPointKeyFrame> create a smooth linear interpolation between values.</span></span>  
  
2. <span data-ttu-id="c8f71-110">次の 0.5 秒の終わりに、<xref:System.Windows.Media.Animation.DiscretePointKeyFrame> クラスのインスタンスを使用して、楕円をパスに沿って次の位置に突然移動させます。</span><span class="sxs-lookup"><span data-stu-id="c8f71-110">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> class to suddenly move the ellipse along the path to the next position.</span></span> <span data-ttu-id="c8f71-111"><xref:System.Windows.Media.Animation.DiscretePointKeyFrame> のような不連続キー フレームは、ある値から次の値への突然の変化を作成します。</span><span class="sxs-lookup"><span data-stu-id="c8f71-111">Discrete key frames like <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> create sudden jumps between values.</span></span>  
  
3. <span data-ttu-id="c8f71-112">最後の 2 秒間は、<xref:System.Windows.Media.Animation.SplinePointKeyFrame> クラスのインスタンスを使用して、楕円を開始位置まで戻します。</span><span class="sxs-lookup"><span data-stu-id="c8f71-112">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplinePointKeyFrame> class to move the ellipse back to its starting position.</span></span> <span data-ttu-id="c8f71-113"><xref:System.Windows.Media.Animation.SplinePointKeyFrame> のようなスプライン キー フレームは、<xref:System.Windows.Media.Animation.SplinePointKeyFrame.KeySpline%2A> プロパティの値に従って、ある値から次の値への可変遷移を作成します。</span><span class="sxs-lookup"><span data-stu-id="c8f71-113">Spline key frames like <xref:System.Windows.Media.Animation.SplinePointKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplinePointKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="c8f71-114">この例では、アニメーションは最初はゆっくりしていますが、時間セグメントの終点に向かって急激に速くなります。</span><span class="sxs-lookup"><span data-stu-id="c8f71-114">In this example, the animation begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/PointAnimationUsingKeyFramesExample.cs#pointanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/pointanimationusingkeyframesexample.vb#pointanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/PointAnimationUsingKeyFramesExample.xaml#pointanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="c8f71-115">サンプル全体については、「[キーフレーム アニメーションのサンプル](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8f71-115">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
 <span data-ttu-id="c8f71-116">他のアニメーション例との一貫性を保つために、この例のコードでは、<xref:System.Windows.Media.Animation.Storyboard> オブジェクトを使用して <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> を適用しています。</span><span class="sxs-lookup"><span data-stu-id="c8f71-116">For consistency with other animation examples, the code versions of this example use a <xref:System.Windows.Media.Animation.Storyboard> object to apply the <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>.</span></span> <span data-ttu-id="c8f71-117">ただし、コード内で 1 つのアニメーションを適用する場合は、<xref:System.Windows.Media.Animation.Storyboard> よりも <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> メソッドを使用する方が簡単です。</span><span class="sxs-lookup"><span data-stu-id="c8f71-117">However, when applying a single animation in code, it's simpler to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method instead of using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="c8f71-118">例については、「[ストーリーボードを使用せずにプロパティをアニメーション化する](how-to-animate-a-property-without-using-a-storyboard.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8f71-118">For an example, see [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8f71-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="c8f71-119">See also</span></span>

- <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>
- <xref:System.Windows.Media.EllipseGeometry.Center%2A?displayProperty=nameWithType>
- <xref:System.Windows.Media.EllipseGeometry>
- [<span data-ttu-id="c8f71-120">キー フレーム アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="c8f71-120">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="c8f71-121">キー フレームに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="c8f71-121">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
