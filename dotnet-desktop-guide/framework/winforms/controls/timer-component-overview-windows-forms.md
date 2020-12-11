---
title: Timer コンポーネントの概要
ms.date: 03/30/2017
f1_keywords:
- Timer
helpviewer_keywords:
- Timer component [Windows Forms], about Timer components
- timers [Windows Forms], about timers
ms.assetid: e672c05b-a8b6-4b26-9e4d-9223aa9e3873
ms.openlocfilehash: ca1a7bf304da3fd602e3b0c36bb3aa20cd6b1345
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980032"
---
# <a name="timer-component-overview-windows-forms"></a><span data-ttu-id="9017b-102">Timer コンポーネントの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="9017b-102">Timer Component Overview (Windows Forms)</span></span>

<span data-ttu-id="9017b-103">Windows フォーム <xref:System.Windows.Forms.Timer> は、一定の間隔でイベントを発生させるコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="9017b-103">The Windows Forms <xref:System.Windows.Forms.Timer> is a component that raises an event at regular intervals.</span></span> <span data-ttu-id="9017b-104">このコンポーネントは、Windows フォームの環境用に設計されています。</span><span class="sxs-lookup"><span data-stu-id="9017b-104">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="9017b-105">サーバー環境に適したタイマーが必要な場合は、「[サーバー ベースのタイマーの概要](/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9017b-105">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span></span>  
  
## <a name="key-properties-methods-and-events"></a><span data-ttu-id="9017b-106">主要なプロパティ、メソッド、およびイベント</span><span class="sxs-lookup"><span data-stu-id="9017b-106">Key Properties, Methods, and Events</span></span>  

 <span data-ttu-id="9017b-107">間隔の長さは、プロパティによって定義され <xref:System.Windows.Forms.Timer.Interval%2A> 、その値はミリ秒単位です。</span><span class="sxs-lookup"><span data-stu-id="9017b-107">The length of the intervals is defined by the <xref:System.Windows.Forms.Timer.Interval%2A> property, whose value is in milliseconds.</span></span> <span data-ttu-id="9017b-108">コンポーネントが有効な場合、 <xref:System.Windows.Forms.Timer.Tick> イベントはすべての間隔で発生します。</span><span class="sxs-lookup"><span data-stu-id="9017b-108">When the component is enabled, the <xref:System.Windows.Forms.Timer.Tick> event is raised every interval.</span></span> <span data-ttu-id="9017b-109">ここで、実行するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="9017b-109">This is where you would add code to be executed.</span></span> <span data-ttu-id="9017b-110">詳細については、「 [方法: Windows フォーム Timer コンポーネントを使用して一定間隔でプロシージャを実行する](run-procedures-at-set-intervals-with-wf-timer-component.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9017b-110">For more information, see [How to: Run Procedures at Set Intervals with the Windows Forms Timer Component](run-procedures-at-set-intervals-with-wf-timer-component.md).</span></span> <span data-ttu-id="9017b-111">コンポーネントの主要なメソッド <xref:System.Windows.Forms.Timer> は、 <xref:System.Windows.Forms.Timer.Start%2A> とです。これにより、 <xref:System.Windows.Forms.Timer.Stop%2A> タイマーがオンまたはオフになります。</span><span class="sxs-lookup"><span data-stu-id="9017b-111">The key methods of the <xref:System.Windows.Forms.Timer> component are <xref:System.Windows.Forms.Timer.Start%2A> and <xref:System.Windows.Forms.Timer.Stop%2A>, which turn the timer on and off.</span></span> <span data-ttu-id="9017b-112">タイマーがオフに切り替わると、リセットされます。コンポーネントを一時停止する方法はありません <xref:System.Windows.Forms.Timer> 。</span><span class="sxs-lookup"><span data-stu-id="9017b-112">When the timer is switched off, it resets; there is no way to pause a <xref:System.Windows.Forms.Timer> component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9017b-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="9017b-113">See also</span></span>

- <xref:System.Windows.Forms.Timer>
- [<span data-ttu-id="9017b-114">Timer コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9017b-114">Timer Component</span></span>](timer-component-windows-forms.md)
- [<span data-ttu-id="9017b-115">Windows フォームの Timer コンポーネントの Interval プロパティの制限</span><span class="sxs-lookup"><span data-stu-id="9017b-115">Limitations of the Windows Forms Timer Component's Interval Property</span></span>](limitations-of-the-timer-component-interval-property.md)
