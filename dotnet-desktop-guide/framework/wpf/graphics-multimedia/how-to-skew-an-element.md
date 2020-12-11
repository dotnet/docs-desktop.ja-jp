---
title: '方法: 要素を傾斜させる'
ms.date: 03/30/2017
helpviewer_keywords:
- skewing elements [WPF]
- graphics [WPF], skewing elements
- classes [WPF], SkewTransform
ms.assetid: 56b65f2f-dc6e-4238-923f-ca44ec53c52f
ms.openlocfilehash: 10b00044c1c518641281e2e72cdb5a68474b5170
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980389"
---
# <a name="how-to-skew-an-element"></a><span data-ttu-id="274b8-102">方法: 要素を傾斜させる</span><span class="sxs-lookup"><span data-stu-id="274b8-102">How to: Skew an Element</span></span>
<span data-ttu-id="274b8-103">この例では、<xref:System.Windows.Media.SkewTransform> を使用して要素を傾斜させる方法を示します。</span><span class="sxs-lookup"><span data-stu-id="274b8-103">This example shows how to use a <xref:System.Windows.Media.SkewTransform> to skew an element.</span></span> <span data-ttu-id="274b8-104">傾斜 (スキューと呼ばれることもあります) は、一様でない方法で座標空間を拡大する変換です。</span><span class="sxs-lookup"><span data-stu-id="274b8-104">A skew, which is also known as a shear, is a transformation that stretches the coordinate space in a non-uniform manner.</span></span> <span data-ttu-id="274b8-105"><xref:System.Windows.Media.SkewTransform> の一般的な用途の 1 つは、2D オブジェクトで 3D の奥行をシミュレートすることです。</span><span class="sxs-lookup"><span data-stu-id="274b8-105">One typical use of a <xref:System.Windows.Media.SkewTransform> is for simulating 3D depth in 2D objects.</span></span>  
  
 <span data-ttu-id="274b8-106"><xref:System.Windows.Media.SkewTransform> の中心点を指定するには、<xref:System.Windows.Media.SkewTransform.CenterX%2A> および <xref:System.Windows.Media.SkewTransform.CenterY%2A> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="274b8-106">Use the <xref:System.Windows.Media.SkewTransform.CenterX%2A> and <xref:System.Windows.Media.SkewTransform.CenterY%2A> properties to specify the center point of the <xref:System.Windows.Media.SkewTransform>.</span></span>  
  
 <span data-ttu-id="274b8-107">x 軸と y 軸の傾斜角度を指定し、これらの軸に沿って現在の座標系を傾斜させるには、<xref:System.Windows.Media.SkewTransform.AngleX%2A> および <xref:System.Windows.Media.SkewTransform.AngleY%2A> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="274b8-107">Use the <xref:System.Windows.Media.SkewTransform.AngleX%2A> and <xref:System.Windows.Media.SkewTransform.AngleY%2A> properties to specify the skew angle of the x-axis and y-axis, and to skew the current coordinate system along these axes.</span></span>  
  
 <span data-ttu-id="274b8-108">傾斜変換の効果を予測する際は、<xref:System.Windows.Media.SkewTransform.AngleX%2A> によって元の座標系に対して x 軸の値が傾斜することを考慮します。</span><span class="sxs-lookup"><span data-stu-id="274b8-108">To predict the effect of a skew transformation, consider that <xref:System.Windows.Media.SkewTransform.AngleX%2A> skews x-axis values relative to the original coordinate system.</span></span> <span data-ttu-id="274b8-109">したがって、<xref:System.Windows.Media.SkewTransform.AngleX%2A> が 30 の場合、y 軸が原点を中心に 30 度回転し、x の値がその原点から 30 度傾斜します。</span><span class="sxs-lookup"><span data-stu-id="274b8-109">Therefore, for an <xref:System.Windows.Media.SkewTransform.AngleX%2A> of 30, the y-axis rotates 30 degrees through the origin and skews the values in x- by 30 degrees from that origin.</span></span> <span data-ttu-id="274b8-110">同様に、<xref:System.Windows.Media.SkewTransform.AngleY%2A> が 30 の場合、図形の y 値が原点から 30 度傾斜します。</span><span class="sxs-lookup"><span data-stu-id="274b8-110">Likewise, an <xref:System.Windows.Media.SkewTransform.AngleY%2A> of 30 skews the y- values of the shape by 30 degrees from the origin.</span></span> <span data-ttu-id="274b8-111">これは、座標系の x または y での 30 度の平行移動 (移動) と同じ効果はないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="274b8-111">Note that this is not the same effect as translating (moving) the coordinate system by 30 degrees in x- or y-.</span></span>  
  
 <span data-ttu-id="274b8-112">次の例では、中心点 (0, 0) から水平方向に 45 度の傾斜を <xref:System.Windows.Shapes.Rectangle> に適用します。</span><span class="sxs-lookup"><span data-stu-id="274b8-112">The following example applies a horizontal skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (0,0).</span></span>  
  
## <a name="example"></a><span data-ttu-id="274b8-113">例</span><span class="sxs-lookup"><span data-stu-id="274b8-113">Example</span></span>  
 [!code-xaml[transformsSample#41](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#41)]  
  
 <span data-ttu-id="274b8-114">次の例では、中心点 (25,25) から水平方向に 45 度の傾斜を <xref:System.Windows.Shapes.Rectangle> に適用します。</span><span class="sxs-lookup"><span data-stu-id="274b8-114">The following example applies a horizontal skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (25,25).</span></span>  
  
 [!code-xaml[transformsSample#42](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#42)]  
  
 <span data-ttu-id="274b8-115">次の例では、中心点 (25,25) から垂直方向に 45 度の傾斜を <xref:System.Windows.Shapes.Rectangle> に適用します。</span><span class="sxs-lookup"><span data-stu-id="274b8-115">The following example applies a vertical skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (25,25).</span></span>  
  
 [!code-xaml[transformsSample#43](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#43)]  
  
 <span data-ttu-id="274b8-116">次の図は、この例で使用されている各種の傾斜を示しています。</span><span class="sxs-lookup"><span data-stu-id="274b8-116">The following illustration shows the different skews that are used in this example.</span></span>  
  
 <span data-ttu-id="274b8-117">![SkewTransform の例](./media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")</span><span class="sxs-lookup"><span data-stu-id="274b8-117">![SkewTransform examples](./media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")</span></span>  
<span data-ttu-id="274b8-118">説明した 3 つの SkewTransform の例</span><span class="sxs-lookup"><span data-stu-id="274b8-118">The three SkewTransform examples illustrated</span></span>  
  
 <span data-ttu-id="274b8-119">サンプル全体については、「[2D 変換のサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="274b8-119">For the complete sample, see [2D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="274b8-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="274b8-120">See also</span></span>

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.SkewTransform>
- [<span data-ttu-id="274b8-121">変換の概要</span><span class="sxs-lookup"><span data-stu-id="274b8-121">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="274b8-122">方法トピック</span><span class="sxs-lookup"><span data-stu-id="274b8-122">How-to Topics</span></span>](transformations-how-to-topics.md)
