---
title: '方法: BorderThickness 値をアニメーション化する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- border thickness [WPF], animating changes to
- animation [WPF], changes to border thickness
ms.assetid: fd021978-f74b-4e7b-a7f7-3987dcad9e0f
ms.openlocfilehash: 4533ce6f2a1fe7243267ee8d638e2ad0a4f9cf3a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985708"
---
# <a name="how-to-animate-a-borderthickness-value"></a><span data-ttu-id="879f0-102">方法: BorderThickness 値をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="879f0-102">How to: Animate a BorderThickness Value</span></span>
<span data-ttu-id="879f0-103">この例は、<xref:System.Windows.Media.Animation.ThicknessAnimation> クラスを使用して境界線の太さの変更をアニメーション化する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="879f0-103">This example shows how to animate changes to the thickness of a border by using the <xref:System.Windows.Media.Animation.ThicknessAnimation> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="879f0-104">例</span><span class="sxs-lookup"><span data-stu-id="879f0-104">Example</span></span>  
 <span data-ttu-id="879f0-105"><xref:System.Windows.Media.Animation.ThicknessAnimation> を使用して境界線の太さをアニメーション化する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="879f0-105">The following example animates the thickness of a border by using <xref:System.Windows.Media.Animation.ThicknessAnimation>.</span></span> <span data-ttu-id="879f0-106">この例では、<xref:System.Windows.Controls.Border> の <xref:System.Windows.Controls.Border.BorderThickness%2A> プロパティを使用しています。</span><span class="sxs-lookup"><span data-stu-id="879f0-106">The example uses the <xref:System.Windows.Controls.Border.BorderThickness%2A> property of <xref:System.Windows.Controls.Border>.</span></span>  
  
 [!code-csharp[BasicAnimations_snip#ThicknessAnimationWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/ThicknessAnimationExample.cs#thicknessanimationwholepage)]
 [!code-vb[BasicAnimations_snip#ThicknessAnimationWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/ThicknessAnimationExample.vb#thicknessanimationwholepage)]  
  
 <span data-ttu-id="879f0-107">サンプル全体については、[アニメーション サンプル ギャラリー](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="879f0-107">For the complete sample, see [Animation Example Gallery](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="879f0-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="879f0-108">See also</span></span>

- <xref:System.Windows.Media.Animation.ThicknessAnimation>
- <xref:System.Windows.Controls.Border.BorderThickness%2A>
- <xref:System.Windows.Controls.Border>
- [<span data-ttu-id="879f0-109">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="879f0-109">Animation Overview</span></span>](../graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="879f0-110">アニメーションおよびタイミングに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="879f0-110">Animation and Timing How-to Topics</span></span>](../graphics-multimedia/animation-and-timing-how-to-topics.md)
- [<span data-ttu-id="879f0-111">キー フレームを使用して境界線の太さをアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="879f0-111">Animate the Thickness of a Border by Using Key Frames</span></span>](../graphics-multimedia/how-to-animate-the-thickness-of-a-border-by-using-key-frames.md)
