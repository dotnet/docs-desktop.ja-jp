---
title: どの修飾キーが押されたかを確認する
description: .NET 用 Windows フォームで、SHIFT、ALT、CTRL の各キーが押されたことを検出する方法について説明します。
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keyboard input
- shift keys
- events [Windows Forms], mouse
- Keys.ControlKey enumeration member
- keys [Windows Forms], control keys
- user input [Windows Forms], checking for keyboard
- keys [Windows Forms], determining last pressed
- keys [Windows Forms], shift keys
- keys [Windows Forms], modifier keys
- control keys
- keys [Windows Forms], alt keys
- alt keys
- Keys.Shift enumeration member
- events [Windows Forms], keyboard
- keyboards [Windows Forms], keyboard input
- Keys.Alt enumeration member
- modifier keys
ms.openlocfilehash: 7feda0f604e1cb40b34f7bf42aa122d817a5a95e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96942262"
---
# <a name="how-to-check-for-modifier-key-presses-windows-forms-net"></a>修飾キーの押下を確認する方法 (Windows フォーム .NET)

ユーザーがアプリケーションにキーを入力すると、<kbd>SHIFT</kbd>、<kbd>ALT</kbd>、<kbd>CTRL</kbd> などの修飾キーが押されたかどうかを監視することができます。 修飾キーが他のキーと組み合わせて押されても、マウス クリックによっても、アプリケーションが適切に応答できるようになります。 たとえば、<kbd>S</kbd> キーを押すと、画面に "s" が表示されることがあります。 そうではなく、<kbd>CTRL + S</kbd> キーが押される場合には、現在のドキュメントが保存されることがあります。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

<xref:System.Windows.Forms.Control.KeyDown> イベントを処理する場合、イベント ハンドラーが受信する <xref:System.Windows.Forms.KeyEventArgs.Modifiers?displayProperty=nameWithType> プロパティによって、どの修飾キーが押されているかが特定されます。 また、ビットごとの OR と組み合わせた修飾キーと共に押された文字が、<xref:System.Windows.Forms.KeyEventArgs.KeyData?displayProperty=nameWithType> プロパティによって特定されます。

<xref:System.Windows.Forms.Control.KeyPress> イベントまたはマウス イベントを処理している場合、イベント ハンドラーがこの情報を受信することはありません。 <xref:System.Windows.Forms.Control> クラスの <xref:System.Windows.Forms.Control.ModifierKeys%2A> プロパティを使用して、キー修飾子を検出します。 どちらの場合も、適切な <xref:System.Windows.Forms.Keys> 値とテスト対象の値のビットごとの AND を実行する必要があります。 <xref:System.Windows.Forms.Keys> 列挙型を使用すると、各修飾キーのバリエーションが増えるため、ビットごとの AND の確認には、正しい値を使用することが重要です。

たとえば、次のキー値は <kbd>SHIFT</kbd> キーを表します。

- <xref:System.Windows.Forms.Keys.Shift?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Keys.ShiftKey?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Keys.RShiftKey?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Keys.LShiftKey?displayProperty=nameWithType>

修飾キーとして <kbd>SHIFT</kbd> をテストする場合の正しい値は、<xref:System.Windows.Forms.Keys.Shift?displayProperty=nameWithType> です。 同様に、修飾子として <kbd>CTRL</kbd> と <kbd>ALT</kbd> をテストする場合は、<xref:System.Windows.Forms.Keys.Control?displayProperty=nameWithType> 値と <xref:System.Windows.Forms.Keys.Alt?displayProperty=nameWithType> 値をそれぞれ使用する必要があります。

## <a name="detect-modifier-key"></a>修飾キーを検出する

<xref:System.Windows.Forms.Control.ModifierKeys%2A> プロパティと <xref:System.Windows.Forms.Keys> 列挙値をビットごとの AND 演算子と比較して、修飾キーが押されているかどうかを検出します。

次のコード例では、<xref:System.Windows.Forms.Control.KeyPress> イベント ハンドラーと <xref:System.Windows.Forms.Control.KeyDown> のイベント ハンドラー内で、<kbd>SHIFT</kbd> キーが押されているかどうかを確認する方法を示します。

:::code language="csharp" source="snippets/how-to-check-modifier-key/csharp/Form1.cs" id="DetectModifier":::
:::code language="vb" source="snippets/how-to-check-modifier-key/vb/Form1.vb" id="DetectModifier":::

## <a name="see-also"></a>関連項目

- [キーボードの使用の概要 (Windows フォーム .NET)](overview.md)
- [キーボード イベントの使用 (Windows フォーム .NET)](events.md)
- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.ModifierKeys>
- <xref:System.Windows.Forms.Control.KeyDown>
- <xref:System.Windows.Forms.Control.KeyPress>
