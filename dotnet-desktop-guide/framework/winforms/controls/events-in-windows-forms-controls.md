---
title: コントロール内のイベント
ms.date: 03/30/2017
helpviewer_keywords:
- events [Windows Forms], custom controls (using code)
- custom controls [Windows Forms], events overview (using code)
ms.assetid: 7e3d1379-87aa-437c-afce-c99454eff30e
ms.openlocfilehash: 27edaf2d895453d64d35ba6eff724df583a9b7dd
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981060"
---
# <a name="events-in-windows-forms-controls"></a><span data-ttu-id="91880-102">Windows フォーム コントロールのイベント</span><span class="sxs-lookup"><span data-stu-id="91880-102">Events in Windows Forms Controls</span></span>

<span data-ttu-id="91880-103">Windows フォームコントロールは、から60を超えるイベントを継承 <xref:System.Windows.Forms.Control?displayProperty=nameWithType> します。</span><span class="sxs-lookup"><span data-stu-id="91880-103">A Windows Forms control inherits more than sixty events from <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span> <span data-ttu-id="91880-104">これには、 <xref:System.Windows.Forms.Control.Paint> コントロールを描画するイベント、イベントやイベントなどのウィンドウの表示に関連するイベント、 <xref:System.Windows.Forms.Control.Resize> <xref:System.Windows.Forms.Control.Layout> 低レベルのマウスイベントとキーボードイベントなどがあります。</span><span class="sxs-lookup"><span data-stu-id="91880-104">These include the <xref:System.Windows.Forms.Control.Paint> event, which causes a control to be drawn, events related to displaying a window, such as the <xref:System.Windows.Forms.Control.Resize> and <xref:System.Windows.Forms.Control.Layout> events, and low-level mouse and keyboard events.</span></span> <span data-ttu-id="91880-105">一部の下位イベントは、によって <xref:System.Windows.Forms.Control> 、やなどのセマンティックイベントに合成され <xref:System.Windows.Forms.Control.Click> <xref:System.Windows.Forms.Control.DoubleClick> ます。</span><span class="sxs-lookup"><span data-stu-id="91880-105">Some low-level events are synthesized by <xref:System.Windows.Forms.Control> into semantic events such as <xref:System.Windows.Forms.Control.Click> and <xref:System.Windows.Forms.Control.DoubleClick>.</span></span> <span data-ttu-id="91880-106">継承されたイベントの詳細については、「」を参照してください <xref:System.Windows.Forms.Control> 。</span><span class="sxs-lookup"><span data-stu-id="91880-106">For details about inherited events, see <xref:System.Windows.Forms.Control>.</span></span>  
  
 <span data-ttu-id="91880-107">継承されたイベントの機能をカスタム コントロールでオーバーライドする必要がある場合、デリゲートを結び付けるのではなく、継承された `On`*EventName* メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="91880-107">If your custom control needs to override inherited event functionality, override the inherited `On`*EventName* method instead of attaching a delegate.</span></span> <span data-ttu-id="91880-108">.NET Framework でのイベント モデルに詳しくない場合は、「[コンポーネントからのイベントの生成](/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="91880-108">If you are not familiar with the event model in the .NET Framework, see [Raising Events from a Component](/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91880-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="91880-109">See also</span></span>

- [<span data-ttu-id="91880-110">OnPaint メソッドのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="91880-110">Overriding the OnPaint Method</span></span>](overriding-the-onpaint-method.md)
- [<span data-ttu-id="91880-111">ユーザーの入力の処理</span><span class="sxs-lookup"><span data-stu-id="91880-111">Handling User Input</span></span>](handling-user-input.md)
- [<span data-ttu-id="91880-112">イベントの定義</span><span class="sxs-lookup"><span data-stu-id="91880-112">Defining an Event</span></span>](defining-an-event-in-windows-forms-controls.md)
- [<span data-ttu-id="91880-113">イベント</span><span class="sxs-lookup"><span data-stu-id="91880-113">Events</span></span>](/dotnet/standard/events/index)
