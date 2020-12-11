---
title: '方法: キー フレーム (QuaternionAnimationUsingKeyFrames) を使用して 3D 回転をアニメーション化する'
ms.date: 03/30/2017
helpviewer_keywords:
- 3D translations [WPF], animating [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
- key frames [WPF], QuaternionAnimationUsingKeyFrames
- animation [WPF], 3D translations [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
ms.assetid: 09e5707b-7523-4a08-9aa7-bb13cbedccdf
ms.openlocfilehash: 5273183aaa49a743cc401dec0b4b16bae09e3129
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984804"
---
# <a name="how-to-animate-a-3d-rotation-using-key-frames-quaternionanimationusingkeyframes"></a><span data-ttu-id="39d0c-102">方法: キー フレーム (QuaternionAnimationUsingKeyFrames) を使用して 3D 回転をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="39d0c-102">How to: Animate a 3D Rotation Using Key Frames (QuaternionAnimationUsingKeyFrames)</span></span>
<span data-ttu-id="39d0c-103">次の例では、3D オブジェクトを回転させるために <xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames> が使用されています。</span><span class="sxs-lookup"><span data-stu-id="39d0c-103">In the following example, <xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames> is used to make a 3D object rotate.</span></span> <span data-ttu-id="39d0c-104">このアニメーションでは、次のキー フレームが使用されます。</span><span class="sxs-lookup"><span data-stu-id="39d0c-104">This animation uses the following key frames:</span></span>  
  
1. <span data-ttu-id="39d0c-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> は、値間に滑らかな線形補間を作成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="39d0c-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> is used to create a smooth, linear interpolation between values.</span></span>  
  
2. <span data-ttu-id="39d0c-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> は、ある値から別の値への突然の "変化" を作成するために使用されます (補間なし)。</span><span class="sxs-lookup"><span data-stu-id="39d0c-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> is used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3. <span data-ttu-id="39d0c-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> は、<xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> プロパティに応じて、値間に可変遷移を作成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="39d0c-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> is used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="39d0c-108">以下の例では、アニメーションのこの部分は、ゆっくりと始まりますが、時間セグメントの終点に向かって急激に速くなります。</span><span class="sxs-lookup"><span data-stu-id="39d0c-108">In the example below, this part of the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39d0c-109">例</span><span class="sxs-lookup"><span data-stu-id="39d0c-109">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationUsingKeyFramesExample.xaml#quaternionanimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="39d0c-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="39d0c-110">See also</span></span>

- [<span data-ttu-id="39d0c-111">ストーリーボードを使用して 3D 回転をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="39d0c-111">Animate a 3D Rotation Using Storyboards</span></span>](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [<span data-ttu-id="39d0c-112">Rotation3DAnimation を使用して 3D 回転をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="39d0c-112">Animate a 3D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [<span data-ttu-id="39d0c-113">四元数を使用して 3D 回転をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="39d0c-113">Animate a 3D Rotation Using Quaternions</span></span>](how-to-animate-a-3-d-rotation-using-quaternions.md)
- [<span data-ttu-id="39d0c-114">キー フレーム (Rotation3DAnimationUsingKeyFrames) を使用して 3D 回転をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="39d0c-114">Animate a 3D Rotation Using Key Frames (Rotation3DAnimationUsingKeyFrames)</span></span>](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [<span data-ttu-id="39d0c-115">3D グラフィックスの概要</span><span class="sxs-lookup"><span data-stu-id="39d0c-115">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="39d0c-116">キー フレーム アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="39d0c-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
