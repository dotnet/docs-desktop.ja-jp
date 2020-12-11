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
# <a name="timer-component-overview-windows-forms"></a>Timer コンポーネントの概要 (Windows フォーム)

Windows フォーム <xref:System.Windows.Forms.Timer> は、一定の間隔でイベントを発生させるコンポーネントです。 このコンポーネントは、Windows フォームの環境用に設計されています。 サーバー環境に適したタイマーが必要な場合は、「[サーバー ベースのタイマーの概要](/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90))」を参照してください。  
  
## <a name="key-properties-methods-and-events"></a>主要なプロパティ、メソッド、およびイベント  

 間隔の長さは、プロパティによって定義され <xref:System.Windows.Forms.Timer.Interval%2A> 、その値はミリ秒単位です。 コンポーネントが有効な場合、 <xref:System.Windows.Forms.Timer.Tick> イベントはすべての間隔で発生します。 ここで、実行するコードを追加します。 詳細については、「 [方法: Windows フォーム Timer コンポーネントを使用して一定間隔でプロシージャを実行する](run-procedures-at-set-intervals-with-wf-timer-component.md)」を参照してください。 コンポーネントの主要なメソッド <xref:System.Windows.Forms.Timer> は、 <xref:System.Windows.Forms.Timer.Start%2A> とです。これにより、 <xref:System.Windows.Forms.Timer.Stop%2A> タイマーがオンまたはオフになります。 タイマーがオフに切り替わると、リセットされます。コンポーネントを一時停止する方法はありません <xref:System.Windows.Forms.Timer> 。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.Timer>
- [Timer コンポーネント](timer-component-windows-forms.md)
- [Windows フォームの Timer コンポーネントの Interval プロパティの制限](limitations-of-the-timer-component-interval-property.md)
