---
title: '方法: 四元数を使用して 3D 回転をアニメーション化する'
ms.date: 03/30/2017
helpviewer_keywords:
- quaternions [WPF]
- animation [WPF], 3D translations [WPF], with quaternions
- 3D translations [WPF], animating [WPF], with quaternions
ms.assetid: adca9cb1-066b-4de8-abbb-6b4007579ee7
ms.openlocfilehash: 0d229b0a714cc53459943fae751ab4d4f787d7d8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984160"
---
# <a name="how-to-animate-a-3d-rotation-using-quaternions"></a><span data-ttu-id="19a17-102">方法: 四元数を使用して 3D 回転をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="19a17-102">How to: Animate a 3D Rotation Using Quaternions</span></span>
<span data-ttu-id="19a17-103">この例では、四元数を使用して 3D オブジェクトの回転をアニメーション化する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="19a17-103">This example shows how to animate a rotation of a 3D object using quaternions.</span></span>  
  
 <span data-ttu-id="19a17-104">次のコードは、<xref:System.Windows.Media.Media3D.RotateTransform3D> の <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> プロパティの値として使用される <xref:System.Windows.Media.Media3D.QuaternionRotation3D> を示しています。</span><span class="sxs-lookup"><span data-stu-id="19a17-104">The code below shows a <xref:System.Windows.Media.Media3D.QuaternionRotation3D> used as the value for the <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> property of a <xref:System.Windows.Media.Media3D.RotateTransform3D>.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline1)]  
  
 <span data-ttu-id="19a17-105">この <xref:System.Windows.Media.Media3D.QuaternionRotation3D> は、次のコードを使用して <xref:System.Windows.Media.Animation.Storyboard> 内の <xref:System.Windows.Media.Animation.QuaternionAnimation> でアニメーション化されます。</span><span class="sxs-lookup"><span data-stu-id="19a17-105">This <xref:System.Windows.Media.Media3D.QuaternionRotation3D> is animated with a <xref:System.Windows.Media.Animation.QuaternionAnimation> within a <xref:System.Windows.Media.Animation.Storyboard> using the code below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline2)]  
  
## <a name="example"></a><span data-ttu-id="19a17-106">例</span><span class="sxs-lookup"><span data-stu-id="19a17-106">Example</span></span>  
 <span data-ttu-id="19a17-107">次のコードは、サンプル全体を示しています。</span><span class="sxs-lookup"><span data-stu-id="19a17-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="19a17-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="19a17-108">See also</span></span>

- [<span data-ttu-id="19a17-109">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="19a17-109">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="19a17-110">3D シーンを作成する</span><span class="sxs-lookup"><span data-stu-id="19a17-110">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="19a17-111">3D グラフィックスの概要</span><span class="sxs-lookup"><span data-stu-id="19a17-111">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="19a17-112">変換の概要</span><span class="sxs-lookup"><span data-stu-id="19a17-112">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="19a17-113">ストーリーボードを使用して 3D 回転をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="19a17-113">Animate a 3D Rotation Using Storyboards</span></span>](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [<span data-ttu-id="19a17-114">Rotation3DAnimation を使用して 3D 回転をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="19a17-114">Animate a 3D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
