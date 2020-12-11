---
title: '方法: ビジュアルで領域を塗りつぶす'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- painting [WPF]
- visuals [WPF], painting with
- brushes [WPF], painting with visuals
ms.assetid: 35f92996-1d03-4542-acc4-3469dcf09492
ms.openlocfilehash: 793a14f0d395a60bf73ca7dc173b82237a139f35
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985228"
---
# <a name="how-to-paint-an-area-with-a-visual"></a><span data-ttu-id="76f95-102">方法: ビジュアルで領域を塗りつぶす</span><span class="sxs-lookup"><span data-stu-id="76f95-102">How to: Paint an Area with a Visual</span></span>
<span data-ttu-id="76f95-103">この例では、<xref:System.Windows.Media.VisualBrush> クラスを使用して <xref:System.Windows.Media.Visual> で領域を塗りつぶす方法を示します。</span><span class="sxs-lookup"><span data-stu-id="76f95-103">This example shows how to use the <xref:System.Windows.Media.VisualBrush> class to paint an area with a <xref:System.Windows.Media.Visual>.</span></span>  
  
 <span data-ttu-id="76f95-104">次の例では、いくつかのコントロールとパネルが四角形の背景として使用されています。</span><span class="sxs-lookup"><span data-stu-id="76f95-104">In the following example, several controls and a panel are used as the background of a rectangle.</span></span>  
  
## <a name="example"></a><span data-ttu-id="76f95-105">例</span><span class="sxs-lookup"><span data-stu-id="76f95-105">Example</span></span>  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/VisualBrushExample.xaml#graphicsmmvisualbrushasrectanglebackgroundexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/VisualBrushExample.cs#graphicsmmvisualbrushasrectanglebackgroundexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/visualbrushexample.vb#graphicsmmvisualbrushasrectanglebackgroundexample1)]  
  
 <span data-ttu-id="76f95-106"><xref:System.Windows.Media.VisualBrush> の詳細とその他の例については、「[イメージ、描画、およびビジュアルによる塗りつぶし](painting-with-images-drawings-and-visuals.md)」の概要を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76f95-106">For more information about <xref:System.Windows.Media.VisualBrush> and additional examples, see the [Painting with Images, Drawings, and Visuals](painting-with-images-drawings-and-visuals.md) overview.</span></span>  
  
 <span data-ttu-id="76f95-107">このコード例は、<xref:System.Windows.Media.VisualBrush> クラスのために提供されている大規模な例の一部です。</span><span class="sxs-lookup"><span data-stu-id="76f95-107">This code example is part of a larger example provided for the <xref:System.Windows.Media.VisualBrush> class.</span></span> <span data-ttu-id="76f95-108">完全なサンプルについては、[VisualBrush のサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/VisualBrush)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="76f95-108">For the complete sample, see the [VisualBrush Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/VisualBrush).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76f95-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="76f95-109">See also</span></span>

- [<span data-ttu-id="76f95-110">イメージ、描画、およびビジュアルによる塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="76f95-110">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
