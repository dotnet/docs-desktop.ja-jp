---
title: '方法: Rotation3DAnimation を使用して 3D 回転をアニメーション化する'
ms.date: 03/30/2017
helpviewer_keywords:
- 3D translations [WPF], animating [WPF], with Rotation3DAnimation
- Rotation3DAnimation [WPF]
- animation [WPF], 3D translations [WPF], with Rotation3DAnimation
ms.assetid: a92223ec-b634-4f5e-8e79-d33bc43ecfb3
ms.openlocfilehash: 4016b2e17d273fc401d00e769ce721e6a381cc23
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984155"
---
# <a name="how-to-animate-a-3d-rotation-using-rotation3danimation"></a><span data-ttu-id="ae6f8-102">方法: Rotation3DAnimation を使用して 3D 回転をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="ae6f8-102">How to: Animate a 3D Rotation Using Rotation3DAnimation</span></span>
<span data-ttu-id="ae6f8-103">次の例は、<xref:System.Windows.Media.Animation.Rotation3DAnimation> を使用して、3D オブジェクトに適用される <xref:System.Windows.Media.Media3D.RotateTransform3D> オブジェクトの <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> プロパティをアニメーション化することによって、3D オブジェクトを "揺らし" ながら回転させる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="ae6f8-103">The following example shows how to make a 3D object rotate while it "wobbles" by using <xref:System.Windows.Media.Animation.Rotation3DAnimation> to animate the <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> property of the <xref:System.Windows.Media.Media3D.RotateTransform3D> object applied to the 3D object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae6f8-104">例</span><span class="sxs-lookup"><span data-stu-id="ae6f8-104">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#Rotation3DAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotation3DAnimationExample.xaml#rotation3danimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="ae6f8-105">関連項目</span><span class="sxs-lookup"><span data-stu-id="ae6f8-105">See also</span></span>

- [<span data-ttu-id="ae6f8-106">3D グラフィックスの概要</span><span class="sxs-lookup"><span data-stu-id="ae6f8-106">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="ae6f8-107">キー フレーム (Rotation3DAnimationUsingKeyFrames) を使用して 3D 回転をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="ae6f8-107">Animate a 3D Rotation Using Key Frames (Rotation3DAnimationUsingKeyFrames)</span></span>](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [<span data-ttu-id="ae6f8-108">ストーリーボードを使用して 3D 回転をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="ae6f8-108">Animate a 3D Rotation Using Storyboards</span></span>](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [<span data-ttu-id="ae6f8-109">四元数を使用して 3D 回転をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="ae6f8-109">Animate a 3D Rotation Using Quaternions</span></span>](how-to-animate-a-3-d-rotation-using-quaternions.md)
- [<span data-ttu-id="ae6f8-110">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="ae6f8-110">Animation Overview</span></span>](animation-overview.md)
