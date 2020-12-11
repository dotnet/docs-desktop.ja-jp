---
title: '方法: アニメーションの継続時間を設定する'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], duration
- Timelines [WPF], description
- duration of animations [WPF]
ms.assetid: 155034ef-7d00-4416-a73c-b1713992d2eb
ms.openlocfilehash: bdae1689ffeb8c54d756b9debbd26d57a052892d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985396"
---
# <a name="how-to-set-a-duration-for-an-animation"></a><span data-ttu-id="0eda0-102">方法: アニメーションの継続時間を設定する</span><span class="sxs-lookup"><span data-stu-id="0eda0-102">How to: Set a Duration for an Animation</span></span>
<span data-ttu-id="0eda0-103"><xref:System.Windows.Media.Animation.Timeline> は、時間のセグメントを表し、そのセグメントの長さはタイムラインの <xref:System.Windows.Duration> によって決定されます。</span><span class="sxs-lookup"><span data-stu-id="0eda0-103">A <xref:System.Windows.Media.Animation.Timeline> represents a segment of time and the length of that segment is determined by the timeline's <xref:System.Windows.Duration>.</span></span> <span data-ttu-id="0eda0-104"><xref:System.Windows.Media.Animation.Timeline> は、継続時間の最後に到達すると、再生を停止します。</span><span class="sxs-lookup"><span data-stu-id="0eda0-104">When a <xref:System.Windows.Media.Animation.Timeline> reaches the end of its duration, it stops playing.</span></span> <span data-ttu-id="0eda0-105"><xref:System.Windows.Media.Animation.Timeline> に子タイムラインがある場合は、子も再生を停止します。</span><span class="sxs-lookup"><span data-stu-id="0eda0-105">If the <xref:System.Windows.Media.Animation.Timeline> has child timelines, they stop playing as well.</span></span> <span data-ttu-id="0eda0-106">アニメーションの場合、<xref:System.Windows.Duration> は、アニメーションが開始値から終了値まで切り替わるのに要する時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="0eda0-106">In the case of an animation, the <xref:System.Windows.Duration> specifies how long the animation takes to transition from its starting value to its ending value.</span></span>  
  
 <span data-ttu-id="0eda0-107"><xref:System.Windows.Duration> には、特定の有限の時間、または特殊な値 <xref:System.Windows.Duration.Automatic%2A> または <xref:System.Windows.Duration.Forever%2A> を指定できます。</span><span class="sxs-lookup"><span data-stu-id="0eda0-107">You can specify a <xref:System.Windows.Duration> with a specific, finite time or the special values <xref:System.Windows.Duration.Automatic%2A> or <xref:System.Windows.Duration.Forever%2A>.</span></span> <span data-ttu-id="0eda0-108">アニメーションには常に有限の長さを定義する必要があるため、アニメーションの継続時間は常に時間の値にする必要があります。そうしないと、アニメーションはターゲット値の間の切り替え方法を認識できません。</span><span class="sxs-lookup"><span data-stu-id="0eda0-108">An animation's duration must always be a time value, because an animation must always have a defined, finite length—otherwise, the animation would not know how to transition between its target values.</span></span> <span data-ttu-id="0eda0-109"><xref:System.Windows.Media.Animation.Storyboard> や <xref:System.Windows.Media.Animation.ParallelTimeline> などのコンテナー タイムライン (<xref:System.Windows.Media.Animation.TimelineGroup> オブジェクト) の既定の継続時間は <xref:System.Windows.Duration.Automatic%2A> で、最後の子が再生を停止すると自動的に終了します。</span><span class="sxs-lookup"><span data-stu-id="0eda0-109">Container timelines (<xref:System.Windows.Media.Animation.TimelineGroup> objects), such as <xref:System.Windows.Media.Animation.Storyboard> and <xref:System.Windows.Media.Animation.ParallelTimeline>, have a default duration of <xref:System.Windows.Duration.Automatic%2A>, which means they automatically end when their last child stops playing.</span></span>  
  
 <span data-ttu-id="0eda0-110">次の例では、<xref:System.Windows.Shapes.Rectangle> の幅、高さ、塗りつぶしの色がアニメーション化されています。</span><span class="sxs-lookup"><span data-stu-id="0eda0-110">In the following example, the width, height and fill color of a <xref:System.Windows.Shapes.Rectangle> is animated.</span></span> <span data-ttu-id="0eda0-111">継続時間はアニメーションとコンテナーのタイムラインに設定されるため、アニメーションの認識速度の制御や、コンテナー タイムラインの継続時間が設定された子タイムラインの継続時間のオーバーライドなどのアニメーション効果に影響します。</span><span class="sxs-lookup"><span data-stu-id="0eda0-111">Durations are set on animation and container timelines resulting in animation effects including controlling the perceived speed of an animation and overriding the duration of child timelines with the duration of a container timeline.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0eda0-112">例</span><span class="sxs-lookup"><span data-stu-id="0eda0-112">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#DurationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/DurationExample.xaml#durationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="0eda0-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="0eda0-113">See also</span></span>

- <xref:System.Windows.Duration>
- [<span data-ttu-id="0eda0-114">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="0eda0-114">Animation Overview</span></span>](animation-overview.md)
