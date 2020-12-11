---
title: '方法: パスに沿ってオブジェクトをアニメーション化する (ダブル アニメーション)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (double animation)
- double animation [WPF]
ms.assetid: 5a3c4a99-f303-42ad-a52a-e4794bb1798e
ms.openlocfilehash: 084caac26fd68b6914ec3858652ec44557a0dbd7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984075"
---
# <a name="how-to-animate-an-object-along-a-path-double-animation"></a><span data-ttu-id="7be73-102">方法: パスに沿ってオブジェクトをアニメーション化する (ダブル アニメーション)</span><span class="sxs-lookup"><span data-stu-id="7be73-102">How to: Animate an Object Along a Path (Double Animation)</span></span>
<span data-ttu-id="7be73-103">この例では、<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> クラスを使用して、<xref:System.Windows.Media.PathGeometry> で定義したパスに沿ってオブジェクトを移動する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7be73-103">This example shows how to use the <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> class to move an object along a path defined by a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7be73-104">例</span><span class="sxs-lookup"><span data-stu-id="7be73-104">Example</span></span>  
 <span data-ttu-id="7be73-105">次の例では、2 つの <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> オブジェクトを使用して、ジオメトリック パスに沿って四角形を移動します。</span><span class="sxs-lookup"><span data-stu-id="7be73-105">The following example uses two <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> objects to move a rectangle along a geometric path:</span></span>  
  
- <span data-ttu-id="7be73-106">最初の <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> は、四角形に適用されている <xref:System.Windows.Media.TranslateTransform> の <xref:System.Windows.Media.TranslateTransform.X%2A> をアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="7be73-106">The first <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animates the <xref:System.Windows.Media.TranslateTransform.X%2A> of the <xref:System.Windows.Media.TranslateTransform> applied to the rectangle.</span></span> <span data-ttu-id="7be73-107">これにより、四角形がパスに沿って水平に移動します。</span><span class="sxs-lookup"><span data-stu-id="7be73-107">It makes the rectangle move horizontally along the path.</span></span>  
  
- <span data-ttu-id="7be73-108">2番目の <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> は、四角形に適用されている <xref:System.Windows.Media.TranslateTransform> の <xref:System.Windows.Media.TranslateTransform.Y%2A> をアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="7be73-108">The second <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animates the <xref:System.Windows.Media.TranslateTransform.Y%2A> of the <xref:System.Windows.Media.TranslateTransform> applied to the rectangle.</span></span> <span data-ttu-id="7be73-109">これにより、四角形がパスに沿って垂直に移動します。</span><span class="sxs-lookup"><span data-stu-id="7be73-109">It makes the rectangle move vertically along the path.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#DoubleAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/doubleanimationusingpathexample.xaml#doubleanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/DoubleAnimationUsingPathExample.cs#doubleanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/DoubleAnimationUsingPathExample.vb#doubleanimationusingpathwholepage)]  
  
 <span data-ttu-id="7be73-110">サンプル全体については、「[パス アニメーションのサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7be73-110">For the complete sample, see [Path Animation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span></span>  
  
 <span data-ttu-id="7be73-111">ジオメトリック パスを使用してオブジェクトを移動するために、<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> オブジェクトを使用する方法もあります。</span><span class="sxs-lookup"><span data-stu-id="7be73-111">Another way to move an object using a geometric path is to use a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object.</span></span> <span data-ttu-id="7be73-112">例については、「[パスに沿ってオブジェクトをアニメーション化する (行列アニメーション)](how-to-animate-an-object-along-a-path-matrix-animation.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7be73-112">For an example, see [Animate an Object Along a Path (Matrix Animation)](how-to-animate-an-object-along-a-path-matrix-animation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7be73-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="7be73-113">See also</span></span>

- [<span data-ttu-id="7be73-114">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="7be73-114">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="7be73-115">パス アニメーションに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="7be73-115">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
