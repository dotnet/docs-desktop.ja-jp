---
title: '方法: 要素をスケーリングする'
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], elements
- graphics [WPF], scaling elements
ms.assetid: 18158d94-bbe7-4f6a-814e-84d27fa748bf
ms.openlocfilehash: 34d954f68747be9eedc0ef71634e0c18b411d260
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984143"
---
# <a name="how-to-scale-an-element"></a><span data-ttu-id="19575-102">方法: 要素をスケーリングする</span><span class="sxs-lookup"><span data-stu-id="19575-102">How to: Scale an Element</span></span>
<span data-ttu-id="19575-103">この例では、<xref:System.Windows.Media.ScaleTransform> を使用して要素を拡大縮小する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="19575-103">This example shows how to use a <xref:System.Windows.Media.ScaleTransform> to scale an element.</span></span>  
  
 <span data-ttu-id="19575-104"><xref:System.Windows.Media.ScaleTransform.ScaleX%2A> プロパティと <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> プロパティは、指定した係数で要素のサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="19575-104">Use the <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> and <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> properties to resize the element by the factor you specify.</span></span> <span data-ttu-id="19575-105">たとえば、<xref:System.Windows.Media.ScaleTransform.ScaleX%2A> 値が 1.5 の場合、要素は元の幅の 150% に拡大します。</span><span class="sxs-lookup"><span data-stu-id="19575-105">For example, a <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> value of 1.5 stretches the element to 150 percent of its original width.</span></span> <span data-ttu-id="19575-106"><xref:System.Windows.Media.ScaleTransform.ScaleY%2A> 値が 0.5 の場合は、要素の高さが 50% 縮小します。</span><span class="sxs-lookup"><span data-stu-id="19575-106">A <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> value of 0.5 shrinks the height of an element by 50 percent.</span></span>  
  
 <span data-ttu-id="19575-107"><xref:System.Windows.Media.ScaleTransform.CenterX%2A> プロパティと <xref:System.Windows.Media.ScaleTransform.CenterY%2A> プロパティを使用して、拡大縮小操作の中心となる点を指定します。</span><span class="sxs-lookup"><span data-stu-id="19575-107">Use the <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A> properties to specify the point that is the center of the scale operation.</span></span> <span data-ttu-id="19575-108">既定では、<xref:System.Windows.Media.ScaleTransform> の中心点は (0, 0) であり、四角形の左上隅に該当します。</span><span class="sxs-lookup"><span data-stu-id="19575-108">By default, a <xref:System.Windows.Media.ScaleTransform> is centered at the point (0,0), which corresponds to the upper-left corner of the rectangle.</span></span> <span data-ttu-id="19575-109"><xref:System.Windows.Media.Transform> を適用すると、オブジェクトが存在する座標空間が変更されるため、要素が移動するという効果に加え、大きくなるように見えるという効果が起こります。</span><span class="sxs-lookup"><span data-stu-id="19575-109">This has the effect of moving the element and also of making it appear larger, because when you apply a <xref:System.Windows.Media.Transform>, you change the coordinate space in which the object resides.</span></span>  
  
 <span data-ttu-id="19575-110">次の例は、<xref:System.Windows.Media.ScaleTransform> を使用して、50 × 50 の <xref:System.Windows.Shapes.Rectangle> のサイズを 2 倍にします。</span><span class="sxs-lookup"><span data-stu-id="19575-110">The following example uses a <xref:System.Windows.Media.ScaleTransform> to double the size of a 50-by-50 <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="19575-111"><xref:System.Windows.Media.ScaleTransform> の値は、<xref:System.Windows.Media.ScaleTransform.CenterX%2A> と <xref:System.Windows.Media.ScaleTransform.CenterY%2A> の両方に対して 0 (既定) に設定されています。</span><span class="sxs-lookup"><span data-stu-id="19575-111">The <xref:System.Windows.Media.ScaleTransform> has a value of 0 (the default) for both <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19575-112">例</span><span class="sxs-lookup"><span data-stu-id="19575-112">Example</span></span>  
 [!code-xaml[transformsSample#21](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#21)]  
  
 <span data-ttu-id="19575-113">通常は、<xref:System.Windows.Media.ScaleTransform.CenterX%2A> と <xref:System.Windows.Media.ScaleTransform.CenterY%2A> を、拡大縮小するオブジェクトの中心、つまり (<xref:System.Windows.FrameworkElement.Width%2A>/2, <xref:System.Windows.FrameworkElement.Height%2A>/2) に設定します。</span><span class="sxs-lookup"><span data-stu-id="19575-113">Typically, you set <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A> to the center of the object that is scaled: (<xref:System.Windows.FrameworkElement.Width%2A>/2, <xref:System.Windows.FrameworkElement.Height%2A>/2).</span></span>  
  
 <span data-ttu-id="19575-114">次の例に、サイズを 2 倍にしたもう 1 つの <xref:System.Windows.Shapes.Rectangle> を示します。ただし、この <xref:System.Windows.Media.ScaleTransform> では、<xref:System.Windows.Media.ScaleTransform.CenterX%2A> と <xref:System.Windows.Media.ScaleTransform.CenterY%2A>の両方の値が 25 に設定されており、これは長方形の中心に相当します。</span><span class="sxs-lookup"><span data-stu-id="19575-114">The following example shows another <xref:System.Windows.Shapes.Rectangle> that is doubled in size; however, this <xref:System.Windows.Media.ScaleTransform> has a value of 25 for both <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A>, which corresponds to the center of the rectangle.</span></span>  
  
 [!code-xaml[transformsSample#22](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#22)]  
  
 <span data-ttu-id="19575-115">次の図は、2 つの <xref:System.Windows.Media.ScaleTransform> 操作間の相違を示しています。</span><span class="sxs-lookup"><span data-stu-id="19575-115">The following illustration shows the difference between the two <xref:System.Windows.Media.ScaleTransform> operations.</span></span> <span data-ttu-id="19575-116">点線は、拡大/縮小する前の四角形のサイズと位置を示しています。</span><span class="sxs-lookup"><span data-stu-id="19575-116">The dotted line shows the size and position of the rectangle before scaling.</span></span>  
  
 <span data-ttu-id="19575-117">![中心点が異なる 2 倍の拡大](./media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")</span><span class="sxs-lookup"><span data-stu-id="19575-117">![2x scales with different center points](./media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")</span></span>  
<span data-ttu-id="19575-118">2 つの ScaleTransform 操作では、ScaleX と ScaleY の値は同じですが、中心点が異なっています。</span><span class="sxs-lookup"><span data-stu-id="19575-118">Two ScaleTransform operations with identical ScaleX and ScaleY values but different centers</span></span>  
  
 <span data-ttu-id="19575-119">サンプル全体については、「[2D 変換のサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="19575-119">For the complete sample, see [2D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19575-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="19575-120">See also</span></span>

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.ScaleTransform>
- [<span data-ttu-id="19575-121">変換の概要</span><span class="sxs-lookup"><span data-stu-id="19575-121">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="19575-122">方法トピック</span><span class="sxs-lookup"><span data-stu-id="19575-122">How-to Topics</span></span>](transformations-how-to-topics.md)
