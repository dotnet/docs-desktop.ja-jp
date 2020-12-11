---
title: '方法: 3D モデルのスケールを変換する'
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], 3D objects
- 3D objects [WPF], scaling
ms.assetid: f3fdfe33-f7dc-44b0-84a5-e43b89947f35
ms.openlocfilehash: be41a0e10929912c1b54bf7140d743d9453199bf
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983236"
---
# <a name="how-to-transform-the-scale-of-a-3d-model"></a><span data-ttu-id="8964a-102">方法: 3D モデルのスケールを変換する</span><span class="sxs-lookup"><span data-stu-id="8964a-102">How to: Transform the Scale of a 3D Model</span></span>
<span data-ttu-id="8964a-103">次の例では、3D オブジェクトを拡大縮小する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8964a-103">This example shows how to scale a 3D object.</span></span> <span data-ttu-id="8964a-104">3D オブジェクトを拡大縮小するには、<xref:System.Windows.Media.Media3D.ScaleTransform3D> を使用します。</span><span class="sxs-lookup"><span data-stu-id="8964a-104">To scale a 3D object, use a <xref:System.Windows.Media.Media3D.ScaleTransform3D>.</span></span> <span data-ttu-id="8964a-105"><xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>、<xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>、<xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> の各プロパティは、指定した係数で要素のサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="8964a-105">The <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>, <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>, and <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> properties resize the element by the factor you specify.</span></span> <span data-ttu-id="8964a-106">たとえば、<xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> 値が 1.5 の場合、オブジェクトは元の幅の 150% に拡大します。</span><span class="sxs-lookup"><span data-stu-id="8964a-106">For example, a <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> value of 1.5 stretches an object to 150 percent of its original width.</span></span> <span data-ttu-id="8964a-107"><xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> 値が 0.5 の場合は、オブジェクトの高さが 50% 縮小します。</span><span class="sxs-lookup"><span data-stu-id="8964a-107">A <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> value of 0.5 shrinks the height of an object by 50 percent.</span></span> <span data-ttu-id="8964a-108">次のコードは、<xref:System.Windows.Media.Media3D.GeometryModel3D> の変換として <xref:System.Windows.Media.Media3D.ScaleTransform3D> を使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="8964a-108">The code below shows using a <xref:System.Windows.Media.Media3D.ScaleTransform3D> as the transform for a <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="8964a-109">例</span><span class="sxs-lookup"><span data-stu-id="8964a-109">Example</span></span>  
 <span data-ttu-id="8964a-110">次のコードは、サンプル全体を示しています。</span><span class="sxs-lookup"><span data-stu-id="8964a-110">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="8964a-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="8964a-111">See also</span></span>

- [<span data-ttu-id="8964a-112">3D 変換をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="8964a-112">Animate 3D Translations</span></span>](how-to-animate-3-d-translations.md)
- [<span data-ttu-id="8964a-113">3D シーンを作成する</span><span class="sxs-lookup"><span data-stu-id="8964a-113">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="8964a-114">3D グラフィックスの概要</span><span class="sxs-lookup"><span data-stu-id="8964a-114">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
