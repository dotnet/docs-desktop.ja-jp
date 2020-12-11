---
title: '方法: ジオメトリック パスを使用してオブジェクトを回転させる (行列アニメーション)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
- matrix animation [WPF]
ms.assetid: 877dc9aa-6bdc-4beb-8772-3efaec32c0f0
ms.openlocfilehash: 63dc873a2b840ea3f870a8c60c5691ab271c1c9f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974861"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation"></a><span data-ttu-id="bfb1a-102">方法: ジオメトリック パスを使用してオブジェクトを回転させる (行列アニメーション)</span><span class="sxs-lookup"><span data-stu-id="bfb1a-102">How to: Rotate an Object by Using a Geometric Path (Matrix Animation)</span></span>
<span data-ttu-id="bfb1a-103">この例では、<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> と <xref:System.Windows.Media.MatrixTransform> を使用して、<xref:System.Windows.Media.PathGeometry> オブジェクトで定義されたジオメトリック パスに沿ってオブジェクトを回転 (ピボット) する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bfb1a-103">This example shows how to use a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> and a <xref:System.Windows.Media.MatrixTransform> to rotate (pivot) an object along a geometric path defined by a <xref:System.Windows.Media.PathGeometry> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bfb1a-104">例</span><span class="sxs-lookup"><span data-stu-id="bfb1a-104">Example</span></span>  
 <span data-ttu-id="bfb1a-105">次の例では、<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> オブジェクトを使用して、<xref:System.Windows.Media.MatrixTransform> の <xref:System.Windows.Media.MatrixTransform.Matrix%2A> プロパティをアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="bfb1a-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="bfb1a-106"><xref:System.Windows.Media.MatrixTransform> がボタンに適用され、曲線パスに沿って移動するようにします。</span><span class="sxs-lookup"><span data-stu-id="bfb1a-106">The <xref:System.Windows.Media.MatrixTransform> is applied to a button and causes it to move along a curved path.</span></span> <span data-ttu-id="bfb1a-107"><xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> プロパティは `true` に設定されているため、四角形がパスの接線に沿って回転します。</span><span class="sxs-lookup"><span data-stu-id="bfb1a-107">Because the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> property is set to `true`, the rectangle rotates along the tangent of the path.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathdoesrotatewithtangentexample.xaml#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathDoesRotateWithTangentExample.cs#matrixanimationusingpathdoesrotatewithtangentwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathDoesRotateWithTangentExample.vb#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 <span data-ttu-id="bfb1a-108">サンプル全体については、「[パス アニメーションのサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfb1a-108">For the complete sample, see [Path Animation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span></span>  
  
 <span data-ttu-id="bfb1a-109">前のサンプルのコード バージョンでは、1 つのアニメーションしか適用されていない場合でも、<xref:System.Windows.Media.Animation.Storyboard> を使用して <xref:System.Windows.Media.EllipseGeometry> をアニメーション化しました。</span><span class="sxs-lookup"><span data-stu-id="bfb1a-109">The code version of the preceding sample used a <xref:System.Windows.Media.Animation.Storyboard> to animate the <xref:System.Windows.Media.EllipseGeometry>, even though only one animation was applied.</span></span> <span data-ttu-id="bfb1a-110">もっと簡単にコード内で 1 つのアニメーションをプロパティに適用する方法は、<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> メソッドを使用することです。</span><span class="sxs-lookup"><span data-stu-id="bfb1a-110">An easier way to apply a single animation to a property in code is to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method.</span></span> <span data-ttu-id="bfb1a-111">例については、「[ストーリーボードを使用せずにプロパティをアニメーション化する](how-to-animate-a-property-without-using-a-storyboard.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfb1a-111">For an example, see [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfb1a-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="bfb1a-112">See also</span></span>

- [<span data-ttu-id="bfb1a-113">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="bfb1a-113">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="bfb1a-114">パス アニメーションに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="bfb1a-114">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
- [<span data-ttu-id="bfb1a-115">パス アニメーションのサンプル</span><span class="sxs-lookup"><span data-stu-id="bfb1a-115">Path Animation Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
