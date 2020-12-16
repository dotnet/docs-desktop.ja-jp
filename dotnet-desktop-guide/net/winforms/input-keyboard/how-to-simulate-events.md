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
# <a name="how-to-simulate-keyboard-events-windows-forms-net"></a><span data-ttu-id="da14a-103">キーボード イベントをシミュレートする方法 (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="da14a-103">How to simulate keyboard events (Windows Forms .NET)</span></span>

<span data-ttu-id="da14a-104">Windows フォームには、プログラムでキーボード入力をシミュレートするためのいくつかのオプションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="da14a-104">Windows Forms provides a few options for programmatically simulating keyboard input.</span></span> <span data-ttu-id="da14a-105">この記事では、これらのオプションの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="da14a-105">This article provides an overview of these options.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="use-sendkeys"></a><span data-ttu-id="da14a-106">SendKeys を使用する</span><span class="sxs-lookup"><span data-stu-id="da14a-106">Use SendKeys</span></span>

<span data-ttu-id="da14a-107">Windows フォームには、アクティブなアプリケーションにキーストロークを送信するための <xref:System.Windows.Forms.SendKeys?displayProperty=fullName> クラスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="da14a-107">Windows Forms provides the <xref:System.Windows.Forms.SendKeys?displayProperty=fullName> class for sending keystrokes to the active application.</span></span> <span data-ttu-id="da14a-108">アプリケーションにキーストロークを送信するには、<xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> と <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> の 2 つのメソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="da14a-108">There are two methods to send keystrokes to an application: <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> and <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="da14a-109">2 つのメソッドの違いは、`SendWait` がキーストロークが送信されたときに現在のスレッドをブロックして、応答を待機するのに対し、`Send` はそれを行わないことです。</span><span class="sxs-lookup"><span data-stu-id="da14a-109">The difference between the two methods is that `SendWait` blocks the current thread when the keystroke is sent, waiting for a response, while `Send` doesn't.</span></span> <span data-ttu-id="da14a-110">`SendWait` の詳細については、「[別のアプリケーションにキーストロークを送信するには](#to-send-a-keystroke-to-a-different-application)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da14a-110">For more information about `SendWait`, see [To send a keystroke to a different application](#to-send-a-keystroke-to-a-different-application).</span></span>

> [!CAUTION]
> <span data-ttu-id="da14a-111">アプリケーションが国際対応し、さまざまなキーボードの使用を想定している場合は、 <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> の使用により予期しない結果になる可能性があるため、回避する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da14a-111">If your application is intended for international use with a variety of keyboards, the use of <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> could yield unpredictable results and should be avoided.</span></span>

<span data-ttu-id="da14a-112">バックグラウンドで、`SendKeys` は古い Windows 実装を使用して入力を送信します。これは、アプリケーションが管理者権限で実行されていないことが予想される最新の Windows では失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="da14a-112">Behind the scenes, `SendKeys` uses an older Windows implementation for sending input, which may fail on modern Windows where it's expected that the application isn't running with administrative rights.</span></span> <span data-ttu-id="da14a-113">古い実装が失敗した場合、コードによって自動的に新しい Windows の実装で入力の送信が試行されます。</span><span class="sxs-lookup"><span data-stu-id="da14a-113">If the older implementation fails, the code automatically tries the newer Windows implementation for sending input.</span></span> <span data-ttu-id="da14a-114">さらに、<xref:System.Windows.Forms.SendKeys> クラスで新しい実装を使用すると、キーストロークを別のアプリケーションに送信するときに、<xref:System.Windows.Forms.SendKeys.SendWait%2A> メソッドで現在のスレッドがブロックされなくなります。</span><span class="sxs-lookup"><span data-stu-id="da14a-114">Additionally, when the <xref:System.Windows.Forms.SendKeys> class uses the new implementation, the <xref:System.Windows.Forms.SendKeys.SendWait%2A> method no longer blocks the current thread when sending keystrokes to another application.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="da14a-115">アプリケーションが、オペレーティング システムに関係なく一貫した動作に依存する場合、app.config ファイルに次のアプリケーション設定を追加することで、 <xref:System.Windows.Forms.SendKeys> クラスが新しい実装を使用するよう強制することができます。</span><span class="sxs-lookup"><span data-stu-id="da14a-115">If your application relies on consistent behavior regardless of the operating system, you can force the <xref:System.Windows.Forms.SendKeys> class to use the new implementation by adding the following application setting to your app.config file.</span></span>
>
> ```xml
> <appSettings>
>   <add key="SendKeys" value="SendInput"/>
> </appSettings>
> ```
>
> <span data-ttu-id="da14a-116"><xref:System.Windows.Forms.SendKeys> クラスで前の実装 "_のみ_" を使用するよう強制するには、代わりに値 `"JournalHook"` を使用します。</span><span class="sxs-lookup"><span data-stu-id="da14a-116">To force the <xref:System.Windows.Forms.SendKeys> class to _only_ use the previous implementation, use the value `"JournalHook"` instead.</span></span>

