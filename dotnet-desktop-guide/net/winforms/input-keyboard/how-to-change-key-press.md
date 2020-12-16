---
title: キーボード キー イベントを変更する
description: キーの押下をインターセプトし、Windows フォーム .NET アプリケーションで押されたキーを変更する方法について説明します。
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keyboard input [Windows Forms], modifying
- modifying keyboard input
- Windows Forms, modifying keyboard input
- keyboards [Windows Forms], keyboard input
ms.openlocfilehash: 94a003a8eb5fbffd9dbaf817a3ce95ca93a7d370
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96942182"
---
# <a name="how-to-modify-keyboard-key-events-windows-forms-net"></a>キーボード キー イベントを変更する方法 (Windows フォーム .NET)

Windows フォームは、キーボードの入力を使用して変更する機能を提供します。 キーの使用とは、メッセージ キューのさらに下のその他のメソッドとイベントが、キーの値を受信しないようにメソッドまたはイベント ハンドラー内のキーを処理することを表します。 また、キーの変更とは、メッセージ キューのさらに下のメソッドとイベント ハンドラーが、異なるキーの値を受け取るようにキーの値を変更することを表します。 この記事では、これらのタスクを実行する方法について説明します。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="consume-a-key"></a>キーを使用する

<xref:System.Windows.Forms.Control.KeyPress> イベント ハンドラーで、<xref:System.Windows.Forms.KeyPressEventArgs> クラスの <xref:System.Windows.Forms.KeyPressEventArgs.Handled%2A> プロパティを `true` に設定します。

または

<xref:System.Windows.Forms.Control.KeyDown> イベント ハンドラーで、<xref:System.Windows.Forms.KeyEventArgs> クラスの <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> プロパティを `true` に設定します。

> [!NOTE]
> <xref:System.Windows.Forms.Control.KeyDown> イベント ハンドラーで <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> プロパティを設定すると、<xref:System.Windows.Forms.Control.KeyPress> イベントと <xref:System.Windows.Forms.Control.KeyUp> イベントが現在のキー入力から発生しないようにすることができます。 この目的には、<xref:System.Windows.Forms.KeyEventArgs.SuppressKeyPress%2A> プロパティを使用します。

次の例では、<xref:System.Windows.Forms.Control.KeyPress> イベントを処理し、`A` と `a` の文字キーを使用します。 これらのキーをテキスト ボックスに入力することはできません。

:::code language="csharp" source="snippets/how-to-change-key-press/csharp/Form1.cs" id="ConsumeKey":::
:::code language="vb" source="snippets/how-to-change-key-press/vb/Form1.vb" id="ConsumeKey":::

## <a name="modify-a-standard-character-key"></a>標準の文字のキーを変更する

<xref:System.Windows.Forms.Control.KeyPress> イベント ハンドラーで、<xref:System.Windows.Forms.KeyPressEventArgs> クラスの <xref:System.Windows.Forms.KeyPressEventArgs.KeyChar%2A> プロパティを新しい文字のキーの値に設定します。

次の例では、<xref:System.Windows.Forms.Control.KeyPress> イベントを処理し、`A` と `a` の文字キーを `!` に変更します。

:::code language="csharp" source="snippets/how-to-change-key-press/csharp/Form1.cs" id="ModifyKey":::
:::code language="vb" source="snippets/how-to-change-key-press/vb/Form1.vb" id="ModifyKey":::

## <a name="modify-a-non-character-key"></a>文字以外のキーを変更する

文字以外のキーの押下を変更するには、コントロールから継承し、<xref:System.Windows.Forms.Control.PreProcessMessage%2A> メソッドをオーバーライドする必要があります。 入力 <xref:System.Windows.Forms.Message> がコントロールに送信されると、コントロールによってイベントが発生する前に処理されます。 これらのメッセージをインターセプトし、変更またはブロックすることができます。

次のコード例は、<xref:System.Windows.Forms.Message> パラメーターの <xref:System.Windows.Forms.Message.WParam%2A> プロパティを使用して、押されたキーを変更する方法を示しています。 このコードを使用すると、<kbd>F1</kbd> から <kbd>F10</kbd> までのキーを検出し、そのキーを <kbd>0</kbd> から <kbd>9</kbd> までの範囲の数字キーに変換することができます (<kbd>F10 </kbd> は <kbd>0</kbd> にマップされます)。

:::code language="csharp" source="snippets/how-to-change-key-press/csharp/NewTextBox.cs" id="PreProcessMessage":::
:::code language="vb" source="snippets/how-to-change-key-press/vb/NewTextBox.vb" id="PreProcessMessage":::

## <a name="see-also"></a>関連項目

- [キーボードの使用の概要 (Windows フォーム .NET)](overview.md)
- [キーボード イベントの使用 (Windows フォーム .NET)](events.md)
- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.KeyDown>
- <xref:System.Windows.Forms.Control.KeyPress>
