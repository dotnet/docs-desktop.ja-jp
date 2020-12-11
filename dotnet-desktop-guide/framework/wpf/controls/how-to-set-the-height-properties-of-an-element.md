---
title: '方法: 要素の Height プロパティを設定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- height properties [WPF]
- Panel control [WPF], height properties of elements
ms.assetid: 5ab9e781-dbb8-469a-a3c8-cf38ce312647
ms.openlocfilehash: f18612d66c477562eb387b76ea30e71dd5f4e8d7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985328"
---
# <a name="how-to-set-the-height-properties-of-an-element"></a><span data-ttu-id="bd784-102">方法: 要素の Height プロパティを設定する</span><span class="sxs-lookup"><span data-stu-id="bd784-102">How to: Set the Height Properties of an Element</span></span>
## <a name="example"></a><span data-ttu-id="bd784-103">例</span><span class="sxs-lookup"><span data-stu-id="bd784-103">Example</span></span>  
 <span data-ttu-id="bd784-104">この例は、[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] の 4 つの高さに関連するプロパティ間のレンダリング動作の違いを視覚的に示しています。</span><span class="sxs-lookup"><span data-stu-id="bd784-104">This example visually shows the differences in rendering behavior among the four height-related properties in [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)].</span></span>  
  
 <span data-ttu-id="bd784-105"><xref:System.Windows.FrameworkElement> クラスでは、要素の高さの特性を記述する 4 つのプロパティが公開されています。</span><span class="sxs-lookup"><span data-stu-id="bd784-105">The <xref:System.Windows.FrameworkElement> class exposes four properties that describe the height characteristics of an element.</span></span> <span data-ttu-id="bd784-106">これらの 4 つのプロパティは競合する可能性があります。その場合、優先される値は次のように決定されます。<xref:System.Windows.FrameworkElement.MinHeight%2A> 値は <xref:System.Windows.FrameworkElement.MaxHeight%2A> 値より優先され、次に <xref:System.Windows.FrameworkElement.Height%2A> 値より優先されます。</span><span class="sxs-lookup"><span data-stu-id="bd784-106">These four properties can conflict, and when they do, the value that takes precedence is determined as follows: the <xref:System.Windows.FrameworkElement.MinHeight%2A> value takes precedence over the <xref:System.Windows.FrameworkElement.MaxHeight%2A> value, which in turn takes precedence over the <xref:System.Windows.FrameworkElement.Height%2A> value.</span></span> <span data-ttu-id="bd784-107">4 つ目のプロパティの <xref:System.Windows.FrameworkElement.ActualHeight%2A> は読み取り専用であり、レイアウト プロセスとの相互作用によって決定された実際の高さが報告されます。</span><span class="sxs-lookup"><span data-stu-id="bd784-107">A fourth property, <xref:System.Windows.FrameworkElement.ActualHeight%2A>, is read-only, and reports the actual height as determined by interactions with the layout process.</span></span>  
  
 <span data-ttu-id="bd784-108">次の [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] の例では、<xref:System.Windows.Shapes.Rectangle> 要素 (`rect1`) を <xref:System.Windows.Controls.Canvas> の子として描画します。</span><span class="sxs-lookup"><span data-stu-id="bd784-108">The following [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] examples draw a <xref:System.Windows.Shapes.Rectangle> element (`rect1`) as a child of <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="bd784-109"><xref:System.Windows.FrameworkElement.MinHeight%2A>、<xref:System.Windows.FrameworkElement.MaxHeight%2A>、および <xref:System.Windows.FrameworkElement.Height%2A> のプロパティ値を表す一連の <xref:System.Windows.Controls.ListBox> 要素を使用して、<xref:System.Windows.Shapes.Rectangle> の height プロパティを変更できます。</span><span class="sxs-lookup"><span data-stu-id="bd784-109">You can change the height properties of a <xref:System.Windows.Shapes.Rectangle> by using a series of <xref:System.Windows.Controls.ListBox> elements that represent the property values of <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, and <xref:System.Windows.FrameworkElement.Height%2A>.</span></span> <span data-ttu-id="bd784-110">この方法で、各プロパティの優先順位が視覚的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd784-110">In this manner, the precedence of each property is visually displayed.</span></span>  
  
 [!code-xaml[HeightMinHeightMaxHeight#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#1)]  
[!code-xaml[HeightMinHeightMaxHeight#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="bd784-111">次のコードビハインドの例では、<xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> イベントによって発生するイベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="bd784-111">The following code-behind examples handle the events that the <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event raises.</span></span> <span data-ttu-id="bd784-112">各ハンドラーは、<xref:System.Windows.Controls.ListBox> から入力を受け取り、値を <xref:System.Double> として解析し、指定された高さに関連するプロパティに値を適用します。</span><span class="sxs-lookup"><span data-stu-id="bd784-112">Each handler takes the input from the <xref:System.Windows.Controls.ListBox>, parses the value as a <xref:System.Double>, and applies the value to the specified height-related property.</span></span> <span data-ttu-id="bd784-113">高さの値も文字列に変換され、さまざまな <xref:System.Windows.Controls.TextBlock> 要素に書き込まれます (これらの要素の定義は、選択した XAML には表示されません)。</span><span class="sxs-lookup"><span data-stu-id="bd784-113">The height values are also converted to a string and written to various <xref:System.Windows.Controls.TextBlock> elements (definition of those elements is not shown in the selected XAML).</span></span>  
  
 [!code-csharp[HeightMinHeightMaxHeight#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml.cs#3)]
 [!code-vb[HeightMinHeightMaxHeight#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HeightMinHeightMaxHeight/VisualBasic/Window1.xaml.vb#3)]  
  
 <span data-ttu-id="bd784-114">サンプル全体については、[Height プロパティのサンプル](https://github.com/microsoft/WPF-Samples/tree/master/Elements/HeightProperties)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd784-114">For the complete sample, see [Height Properties Sample](https://github.com/microsoft/WPF-Samples/tree/master/Elements/HeightProperties).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd784-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="bd784-115">See also</span></span>

- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement.ActualHeight%2A>
- <xref:System.Windows.FrameworkElement.MaxHeight%2A>
- <xref:System.Windows.FrameworkElement.MinHeight%2A>
- <xref:System.Windows.FrameworkElement.Height%2A>
- [<span data-ttu-id="bd784-116">要素の Width プロパティを設定する</span><span class="sxs-lookup"><span data-stu-id="bd784-116">Set the Width Properties of an Element</span></span>](how-to-set-the-width-properties-of-an-element.md)
- [<span data-ttu-id="bd784-117">パネルの概要</span><span class="sxs-lookup"><span data-stu-id="bd784-117">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="bd784-118">Height プロパティのサンプル</span><span class="sxs-lookup"><span data-stu-id="bd784-118">Height Properties Sample</span></span>](https://github.com/microsoft/WPF-Samples/tree/master/Elements/HeightProperties)
