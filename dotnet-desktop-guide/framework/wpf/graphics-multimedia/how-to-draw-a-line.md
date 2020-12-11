---
title: '方法: 線を描画する'
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], lines
- graphics [WPF], lines
- lines [WPF], drawing
ms.assetid: 0513ee01-6b27-4bb3-85f3-3a3e6710d80e
ms.openlocfilehash: a803c1be01086ca8911ef4cc33bd67697239e2c0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974310"
---
# <a name="how-to-draw-a-line"></a><span data-ttu-id="3102c-102">方法: 線を描画する</span><span class="sxs-lookup"><span data-stu-id="3102c-102">How to: Draw a Line</span></span>
<span data-ttu-id="3102c-103">この例では、<xref:System.Windows.Shapes.Line> 要素を使用して線を描画する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3102c-103">This example shows you how to draw lines by using the <xref:System.Windows.Shapes.Line> element.</span></span>  
  
 <span data-ttu-id="3102c-104">線を描画するには、<xref:System.Windows.Shapes.Line> 要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="3102c-104">To draw a line, create a <xref:System.Windows.Shapes.Line> element.</span></span> <span data-ttu-id="3102c-105"><xref:System.Windows.Shapes.Line.X1%2A> および <xref:System.Windows.Shapes.Line.Y1%2A> プロパティを使用して、開始点を設定します。また、<xref:System.Windows.Shapes.Line.X2%2A> および <xref:System.Windows.Shapes.Line.Y2%2A> プロパティを使用して、終了点を設定します。</span><span class="sxs-lookup"><span data-stu-id="3102c-105">Use its <xref:System.Windows.Shapes.Line.X1%2A> and <xref:System.Windows.Shapes.Line.Y1%2A> properties to set its start point; and use its <xref:System.Windows.Shapes.Line.X2%2A> and <xref:System.Windows.Shapes.Line.Y2%2A> properties to set its end point.</span></span> <span data-ttu-id="3102c-106">最後に、<xref:System.Windows.Shapes.Shape.Stroke%2A> と <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> を設定します。ストロークがない線は非表示になるためです。</span><span class="sxs-lookup"><span data-stu-id="3102c-106">Finally, set its <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> because a line without a stroke is invisible.</span></span>  
  
 <span data-ttu-id="3102c-107">線には内部がないため、線の <xref:System.Windows.Shapes.Shape.Fill%2A> 要素を設定しても効果はありません。</span><span class="sxs-lookup"><span data-stu-id="3102c-107">Setting the <xref:System.Windows.Shapes.Shape.Fill%2A> element for a line has no effect, because a line has no interior.</span></span>  
  
 <span data-ttu-id="3102c-108">次の例では、<xref:System.Windows.Controls.Canvas> 要素内に 3 つの線を描画しています。</span><span class="sxs-lookup"><span data-stu-id="3102c-108">The following example draws three lines inside a <xref:System.Windows.Controls.Canvas> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3102c-109">例</span><span class="sxs-lookup"><span data-stu-id="3102c-109">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#LineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 <span data-ttu-id="3102c-110">この例は、より大きなサンプルの一部です。サンプル全体については、「[Shape 要素のサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3102c-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3102c-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="3102c-111">See also</span></span>

- <xref:System.Windows.Shapes.Line>
- [<span data-ttu-id="3102c-112">Shape 要素のサンプル</span><span class="sxs-lookup"><span data-stu-id="3102c-112">Shape Elements Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
