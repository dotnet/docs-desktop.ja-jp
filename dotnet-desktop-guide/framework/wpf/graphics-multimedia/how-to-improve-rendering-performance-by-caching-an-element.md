---
title: '方法: 要素をキャッシュしてレンダリングのパフォーマンスを向上させる'
ms.date: 03/30/2017
helpviewer_keywords:
- rendering performance [WPF], caching an element
- BitmapCache [WPF], improving rendering performance
- CacheMode [WPF], improving rendering performance
- performance [WPF], caching an element
- UIElement [WPF], caching
ms.assetid: 4739c1fc-60ba-4c46-aba6-f6c1a2688f19
ms.openlocfilehash: 118e8b0cca52c44788c9d5b291d710f765e7af2a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983071"
---
# <a name="how-to-improve-rendering-performance-by-caching-an-element"></a><span data-ttu-id="59dda-102">方法: 要素をキャッシュしてレンダリングのパフォーマンスを向上させる</span><span class="sxs-lookup"><span data-stu-id="59dda-102">How to: Improve Rendering Performance by Caching an Element</span></span>
<span data-ttu-id="59dda-103"><xref:System.Windows.Media.BitmapCache> クラスを使用すると、複雑な <xref:System.Windows.UIElement> のレンダリング パフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="59dda-103">Use the <xref:System.Windows.Media.BitmapCache> class to improve rendering performance of a complex <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="59dda-104">要素をキャッシュするには、<xref:System.Windows.Media.BitmapCache> クラスの新しいインスタンスを作成し、それを要素の <xref:System.Windows.UIElement.CacheMode%2A> プロパティに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="59dda-104">To cache an element, create a new instance of the <xref:System.Windows.Media.BitmapCache> class and assign it to the element's <xref:System.Windows.UIElement.CacheMode%2A> property.</span></span> <span data-ttu-id="59dda-105"><xref:System.Windows.Media.BitmapCache>は、<xref:System.Windows.Media.BitmapCacheBrush> で効率的に再利用できます。</span><span class="sxs-lookup"><span data-stu-id="59dda-105">You can reuse a <xref:System.Windows.Media.BitmapCache> efficiently in a <xref:System.Windows.Media.BitmapCacheBrush>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="59dda-106">例</span><span class="sxs-lookup"><span data-stu-id="59dda-106">Example</span></span>  
 <span data-ttu-id="59dda-107">次のコード例では、複合要素を作成し、それをビットマップとしてキャッシュして、要素をアニメーション化するときにパフォーマンスを向上させる方法を示します。</span><span class="sxs-lookup"><span data-stu-id="59dda-107">The following code example shows how to create a complex element and cache it as a bitmap, which improves performance when the element is animated.</span></span> <span data-ttu-id="59dda-108">この要素は、頂点が多数ある形状ジオメトリを保持するキャンバスです。</span><span class="sxs-lookup"><span data-stu-id="59dda-108">The element is a canvas that holds shape geometries with many vertices.</span></span> <span data-ttu-id="59dda-109">既定値の <xref:System.Windows.Media.BitmapCache> がキャンバスの <xref:System.Windows.UIElement.CacheMode%2A> に割り当てられ、キャッシュされたビットマップはアニメーションでスムーズにスケーリングされます。</span><span class="sxs-lookup"><span data-stu-id="59dda-109">A <xref:System.Windows.Media.BitmapCache> with default values is assigned to the <xref:System.Windows.UIElement.CacheMode%2A> of the canvas, and an animation shows the smooth scaling of the cached bitmap.</span></span>  
  
 [!code-xaml[System.Windows.Media.BitmapCache#_BitmapCacheXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcache/cs/window1.xaml#_bitmapcachexaml)]  
  
## <a name="see-also"></a><span data-ttu-id="59dda-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="59dda-110">See also</span></span>

- <xref:System.Windows.Media.BitmapCache>
- <xref:System.Windows.Media.BitmapCacheBrush>
- <xref:System.Windows.UIElement.CacheMode%2A>
- [<span data-ttu-id="59dda-111">方法: キャッシュされた要素をブラシとして使用する</span><span class="sxs-lookup"><span data-stu-id="59dda-111">How to: Use a Cached Element as a Brush</span></span>](how-to-use-a-cached-element-as-a-brush.md)
