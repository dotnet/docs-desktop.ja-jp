---
title: '方法: ブラシを変換する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], rotating contents
- brushes [WPF], Transform property
- rotating contents of brushes [WPF]
ms.assetid: ebada2f9-f01f-4863-9ea2-c2e4e51610f1
ms.openlocfilehash: b4484e2fc1ae3e969b02b1d8f3ae4ab2a035558e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983243"
---
# <a name="how-to-transform-a-brush"></a><span data-ttu-id="7f245-102">方法: ブラシを変換する</span><span class="sxs-lookup"><span data-stu-id="7f245-102">How to: Transform a Brush</span></span>
<span data-ttu-id="7f245-103">この例では、2 つの変換プロパティの <xref:System.Windows.Media.Brush.RelativeTransform%2A> と <xref:System.Windows.Media.Brush.Transform%2A> を使用して、<xref:System.Windows.Media.Brush> オブジェクトを変換する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7f245-103">This example shows how to transform <xref:System.Windows.Media.Brush> objects by using their two transformation properties: <xref:System.Windows.Media.Brush.RelativeTransform%2A> and <xref:System.Windows.Media.Brush.Transform%2A>.</span></span>  
  
 <span data-ttu-id="7f245-104">次の例では、<xref:System.Windows.Media.RotateTransform> を使用して、<xref:System.Windows.Media.ImageBrush> のコンテンツを 45 度回転させます。</span><span class="sxs-lookup"><span data-stu-id="7f245-104">The following examples use a <xref:System.Windows.Media.RotateTransform> to rotate the content of an <xref:System.Windows.Media.ImageBrush> by 45 degrees.</span></span>  
  
 <span data-ttu-id="7f245-105">次の図は、<xref:System.Windows.Media.ImageBrush> について、<xref:System.Windows.Media.RotateTransform> が適用されていないもの、<xref:System.Windows.Media.RotateTransform> が <xref:System.Windows.Media.Brush.RelativeTransform%2A> プロパティに適用されているもの、<xref:System.Windows.Media.RotateTransform> が <xref:System.Windows.Media.Brush.Transform%2A> プロパティに適用されているものをそれぞれ示しています。</span><span class="sxs-lookup"><span data-stu-id="7f245-105">The following illustration shows the <xref:System.Windows.Media.ImageBrush> without a <xref:System.Windows.Media.RotateTransform>, with the <xref:System.Windows.Media.RotateTransform> applied to the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property, and with the <xref:System.Windows.Media.RotateTransform> applied to the <xref:System.Windows.Media.Brush.Transform%2A> property.</span></span>  
  
 <span data-ttu-id="7f245-106">![ブラシの RelativeTransform と Transform の設定](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")</span><span class="sxs-lookup"><span data-stu-id="7f245-106">![Brush RelativeTransform and Transform settings](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f245-107">例</span><span class="sxs-lookup"><span data-stu-id="7f245-107">Example</span></span>  
 <span data-ttu-id="7f245-108">最初の例では、<xref:System.Windows.Media.ImageBrush> の <xref:System.Windows.Media.Brush.RelativeTransform%2A> プロパティに <xref:System.Windows.Media.RotateTransform> を適用します。</span><span class="sxs-lookup"><span data-stu-id="7f245-108">The first example applies a <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property of an <xref:System.Windows.Media.ImageBrush>.</span></span> <span data-ttu-id="7f245-109"><xref:System.Windows.Media.RotateTransform> オブジェクトの <xref:System.Windows.Media.RotateTransform.CenterX%2A> プロパティおよび <xref:System.Windows.Media.RotateTransform.CenterY%2A> プロパティは両方とも 0.5 に設定されています。これは、このコンテンツの中心点の相対座標です。</span><span class="sxs-lookup"><span data-stu-id="7f245-109">The <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of a <xref:System.Windows.Media.RotateTransform> object are both set to 0.5, which is the relative coordinate of the center point of this content.</span></span> <span data-ttu-id="7f245-110">結果として、<xref:System.Windows.Media.ImageBrush> コンテンツはその中心を基点に回転します。</span><span class="sxs-lookup"><span data-stu-id="7f245-110">As a result, the <xref:System.Windows.Media.ImageBrush> content rotates about its center.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 <span data-ttu-id="7f245-111">2 番目の例でも <xref:System.Windows.Media.RotateTransform> を <xref:System.Windows.Media.ImageBrush> に適用していますが、この例では、<xref:System.Windows.Media.Brush.RelativeTransform%2A> プロパティの代わりに <xref:System.Windows.Media.Brush.Transform%2A> プロパティを使用しています。</span><span class="sxs-lookup"><span data-stu-id="7f245-111">The second example also applies a <xref:System.Windows.Media.RotateTransform> to an <xref:System.Windows.Media.ImageBrush>; however, this example uses the <xref:System.Windows.Media.Brush.Transform%2A> property instead of the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property.</span></span>  
  
 <span data-ttu-id="7f245-112">この例では、中心を基点にブラシを回転させるために、<xref:System.Windows.Media.RotateTransform> オブジェクトの <xref:System.Windows.Media.RotateTransform.CenterX%2A> プロパティおよび <xref:System.Windows.Media.RotateTransform.CenterY%2A> プロパティを絶対座標に設定しています。</span><span class="sxs-lookup"><span data-stu-id="7f245-112">To rotate the brush about its center, the example sets the <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of the <xref:System.Windows.Media.RotateTransform> object to absolute coordinates.</span></span> <span data-ttu-id="7f245-113">このブラシは、175 x 90 ピクセルの四角形を描画するため、四角形の中心点は (87.5, 45) になります。</span><span class="sxs-lookup"><span data-stu-id="7f245-113">Because the brush paints a rectangle that is 175 by 90 pixels, the center point of the rectangle is (87.5, 45).</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 <span data-ttu-id="7f245-114"><xref:System.Windows.Media.Brush.RelativeTransform%2A> プロパティおよび <xref:System.Windows.Media.Brush.Transform%2A> プロパティの動作については、「[ブラシの変換の概要](brush-transformation-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7f245-114">For a description of how the <xref:System.Windows.Media.Brush.RelativeTransform%2A> and <xref:System.Windows.Media.Brush.Transform%2A> properties work, see the [Brush Transformation Overview](brush-transformation-overview.md).</span></span>  
  
 <span data-ttu-id="7f245-115">完全なサンプルについては、「[ブラシのサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f245-115">For the complete sample, see [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span> <span data-ttu-id="7f245-116">ブラシの詳細については、「[純色およびグラデーションによる塗りつぶしの概要](painting-with-solid-colors-and-gradients-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f245-116">For more information about brushes, see [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f245-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="7f245-117">See also</span></span>

- [<span data-ttu-id="7f245-118">ブラシの変換の概要</span><span class="sxs-lookup"><span data-stu-id="7f245-118">Brush Transformation Overview</span></span>](brush-transformation-overview.md)
- [<span data-ttu-id="7f245-119">純色およびグラデーションによる塗りつぶしの概要</span><span class="sxs-lookup"><span data-stu-id="7f245-119">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="7f245-120">変換の概要</span><span class="sxs-lookup"><span data-stu-id="7f245-120">Transforms Overview</span></span>](transforms-overview.md)
