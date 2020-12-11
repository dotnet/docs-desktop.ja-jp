---
title: '方法: ストーリーボードを使用して MediaElement を制御する'
description: Windows Presentation Foundation (WPF) でストーリーボードを使用してメディアの再生を制御します。 単純なメディア プレーヤーを作成する場合は、この例を検討してください。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- multimedia [WPF], controlling playback of media with Storyboards
- controlling playback of media [WPF], with Storyboards
- Storyboards [WPF], controlling playback of media with
- media [WPF], controlling playback with Storyboards
- playback of media [WPF], controlling with Storyboards
ms.assetid: 6128ca77-b826-4e36-b968-6f237157c543
ms.openlocfilehash: 0ee25549799eada72ba2c35908842c1e2d2adaf6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985256"
---
# <a name="how-to-control-a-mediaelement-by-using-a-storyboard"></a><span data-ttu-id="d66e0-104">方法: ストーリーボードを使用して MediaElement を制御する</span><span class="sxs-lookup"><span data-stu-id="d66e0-104">How to: Control a MediaElement by Using a Storyboard</span></span>
<span data-ttu-id="d66e0-105">この例では、<xref:System.Windows.Media.Animation.Storyboard> で <xref:System.Windows.Media.MediaTimeline> を使用し、<xref:System.Windows.Controls.MediaElement> を制御する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d66e0-105">This example shows how to control a <xref:System.Windows.Controls.MediaElement> by using a <xref:System.Windows.Media.MediaTimeline> in a <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d66e0-106">例</span><span class="sxs-lookup"><span data-stu-id="d66e0-106">Example</span></span>  
 <span data-ttu-id="d66e0-107"><xref:System.Windows.Media.Animation.Storyboard> で <xref:System.Windows.Media.MediaTimeline> を使用して <xref:System.Windows.Controls.MediaElement> のタイミングを制御するとき、機能は、アニメーションなど、他の <xref:System.Windows.Media.Animation.Timeline> オブジェクトの機能と同じになります。</span><span class="sxs-lookup"><span data-stu-id="d66e0-107">When you use a <xref:System.Windows.Media.MediaTimeline> in a <xref:System.Windows.Media.Animation.Storyboard> to control the timing of a <xref:System.Windows.Controls.MediaElement>, the functionality is identical to the functionality of other <xref:System.Windows.Media.Animation.Timeline> objects, such as animations.</span></span> <span data-ttu-id="d66e0-108">たとえば、<xref:System.Windows.Media.MediaTimeline> では、<xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> プロパティなどの <xref:System.Windows.Media.Animation.Timeline> プロパティを使用し、<xref:System.Windows.Controls.MediaElement> を起動するタイミングを指定します (メディア再生開始)。</span><span class="sxs-lookup"><span data-stu-id="d66e0-108">For example, a <xref:System.Windows.Media.MediaTimeline> uses <xref:System.Windows.Media.Animation.Timeline> properties like the <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> property to specify when to start a <xref:System.Windows.Controls.MediaElement> (start media playback).</span></span> <span data-ttu-id="d66e0-109">また、<xref:System.Windows.Media.Animation.Timeline.Duration%2A> プロパティを使用し、<xref:System.Windows.Controls.MediaElement> がアクティブになる時間を指定します (メディア再生時間)。</span><span class="sxs-lookup"><span data-stu-id="d66e0-109">It also uses the <xref:System.Windows.Media.Animation.Timeline.Duration%2A> property to specify how long the <xref:System.Windows.Controls.MediaElement> is active (duration of media playback).</span></span> <span data-ttu-id="d66e0-110"><xref:System.Windows.Media.Animation.Storyboard> で <xref:System.Windows.Media.Animation.Timeline> オブジェクトを使用する方法の詳細については、「[ストーリーボードの概要](storyboards-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d66e0-110">For more information about using <xref:System.Windows.Media.Animation.Timeline> objects with a <xref:System.Windows.Media.Animation.Storyboard>, see [Storyboards Overview](storyboards-overview.md).</span></span>  
  
 <span data-ttu-id="d66e0-111">この例では、<xref:System.Windows.Media.MediaTimeline> を使用して再生を制御する単純なメディア プレーヤーを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d66e0-111">This example shows how to create a simple media player that uses a <xref:System.Windows.Media.MediaTimeline> to control playback.</span></span> <span data-ttu-id="d66e0-112">メディア プレーヤーには、再生、一時停止、再開、停止のボタンがあります。</span><span class="sxs-lookup"><span data-stu-id="d66e0-112">The media player includes play, pause, resume, and stop buttons.</span></span> <span data-ttu-id="d66e0-113">プレーヤーにはまた、進行状況バーとして機能する <xref:System.Windows.Controls.Slider> コントロールがあります。</span><span class="sxs-lookup"><span data-stu-id="d66e0-113">The player also has a <xref:System.Windows.Controls.Slider> control that acts as a progress bar.</span></span>  
  
 <span data-ttu-id="d66e0-114">次の例では、メディア プレーヤーの [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] が作成されます。</span><span class="sxs-lookup"><span data-stu-id="d66e0-114">The following example creates the [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] for the media player.</span></span>  
  
 [!code-xaml[MediaGallery_snip#MediaTimelineExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml#mediatimelineexamplewholepage)]  
  
 <span data-ttu-id="d66e0-115">次の例では、進行状況バーの機能が作成されます。</span><span class="sxs-lookup"><span data-stu-id="d66e0-115">The following example creates the functionality for the progress bar.</span></span>  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaTimelineExample.xaml.cs#codebehindmediatimelineexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml.vb#codebehindmediatimelineexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="d66e0-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="d66e0-116">See also</span></span>

- <xref:System.Windows.Controls.MediaElement>
- <xref:System.Windows.Media.MediaTimeline>
- <xref:System.Windows.Media.Animation.Storyboard>
- [<span data-ttu-id="d66e0-117">MediaElement (再生、一時停止、停止、ボリューム、および速度) を制御する</span><span class="sxs-lookup"><span data-stu-id="d66e0-117">Control a MediaElement (Play, Pause, Stop, Volume, and Speed)</span></span>](how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md)
- [<span data-ttu-id="d66e0-118">ストーリーボードの概要</span><span class="sxs-lookup"><span data-stu-id="d66e0-118">Storyboards Overview</span></span>](storyboards-overview.md)
- [<span data-ttu-id="d66e0-119">キー フレーム アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="d66e0-119">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="d66e0-120">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="d66e0-120">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="d66e0-121">方法トピック</span><span class="sxs-lookup"><span data-stu-id="d66e0-121">How-to Topics</span></span>](audio-and-video-how-to-topics.md)
- [<span data-ttu-id="d66e0-122">グラフィックスとマルチメディア</span><span class="sxs-lookup"><span data-stu-id="d66e0-122">Graphics and Multimedia</span></span>](index.md)
