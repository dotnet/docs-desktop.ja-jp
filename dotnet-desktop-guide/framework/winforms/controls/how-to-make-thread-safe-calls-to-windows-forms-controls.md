---
title: コントロールに対してスレッドセーフな呼び出しを行う
ms.date: 02/19/2019
description: スレッドセーフな方法でスレッド間の制御を呼び出すことによって、アプリにマルチスレッドを実装する方法について説明します。
dev_langs:
- csharp
- vb
f1_keywords:
- EHInvalidOperation.WinForms.IllegalCrossThreadCall
helpviewer_keywords:
- thread safety [Windows Forms], calling controls [Windows Forms]
- calling controls [Windows Forms], thread safety [Windows Forms]
- CheckForIllegalCrossThreadCalls property [Windows Forms]
- Windows Forms controls [Windows Forms], multithreading
- BackgroundWorker class [Windows Forms], examples
- threading [Windows Forms], cross-thread calls
- controls [Windows Forms], multithreading
ms.assetid: 138f38b6-1099-4fd5-910c-390b41cbad35
ms.openlocfilehash: b44a37ceb0aec196d78f0a0024fc0350c717e3c2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974818"
---
# <a name="how-to-make-thread-safe-calls-to-windows-forms-controls"></a><span data-ttu-id="cf960-103">方法: Windows フォームコントロールに対してスレッドセーフな呼び出しを行う</span><span class="sxs-lookup"><span data-stu-id="cf960-103">How to: Make thread-safe calls to Windows Forms controls</span></span>

<span data-ttu-id="cf960-104">マルチスレッドは Windows フォームアプリのパフォーマンスを向上させることができますが、Windows フォームコントロールへのアクセスは本質的にスレッドセーフではありません。</span><span class="sxs-lookup"><span data-stu-id="cf960-104">Multithreading can improve the performance of Windows Forms apps, but access to Windows Forms controls isn't inherently thread-safe.</span></span> <span data-ttu-id="cf960-105">マルチスレッドでは、非常に深刻で複雑なバグにコードを公開できます。</span><span class="sxs-lookup"><span data-stu-id="cf960-105">Multithreading can expose your code to very serious and complex bugs.</span></span> <span data-ttu-id="cf960-106">コントロールを操作する2つ以上のスレッドによって、コントロールが一貫性のない状態になり、競合状態、デッドロック、フリーズまたはハングが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cf960-106">Two or more threads manipulating a control can force the control into an inconsistent state and lead to race conditions, deadlocks, and freezes or hangs.</span></span> <span data-ttu-id="cf960-107">アプリにマルチスレッドを実装する場合は、スレッドセーフな方法でスレッド間コントロールを呼び出すようにしてください。</span><span class="sxs-lookup"><span data-stu-id="cf960-107">If you implement multithreading in your app, be sure to call cross-thread controls in a thread-safe way.</span></span> <span data-ttu-id="cf960-108">詳細については、「 [マネージスレッド処理のベストプラクティス](/dotnet/standard/threading/managed-threading-best-practices)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf960-108">For more information, see [Managed threading best practices](/dotnet/standard/threading/managed-threading-best-practices).</span></span>

<span data-ttu-id="cf960-109">コントロールを作成していないスレッドから Windows フォームコントロールを安全に呼び出すには、2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="cf960-109">There are two ways to safely call a Windows Forms control from a thread that didn't create that control.</span></span> <span data-ttu-id="cf960-110">メソッドを使用して、 <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> メインスレッドで作成されたデリゲートを呼び出すことができます。このデリゲートは、コントロールを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="cf960-110">You can use the <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> method to call a delegate created in the main thread, which in turn calls the control.</span></span> <span data-ttu-id="cf960-111">または、を実装できます <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> 。これは、イベントドリブンモデルを使用して、バックグラウンドスレッドで実行された作業を結果のレポートから分離します。</span><span class="sxs-lookup"><span data-stu-id="cf960-111">Or, you can implement a <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>, which uses an event-driven model to separate work done in the background thread from reporting on the results.</span></span>

## <a name="unsafe-cross-thread-calls"></a><span data-ttu-id="cf960-112">安全でないクロススレッド呼び出し</span><span class="sxs-lookup"><span data-stu-id="cf960-112">Unsafe cross-thread calls</span></span>

