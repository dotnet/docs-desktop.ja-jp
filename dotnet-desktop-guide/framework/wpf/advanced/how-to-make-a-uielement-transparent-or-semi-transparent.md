---
title: '方法: UIElement を透明または半透明にする'
ms.date: 03/30/2017
helpviewer_keywords:
- UIElements [WPF], transparency
- opacity [WPF], of UIElements
- transparency of UIElements [WPF]
- UIElements [WPF], opacity
ms.assetid: a49fc8d6-7b32-4f28-9122-39b632a19b4b
ms.openlocfilehash: 1de9a7e11fee241ecb71242e9808e77b7e5e63b0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982080"
---
# <a name="how-to-make-a-uielement-transparent-or-semi-transparent"></a><span data-ttu-id="7f93e-102">方法: UIElement を透明または半透明にする</span><span class="sxs-lookup"><span data-stu-id="7f93e-102">How to: Make a UIElement Transparent or Semi-Transparent</span></span>
<span data-ttu-id="7f93e-103">この例では、<xref:System.Windows.UIElement> を透明または半透明にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7f93e-103">This example shows how to make a <xref:System.Windows.UIElement> transparent or semi-transparent.</span></span> <span data-ttu-id="7f93e-104">要素を透明または半透明にするには、その <xref:System.Windows.UIElement.Opacity%2A> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="7f93e-104">To make an element transparent or semi-transparent, you set its <xref:System.Windows.UIElement.Opacity%2A> property.</span></span> <span data-ttu-id="7f93e-105">値に `0.0` を指定すると要素は完全に透明になり、値に `1.0` を指定すると要素は完全に不透明になります。</span><span class="sxs-lookup"><span data-stu-id="7f93e-105">A value of `0.0` makes the element completely transparent, while a value of `1.0` makes the element completely opaque.</span></span> <span data-ttu-id="7f93e-106">値に `0.5` を指定すると、要素の不透明度は 50% などになります。</span><span class="sxs-lookup"><span data-stu-id="7f93e-106">A value of `0.5` makes the element 50% opaque, and so on.</span></span> <span data-ttu-id="7f93e-107">要素の <xref:System.Windows.UIElement.Opacity%2A> は、既定で `1.0` に設定されています。</span><span class="sxs-lookup"><span data-stu-id="7f93e-107">An element's <xref:System.Windows.UIElement.Opacity%2A> is set to `1.0` by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f93e-108">例</span><span class="sxs-lookup"><span data-stu-id="7f93e-108">Example</span></span>  
 <span data-ttu-id="7f93e-109">次の例では、ボタンの <xref:System.Windows.UIElement.Opacity%2A> を `0.25` に設定し、それとそのコンテンツ (この場合はボタンのテキスト) を 25% 不透明にします。</span><span class="sxs-lookup"><span data-stu-id="7f93e-109">The following example sets the <xref:System.Windows.UIElement.Opacity%2A> of a button to `0.25`, making it and its contents (in this case, the button's text) 25% opaque.</span></span>  
  
 [!code-xaml[brushsamples_snip#2](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#2)]  
  
 [!code-csharp[brushsamples_procedural_snip#2](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#2)]  
  
 <span data-ttu-id="7f93e-110">要素のコンテンツに独自の <xref:System.Windows.UIElement.Opacity%2A> 設定がある場合、それらの値は、含まれる要素 <xref:System.Windows.UIElement.Opacity%2A> に乗算されます。</span><span class="sxs-lookup"><span data-stu-id="7f93e-110">If an element's contents have their own <xref:System.Windows.UIElement.Opacity%2A> settings, those values are multiplied against the containing elements <xref:System.Windows.UIElement.Opacity%2A>.</span></span>  
  
 <span data-ttu-id="7f93e-111">次の例では、ボタンの <xref:System.Windows.UIElement.Opacity%2A> を `0.25` に設定し、ボタンに含まれる <xref:System.Windows.Controls.Image> コントロールの <xref:System.Windows.UIElement.Opacity%2A> を `0.5` に設定します。</span><span class="sxs-lookup"><span data-stu-id="7f93e-111">The following example sets a button's <xref:System.Windows.UIElement.Opacity%2A> to `0.25`, and the <xref:System.Windows.UIElement.Opacity%2A> of an <xref:System.Windows.Controls.Image> control contained with in the button to `0.5`.</span></span> <span data-ttu-id="7f93e-112">その結果、イメージは次に従って 12.5% 不透明になります。0.25 \* 0.5 = 0.125。</span><span class="sxs-lookup"><span data-stu-id="7f93e-112">As a result, the image appears 12.5% opaque: 0.25 \* 0.5 = 0.125.</span></span>  
  
 [!code-xaml[brushsamples_snip#3](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#3)]  
  
 [!code-csharp[brushsamples_procedural_snip#3](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#3)]  
  
 <span data-ttu-id="7f93e-113">要素の不透明度を制御するもう 1 つの方法は、要素を塗りつぶす <xref:System.Windows.Media.Brush> の不透明度を設定する方法です。</span><span class="sxs-lookup"><span data-stu-id="7f93e-113">Another way to control the opacity of an element is to set the opacity of the <xref:System.Windows.Media.Brush> that paints the element.</span></span> <span data-ttu-id="7f93e-114">この方法により、要素の一部を選択的に不透明に変更でき、要素の <xref:System.Windows.UIElement.Opacity%2A> プロパティを使用するよりもパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="7f93e-114">This approach enables you to selectively alter the opacity of portions of an element, and provides performance benefits over using the element's <xref:System.Windows.UIElement.Opacity%2A> property.</span></span> <span data-ttu-id="7f93e-115">次の例では、ボタンの <xref:System.Windows.Controls.Control.Background%2A> の塗りつぶしに使用される <xref:System.Windows.Media.SolidColorBrush> の <xref:System.Windows.Media.Brush.Opacity%2A> を `0.25` に設定します。</span><span class="sxs-lookup"><span data-stu-id="7f93e-115">The following example sets the <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush> used to paint the button's <xref:System.Windows.Controls.Control.Background%2A> is set to `0.25`.</span></span> <span data-ttu-id="7f93e-116">その結果、このブラシの背景は 25% 不透明になりますが、そのコンテンツ (ボタンのテキスト) は、100% 不透明のままです。</span><span class="sxs-lookup"><span data-stu-id="7f93e-116">As a result, the brush's background is 25% opaque, but its contents (the button's text) remain 100% opaque.</span></span>  
  
 [!code-xaml[brushsamples_snip#4](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#4)]  
  
 [!code-csharp[brushsamples_procedural_snip#4](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#4)]  
  
 <span data-ttu-id="7f93e-117">また、ブラシ内の個々の色の不透明度を制御することもできます。</span><span class="sxs-lookup"><span data-stu-id="7f93e-117">You may also control the opacity of individual colors within a brush.</span></span> <span data-ttu-id="7f93e-118">色とブラシの詳細については、「[単色とグラデーションによる塗りつぶしの概要](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f93e-118">For more information about colors and brushes, see [Painting with Solid Colors and Gradients Overview](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span></span> <span data-ttu-id="7f93e-119">要素の不透明度をアニメーション化する方法の例については、「[要素またはブラシの不透明度をアニメーション化する](../graphics-multimedia/how-to-animate-the-opacity-of-an-element-or-brush.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f93e-119">For an example showing how to animate an element's opacity, see [Animate the Opacity of an Element or Brush](../graphics-multimedia/how-to-animate-the-opacity-of-an-element-or-brush.md).</span></span>
