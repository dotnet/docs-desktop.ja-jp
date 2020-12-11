---
title: '方法: ビジュアルの描画コンテンツを列挙する'
ms.date: 03/30/2017
helpviewer_keywords:
- retrieving the DrawingGroup value of a Visual [WPF]
- enumerating the contents of a Visual [WPF]
ms.assetid: 2974ddb3-2997-4713-8fd2-e93d549c58a8
ms.openlocfilehash: 25aa0c3706005c1e16cedd7e06914db764545ebb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985227"
---
# <a name="how-to-enumerate-drawing-content-of-a-visual"></a><span data-ttu-id="b3fd8-102">方法: ビジュアルの描画コンテンツを列挙する</span><span class="sxs-lookup"><span data-stu-id="b3fd8-102">How to: Enumerate Drawing Content of a Visual</span></span>
<span data-ttu-id="b3fd8-103"><xref:System.Windows.Media.Drawing> オブジェクトは、<xref:System.Windows.Media.Visual> のコンテンツを列挙するためのオブジェクト モデルを提供します。</span><span class="sxs-lookup"><span data-stu-id="b3fd8-103">The <xref:System.Windows.Media.Drawing> object provide an object model for enumerating the contents of a <xref:System.Windows.Media.Visual>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3fd8-104">例</span><span class="sxs-lookup"><span data-stu-id="b3fd8-104">Example</span></span>  
 <span data-ttu-id="b3fd8-105">次の例では、<xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> メソッドを使用して <xref:System.Windows.Media.Visual> の <xref:System.Windows.Media.DrawingGroup> 値を取得し、それを列挙します。</span><span class="sxs-lookup"><span data-stu-id="b3fd8-105">The following example uses the <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> method to retrieve the <xref:System.Windows.Media.DrawingGroup> value of a <xref:System.Windows.Media.Visual> and enumerate it.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b3fd8-106">ビジュアルのコンテンツを列挙する場合は、レンダリング データの基になる表現をベクター グラフィックス命令リストとして取得するのではなく、<xref:System.Windows.Media.Drawing> オブジェクトを取得することになります。</span><span class="sxs-lookup"><span data-stu-id="b3fd8-106">When you are enumerating the contents of the visual, you are retrieving <xref:System.Windows.Media.Drawing> objects, and not the underlying representation of the render data as a vector graphics instruction list.</span></span> <span data-ttu-id="b3fd8-107">詳しくは、「[WPF グラフィックス レンダリングの概要](wpf-graphics-rendering-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b3fd8-107">For more information, see [WPF Graphics Rendering Overview](wpf-graphics-rendering-overview.md).</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## <a name="see-also"></a><span data-ttu-id="b3fd8-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3fd8-108">See also</span></span>

- <xref:System.Windows.Media.Drawing>
- <xref:System.Windows.Media.DrawingGroup>
- <xref:System.Windows.Media.VisualTreeHelper>
- [<span data-ttu-id="b3fd8-109">Drawing オブジェクトの概要</span><span class="sxs-lookup"><span data-stu-id="b3fd8-109">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="b3fd8-110">WPF グラフィックス レンダリングの概要</span><span class="sxs-lookup"><span data-stu-id="b3fd8-110">WPF Graphics Rendering Overview</span></span>](wpf-graphics-rendering-overview.md)
