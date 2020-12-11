---
title: '方法: マウス イベントとキーボード イベントをコードでシミュレートする'
description: Windows フォームが提供するオプションを使用して、マウスとキーボードの入力をプログラムでシミュレートする方法について説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- keyboards [Windows Forms], event simulation
- user input [Windows Forms], simulating
- SendKeys [Windows Forms], using
- mouse clicks [Windows Forms], simulating
- mouse [Windows Forms], event simulation
ms.assetid: 6abcb67e-3766-4af2-9590-bf5dabd17e41
ms.openlocfilehash: 3c60533479352151ac4f28690413ebc7d8e5879d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983175"
---
# <a name="how-to-simulate-mouse-and-keyboard-events-in-code"></a><span data-ttu-id="fbb6a-103">方法: マウス イベントとキーボード イベントをコードでシミュレートする</span><span class="sxs-lookup"><span data-stu-id="fbb6a-103">How to: Simulate Mouse and Keyboard Events in Code</span></span>

<span data-ttu-id="fbb6a-104">Windows フォームは、プログラムでマウスおよびキーボード入力をシミュレートするためのいくつかのオプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="fbb6a-104">Windows Forms provides several options for programmatically simulating mouse and keyboard input.</span></span> <span data-ttu-id="fbb6a-105">ここでは、これらのオプションの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="fbb6a-105">This topic provides an overview of these options.</span></span>

## <a name="simulating-mouse-input"></a><span data-ttu-id="fbb6a-106">マウス入力のシミュレート</span><span class="sxs-lookup"><span data-stu-id="fbb6a-106">Simulating Mouse Input</span></span>

<span data-ttu-id="fbb6a-107">マウス イベントをシミュレートする最善の方法は、 `On`*EventName* メソッドを呼び出して、シミュレートの対象となるマウス イベントを発生させる方法です。</span><span class="sxs-lookup"><span data-stu-id="fbb6a-107">The best way to simulate mouse events is to call the `On`*EventName* method that raises the mouse event you want to simulate.</span></span> <span data-ttu-id="fbb6a-108">このオプションは、イベントを発生させるメソッドが保護され、コントロールまたはフォームの外部にアクセスできないため、通常はカスタム コントロールおよびフォーム内でのみ可能です。</span><span class="sxs-lookup"><span data-stu-id="fbb6a-108">This option is usually possible only within custom controls and forms, because the methods that raise events are protected and cannot be accessed outside the control or form.</span></span> <span data-ttu-id="fbb6a-109">たとえば、次の手順は、コードでマウスの右ボタンのクリックをシミュレートする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="fbb6a-109">For example, the following steps illustrate how to simulate clicking the right mouse button in code.</span></span>

#### <a name="to-programmatically-click-the-right-mouse-button"></a><span data-ttu-id="fbb6a-110">プログラムでマウスの右ボタンをクリックするには</span><span class="sxs-lookup"><span data-stu-id="fbb6a-110">To programmatically click the right mouse button</span></span>

1. <span data-ttu-id="fbb6a-111"><xref:System.Windows.Forms.MouseEventArgs> プロパティが <xref:System.Windows.Forms.MouseEventArgs.Button%2A> 値に設定された <xref:System.Windows.Forms.MouseButtons.Right?displayProperty=nameWithType> を作成します。</span><span class="sxs-lookup"><span data-stu-id="fbb6a-111">Create a <xref:System.Windows.Forms.MouseEventArgs> whose <xref:System.Windows.Forms.MouseEventArgs.Button%2A> property is set to the <xref:System.Windows.Forms.MouseButtons.Right?displayProperty=nameWithType> value.</span></span>

2. <span data-ttu-id="fbb6a-112">この <xref:System.Windows.Forms.Control.OnMouseClick%2A> を持つ <xref:System.Windows.Forms.MouseEventArgs> メソッドを引数として呼び出します。</span><span class="sxs-lookup"><span data-stu-id="fbb6a-112">Call the <xref:System.Windows.Forms.Control.OnMouseClick%2A> method with this <xref:System.Windows.Forms.MouseEventArgs> as the argument.</span></span>

