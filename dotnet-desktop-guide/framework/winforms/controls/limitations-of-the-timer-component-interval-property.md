---
title: Timer Component Interval プロパティの制限事項
ms.date: 03/30/2017
helpviewer_keywords:
- timers [Windows Forms], event intervals
- Interval property [Windows Forms], limitations
- timers [Windows Forms], Windows-based
- Timer component [Windows Forms], limitations of Interval property
ms.assetid: 7e5fb513-77e7-4046-a8e8-aab94e61ca0f
ms.openlocfilehash: 90023a20b32cc4f5709d35f4e8c0a339e1d46751
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982963"
---
# <a name="limitations-of-the-windows-forms-timer-components-interval-property"></a><span data-ttu-id="e9a24-102">Windows フォームの Timer コンポーネントの Interval プロパティの制限</span><span class="sxs-lookup"><span data-stu-id="e9a24-102">Limitations of the Windows Forms Timer Component's Interval Property</span></span>

<span data-ttu-id="e9a24-103">Windows フォーム <xref:System.Windows.Forms.Timer> コンポーネントには、 <xref:System.Windows.Forms.Timer.Interval%2A> 1 つのタイマーイベントから次のタイマーイベントまでに経過するミリ秒数を指定するプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="e9a24-103">The Windows Forms <xref:System.Windows.Forms.Timer> component has an <xref:System.Windows.Forms.Timer.Interval%2A> property that specifies the number of milliseconds that pass between one timer event and the next.</span></span> <span data-ttu-id="e9a24-104">コンポーネントが無効になっていない限り、タイマーは <xref:System.Windows.Forms.Timer.Tick> ほぼ同じ間隔でイベントを受信し続けます。</span><span class="sxs-lookup"><span data-stu-id="e9a24-104">Unless the component is disabled, a timer continues to receive the <xref:System.Windows.Forms.Timer.Tick> event at roughly equal intervals of time.</span></span>  
  
 <span data-ttu-id="e9a24-105">このコンポーネントは、Windows フォームの環境用に設計されています。</span><span class="sxs-lookup"><span data-stu-id="e9a24-105">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="e9a24-106">サーバー環境に適したタイマーが必要な場合は、「[サーバー ベースのタイマーの概要](/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9a24-106">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span></span>  
  
## <a name="the-interval-property"></a><span data-ttu-id="e9a24-107">Interval プロパティ</span><span class="sxs-lookup"><span data-stu-id="e9a24-107">The Interval Property</span></span>  

 <span data-ttu-id="e9a24-108"><xref:System.Windows.Forms.Timer.Interval%2A>コンポーネントをプログラミングする場合、プロパティにはいくつかの制限事項があり <xref:System.Windows.Forms.Timer> ます。</span><span class="sxs-lookup"><span data-stu-id="e9a24-108">The <xref:System.Windows.Forms.Timer.Interval%2A> property has a few limitations to consider when you are programming a <xref:System.Windows.Forms.Timer> component:</span></span>  
  
- <span data-ttu-id="e9a24-109">アプリケーションまたは他のアプリケーションがシステムに対して大量の要求 (長いループ、集中的な計算、ドライブ、ネットワーク、ポートアクセスなど) を実行している場合は、プロパティで指定されているように、アプリケーションでタイマーイベントを取得できないことがあり <xref:System.Windows.Forms.Timer.Interval%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="e9a24-109">If your application or another application is making heavy demands on the system — such as long loops, intensive calculations, or drive, network, or port access — your application may not get timer events as often as the <xref:System.Windows.Forms.Timer.Interval%2A> property specifies.</span></span>  
  
- <span data-ttu-id="e9a24-110">この間隔は、時間の経過と共に正確には保証されません。</span><span class="sxs-lookup"><span data-stu-id="e9a24-110">The interval is not guaranteed to elapse exactly on time.</span></span> <span data-ttu-id="e9a24-111">正確さを確保するために、タイマーは、蓄積された時間を内部で追跡するのではなく、必要に応じてシステムクロックをチェックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9a24-111">To ensure accuracy, the timer should check the system clock as needed, rather than try to keep track of accumulated time internally.</span></span>  
  
- <span data-ttu-id="e9a24-112">プロパティの有効桁数 <xref:System.Windows.Forms.Timer.Interval%2A> はミリ秒単位です。</span><span class="sxs-lookup"><span data-stu-id="e9a24-112">The precision of the <xref:System.Windows.Forms.Timer.Interval%2A> property is in milliseconds.</span></span> <span data-ttu-id="e9a24-113">コンピューターによっては、ミリ秒よりも高い解像度の高解像度カウンターが提供される場合があります。</span><span class="sxs-lookup"><span data-stu-id="e9a24-113">Some computers provide a high-resolution counter that has a resolution higher than milliseconds.</span></span> <span data-ttu-id="e9a24-114">このようなカウンターの可用性は、コンピューターのプロセッサハードウェアによって異なります。</span><span class="sxs-lookup"><span data-stu-id="e9a24-114">The availability of such a counter depends on the processor hardware of your computer.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e9a24-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="e9a24-115">See also</span></span>

- <xref:System.Windows.Forms.Timer>
- [<span data-ttu-id="e9a24-116">Timer コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e9a24-116">Timer Component</span></span>](timer-component-windows-forms.md)
- [<span data-ttu-id="e9a24-117">Timer コンポーネントの概要</span><span class="sxs-lookup"><span data-stu-id="e9a24-117">Timer Component Overview</span></span>](timer-component-overview-windows-forms.md)
