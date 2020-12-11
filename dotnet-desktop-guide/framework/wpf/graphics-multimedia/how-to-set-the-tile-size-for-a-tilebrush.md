---
title: '方法: TileBrush のタイル サイズを設定する'
ms.date: 03/30/2017
helpviewer_keywords:
- TileBrush [WPF], size of tile properties
- Viewport property of TileBrush [WPF]
ms.assetid: 04f41090-1b46-4e36-832f-d27d28708b8c
ms.openlocfilehash: af7bab59a292549b29dad9b6a7417f22b1b84e48
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980401"
---
# <a name="how-to-set-the-tile-size-for-a-tilebrush"></a><span data-ttu-id="07108-102">方法: TileBrush のタイル サイズを設定する</span><span class="sxs-lookup"><span data-stu-id="07108-102">How to: Set the Tile Size for a TileBrush</span></span>

<span data-ttu-id="07108-103">次の例は、<xref:System.Windows.Media.TileBrush> のタイル サイズを設定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="07108-103">This example shows how to set the tile size for a <xref:System.Windows.Media.TileBrush>.</span></span> <span data-ttu-id="07108-104">既定では、<xref:System.Windows.Media.TileBrush> は、描画する領域全体を塗りつぶす 1 つのタイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="07108-104">By default, a <xref:System.Windows.Media.TileBrush> produces a single tile that completely fills the area that you are painting.</span></span> <span data-ttu-id="07108-105"><xref:System.Windows.Media.TileBrush.Viewport%2A> プロパティと <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> プロパティを設定することで、この動作をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="07108-105">You can override this behavior by setting the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> properties.</span></span>

<span data-ttu-id="07108-106"><xref:System.Windows.Media.TileBrush.Viewport%2A> プロパティは、<xref:System.Windows.Media.TileBrush> のタイル サイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="07108-106">The <xref:System.Windows.Media.TileBrush.Viewport%2A> property specifies the tile size for a <xref:System.Windows.Media.TileBrush>.</span></span> <span data-ttu-id="07108-107">既定では、<xref:System.Windows.Media.TileBrush.Viewport%2A> プロパティの値は、描画される領域のサイズに対する相対的な値です。</span><span class="sxs-lookup"><span data-stu-id="07108-107">By default, the value of the <xref:System.Windows.Media.TileBrush.Viewport%2A> property is relative to the size of the area being painted.</span></span> <span data-ttu-id="07108-108"><xref:System.Windows.Media.TileBrush.Viewport%2A> プロパティで絶対タイル サイズを指定するには、<xref:System.Windows.Media.TileBrush.ViewportUnits%2A> プロパティを <xref:System.Windows.Media.BrushMappingMode.Absolute> に設定します。</span><span class="sxs-lookup"><span data-stu-id="07108-108">To make the <xref:System.Windows.Media.TileBrush.Viewport%2A> property specify an absolute tile size, set the <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> property to <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span></span>

## <a name="example"></a><span data-ttu-id="07108-109">例</span><span class="sxs-lookup"><span data-stu-id="07108-109">Example</span></span>

<span data-ttu-id="07108-110">次の例では、<xref:System.Windows.Media.TileBrush> の一種である <xref:System.Windows.Media.ImageBrush> を使用して、タイルで四角形を塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="07108-110">The following example uses an <xref:System.Windows.Media.ImageBrush>, a type of <xref:System.Windows.Media.TileBrush>, to paint a rectangle with tiles.</span></span> <span data-ttu-id="07108-111">例では、各タイルを出力領域 (四角形) の 50% x 50% に設定します。</span><span class="sxs-lookup"><span data-stu-id="07108-111">The example sets each tile to 50 percent by 50 percent of the output area (the rectangle).</span></span> <span data-ttu-id="07108-112">その結果、四角形は、イメージの 4 つの投影で塗りつぶされます。</span><span class="sxs-lookup"><span data-stu-id="07108-112">As a result, the rectangle is painted with four projections of the image.</span></span>

