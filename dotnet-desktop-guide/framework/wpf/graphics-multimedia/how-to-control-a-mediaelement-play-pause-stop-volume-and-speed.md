---
title: '方法: MediaElement (再生、一時停止、停止、ボリューム、および速度) を制御する'
description: Windows Presentation Foundation (WPF) でメディアの再生を制御します。 開始、停止、一時停止、前後へのスキップ、ボリュームと速度の調整を行います。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- playback of media [WPF], controlling
- controlling playback of media [WPF]
- multimedia [WPF], controlling playback of media
- media [WPF], controlling playback of
ms.assetid: 6885a730-e054-4c16-8c1e-ffe17b1f7c32
ms.openlocfilehash: da846299eaa1e36b6e5caab08bc1f861e9f9c46d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974313"
---
# <a name="how-to-control-a-mediaelement-play-pause-stop-volume-and-speed"></a><span data-ttu-id="84718-104">方法: MediaElement (再生、一時停止、停止、ボリューム、および速度) を制御する</span><span class="sxs-lookup"><span data-stu-id="84718-104">How to: Control a MediaElement (Play, Pause, Stop, Volume, and Speed)</span></span>
<span data-ttu-id="84718-105">次の例では、<xref:System.Windows.Controls.MediaElement> を使用してメディアの再生を制御する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="84718-105">The following example shows how to control playback of media using a <xref:System.Windows.Controls.MediaElement>.</span></span> <span data-ttu-id="84718-106">この例では、メディアの再生、一時停止、停止、前後へのスキップに加え、ボリュームと速度の調整も可能な簡単なメディア プレーヤーを作成します。</span><span class="sxs-lookup"><span data-stu-id="84718-106">The example creates a simple media player that allows you to play, pause, stop, and skip back and forth in the media as well as adjust the volume and speed ratio.</span></span>  
  
## <a name="example"></a><span data-ttu-id="84718-107">例</span><span class="sxs-lookup"><span data-stu-id="84718-107">Example</span></span>  
 <span data-ttu-id="84718-108">次のコードでは、UI を作成します。</span><span class="sxs-lookup"><span data-stu-id="84718-108">The code below creates the UI.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="84718-109">メディアを対話的に停止、一時停止、再生できるようにするには、<xref:System.Windows.Controls.MediaElement> の <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> プロパティを `Manual` に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="84718-109">The <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> property of <xref:System.Windows.Controls.MediaElement> must be set to `Manual` in order to be able to interactively stop, pause, and play the media.</span></span>  
  
 [!code-xaml[MediaGallery_snip#MediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml#mediaelementexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="84718-110">例</span><span class="sxs-lookup"><span data-stu-id="84718-110">Example</span></span>  
 <span data-ttu-id="84718-111">次のコードは、サンプル UI コントロールの機能を実装しています。</span><span class="sxs-lookup"><span data-stu-id="84718-111">The code below implements the functionality of the sample UI controls.</span></span> <span data-ttu-id="84718-112"><xref:System.Windows.Controls.MediaElement.Play%2A> メソッド、<xref:System.Windows.Controls.MediaElement.Pause%2A> メソッド、<xref:System.Windows.Controls.MediaElement.Stop%2A> メソッドを使用して、メディアをそれぞれ再生、一時停止、停止します。</span><span class="sxs-lookup"><span data-stu-id="84718-112">The <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, and <xref:System.Windows.Controls.MediaElement.Stop%2A> methods are used to respectively play, pause and stop the media.</span></span> <span data-ttu-id="84718-113"><xref:System.Windows.Controls.MediaElement> の <xref:System.Windows.Controls.MediaElement.Position%2A> プロパティを変更すると、メディア内でスキップできます。</span><span class="sxs-lookup"><span data-stu-id="84718-113">Changing the <xref:System.Windows.Controls.MediaElement.Position%2A> property of the <xref:System.Windows.Controls.MediaElement> allows you to skip around in the media.</span></span> <span data-ttu-id="84718-114">最後に、<xref:System.Windows.Controls.MediaElement.Volume%2A> プロパティと <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> プロパティを使用して、メディアのボリュームと再生速度を調整します。</span><span class="sxs-lookup"><span data-stu-id="84718-114">Finally, the <xref:System.Windows.Controls.MediaElement.Volume%2A> and <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> properties are used to adjust the volume and playback speed of the media.</span></span>  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaElementExample.xaml.cs#codebehindmediaelementexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml.vb#codebehindmediaelementexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="84718-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="84718-115">See also</span></span>

- [<span data-ttu-id="84718-116">ストーリーボードを使用して MediaElement を制御する</span><span class="sxs-lookup"><span data-stu-id="84718-116">Control a MediaElement by Using a Storyboard</span></span>](how-to-control-a-mediaelement-by-using-a-storyboard.md)
