---
title: '方法: 純色で領域を塗りつぶす'
ms.date: 03/30/2017
helpviewer_keywords:
- solid colors [WPF], painting with
- brushes [WPF], painting with solid colors
- painting [WPF], with solid colors
ms.assetid: 5d27d8a7-4bd7-4063-bdf3-2c5c0f19f9d3
ms.openlocfilehash: be28a0af04c4e43cdf745a5429468aee99e34c40
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982596"
---
# <a name="how-to-paint-an-area-with-a-solid-color"></a><span data-ttu-id="a7779-102">方法: 純色で領域を塗りつぶす</span><span class="sxs-lookup"><span data-stu-id="a7779-102">How to: Paint an Area with a Solid Color</span></span>
<span data-ttu-id="a7779-103">純色で領域を塗りつぶす場合、<xref:System.Windows.Media.Brushes.Red%2A> や <xref:System.Windows.Media.Brushes.Blue%2A> などの定義済みのシステム ブラシを使用することも、新しい <xref:System.Windows.Media.SolidColorBrush> を作成し、アルファ、赤、緑、青の値を使用してその <xref:System.Windows.Media.SolidColorBrush.Color%2A> を記述することもできます。</span><span class="sxs-lookup"><span data-stu-id="a7779-103">To paint an area with a solid color, you can use a predefined system brush, such as <xref:System.Windows.Media.Brushes.Red%2A> or <xref:System.Windows.Media.Brushes.Blue%2A>, or you can create a new <xref:System.Windows.Media.SolidColorBrush> and describe its <xref:System.Windows.Media.SolidColorBrush.Color%2A> using alpha, red, green, and blue values.</span></span> <span data-ttu-id="a7779-104">XAML では、16 進数表記を使用して、純色で領域を塗りつぶすこともできます。</span><span class="sxs-lookup"><span data-stu-id="a7779-104">In XAML, you may also paint an area with a solid color by using hexidecimal notation.</span></span>  
  
 <span data-ttu-id="a7779-105">これらの各手法を使用して <xref:System.Windows.Shapes.Rectangle> を青で塗りつぶす例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a7779-105">The following examples uses each of these techniques to paint a <xref:System.Windows.Shapes.Rectangle> blue.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7779-106">例</span><span class="sxs-lookup"><span data-stu-id="a7779-106">Example</span></span>  
 <span data-ttu-id="a7779-107">**定義済みのブラシの使用**</span><span class="sxs-lookup"><span data-stu-id="a7779-107">**Using a Predefined Brush**</span></span>  
  
 <span data-ttu-id="a7779-108">次の例では、定義済みのブラシ <xref:System.Windows.Media.Brushes.Blue%2A> を使用して、四角形を青で塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="a7779-108">In the following example uses the predefined brush <xref:System.Windows.Media.Brushes.Blue%2A> to paint a rectangle blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_predefinedbrush1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_predefinedbrush1)]  
  
 <span data-ttu-id="a7779-109">**16 進数表記の使用**</span><span class="sxs-lookup"><span data-stu-id="a7779-109">**Using Hexadecimal Notation**</span></span>  
  
 <span data-ttu-id="a7779-110">次の例では、8 桁の 16 進数表記を使用して、四角形を青で塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="a7779-110">The next example uses 8-digit hexadecimal notation to paint a rectangle blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_HexNotation8Digit1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_hexnotation8digit1)]  
  
 <span data-ttu-id="a7779-111">**ARGB 値の使用**</span><span class="sxs-lookup"><span data-stu-id="a7779-111">**Using ARGB Values**</span></span>  
  
 <span data-ttu-id="a7779-112">次の例では、<xref:System.Windows.Media.SolidColorBrush> を作成し、青色の ARGB 値を使用してその <xref:System.Windows.Media.SolidColorBrush.Color%2A> を記述します。</span><span class="sxs-lookup"><span data-stu-id="a7779-112">The next example creates a <xref:System.Windows.Media.SolidColorBrush> and describes its <xref:System.Windows.Media.SolidColorBrush.Color%2A> using the ARGB values for the color blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_rgbnotation1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_rgbnotation1)]  
  
 <span data-ttu-id="a7779-113">色を記述するその他の方法については、<xref:System.Windows.Media.Color> 構造体を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7779-113">For other ways of describing color, see the <xref:System.Windows.Media.Color> structure.</span></span>  
  
 <span data-ttu-id="a7779-114">**関連トピック**</span><span class="sxs-lookup"><span data-stu-id="a7779-114">**Related Topics**</span></span>  
  
 <span data-ttu-id="a7779-115"><xref:System.Windows.Media.SolidColorBrush> の詳細とその他の例については、「[純色およびグラデーションによる塗りつぶしの概要](painting-with-solid-colors-and-gradients-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7779-115">For more information about <xref:System.Windows.Media.SolidColorBrush> and additional examples, see the [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md) overview.</span></span>  
  
 <span data-ttu-id="a7779-116">このコード例は、<xref:System.Windows.Media.SolidColorBrush> クラスのために提供されている大規模な例の一部です。</span><span class="sxs-lookup"><span data-stu-id="a7779-116">This code example is part of a larger example provided for the <xref:System.Windows.Media.SolidColorBrush> class.</span></span> <span data-ttu-id="a7779-117">完全なサンプルについては、「[ブラシのサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a7779-117">For the complete sample, see the [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7779-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="a7779-118">See also</span></span>

- <xref:System.Windows.Media.Brushes>
