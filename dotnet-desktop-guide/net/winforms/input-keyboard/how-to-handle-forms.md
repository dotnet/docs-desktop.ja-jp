---
title: キーボード入力をフォーム レベルで処理する
description: メッセージがコントロールに到達する前に、Windows フォームのキーボード入力をフォーム レベルで処理する方法について説明します。
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keyboard input [Windows Forms], at form level
- Windows Forms, handling keyboard input
- keyboards [Windows Forms], form-level input
ms.openlocfilehash: 51433eeb32f73385fd74d8a236a273526c1b72ed
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96942226"
---
# <a name="how-to-handle-keyboard-input-messages-in-the-form-windows-forms-net"></a><span data-ttu-id="94e90-103">フォームでキーボード入力メッセージを処理する方法 (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="94e90-103">How to handle keyboard input messages in the form (Windows Forms .NET)</span></span>

<span data-ttu-id="94e90-104">Windows フォームでは、キーボード メッセージがコントロールに到達する前に、それらのメッセージをフォーム レベルで処理できます。</span><span class="sxs-lookup"><span data-stu-id="94e90-104">Windows Forms provides the ability to handle keyboard messages at the form level, before the messages reach a control.</span></span> <span data-ttu-id="94e90-105">この記事では、このタスクを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="94e90-105">This article shows how to accomplish this task.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="handle-a-keyboard-message"></a><span data-ttu-id="94e90-106">キーボード メッセージを処理する</span><span class="sxs-lookup"><span data-stu-id="94e90-106">Handle a keyboard message</span></span>

<span data-ttu-id="94e90-107">アクティブ フォームの <xref:System.Windows.Forms.Control.KeyPress> イベントまたは <xref:System.Windows.Forms.Control.KeyDown> イベントを処理し、フォームの <xref:System.Windows.Forms.Form.KeyPreview%2A> プロパティを `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="94e90-107">Handle the <xref:System.Windows.Forms.Control.KeyPress> or <xref:System.Windows.Forms.Control.KeyDown> event of the active form and set the <xref:System.Windows.Forms.Form.KeyPreview%2A> property of the form to `true`.</span></span> <span data-ttu-id="94e90-108">このプロパティを使用すると、フォーム上のコントロールに到達する前に、フォームによってキーボードが受信されます。</span><span class="sxs-lookup"><span data-stu-id="94e90-108">This property causes the keyboard to be received by the form before they reach any controls on the form.</span></span> <span data-ttu-id="94e90-109">次のコード例では、<xref:System.Windows.Forms.Control.KeyPress> イベントを処理して、すべての数値キーを検出し、<kbd>1</kbd>、<kbd>4</kbd>、<kbd>7</kbd> の各キーを使用します。</span><span class="sxs-lookup"><span data-stu-id="94e90-109">The following code example handles the <xref:System.Windows.Forms.Control.KeyPress> event by detecting all of the number keys and consuming <kbd>1</kbd>, <kbd>4</kbd>, and <kbd>7</kbd>.</span></span>

:::code language="csharp" source="snippets/how-to-handle-forms/csharp/Form1.cs" id="HandleKey":::
:::code language="vb" source="snippets/how-to-handle-forms/vb/Form1.vb" id="HandleKey":::

## <a name="see-also"></a><span data-ttu-id="94e90-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="94e90-110">See also</span></span>

- [<span data-ttu-id="94e90-111">キーボードの使用の概要 (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="94e90-111">Overview of using the keyboard (Windows Forms .NET)</span></span>](overview.md)
- [<span data-ttu-id="94e90-112">キーボード イベントの使用 (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="94e90-112">Using keyboard events (Windows Forms .NET)</span></span>](events.md)
- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.ModifierKeys>
- <xref:System.Windows.Forms.Control.KeyDown>
- <xref:System.Windows.Forms.Control.KeyPress>
