---
title: 電源管理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- battery states
- power states
ms.assetid: ad04a801-5682-4d88-92c5-26eb9cdb209a
ms.openlocfilehash: 9ac39df43a08f62e50116c61c4bdeda4cd1c8281
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981659"
---
# <a name="power-management-in-windows-forms"></a><span data-ttu-id="9e83b-102">Windows フォームでの電源管理</span><span class="sxs-lookup"><span data-stu-id="9e83b-102">Power Management in Windows Forms</span></span>
<span data-ttu-id="9e83b-103">Windows フォームアプリケーションは、Windows オペレーティングシステムの電源管理機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="9e83b-103">Your Windows Forms applications can take advantage of the power management features in the Windows operating system.</span></span> <span data-ttu-id="9e83b-104">アプリケーションでは、コンピューターの電源状態を監視し、状態が変化したときにアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="9e83b-104">Your applications can monitor the power status of a computer and take action when a status change occurs.</span></span> <span data-ttu-id="9e83b-105">たとえば、アプリケーションがポータブルコンピューター上で実行されている場合、コンピューターのバッテリ残量が一定のレベルに達したときに、アプリケーションの特定の機能を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="9e83b-105">For example, if your application is running on a portable computer, you might want to disable certain features in your application when the computer's battery charge falls under a certain level.</span></span>  
  
 <span data-ttu-id="9e83b-106">この .NET Framework は、 <xref:Microsoft.Win32.SystemEvents.PowerModeChanged> ユーザーがオペレーティングシステムを中断または再開するときや、AC 電源の状態またはバッテリの状態が変化したときなど、電源の状態が変化するたびに発生するイベントを提供します。</span><span class="sxs-lookup"><span data-stu-id="9e83b-106">The .NET Framework provides a <xref:Microsoft.Win32.SystemEvents.PowerModeChanged> event that occurs whenever there is a change in power status, such as when a user suspends or resumes the operating system, or when the AC power status or battery status changes.</span></span> <span data-ttu-id="9e83b-107"><xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>クラスのプロパティは、 <xref:System.Windows.Forms.SystemInformation> 次のコード例に示すように、現在の状態を照会するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="9e83b-107">The <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> property of the <xref:System.Windows.Forms.SystemInformation> class can be used to query for the current status, as shown in the following code example.</span></span>  
  
 [!code-csharp[PowerMode#1](~/samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#1)]
 [!code-vb[PowerMode#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#1)]  
  
 <span data-ttu-id="9e83b-108"><xref:System.Windows.Forms.BatteryChargeStatus>列挙型に加えて、プロパティには、 <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> バッテリ容量 ( <xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A> ) とバッテリの充電率 (、) を決定するための列挙も含まれてい <xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A> <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="9e83b-108">Besides the <xref:System.Windows.Forms.BatteryChargeStatus> enumerations, the <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> property also contains enumerations for determining battery capacity (<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>) and battery charge percentage (<xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A>, <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A>).</span></span>  
  
 <span data-ttu-id="9e83b-109">のメソッドを使用して <xref:System.Windows.Forms.Application.SetSuspendState%2A> 、 <xref:System.Windows.Forms.Application> コンピューターを休止状態または中断モードにすることができます。</span><span class="sxs-lookup"><span data-stu-id="9e83b-109">You can use the <xref:System.Windows.Forms.Application.SetSuspendState%2A> method of the <xref:System.Windows.Forms.Application> to put a computer into hibernation or suspend mode.</span></span> <span data-ttu-id="9e83b-110">`force`引数がに設定されている場合 `false` 、オペレーティングシステムは、中断するアクセス許可を要求しているすべてのアプリケーションにイベントをブロードキャストします。</span><span class="sxs-lookup"><span data-stu-id="9e83b-110">If the `force` argument is set to `false`, the operating system will broadcast an event to all applications requesting permission to suspend.</span></span> <span data-ttu-id="9e83b-111">`disableWakeEvent`引数がに設定されている場合 `true` 、オペレーティングシステムはすべてのウェイクイベントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="9e83b-111">If the `disableWakeEvent` argument is set to `true`, the operating system disables all wake events.</span></span>  
  
 <span data-ttu-id="9e83b-112">次のコード例は、コンピューターを休止状態にする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="9e83b-112">The following code example demonstrates how to put a computer into hibernation.</span></span>  
  
 [!code-csharp[PowerMode#2](~/samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#2)]
 [!code-vb[PowerMode#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="9e83b-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="9e83b-113">See also</span></span>

- <xref:Microsoft.Win32.SystemEvents.PowerModeChanged>
- <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>
- <xref:System.Windows.Forms.Application.SetSuspendState%2A>
- <xref:Microsoft.Win32.SystemEvents.SessionSwitch>
