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
# <a name="soundplayer-class-overview"></a><span data-ttu-id="88066-102">SoundPlayer クラスの概要</span><span class="sxs-lookup"><span data-stu-id="88066-102">SoundPlayer Class Overview</span></span>
<span data-ttu-id="88066-103"><xref:System.Media.SoundPlayer> クラスを使用すると、アプリケーションにサウンドを簡単に組み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="88066-103">The <xref:System.Media.SoundPlayer> class enables you to easily include sounds in your applications.</span></span>  
  
 <span data-ttu-id="88066-104">クラスは、 <xref:System.Media.SoundPlayer> リソースまたは UNC または HTTP の場所から .wav 形式でサウンドファイルを再生できます。</span><span class="sxs-lookup"><span data-stu-id="88066-104">The <xref:System.Media.SoundPlayer> class can play sound files in the .wav format, either from a resource or from UNC or HTTP locations.</span></span> <span data-ttu-id="88066-105">また、 <xref:System.Media.SoundPlayer> クラスを使用すると、サウンドを非同期に読み込んだり、再生したりできます。</span><span class="sxs-lookup"><span data-stu-id="88066-105">Additionally, the <xref:System.Media.SoundPlayer> class enables you to load or play sounds asynchronously.</span></span>  
  
 <span data-ttu-id="88066-106"><xref:System.Media.SystemSounds> クラスを使用して、ビープ音を含む、共通のシステム サウンドを再生することもできます。</span><span class="sxs-lookup"><span data-stu-id="88066-106">You can also use the <xref:System.Media.SystemSounds> class to play common system sounds, including a beep.</span></span>  
  
## <a name="commonly-used-properties-methods-and-events"></a><span data-ttu-id="88066-107">一般的に使用されるプロパティ、メソッド、およびイベント</span><span class="sxs-lookup"><span data-stu-id="88066-107">Commonly Used Properties, Methods, and Events</span></span>  
  
