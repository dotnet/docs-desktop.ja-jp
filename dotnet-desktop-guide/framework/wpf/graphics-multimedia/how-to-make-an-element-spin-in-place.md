---
title: '方法: 要素のスピンを設定する'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
ms.openlocfilehash: a1b515822391de08ec8ed8ff0ff1f0086874dc02
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985903"
---
# <a name="how-to-make-an-element-spin-in-place"></a><span data-ttu-id="f6499-102">方法: 要素のスピンを設定する</span><span class="sxs-lookup"><span data-stu-id="f6499-102">How to: Make an Element Spin in Place</span></span>
<span data-ttu-id="f6499-103">この例では、<xref:System.Windows.Media.RotateTransform> と <xref:System.Windows.Media.Animation.DoubleAnimation> を使用して要素をスピンさせる方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f6499-103">This example shows how to make an element spin by using a <xref:System.Windows.Media.RotateTransform> and a <xref:System.Windows.Media.Animation.DoubleAnimation>.</span></span>  
  
 <span data-ttu-id="f6499-104">次の例では、要素の <xref:System.Windows.UIElement.RenderTransform%2A> プロパティに <xref:System.Windows.Media.RotateTransform> を適用します。</span><span class="sxs-lookup"><span data-stu-id="f6499-104">The following example applies the <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span> <span data-ttu-id="f6499-105">この例では、<xref:System.Windows.Media.Animation.DoubleAnimation> を使用して <xref:System.Windows.Media.RotateTransform> の <xref:System.Windows.Media.RotateTransform.Angle%2A> をアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="f6499-105">The example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the <xref:System.Windows.Media.RotateTransform.Angle%2A> of the <xref:System.Windows.Media.RotateTransform>.</span></span> <span data-ttu-id="f6499-106">要素を定位置でスピンさせるために、この例では要素の <xref:System.Windows.UIElement.RenderTransformOrigin%2A> プロパティを点 (0.5, 0.5) に設定しています。</span><span class="sxs-lookup"><span data-stu-id="f6499-106">To make the element spin in place, the example sets the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property of the element to the point (0.5, 0.5).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f6499-107">例</span><span class="sxs-lookup"><span data-stu-id="f6499-107">Example</span></span>  
 [!code-xaml[transformanimations_snip#11](~/samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 <span data-ttu-id="f6499-108">その他の変換の例を含むサンプル全体については、「[2D 変換のサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f6499-108">For the complete sample, which includes more transformation examples, see [2D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6499-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="f6499-109">See also</span></span>

- [<span data-ttu-id="f6499-110">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="f6499-110">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="f6499-111">変換の概要</span><span class="sxs-lookup"><span data-stu-id="f6499-111">Transforms Overview</span></span>](transforms-overview.md)
