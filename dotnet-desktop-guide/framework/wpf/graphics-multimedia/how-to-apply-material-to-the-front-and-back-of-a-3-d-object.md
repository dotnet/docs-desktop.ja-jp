---
title: '方法: 3D オブジェクトの前面および背面に素材を適用する'
ms.date: 03/30/2017
helpviewer_keywords:
- 3D objects [WPF], applying Material class
- Material class [WPF], applying to both sides of 3D object
- classes [WPF], Material
ms.assetid: d93c8ad6-4939-4d29-9544-4d16d98093c1
ms.openlocfilehash: 5c24879d97e7857fb07fcef4a9ba8efa901e4a39
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96979918"
---
# <a name="how-to-apply-material-to-the-front-and-back-of-a-3d-object"></a><span data-ttu-id="9bf5e-102">方法: 3D オブジェクトの前面および背面に素材を適用する</span><span class="sxs-lookup"><span data-stu-id="9bf5e-102">How to: Apply Material to the Front and Back of a 3D Object</span></span>
<span data-ttu-id="9bf5e-103">次の例では、3D オブジェクトの前面および背面に <xref:System.Windows.Media.Media3D.Material> を適用し、オブジェクトをアニメーション化してオブジェクトの両面を表示する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9bf5e-103">The following example shows how to apply a <xref:System.Windows.Media.Media3D.Material> to the front and back of a 3D object and animate the object to show both sides of the object.</span></span> <span data-ttu-id="9bf5e-104"><xref:System.Windows.Media.Media3D.GeometryModel3D> の <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> プロパティを使用して、オブジェクトの前面に赤色の <xref:System.Windows.Media.Brush> を適用し、<xref:System.Windows.Media.Media3D.GeometryModel3D> の <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> プロパティを使用して、オブジェクトの背面に青色の <xref:System.Windows.Media.Brush> を適用します。</span><span class="sxs-lookup"><span data-stu-id="9bf5e-104">The <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D> is used to apply a red <xref:System.Windows.Media.Brush> to the front side of the object and the <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> property of the <xref:System.Windows.Media.Media3D.GeometryModel3D> is used to apply a blue <xref:System.Windows.Media.Brush> to the back side of the object.</span></span> <span data-ttu-id="9bf5e-105">次のコードは、オブジェクトへの素材の適用を示しています。</span><span class="sxs-lookup"><span data-stu-id="9bf5e-105">The code below shows the application of the materials to the object:</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="9bf5e-106">例</span><span class="sxs-lookup"><span data-stu-id="9bf5e-106">Example</span></span>  
 <span data-ttu-id="9bf5e-107">次のコードは、サンプル全体を示しています。</span><span class="sxs-lookup"><span data-stu-id="9bf5e-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="9bf5e-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="9bf5e-108">See also</span></span>

- [<span data-ttu-id="9bf5e-109">3D シーンを作成する</span><span class="sxs-lookup"><span data-stu-id="9bf5e-109">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="9bf5e-110">3D グラフィックスの概要</span><span class="sxs-lookup"><span data-stu-id="9bf5e-110">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="9bf5e-111">3D シーンで素材プロパティをアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="9bf5e-111">Animate Material Properties in a 3D Scene</span></span>](how-to-animate-material-properties-in-a-3-d-scene.md)
- [<span data-ttu-id="9bf5e-112">3D オブジェクトに発色マテリアルを適用する</span><span class="sxs-lookup"><span data-stu-id="9bf5e-112">Apply Emissive Material to a 3D Object</span></span>](how-to-apply-emissive-material-to-a-3-d-object.md)
