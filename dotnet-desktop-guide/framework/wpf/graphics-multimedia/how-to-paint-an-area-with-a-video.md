---
title: '方法: ビデオを使用して領域を塗りつぶす'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- painting with a video [WPF]
- video [WPF], painting with
- brushes [WPF], painting with a video
ms.assetid: 04dd6600-4a6e-4b43-a93e-21cce7dfbcb8
ms.openlocfilehash: be09d1310847cd7214ea795a704c25d994f07b7a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985224"
---
# <a name="how-to-paint-an-area-with-a-video"></a><span data-ttu-id="4e5d3-102">方法: ビデオを使用して領域を塗りつぶす</span><span class="sxs-lookup"><span data-stu-id="4e5d3-102">How to: Paint an Area with a Video</span></span>
<span data-ttu-id="4e5d3-103">この例では、メディアを使用して領域を塗りつぶす方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4e5d3-103">This example shows how to paint an area with media.</span></span> <span data-ttu-id="4e5d3-104">メディアを使用して領域を塗りつぶす 1 つの方法は、<xref:System.Windows.Media.VisualBrush> と共に <xref:System.Windows.Controls.MediaElement> を使用する方法です。</span><span class="sxs-lookup"><span data-stu-id="4e5d3-104">One way to paint an area with media is to use a <xref:System.Windows.Controls.MediaElement> together with a <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="4e5d3-105"><xref:System.Windows.Controls.MediaElement> を使用してメディアを読み込み、再生し、それを使用して <xref:System.Windows.Media.VisualBrush> の <xref:System.Windows.Media.VisualBrush.Visual%2A> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="4e5d3-105">Use the <xref:System.Windows.Controls.MediaElement> to load and play the media, and then use it to set the <xref:System.Windows.Media.VisualBrush.Visual%2A> property of the <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="4e5d3-106">それから、<xref:System.Windows.Media.VisualBrush> を使用して、読み込まれたメディアで領域を塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="4e5d3-106">You can then use the <xref:System.Windows.Media.VisualBrush> to paint an area with the loaded media.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e5d3-107">例</span><span class="sxs-lookup"><span data-stu-id="4e5d3-107">Example</span></span>  
 <span data-ttu-id="4e5d3-108">次の例では、<xref:System.Windows.Controls.MediaElement> と <xref:System.Windows.Media.VisualBrush> を使用して、<xref:System.Windows.Controls.TextBlock> コントロールの <xref:System.Windows.Controls.TextBlock.Foreground%2A> をビデオで塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="4e5d3-108">The following example uses a <xref:System.Windows.Controls.MediaElement> and a <xref:System.Windows.Media.VisualBrush> to paint the <xref:System.Windows.Controls.TextBlock.Foreground%2A> of a <xref:System.Windows.Controls.TextBlock> control with video.</span></span> <span data-ttu-id="4e5d3-109">この例では、<xref:System.Windows.Controls.MediaElement> の <xref:System.Windows.Controls.MediaElement.IsMuted%2A> プロパティを `true` に設定して、音声が生成されないようにします。</span><span class="sxs-lookup"><span data-stu-id="4e5d3-109">This example sets the <xref:System.Windows.Controls.MediaElement.IsMuted%2A> property of the <xref:System.Windows.Controls.MediaElement> to `true` so that it produces no sound.</span></span>  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](~/samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundinline)]
 [!code-xaml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](~/samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundinline)]  
  
## <a name="example"></a><span data-ttu-id="4e5d3-110">例</span><span class="sxs-lookup"><span data-stu-id="4e5d3-110">Example</span></span>  
 <span data-ttu-id="4e5d3-111"><xref:System.Windows.Media.VisualBrush> は <xref:System.Windows.Media.TileBrush> クラスから継承されるため、いくつかのタイル モードが用意されています。</span><span class="sxs-lookup"><span data-stu-id="4e5d3-111">Because <xref:System.Windows.Media.VisualBrush> inherits from the <xref:System.Windows.Media.TileBrush> class, it provides several tiling modes.</span></span> <span data-ttu-id="4e5d3-112"><xref:System.Windows.Media.VisualBrush> の <xref:System.Windows.Media.TileBrush.TileMode%2A> プロパティを <xref:System.Windows.Media.TileMode.Tile> に設定し、その <xref:System.Windows.Media.TileBrush.Viewport%2A> プロパティを塗りつぶす領域よりも小さい値に設定すると、タイル化されたパターンを作成できます。</span><span class="sxs-lookup"><span data-stu-id="4e5d3-112">By setting the <xref:System.Windows.Media.TileBrush.TileMode%2A> property of a <xref:System.Windows.Media.VisualBrush> to <xref:System.Windows.Media.TileMode.Tile> and by setting its <xref:System.Windows.Media.TileBrush.Viewport%2A> property to a value smaller than the area that you are painting, you can create a tiled pattern.</span></span>  
  
 <span data-ttu-id="4e5d3-113">次の例は、前の例と <xref:System.Windows.Media.VisualBrush> がビデオからパターンを生成することを除き同じです。</span><span class="sxs-lookup"><span data-stu-id="4e5d3-113">The following example is identical to the previous example, except that the <xref:System.Windows.Media.VisualBrush> generates a pattern from the video.</span></span>  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](~/samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-xaml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](~/samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundtiledinline)]  
  
 <span data-ttu-id="4e5d3-114">メディア ファイルなどのコンテンツ ファイルをお使いのアプリケーションに追加する方法については、「[WPF アプリケーションのリソース ファイル、コンテンツ ファイル、およびデータ ファイル](../app-development/wpf-application-resource-content-and-data-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e5d3-114">For information about how to add a content file, such as a media file, to your application, see [WPF Application Resource, Content, and Data Files](../app-development/wpf-application-resource-content-and-data-files.md).</span></span> <span data-ttu-id="4e5d3-115">メディア ファイルを追加する場合は、それをリソース ファイルとしてではなく、コンテンツ ファイルとして追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e5d3-115">When you add a media file, you must add it as a content file, not as a resource file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e5d3-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="4e5d3-116">See also</span></span>

- <xref:System.Windows.Media.VisualBrush>
- [<span data-ttu-id="4e5d3-117">イメージ、描画、およびビジュアルによる塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="4e5d3-117">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
- [<span data-ttu-id="4e5d3-118">TileBrush の概要</span><span class="sxs-lookup"><span data-stu-id="4e5d3-118">TileBrush Overview</span></span>](tilebrush-overview.md)
- [<span data-ttu-id="4e5d3-119">マルチメディアの概要</span><span class="sxs-lookup"><span data-stu-id="4e5d3-119">Multimedia Overview</span></span>](multimedia-overview.md)
