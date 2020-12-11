---
title: '方法: 3D モデルに描画を適用する'
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3D models
- 3D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: 794ca9a48bcec42c3eee4d8da143f3ae9d27fcf2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984063"
---
# <a name="how-to-apply-a-drawing-to-a-3d-model"></a><span data-ttu-id="77103-102">方法: 3D モデルに描画を適用する</span><span class="sxs-lookup"><span data-stu-id="77103-102">How to: Apply a Drawing to a 3D Model</span></span>

<span data-ttu-id="77103-103">この例では、3D モデルに適用される <xref:System.Windows.Media.Media3D.Material> として <xref:System.Windows.Media.DrawingBrush> を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="77103-103">This example shows how to use a <xref:System.Windows.Media.DrawingBrush> as the <xref:System.Windows.Media.Media3D.Material> applied to a 3D model.</span></span>

<span data-ttu-id="77103-104">次のコードでは、<xref:System.Windows.Media.DrawingGroup> を <xref:System.Windows.Media.DrawingBrush> のコンテンツとして定義しています。</span><span class="sxs-lookup"><span data-stu-id="77103-104">The following code defines a <xref:System.Windows.Media.DrawingGroup> as the content of a <xref:System.Windows.Media.DrawingBrush>.</span></span>  <span data-ttu-id="77103-105"><xref:System.Windows.Media.DrawingBrush> は、3D 平面に適用される <xref:System.Windows.Media.Media3D.DiffuseMaterial> の <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> プロパティとして設定します。</span><span class="sxs-lookup"><span data-stu-id="77103-105">The <xref:System.Windows.Media.DrawingBrush> is set as the <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> property of the <xref:System.Windows.Media.Media3D.DiffuseMaterial> applied to a 3D plane.</span></span>

> [!NOTE]
> <span data-ttu-id="77103-106">次の図のような複雑なオブジェクトと値は、できるだけ再利用できるリソースとして定義し、コードを単純化するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="77103-106">It is often desirable to define complex objects and values like the drawing below as resources which can be reused and simplify your code.</span></span> <span data-ttu-id="77103-107">詳細については、「[XAML リソース](/dotnet/desktop-wpf/fundamentals/xaml-resources-define)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77103-107">See [XAML Resources](/dotnet/desktop-wpf/fundamentals/xaml-resources-define) for more information.</span></span>

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]

## <a name="example"></a><span data-ttu-id="77103-108">例</span><span class="sxs-lookup"><span data-stu-id="77103-108">Example</span></span>

<span data-ttu-id="77103-109">次のコードは、サンプル全体を示しています。</span><span class="sxs-lookup"><span data-stu-id="77103-109">The following code shows the entire sample.</span></span>

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]

## <a name="see-also"></a><span data-ttu-id="77103-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="77103-110">See also</span></span>

- [<span data-ttu-id="77103-111">XAML リソース</span><span class="sxs-lookup"><span data-stu-id="77103-111">XAML Resources</span></span>](/dotnet/desktop-wpf/fundamentals/xaml-resources-define)
- [<span data-ttu-id="77103-112">3D シーンを作成する</span><span class="sxs-lookup"><span data-stu-id="77103-112">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="77103-113">Drawing オブジェクトの概要</span><span class="sxs-lookup"><span data-stu-id="77103-113">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="77103-114">3D グラフィックスの概要</span><span class="sxs-lookup"><span data-stu-id="77103-114">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
