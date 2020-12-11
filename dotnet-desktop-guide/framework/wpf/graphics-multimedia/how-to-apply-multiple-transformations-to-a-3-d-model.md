---
title: '方法: 複数の変換を 3D モデルに適用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3D models [WPF], applying multiple transformations to
ms.assetid: cb72245a-5560-4c96-9f58-593c66296992
ms.openlocfilehash: 6400d224fb51b93c76c5e9798b4bcc68ff3b9de6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985051"
---
# <a name="how-to-apply-multiple-transformations-to-a-3d-model"></a><span data-ttu-id="c8748-102">方法: 複数の変換を 3D モデルに適用する</span><span class="sxs-lookup"><span data-stu-id="c8748-102">How to: Apply Multiple Transformations to a 3D Model</span></span>
<span data-ttu-id="c8748-103">このサンプルでは、<xref:System.Windows.Media.Media3D.RotateTransform3D> と <xref:System.Windows.Media.Media3D.ScaleTransform3D> を使用して、3D モデルを回転させたりスケールを変更したりする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c8748-103">This sample shows how to use a <xref:System.Windows.Media.Media3D.RotateTransform3D> and a <xref:System.Windows.Media.Media3D.ScaleTransform3D> to rotate and change the scale of a 3D model.</span></span> <span data-ttu-id="c8748-104">次のコードは、XAML で <xref:System.Windows.Media.Media3D.GeometryModel3D> の <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> プロパティにこれらの変換を適用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="c8748-104">The code below shows how to apply these transforms to the <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D> in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Multiple3DTransformationsExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/MultipleTransformationsExample.xaml#multiple3dtransformationsexampleinline1)]  
  
 <span data-ttu-id="c8748-105">コードは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c8748-105">In code:</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/MultipleTransformationsExample.cs#multiple3dtransformationscodeexampleinline1)]
 [!code-vb[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/multipletransformationsexample.vb#multiple3dtransformationscodeexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="c8748-106">例</span><span class="sxs-lookup"><span data-stu-id="c8748-106">Example</span></span>  
 <span data-ttu-id="c8748-107">次のコードは、XAML でサンプル全体を示しています。</span><span class="sxs-lookup"><span data-stu-id="c8748-107">The following code shows the entire sample in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Multiple3DTransformationsExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/MultipleTransformationsExample.xaml#multiple3dtransformationsexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="c8748-108">例</span><span class="sxs-lookup"><span data-stu-id="c8748-108">Example</span></span>  
 <span data-ttu-id="c8748-109">コードでサンプル全体を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c8748-109">Below is the entire sample in code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/MultipleTransformationsExample.cs#multiple3dtransformationscodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/multipletransformationsexample.vb#multiple3dtransformationscodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="c8748-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="c8748-110">See also</span></span>

- [<span data-ttu-id="c8748-111">3D モデルのスケールを変換する</span><span class="sxs-lookup"><span data-stu-id="c8748-111">Transform the Scale of a 3D Model</span></span>](how-to-transform-the-scale-of-a-3-d-model.md)
