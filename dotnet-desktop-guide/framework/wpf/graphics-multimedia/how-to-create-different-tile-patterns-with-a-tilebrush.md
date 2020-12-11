---
title: '方法: TileBrush を使用してさまざまなタイル パターンを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TileBrush [WPF], creating tile patterns
- tile patterns [WPF], creating
- creating [WPF], tile patterns with TileBrush
ms.assetid: 5aa46632-3527-4668-9d8d-0375c8af28aa
ms.openlocfilehash: c1051b234961eee9ae740af2abac3d64c523656c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983384"
---
# <a name="how-to-create-different-tile-patterns-with-a-tilebrush"></a><span data-ttu-id="1e8a2-102">方法: TileBrush を使用してさまざまなタイル パターンを作成する</span><span class="sxs-lookup"><span data-stu-id="1e8a2-102">How to: Create Different Tile Patterns with a TileBrush</span></span>
<span data-ttu-id="1e8a2-103">この例からは、<xref:System.Windows.Media.TileBrush> の <xref:System.Windows.Media.TileBrush.TileMode%2A> プロパティを利用してパターンを作成する方法がわかります。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-103">This example shows how to use the <xref:System.Windows.Media.TileBrush.TileMode%2A> property of a <xref:System.Windows.Media.TileBrush> to create a pattern.</span></span>  
  
 <span data-ttu-id="1e8a2-104"><xref:System.Windows.Media.TileBrush.TileMode%2A> プロパティでは、<xref:System.Windows.Media.TileBrush> のコンテンツを繰り返す方法を、つまり、出力領域を塗りつぶす目的で並べる方法を指定できます。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-104">The <xref:System.Windows.Media.TileBrush.TileMode%2A> property enables you to specify how the content of a <xref:System.Windows.Media.TileBrush> is repeated, that is, tiled to fill an output area.</span></span> <span data-ttu-id="1e8a2-105">パターンを作成するために、<xref:System.Windows.Media.TileBrush.TileMode%2A> を <xref:System.Windows.Media.TileMode.Tile>、<xref:System.Windows.Media.TileMode.FlipX>、<xref:System.Windows.Media.TileMode.FlipY>、<xref:System.Windows.Media.TileMode.FlipXY> に設定します。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-105">To create a pattern, you set the <xref:System.Windows.Media.TileBrush.TileMode%2A> to <xref:System.Windows.Media.TileMode.Tile>, <xref:System.Windows.Media.TileMode.FlipX>, <xref:System.Windows.Media.TileMode.FlipY>, or <xref:System.Windows.Media.TileMode.FlipXY>.</span></span> <span data-ttu-id="1e8a2-106">また、色を塗りつぶす領域より小さくなるよう、<xref:System.Windows.Media.TileBrush> の <xref:System.Windows.Media.TileBrush.Viewport%2A> を設定する必要があります。このように設定しないと、使用する <xref:System.Windows.Media.TileBrush.TileMode%2A> 設定に関係なく、タイルが 1 つだけ生成されます。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-106">You must also set the <xref:System.Windows.Media.TileBrush.Viewport%2A> of the <xref:System.Windows.Media.TileBrush> so that it is smaller than the area that you are painting; otherwise, only a single tile is produced, regardless which <xref:System.Windows.Media.TileBrush.TileMode%2A> setting you use.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e8a2-107">例</span><span class="sxs-lookup"><span data-stu-id="1e8a2-107">Example</span></span>  
 <span data-ttu-id="1e8a2-108">次の例では、<xref:System.Windows.Media.DrawingBrush> オブジェクトが 5 つ作成され、それぞれに異なる <xref:System.Windows.Media.TileBrush.TileMode%2A> 設定が与えられ、このオブジェクトを利用して 5 つの四角形が塗りつぶされます。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-108">The following example creates five <xref:System.Windows.Media.DrawingBrush> objects, gives them each a different <xref:System.Windows.Media.TileBrush.TileMode%2A> setting, and uses them to paint five rectangles.</span></span> <span data-ttu-id="1e8a2-109">この例では <xref:System.Windows.Media.DrawingBrush> クラスを使用することで <xref:System.Windows.Media.TileBrush.TileMode%2A> 動作が示されていますが、<xref:System.Windows.Media.TileBrush.TileMode%2A> プロパティは、すべての <xref:System.Windows.Media.TileBrush> オブジェクトに対して、つまり、<xref:System.Windows.Media.ImageBrush>、<xref:System.Windows.Media.VisualBrush>、<xref:System.Windows.Media.DrawingBrush> に対して同じように機能します。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-109">Although this example uses the <xref:System.Windows.Media.DrawingBrush> class to demonstrate <xref:System.Windows.Media.TileBrush.TileMode%2A> behavior, the <xref:System.Windows.Media.TileBrush.TileMode%2A> property works identically for all the <xref:System.Windows.Media.TileBrush> objects, that is, for <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.VisualBrush>, and <xref:System.Windows.Media.DrawingBrush>.</span></span>  
  
 <span data-ttu-id="1e8a2-110">次の図は、この例で生成される出力を示しています。</span><span class="sxs-lookup"><span data-stu-id="1e8a2-110">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="1e8a2-111">![TileBrush を並べて表示する例の出力結果](./media/graphicsmm-drawingbrushtilemodeexample.png "graphicsmm_DrawingBrushTileModeExample")</span><span class="sxs-lookup"><span data-stu-id="1e8a2-111">![TileBrush tiling example output](./media/graphicsmm-drawingbrushtilemodeexample.png "graphicsmm_DrawingBrushTileModeExample")</span></span>  
<span data-ttu-id="1e8a2-112">TileMode プロパティで作成されたタイル パターン</span><span class="sxs-lookup"><span data-stu-id="1e8a2-112">Tile patterns created with the TileMode property</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/TileModeExample.cs#graphicsmmdrawingbrushtilemodeexample)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/tilemodeexample.vb#graphicsmmdrawingbrushtilemodeexample)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/TileModeExample.xaml#graphicsmmdrawingbrushtilemodeexample)]  
  
## <a name="see-also"></a><span data-ttu-id="1e8a2-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="1e8a2-113">See also</span></span>

- [<span data-ttu-id="1e8a2-114">TileBrush のタイル サイズを設定する</span><span class="sxs-lookup"><span data-stu-id="1e8a2-114">Set the Tile Size for a TileBrush</span></span>](how-to-set-the-tile-size-for-a-tilebrush.md)
- [<span data-ttu-id="1e8a2-115">イメージ、描画、およびビジュアルによる塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="1e8a2-115">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
