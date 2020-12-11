---
title: '方法: 要素の Width プロパティを設定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- width properties [WPF]
- Panel control [WPF], width properties of elements
ms.assetid: 6ee04a9d-63f0-4f5b-a406-0a8cd4c35729
ms.openlocfilehash: fcdb8d58c17137d22edd4ee8cf6768c5d7def7c5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96979987"
---
# <a name="how-to-set-the-width-properties-of-an-element"></a><span data-ttu-id="b7e0a-102">方法: 要素の Width プロパティを設定する</span><span class="sxs-lookup"><span data-stu-id="b7e0a-102">How to: Set the Width Properties of an Element</span></span>
## <a name="example"></a><span data-ttu-id="b7e0a-103">例</span><span class="sxs-lookup"><span data-stu-id="b7e0a-103">Example</span></span>  
 <span data-ttu-id="b7e0a-104">この例は、[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] の 4 つの幅に関連するプロパティ間のレンダリング動作の違いを視覚的に示しています。</span><span class="sxs-lookup"><span data-stu-id="b7e0a-104">This example visually shows the differences in rendering behavior among the four width-related properties in [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)].</span></span>  
  
 <span data-ttu-id="b7e0a-105"><xref:System.Windows.FrameworkElement> クラスでは、要素の幅の特性を記述する 4 つのプロパティが公開されています。</span><span class="sxs-lookup"><span data-stu-id="b7e0a-105">The <xref:System.Windows.FrameworkElement> class exposes four properties that describe the width characteristics of an element.</span></span> <span data-ttu-id="b7e0a-106">これらの 4 つのプロパティは競合する可能性があります。その場合、優先される値は次のように決定されます。<xref:System.Windows.FrameworkElement.MinWidth%2A> 値は <xref:System.Windows.FrameworkElement.MaxWidth%2A> 値より優先され、次に <xref:System.Windows.FrameworkElement.Width%2A> 値より優先されます。</span><span class="sxs-lookup"><span data-stu-id="b7e0a-106">These four properties can conflict, and when they do, the value that takes precedence is determined as follows: the <xref:System.Windows.FrameworkElement.MinWidth%2A> value takes precedence over the <xref:System.Windows.FrameworkElement.MaxWidth%2A> value, which in turn takes precedence over the <xref:System.Windows.FrameworkElement.Width%2A> value.</span></span> <span data-ttu-id="b7e0a-107">4 つ目のプロパティの <xref:System.Windows.FrameworkElement.ActualWidth%2A> は読み取り専用であり、レイアウト プロセスとの相互作用によって決定された実際の幅が報告されます。</span><span class="sxs-lookup"><span data-stu-id="b7e0a-107">A fourth property, <xref:System.Windows.FrameworkElement.ActualWidth%2A>, is read-only, and reports the actual width as determined by interactions with the layout process.</span></span>  
  
 <span data-ttu-id="b7e0a-108">次の [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] の例では、<xref:System.Windows.Shapes.Rectangle> 要素 (`rect1`) を <xref:System.Windows.Controls.Canvas> の子として描画します。</span><span class="sxs-lookup"><span data-stu-id="b7e0a-108">The following [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] examples draw a <xref:System.Windows.Shapes.Rectangle> element (`rect1`) as a child of <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="b7e0a-109"><xref:System.Windows.FrameworkElement.MinWidth%2A>、<xref:System.Windows.FrameworkElement.MaxWidth%2A>、および <xref:System.Windows.FrameworkElement.Width%2A> のプロパティ値を表す一連の <xref:System.Windows.Controls.ListBox> 要素を使用して、<xref:System.Windows.Shapes.Rectangle> の width プロパティを変更できます。</span><span class="sxs-lookup"><span data-stu-id="b7e0a-109">You can change the width properties of a <xref:System.Windows.Shapes.Rectangle> by using a series of <xref:System.Windows.Controls.ListBox> elements that represent the property values of <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.MaxWidth%2A>, and <xref:System.Windows.FrameworkElement.Width%2A>.</span></span> <span data-ttu-id="b7e0a-110">この方法で、各プロパティの優先順位が視覚的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="b7e0a-110">In this manner, the precedence of each property is visually displayed.</span></span>  
  
 [!code-xaml[WidthMinWidthMaxWidth#1](~/samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#1)]  
[!code-xaml[WidthMinWidthMaxWidth#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="b7e0a-111">次のコードビハインドの例では、<xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> イベントによって発生するイベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="b7e0a-111">The following code-behind examples handle the events that the <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event raises.</span></span> <span data-ttu-id="b7e0a-112">各カスタム メソッドは、<xref:System.Windows.Controls.ListBox> から入力を受け取り、値を <xref:System.Double> として解析し、指定された幅に関連するプロパティに値を適用します。</span><span class="sxs-lookup"><span data-stu-id="b7e0a-112">Each custom method takes the input from the <xref:System.Windows.Controls.ListBox>, parses the value as a <xref:System.Double>, and applies the value to the specified width-related property.</span></span> <span data-ttu-id="b7e0a-113">幅の値も文字列に変換され、さまざまな <xref:System.Windows.Controls.TextBlock> 要素に書き込まれます (これらの要素の定義は、選択した XAML には表示されません)。</span><span class="sxs-lookup"><span data-stu-id="b7e0a-113">The width values are also converted to a string and written to various <xref:System.Windows.Controls.TextBlock> elements (definition of those elements is not shown in the selected XAML).</span></span>  
  
 [!code-csharp[WidthMinWidthMaxWidth#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml.cs#3)]
 [!code-vb[WidthMinWidthMaxWidth#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WidthMinWidthMaxWidth/VisualBasic/Window1.xaml.vb#3)]  
  
 <span data-ttu-id="b7e0a-114">サンプル全体については、[Width プロパティの比較のサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Elements/WidthProperties)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7e0a-114">For the complete sample, see [Width Properties Comparison Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Elements/WidthProperties).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7e0a-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="b7e0a-115">See also</span></span>

- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.FrameworkElement.ActualWidth%2A>
- <xref:System.Windows.FrameworkElement.MaxWidth%2A>
- <xref:System.Windows.FrameworkElement.MinWidth%2A>
- <xref:System.Windows.FrameworkElement.Width%2A>
- [<span data-ttu-id="b7e0a-116">パネルの概要</span><span class="sxs-lookup"><span data-stu-id="b7e0a-116">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="b7e0a-117">要素の Height プロパティを設定する</span><span class="sxs-lookup"><span data-stu-id="b7e0a-117">Set the Height Properties of an Element</span></span>](how-to-set-the-height-properties-of-an-element.md)
- [<span data-ttu-id="b7e0a-118">Width プロパティの比較のサンプル</span><span class="sxs-lookup"><span data-stu-id="b7e0a-118">Width Properties Comparison Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Elements/WidthProperties)
