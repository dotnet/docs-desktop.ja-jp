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
# <a name="how-to-modify-keyboard-key-events-windows-forms-net"></a><span data-ttu-id="57b55-103">キーボード キー イベントを変更する方法 (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="57b55-103">How to modify keyboard key events (Windows Forms .NET)</span></span>

<span data-ttu-id="57b55-104">Windows フォームは、キーボードの入力を使用して変更する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="57b55-104">Windows Forms provides the ability to consume and modify keyboard input.</span></span> <span data-ttu-id="57b55-105">キーの使用とは、メッセージ キューのさらに下のその他のメソッドとイベントが、キーの値を受信しないようにメソッドまたはイベント ハンドラー内のキーを処理することを表します。</span><span class="sxs-lookup"><span data-stu-id="57b55-105">Consuming a key refers to handling a key within a method or event handler so that other methods and events further down the message queue don't receive the key value.</span></span> <span data-ttu-id="57b55-106">また、キーの変更とは、メッセージ キューのさらに下のメソッドとイベント ハンドラーが、異なるキーの値を受け取るようにキーの値を変更することを表します。</span><span class="sxs-lookup"><span data-stu-id="57b55-106">And, modifying a key refers to modifying the value of a key so that methods and event handlers further down the message queue receive a different key value.</span></span> <span data-ttu-id="57b55-107">この記事では、これらのタスクを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="57b55-107">This article shows how to accomplish these tasks.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="consume-a-key"></a><span data-ttu-id="57b55-108">キーを使用する</span><span class="sxs-lookup"><span data-stu-id="57b55-108">Consume a key</span></span>

<span data-ttu-id="57b55-109"><xref:System.Windows.Forms.Control.KeyPress> イベント ハンドラーで、<xref:System.Windows.Forms.KeyPressEventArgs> クラスの <xref:System.Windows.Forms.KeyPressEventArgs.Handled%2A> プロパティを `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="57b55-109">In a <xref:System.Windows.Forms.Control.KeyPress> event handler, set the <xref:System.Windows.Forms.KeyPressEventArgs.Handled%2A> property of the <xref:System.Windows.Forms.KeyPressEventArgs> class to `true`.</span></span>

<span data-ttu-id="57b55-110">または</span><span class="sxs-lookup"><span data-stu-id="57b55-110">-or-</span></span>

<span data-ttu-id="57b55-111"><xref:System.Windows.Forms.Control.KeyDown> イベント ハンドラーで、<xref:System.Windows.Forms.KeyEventArgs> クラスの <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> プロパティを `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="57b55-111">In a <xref:System.Windows.Forms.Control.KeyDown> event handler, set the <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> property of the <xref:System.Windows.Forms.KeyEventArgs> class to `true`.</span></span>

> [!NOTE]
> <span data-ttu-id="57b55-112"><xref:System.Windows.Forms.Control.KeyDown> イベント ハンドラーで <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> プロパティを設定すると、<xref:System.Windows.Forms.Control.KeyPress> イベントと <xref:System.Windows.Forms.Control.KeyUp> イベントが現在のキー入力から発生しないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="57b55-112">Setting the <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> property in the <xref:System.Windows.Forms.Control.KeyDown> event handler does not prevent the <xref:System.Windows.Forms.Control.KeyPress> and <xref:System.Windows.Forms.Control.KeyUp> events from being raised for the current keystroke.</span></span> <span data-ttu-id="57b55-113">この目的には、<xref:System.Windows.Forms.KeyEventArgs.SuppressKeyPress%2A> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="57b55-113">Use the <xref:System.Windows.Forms.KeyEventArgs.SuppressKeyPress%2A> property for this purpose.</span></span>

<span data-ttu-id="57b55-114">次の例では、<xref:System.Windows.Forms.Control.KeyPress> イベントを処理し、`A` と `a` の文字キーを使用します。</span><span class="sxs-lookup"><span data-stu-id="57b55-114">The following example handles the <xref:System.Windows.Forms.Control.KeyPress> event to consume the `A` and `a` character keys.</span></span> <span data-ttu-id="57b55-115">これらのキーをテキスト ボックスに入力することはできません。</span><span class="sxs-lookup"><span data-stu-id="57b55-115">Those keys can't be typed into the text box:</span></span>

:::code language="csharp" source="snippets/how-to-change-key-press/csharp/Form1.cs" id="ConsumeKey":::
:::code language="vb" source="snippets/how-to-change-key-press/vb/Form1.vb" id="ConsumeKey":::

