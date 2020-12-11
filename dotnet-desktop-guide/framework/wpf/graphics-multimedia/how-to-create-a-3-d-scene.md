---
title: '方法: 3D シーンを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- scenes [WPF], 3D
- 3D scenes
ms.assetid: adb4a598-71a2-4dd5-b677-ea3fc11b78b2
ms.openlocfilehash: 36453894e06e7b59f339c21713449140c17f6851
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984763"
---
# <a name="how-to-create-a-3d-scene"></a><span data-ttu-id="aef71-102">方法: 3D シーンを作成する</span><span class="sxs-lookup"><span data-stu-id="aef71-102">How to: Create a 3D Scene</span></span>
<span data-ttu-id="aef71-103">この例では、回転した平らな 1 枚の紙のように見える 3D オブジェクトを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="aef71-103">This example shows how to create a 3D object that looks like a flat sheet of paper which has been rotated.</span></span> <span data-ttu-id="aef71-104">この単純な 3D シーンの作成には、次のコンポーネントと共に <xref:System.Windows.Controls.Viewport3D> が使用されます。</span><span class="sxs-lookup"><span data-stu-id="aef71-104">A <xref:System.Windows.Controls.Viewport3D> along with the following components are used to create this simple 3D scene:</span></span>  
  
- <span data-ttu-id="aef71-105"><xref:System.Windows.Media.Media3D.PerspectiveCamera> を使用してカメラが作成されます。</span><span class="sxs-lookup"><span data-stu-id="aef71-105">A camera is created using a <xref:System.Windows.Media.Media3D.PerspectiveCamera>.</span></span> <span data-ttu-id="aef71-106">カメラは、3D シーンのどの部分を表示できるかを指定します。</span><span class="sxs-lookup"><span data-stu-id="aef71-106">The camera specifies what part of the 3D scene is viewable.</span></span>  
  
- <span data-ttu-id="aef71-107"><xref:System.Windows.Media.Media3D.GeometryModel3D> の <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> プロパティを使用して、3D オブジェクト (1 枚の紙) の形状を指定するために、メッシュが作成されます。</span><span class="sxs-lookup"><span data-stu-id="aef71-107">A mesh is created to specify the shape of 3D object (sheet of paper) using the <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> property of <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
- <span data-ttu-id="aef71-108"><xref:System.Windows.Media.Media3D.GeometryModel3D> の <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> プロパティを使用して、オブジェクト (この例では線状グラデーション) の表面に表示される素材が指定されます。</span><span class="sxs-lookup"><span data-stu-id="aef71-108">A material is specified to be displayed on the surface of the object (linear gradient in this sample) using the <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> property of <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
- <span data-ttu-id="aef71-109"><xref:System.Windows.Media.Media3D.DirectionalLight> を使用して、オブジェクトに光をかけるためのライトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="aef71-109">A light is created to shine on the object using <xref:System.Windows.Media.Media3D.DirectionalLight>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aef71-110">例</span><span class="sxs-lookup"><span data-stu-id="aef71-110">Example</span></span>  
 <span data-ttu-id="aef71-111">次のコードは、XAML で 3D シーンを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="aef71-111">The code below shows how to create a 3D scene in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Basic3DShapeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/Basic3DShapeExample.xaml#basic3dshapeexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="aef71-112">例</span><span class="sxs-lookup"><span data-stu-id="aef71-112">Example</span></span>  
 <span data-ttu-id="aef71-113">次のコードは、手続き型コードで同じ 3D シーンを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="aef71-113">The code below shows how to create the same 3D scene in procedural code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="aef71-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="aef71-114">See also</span></span>

- [<span data-ttu-id="aef71-115">3D グラフィックスの概要</span><span class="sxs-lookup"><span data-stu-id="aef71-115">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
