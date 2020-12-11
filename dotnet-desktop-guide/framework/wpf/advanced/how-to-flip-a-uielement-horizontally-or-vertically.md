---
title: '方法: UIElement を左右または上下に反転させる'
ms.date: 03/30/2017
helpviewer_keywords:
- flipping UIElements [WPF]
- UIElements [WPF], flipping
ms.assetid: 02c6730f-65c0-40d5-a553-4cb663721882
ms.openlocfilehash: 6b3da322493d17e4f8e36a35b9a0e40fdc9dc685
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984659"
---
# <a name="how-to-flip-a-uielement-horizontally-or-vertically"></a><span data-ttu-id="340cf-102">方法: UIElement を左右または上下に反転させる</span><span class="sxs-lookup"><span data-stu-id="340cf-102">How to: Flip a UIElement Horizontally or Vertically</span></span>
<span data-ttu-id="340cf-103">この例からは、<xref:System.Windows.Media.ScaleTransform> を使用し、<xref:System.Windows.UIElement> を左右または上下に反転させる方法がわかります。</span><span class="sxs-lookup"><span data-stu-id="340cf-103">This example shows how to use a <xref:System.Windows.Media.ScaleTransform> to flip a <xref:System.Windows.UIElement> horizontally or vertically.</span></span> <span data-ttu-id="340cf-104">この例では、<xref:System.Windows.Media.ScaleTransform> をその <xref:System.Windows.UIElement.RenderTransform%2A> プロパティに適用することで <xref:System.Windows.Controls.Button> コントロール (<xref:System.Windows.UIElement> 型) が反転します。</span><span class="sxs-lookup"><span data-stu-id="340cf-104">In this example, a <xref:System.Windows.Controls.Button> control (a type of <xref:System.Windows.UIElement>) is flipped by applying a <xref:System.Windows.Media.ScaleTransform> to its <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="340cf-105">例</span><span class="sxs-lookup"><span data-stu-id="340cf-105">Example</span></span>  
 <span data-ttu-id="340cf-106">反転するボタンを以下で図解します。</span><span class="sxs-lookup"><span data-stu-id="340cf-106">The following illustration shows the button to flip.</span></span>  
  
 <span data-ttu-id="340cf-107">![変換のないボタン](./media/graphicsmm-buttonflipbeforeflip.gif "graphicsmm_buttonflipbeforeflip")</span><span class="sxs-lookup"><span data-stu-id="340cf-107">![A button with no transform](./media/graphicsmm-buttonflipbeforeflip.gif "graphicsmm_buttonflipbeforeflip")</span></span>  
<span data-ttu-id="340cf-108">反転する UIElement</span><span class="sxs-lookup"><span data-stu-id="340cf-108">The UIElement to flip</span></span>  
  
 <span data-ttu-id="340cf-109">次のコードではボタンが作成されます。</span><span class="sxs-lookup"><span data-stu-id="340cf-109">The following shows the code that creates the button.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMButtonWithoutFlip](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmbuttonwithoutflip)]  
  
