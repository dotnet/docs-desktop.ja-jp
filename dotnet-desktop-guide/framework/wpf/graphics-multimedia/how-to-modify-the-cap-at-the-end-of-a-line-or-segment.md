---
title: '方法: 直線または線分の終点のキャップを変更する'
ms.date: 03/30/2017
helpviewer_keywords:
- Shape elements [WPF], ends
- Shape elements [WPF], caps
- graphics [WPF], Shape caps
ms.assetid: f4bf3416-b3d8-4568-b98e-3eda8f6dbf7a
ms.openlocfilehash: 5f755d7b4d1682755ea461121f91c0666d450ad1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985900"
---
# <a name="how-to-modify-the-cap-at-the-end-of-a-line-or-segment"></a><span data-ttu-id="f1fc9-102">方法: 直線または線分の終点のキャップを変更する</span><span class="sxs-lookup"><span data-stu-id="f1fc9-102">How to: Modify the Cap at the End of a Line or Segment</span></span>
<span data-ttu-id="f1fc9-103">この例では、開いた <xref:System.Windows.Shapes.Shape> 要素の始点または終点で図形を変更する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f1fc9-103">This example shows how to modify the shape at the start or end of an open <xref:System.Windows.Shapes.Shape> element.</span></span> <span data-ttu-id="f1fc9-104">開いた <xref:System.Windows.Shapes.Shape> の始点の線端を変更するには、<xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="f1fc9-104">To change the cap at the beginning of an open <xref:System.Windows.Shapes.Shape>, use its <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> property.</span></span> <span data-ttu-id="f1fc9-105">開いた <xref:System.Windows.Shapes.Shape> の終点の線端を変更するには、<xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="f1fc9-105">To change the cap at the end of an open <xref:System.Windows.Shapes.Shape>, use its <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> property.</span></span> <span data-ttu-id="f1fc9-106">使用可能な線端を確認するには、<xref:System.Windows.Media.PenLineCap> 列挙体をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f1fc9-106">To view the available line caps, see the <xref:System.Windows.Media.PenLineCap> enumeration.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f1fc9-107">このプロパティは、開いた図形 (<xref:System.Windows.Shapes.Line>、<xref:System.Windows.Shapes.Polyline>、開いた <xref:System.Windows.Shapes.Path> 要素など) にのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="f1fc9-107">This property only affects an open shape, such as a <xref:System.Windows.Shapes.Line>, a <xref:System.Windows.Shapes.Polyline>, or an open <xref:System.Windows.Shapes.Path> element.</span></span>  
  
 <span data-ttu-id="f1fc9-108">次の例では、4 つの <xref:System.Windows.Shapes.Polyline> 要素を描画し、それぞれの端で異なる図形セットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f1fc9-108">The following example draws four <xref:System.Windows.Shapes.Polyline> elements and uses a different set of shapes on the ends of each.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1fc9-109">例</span><span class="sxs-lookup"><span data-stu-id="f1fc9-109">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#ShapeLineCaps1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 <span data-ttu-id="f1fc9-110">この例は、より大きなサンプルの一部です。サンプル全体については、「[Shape 要素のサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f1fc9-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1fc9-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1fc9-111">See also</span></span>

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Media.PenLineCap>