## <a name="modify-a-standard-character-key"></a><span data-ttu-id="57b55-116">標準の文字のキーを変更する</span><span class="sxs-lookup"><span data-stu-id="57b55-116">Modify a standard character key</span></span>

<span data-ttu-id="57b55-117"><xref:System.Windows.Forms.Control.KeyPress> イベント ハンドラーで、<xref:System.Windows.Forms.KeyPressEventArgs> クラスの <xref:System.Windows.Forms.KeyPressEventArgs.KeyChar%2A> プロパティを新しい文字のキーの値に設定します。</span><span class="sxs-lookup"><span data-stu-id="57b55-117">In a <xref:System.Windows.Forms.Control.KeyPress> event handler, set the <xref:System.Windows.Forms.KeyPressEventArgs.KeyChar%2A> property of the <xref:System.Windows.Forms.KeyPressEventArgs> class to the value of the new character key.</span></span>

<span data-ttu-id="57b55-118">次の例では、<xref:System.Windows.Forms.Control.KeyPress> イベントを処理し、`A` と `a` の文字キーを `!` に変更します。</span><span class="sxs-lookup"><span data-stu-id="57b55-118">The following example handles the <xref:System.Windows.Forms.Control.KeyPress> event to change any `A` and `a` character keys to `!`:</span></span>

:::code language="csharp" source="snippets/how-to-change-key-press/csharp/Form1.cs" id="ModifyKey":::
:::code language="vb" source="snippets/how-to-change-key-press/vb/Form1.vb" id="ModifyKey":::

## <a name="modify-a-non-character-key"></a><span data-ttu-id="57b55-119">文字以外のキーを変更する</span><span class="sxs-lookup"><span data-stu-id="57b55-119">Modify a non-character key</span></span>

<span data-ttu-id="57b55-120">文字以外のキーの押下を変更するには、コントロールから継承し、<xref:System.Windows.Forms.Control.PreProcessMessage%2A> メソッドをオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="57b55-120">You can only modify non-character key presses by inheriting from the control and overriding the <xref:System.Windows.Forms.Control.PreProcessMessage%2A> method.</span></span> <span data-ttu-id="57b55-121">入力 <xref:System.Windows.Forms.Message> がコントロールに送信されると、コントロールによってイベントが発生する前に処理されます。</span><span class="sxs-lookup"><span data-stu-id="57b55-121">As the   input <xref:System.Windows.Forms.Message> is sent to the control, it's processed before the control raising events.</span></span> <span data-ttu-id="57b55-122">これらのメッセージをインターセプトし、変更またはブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="57b55-122">You can intercept these messages to modify or block them.</span></span>

<span data-ttu-id="57b55-123">次のコード例は、<xref:System.Windows.Forms.Message> パラメーターの <xref:System.Windows.Forms.Message.WParam%2A> プロパティを使用して、押されたキーを変更する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="57b55-123">The following code example demonstrates how to use the <xref:System.Windows.Forms.Message.WParam%2A> property of the <xref:System.Windows.Forms.Message> parameter to change the key pressed.</span></span> <span data-ttu-id="57b55-124">このコードを使用すると、<kbd>F1</kbd> から <kbd>F10</kbd> までのキーを検出し、そのキーを <kbd>0</kbd> から <kbd>9</kbd> までの範囲の数字キーに変換することができます (<kbd>F10 </kbd> は <kbd>0</kbd> にマップされます)。</span><span class="sxs-lookup"><span data-stu-id="57b55-124">This code detects a key from <kbd>F1</kbd> through <kbd>F10</kbd> and translates the key into a numeric key ranging from <kbd>0</kbd> through <kbd>9</kbd> (where <kbd>F10</kbd> maps to <kbd>0</kbd>).</span></span>

:::code language="csharp" source="snippets/how-to-change-key-press/csharp/NewTextBox.cs" id="PreProcessMessage":::
:::code language="vb" source="snippets/how-to-change-key-press/vb/NewTextBox.vb" id="PreProcessMessage":::

## <a name="see-also"></a><span data-ttu-id="57b55-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="57b55-125">See also</span></span>

- [<span data-ttu-id="57b55-126">キーボードの使用の概要 (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="57b55-126">Overview of using the keyboard (Windows Forms .NET)</span></span>](overview.md)
- [<span data-ttu-id="57b55-127">キーボード イベントの使用 (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="57b55-127">Using keyboard events (Windows Forms .NET)</span></span>](events.md)
- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.KeyDown>
- <xref:System.Windows.Forms.Control.KeyPress>