### <a name="to-send-a-keystroke-to-the-same-application"></a><span data-ttu-id="da14a-117">同じアプリケーションにキーストロークを送信するには</span><span class="sxs-lookup"><span data-stu-id="da14a-117">To send a keystroke to the same application</span></span>

<span data-ttu-id="da14a-118"><xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> クラスの <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> メソッドまたは <xref:System.Windows.Forms.SendKeys> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="da14a-118">Call the <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> or <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> method of the <xref:System.Windows.Forms.SendKeys> class.</span></span> <span data-ttu-id="da14a-119">指定されたキーストロークは、アプリケーションのアクティブなコントロールによって受信されます。</span><span class="sxs-lookup"><span data-stu-id="da14a-119">The specified keystrokes will be received by the active control of the application.</span></span>

<span data-ttu-id="da14a-120">次のコード例では、`Send` を使用して、<kbd>ALT</kbd> と <kbd>下方向</kbd> キーを一緒に押すことをシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="da14a-120">The following code example uses `Send` to simulate pressing the <kbd>ALT</kbd> and <kbd>DOWN</kbd> keys together.</span></span> <span data-ttu-id="da14a-121">これらのキーストロークによって、<xref:System.Windows.Forms.ComboBox> コントロールのドロップダウンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="da14a-121">These keystrokes cause the <xref:System.Windows.Forms.ComboBox> control to display its dropdown.</span></span> <span data-ttu-id="da14a-122">この例では、<xref:System.Windows.Forms.Button> と <xref:System.Windows.Forms.ComboBox> がある <xref:System.Windows.Forms.Form> を想定しています。</span><span class="sxs-lookup"><span data-stu-id="da14a-122">This example assumes a <xref:System.Windows.Forms.Form> with a <xref:System.Windows.Forms.Button> and <xref:System.Windows.Forms.ComboBox>.</span></span>

:::code language="csharp" source="snippets/how-to-simulate-events/csharp/Form1.cs" id="ShowDropDown":::
:::code language="vb" source="snippets/how-to-simulate-events/vb/Form1.vb" id="ShowDropDown":::

### <a name="to-send-a-keystroke-to-a-different-application"></a><span data-ttu-id="da14a-123">別のアプリケーションにキーストロークを送信するには</span><span class="sxs-lookup"><span data-stu-id="da14a-123">To send a keystroke to a different application</span></span>

<span data-ttu-id="da14a-124"><xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> と <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> のメソッドは、アクティブなアプリケーション (通常はキーストロークの送信元のアプリケーション) にキーストロークを送信します。</span><span class="sxs-lookup"><span data-stu-id="da14a-124">The <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> and <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> methods send keystrokes to the active application, which is usually the application you're sending keystrokes from.</span></span> <span data-ttu-id="da14a-125">キーストロークを別のアプリケーションに送信するには、まず、それをアクティブ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da14a-125">To send keystrokes to another application, you first need to activate it.</span></span> <span data-ttu-id="da14a-126">別のアプリケーションをアクティブ化するマネージド メソッドがないため、ネイティブ Windows メソッドを使用して他のアプリケーションにフォーカスを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da14a-126">Because there's no managed method to activate another application, you must use native Windows methods to focus the other application.</span></span> <span data-ttu-id="da14a-127">次のコード例は、プラットフォーム呼び出しを使用して `FindWindow` メソッドと `SetForegroundWindow` メソッドを呼び出し、電卓アプリケーションのウィンドウをアクティブ化してから、 `Send` を呼び出して電卓アプリケーションに一連の計算を発行します。</span><span class="sxs-lookup"><span data-stu-id="da14a-127">The following code example uses platform invoke to call the `FindWindow` and `SetForegroundWindow` methods to activate the Calculator application window, and then calls `Send` to issue a series of calculations to the Calculator application.</span></span>

