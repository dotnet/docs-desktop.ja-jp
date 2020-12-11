---
title: '方法: パスに沿ってオブジェクトをアニメーション化する (ポイント アニメーション)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (point animation)
- point animation [WPF]
ms.assetid: 1fa3f817-35bc-41a1-b366-f5a20b70da0c
ms.openlocfilehash: eff0c24a9369ffaa0cfca1cc46af4eff39f58a38
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984068"
---
# <a name="how-to-animate-an-object-along-a-path-point-animation"></a><span data-ttu-id="98e21-102">方法: パスに沿ってオブジェクトをアニメーション化する (ポイント アニメーション)</span><span class="sxs-lookup"><span data-stu-id="98e21-102">How to: Animate an Object Along a Path (Point Animation)</span></span>
<span data-ttu-id="98e21-103">この例では、<xref:System.Windows.Media.Animation.PointAnimationUsingPath> オブジェクトを使用して、曲線のパスに沿って <xref:System.Windows.Point> をアニメーション化する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="98e21-103">This example shows how to use a <xref:System.Windows.Media.Animation.PointAnimationUsingPath> object to animate a <xref:System.Windows.Point> along a curved path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="98e21-104">例</span><span class="sxs-lookup"><span data-stu-id="98e21-104">Example</span></span>  
 <span data-ttu-id="98e21-105">次の例では、<xref:System.Windows.Media.PathGeometry> で定義されたパスに沿って <xref:System.Windows.Media.EllipseGeometry> を移動します。</span><span class="sxs-lookup"><span data-stu-id="98e21-105">The following example moves an <xref:System.Windows.Media.EllipseGeometry> along a path defined by a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="98e21-106">楕円のジオメトリの <xref:System.Windows.Media.EllipseGeometry.Center%2A> プロパティは、<xref:System.Windows.Point> 値を受け取り、その位置を指定します。楕円ジオメトリを移動するには、その <xref:System.Windows.Media.EllipseGeometry.Center%2A> プロパティをアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="98e21-106">The ellipse geometry's <xref:System.Windows.Media.EllipseGeometry.Center%2A> property, which takes a <xref:System.Windows.Point> value, specifies its position; to move the ellipse geometry, you animate its <xref:System.Windows.Media.EllipseGeometry.Center%2A> property.</span></span> <span data-ttu-id="98e21-107">この例では、<xref:System.Windows.Media.Animation.PointAnimationUsingPath> を使用して、<xref:System.Windows.Media.EllipseGeometry> オブジェクトの <xref:System.Windows.Media.EllipseGeometry.Center%2A> プロパティをアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="98e21-107">The example uses a <xref:System.Windows.Media.Animation.PointAnimationUsingPath> to animate the <xref:System.Windows.Media.EllipseGeometry> object's <xref:System.Windows.Media.EllipseGeometry.Center%2A> property.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#PointAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/pointanimationusingpathexample.xaml#pointanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/PointAnimationUsingPathExample.cs#pointanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/PointAnimationUsingPathExample.vb#pointanimationusingpathwholepage)]  
  
 <span data-ttu-id="98e21-108">サンプル全体については、「[パス アニメーションのサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98e21-108">For the complete sample, see [Path Animation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span></span>  
  
 <span data-ttu-id="98e21-109">前のサンプルのコード バージョンでは、1 つのアニメーションしか適用しないにもかかわらず、<xref:System.Windows.Media.Animation.Storyboard> を使用して <xref:System.Windows.Media.EllipseGeometry> をアニメーション化しました。</span><span class="sxs-lookup"><span data-stu-id="98e21-109">The code version of the preceding sample used a <xref:System.Windows.Media.Animation.Storyboard> to animate the <xref:System.Windows.Media.EllipseGeometry>, even though only one animation was applied.</span></span> <span data-ttu-id="98e21-110">多くの場合、<xref:System.Windows.Media.Animation.Storyboard> は複数のアニメーションを適用する最も簡単な方法です。その理由は、これらのアニメーションを同じ <xref:System.Windows.Media.Animation.Storyboard> で制御できるためです。</span><span class="sxs-lookup"><span data-stu-id="98e21-110">A <xref:System.Windows.Media.Animation.Storyboard> is often the easiest way to apply multiple animations because these animations can be controlled by the same <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="98e21-111">ただし、コードを使用する場合に 1 つのアニメーションをプロパティに適用するさらに簡単な方法は、<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> メソッドを使用することです。</span><span class="sxs-lookup"><span data-stu-id="98e21-111">However, an easier way to apply a single animation to a property when using code is to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method.</span></span> <span data-ttu-id="98e21-112">例については、「[ストーリーボードを使用せずにプロパティをアニメーション化する](how-to-animate-a-property-without-using-a-storyboard.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98e21-112">For an example, see [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98e21-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="98e21-113">See also</span></span>

- [<span data-ttu-id="98e21-114">パス アニメーションのサンプル</span><span class="sxs-lookup"><span data-stu-id="98e21-114">Path Animation Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
- [<span data-ttu-id="98e21-115">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="98e21-115">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="98e21-116">パス アニメーションに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="98e21-116">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
