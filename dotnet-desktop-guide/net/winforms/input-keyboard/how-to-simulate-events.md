---
title: キーボード イベントをシミュレートする
description: .NET 用の Windows フォームでキーボード イベントをシミュレートする方法について説明します。
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keyboards [Windows Forms], event simulation
- user input [Windows Forms], simulating
- SendKeys [Windows Forms], using
ms.openlocfilehash: 5ac62ca4311461ba95a2c31876d038baffe678a2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96942351"
---
# <a name="how-to-simulate-keyboard-events-windows-forms-net"></a>キーボード イベントをシミュレートする方法 (Windows フォーム .NET)

Windows フォームには、プログラムでキーボード入力をシミュレートするためのいくつかのオプションが用意されています。 この記事では、これらのオプションの概要について説明します。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="use-sendkeys"></a>SendKeys を使用する

Windows フォームには、アクティブなアプリケーションにキーストロークを送信するための <xref:System.Windows.Forms.SendKeys?displayProperty=fullName> クラスが用意されています。 アプリケーションにキーストロークを送信するには、<xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> と <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> の 2 つのメソッドがあります。 2 つのメソッドの違いは、`SendWait` がキーストロークが送信されたときに現在のスレッドをブロックして、応答を待機するのに対し、`Send` はそれを行わないことです。 `SendWait` の詳細については、「[別のアプリケーションにキーストロークを送信するには](#to-send-a-keystroke-to-a-different-application)」を参照してください。

> [!CAUTION]
> アプリケーションが国際対応し、さまざまなキーボードの使用を想定している場合は、 <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> の使用により予期しない結果になる可能性があるため、回避する必要があります。

バックグラウンドで、`SendKeys` は古い Windows 実装を使用して入力を送信します。これは、アプリケーションが管理者権限で実行されていないことが予想される最新の Windows では失敗する可能性があります。 古い実装が失敗した場合、コードによって自動的に新しい Windows の実装で入力の送信が試行されます。 さらに、<xref:System.Windows.Forms.SendKeys> クラスで新しい実装を使用すると、キーストロークを別のアプリケーションに送信するときに、<xref:System.Windows.Forms.SendKeys.SendWait%2A> メソッドで現在のスレッドがブロックされなくなります。

> [!IMPORTANT]
> アプリケーションが、オペレーティング システムに関係なく一貫した動作に依存する場合、app.config ファイルに次のアプリケーション設定を追加することで、 <xref:System.Windows.Forms.SendKeys> クラスが新しい実装を使用するよう強制することができます。
>
> ```xml
> <appSettings>
>   <add key="SendKeys" value="SendInput"/>
> </appSettings>
> ```
>
> <xref:System.Windows.Forms.SendKeys> クラスで前の実装 "_のみ_" を使用するよう強制するには、代わりに値 `"JournalHook"` を使用します。

### <a name="to-send-a-keystroke-to-the-same-application"></a>同じアプリケーションにキーストロークを送信するには

<xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> クラスの <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> メソッドまたは <xref:System.Windows.Forms.SendKeys> メソッドを呼び出します。 指定されたキーストロークは、アプリケーションのアクティブなコントロールによって受信されます。

次のコード例では、`Send` を使用して、<kbd>ALT</kbd> と <kbd>下方向</kbd> キーを一緒に押すことをシミュレートします。 これらのキーストロークによって、<xref:System.Windows.Forms.ComboBox> コントロールのドロップダウンが表示されます。 この例では、<xref:System.Windows.Forms.Button> と <xref:System.Windows.Forms.ComboBox> がある <xref:System.Windows.Forms.Form> を想定しています。

:::code language="csharp" source="snippets/how-to-simulate-events/csharp/Form1.cs" id="ShowDropDown":::
:::code language="vb" source="snippets/how-to-simulate-events/vb/Form1.vb" id="ShowDropDown":::

### <a name="to-send-a-keystroke-to-a-different-application"></a>別のアプリケーションにキーストロークを送信するには

<xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> と <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> のメソッドは、アクティブなアプリケーション (通常はキーストロークの送信元のアプリケーション) にキーストロークを送信します。 キーストロークを別のアプリケーションに送信するには、まず、それをアクティブ化する必要があります。 別のアプリケーションをアクティブ化するマネージド メソッドがないため、ネイティブ Windows メソッドを使用して他のアプリケーションにフォーカスを設定する必要があります。 次のコード例は、プラットフォーム呼び出しを使用して `FindWindow` メソッドと `SetForegroundWindow` メソッドを呼び出し、電卓アプリケーションのウィンドウをアクティブ化してから、 `Send` を呼び出して電卓アプリケーションに一連の計算を発行します。

次のコード例では、`Send` を使用して、Windows 10 電卓アプリケーションでのキーの押下をシミュレートします。 まず、`Calculator` というタイトルのアプリケーション ウィンドウを検索し、アクティブ化します。 アクティブ化したら、10 + 10 を計算するキーストロークが送信されます。

:::code language="csharp" source="snippets/how-to-simulate-events/csharp/Form2.cs" id="Calculator":::
:::code language="vb" source="snippets/how-to-simulate-events/vb/Form2.vb" id="Calculator":::

## <a name="use-oneventname-methods"></a>OnEventName メソッドを使用する

キーボード イベントをシミュレートする最も簡単な方法は、イベントを発生させるオブジェクトでメソッドを呼び出すことです。 ほとんどのイベントには、それらを呼び出す対応するメソッドがあり、`OnKeyPress` のように `On` の後に `EventName` が続く名前が付けられています。 これらのメソッドは保護されており、コントロールまたはフォームのコンテキストの外部からアクセスすることはできないため、このオプションは、カスタム コントロールまたはフォーム内でのみ使用できます。

これらの保護されたメソッドは、キーボード イベントをシミュレートするために使用できます。

- `OnKeyDown`
- `OnKeyPress`
- `OnKeyUp`

これらのイベントの詳細については、「[キーボード イベントの使用 (Windows フォーム .NET)](events.md)」を参照してください。

## <a name="see-also"></a>関連項目

- [キーボードの使用の概要 (Windows フォーム .NET)](overview.md)
- [キーボード イベントの使用 (Windows フォーム .NET)](events.md)
- [マウス イベントの使用 (Windows フォーム .NET)](../input-mouse/events.md)
- <xref:System.Windows.Forms.SendKeys>
- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.KeyDown>
- <xref:System.Windows.Forms.Control.KeyPress>
