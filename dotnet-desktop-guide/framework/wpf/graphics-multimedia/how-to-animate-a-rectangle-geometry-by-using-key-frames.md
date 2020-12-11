---
title: '方法: キー フレームを使用して四角形のジオメトリをアニメーション化する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], animating RectangleGeometry objects with
- RectangleGeometry objects [WPF], animating with key frames
- animation [WPF], RectangleGeometry objects with key frames
ms.assetid: a8b45ceb-0e32-4ba1-928f-df6d30db17c6
ms.openlocfilehash: bcc9e7f198b8a20ffe13daf6508fb8a735937652
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974929"
---
# <a name="how-to-animate-a-rectangle-geometry-by-using-key-frames"></a><span data-ttu-id="d5ad4-102">方法: キー フレームを使用して四角形のジオメトリをアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="d5ad4-102">How to: Animate a Rectangle Geometry by Using Key Frames</span></span>
<span data-ttu-id="d5ad4-103">この例では、キー フレームを使用して <xref:System.Windows.Media.RectangleGeometry> の <xref:System.Windows.Media.RectangleGeometry.Rect%2A> プロパティをアニメーション化する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-103">This example shows how to animate the <xref:System.Windows.Media.RectangleGeometry.Rect%2A> property of a <xref:System.Windows.Media.RectangleGeometry> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5ad4-104">例</span><span class="sxs-lookup"><span data-stu-id="d5ad4-104">Example</span></span>  
 <span data-ttu-id="d5ad4-105">次の例では、<xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> クラスを使用して、<xref:System.Windows.Media.RectangleGeometry> の <xref:System.Windows.Media.RectangleGeometry.Rect%2A> プロパティをアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-105">The following example uses the <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.RectangleGeometry.Rect%2A> property of a <xref:System.Windows.Media.RectangleGeometry>.</span></span> <span data-ttu-id="d5ad4-106">このアニメーションは、次の方法で 3 つのキー フレームを使用します。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-106">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="d5ad4-107">最初の 2 秒間は、<xref:System.Windows.Media.Animation.LinearRectKeyFrame> クラスのインスタンスを使用して、四角形の位置、幅、および高さが徐々に変化する様子をアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-107">During the first two seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearRectKeyFrame> class to animate a gradual change in the position, width, and height of a rectangle.</span></span> <span data-ttu-id="d5ad4-108"><xref:System.Windows.Media.Animation.LinearRectKeyFrame> のような線形キー フレームは、ある値から次の値への滑らかで直線的な遷移を作成します。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-108">Linear key frames like <xref:System.Windows.Media.Animation.LinearRectKeyFrame> create a smooth linear transition between values.</span></span>  
  
2. <span data-ttu-id="d5ad4-109">次の 0.5 秒間の後わりに、<xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> クラスのインスタンスを使用して、四角形の高さを突然低くします。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-109">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> class to suddenly decrease the height of the rectangle.</span></span> <span data-ttu-id="d5ad4-110"><xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> のような不連続キー フレームは、ある値から次の値への突然の変化を作成します。つまり、高さの減少は急速に行われ、滑らかではありません。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-110">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> create sudden changes between values, that is, the decrease in height occurs quickly and is not subtle.</span></span>  
  
3. <span data-ttu-id="d5ad4-111">最後の 2 秒間は、<xref:System.Windows.Media.Animation.SplineRectKeyFrame> クラスのインスタンスを使用して、四角形を元のサイズと位置に戻します。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineRectKeyFrame> class to change the rectangle back to its original size and position.</span></span> <span data-ttu-id="d5ad4-112"><xref:System.Windows.Media.Animation.SplineRectKeyFrame> のようなスプライン キー フレームは、<xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> プロパティの値に従って、ある値から次の値への可変遷移を作成します。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-112">Spline key frames like <xref:System.Windows.Media.Animation.SplineRectKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="d5ad4-113">この例では、変化は最初はゆっくりしていますが、時間セグメントの終点に向かって急激に速くなります。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-113">In this example, the change begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/RectAnimationUsingKeyFramesExample.cs#rectanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/rectanimationusingkeyframesexample.vb#rectanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/RectAnimationUsingKeyFramesExample.xaml#rectanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="d5ad4-114">サンプル全体については、「[キーフレーム アニメーションのサンプル](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5ad4-114">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5ad4-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="d5ad4-115">See also</span></span>

- <xref:System.Windows.Media.RectangleGeometry>
- <xref:System.Windows.Media.RectangleGeometry.Rect%2A>
- <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>
- [<span data-ttu-id="d5ad4-116">キー フレーム アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="d5ad4-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="d5ad4-117">キー フレームに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="d5ad4-117">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
