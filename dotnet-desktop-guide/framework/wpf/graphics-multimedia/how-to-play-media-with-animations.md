---
title: '方法: アニメーションを使用してメディアを再生する'
ms.date: 03/30/2017
helpviewer_keywords:
- multimedia [WPF], playback with animations
- playback of media [WPF], with animations
- animation [WPF], media playback with
- media [WPF], playback with animations
ms.assetid: 8982b7b7-1c6c-4b24-8801-b328862975f5
ms.openlocfilehash: 200f9d62c67a02088fe5a5789cdb41a04837d430
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96979915"
---
# <a name="how-to-play-media-with-animations"></a><span data-ttu-id="6388c-102">方法: アニメーションを使用してメディアを再生する</span><span class="sxs-lookup"><span data-stu-id="6388c-102">How to: Play Media with Animations</span></span>
<span data-ttu-id="6388c-103">この例では、同じ <xref:System.Windows.Media.Animation.Storyboard>で <xref:System.Windows.Media.MediaTimeline> クラスと <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> クラスで、メディアとアニメーションを同時に再生する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6388c-103">This example shows how to play media and animations at the same time by using the <xref:System.Windows.Media.MediaTimeline> and <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> classes in the same <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6388c-104">例</span><span class="sxs-lookup"><span data-stu-id="6388c-104">Example</span></span>  
 <span data-ttu-id="6388c-105"><xref:System.Windows.Media.Animation.Storyboard> では、1 つ以上の <xref:System.Windows.Media.MediaTimeline> オブジェクトを、アニメーションなどの他の <xref:System.Windows.Media.Animation.Timeline> オブジェクトと共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="6388c-105">You can use one or more <xref:System.Windows.Media.MediaTimeline> objects in a <xref:System.Windows.Media.Animation.Storyboard> together with other <xref:System.Windows.Media.Animation.Timeline> objects, such as animations.</span></span>  
  
 <span data-ttu-id="6388c-106">次の例では、<xref:System.Windows.Media.Animation.Storyboard> の <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A> プロパティを `Slip` の値に設定します。これにより、メディア (この例ではビデオ) が進行するまでアニメーションが進行しないことが指定されます。</span><span class="sxs-lookup"><span data-stu-id="6388c-106">The following example sets the <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A> property of the <xref:System.Windows.Media.Animation.Storyboard> to a value of `Slip`, which specifies that the animation does not progress until the media (video in this example) progresses.</span></span> <span data-ttu-id="6388c-107">この機能は、読み込み時間のためにメディアの再生が遅れる場合などに必要です。</span><span class="sxs-lookup"><span data-stu-id="6388c-107">This functionality might be needed if media playback is delayed because of loading time.</span></span>  
  
 [!code-xaml[MediaGallery_snippet#MediaTimelinePlusAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snippet/CSharp/MediaTimelinePlusAnimationExample.xaml#mediatimelineplusanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="6388c-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="6388c-108">See also</span></span>

- <xref:System.Windows.Media.MediaTimeline>
- <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>
- <xref:System.Windows.Media.Animation.Storyboard>
- <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A>
- [<span data-ttu-id="6388c-109">方法トピック</span><span class="sxs-lookup"><span data-stu-id="6388c-109">How-to Topics</span></span>](audio-and-video-how-to-topics.md)
- [<span data-ttu-id="6388c-110">ストーリーボードの概要</span><span class="sxs-lookup"><span data-stu-id="6388c-110">Storyboards Overview</span></span>](storyboards-overview.md)
- [<span data-ttu-id="6388c-111">キー フレーム アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="6388c-111">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="6388c-112">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="6388c-112">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="6388c-113">グラフィックスとマルチメディア</span><span class="sxs-lookup"><span data-stu-id="6388c-113">Graphics and Multimedia</span></span>](index.md)