<span data-ttu-id="cf960-113">コントロールを作成していないスレッドから直接呼び出すことは安全ではありません。</span><span class="sxs-lookup"><span data-stu-id="cf960-113">It's unsafe to call a control directly from a thread that didn't create it.</span></span> <span data-ttu-id="cf960-114">次のコードスニペットは、コントロールへの安全でない呼び出しを示してい <xref:System.Windows.Forms.TextBox?displayProperty=nameWithType> ます。</span><span class="sxs-lookup"><span data-stu-id="cf960-114">The following code snippet illustrates an unsafe call to the <xref:System.Windows.Forms.TextBox?displayProperty=nameWithType> control.</span></span> <span data-ttu-id="cf960-115">`Button1_Click`イベントハンドラーは、 `WriteTextUnsafe` メインスレッドのプロパティを直接設定する新しいスレッドを作成し <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> ます。</span><span class="sxs-lookup"><span data-stu-id="cf960-115">The `Button1_Click` event handler creates a new `WriteTextUnsafe` thread, which sets the main thread's <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> property directly.</span></span>

```csharp
private void Button1_Click(object sender, EventArgs e)
{
    thread2 = new Thread(new ThreadStart(WriteTextUnsafe));
    thread2.Start();
}
private void WriteTextUnsafe()
{
    textBox1.Text = "This text was set unsafely.";
}
```

```vb
Private Sub Button1_Click(ByVal sender As Object, e As EventArgs) Handles Button1.Click
    Thread2 = New Thread(New ThreadStart(AddressOf WriteTextUnsafe))
    Thread2.Start()
End Sub

Private Sub WriteTextUnsafe()
    TextBox1.Text = "This text was set unsafely."
End Sub
```

<span data-ttu-id="cf960-116">Visual Studio デバッガーは、メッセージを使用してを発生 <xref:System.InvalidOperationException> させ、スレッド間の操作が無効であることによって、これらのアンセーフスレッド呼び出しを検出し **ます。コントロール "" が作成されたスレッド以外のスレッドからアクセスされました。**</span><span class="sxs-lookup"><span data-stu-id="cf960-116">The Visual Studio debugger detects these unsafe thread calls by raising an <xref:System.InvalidOperationException> with the message, **Cross-thread operation not valid. Control "" accessed from a thread other than the thread it was created on.**</span></span> <span data-ttu-id="cf960-117">は、 <xref:System.InvalidOperationException> Visual Studio のデバッグ中に安全でないクロススレッド呼び出しに対して常に発生し、アプリの実行時に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cf960-117">The <xref:System.InvalidOperationException> always occurs for unsafe cross-thread calls during Visual Studio debugging, and may occur at app runtime.</span></span> <span data-ttu-id="cf960-118">この問題は解決する必要がありますが、プロパティをに設定することによって例外を無効にすることができ <xref:System.Windows.Forms.Control.CheckForIllegalCrossThreadCalls%2A?displayProperty=nameWithType> `false` ます。</span><span class="sxs-lookup"><span data-stu-id="cf960-118">You should fix the issue, but you can disable the exception by setting the <xref:System.Windows.Forms.Control.CheckForIllegalCrossThreadCalls%2A?displayProperty=nameWithType> property to `false`.</span></span>

## <a name="safe-cross-thread-calls"></a><span data-ttu-id="cf960-119">安全なクロススレッド呼び出し</span><span class="sxs-lookup"><span data-stu-id="cf960-119">Safe cross-thread calls</span></span>

<span data-ttu-id="cf960-120">次のコード例は、作成されていないスレッドから Windows フォームコントロールを安全に呼び出す2つの方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="cf960-120">The following code examples demonstrate two ways to safely call a Windows Forms control from a thread that didn't create it:</span></span>

1. <span data-ttu-id="cf960-121"><xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName>メソッド。このメソッドは、コントロールを呼び出すメインスレッドからデリゲートを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="cf960-121">The <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> method, which calls a delegate from the main thread to call the control.</span></span>
2. <span data-ttu-id="cf960-122"><xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>イベントドリブンモデルを提供するコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="cf960-122">A <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> component, which offers an event-driven model.</span></span>

<span data-ttu-id="cf960-123">どちらの例でも、バックグラウンドスレッドは1秒間スリープして、そのスレッドで実行されている作業をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="cf960-123">In both examples, the background thread sleeps for one second to simulate work being done in that thread.</span></span>

<span data-ttu-id="cf960-124">これらの例は、C# または Visual Basic のコマンドラインから .NET Framework アプリとしてビルドして実行できます。</span><span class="sxs-lookup"><span data-stu-id="cf960-124">You can build and run these examples as .NET Framework apps from the C# or Visual Basic command line.</span></span> <span data-ttu-id="cf960-125">詳細については、「 [csc.exeを使用したコマンドライン ](/dotnet/csharp/language-reference/compiler-options/command-line-building-with-csc-exe) からのビルド」または「 [コマンドラインからのビルド (Visual Basic)](/dotnet/visual-basic/reference/command-line-compiler/building-from-the-command-line)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf960-125">For more information, see [Command-line building with csc.exe](/dotnet/csharp/language-reference/compiler-options/command-line-building-with-csc-exe) or [Build from the command line (Visual Basic)](/dotnet/visual-basic/reference/command-line-compiler/building-from-the-command-line).</span></span>

