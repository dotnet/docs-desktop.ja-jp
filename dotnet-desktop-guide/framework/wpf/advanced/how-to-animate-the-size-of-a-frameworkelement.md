---
title: '方法: FrameworkElement のサイズをアニメーション化する'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], FrameworkElement size
- FrameworkElement [WPF], animating size of
ms.assetid: d4cd5a13-c20d-4a6f-a2ba-14f2c9ce4cef
ms.openlocfilehash: d1995deec5ab2c9bf405911af43b4d242d599119
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982300"
---
# <a name="how-to-animate-the-size-of-a-frameworkelement"></a><span data-ttu-id="3b3fc-102">方法: FrameworkElement のサイズをアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="3b3fc-102">How to: Animate the Size of a FrameworkElement</span></span>
<span data-ttu-id="3b3fc-103"><xref:System.Windows.FrameworkElement> のサイズをアニメーション化するには、その <xref:System.Windows.FrameworkElement.Width%2A> プロパティと <xref:System.Windows.FrameworkElement.Height%2A> プロパティをアニメーション化するか、またはアニメーション化された <xref:System.Windows.Media.ScaleTransform> を使用します。</span><span class="sxs-lookup"><span data-stu-id="3b3fc-103">To animate the size of a <xref:System.Windows.FrameworkElement>, you can either animate its <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties or use an animated <xref:System.Windows.Media.ScaleTransform>.</span></span>  
  
 <span data-ttu-id="3b3fc-104">次の例では、2 つの方法を使用して、2 つのボタンのサイズがアニメーション化されています。</span><span class="sxs-lookup"><span data-stu-id="3b3fc-104">In the following example animates the size of two buttons using these two approaches.</span></span> <span data-ttu-id="3b3fc-105">1 つのボタンはその <xref:System.Windows.FrameworkElement.Width%2A> プロパティをアニメーション化してサイズ変更し、もう 1 つは、その <xref:System.Windows.UIElement.RenderTransform%2A> プロパティに適用された <xref:System.Windows.Media.ScaleTransform> をアニメーション化してサイズ変更しています。</span><span class="sxs-lookup"><span data-stu-id="3b3fc-105">One button is resized by animating its <xref:System.Windows.FrameworkElement.Width%2A> property and another is resized by animating a <xref:System.Windows.Media.ScaleTransform> applied to its <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span> <span data-ttu-id="3b3fc-106">各ボタンには、テキストがいくつか含まれます。</span><span class="sxs-lookup"><span data-stu-id="3b3fc-106">Each button contains some text.</span></span> <span data-ttu-id="3b3fc-107">初期状態では、両ボタンのテキストは同じに表示されますが、ボタンのサイズが変更されると、2 番目のボタンのテキストはゆがんで表示されます。</span><span class="sxs-lookup"><span data-stu-id="3b3fc-107">Initially, the text appears the same in both buttons, but as the buttons are resized, the text in the second button becomes distorted.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b3fc-108">例</span><span class="sxs-lookup"><span data-stu-id="3b3fc-108">Example</span></span>  
 [!code-xaml[transformanimations_snip#1](~/samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/AnimatingSizeExample.xaml#1)]  
  
 <span data-ttu-id="3b3fc-109">要素を変換すると、その要素全体とそのコンテンツが変換されます。</span><span class="sxs-lookup"><span data-stu-id="3b3fc-109">When you transform an element, the entire element and its contents are transformed.</span></span> <span data-ttu-id="3b3fc-110">最初のボタンの場合のように、要素のサイズが直接変更されると、親要素のサイズにそのサイズと位置が依存していない限り、要素のコンテンツのサイズは変更されません。</span><span class="sxs-lookup"><span data-stu-id="3b3fc-110">When you directly alter the size of an element, as in the case of the first button, the element's contents are not resized unless their size and position depend on the size of their parent element.</span></span>  
  
 <span data-ttu-id="3b3fc-111">要素の <xref:System.Windows.UIElement.RenderTransform%2A> プロパティにアニメーション化された変換を適用してサイズをアニメーション化する場合、<xref:System.Windows.UIElement.RenderTransform%2A> プロパティはレイアウト パスをトリガーしないため、<xref:System.Windows.FrameworkElement.Width%2A> と <xref:System.Windows.FrameworkElement.Height%2A> を直接アニメーション化する場合よりもパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="3b3fc-111">Animating the size of an element by applying an animated transform to its <xref:System.Windows.UIElement.RenderTransform%2A> property provides better performance than animated its <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> directly, because the <xref:System.Windows.UIElement.RenderTransform%2A> property does not trigger a layout pass.</span></span>  
  
 <span data-ttu-id="3b3fc-112">プロパティのアニメーション化の詳細については、「[アニメーションの概要](../graphics-multimedia/animation-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b3fc-112">For more information about animating properties, see the [Animation Overview](../graphics-multimedia/animation-overview.md).</span></span> <span data-ttu-id="3b3fc-113">変換の詳細については「[変換の概要](../graphics-multimedia/transforms-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b3fc-113">For more information about transforms, see the [Transforms Overview](../graphics-multimedia/transforms-overview.md).</span></span>
