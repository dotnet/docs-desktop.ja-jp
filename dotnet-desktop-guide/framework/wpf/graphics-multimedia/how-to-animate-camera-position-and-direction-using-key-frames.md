---
title: '方法: キー フレームを使用してカメラの位置および方向をアニメーション化する'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], camera direction with key frames
- key frames [WPF], animating camera direction
- animation [WPF], camera position with key frames
- camera position [WPF], animating with key frames
- key frames [WPF], animating camera position
- camera direction [WPF], animating with key frames
ms.assetid: 5753024e-0057-454d-947f-43ea686879c7
ms.openlocfilehash: 28471f9b42140a6c75b043d33939503528b63194
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985052"
---
# <a name="how-to-animate-camera-position-and-direction-using-key-frames"></a><span data-ttu-id="748d2-102">方法: キー フレームを使用してカメラの位置および方向をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="748d2-102">How to: Animate Camera Position and Direction Using Key Frames</span></span>
<span data-ttu-id="748d2-103">次の例では、<xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> を使用して、3D シーンにおける <xref:System.Windows.Media.Media3D.PerspectiveCamera> の位置をアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="748d2-103">In the following example, <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> is used to animate the position of a <xref:System.Windows.Media.Media3D.PerspectiveCamera> in a 3D scene.</span></span> <span data-ttu-id="748d2-104">また、<xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> を使用して、3D シーンでカメラが指す方向をアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="748d2-104">In addition, <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> is used to animate the direction the camera is pointing in the 3D scene.</span></span> <span data-ttu-id="748d2-105">どちらのアニメーションでも、次のようなキー フレームを使用して、一連のアニメーション効果を生み出します。</span><span class="sxs-lookup"><span data-stu-id="748d2-105">Both of these animations use several key frames which create a series of animation effects:</span></span>  
  
1. <span data-ttu-id="748d2-106"><xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame> と <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> を使用して、値間に滑らかな線形補間を作成します。</span><span class="sxs-lookup"><span data-stu-id="748d2-106"><xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame> and <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> are used to create a smooth, linear interpolation between values.</span></span>  
  
2. <span data-ttu-id="748d2-107"><xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame> と <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> を使用して、ある値から別の値への突然の "変化" を作成します。</span><span class="sxs-lookup"><span data-stu-id="748d2-107"><xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame> and <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> are used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3. <span data-ttu-id="748d2-108"><xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame> と <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> を使用して、<xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> プロパティに応じて値間に可変遷移を作成します。</span><span class="sxs-lookup"><span data-stu-id="748d2-108"><xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame> and <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> are used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="748d2-109">次の例では、アニメーションはゆっくりと始まりますが、時間セグメントの終点に向かって急激に速くなります。</span><span class="sxs-lookup"><span data-stu-id="748d2-109">In the example below, the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="748d2-110">例</span><span class="sxs-lookup"><span data-stu-id="748d2-110">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationUsingKeyFramesExample.xaml#pointvector3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="748d2-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="748d2-111">See also</span></span>

- [<span data-ttu-id="748d2-112">3D シーンでカメラの位置および方向をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="748d2-112">Animate Camera Position and Direction in a 3D Scene</span></span>](how-to-animate-camera-position-and-direction-in-a-3d-scene.md)
- [<span data-ttu-id="748d2-113">3D グラフィックスの概要</span><span class="sxs-lookup"><span data-stu-id="748d2-113">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