<span data-ttu-id="07108-113">次の図は、この例で生成される出力を示しています。</span><span class="sxs-lookup"><span data-stu-id="07108-113">The following illustration shows the output that the example produces:</span></span>

![イメージ ブラシを使用したタイルの例を示す 4 つのサクランボを含む四角形。](./media/how-to-set-the-tile-size-for-a-tilebrush/rectangle-tile-image-brush.png)

[!code-csharp[UsingImageBrush_snip#RelativeTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#relativetilesizeexample)]

<span data-ttu-id="07108-115">次の例では、<xref:System.Windows.Media.ImageBrush> を作成し、その <xref:System.Windows.Media.TileBrush.Viewport%2A> を `0,0,25,25`、<xref:System.Windows.Media.TileBrush.ViewportUnits%2A> を <xref:System.Windows.Media.BrushMappingMode.Absolute> に設定して、それを使用して別の四角形を塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="07108-115">The next example creates an <xref:System.Windows.Media.ImageBrush>, sets its <xref:System.Windows.Media.TileBrush.Viewport%2A> to `0,0,25,25` and its <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> to <xref:System.Windows.Media.BrushMappingMode.Absolute>, and uses it to paint another rectangle.</span></span> <span data-ttu-id="07108-116">その結果、ブラシは、幅が 25 ピクセル、高さが 25 ピクセルのタイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="07108-116">As a result, the brush produces tiles that have a width of 25  pixels and a height of 25 pixels .</span></span>

<span data-ttu-id="07108-117">次の図は、この例で生成される出力を示しています。</span><span class="sxs-lookup"><span data-stu-id="07108-117">The following illustration shows the output that the example produces:</span></span>

![ビューポートを使用してタイル化された TileBrush を示す 48 個のサクランボを含む四角形。](./media/how-to-set-the-tile-size-for-a-tilebrush/25-x-25-viewport-tilebrush.png)

[!code-csharp[UsingImageBrush_snip#AbsoluteTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#absolutetilesizeexample)]

<span data-ttu-id="07108-119">上記の例は、大規模なサンプルの一部です。</span><span class="sxs-lookup"><span data-stu-id="07108-119">The preceding examples are part of a larger sample.</span></span> <span data-ttu-id="07108-120">サンプル全体については、「[ImageBrush のサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="07108-120">For the complete sample, see [ImageBrush Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush).</span></span>

<span data-ttu-id="07108-121">この例では <xref:System.Windows.Media.ImageBrush> クラスを使用していますが、<xref:System.Windows.Media.TileBrush.Viewport%2A> プロパティと <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> プロパティは、他の <xref:System.Windows.Media.TileBrush> オブジェクト (つまり、<xref:System.Windows.Media.DrawingBrush> と <xref:System.Windows.Media.VisualBrush>) でも同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="07108-121">Although this example uses the <xref:System.Windows.Media.ImageBrush> class, the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> properties behave identically for the other <xref:System.Windows.Media.TileBrush> objects, that is, for <xref:System.Windows.Media.DrawingBrush> and <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="07108-122"><xref:System.Windows.Media.ImageBrush> および他の <xref:System.Windows.Media.TileBrush> オブジェクトの詳細については、「[イメージ、描画、およびビジュアルによる塗りつぶし](painting-with-images-drawings-and-visuals.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="07108-122">For more information about <xref:System.Windows.Media.ImageBrush> and the other <xref:System.Windows.Media.TileBrush> objects, see [Painting with Images, Drawings, and Visuals](painting-with-images-drawings-and-visuals.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="07108-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="07108-123">See also</span></span>

- <xref:System.Windows.Media.TileBrush>
- [<span data-ttu-id="07108-124">イメージ、描画、およびビジュアルによる塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="07108-124">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
- [<span data-ttu-id="07108-125">TileBrush を使用してさまざまなタイル パターンを作成する</span><span class="sxs-lookup"><span data-stu-id="07108-125">Create Different Tile Patterns with a TileBrush</span></span>](how-to-create-different-tile-patterns-with-a-tilebrush.md)
