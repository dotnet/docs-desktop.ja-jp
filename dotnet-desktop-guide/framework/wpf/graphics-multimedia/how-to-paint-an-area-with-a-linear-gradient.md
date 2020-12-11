---
title: '方法: 線形グラデーションを使用して領域を塗りつぶす'
ms.date: 03/30/2017
helpviewer_keywords:
- linear gradients [WPF], painting with
- brushes [WPF], painting with linear gradients
- painting [WPF], with linear gradients
ms.assetid: 00e0cd04-48c0-4ec5-850e-d321beb37a34
ms.openlocfilehash: 76c491632911c48db34d932ba3895278591378a5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982603"
---
# <a name="how-to-paint-an-area-with-a-linear-gradient"></a><span data-ttu-id="ee4c0-102">方法: 線形グラデーションを使用して領域を塗りつぶす</span><span class="sxs-lookup"><span data-stu-id="ee4c0-102">How to: Paint an Area with a Linear Gradient</span></span>
<span data-ttu-id="ee4c0-103">この例では、<xref:System.Windows.Media.LinearGradientBrush> クラスを使用して、線状グラデーションで領域を塗りつぶす方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ee4c0-103">This example shows how to use the <xref:System.Windows.Media.LinearGradientBrush> class to paint an area with a linear gradient.</span></span> <span data-ttu-id="ee4c0-104">次の例では、<xref:System.Windows.Shapes.Rectangle> の <xref:System.Windows.Shapes.Shape.Fill%2A> が、黄色から赤、青、ライム グリーンへと変化する対角線方向の線形グラデーションで塗りつぶされています。</span><span class="sxs-lookup"><span data-stu-id="ee4c0-104">In the following example, the <xref:System.Windows.Shapes.Shape.Fill%2A> of a <xref:System.Windows.Shapes.Rectangle> is painted with a diagonal linear gradient that transitions from yellow to red to blue to lime green.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee4c0-105">例</span><span class="sxs-lookup"><span data-stu-id="ee4c0-105">Example</span></span>  
 [!code-xaml[GradientBrushExamples_snip#DiagonalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]  
  
 <span data-ttu-id="ee4c0-106">次の図は、前の例で作成されたグラデーションを示しています。</span><span class="sxs-lookup"><span data-stu-id="ee4c0-106">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="ee4c0-107">![対角線方向の線形グラデーション](./media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")</span><span class="sxs-lookup"><span data-stu-id="ee4c0-107">![Diagonal linear gradient](./media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")</span></span>  
  
 <span data-ttu-id="ee4c0-108">水平方向の線状グラデーションを作成するには、<xref:System.Windows.Media.LinearGradientBrush> の <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> と <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> を (0,0.5) と (1,0.5) に変更します。</span><span class="sxs-lookup"><span data-stu-id="ee4c0-108">To create a horizontal linear gradient, change the <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> and <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> of the <xref:System.Windows.Media.LinearGradientBrush> to (0,0.5) and (1,0.5).</span></span> <span data-ttu-id="ee4c0-109">次の例では、<xref:System.Windows.Shapes.Rectangle> は水平方向の線形グラデーションで塗りつぶされています。</span><span class="sxs-lookup"><span data-stu-id="ee4c0-109">In the following example, a <xref:System.Windows.Shapes.Rectangle> is painted with a horizontal linear gradient.</span></span>  
  
 [!code-xaml[GradientBrushExamples_snip#HorizontalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]  
  
 <span data-ttu-id="ee4c0-110">次の図は、前の例で作成されたグラデーションを示しています。</span><span class="sxs-lookup"><span data-stu-id="ee4c0-110">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="ee4c0-111">![水平方向の線形グラデーション](./media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")</span><span class="sxs-lookup"><span data-stu-id="ee4c0-111">![A horizontal linear gradient](./media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")</span></span>  
  
 <span data-ttu-id="ee4c0-112">垂直方向の線状グラデーションを作成するには、<xref:System.Windows.Media.LinearGradientBrush> の <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> と <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> を (0.5,0) と (0.5,1) に変更します。</span><span class="sxs-lookup"><span data-stu-id="ee4c0-112">To create a vertical linear gradient, change the <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> and <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> of the <xref:System.Windows.Media.LinearGradientBrush> to (0.5,0) and (0.5,1).</span></span> <span data-ttu-id="ee4c0-113">次の例では、<xref:System.Windows.Shapes.Rectangle> は垂直方向の線形グラデーションで塗りつぶされています。</span><span class="sxs-lookup"><span data-stu-id="ee4c0-113">In the following example, a <xref:System.Windows.Shapes.Rectangle> is painted with a vertical linear gradient.</span></span>  
  
 [!code-xaml[GradientBrushExamples_snip#VerticalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]  
  
 <span data-ttu-id="ee4c0-114">次の図は、前の例で作成されたグラデーションを示しています。</span><span class="sxs-lookup"><span data-stu-id="ee4c0-114">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="ee4c0-115">![垂直方向の線形グラデーション](./media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")</span><span class="sxs-lookup"><span data-stu-id="ee4c0-115">![Vertical linear gradient](./media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ee4c0-116">このトピックの例では、始点と終点を設定するために既定の座標系を使用しています。</span><span class="sxs-lookup"><span data-stu-id="ee4c0-116">The examples in this topic use the default coordinate system for setting start points and end points.</span></span> <span data-ttu-id="ee4c0-117">既定の座標系は、境界ボックスに対して相対的です。0 は境界ボックスの 0% を示し、1 は境界ボックスの 100% を示します。</span><span class="sxs-lookup"><span data-stu-id="ee4c0-117">The default coordinate system is relative to a bounding box: 0 indicates 0 percent of the bounding box, and 1 indicates 100 percent of the bounding box.</span></span> <span data-ttu-id="ee4c0-118">この座標系を変更するには、<xref:System.Windows.Media.GradientBrush.MappingMode%2A> プロパティを値 <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType> に設定します。</span><span class="sxs-lookup"><span data-stu-id="ee4c0-118">You can change this coordinate system by setting the <xref:System.Windows.Media.GradientBrush.MappingMode%2A> property to the value <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ee4c0-119">絶対座標系は、境界ボックスに相対しません。</span><span class="sxs-lookup"><span data-stu-id="ee4c0-119">An absolute coordinate system is not relative to a bounding box.</span></span> <span data-ttu-id="ee4c0-120">値は、ローカル空間に直接変換されます。</span><span class="sxs-lookup"><span data-stu-id="ee4c0-120">Values are interpreted directly in local space.</span></span>  
  
 <span data-ttu-id="ee4c0-121">その他の例については、[ブラシのサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)のページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee4c0-121">For additional examples, see [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span> <span data-ttu-id="ee4c0-122">グラデーションとその他の種類のブラシの詳細については、「[純色およびグラデーションによる塗りつぶしの概要](painting-with-solid-colors-and-gradients-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee4c0-122">For more information about gradients and other types of brushes, see [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>
