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
# <a name="how-to-handle-keyboard-input-messages-in-the-form-windows-forms-net"></a>フォームでキーボード入力メッセージを処理する方法 (Windows フォーム .NET)

Windows フォームでは、キーボード メッセージがコントロールに到達する前に、それらのメッセージをフォーム レベルで処理できます。 この記事では、このタスクを実行する方法について説明します。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="handle-a-keyboard-message"></a>キーボード メッセージを処理する

アクティブ フォームの <xref:System.Windows.Forms.Control.KeyPress> イベントまたは <xref:System.Windows.Forms.Control.KeyDown> イベントを処理し、フォームの <xref:System.Windows.Forms.Form.KeyPreview%2A> プロパティを `true` に設定します。 このプロパティを使用すると、フォーム上のコントロールに到達する前に、フォームによってキーボードが受信されます。 次のコード例では、<xref:System.Windows.Forms.Control.KeyPress> イベントを処理して、すべての数値キーを検出し、<kbd>1</kbd>、<kbd>4</kbd>、<kbd>7</kbd> の各キーを使用します。

:::code language="csharp" source="snippets/how-to-handle-forms/csharp/Form1.cs" id="HandleKey":::
:::code language="vb" source="snippets/how-to-handle-forms/vb/Form1.vb" id="HandleKey":::

## <a name="see-also"></a>関連項目

- [キーボードの使用の概要 (Windows フォーム .NET)](overview.md)
- [キーボード イベントの使用 (Windows フォーム .NET)](events.md)
- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.ModifierKeys>
- <xref:System.Windows.Forms.Control.KeyDown>
- <xref:System.Windows.Forms.Control.KeyPress>