<span data-ttu-id="da14a-128">次のコード例では、`Send` を使用して、Windows 10 電卓アプリケーションでのキーの押下をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="da14a-128">The following code example uses `Send` to simulate pressing keys into the Windows 10 Calculator application.</span></span> <span data-ttu-id="da14a-129">まず、`Calculator` というタイトルのアプリケーション ウィンドウを検索し、アクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="da14a-129">It first searches for an application window with title of `Calculator` and then activates it.</span></span> <span data-ttu-id="da14a-130">アクティブ化したら、10 + 10 を計算するキーストロークが送信されます。</span><span class="sxs-lookup"><span data-stu-id="da14a-130">Once activated, the keystrokes are sent to calculate 10 plus 10.</span></span>

:::code language="csharp" source="snippets/how-to-simulate-events/csharp/Form2.cs" id="Calculator":::
:::code language="vb" source="snippets/how-to-simulate-events/vb/Form2.vb" id="Calculator":::

## <a name="use-oneventname-methods"></a><span data-ttu-id="da14a-131">OnEventName メソッドを使用する</span><span class="sxs-lookup"><span data-stu-id="da14a-131">Use OnEventName methods</span></span>

<span data-ttu-id="da14a-132">キーボード イベントをシミュレートする最も簡単な方法は、イベントを発生させるオブジェクトでメソッドを呼び出すことです。</span><span class="sxs-lookup"><span data-stu-id="da14a-132">The easiest way to simulate keyboard events is to call a method on the object that raises the event.</span></span> <span data-ttu-id="da14a-133">ほとんどのイベントには、それらを呼び出す対応するメソッドがあり、`OnKeyPress` のように `On` の後に `EventName` が続く名前が付けられています。</span><span class="sxs-lookup"><span data-stu-id="da14a-133">Most events have a corresponding method that invokes them, named in the pattern of `On` followed by `EventName`, such as `OnKeyPress`.</span></span> <span data-ttu-id="da14a-134">これらのメソッドは保護されており、コントロールまたはフォームのコンテキストの外部からアクセスすることはできないため、このオプションは、カスタム コントロールまたはフォーム内でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="da14a-134">This option is only possible within custom controls or forms, because these methods are protected and can't be accessed from outside the context of the control or form.</span></span>

<span data-ttu-id="da14a-135">これらの保護されたメソッドは、キーボード イベントをシミュレートするために使用できます。</span><span class="sxs-lookup"><span data-stu-id="da14a-135">These protected methods are available to simulate keyboard events.</span></span>

- `OnKeyDown`
- `OnKeyPress`
- `OnKeyUp`

<span data-ttu-id="da14a-136">これらのイベントの詳細については、「[キーボード イベントの使用 (Windows フォーム .NET)](events.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da14a-136">For more information about these events, see [Using keyboard events (Windows Forms .NET)](events.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="da14a-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="da14a-137">See also</span></span>

- [<span data-ttu-id="da14a-138">キーボードの使用の概要 (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="da14a-138">Overview of using the keyboard (Windows Forms .NET)</span></span>](overview.md)
- [<span data-ttu-id="da14a-139">キーボード イベントの使用 (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="da14a-139">Using keyboard events (Windows Forms .NET)</span></span>](events.md)
- [<span data-ttu-id="da14a-140">マウス イベントの使用 (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="da14a-140">Using mouse events (Windows Forms .NET)</span></span>](../input-mouse/events.md)
- <xref:System.Windows.Forms.SendKeys>
- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.KeyDown>
- <xref:System.Windows.Forms.Control.KeyPress>
