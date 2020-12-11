---
title: '方法: 3D シーンで素材プロパティをアニメーション化する'
ms.date: 03/30/2017
helpviewer_keywords:
- Material properties [WPF], animating in 3D scenes
- animation [WPF], Material properties in 3D scenes
- 3D scenes [WPF], animating Material properties
ms.assetid: 229fd6eb-7401-4992-b0c9-8b28de230c0f
ms.openlocfilehash: db59debcd7558cde52d8604cb04c8c4e68921825
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980200"
---
# <a name="how-to-animate-material-properties-in-a-3d-scene"></a><span data-ttu-id="5ee04-102">方法: 3D シーンで素材プロパティをアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="5ee04-102">How to: Animate Material Properties in a 3D Scene</span></span>
<span data-ttu-id="5ee04-103">この例では、3D モデルに適用された <xref:System.Windows.Media.Media3D.Material> の <xref:System.Windows.Media.Brush.Opacity%2A> プロパティをアニメーション化する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5ee04-103">This example shows how to animate the <xref:System.Windows.Media.Brush.Opacity%2A> property of the <xref:System.Windows.Media.Media3D.Material> applied to a 3D model.</span></span>  
  
 <span data-ttu-id="5ee04-104">次のコード例では、3D オブジェクトに適用される <xref:System.Windows.Media.Media3D.Material> として使用される <xref:System.Windows.Media.LinearGradientBrush> を定義します。</span><span class="sxs-lookup"><span data-stu-id="5ee04-104">The following code example defines the <xref:System.Windows.Media.LinearGradientBrush> used as the <xref:System.Windows.Media.Media3D.Material> applied to the 3D object.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline1)]  
  
 <span data-ttu-id="5ee04-105">この <xref:System.Windows.Media.LinearGradientBrush> の <xref:System.Windows.Media.Brush.Opacity%2A> プロパティは、次のコード例を使用してアニメーション化されます。</span><span class="sxs-lookup"><span data-stu-id="5ee04-105">The <xref:System.Windows.Media.Brush.Opacity%2A> property of this <xref:System.Windows.Media.LinearGradientBrush> is animated using the code example below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline2)]  
  
## <a name="example"></a><span data-ttu-id="5ee04-106">例</span><span class="sxs-lookup"><span data-stu-id="5ee04-106">Example</span></span>  
 <span data-ttu-id="5ee04-107">次のコードは、サンプル全体を示しています。</span><span class="sxs-lookup"><span data-stu-id="5ee04-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="5ee04-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="5ee04-108">See also</span></span>

- [<span data-ttu-id="5ee04-109">3D シーンを作成する</span><span class="sxs-lookup"><span data-stu-id="5ee04-109">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="5ee04-110">3D グラフィックスの概要</span><span class="sxs-lookup"><span data-stu-id="5ee04-110">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
