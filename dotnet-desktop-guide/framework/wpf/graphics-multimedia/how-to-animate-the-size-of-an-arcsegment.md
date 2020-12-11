---
title: '方法: ArcSegment のサイズをアニメーション化する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], animation
- animation [WPF], ArcSegment size
- ArcSegment [WPF], animating size
ms.assetid: f93a1065-b00a-4d7e-9d4b-37023f98186a
ms.openlocfilehash: d1b9db72c9d1ea47f3c1bc6476a3b579bc03eae2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96979954"
---
# <a name="how-to-animate-the-size-of-an-arcsegment"></a><span data-ttu-id="c71ff-102">方法: ArcSegment のサイズをアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="c71ff-102">How to: Animate the Size of an ArcSegment</span></span>
<span data-ttu-id="c71ff-103">この例では、<xref:System.Windows.Media.ArcSegment> の <xref:System.Windows.Media.ArcSegment.Size%2A> プロパティをアニメーション化する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c71ff-103">This example shows how to animate the <xref:System.Windows.Media.ArcSegment.Size%2A> property of an <xref:System.Windows.Media.ArcSegment>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c71ff-104">例</span><span class="sxs-lookup"><span data-stu-id="c71ff-104">Example</span></span>  
 <span data-ttu-id="c71ff-105">次の例では、<xref:System.Windows.Media.ArcSegment> を作成します。これは、画面に読み込まれたときに、その <xref:System.Windows.Media.ArcSegment.Size%2A> をアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="c71ff-105">The following example creates an <xref:System.Windows.Media.ArcSegment> that animates its <xref:System.Windows.Media.ArcSegment.Size%2A> when it loads on the screen.</span></span>  
  
 [!code-csharp[BasicAnimations_snip#SizeAnimationWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/SizeAnimationExample.cs#sizeanimationwholepage)]
 [!code-vb[BasicAnimations_snip#SizeAnimationWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/SizeAnimationExample.vb#sizeanimationwholepage)]  
  
 <span data-ttu-id="c71ff-106">ジオメトリとアニメーションのその他のサンプルについては、「[ジオメトリのサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c71ff-106">For additional geometry and animation samples, see the [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c71ff-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="c71ff-107">See also</span></span>

- <xref:System.Windows.Media.ArcSegment.Size%2A>
- <xref:System.Windows.Media.ArcSegment>
- [<span data-ttu-id="c71ff-108">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="c71ff-108">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="c71ff-109">ジオメトリの概要</span><span class="sxs-lookup"><span data-stu-id="c71ff-109">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="c71ff-110">ジオメトリに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="c71ff-110">Geometries How-to Topics</span></span>](geometries-how-to-topics.md)
- [<span data-ttu-id="c71ff-111">アニメーションおよびタイミングに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="c71ff-111">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
