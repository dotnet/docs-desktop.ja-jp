---
title: '方法: アクティブな期間の末尾に到達したタイムラインの FillBehavior を指定する'
ms.date: 03/30/2017
helpviewer_keywords:
- FillBehavior property for inactive timelines [WPF]
- Timelines [WPF], FillBehavior property
ms.assetid: db805f59-d513-4dac-af15-47005dae3199
ms.openlocfilehash: 1f54f2c1bb49bb7a0301f112a109194ab1a8658e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983207"
---
# <a name="how-to-specify-the-fillbehavior-for-a-timeline-that-has-reached-the-end-of-its-active-period"></a><span data-ttu-id="2ce8b-102">方法: アクティブな期間の末尾に到達したタイムラインの FillBehavior を指定する</span><span class="sxs-lookup"><span data-stu-id="2ce8b-102">How to: Specify the FillBehavior for a Timeline that has Reached the End of Its Active Period</span></span>
<span data-ttu-id="2ce8b-103">この例では、アニメーション化対象のプロパティの非アクティブな <xref:System.Windows.Media.Animation.Timeline> の <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> を指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2ce8b-103">This example shows how to specify the <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> for the inactive <xref:System.Windows.Media.Animation.Timeline> of an animated property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ce8b-104">例</span><span class="sxs-lookup"><span data-stu-id="2ce8b-104">Example</span></span>  
 <span data-ttu-id="2ce8b-105"><xref:System.Windows.Media.Animation.Timeline> の <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> プロパティは、アニメーション化対象のプロパティの値がアニメーション化されていないとき、つまり、<xref:System.Windows.Media.Animation.Timeline> は非アクティブであるが、その親 <xref:System.Windows.Media.Animation.Timeline> がアクティブな期間つまり保持期間内のときに、その値がどのように処理されるかを決定します。</span><span class="sxs-lookup"><span data-stu-id="2ce8b-105">The <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> determines what happens to the value of an animated property when it is not being animated, that is, when the <xref:System.Windows.Media.Animation.Timeline> is inactive but its parent <xref:System.Windows.Media.Animation.Timeline> is inside its active or hold period.</span></span> <span data-ttu-id="2ce8b-106">たとえば、アニメーション化対象のプロパティが、アニメーションの終了後にその終了値のままになるか、アニメーションが開始される前の値に戻るかなどです。</span><span class="sxs-lookup"><span data-stu-id="2ce8b-106">For example, does an animated property remain at its end value after the animation ends or does it revert back to the value it had before the animation started?</span></span>  
  
 <span data-ttu-id="2ce8b-107">次の例では、<xref:System.Windows.Media.Animation.DoubleAnimation> を使用して、2 つの四角形の <xref:System.Windows.FrameworkElement.Width%2A> をアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="2ce8b-107">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the <xref:System.Windows.FrameworkElement.Width%2A> of two rectangles.</span></span> <span data-ttu-id="2ce8b-108">それぞれの四角形は、別個の <xref:System.Windows.Media.Animation.Timeline> オブジェクトを使用します。</span><span class="sxs-lookup"><span data-stu-id="2ce8b-108">Each rectangle uses a different <xref:System.Windows.Media.Animation.Timeline> object.</span></span>  
  
 <span data-ttu-id="2ce8b-109">一方の <xref:System.Windows.Media.Animation.Timeline> の <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> は <xref:System.Windows.Media.Animation.FillBehavior.Stop> に設定されています。これにより、<xref:System.Windows.Media.Animation.Timeline> の終了時に四角形の幅がアニメーション化されていない値に戻ります。</span><span class="sxs-lookup"><span data-stu-id="2ce8b-109">One <xref:System.Windows.Media.Animation.Timeline> has a <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> that is set to <xref:System.Windows.Media.Animation.FillBehavior.Stop>, which causes the width of the rectangle to revert back to its non-animated value when the <xref:System.Windows.Media.Animation.Timeline> ends.</span></span> <span data-ttu-id="2ce8b-110">もう一方の <xref:System.Windows.Media.Animation.Timeline> の <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> は <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd> であり、<xref:System.Windows.Media.Animation.Timeline> の終了時に幅が終了値のままになります。</span><span class="sxs-lookup"><span data-stu-id="2ce8b-110">The other <xref:System.Windows.Media.Animation.Timeline> has a <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> of <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, which causes the width to remain at its end value when the <xref:System.Windows.Media.Animation.Timeline> ends.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#FillBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/FillBehaviorExample.xaml#fillbehaviorwholepage)]  
  
 <span data-ttu-id="2ce8b-111">サンプル全体については、「[アニメーション サンプル ギャラリー](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2ce8b-111">For the complete sample, see [Animation Example Gallery](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ce8b-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ce8b-112">See also</span></span>

- <xref:System.Windows.Media.Animation.DoubleAnimation>
- <xref:System.Windows.FrameworkElement.Width%2A>
- <xref:System.Windows.Media.Animation.Timeline>
- <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>
- <xref:System.Windows.Media.Animation.FillBehavior.Stop>
- <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>
- [<span data-ttu-id="2ce8b-113">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="2ce8b-113">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="2ce8b-114">アニメーションおよびタイミングに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="2ce8b-114">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
