---
title: '方法: メディアの再生を反復する'
ms.date: 03/30/2017
helpviewer_keywords:
- media [WPF], repeating playback
- repeating media playback [WPF]
- multimedia [WPF], repeating media playback
- playback of media [WPF], repeating
ms.assetid: 02ab486d-c6b6-4918-9edd-45a12aca4683
ms.openlocfilehash: 788bc6f31d61626f15548791135adb8c60258b49
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983475"
---
# <a name="how-to-repeat-media-playback"></a><span data-ttu-id="118cb-102">方法: メディアの再生を反復する</span><span class="sxs-lookup"><span data-stu-id="118cb-102">How to: Repeat Media Playback</span></span>
<span data-ttu-id="118cb-103">この例では、メディアを無制限に再生する (無限ループで再生されるようにメディアを設定する) 方法を示します。</span><span class="sxs-lookup"><span data-stu-id="118cb-103">This example shows how to playback media indefinitely, that is, to set media so that it plays in an infinite loop.</span></span>  
  
## <a name="example"></a><span data-ttu-id="118cb-104">例</span><span class="sxs-lookup"><span data-stu-id="118cb-104">Example</span></span>  
 <span data-ttu-id="118cb-105">次の例では、<xref:System.Windows.Media.Animation.Storyboard> で <xref:System.Windows.Controls.MediaElement> と <xref:System.Windows.Media.MediaTimeline> を使用して、無限ループでメディア クリップを再生します。</span><span class="sxs-lookup"><span data-stu-id="118cb-105">The following example uses <xref:System.Windows.Controls.MediaElement> and <xref:System.Windows.Media.MediaTimeline> in a <xref:System.Windows.Media.Animation.Storyboard> to play a media clip in an infinite loop.</span></span>  
  
 [!code-xaml[MediaGallery_snippet#SoundRepeatExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snippet/CSharp/SoundRepeatExample.xaml#soundrepeatexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="118cb-106">関連項目</span><span class="sxs-lookup"><span data-stu-id="118cb-106">See also</span></span>

- <xref:System.Windows.Controls.MediaElement>
- <xref:System.Windows.Media.MediaTimeline>
- <xref:System.Windows.Media.Animation.Storyboard>
- [<span data-ttu-id="118cb-107">方法トピック</span><span class="sxs-lookup"><span data-stu-id="118cb-107">How-to Topics</span></span>](audio-and-video-how-to-topics.md)
- [<span data-ttu-id="118cb-108">グラフィックスとマルチメディア</span><span class="sxs-lookup"><span data-stu-id="118cb-108">Graphics and Multimedia</span></span>](index.md)
