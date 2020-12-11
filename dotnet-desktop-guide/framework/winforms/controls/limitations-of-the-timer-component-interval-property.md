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
# <a name="limitations-of-the-windows-forms-timer-components-interval-property"></a>Windows フォームの Timer コンポーネントの Interval プロパティの制限

Windows フォーム <xref:System.Windows.Forms.Timer> コンポーネントには、 <xref:System.Windows.Forms.Timer.Interval%2A> 1 つのタイマーイベントから次のタイマーイベントまでに経過するミリ秒数を指定するプロパティがあります。 コンポーネントが無効になっていない限り、タイマーは <xref:System.Windows.Forms.Timer.Tick> ほぼ同じ間隔でイベントを受信し続けます。  
  
 このコンポーネントは、Windows フォームの環境用に設計されています。 サーバー環境に適したタイマーが必要な場合は、「[サーバー ベースのタイマーの概要](/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90))」を参照してください。  
  
## <a name="the-interval-property"></a>Interval プロパティ  

 <xref:System.Windows.Forms.Timer.Interval%2A>コンポーネントをプログラミングする場合、プロパティにはいくつかの制限事項があり <xref:System.Windows.Forms.Timer> ます。  
  
- アプリケーションまたは他のアプリケーションがシステムに対して大量の要求 (長いループ、集中的な計算、ドライブ、ネットワーク、ポートアクセスなど) を実行している場合は、プロパティで指定されているように、アプリケーションでタイマーイベントを取得できないことがあり <xref:System.Windows.Forms.Timer.Interval%2A> ます。  
  
- この間隔は、時間の経過と共に正確には保証されません。 正確さを確保するために、タイマーは、蓄積された時間を内部で追跡するのではなく、必要に応じてシステムクロックをチェックする必要があります。  
  
- プロパティの有効桁数 <xref:System.Windows.Forms.Timer.Interval%2A> はミリ秒単位です。 コンピューターによっては、ミリ秒よりも高い解像度の高解像度カウンターが提供される場合があります。 このようなカウンターの可用性は、コンピューターのプロセッサハードウェアによって異なります。
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.Timer>
- [Timer コンポーネント](timer-component-windows-forms.md)
- [Timer コンポーネントの概要](timer-component-overview-windows-forms.md)
