---
title: '方法: ビジュアルにテキストを描画する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], drawing text to visuals
- visuals [WPF], drawing text to
- text [WPF], drawing to visuals
- drawing [WPF], text to visuals
ms.assetid: fee4003c-e8a6-46ec-babd-2c7f4231a101
ms.openlocfilehash: 654bfadb42f053b6dcf353d4423bddf281d69478
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984847"
---
# <a name="how-to-draw-text-to-a-visual"></a><span data-ttu-id="b9726-102">方法: ビジュアルにテキストを描画する</span><span class="sxs-lookup"><span data-stu-id="b9726-102">How to: Draw Text to a Visual</span></span>
<span data-ttu-id="b9726-103">次の例は、<xref:System.Windows.Media.DrawingContext> オブジェクトを使用して <xref:System.Windows.Media.DrawingVisual> にテキストを描画する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b9726-103">The following example shows how to draw text to a <xref:System.Windows.Media.DrawingVisual> using a <xref:System.Windows.Media.DrawingContext> object.</span></span> <span data-ttu-id="b9726-104">描画コンテキストは、<xref:System.Windows.Media.DrawingVisual> オブジェクトの <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> メソッドを呼び出すことによって返されます。</span><span class="sxs-lookup"><span data-stu-id="b9726-104">A drawing context is returned by calling the <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> method of a <xref:System.Windows.Media.DrawingVisual> object.</span></span> <span data-ttu-id="b9726-105">グラフィックとテキストを描画コンテキストに描画できます。</span><span class="sxs-lookup"><span data-stu-id="b9726-105">You can draw graphics and text into a drawing context.</span></span>  
  
 <span data-ttu-id="b9726-106">テキストを描画コンテキストに描画するには、<xref:System.Windows.Media.DrawingContext> オブジェクトの <xref:System.Windows.Media.DrawingContext.DrawText%2A> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="b9726-106">To draw text into the drawing context, use the <xref:System.Windows.Media.DrawingContext.DrawText%2A> method of a <xref:System.Windows.Media.DrawingContext> object.</span></span> <span data-ttu-id="b9726-107">コンテンツを描画コンテキストに描画し終えたら、<xref:System.Windows.Media.DrawingContext.Close%2A> メソッドを呼び出して描画コンテキストを閉じ、コンテンツを永続化します。</span><span class="sxs-lookup"><span data-stu-id="b9726-107">When you are finished drawing content into the drawing context, call the <xref:System.Windows.Media.DrawingContext.Close%2A> method to close the drawing context and persist the content.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9726-108">例</span><span class="sxs-lookup"><span data-stu-id="b9726-108">Example</span></span>  
 [!code-csharp[DrawingVisualSample#110](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#110)]
 [!code-vb[DrawingVisualSample#110](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#110)]  
  
> [!NOTE]
> <span data-ttu-id="b9726-109">上記のコードの抽出元となった完全なコード サンプルについては、「[DrawingVisual を使用したヒット テストのサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Visual%20Layer/DrawingVisual)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b9726-109">For the complete code sample from which the preceding code example was extracted, see [Hit Test Using DrawingVisuals Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Visual%20Layer/DrawingVisual).</span></span>
