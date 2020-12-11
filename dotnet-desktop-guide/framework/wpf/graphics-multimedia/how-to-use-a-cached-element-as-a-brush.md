---
title: '方法: キャッシュされた要素をブラシとして使用する'
ms.date: 03/30/2017
helpviewer_keywords:
- BitmapCache [WPF], using
- cached element [WPF], use as a brush
- BitmapCacheBrush [WPF], using
- CacheMode [WPF], using
ms.assetid: d36e944a-866e-4baf-98c4-fd6a75f6fdd0
ms.openlocfilehash: 78df242c7f00b69e36ea4ab6751f51509d9e2220
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985255"
---
# <a name="how-to-use-a-cached-element-as-a-brush"></a><span data-ttu-id="9fcca-102">方法: キャッシュされた要素をブラシとして使用する</span><span class="sxs-lookup"><span data-stu-id="9fcca-102">How to: Use a Cached Element as a Brush</span></span>
<span data-ttu-id="9fcca-103"><xref:System.Windows.Media.BitmapCacheBrush> クラスを使用し、キャッシュされた要素を効率良く再利用します。</span><span class="sxs-lookup"><span data-stu-id="9fcca-103">Use the <xref:System.Windows.Media.BitmapCacheBrush> class to reuse a cached element efficiently.</span></span> <span data-ttu-id="9fcca-104">要素をキャッシュするには、<xref:System.Windows.Media.BitmapCache> クラスの新しいインスタンスを作成し、それを要素の <xref:System.Windows.UIElement.CacheMode%2A> プロパティに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="9fcca-104">To cache an element, create a new instance of the <xref:System.Windows.Media.BitmapCache> class and assign it to the element's <xref:System.Windows.UIElement.CacheMode%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9fcca-105">例</span><span class="sxs-lookup"><span data-stu-id="9fcca-105">Example</span></span>  
 <span data-ttu-id="9fcca-106">キャッシュされた要素を再利用する方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="9fcca-106">The following code example shows how to reuse a cached element.</span></span> <span data-ttu-id="9fcca-107">キャッシュされた要素は、大きな画像を表示する <xref:System.Windows.Controls.Image> コントロールです。</span><span class="sxs-lookup"><span data-stu-id="9fcca-107">The cached element is an <xref:System.Windows.Controls.Image> control that displays a large image.</span></span> <span data-ttu-id="9fcca-108"><xref:System.Windows.Controls.Image> コントロールは <xref:System.Windows.Media.BitmapCache> クラスを使用することでビットマップとしてキャッシュされ、それを <xref:System.Windows.Media.BitmapCacheBrush> に割り当てることでキャッシュが再利用されます。</span><span class="sxs-lookup"><span data-stu-id="9fcca-108">The <xref:System.Windows.Controls.Image> control is cached as a bitmap by using the <xref:System.Windows.Media.BitmapCache> class, and the cache is reused by assigning it to a <xref:System.Windows.Media.BitmapCacheBrush>.</span></span> <span data-ttu-id="9fcca-109">ブラシは 25 個のボタンの背景に割り当てられ、効率的な再利用を示します。</span><span class="sxs-lookup"><span data-stu-id="9fcca-109">The brush is assigned to the background of twenty-five buttons to show efficient reuse.</span></span>  
  
 [!code-xaml[System.Windows.Media.BitmapCacheBrush#_BitmapCacheBrushXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcachebrush/cs/window1.xaml#_bitmapcachebrushxaml)]  
  
## <a name="see-also"></a><span data-ttu-id="9fcca-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="9fcca-110">See also</span></span>

- <xref:System.Windows.Media.BitmapCache>
- <xref:System.Windows.Media.BitmapCacheBrush>
- <xref:System.Windows.UIElement.CacheMode%2A>
- [<span data-ttu-id="9fcca-111">方法: 要素をキャッシュしてレンダリングのパフォーマンスを向上させる</span><span class="sxs-lookup"><span data-stu-id="9fcca-111">How to: Improve Rendering Performance by Caching an Element</span></span>](how-to-improve-rendering-performance-by-caching-an-element.md)
