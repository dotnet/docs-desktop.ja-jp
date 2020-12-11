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
# <a name="power-management-in-windows-forms"></a>Windows フォームでの電源管理
Windows フォームアプリケーションは、Windows オペレーティングシステムの電源管理機能を利用できます。 アプリケーションでは、コンピューターの電源状態を監視し、状態が変化したときにアクションを実行できます。 たとえば、アプリケーションがポータブルコンピューター上で実行されている場合、コンピューターのバッテリ残量が一定のレベルに達したときに、アプリケーションの特定の機能を無効にすることができます。  
  
 この .NET Framework は、 <xref:Microsoft.Win32.SystemEvents.PowerModeChanged> ユーザーがオペレーティングシステムを中断または再開するときや、AC 電源の状態またはバッテリの状態が変化したときなど、電源の状態が変化するたびに発生するイベントを提供します。 <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>クラスのプロパティは、 <xref:System.Windows.Forms.SystemInformation> 次のコード例に示すように、現在の状態を照会するために使用できます。  
  
 [!code-csharp[PowerMode#1](~/samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#1)]
 [!code-vb[PowerMode#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#1)]  
  
 <xref:System.Windows.Forms.BatteryChargeStatus>列挙型に加えて、プロパティには、 <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> バッテリ容量 ( <xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A> ) とバッテリの充電率 (、) を決定するための列挙も含まれてい <xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A> <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A> ます。  
  
 のメソッドを使用して <xref:System.Windows.Forms.Application.SetSuspendState%2A> 、 <xref:System.Windows.Forms.Application> コンピューターを休止状態または中断モードにすることができます。 `force`引数がに設定されている場合 `false` 、オペレーティングシステムは、中断するアクセス許可を要求しているすべてのアプリケーションにイベントをブロードキャストします。 `disableWakeEvent`引数がに設定されている場合 `true` 、オペレーティングシステムはすべてのウェイクイベントを無効にします。  
  
 次のコード例は、コンピューターを休止状態にする方法を示しています。  
  
 [!code-csharp[PowerMode#2](~/samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#2)]
 [!code-vb[PowerMode#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#2)]  
  
## <a name="see-also"></a>関連項目

- <xref:Microsoft.Win32.SystemEvents.PowerModeChanged>
- <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>
- <xref:System.Windows.Forms.Application.SetSuspendState%2A>
- <xref:Microsoft.Win32.SystemEvents.SessionSwitch>
