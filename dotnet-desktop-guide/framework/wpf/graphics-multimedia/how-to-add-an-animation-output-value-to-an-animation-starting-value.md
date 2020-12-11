---
title: '方法: アニメーションの出力値をアニメーションの開始値に追加する'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF]
ms.assetid: b89a82be-b03d-481e-a8d3-cc513d09ca00
ms.openlocfilehash: 945675d03a280e2394fdb0eab27c0978dc7cc320
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96979972"
---
# <a name="how-to-add-an-animation-output-value-to-an-animation-starting-value"></a><span data-ttu-id="a518a-102">方法: アニメーションの出力値をアニメーションの開始値に追加する</span><span class="sxs-lookup"><span data-stu-id="a518a-102">How to: Add an Animation Output Value to an Animation Starting Value</span></span>
<span data-ttu-id="a518a-103">この例では、アニメーションの出力値をアニメーションの開始値に追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a518a-103">This example shows how to add an animation output value to an animation starting value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a518a-104">例</span><span class="sxs-lookup"><span data-stu-id="a518a-104">Example</span></span>  
 <span data-ttu-id="a518a-105"><xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> プロパティでは、アニメーションの出力値をアニメーション化されたプロパティの開始値 (基本値) に追加するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="a518a-105">The <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> property specifies whether you want the output value of an animation added to the starting value (base value) of an animated property.</span></span> <span data-ttu-id="a518a-106">ほとんどの基本的なアニメーションと、ほとんどのキー フレーム アニメーションでは、<xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> プロパティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a518a-106">You can use the <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> property with most basic animations and most key frame animations.</span></span> <span data-ttu-id="a518a-107">詳細については、「[アニメーションの概要](animation-overview.md)」と「[キーフレーム アニメーションの概要](key-frame-animations-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a518a-107">For more information, see [Animation Overview](animation-overview.md) and [Key-Frame Animations Overview](key-frame-animations-overview.md).</span></span>  
  
 <span data-ttu-id="a518a-108">次の例では、<xref:System.Windows.Media.Animation.DoubleAnimation> で <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A?displayProperty=nameWithType> プロパティを使用し、<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>で <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsAdditive%2A?displayProperty=nameWithType> プロパティを使用した場合の効果を示しています。</span><span class="sxs-lookup"><span data-stu-id="a518a-108">The following example shows the effect of using the <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A?displayProperty=nameWithType> property with <xref:System.Windows.Media.Animation.DoubleAnimation> and using the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsAdditive%2A?displayProperty=nameWithType> property with <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#IsAdditiveWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsAdditiveExample.xaml#isadditivewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="a518a-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="a518a-109">See also</span></span>

- [<span data-ttu-id="a518a-110">反復サイクル中にアニメーション値を累積する</span><span class="sxs-lookup"><span data-stu-id="a518a-110">Accumulate Animation Values During Repeat Cycles</span></span>](how-to-accumulate-animation-values-during-repeat-cycles.md)
- [<span data-ttu-id="a518a-111">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="a518a-111">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="a518a-112">キー フレーム アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="a518a-112">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="a518a-113">アニメーションおよびタイミングに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="a518a-113">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
