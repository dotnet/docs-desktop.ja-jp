---
title: '方法: 放射状グラデーションを使用して領域を塗りつぶす'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with radial gradients
- radial gradients [WPF], painting with
- painting [WPF], with radial gradients
ms.assetid: b5d0fc8a-8986-4796-b003-a75b41a48928
ms.openlocfilehash: 8a53d5d7247f82905816265f7c92b22f287591c5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982599"
---
# <a name="how-to-paint-an-area-with-a-radial-gradient"></a><span data-ttu-id="b17fe-102">方法: 放射状グラデーションを使用して領域を塗りつぶす</span><span class="sxs-lookup"><span data-stu-id="b17fe-102">How to: Paint an Area with a Radial Gradient</span></span>
<span data-ttu-id="b17fe-103">この例では、<xref:System.Windows.Media.RadialGradientBrush> クラスを使用して、放射状グラデーションで領域を塗りつぶす方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b17fe-103">This example shows how to use the <xref:System.Windows.Media.RadialGradientBrush> class to paint an area with a radial gradient.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b17fe-104">例</span><span class="sxs-lookup"><span data-stu-id="b17fe-104">Example</span></span>  
 <span data-ttu-id="b17fe-105">次の例では、<xref:System.Windows.Media.RadialGradientBrush> を使用して、黄色から赤、青からライム グリーンに変わる放射状グラデーションで四角形を塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="b17fe-105">The following example uses a <xref:System.Windows.Media.RadialGradientBrush> to paint a rectangle with a radial gradient that transitions from yellow to red to blue to lime green.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/RadialGradientBrushSnippet.cs#simpleradialgradientexamplewholepage)]
 [!code-vb[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/radialgradientbrushsnippet.vb#simpleradialgradientexamplewholepage)]
 [!code-xaml[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/RadialGradientBrushSnippet.xaml#simpleradialgradientexamplewholepage)]  
  
 <span data-ttu-id="b17fe-106">次の図は、前の例のグラデーションを示しています。</span><span class="sxs-lookup"><span data-stu-id="b17fe-106">The following illustration shows the gradient from the preceding example.</span></span> <span data-ttu-id="b17fe-107">グラデーションの境界が強調表示されています。</span><span class="sxs-lookup"><span data-stu-id="b17fe-107">The gradient's stops have been highlighted.</span></span>  
  
 <span data-ttu-id="b17fe-108">![放射状グラデーションのグラデーション境界](./media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")</span><span class="sxs-lookup"><span data-stu-id="b17fe-108">![Gradient stops in a radial gradient](./media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b17fe-109">このトピックの例では、制御点の設定に既定の座標系を使用しています。</span><span class="sxs-lookup"><span data-stu-id="b17fe-109">The examples in this topic use the default coordinate system for setting control points.</span></span> <span data-ttu-id="b17fe-110">既定の座標系は、境界ボックスに対して相対的です。0 は境界ボックスの 0% を示し、1 は境界ボックスの 100% を示します。</span><span class="sxs-lookup"><span data-stu-id="b17fe-110">The default coordinate system is relative to a bounding box: 0 indicates 0 percent of the bounding box, and 1 indicates 100 percent of the bounding box.</span></span> <span data-ttu-id="b17fe-111">この座標系を変更するには、<xref:System.Windows.Media.GradientBrush.MappingMode%2A> プロパティを値 <xref:System.Windows.Media.BrushMappingMode.Absolute> に設定します。</span><span class="sxs-lookup"><span data-stu-id="b17fe-111">You can change this coordinate system by setting the <xref:System.Windows.Media.GradientBrush.MappingMode%2A> property to the value <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span></span> <span data-ttu-id="b17fe-112">絶対座標系は、境界ボックスに相対しません。</span><span class="sxs-lookup"><span data-stu-id="b17fe-112">An absolute coordinate system is not relative to a bounding box.</span></span> <span data-ttu-id="b17fe-113">値は、ローカル空間に直接変換されます。</span><span class="sxs-lookup"><span data-stu-id="b17fe-113">Values are interpreted directly in local space.</span></span>  
  
 <span data-ttu-id="b17fe-114"><xref:System.Windows.Media.RadialGradientBrush> の他の例については、[ブラシのサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b17fe-114">For additional <xref:System.Windows.Media.RadialGradientBrush> examples, see the [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span> <span data-ttu-id="b17fe-115">グラデーションとその他の種類のブラシの詳細については、「[純色およびグラデーションによる塗りつぶしの概要](painting-with-solid-colors-and-gradients-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b17fe-115">For more information about gradients and other types of brushes, see [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>