<span data-ttu-id="fbb6a-113">カスタム コントロールの詳細については、「[デザイン時の Windows フォーム コントロールの開発](./controls/developing-windows-forms-controls-at-design-time.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbb6a-113">For more information on custom controls, see [Developing Windows Forms Controls at Design Time](./controls/developing-windows-forms-controls-at-design-time.md).</span></span>

<span data-ttu-id="fbb6a-114">マウス入力をシミュレートする方法はほかにもあります。</span><span class="sxs-lookup"><span data-stu-id="fbb6a-114">There are other ways to simulate mouse input.</span></span> <span data-ttu-id="fbb6a-115">たとえば、マウス入力によって標準的に設定する状態を表すコントロールのプロパティをプログラムで設定したり ( <xref:System.Windows.Forms.CheckBox.Checked%2A> コントロールの <xref:System.Windows.Forms.CheckBox> プロパティなど)、シミュレートの対象イベントにアタッチされているデリゲートを直接呼び出したりできます。</span><span class="sxs-lookup"><span data-stu-id="fbb6a-115">For example, you can programmatically set a control property that represents a state that is typically set through mouse input (such as the <xref:System.Windows.Forms.CheckBox.Checked%2A> property of the <xref:System.Windows.Forms.CheckBox> control), or you can directly call the delegate that is attached to the event you want to simulate.</span></span>

## <a name="simulating-keyboard-input"></a><span data-ttu-id="fbb6a-116">キーボード入力のシミュレート</span><span class="sxs-lookup"><span data-stu-id="fbb6a-116">Simulating Keyboard Input</span></span>

<span data-ttu-id="fbb6a-117">前述のマウス入力に関する戦略を使用することで、キーボード入力をシミュレートできますが、Windows フォームはアクティブなアプリケーションにキー入力を送信するための <xref:System.Windows.Forms.SendKeys> クラスも提供します。</span><span class="sxs-lookup"><span data-stu-id="fbb6a-117">Although you can simulate keyboard input by using the strategies discussed above for mouse input, Windows Forms also provides the <xref:System.Windows.Forms.SendKeys> class for sending keystrokes to the active application.</span></span>

> [!CAUTION]
> <span data-ttu-id="fbb6a-118">アプリケーションが国際対応し、さまざまなキーボードの使用を想定している場合は、 <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> の使用により予期しない結果になる可能性があるため、回避する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fbb6a-118">If your application is intended for international use with a variety of keyboards, the use of <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> could yield unpredictable results and should be avoided.</span></span>

> [!NOTE]
> <span data-ttu-id="fbb6a-119">.NET Framework 3.0 の <xref:System.Windows.Forms.SendKeys> クラスが更新され、Windows Vista で実行されるアプリケーションで使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="fbb6a-119">The <xref:System.Windows.Forms.SendKeys> class has been updated for the .NET Framework 3.0 to enable its use in applications that run on Windows Vista.</span></span> <span data-ttu-id="fbb6a-120">Windows Vista の強化されたセキュリティ、(ユーザー アカウント制御または UAC と呼ばれます) により、前の実装は想定どおり機能できません。</span><span class="sxs-lookup"><span data-stu-id="fbb6a-120">The enhanced security of Windows Vista (known as User Account Control or UAC) prevents the previous implementation from working as expected.</span></span>
>
> <span data-ttu-id="fbb6a-121"><xref:System.Windows.Forms.SendKeys> クラスはタイミングの問題が発生する可能性があり、一部の開発者は回避策を取る必要がありました。</span><span class="sxs-lookup"><span data-stu-id="fbb6a-121">The <xref:System.Windows.Forms.SendKeys> class is susceptible to timing issues, which some developers have had to work around.</span></span> <span data-ttu-id="fbb6a-122">更新された実装は、引き続きタイミングの問題が発生する可能性がありますが、速度が少し向上し、回避策の変更が必要となる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fbb6a-122">The updated implementation is still susceptible to timing issues, but is slightly faster and may require changes to the workarounds.</span></span> <span data-ttu-id="fbb6a-123"><xref:System.Windows.Forms.SendKeys> クラスは、最初に前の実装を使用しようとし、失敗した場合に、新しい実装を使用します。</span><span class="sxs-lookup"><span data-stu-id="fbb6a-123">The <xref:System.Windows.Forms.SendKeys> class tries to use the previous implementation first, and if that fails, uses the new implementation.</span></span> <span data-ttu-id="fbb6a-124">その結果、 <xref:System.Windows.Forms.SendKeys> クラスが別のオペレーティング システムと異なる動作を取る可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fbb6a-124">As a result, the <xref:System.Windows.Forms.SendKeys> class may behave differently on different operating systems.</span></span> <span data-ttu-id="fbb6a-125">さらに、 <xref:System.Windows.Forms.SendKeys> クラスは、新しい実装を使用した場合、 <xref:System.Windows.Forms.SendKeys.SendWait%2A> メソッドが別のプロセスに送信されたときにメッセージの処理を待機しません。</span><span class="sxs-lookup"><span data-stu-id="fbb6a-125">Additionally, when the <xref:System.Windows.Forms.SendKeys> class uses the new implementation, the <xref:System.Windows.Forms.SendKeys.SendWait%2A> method will not wait for messages to be processed when they are sent to another process.</span></span>
>
> <span data-ttu-id="fbb6a-126">アプリケーションが、オペレーティング システムに関係なく一貫した動作に依存する場合、app.config ファイルに次のアプリケーション設定を追加することで、 <xref:System.Windows.Forms.SendKeys> クラスが新しい実装を使用するよう強制することができます。</span><span class="sxs-lookup"><span data-stu-id="fbb6a-126">If your application relies on consistent behavior regardless of the operating system, you can force the <xref:System.Windows.Forms.SendKeys> class to use the new implementation by adding the following application setting to your app.config file.</span></span>
>
> ```xml
> <appSettings>
>  <add key="SendKeys" value="SendInput"/>
> </appSettings>
> ```
>
> <span data-ttu-id="fbb6a-127"><xref:System.Windows.Forms.SendKeys> クラスが前の実装を使用するよう強制するには、代わりに値 `"JournalHook"` を使用します。</span><span class="sxs-lookup"><span data-stu-id="fbb6a-127">To force the <xref:System.Windows.Forms.SendKeys> class to use the previous implementation, use the value `"JournalHook"` instead.</span></span>

#### <a name="to-send-a-keystroke-to-the-same-application"></a><span data-ttu-id="fbb6a-128">同じアプリケーションにキーストロークを送信するには</span><span class="sxs-lookup"><span data-stu-id="fbb6a-128">To send a keystroke to the same application</span></span>

1. <span data-ttu-id="fbb6a-129"><xref:System.Windows.Forms.SendKeys.Send%2A> クラスの <xref:System.Windows.Forms.SendKeys.SendWait%2A> メソッドまたは <xref:System.Windows.Forms.SendKeys> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="fbb6a-129">Call the <xref:System.Windows.Forms.SendKeys.Send%2A> or <xref:System.Windows.Forms.SendKeys.SendWait%2A> method of the <xref:System.Windows.Forms.SendKeys> class.</span></span> <span data-ttu-id="fbb6a-130">指定されたキーストロークは、アプリケーションのアクティブなコントロールによって受信されます。</span><span class="sxs-lookup"><span data-stu-id="fbb6a-130">The specified keystrokes will be received by the active control of the application.</span></span> <span data-ttu-id="fbb6a-131">次のコード例では、 <xref:System.Windows.Forms.SendKeys.Send%2A> を使用して、ユーザーがフォームのサーフェイスをダブルクリックしたときに、ENTER キーを押す操作をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="fbb6a-131">The following code example uses <xref:System.Windows.Forms.SendKeys.Send%2A> to simulate pressing the ENTER key when the user double-clicks the surface of the form.</span></span> <span data-ttu-id="fbb6a-132">この例では、0 のタブ インデックスを持つ単一の <xref:System.Windows.Forms.Form> コントロールがある <xref:System.Windows.Forms.Button> を想定しています。</span><span class="sxs-lookup"><span data-stu-id="fbb6a-132">This example assumes a <xref:System.Windows.Forms.Form> with a single <xref:System.Windows.Forms.Button> control that has a tab index of 0.</span></span>

    [!code-cpp[System.Windows.Forms.SimulateKeyPress#10](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/cpp/form1.cpp#10)]
    [!code-csharp[System.Windows.Forms.SimulateKeyPress#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/CS/form1.cs#10)]
    [!code-vb[System.Windows.Forms.SimulateKeyPress#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/VB/form1.vb#10)]

#### <a name="to-send-a-keystroke-to-a-different-application"></a><span data-ttu-id="fbb6a-133">別のアプリケーションにキーストロークを送信するには</span><span class="sxs-lookup"><span data-stu-id="fbb6a-133">To send a keystroke to a different application</span></span>

1. <span data-ttu-id="fbb6a-134">キー入力を受信するアプリケーション ウィンドウをアクティブ化し、 <xref:System.Windows.Forms.SendKeys.Send%2A> メソッドまたは <xref:System.Windows.Forms.SendKeys.SendWait%2A> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="fbb6a-134">Activate the application window that will receive the keystrokes, and then call the <xref:System.Windows.Forms.SendKeys.Send%2A> or <xref:System.Windows.Forms.SendKeys.SendWait%2A> method.</span></span> <span data-ttu-id="fbb6a-135">別のアプリケーションをアクティブ化するマネージド メソッドがないため、ネイティブ Windows メソッドを使用して他のアプリケーションにフォーカスを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fbb6a-135">Because there is no managed method to activate another application, you must use native Windows methods to force focus on other applications.</span></span> <span data-ttu-id="fbb6a-136">次のコード例は、プラットフォーム呼び出しを使用して `FindWindow` メソッドと `SetForegroundWindow` メソッドを呼び出し、電卓アプリケーションのウィンドウをアクティブ化してから、 <xref:System.Windows.Forms.SendKeys.SendWait%2A> を呼び出して電卓アプリケーションに一連の計算を発行します。</span><span class="sxs-lookup"><span data-stu-id="fbb6a-136">The following code example uses platform invoke to call the `FindWindow` and `SetForegroundWindow` methods to activate the Calculator application window, and then calls <xref:System.Windows.Forms.SendKeys.SendWait%2A> to issue a series of calculations to the Calculator application.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fbb6a-137">電卓アプリケーションを特定する `FindWindow` 呼び出しの適切なパラメーターは、Windows のバージョンに応じて異なります。</span><span class="sxs-lookup"><span data-stu-id="fbb6a-137">The correct parameters of the `FindWindow` call that locates the Calculator application vary based on your version of Windows.</span></span>  <span data-ttu-id="fbb6a-138">次のコードは、Windows 7 の電卓アプリケーションを検索します。</span><span class="sxs-lookup"><span data-stu-id="fbb6a-138">The following code finds the Calculator application on Windows 7.</span></span> <span data-ttu-id="fbb6a-139">Windows Vista では、最初のパラメーターを "Scて c" に変更します。</span><span class="sxs-lookup"><span data-stu-id="fbb6a-139">On Windows Vista, change the first parameter to "SciCalc".</span></span> <span data-ttu-id="fbb6a-140">Visual Studio に付属の Spy++ ツールを使用して、適切なパラメーターを特定します。</span><span class="sxs-lookup"><span data-stu-id="fbb6a-140">You can use the Spy++ tool, included with Visual Studio, to determine the correct parameters.</span></span>

    [!code-cpp[System.Windows.Forms.SimulateKeyPress#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/cpp/form1.cpp#5)]
    [!code-csharp[System.Windows.Forms.SimulateKeyPress#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/CS/form1.cs#5)]
    [!code-vb[System.Windows.Forms.SimulateKeyPress#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/VB/form1.vb#5)]

## <a name="example"></a><span data-ttu-id="fbb6a-141">例</span><span class="sxs-lookup"><span data-stu-id="fbb6a-141">Example</span></span>

<span data-ttu-id="fbb6a-142">次のコード例は、前のコード例の完全なアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="fbb6a-142">The following code example is the complete application for the previous code examples.</span></span>

[!code-cpp[System.Windows.Forms.SimulateKeyPress#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/cpp/form1.cpp#0)]
[!code-csharp[System.Windows.Forms.SimulateKeyPress#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/CS/form1.cs#0)]
[!code-vb[System.Windows.Forms.SimulateKeyPress#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/VB/form1.vb#0)]

## <a name="compiling-the-code"></a><span data-ttu-id="fbb6a-143">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="fbb6a-143">Compiling the Code</span></span>

<span data-ttu-id="fbb6a-144">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fbb6a-144">This example requires:</span></span>

- <span data-ttu-id="fbb6a-145">System、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="fbb6a-145">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>

## <a name="see-also"></a><span data-ttu-id="fbb6a-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="fbb6a-146">See also</span></span>

- [<span data-ttu-id="fbb6a-147">Windows フォームでのユーザー入力</span><span class="sxs-lookup"><span data-stu-id="fbb6a-147">User Input in Windows Forms</span></span>](user-input-in-windows-forms.md)
