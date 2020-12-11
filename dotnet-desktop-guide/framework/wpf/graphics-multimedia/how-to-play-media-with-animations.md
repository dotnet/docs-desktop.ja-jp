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
# <a name="how-to-play-media-with-animations"></a>方法: アニメーションを使用してメディアを再生する
この例では、同じ <xref:System.Windows.Media.Animation.Storyboard>で <xref:System.Windows.Media.MediaTimeline> クラスと <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> クラスで、メディアとアニメーションを同時に再生する方法を示します。  
  
## <a name="example"></a>例  
 <xref:System.Windows.Media.Animation.Storyboard> では、1 つ以上の <xref:System.Windows.Media.MediaTimeline> オブジェクトを、アニメーションなどの他の <xref:System.Windows.Media.Animation.Timeline> オブジェクトと共に使用できます。  
  
 次の例では、<xref:System.Windows.Media.Animation.Storyboard> の <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A> プロパティを `Slip` の値に設定します。これにより、メディア (この例ではビデオ) が進行するまでアニメーションが進行しないことが指定されます。 この機能は、読み込み時間のためにメディアの再生が遅れる場合などに必要です。  
  
 [!code-xaml[MediaGallery_snippet#MediaTimelinePlusAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snippet/CSharp/MediaTimelinePlusAnimationExample.xaml#mediatimelineplusanimationexamplewholepage)]  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Media.MediaTimeline>
- <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>
- <xref:System.Windows.Media.Animation.Storyboard>
- <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A>
- [方法トピック](audio-and-video-how-to-topics.md)
- [ストーリーボードの概要](storyboards-overview.md)
- [キー フレーム アニメーションの概要](key-frame-animations-overview.md)
- [アニメーションの概要](animation-overview.md)
- [グラフィックスとマルチメディア](index.md)
