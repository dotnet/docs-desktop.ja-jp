---
title: '方法: 複合図形の塗りつぶしを制御する'
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], composite [WPF], controlling fill
- composite shapes [WPF], controlling fill
- graphics [WPF], composite shapes
- fill [WPF], controlling
ms.assetid: c1c94575-9eca-48a5-a49a-2ec65259f229
ms.openlocfilehash: 89f69d392e8838af99538c759a2f06453e1bcd60
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984771"
---
# <a name="how-to-control-the-fill-of-a-composite-shape"></a><span data-ttu-id="8e71c-102">方法: 複合図形の塗りつぶしを制御する</span><span class="sxs-lookup"><span data-stu-id="8e71c-102">How to: Control the Fill of a Composite Shape</span></span>

<span data-ttu-id="8e71c-103"><xref:System.Windows.Media.GeometryGroup> または <xref:System.Windows.Media.PathGeometry> の <xref:System.Windows.Media.GeometryGroup.FillRule%2A> プロパティでは、指定された点がジオメトリの一部であるかどうかを判断するために、複合図形で使用される "規則" を指定します。</span><span class="sxs-lookup"><span data-stu-id="8e71c-103">The <xref:System.Windows.Media.GeometryGroup.FillRule%2A> property of a <xref:System.Windows.Media.GeometryGroup> or a <xref:System.Windows.Media.PathGeometry>, specifies a "rule" which the composite shape uses to determine whether a given point is part of the geometry.</span></span> <span data-ttu-id="8e71c-104"><xref:System.Windows.Media.FillRule> には、<xref:System.Windows.Media.FillRule.EvenOdd> と <xref:System.Windows.Media.FillRule.Nonzero> という指定できる値が 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="8e71c-104">There are two possible values for <xref:System.Windows.Media.FillRule>: <xref:System.Windows.Media.FillRule.EvenOdd> and <xref:System.Windows.Media.FillRule.Nonzero>.</span></span> <span data-ttu-id="8e71c-105">以下のセクションでは、これら 2 つの規則の使用方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="8e71c-105">The following sections will describe how to use these two rules.</span></span>

<span data-ttu-id="8e71c-106">**EvenOdd:** この規則では、ある点から任意の方向に無限に伸びる射線を描画し、その射線が横断する指定された図形内のパス セグメントの数をカウントすることにより、その点が塗りつぶし領域にあるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="8e71c-106">**EvenOdd:** This rule determines whether a point is in the fill region by drawing a ray from that point to infinity in any direction and counting the number of path segments within the given shape that the ray crosses.</span></span> <span data-ttu-id="8e71c-107">この数値が偶数の場合は、ポイントは内側にあります。偶数の場合は、ポイントは外側にあります。</span><span class="sxs-lookup"><span data-stu-id="8e71c-107">If this number is odd, the point is inside; if even, the point is outside.</span></span>

<span data-ttu-id="8e71c-108">たとえば、以下の XAML では、<xref:System.Windows.Media.GeometryGroup.FillRule%2A> を <xref:System.Windows.Media.FillRule.EvenOdd> に設定し、一連の同心リングで構成される複合図形 (射撃の的) を作成します。</span><span class="sxs-lookup"><span data-stu-id="8e71c-108">For example, the XAML below creates a composite shape made up of a series of concentric rings (target) with a <xref:System.Windows.Media.GeometryGroup.FillRule%2A> set to <xref:System.Windows.Media.FillRule.EvenOdd>.</span></span>

