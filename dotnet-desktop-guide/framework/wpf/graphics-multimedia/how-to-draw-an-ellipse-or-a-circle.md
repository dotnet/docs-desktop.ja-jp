---
title: '方法: 楕円または円を描画する'
description: Windows Presentation Foundation (WPF) で輪郭の太さと内部の色を選択して楕円または円を描画する方法について説明します。
ms.date: 03/30/2017
helpviewer_keywords:
- ellipses [WPF], drawing
- circles [WPF], drawing
- drawing circles [WPF]
- drawing ellipses [WPF]
- graphics [WPF], drawing circles
- graphics [WPF], drawing ellipses
ms.assetid: 99763b8c-bfc8-44be-8231-8a70daf5481a
ms.openlocfilehash: afa0e7d2af42aaee39dca164f23b1a1cacf430ca
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984060"
---
# <a name="how-to-draw-an-ellipse-or-a-circle"></a><span data-ttu-id="6fbeb-103">方法: 楕円または円を描画する</span><span class="sxs-lookup"><span data-stu-id="6fbeb-103">How to: Draw an Ellipse or a Circle</span></span>
<span data-ttu-id="6fbeb-104">この例では、<xref:System.Windows.Shapes.Ellipse> 要素を使用して、楕円と円を描画する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6fbeb-104">This example shows how to draw ellipses and circles by using the <xref:System.Windows.Shapes.Ellipse> element.</span></span> <span data-ttu-id="6fbeb-105">楕円を描画するには、<xref:System.Windows.Shapes.Ellipse> 要素を作成し、その <xref:System.Windows.FrameworkElement.Width%2A> と <xref:System.Windows.FrameworkElement.Height%2A>を指定します。</span><span class="sxs-lookup"><span data-stu-id="6fbeb-105">To draw an ellipse, create an <xref:System.Windows.Shapes.Ellipse> element and specify its <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A>.</span></span> <span data-ttu-id="6fbeb-106"><xref:System.Windows.Shapes.Shape.Fill%2A> プロパティを使用して、楕円の内部を描画するために使用される <xref:System.Windows.Media.Brush> を指定します。</span><span class="sxs-lookup"><span data-stu-id="6fbeb-106">Use its <xref:System.Windows.Shapes.Shape.Fill%2A> property to specify the <xref:System.Windows.Media.Brush> that is used to paint the interior of the ellipse.</span></span> <span data-ttu-id="6fbeb-107"><xref:System.Windows.Shapes.Shape.Stroke%2A> プロパティを使用して、楕円の輪郭の描画に使用される <xref:System.Windows.Media.Brush> を指定します。</span><span class="sxs-lookup"><span data-stu-id="6fbeb-107">Use its <xref:System.Windows.Shapes.Shape.Stroke%2A> property to specify the <xref:System.Windows.Media.Brush> that is used to paint the outline of the ellipse.</span></span> <span data-ttu-id="6fbeb-108"><xref:System.Windows.Shapes.Shape.StrokeThickness%2A> プロパティは、楕円の輪郭の太さを指定します。</span><span class="sxs-lookup"><span data-stu-id="6fbeb-108">The <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> property specifies the thickness of the ellipse outline.</span></span>  
  
 <span data-ttu-id="6fbeb-109">円を描画するには、<xref:System.Windows.Shapes.Ellipse> 要素の <xref:System.Windows.FrameworkElement.Width%2A> と <xref:System.Windows.FrameworkElement.Height%2A> が等しくなるようにします。</span><span class="sxs-lookup"><span data-stu-id="6fbeb-109">To draw a circle, make the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> of the <xref:System.Windows.Shapes.Ellipse> element equal to each other.</span></span>  
  
 <span data-ttu-id="6fbeb-110">次の例では、<xref:System.Windows.Controls.Canvas> 内に 4 つの <xref:System.Windows.Shapes.Ellipse> 要素を描画しています。</span><span class="sxs-lookup"><span data-stu-id="6fbeb-110">The following example draws four <xref:System.Windows.Shapes.Ellipse> elements within a <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6fbeb-111">例</span><span class="sxs-lookup"><span data-stu-id="6fbeb-111">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#EllipseExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/ellipseexample.xaml#ellipseexample1)]  
  
 <span data-ttu-id="6fbeb-112">この例では、<xref:System.Windows.Controls.Canvas> を使用して楕円を格納していますが、テキスト以外のコンテンツをサポートする <xref:System.Windows.Controls.Panel> または <xref:System.Windows.Controls.Control> で楕円要素 (およびその他のすべての図形要素) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6fbeb-112">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the ellipses, you can use ellipse elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="6fbeb-113">この例は、より大きなサンプルの一部です。サンプル全体については、「[Shape 要素のサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fbeb-113">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fbeb-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="6fbeb-114">See also</span></span>

- <xref:System.Windows.Shapes.Ellipse>
- <xref:System.Windows.Shapes.Shape>
- [<span data-ttu-id="6fbeb-115">Shape 要素のサンプル</span><span class="sxs-lookup"><span data-stu-id="6fbeb-115">Shape Elements Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
