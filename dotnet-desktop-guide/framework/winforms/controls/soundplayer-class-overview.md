---
title: SoundPlayer クラスの概要
ms.date: 03/30/2017
helpviewer_keywords:
- playing sounds [Windows Forms], SoundPlayer class
- SoundPlayer class [Windows Forms], about SoundPlayer class
- sounds [Windows Forms], playing
ms.assetid: fcebb938-62b9-4677-9cbe-6465bc863e22
ms.openlocfilehash: 3ff23cbfa78b803d4526e7a7c389fd5d458a967c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983660"
---
# <a name="soundplayer-class-overview"></a>SoundPlayer クラスの概要
<xref:System.Media.SoundPlayer> クラスを使用すると、アプリケーションにサウンドを簡単に組み込むことができます。  
  
 クラスは、 <xref:System.Media.SoundPlayer> リソースまたは UNC または HTTP の場所から .wav 形式でサウンドファイルを再生できます。 また、 <xref:System.Media.SoundPlayer> クラスを使用すると、サウンドを非同期に読み込んだり、再生したりできます。  
  
 <xref:System.Media.SystemSounds> クラスを使用して、ビープ音を含む、共通のシステム サウンドを再生することもできます。  
  
## <a name="commonly-used-properties-methods-and-events"></a>一般的に使用されるプロパティ、メソッド、およびイベント  
  
|名前|説明|  
|----------|-----------------|  
|<xref:System.Media.SoundPlayer.SoundLocation%2A> プロパティ|サウンドのファイル パスまたは Web アドレスです。 使用可能な値には UNC または HTTP があります。|  
|<xref:System.Media.SoundPlayer.LoadTimeout%2A> プロパティ|プログラムが、例外をスローする前にサウンドの読み込みを待機するミリ秒単位の時間です。 既定値は 10 秒です。|  
|<xref:System.Media.SoundPlayer.IsLoadCompleted%2A> プロパティ|サウンドの読み込みが終了したかどうかを示すブール値です。|  
|<xref:System.Media.SoundPlayer.Load%2A> メソッド|サウンドを同期的に読み込みます。|  
|<xref:System.Media.SoundPlayer.LoadAsync%2A> メソッド|サウンドの非同期的な読み込みを開始します。 読み込みが完了すると、イベントが発生し <xref:System.Media.SoundPlayer.OnLoadCompleted%2A> ます。|  
|<xref:System.Media.SoundPlayer.Play%2A> メソッド|<xref:System.Media.SoundPlayer.SoundLocation%2A>新しいスレッドで、プロパティまたはプロパティで指定されたサウンドを再生し <xref:System.Media.SoundPlayer.Stream%2A> ます。|  
|<xref:System.Media.SoundPlayer.PlaySync%2A> メソッド|<xref:System.Media.SoundPlayer.SoundLocation%2A>現在のスレッドのプロパティまたはプロパティで指定されたサウンドを再生し <xref:System.Media.SoundPlayer.Stream%2A> ます。|  
|<xref:System.Media.SoundPlayer.Stop%2A> メソッド|現在再生されているサウンドを停止します。|  
|<xref:System.Media.SoundPlayer.LoadCompleted> イベント|サウンドの読み込みが試みられた後に発生します。|  
  
## <a name="see-also"></a>関連項目

- <xref:System.Media.SoundPlayer>
- <xref:System.Media.SystemSounds>