[!code-xaml[GeometriesMiscSnippets_snip#FillRuleEvenOddValue](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/FillRuleExample.xaml#fillruleevenoddvalue)]

<span data-ttu-id="8e71c-109">前の例で作成した図を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8e71c-109">The following illustration shows the shape created in the previous example.</span></span>

![色が交互になっている一連の同心リングで構成された円。](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-evenodd-property.png)

<span data-ttu-id="8e71c-111">前の図では、中央と 3 番目のリングが塗りつぶされていないことに注目してください。</span><span class="sxs-lookup"><span data-stu-id="8e71c-111">In the previous illustration, notice that the center and third ring are not filled.</span></span> <span data-ttu-id="8e71c-112">これは、これら 2 つのリングの任意の点から描画された射線が、偶数個のセグメントを通過するためです。</span><span class="sxs-lookup"><span data-stu-id="8e71c-112">This is because a ray drawn from any point within either of those two rings passes through an even number of segments.</span></span> <span data-ttu-id="8e71c-113">次の図を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e71c-113">See the following illustration:</span></span>

![円に描画された EvenOdd 斜線を示す図。](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-evenodd-rays.png)

<span data-ttu-id="8e71c-115">**NonZero:** この規則では、ある点から任意の方向に無限に伸びる射線を描画してから、図形のセグメントがこの射線と交わる場所を調べることにより、その点がパスの塗りつぶし領域の内側にあるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="8e71c-115">**NonZero:** This rule determines whether a point is in the fill region of the path by drawing a ray from that point to infinity in any direction and then examining the places where a segment of the shape crosses the ray.</span></span> <span data-ttu-id="8e71c-116">0 からカウントを開始し、パス セグメントが左から右に射線と交わるたびに 1 を加算し、パス セグメントが右から左に射線と交わるたびに 1 を減算します。</span><span class="sxs-lookup"><span data-stu-id="8e71c-116">Starting with a count of zero, add one each time a Segment crosses the ray from left to right and subtract one each time a path segment crosses the ray from right to left.</span></span> <span data-ttu-id="8e71c-117">交差のカウント後、結果が 0 の場合は、ポイントは、パスの外側にあります。</span><span class="sxs-lookup"><span data-stu-id="8e71c-117">After counting the crossings, if the result is zero then the point is outside the path.</span></span> <span data-ttu-id="8e71c-118">それ以外の場合は、内側にあります。</span><span class="sxs-lookup"><span data-stu-id="8e71c-118">Otherwise, it is inside.</span></span>

[!code-xaml[GeometriesMiscSnippets_snip#FillRuleNonZeroValueEllipseGeometry](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/FillRuleExample.xaml#fillrulenonzerovalueellipsegeometry)]

<span data-ttu-id="8e71c-119">前の例を使用し、<xref:System.Windows.Media.GeometryGroup.FillRule%2A> に <xref:System.Windows.Media.FillRule.Nonzero> の値を指定すると、結果として次の図のようになります。</span><span class="sxs-lookup"><span data-stu-id="8e71c-119">Using the previous example, a value of <xref:System.Windows.Media.FillRule.Nonzero> for <xref:System.Windows.Media.GeometryGroup.FillRule%2A> gives the following illustration as a result:</span></span>

![すべて同じ色で塗りつぶされた一連の同心リングで構成された円。](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-value-nonzero.png)

<span data-ttu-id="8e71c-121">上の図からわかるように、すべてのリングが塗りつぶされます。</span><span class="sxs-lookup"><span data-stu-id="8e71c-121">As you can see, all the rings are filled.</span></span> <span data-ttu-id="8e71c-122">これは、すべてのセグメントが同じ方向で、任意の点から描画された射線は 1 つ以上のセグメントと交わり、交差の合計が 0 にならないためです。</span><span class="sxs-lookup"><span data-stu-id="8e71c-122">This is because all the segments are running in the same direction and so a ray drawn from any point will cross one or more segments and the sum of the crossings will not equal zero.</span></span> <span data-ttu-id="8e71c-123">たとえば、次の図では、赤い矢印はセグメントが描画されている方向を表し、白い矢印は最も内側のリング内にある点から伸びる任意の射線を表しています。</span><span class="sxs-lookup"><span data-stu-id="8e71c-123">For example, in the following illustration, the red arrows represent the direction the segments are drawn and the white arrow represents an arbitrary ray running from a point in the innermost ring.</span></span> <span data-ttu-id="8e71c-124">値 0 から開始し、セグメントは左から右に射線と交わるため、射線が交わるセグメントごとに値 1 が加算されます。</span><span class="sxs-lookup"><span data-stu-id="8e71c-124">Starting with a value of zero, for each segment that the ray crosses, a value of one is added because the segment crosses the ray from left to right.</span></span>

![Nonzero と等しい FillRule プロパティ値を示す図。](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-value-equal-nonzero.png)

<span data-ttu-id="8e71c-126"><xref:System.Windows.Media.FillRule.Nonzero> 規則の動作をよりわかりやすく説明するには、方向の異なる複数のセグメントから構成される、より複雑な図形が必要になります。</span><span class="sxs-lookup"><span data-stu-id="8e71c-126">To better demonstrate the behavior of <xref:System.Windows.Media.FillRule.Nonzero> rule a more complex shape with segments running in different directions is required.</span></span> <span data-ttu-id="8e71c-127">以下の XAML コードでは、前の例と似た図形を作成しますが、<xref:System.Windows.Media.EllipseGeometry> ではなく、<xref:System.Windows.Media.PathGeometry> を使用して、完全に閉じた同心円ではなく、4 つの同心の円弧を作成しています。</span><span class="sxs-lookup"><span data-stu-id="8e71c-127">The XAML code below creates a similar shape as the previous example except that it is created with a <xref:System.Windows.Media.PathGeometry> rather then a <xref:System.Windows.Media.EllipseGeometry> which creates four concentric arcs rather then fully closed concentric circles.</span></span>

[!code-xaml[GeometriesMiscSnippets_snip#FillRuleNonZeroValuePathGeometry](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/FillRuleExample.xaml#fillrulenonzerovaluepathgeometry)]

<span data-ttu-id="8e71c-128">前の例で作成した図を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8e71c-128">The following illustration shows the shape created in the previous example.</span></span>

![3 番目の円弧が塗りつぶされておらず、色が交互になっている一連の同心リングで構成された円。](./media/how-to-control-the-fill-of-a-composite-shape/pathgeometry-concentric-arcs.png)

<span data-ttu-id="8e71c-130">中央から 3 番目の円弧が塗りつぶされていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8e71c-130">Notice that the third arc from the center is not filled.</span></span> <span data-ttu-id="8e71c-131">次の図には、この理由が示されています。</span><span class="sxs-lookup"><span data-stu-id="8e71c-131">The following illustration shows why this is.</span></span> <span data-ttu-id="8e71c-132">この図で、赤い矢印はセグメントが描画されている方向を表しています。</span><span class="sxs-lookup"><span data-stu-id="8e71c-132">In the illustration, the red arrows represent the direction the segments are drawn.</span></span> <span data-ttu-id="8e71c-133">2 つの白い矢印は、"塗りつぶされていない" 領域内の点から外に向かって伸びる、2 本の任意の射線を表しています。</span><span class="sxs-lookup"><span data-stu-id="8e71c-133">The two white arrows represent two arbitrary rays that move out from a point in the "non-filled" region.</span></span> <span data-ttu-id="8e71c-134">この図からわかるように、指定された射線がパス内でセグメントと交わることによる値の合計は 0 です。</span><span class="sxs-lookup"><span data-stu-id="8e71c-134">As can be seen from the illustration, the sum of the values from a given ray crossing the segments in its path is zero.</span></span> <span data-ttu-id="8e71c-135">前に定義したように、合計が 0 となるのは、その点がジオメトリの一部でない (塗りつぶしに含まれない) ことを意味し、合計が 0 で *ない* 場合 (負の値を含む) は、その点がジオメトリの一部であることを意味しています。</span><span class="sxs-lookup"><span data-stu-id="8e71c-135">As defined above, a sum of zero means that the point is not part of the geometry (not part of the fill) while a sum that is *not* zero, including a negative value, is part of the geometry.</span></span>

![セグメントを横断する任意の斜線を示す図。](./media/how-to-control-the-fill-of-a-composite-shape/arbitrary-ray-cross-segment.png)

> [!NOTE]
> <span data-ttu-id="8e71c-137"><xref:System.Windows.Media.FillRule> の目的上、すべての図形は閉じていると見なされます。</span><span class="sxs-lookup"><span data-stu-id="8e71c-137">For the purposes of <xref:System.Windows.Media.FillRule>, all shapes are considered closed.</span></span> <span data-ttu-id="8e71c-138">セグメントにすき間がある場合は、架空の線を描画して、そのすき間を閉じます。</span><span class="sxs-lookup"><span data-stu-id="8e71c-138">If there is a gap in a segment, draw an imaginary line to close it.</span></span> <span data-ttu-id="8e71c-139">上の例では、リングに小さなすき間があります。</span><span class="sxs-lookup"><span data-stu-id="8e71c-139">In the example above, there are small gaps in the rings.</span></span> <span data-ttu-id="8e71c-140">この場合、このすき間を通る射線は、別の方向に伸びる射線とは異なる結果を生じると思えるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="8e71c-140">Given this, one might expect a ray that runs through the gap to give a different result then a ray running in another direction.</span></span> <span data-ttu-id="8e71c-141">これらのすき間の 1 つと、それを閉じる "架空のセグメント" (<xref:System.Windows.Media.FillRule> を適用するために描画されるセグメント) を拡大した図を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="8e71c-141">Below is an enlarged illustration of one of these gaps and the "imaginary segment" (segment that is drawn for purposes of applying the <xref:System.Windows.Media.FillRule>) that closes it.</span></span>

![常に閉じられている FillRule セグメントを示す図。](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-closed-segments.png)

## <a name="example"></a><span data-ttu-id="8e71c-143">例</span><span class="sxs-lookup"><span data-stu-id="8e71c-143">Example</span></span>

## <a name="see-also"></a><span data-ttu-id="8e71c-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="8e71c-144">See also</span></span>

- [<span data-ttu-id="8e71c-145">複合図形を作成する</span><span class="sxs-lookup"><span data-stu-id="8e71c-145">Create a Composite Shape</span></span>](how-to-create-a-composite-shape.md)
- [<span data-ttu-id="8e71c-146">ジオメトリの概要</span><span class="sxs-lookup"><span data-stu-id="8e71c-146">Geometry Overview</span></span>](geometry-overview.md)