|<span data-ttu-id="88066-108">名前</span><span class="sxs-lookup"><span data-stu-id="88066-108">Name</span></span>|<span data-ttu-id="88066-109">説明</span><span class="sxs-lookup"><span data-stu-id="88066-109">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="88066-110"><xref:System.Media.SoundPlayer.SoundLocation%2A> プロパティ</span><span class="sxs-lookup"><span data-stu-id="88066-110"><xref:System.Media.SoundPlayer.SoundLocation%2A> property</span></span>|<span data-ttu-id="88066-111">サウンドのファイル パスまたは Web アドレスです。</span><span class="sxs-lookup"><span data-stu-id="88066-111">The file path or Web address of the sound.</span></span> <span data-ttu-id="88066-112">使用可能な値には UNC または HTTP があります。</span><span class="sxs-lookup"><span data-stu-id="88066-112">Acceptable values can be UNC or HTTP.</span></span>|  
|<span data-ttu-id="88066-113"><xref:System.Media.SoundPlayer.LoadTimeout%2A> プロパティ</span><span class="sxs-lookup"><span data-stu-id="88066-113"><xref:System.Media.SoundPlayer.LoadTimeout%2A> property</span></span>|<span data-ttu-id="88066-114">プログラムが、例外をスローする前にサウンドの読み込みを待機するミリ秒単位の時間です。</span><span class="sxs-lookup"><span data-stu-id="88066-114">The number of milliseconds your program will wait to load a sound before it throws an exception.</span></span> <span data-ttu-id="88066-115">既定値は 10 秒です。</span><span class="sxs-lookup"><span data-stu-id="88066-115">The default is 10 seconds.</span></span>|  
|<span data-ttu-id="88066-116"><xref:System.Media.SoundPlayer.IsLoadCompleted%2A> プロパティ</span><span class="sxs-lookup"><span data-stu-id="88066-116"><xref:System.Media.SoundPlayer.IsLoadCompleted%2A> property</span></span>|<span data-ttu-id="88066-117">サウンドの読み込みが終了したかどうかを示すブール値です。</span><span class="sxs-lookup"><span data-stu-id="88066-117">A Boolean value indicating whether the sound has finished loading.</span></span>|  
|<span data-ttu-id="88066-118"><xref:System.Media.SoundPlayer.Load%2A> メソッド</span><span class="sxs-lookup"><span data-stu-id="88066-118"><xref:System.Media.SoundPlayer.Load%2A> method</span></span>|<span data-ttu-id="88066-119">サウンドを同期的に読み込みます。</span><span class="sxs-lookup"><span data-stu-id="88066-119">Loads a sound synchronously.</span></span>|  
|<span data-ttu-id="88066-120"><xref:System.Media.SoundPlayer.LoadAsync%2A> メソッド</span><span class="sxs-lookup"><span data-stu-id="88066-120"><xref:System.Media.SoundPlayer.LoadAsync%2A> method</span></span>|<span data-ttu-id="88066-121">サウンドの非同期的な読み込みを開始します。</span><span class="sxs-lookup"><span data-stu-id="88066-121">Begins to load a sound asynchronously.</span></span> <span data-ttu-id="88066-122">読み込みが完了すると、イベントが発生し <xref:System.Media.SoundPlayer.OnLoadCompleted%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="88066-122">When loading is complete, it raises the <xref:System.Media.SoundPlayer.OnLoadCompleted%2A> event.</span></span>|  
|<span data-ttu-id="88066-123"><xref:System.Media.SoundPlayer.Play%2A> メソッド</span><span class="sxs-lookup"><span data-stu-id="88066-123"><xref:System.Media.SoundPlayer.Play%2A> method</span></span>|<span data-ttu-id="88066-124"><xref:System.Media.SoundPlayer.SoundLocation%2A>新しいスレッドで、プロパティまたはプロパティで指定されたサウンドを再生し <xref:System.Media.SoundPlayer.Stream%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="88066-124">Plays the sound specified in the <xref:System.Media.SoundPlayer.SoundLocation%2A> or <xref:System.Media.SoundPlayer.Stream%2A> property in a new thread.</span></span>|  
|<span data-ttu-id="88066-125"><xref:System.Media.SoundPlayer.PlaySync%2A> メソッド</span><span class="sxs-lookup"><span data-stu-id="88066-125"><xref:System.Media.SoundPlayer.PlaySync%2A> method</span></span>|<span data-ttu-id="88066-126"><xref:System.Media.SoundPlayer.SoundLocation%2A>現在のスレッドのプロパティまたはプロパティで指定されたサウンドを再生し <xref:System.Media.SoundPlayer.Stream%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="88066-126">Plays the sound specified in the <xref:System.Media.SoundPlayer.SoundLocation%2A> or <xref:System.Media.SoundPlayer.Stream%2A> property in the current thread.</span></span>|  
|<span data-ttu-id="88066-127"><xref:System.Media.SoundPlayer.Stop%2A> メソッド</span><span class="sxs-lookup"><span data-stu-id="88066-127"><xref:System.Media.SoundPlayer.Stop%2A> method</span></span>|<span data-ttu-id="88066-128">現在再生されているサウンドを停止します。</span><span class="sxs-lookup"><span data-stu-id="88066-128">Stops any sound currently playing.</span></span>|  
|<span data-ttu-id="88066-129"><xref:System.Media.SoundPlayer.LoadCompleted> イベント</span><span class="sxs-lookup"><span data-stu-id="88066-129"><xref:System.Media.SoundPlayer.LoadCompleted> event</span></span>|<span data-ttu-id="88066-130">サウンドの読み込みが試みられた後に発生します。</span><span class="sxs-lookup"><span data-stu-id="88066-130">Raised after the load of a sound is attempted.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="88066-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="88066-131">See also</span></span>

- <xref:System.Media.SoundPlayer>
- <xref:System.Media.SystemSounds>
