---
title: '方法: 背景として使用するイメージの縦横比を保持する'
ms.date: 03/30/2017
helpviewer_keywords:
- aspect ratios of background images [WPF], preserving
- brushes [WPF], preserving aspect ratios of background images
- background images [WPF], preserving aspect ratios
ms.assetid: 28c39478-13d7-4011-80a3-8b9cc3e54478
ms.openlocfilehash: b467fcd353994faef19b5a997e03d6582789eac1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96979909"
---
# <a name="how-to-preserve-the-aspect-ratio-of-an-image-used-as-a-background"></a><span data-ttu-id="577b1-102">方法: 背景として使用するイメージの縦横比を保持する</span><span class="sxs-lookup"><span data-stu-id="577b1-102">How to: Preserve the Aspect Ratio of an Image Used as a Background</span></span>
<span data-ttu-id="577b1-103">この例では、イメージの縦横比を保持するために <xref:System.Windows.Media.ImageBrush> の <xref:System.Windows.Media.TileBrush.Stretch%2A> プロパティを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="577b1-103">This example shows how to use the <xref:System.Windows.Media.TileBrush.Stretch%2A> property of an <xref:System.Windows.Media.ImageBrush> in order to preserve the aspect ratio of the image.</span></span>  
  
 <span data-ttu-id="577b1-104">既定では、<xref:System.Windows.Media.ImageBrush> を使用して領域を塗りつぶすと、出力領域が完全に塗りつぶされるようにコンテンツが引き伸ばされます。</span><span class="sxs-lookup"><span data-stu-id="577b1-104">By default, when you use an <xref:System.Windows.Media.ImageBrush> to paint an area, its content stretches to completely fill the output area.</span></span> <span data-ttu-id="577b1-105">出力領域とイメージの縦横比が異なる場合は、この引き伸ばしによってイメージがゆがめられます。</span><span class="sxs-lookup"><span data-stu-id="577b1-105">When the output area and the image have different aspect ratios, the image is distorted by this stretching.</span></span>  
  
 <span data-ttu-id="577b1-106"><xref:System.Windows.Media.ImageBrush> がそのイメージの縦横比を保持するようにするには、<xref:System.Windows.Media.TileBrush.Stretch%2A> プロパティを <xref:System.Windows.Media.Stretch.Uniform> または <xref:System.Windows.Media.Stretch.UniformToFill> に設定します。</span><span class="sxs-lookup"><span data-stu-id="577b1-106">To make an <xref:System.Windows.Media.ImageBrush> preserve the aspect ratio of its image, set the <xref:System.Windows.Media.TileBrush.Stretch%2A> property to <xref:System.Windows.Media.Stretch.Uniform> or <xref:System.Windows.Media.Stretch.UniformToFill>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="577b1-107">例</span><span class="sxs-lookup"><span data-stu-id="577b1-107">Example</span></span>  
 <span data-ttu-id="577b1-108">次の例では、2 つの <xref:System.Windows.Media.ImageBrush> オブジェクトを使用して、2 つの四角形を塗りつぶしています。</span><span class="sxs-lookup"><span data-stu-id="577b1-108">The following example uses two <xref:System.Windows.Media.ImageBrush> objects to paint two rectangles.</span></span> <span data-ttu-id="577b1-109">これらの四角形は 300 × 150 ピクセルで、どちらも 300 × 300 ピクセルのイメージを保持しています。</span><span class="sxs-lookup"><span data-stu-id="577b1-109">Each rectangle is 300 by 150 pixels and each contains a 300 by 300 pixel image.</span></span> <span data-ttu-id="577b1-110">最初のブラシの <xref:System.Windows.Media.TileBrush.Stretch%2A> プロパティは <xref:System.Windows.Media.Stretch.Uniform> に設定され、2 番目のブラシの <xref:System.Windows.Media.TileBrush.Stretch%2A> プロパティは <xref:System.Windows.Media.Stretch.UniformToFill> に設定されています。</span><span class="sxs-lookup"><span data-stu-id="577b1-110">The <xref:System.Windows.Media.TileBrush.Stretch%2A> property of the first brush is set to <xref:System.Windows.Media.Stretch.Uniform>, and the <xref:System.Windows.Media.TileBrush.Stretch%2A> property of the second brush is set to <xref:System.Windows.Media.Stretch.UniformToFill>.</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushStretchModesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/StretchModes.cs#imagebrushstretchmodesexamplewholepage)]  
  
 <span data-ttu-id="577b1-111"><xref:System.Windows.Media.TileBrush.Stretch%2A> を <xref:System.Windows.Media.Stretch.Uniform> に設定した最初のブラシの出力を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="577b1-111">The following illustration shows the output of the first brush, which has a <xref:System.Windows.Media.TileBrush.Stretch%2A> setting of <xref:System.Windows.Media.Stretch.Uniform>.</span></span>  
  
 <span data-ttu-id="577b1-112">![Uniform 拡大を使用した ImageBrush](./media/graphicsmm-imagebrushuniformstretch.jpg "graphicsmm_ImageBrushUniformStretch")</span><span class="sxs-lookup"><span data-stu-id="577b1-112">![ImageBrush with Uniform stretching](./media/graphicsmm-imagebrushuniformstretch.jpg "graphicsmm_ImageBrushUniformStretch")</span></span>  
  
 <span data-ttu-id="577b1-113"><xref:System.Windows.Media.TileBrush.Stretch%2A> を <xref:System.Windows.Media.Stretch.UniformToFill> に設定した 2 番目のブラシの出力を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="577b1-113">The next illustration shows the output of the second brush, which has a <xref:System.Windows.Media.TileBrush.Stretch%2A> setting of <xref:System.Windows.Media.Stretch.UniformToFill>.</span></span>  
  
 <span data-ttu-id="577b1-114">![UniformToFill 拡大を使用した ImageBrush](./media/graphicsmm-imagebrushuniformtofillstretch.jpg "graphicsmm_ImageBrushUniformToFillStretch")</span><span class="sxs-lookup"><span data-stu-id="577b1-114">![ImageBrush with UniformToFill stretching](./media/graphicsmm-imagebrushuniformtofillstretch.jpg "graphicsmm_ImageBrushUniformToFillStretch")</span></span>  
  
 <span data-ttu-id="577b1-115"><xref:System.Windows.Media.TileBrush.Stretch%2A> プロパティは、他の <xref:System.Windows.Media.TileBrush> オブジェクト、つまり <xref:System.Windows.Media.DrawingBrush> と <xref:System.Windows.Media.VisualBrush> に対してもまったく同じように動作することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="577b1-115">Note that the <xref:System.Windows.Media.TileBrush.Stretch%2A> property behaves identically for the other <xref:System.Windows.Media.TileBrush> objects, that is, for <xref:System.Windows.Media.DrawingBrush> and <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="577b1-116"><xref:System.Windows.Media.ImageBrush> と他の <xref:System.Windows.Media.TileBrush> オブジェクトの詳細については、「[イメージ、描画、およびビジュアルによる塗りつぶし](painting-with-images-drawings-and-visuals.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="577b1-116">For more information about <xref:System.Windows.Media.ImageBrush> and the other <xref:System.Windows.Media.TileBrush> objects, see [Painting with Images, Drawings, and Visuals](painting-with-images-drawings-and-visuals.md).</span></span>  
  
 <span data-ttu-id="577b1-117">また、<xref:System.Windows.Media.TileBrush.Stretch%2A> プロパティは、<xref:System.Windows.Media.TileBrush> コンテンツを出力領域に合わせて引き伸ばす方法を指定するように見えますが、実際には基本タイルを塗りつぶすように <xref:System.Windows.Media.TileBrush> コンテンツを引き伸ばす方法を指定することにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="577b1-117">Note also that, although the <xref:System.Windows.Media.TileBrush.Stretch%2A> property appears to specify how the <xref:System.Windows.Media.TileBrush> content stretches to fit its output area, it actually specifies how the <xref:System.Windows.Media.TileBrush> content stretches to fill its base tile.</span></span> <span data-ttu-id="577b1-118">詳細については、「<xref:System.Windows.Media.TileBrush>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="577b1-118">For more information, see <xref:System.Windows.Media.TileBrush>.</span></span>  
  
 <span data-ttu-id="577b1-119">このコード例は、<xref:System.Windows.Media.ImageBrush> クラスで提供されている、より大きな例の一部です。</span><span class="sxs-lookup"><span data-stu-id="577b1-119">This code example is part of a larger example that is provided for the <xref:System.Windows.Media.ImageBrush> class.</span></span> <span data-ttu-id="577b1-120">完全なサンプルについては、「[ImageBrush のサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="577b1-120">For the complete sample, see [ImageBrush Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="577b1-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="577b1-121">See also</span></span>

- <xref:System.Windows.Media.TileBrush>
- [<span data-ttu-id="577b1-122">イメージ、描画、およびビジュアルによる塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="577b1-122">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