## <a name="example"></a><span data-ttu-id="340cf-110">例</span><span class="sxs-lookup"><span data-stu-id="340cf-110">Example</span></span>  
 <span data-ttu-id="340cf-111">ボタンを左右に反転させるには、<xref:System.Windows.Media.ScaleTransform> を作成し、その <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> プロパティを -1 に設定します。</span><span class="sxs-lookup"><span data-stu-id="340cf-111">To flip the button horizontally, create a <xref:System.Windows.Media.ScaleTransform> and set its <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> property to -1.</span></span> <span data-ttu-id="340cf-112">ボタンの <xref:System.Windows.UIElement.RenderTransform%2A> プロパティに <xref:System.Windows.Media.ScaleTransform> を適用します。</span><span class="sxs-lookup"><span data-stu-id="340cf-112">Apply the <xref:System.Windows.Media.ScaleTransform> to the button's <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample1)]  
  
 <span data-ttu-id="340cf-113">![&#40;0, 0&#41;について水平方向に反転したボタン ](./media/graphicsmm-buttonfliphorizontalflip-displaced.gif "graphicsmm_buttonfliphorizontalflip_displaced")</span><span class="sxs-lookup"><span data-stu-id="340cf-113">![A button flipped horizontally about &#40;0,0&#41;](./media/graphicsmm-buttonfliphorizontalflip-displaced.gif "graphicsmm_buttonfliphorizontalflip_displaced")</span></span>  
<span data-ttu-id="340cf-114">ScaleTransform 適用後のボタン</span><span class="sxs-lookup"><span data-stu-id="340cf-114">The button after applying the ScaleTransform</span></span>  
  
## <a name="example"></a><span data-ttu-id="340cf-115">例</span><span class="sxs-lookup"><span data-stu-id="340cf-115">Example</span></span>  
 <span data-ttu-id="340cf-116">上の画像からわかるように、反転したボタンは移動もしています。</span><span class="sxs-lookup"><span data-stu-id="340cf-116">As you can see from the previous illustration, the button was flipped, but it was also moved.</span></span> <span data-ttu-id="340cf-117">これはボタンがその左上隅から反転されたためです。</span><span class="sxs-lookup"><span data-stu-id="340cf-117">That's because the button was flipped from its top left corner.</span></span> <span data-ttu-id="340cf-118">ボタンを定位置で反転させるには、<xref:System.Windows.Media.ScaleTransform> をその隅ではなくその中心に適用します。</span><span class="sxs-lookup"><span data-stu-id="340cf-118">To flip the button in place, you want to apply the <xref:System.Windows.Media.ScaleTransform> to its center, not its corner.</span></span> <span data-ttu-id="340cf-119"><xref:System.Windows.Media.ScaleTransform> をボタンの中心に適用する簡単な方法は、ボタンの <xref:System.Windows.UIElement.RenderTransformOrigin%2A> プロパティを 0.5, 0.5 に設定することです。</span><span class="sxs-lookup"><span data-stu-id="340cf-119">An easy way to apply the <xref:System.Windows.Media.ScaleTransform> to the buttons center is to set the button's <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property to 0.5, 0.5.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample2)]  
  
 <span data-ttu-id="340cf-120">![中心の周りで水平方向に反転されるボタン](./media/graphicsmm-buttonfliphorizontalflip-inplace.gif "graphicsmm_buttonfliphorizontalflip_inplace")</span><span class="sxs-lookup"><span data-stu-id="340cf-120">![A button flipped horizontally about its center](./media/graphicsmm-buttonfliphorizontalflip-inplace.gif "graphicsmm_buttonfliphorizontalflip_inplace")</span></span>  
<span data-ttu-id="340cf-121">RenderTransformOrigin が 0.5, 0.5 のボタン</span><span class="sxs-lookup"><span data-stu-id="340cf-121">The button with a RenderTransformOrigin of 0.5, 0.5</span></span>  
  
## <a name="example"></a><span data-ttu-id="340cf-122">例</span><span class="sxs-lookup"><span data-stu-id="340cf-122">Example</span></span>  
 <span data-ttu-id="340cf-123">ボタンを上下に反転させるには、<xref:System.Windows.Media.ScaleTransform> オブジェクトの <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> プロパティをその <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> プロパティの代わりに設定します。</span><span class="sxs-lookup"><span data-stu-id="340cf-123">To flip the button vertically, set the <xref:System.Windows.Media.ScaleTransform> object's <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> property instead of its <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> property.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMVerticalFlipButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmverticalflipbuttonexample2)]  
  
 <span data-ttu-id="340cf-124">![中心の周りで垂直方向に反転されるボタン](./media/graphicsmm-buttonflipverticalflip-inplace.gif "graphicsmm_buttonflipverticalflip_inplace")</span><span class="sxs-lookup"><span data-stu-id="340cf-124">![A button flipped vertically about its center](./media/graphicsmm-buttonflipverticalflip-inplace.gif "graphicsmm_buttonflipverticalflip_inplace")</span></span>  
<span data-ttu-id="340cf-125">上下に反転したボタン</span><span class="sxs-lookup"><span data-stu-id="340cf-125">The vertically flipped button</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="340cf-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="340cf-126">See also</span></span>

- [<span data-ttu-id="340cf-127">変換の概要</span><span class="sxs-lookup"><span data-stu-id="340cf-127">Transforms Overview</span></span>](../graphics-multimedia/transforms-overview.md)