<span data-ttu-id="cf960-126">.NET Core 3.0 以降では、.NET Core Windows フォーム *\<folder name> .csproj* プロジェクトファイルを持つフォルダーから、Windows .net core アプリとして例をビルドして実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="cf960-126">Starting with .NET Core 3.0, you can also build and run the examples as Windows .NET Core apps from a folder that has a .NET Core Windows Forms *\<folder name>.csproj* project file.</span></span>

## <a name="example-use-the-invoke-method-with-a-delegate"></a><span data-ttu-id="cf960-127">例: デリゲートで Invoke メソッドを使用する</span><span class="sxs-lookup"><span data-stu-id="cf960-127">Example: Use the Invoke method with a delegate</span></span>

<span data-ttu-id="cf960-128">次の例は、Windows フォームコントロールへのスレッドセーフな呼び出しを保証するパターンを示しています。</span><span class="sxs-lookup"><span data-stu-id="cf960-128">The following example demonstrates a pattern for ensuring thread-safe calls to a Windows Forms control.</span></span> <span data-ttu-id="cf960-129">このメソッドは、プロパティに対してクエリを行います。これにより、 <xref:System.Windows.Forms.Control.InvokeRequired%2A?displayProperty=fullName> コントロールの作成スレッド id が呼び出し元のスレッド id と比較されます。</span><span class="sxs-lookup"><span data-stu-id="cf960-129">It queries the <xref:System.Windows.Forms.Control.InvokeRequired%2A?displayProperty=fullName> property, which compares the control's creating thread ID to the calling thread ID.</span></span> <span data-ttu-id="cf960-130">スレッド Id が同じである場合は、コントロールを直接呼び出します。</span><span class="sxs-lookup"><span data-stu-id="cf960-130">If the thread IDs are the same, it calls the control directly.</span></span> <span data-ttu-id="cf960-131">スレッド Id が異なる場合は、 <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=nameWithType> メインスレッドからのデリゲートを使用してメソッドを呼び出します。これにより、コントロールへの実際の呼び出しが行われます。</span><span class="sxs-lookup"><span data-stu-id="cf960-131">If the thread IDs are different, it calls the <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=nameWithType> method with a delegate from the main thread, which makes the actual call to the control.</span></span>

