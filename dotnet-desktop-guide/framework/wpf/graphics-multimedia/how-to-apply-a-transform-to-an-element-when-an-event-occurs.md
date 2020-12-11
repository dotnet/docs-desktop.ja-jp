---
title: '方法: イベントの発生時に要素に変換を適用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], transformations as event responses
- properties [WPF], LayoutTransform
- transformations as event responses [WPF]
- properties [WPF], RenderTransform
- LayoutTransform property [WPF]
ms.assetid: 71e4327e-ca57-444c-a3cf-09fb381491a0
ms.openlocfilehash: 8f04db274432c0e89c6839bef825976c8a2f853c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96979927"
---
# <a name="how-to-apply-a-transform-to-an-element-when-an-event-occurs"></a><span data-ttu-id="799be-102">方法: イベントの発生時に要素に変換を適用する</span><span class="sxs-lookup"><span data-stu-id="799be-102">How to: Apply a Transform to an Element When an Event Occurs</span></span>
<span data-ttu-id="799be-103">この例では、イベントが発生したときに <xref:System.Windows.Media.ScaleTransform> を適用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="799be-103">This example shows how to apply a <xref:System.Windows.Media.ScaleTransform> when an event occurs.</span></span> <span data-ttu-id="799be-104">ここで示される概念は、他の種類の変換を適用する場合に使用するものと同じです。</span><span class="sxs-lookup"><span data-stu-id="799be-104">The concept that is shown here is the same that you use for applying other types of transformations.</span></span> <span data-ttu-id="799be-105">使用可能な変換の種類の詳細については、「<xref:System.Windows.Media.Transform> クラス」または「[変換の概要](transforms-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="799be-105">For more information about the available types of transformations, see the <xref:System.Windows.Media.Transform> class or [Transforms Overview](transforms-overview.md).</span></span>  
  
 <span data-ttu-id="799be-106">要素に変換を適用するには、次の 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="799be-106">You can apply a transform to an element in either of these two ways:</span></span>  
  
- <span data-ttu-id="799be-107">変換がレイアウトに影響 "*しない*" ようにする場合は、要素の <xref:System.Windows.UIElement.RenderTransform%2A> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="799be-107">If you do *not* want the transform to affect layout, use the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span>  
  
- <span data-ttu-id="799be-108">変換がレイアウトに影響するようにする場合は、要素の <xref:System.Windows.FrameworkElement.LayoutTransform%2A> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="799be-108">If you do want the transform to affect layout, use the <xref:System.Windows.FrameworkElement.LayoutTransform%2A> property of the element.</span></span>  
  
 <span data-ttu-id="799be-109">次の例では、ボタンの <xref:System.Windows.UIElement.RenderTransform%2A> プロパティに <xref:System.Windows.Media.ScaleTransform> を適用します。</span><span class="sxs-lookup"><span data-stu-id="799be-109">The following example applies a <xref:System.Windows.Media.ScaleTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of a button.</span></span> <span data-ttu-id="799be-110">マウスをボタンの上に移動すると、<xref:System.Windows.Media.ScaleTransform> の <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> プロパティと <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> プロパティが `2` に設定され、ボタンが大きくなります。</span><span class="sxs-lookup"><span data-stu-id="799be-110">When the mouse moves over the button, the <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> and <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> properties of the <xref:System.Windows.Media.ScaleTransform> are set to `2`, which causes the button to become larger.</span></span> <span data-ttu-id="799be-111">マウスがボタンから離れると、<xref:System.Windows.Media.ScaleTransform.ScaleX%2A> と <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> が `1` に設定され、ボタンは元のサイズに戻ります。</span><span class="sxs-lookup"><span data-stu-id="799be-111">When the mouse moves off the button, <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> and <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> are set to `1`, which causes the button to return to its original size.</span></span>  
  
## <a name="example"></a><span data-ttu-id="799be-112">例</span><span class="sxs-lookup"><span data-stu-id="799be-112">Example</span></span>  
 [!code-xaml[ButtonTransform#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml#1)]  
  
 [!code-csharp[ButtonTransform#1cb](~/samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml.cs#1cb)]
 [!code-vb[ButtonTransform#1cb](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ButtonTransform/VisualBasic/ButtonTransformExample.xaml.vb#1cb)]  
  
## <a name="see-also"></a><span data-ttu-id="799be-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="799be-113">See also</span></span>

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.ScaleTransform>
- [<span data-ttu-id="799be-114">変換の概要</span><span class="sxs-lookup"><span data-stu-id="799be-114">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="799be-115">方法トピック</span><span class="sxs-lookup"><span data-stu-id="799be-115">How-to Topics</span></span>](transformations-how-to-topics.md)
- [<span data-ttu-id="799be-116">ルーティング イベントの概要</span><span class="sxs-lookup"><span data-stu-id="799be-116">Routed Events Overview</span></span>](../advanced/routed-events-overview.md)
