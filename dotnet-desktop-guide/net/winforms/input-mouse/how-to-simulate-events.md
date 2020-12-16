---
title: マウス イベントをシミュレートする方法
description: .NET の Windows フォームでマウス イベントをシミュレートする方法について説明します。
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mouse [Windows Forms], event simulation
- user input [Windows Forms], simulating
- SendKeys [Windows Forms], using
ms.openlocfilehash: 443611163d33a266b3c49d03df13131c994b0bd3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96942295"
---
# <a name="how-to-simulate-mouse-events-windows-forms-net"></a>マウス イベントをシミュレートする方法 (Windows フォーム .NET)

Windows フォームでのマウス イベントのシミュレートは、キーボード イベントをシミュレートするほど簡単ではありません。 Windows フォームには、マウスを移動してマウスクリックのアクションを呼び出すヘルパー クラスがありません。 マウスは、Windows のネイティブ メソッドを使用してのみ制御することができます。 カスタム コントロールまたはフォームを使用している場合は、マウス イベントをシミュレートできますが、マウスを直接制御することはできません。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="events"></a>イベント

ほとんどのイベントには、それらを呼び出す対応するメソッドがあり、`OnMouseMove` のように `On` の後に `EventName` が続く名前が付けられています。 これらのメソッドは保護されており、コントロールまたはフォームのコンテキストの外部からアクセスすることはできないため、このオプションは、カスタム コントロールまたはフォーム内でのみ使用できます。 `OnMouseMove` などのメソッドを使用する場合には、実際にマウスを制御したり、コントロールとやり取りしたりできず、関連するイベントが発生するだけという欠点があります。 たとえば、<xref:System.Windows.Forms.ListBox> 内の項目にマウス ポインターを重ねた状態をシミュレートしたい場合、`OnMouseMove` と `ListBox` は、カーソルの下で強調表示されている項目に視覚的に反応しません。

これらの保護されたメソッドは、マウス イベントをシミュレートするために使用します。

- `OnMouseDown`
- `OnMouseEnter`
- `OnMouseHover`
- `OnMouseLeave`
- `OnMouseMove`
- `OnMouseUp`
- `OnMouseWheel`
- `OnMouseClick`
- `OnMouseDoubleClick`

これらのイベントの詳細については、「[マウス イベントの使用 (Windows フォーム .NET)](events.md)」を参照してください。

## <a name="invoke-a-click"></a>クリックを呼び出す

ユーザー コードを呼び出すボタンやチェック状態を変更するチェックボックスなどのように、ほとんどのコントロールはクリックされると何らかの動作を実行するので、Windows フォームにはクリックを簡単にトリガーする方法が用意されています。 コンボボックスなどの一部のコントロールでは、クリックしても特別な処理は行われず、このコントロールにクリックをシミュレートしても何も作用はありません。

### <a name="performclick"></a>PerformClick

<xref:System.Windows.Forms.IButtonControl?displayProperty=nameWithType> インターフェイスには、コントロールのクリックをシミュレートする <xref:System.Windows.Forms.IButtonControl.PerformClick%2A> メソッドが実装されています。 このインターフェイスは、<xref:System.Windows.Forms.Button?displayProperty=nameWithType> と <xref:System.Windows.Forms.LinkLabel?displayProperty=nameWithType> の両コントロールに実装されています。

:::code language="csharp" source="snippets/how-to-simulate-events/csharp/Form1.cs" id="PerformClick":::
:::code language="vb" source="snippets/how-to-simulate-events/vb/Form1.vb" id="PerformClick":::

### <a name="invokeclick"></a>InvokeClick

フォームまたはカスタム コントロールでは、マウスのクリックのシミュレートに <xref:System.Windows.Forms.Control.InvokeOnClick%2A> メソッドを使用します。 これは、フォームまたは派生したカスタム コントロールからのみ呼び出すことができる保護されたメソッドです。

たとえば、次のコードでは、`button1` からチェックボックスをクリックします。

:::code language="csharp" source="snippets/how-to-simulate-events/csharp/Form1.cs" id="ClickCheckbox":::
:::code language="vb" source="snippets/how-to-simulate-events/vb/Form1.vb" id="ClickCheckbox":::

## <a name="use-native-windows-methods"></a>Windows のネイティブ メソッドを使用する

Windows には、マウスの動きとクリックをシミュレートするために呼び出せる、[`User32.dll SendInput`](/windows/win32/api/winuser/nf-winuser-sendinput) や [`User32.dll SetCursorPos`](/windows/win32/api/winuser/nf-winuser-setcursorpos) などのメソッドがあります。 次の例は、マウス カーソルをコントロールの中央に移動します。

:::code language="csharp" source="snippets/how-to-simulate-events/csharp/Form2.cs" id="MoveCursor":::
:::code language="vb" source="snippets/how-to-simulate-events/vb/Form2.vb" id="MoveCursor":::

## <a name="see-also"></a>関連項目

- [マウスの使用の概要 (Windows フォーム .NET)](overview.md)
- [マウス イベントの使用 (Windows フォーム .NET)](events.md)
- [クリックとダブルクリックを区別する方法 (Windows フォーム .NET)](how-to-distinguish-between-clicks-and-double-clicks.md)
- [マウス ポインターを管理する (Windows フォーム .NET)](how-to-manage-cursor-pointer.md)