<span data-ttu-id="cf960-132">を使用すると、 `SafeCallDelegate` <xref:System.Windows.Forms.TextBox> コントロールのプロパティを設定でき <xref:System.Windows.Forms.TextBox.Text%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="cf960-132">The `SafeCallDelegate` enables setting the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span> <span data-ttu-id="cf960-133">`WriteTextSafe`メソッドがクエリを <xref:System.Windows.Forms.Control.InvokeRequired%2A> 行います。</span><span class="sxs-lookup"><span data-stu-id="cf960-133">The `WriteTextSafe` method queries <xref:System.Windows.Forms.Control.InvokeRequired%2A>.</span></span> <span data-ttu-id="cf960-134">がを返す場合は、を <xref:System.Windows.Forms.Control.InvokeRequired%2A> `true` `WriteTextSafe` メソッドに渡して、 `SafeCallDelegate` <xref:System.Windows.Forms.Control.Invoke%2A> コントロールへの実際の呼び出しを行います。</span><span class="sxs-lookup"><span data-stu-id="cf960-134">If <xref:System.Windows.Forms.Control.InvokeRequired%2A> returns `true`, `WriteTextSafe` passes the `SafeCallDelegate` to the <xref:System.Windows.Forms.Control.Invoke%2A> method to make the actual call to the control.</span></span> <span data-ttu-id="cf960-135">が <xref:System.Windows.Forms.Control.InvokeRequired%2A> を返す場合は、 `false` を `WriteTextSafe` 直接設定し <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> ます。</span><span class="sxs-lookup"><span data-stu-id="cf960-135">If <xref:System.Windows.Forms.Control.InvokeRequired%2A> returns `false`, `WriteTextSafe` sets the <xref:System.Windows.Forms.TextBox.Text%2A?displayProperty=nameWithType> directly.</span></span> <span data-ttu-id="cf960-136">`Button1_Click`イベントハンドラーは、新しいスレッドを作成し、メソッドを実行し `WriteTextSafe` ます。</span><span class="sxs-lookup"><span data-stu-id="cf960-136">The `Button1_Click` event handler creates the new thread and runs the `WriteTextSafe` method.</span></span>

 [!code-csharp[ThreadSafeCalls#1](~/samples/snippets/winforms/thread-safe/example1/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#1](~/samples/snippets/winforms/thread-safe/example1/vb/Form1.vb)]  

## <a name="example-use-a-backgroundworker-event-handler"></a><span data-ttu-id="cf960-137">例: BackgroundWorker イベントハンドラーを使用する</span><span class="sxs-lookup"><span data-stu-id="cf960-137">Example: Use a BackgroundWorker event handler</span></span>

<span data-ttu-id="cf960-138">マルチスレッドを実装する簡単な方法は、 <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> イベントドリブンモデルを使用するコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="cf960-138">An easy way to implement multithreading is with the <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType> component, which uses an event-driven model.</span></span> <span data-ttu-id="cf960-139">バックグラウンドスレッドは、 <xref:System.ComponentModel.BackgroundWorker.DoWork?displayProperty=nameWithType> メインスレッドと対話しないイベントを実行します。</span><span class="sxs-lookup"><span data-stu-id="cf960-139">The background thread runs the <xref:System.ComponentModel.BackgroundWorker.DoWork?displayProperty=nameWithType> event, which doesn't interact with the main thread.</span></span> <span data-ttu-id="cf960-140">メインスレッドは、 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged?displayProperty=nameWithType> <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted?displayProperty=nameWithType> メインスレッドのコントロールを呼び出すことができるイベントハンドラーとイベントハンドラーを実行します。</span><span class="sxs-lookup"><span data-stu-id="cf960-140">The main thread runs the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged?displayProperty=nameWithType> and <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted?displayProperty=nameWithType> event handlers, which can call the main thread's controls.</span></span>

<span data-ttu-id="cf960-141">を使用してスレッドセーフな呼び出しを行うには <xref:System.ComponentModel.BackgroundWorker> 、バックグラウンドスレッドでメソッドを作成して作業を実行し、イベントにバインドし <xref:System.ComponentModel.BackgroundWorker.DoWork> ます。</span><span class="sxs-lookup"><span data-stu-id="cf960-141">To make a thread-safe call by using <xref:System.ComponentModel.BackgroundWorker>, create a method in the background thread to do the work, and bind it to the <xref:System.ComponentModel.BackgroundWorker.DoWork> event.</span></span> <span data-ttu-id="cf960-142">メインスレッドで別のメソッドを作成して、バックグラウンド作業の結果を報告し、 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> イベントまたはイベントにバインドし <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> ます。</span><span class="sxs-lookup"><span data-stu-id="cf960-142">Create another method in the main thread to report the results of the background work, and bind it to the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> or <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event.</span></span> <span data-ttu-id="cf960-143">バックグラウンドスレッドを開始するには、を呼び出し <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A?displayProperty=nameWithType> ます。</span><span class="sxs-lookup"><span data-stu-id="cf960-143">To start the background thread, call <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="cf960-144">この例では、イベントハンドラーを使用して、 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> <xref:System.Windows.Forms.TextBox> コントロールのプロパティを設定し <xref:System.Windows.Forms.TextBox.Text%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="cf960-144">The example uses the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler to set the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span> <span data-ttu-id="cf960-145">イベントの使用例については <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 、「」を参照してください <xref:System.ComponentModel.BackgroundWorker> 。</span><span class="sxs-lookup"><span data-stu-id="cf960-145">For an example using the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event, see <xref:System.ComponentModel.BackgroundWorker>.</span></span>

 [!code-csharp[ThreadSafeCalls#2](~/samples/snippets/winforms/thread-safe/example2/cs/Form1.cs)]
 [!code-vb[ThreadSafeCalls#2](~/samples/snippets/winforms/thread-safe/example2/vb/Form1.vb)]  

## <a name="see-also"></a><span data-ttu-id="cf960-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="cf960-146">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker>
- [<span data-ttu-id="cf960-147">方法: バックグラウンドで操作を実行する</span><span class="sxs-lookup"><span data-stu-id="cf960-147">How to: Run an operation in the background</span></span>](how-to-run-an-operation-in-the-background.md)
- [<span data-ttu-id="cf960-148">方法: バックグラウンド操作を使用するフォームを実装する</span><span class="sxs-lookup"><span data-stu-id="cf960-148">How to: Implement a form that uses a background operation</span></span>](how-to-implement-a-form-that-uses-a-background-operation.md)
- [<span data-ttu-id="cf960-149">.NET Framework を使用したカスタム Windows フォームコントロールの開発</span><span class="sxs-lookup"><span data-stu-id="cf960-149">Develop custom Windows Forms controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
