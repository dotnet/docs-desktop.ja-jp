---
title: 'チュートリアル: バックグラウンド操作を使用するフォームの実装'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [Windows Forms], forms
- BackgroundWorker component
- background tasks
- forms [Windows Forms], multithreading
- threading [Windows Forms], walkthroughs
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: 4691b796-9200-471a-89c3-ba4c7cc78c03
ms.openlocfilehash: bdd82b0f32f93fbcdd5713bfb9ba9081f653298b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982719"
---
# <a name="walkthrough-implementing-a-form-that-uses-a-background-operation"></a><span data-ttu-id="ce1c4-102">チュートリアル: バックグラウンド操作を使用するフォームの実装</span><span class="sxs-lookup"><span data-stu-id="ce1c4-102">Walkthrough: Implementing a Form That Uses a Background Operation</span></span>

<span data-ttu-id="ce1c4-103">完了までに時間がかかる操作があり、ユーザーインターフェイス (UI) が応答を停止したりブロックしたりしないようにするには、クラスを使用して <xref:System.ComponentModel.BackgroundWorker> 別のスレッドで操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-103">If you have an operation that will take a long time to complete, and you do not want your user interface (UI) to stop responding or to block, you can use the <xref:System.ComponentModel.BackgroundWorker> class to execute the operation on another thread.</span></span>

<span data-ttu-id="ce1c4-104">このチュートリアルでは、 <xref:System.ComponentModel.BackgroundWorker> ユーザーインターフェイスの応答性を維持したまま、クラスを使用して時間のかかる計算をバックグラウンドで実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-104">This walkthrough illustrates how to use the <xref:System.ComponentModel.BackgroundWorker> class to perform time-consuming computations "in the background," while the user interface remains responsive.</span></span>  <span data-ttu-id="ce1c4-105">このチュートリアルを完了すると、フィボナッチ数を非同期に計算するアプリケーションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-105">When you are through, you will have an application that computes Fibonacci numbers asynchronously.</span></span> <span data-ttu-id="ce1c4-106">大きなフィボナッチ数の計算にはかなりの時間がかかることがありますが、この遅延によってメイン UI スレッドが中断されることはなく、計算中もフォームは応答性を維持します。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-106">Even though computing a large Fibonacci number can take a noticeable amount of time, the main UI thread will not be interrupted by this delay, and the form will be responsive during the calculation.</span></span>

<span data-ttu-id="ce1c4-107">このチュートリアルでは、以下のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-107">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="ce1c4-108">Windows ベースのアプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="ce1c4-108">Creating a Windows-based Application</span></span>

- <span data-ttu-id="ce1c4-109">フォームでのの作成 <xref:System.ComponentModel.BackgroundWorker></span><span class="sxs-lookup"><span data-stu-id="ce1c4-109">Creating a <xref:System.ComponentModel.BackgroundWorker> in Your Form</span></span>

- <span data-ttu-id="ce1c4-110">非同期イベント ハンドラーの追加</span><span class="sxs-lookup"><span data-stu-id="ce1c4-110">Adding Asynchronous Event Handlers</span></span>

- <span data-ttu-id="ce1c4-111">進行状況の報告とキャンセルのサポートの追加</span><span class="sxs-lookup"><span data-stu-id="ce1c4-111">Adding Progress Reporting and Support for Cancellation</span></span>

<span data-ttu-id="ce1c4-112">この例で使用するコード全体については、「[方法 : バックグラウンド操作を使用するフォームを実装する](how-to-implement-a-form-that-uses-a-background-operation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-112">For a complete listing of the code used in this example, see [How to: Implement a Form That Uses a Background Operation](how-to-implement-a-form-that-uses-a-background-operation.md).</span></span>

## <a name="create-a-form-that-uses-a-background-operation"></a><span data-ttu-id="ce1c4-113">バックグラウンド操作を使用するフォームを作成する</span><span class="sxs-lookup"><span data-stu-id="ce1c4-113">Create a form that uses a background operation</span></span>

1. <span data-ttu-id="ce1c4-114">Visual Studio で、という名前の Windows ベースのアプリケーションプロジェクトを作成 `BackgroundWorkerExample` します ([**ファイル**] [  >  **新しい**  >  **プロジェクト**] [  >  **Visual C#** ] または [ **Visual Basic**  >  **クラシックデスクトップ**  >  **Windows フォームアプリケーション**])。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-114">In Visual Studio, create a Windows-based application project called `BackgroundWorkerExample` (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="ce1c4-115">**ソリューション エクスプローラー** で、**[Form1]** を右クリックし、ショートカット メニューの **[名前の変更]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-115">In **Solution Explorer**, right-click **Form1** and select **Rename** from the shortcut menu.</span></span> <span data-ttu-id="ce1c4-116">ファイル名を `FibonacciCalculator` に変更します。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-116">Change the file name to `FibonacciCalculator`.</span></span> <span data-ttu-id="ce1c4-117">コード要素 "`Form1`" へのすべての参照の名前を変更するかどうかをたずねられたら、**[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-117">Click the **Yes** button when you are asked if you want to rename all references to the code element '`Form1`'.</span></span>

3. <span data-ttu-id="ce1c4-118"><xref:System.Windows.Forms.NumericUpDown>**ツールボックス** からコントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-118">Drag a <xref:System.Windows.Forms.NumericUpDown> control from the **Toolbox** onto the form.</span></span> <span data-ttu-id="ce1c4-119">プロパティを <xref:System.Windows.Forms.NumericUpDown.Minimum%2A> に設定し `1` 、 <xref:System.Windows.Forms.NumericUpDown.Maximum%2A> プロパティをに設定し `91` ます。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-119">Set the <xref:System.Windows.Forms.NumericUpDown.Minimum%2A> property to `1` and the <xref:System.Windows.Forms.NumericUpDown.Maximum%2A> property to `91`.</span></span>

4. <span data-ttu-id="ce1c4-120"><xref:System.Windows.Forms.Button>フォームに2つのコントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-120">Add two <xref:System.Windows.Forms.Button> controls to the form.</span></span>

5. <span data-ttu-id="ce1c4-121">最初のコントロールの名前を変更 <xref:System.Windows.Forms.Button> `startAsyncButton` し、 <xref:System.Windows.Forms.Control.Text%2A> プロパティをに設定し `Start Async` ます。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-121">Rename the first <xref:System.Windows.Forms.Button> control `startAsyncButton` and set the <xref:System.Windows.Forms.Control.Text%2A> property to `Start Async`.</span></span> <span data-ttu-id="ce1c4-122">2つ目のコントロールの名前を変更 <xref:System.Windows.Forms.Button> `cancelAsyncButton` し、 <xref:System.Windows.Forms.Control.Text%2A> プロパティをに設定し `Cancel Async` ます。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-122">Rename the second <xref:System.Windows.Forms.Button> control `cancelAsyncButton`, and set the <xref:System.Windows.Forms.Control.Text%2A> property to `Cancel Async`.</span></span> <span data-ttu-id="ce1c4-123"><xref:System.Windows.Forms.Control.Enabled%2A>プロパティをに設定 `false` します。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-123">Set its <xref:System.Windows.Forms.Control.Enabled%2A> property to `false`.</span></span>

6. <span data-ttu-id="ce1c4-124">両方のコントロールのイベントに対してイベントハンドラーを作成 <xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.Control.Click> します。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-124">Create an event handler for both of the <xref:System.Windows.Forms.Button> controls' <xref:System.Windows.Forms.Control.Click> events.</span></span> <span data-ttu-id="ce1c4-125">詳細については、「[方法 : デザイナーを使用してイベント ハンドラーを作成する](/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-125">For details, see [How to: Create Event Handlers Using the Designer](/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)).</span></span>

7. <span data-ttu-id="ce1c4-126"><xref:System.Windows.Forms.Label>**ツールボックス** からコントロールをフォームにドラッグし、名前を変更 `resultLabel` します。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-126">Drag a <xref:System.Windows.Forms.Label> control from the **Toolbox** onto the form and rename it `resultLabel`.</span></span>

8. <span data-ttu-id="ce1c4-127"><xref:System.Windows.Forms.ProgressBar>**ツールボックス** からコントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-127">Drag a <xref:System.Windows.Forms.ProgressBar> control from the **Toolbox** onto the form.</span></span>

## <a name="create-a-backgroundworker-with-the-designer"></a><span data-ttu-id="ce1c4-128">デザイナーを使用して BackgroundWorker を作成する</span><span class="sxs-lookup"><span data-stu-id="ce1c4-128">Create a BackgroundWorker with the Designer</span></span>

<span data-ttu-id="ce1c4-129"><xref:System.ComponentModel.BackgroundWorker> **Windows** **フォームデザイナー** を使用して、非同期操作のを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-129">You can create the <xref:System.ComponentModel.BackgroundWorker> for your asynchronous operation using the **Windows** **Forms Designer**.</span></span>

<span data-ttu-id="ce1c4-130">[**ツールボックス**] の [**コンポーネント**] タブから、を <xref:System.ComponentModel.BackgroundWorker> フォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-130">From the **Components** tab of the **Toolbox**, drag a <xref:System.ComponentModel.BackgroundWorker> onto the form.</span></span>

## <a name="add-asynchronous-event-handlers"></a><span data-ttu-id="ce1c4-131">非同期イベントハンドラーの追加</span><span class="sxs-lookup"><span data-stu-id="ce1c4-131">Add asynchronous event handlers</span></span>

<span data-ttu-id="ce1c4-132">これで、 <xref:System.ComponentModel.BackgroundWorker> コンポーネントの非同期イベントのイベントハンドラーを追加する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-132">You are now ready to add event handlers for the <xref:System.ComponentModel.BackgroundWorker> component's asynchronous events.</span></span> <span data-ttu-id="ce1c4-133">バックグラウンドで実行される時間のかかる操作 (フィボナッチ数の計算) は、これらのイベント ハンドラーのいずれかによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-133">The time-consuming operation that will run in the background, which computes Fibonacci numbers, is called by one of these event handlers.</span></span>

1. <span data-ttu-id="ce1c4-134">[ **プロパティ** ] ウィンドウで、コンポーネントを選択した状態で、 <xref:System.ComponentModel.BackgroundWorker> [ **イベント** ] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-134">In the **Properties** window, with the <xref:System.ComponentModel.BackgroundWorker> component still selected, click the **Events** button.</span></span> <span data-ttu-id="ce1c4-135">イベントとイベントをダブルクリックして、 <xref:System.ComponentModel.BackgroundWorker.DoWork> <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> イベントハンドラーを作成します。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-135">Double-click the <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> events to create event handlers.</span></span> <span data-ttu-id="ce1c4-136">イベント ハンドラーの使用方法の詳細については、「[方法 : デザイナーを使用してイベント ハンドラーを作成する](/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-136">For more information about how to use event handlers, see [How to: Create Event Handlers Using the Designer](/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)).</span></span>

2. <span data-ttu-id="ce1c4-137">フォームで `ComputeFibonacci` という新しいメソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-137">Create a new method, called `ComputeFibonacci`, in your form.</span></span> <span data-ttu-id="ce1c4-138">このメソッドがバックグラウンドで実行され、実際の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-138">This method does the actual work, and it will run in the background.</span></span> <span data-ttu-id="ce1c4-139">このコードは、フィボナッチ アルゴリズムの再帰的実装を示しています。これは、非常に非効率であり、数が大きくなるにつれて、完了までの所要時間が急激に増大します。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-139">This code demonstrates the recursive implementation of the Fibonacci algorithm, which is notably inefficient, taking exponentially longer time to complete for larger numbers.</span></span> <span data-ttu-id="ce1c4-140">ここでは、アプリケーションで長時間の遅延が発生する可能性のある操作を示すために、このコードを使用しています。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-140">It is used here for illustrative purposes, to show an operation that can introduce long delays in your application.</span></span>

     [!code-cpp[System.ComponentModel.BackgroundWorker#10](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#10)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#10)]
     [!code-vb[System.ComponentModel.BackgroundWorker#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#10)]

3. <span data-ttu-id="ce1c4-141"><xref:System.ComponentModel.BackgroundWorker.DoWork>イベントハンドラーで、メソッドの呼び出しを追加し `ComputeFibonacci` ます。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-141">In the <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler, add a call to the `ComputeFibonacci` method.</span></span> <span data-ttu-id="ce1c4-142">のプロパティからの最初のパラメーターを取得し `ComputeFibonacci` <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> <xref:System.ComponentModel.DoWorkEventArgs> ます。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-142">Take the first parameter for `ComputeFibonacci` from the <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> property of the <xref:System.ComponentModel.DoWorkEventArgs>.</span></span> <span data-ttu-id="ce1c4-143"><xref:System.ComponentModel.BackgroundWorker>およびパラメーターは、 <xref:System.ComponentModel.DoWorkEventArgs> 後で進行状況の報告とキャンセルのサポートに使用されます。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-143">The <xref:System.ComponentModel.BackgroundWorker> and <xref:System.ComponentModel.DoWorkEventArgs> parameters will be used later for progress reporting and cancellation support.</span></span> <span data-ttu-id="ce1c4-144">の戻り値をの `ComputeFibonacci` プロパティに代入し <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> <xref:System.ComponentModel.DoWorkEventArgs> ます。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-144">Assign the return value from `ComputeFibonacci` to the <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> property of the <xref:System.ComponentModel.DoWorkEventArgs>.</span></span> <span data-ttu-id="ce1c4-145">この結果は、イベントハンドラーで使用できるようになり <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> ます。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-145">This result will be available to the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ce1c4-146"><xref:System.ComponentModel.BackgroundWorker.DoWork>イベントハンドラーはインスタンス変数を直接参照しません。これは、この `backgroundWorker1` イベントハンドラーをの特定のインスタンスに対して行うため <xref:System.ComponentModel.BackgroundWorker> です。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-146">The <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler does not reference the `backgroundWorker1` instance variable directly, as this would couple this event handler to a specific instance of <xref:System.ComponentModel.BackgroundWorker>.</span></span> <span data-ttu-id="ce1c4-147">代わりに、 <xref:System.ComponentModel.BackgroundWorker> このイベントを発生させたへの参照がパラメーターから回復され `sender` ます。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-147">Instead, a reference to the <xref:System.ComponentModel.BackgroundWorker> that raised this event is recovered from the `sender` parameter.</span></span> <span data-ttu-id="ce1c4-148">これは、フォームが複数のをホストする場合に重要です <xref:System.ComponentModel.BackgroundWorker> 。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-148">This is important when the form hosts more than one <xref:System.ComponentModel.BackgroundWorker>.</span></span> <span data-ttu-id="ce1c4-149">また、イベントハンドラー内のユーザーインターフェイスオブジェクトを操作しないことも重要です <xref:System.ComponentModel.BackgroundWorker.DoWork> 。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-149">It is also important not to manipulate any user-interface objects in your <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler.</span></span> <span data-ttu-id="ce1c4-150">代わりに、イベントを使用してユーザーインターフェイスと通信し <xref:System.ComponentModel.BackgroundWorker> ます。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-150">Instead, communicate to the user interface through the <xref:System.ComponentModel.BackgroundWorker> events.</span></span>

     [!code-cpp[System.ComponentModel.BackgroundWorker#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#5)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#5)]
     [!code-vb[System.ComponentModel.BackgroundWorker#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#5)]

4. <span data-ttu-id="ce1c4-151">`startAsyncButton`コントロールの <xref:System.Windows.Forms.Control.Click> イベントハンドラーに、非同期操作を開始するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-151">In the `startAsyncButton` control's <xref:System.Windows.Forms.Control.Click> event handler, add the code that starts the asynchronous operation.</span></span>

     [!code-cpp[System.ComponentModel.BackgroundWorker#13](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#13)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#13)]
     [!code-vb[System.ComponentModel.BackgroundWorker#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#13)]

5. <span data-ttu-id="ce1c4-152"><xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>イベントハンドラーで、計算の結果をコントロールに割り当て `resultLabel` ます。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-152">In the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler, assign the result of the calculation to the `resultLabel` control.</span></span>

     [!code-cpp[System.ComponentModel.BackgroundWorker#6](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#6)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#6)]
     [!code-vb[System.ComponentModel.BackgroundWorker#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#6)]

## <a name="adding-progress-reporting-and-support-for-cancellation"></a><span data-ttu-id="ce1c4-153">進行状況の報告とキャンセルのサポートの追加</span><span class="sxs-lookup"><span data-stu-id="ce1c4-153">Adding Progress Reporting and Support for Cancellation</span></span>

<span data-ttu-id="ce1c4-154">時間のかかる非同期操作では、多くの場合、進行状況をユーザーに報告し、ユーザーが操作をキャンセルできるようにすることが望まれます。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-154">For asynchronous operations that will take a long time, it is often desirable to report progress to the user and to allow the user to cancel the operation.</span></span> <span data-ttu-id="ce1c4-155">クラスには、 <xref:System.ComponentModel.BackgroundWorker> バックグラウンド操作の進行に応じて進行状況を通知するためのイベントが用意されています。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-155">The <xref:System.ComponentModel.BackgroundWorker> class provides an event that allows you to post progress as your background operation proceeds.</span></span> <span data-ttu-id="ce1c4-156">また、ワーカーコードがの呼び出しを検出してそれ自体を中断できるようにするフラグも提供し <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-156">It also provides a flag that allows your worker code to detect a call to <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> and interrupt itself.</span></span>

### <a name="implement-progress-reporting"></a><span data-ttu-id="ce1c4-157">進行状況レポートを実装する</span><span class="sxs-lookup"><span data-stu-id="ce1c4-157">Implement progress reporting</span></span>

1. <span data-ttu-id="ce1c4-158">**[プロパティ]** ウィンドウで `backgroundWorker1` を選択します。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-158">In the **Properties**, window, select `backgroundWorker1`.</span></span> <span data-ttu-id="ce1c4-159"><xref:System.ComponentModel.BackgroundWorker.WorkerReportsProgress%2A> と <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> プロパティを `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-159">Set the <xref:System.ComponentModel.BackgroundWorker.WorkerReportsProgress%2A> and <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> properties to `true`.</span></span>

2. <span data-ttu-id="ce1c4-160">`FibonacciCalculator` フォームで 2 つの変数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-160">Declare two variables in the `FibonacciCalculator` form.</span></span> <span data-ttu-id="ce1c4-161">これらの変数を使用して進行状況を追跡します。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-161">These will be used to track progress.</span></span>

     [!code-cpp[System.ComponentModel.BackgroundWorker#14](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#14)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#14](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#14)]
     [!code-vb[System.ComponentModel.BackgroundWorker#14](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#14)]

3. <span data-ttu-id="ce1c4-162"><xref:System.ComponentModel.BackgroundWorker.ProgressChanged> イベントのイベント ハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-162">Add an event handler for the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event.</span></span> <span data-ttu-id="ce1c4-163"><xref:System.ComponentModel.BackgroundWorker.ProgressChanged>イベントハンドラーで、 <xref:System.Windows.Forms.ProgressBar> パラメーターのプロパティを使用してを更新し <xref:System.ComponentModel.ProgressChangedEventArgs.ProgressPercentage%2A> <xref:System.ComponentModel.ProgressChangedEventArgs> ます。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-163">In the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event handler, update the <xref:System.Windows.Forms.ProgressBar> with the <xref:System.ComponentModel.ProgressChangedEventArgs.ProgressPercentage%2A> property of the <xref:System.ComponentModel.ProgressChangedEventArgs> parameter.</span></span>

     [!code-cpp[System.ComponentModel.BackgroundWorker#7](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#7)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#7)]
     [!code-vb[System.ComponentModel.BackgroundWorker#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#7)]

### <a name="implement-support-for-cancellation"></a><span data-ttu-id="ce1c4-164">キャンセルのサポートを実装する</span><span class="sxs-lookup"><span data-stu-id="ce1c4-164">Implement support for cancellation</span></span>

1. <span data-ttu-id="ce1c4-165">`cancelAsyncButton`コントロールの <xref:System.Windows.Forms.Control.Click> イベントハンドラーに、非同期操作をキャンセルするコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-165">In the `cancelAsyncButton` control's <xref:System.Windows.Forms.Control.Click> event handler, add the code that cancels the asynchronous operation.</span></span>

     [!code-cpp[System.ComponentModel.BackgroundWorker#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#4)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#4)]
     [!code-vb[System.ComponentModel.BackgroundWorker#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#4)]

2. <span data-ttu-id="ce1c4-166">`ComputeFibonacci` メソッドの次のコード フラグメントは、進行状況の報告とキャンセルのサポートを示しています。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-166">The following code fragments in the `ComputeFibonacci` method report progress and support cancellation.</span></span>

     [!code-cpp[System.ComponentModel.BackgroundWorker#11](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#11)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#11)]
     [!code-vb[System.ComponentModel.BackgroundWorker#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#11)]
    [!code-cpp[System.ComponentModel.BackgroundWorker#12](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#12)]
    [!code-csharp[System.ComponentModel.BackgroundWorker#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#12)]
    [!code-vb[System.ComponentModel.BackgroundWorker#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#12)]

## <a name="checkpoint"></a><span data-ttu-id="ce1c4-167">Checkpoint</span><span class="sxs-lookup"><span data-stu-id="ce1c4-167">Checkpoint</span></span>

<span data-ttu-id="ce1c4-168">この時点で、フィボナッチ電卓アプリケーションをコンパイルして実行できます。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-168">At this point, you can compile and run the Fibonacci Calculator application.</span></span>

<span data-ttu-id="ce1c4-169">**F5** キーを押して、アプリケーションをコンパイルして実行します。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-169">Press **F5** to compile and run the application.</span></span>

<span data-ttu-id="ce1c4-170">計算がバックグラウンドで実行されている間、 <xref:System.Windows.Forms.ProgressBar> 計算の進行状況が完了するまで表示されます。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-170">While the calculation is running in the background, you will see the <xref:System.Windows.Forms.ProgressBar> displaying the progress of the calculation toward completion.</span></span> <span data-ttu-id="ce1c4-171">また、保留中の操作をキャンセルすることもできます。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-171">You can also cancel the pending operation.</span></span>

<span data-ttu-id="ce1c4-172">数値が小さい場合、計算に時間はかかりませんが、数値が大きくなると、大幅な遅延が発生します。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-172">For small numbers, the calculation should be very fast, but for larger numbers, you should see a noticeable delay.</span></span> <span data-ttu-id="ce1c4-173">30 以上の値を入力した場合、コンピューターの速度によっては数秒の遅延が発生します。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-173">If you enter a value of 30 or greater, you should see a delay of several seconds, depending on the speed of your computer.</span></span> <span data-ttu-id="ce1c4-174">値が 40 を超えると、計算が終了するまでに数分から数時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-174">For values greater than 40, it may take minutes or hours to finish the calculation.</span></span> <span data-ttu-id="ce1c4-175">電卓が大きなフィボナッチ数を計算している間も、フォームの移動、最小化、最大化を自由に行うことができ、フォームを閉じることもできます。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-175">While the calculator is busy computing a large Fibonacci number, notice that you can freely move the form around, minimize, maximize, and even dismiss it.</span></span> <span data-ttu-id="ce1c4-176">これは、メイン UI スレッドが計算の終了を待機していないためです。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-176">This is because the main UI thread is not waiting for the calculation to finish.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ce1c4-177">次のステップ</span><span class="sxs-lookup"><span data-stu-id="ce1c4-177">Next steps</span></span>

<span data-ttu-id="ce1c4-178">コンポーネントを使用してバックグラウンドで計算を実行するフォームを実装したので <xref:System.ComponentModel.BackgroundWorker> 、非同期操作の他の可能性を調べることができます。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-178">Now that you have implemented a form that uses a <xref:System.ComponentModel.BackgroundWorker> component to execute a computation in the background, you can explore other possibilities for asynchronous operations:</span></span>

- <span data-ttu-id="ce1c4-179">複数 <xref:System.ComponentModel.BackgroundWorker> のオブジェクトを同時操作に使用します。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-179">Use multiple <xref:System.ComponentModel.BackgroundWorker> objects for several simultaneous operations.</span></span>

- <span data-ttu-id="ce1c4-180">マルチスレッド アプリケーションをデバッグする方法については、「[方法 : [スレッド] ウィンドウを使用する](/visualstudio/debugger/how-to-use-the-threads-window)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-180">To debug your multithreaded application, see [How to: Use the Threads Window](/visualstudio/debugger/how-to-use-the-threads-window).</span></span>

- <span data-ttu-id="ce1c4-181">非同期プログラミング モデルをサポートする独自のコンポーネントを実装する。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-181">Implement your own component that supports the asynchronous programming model.</span></span> <span data-ttu-id="ce1c4-182">詳細については、「[イベント ベースの非同期パターンの概要](/dotnet/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-182">For more information, see [Event-based Asynchronous Pattern Overview](/dotnet/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview).</span></span>

    > [!CAUTION]
    > <span data-ttu-id="ce1c4-183">どのような種類のマルチスレッドを使用している場合でも、非常に深刻で複雑なバグを引き起こしてしまう可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-183">When using multithreading of any sort, you potentially expose yourself to very serious and complex bugs.</span></span> <span data-ttu-id="ce1c4-184">マルチスレッドを使用するソリューションを実装する前に、「[マネージド スレッド処理の実施](/dotnet/standard/threading/managed-threading-best-practices)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce1c4-184">Consult the [Managed Threading Best Practices](/dotnet/standard/threading/managed-threading-best-practices) before implementing any solution that uses multithreading.</span></span>

## <a name="see-also"></a><span data-ttu-id="ce1c4-185">関連項目</span><span class="sxs-lookup"><span data-stu-id="ce1c4-185">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>
- [<span data-ttu-id="ce1c4-186">マネージド スレッド処理</span><span class="sxs-lookup"><span data-stu-id="ce1c4-186">Managed Threading</span></span>](/dotnet/standard/threading/index)
- [<span data-ttu-id="ce1c4-187">マネージド スレッド処理の実施</span><span class="sxs-lookup"><span data-stu-id="ce1c4-187">Managed Threading Best Practices</span></span>](/dotnet/standard/threading/managed-threading-best-practices)
- [<span data-ttu-id="ce1c4-188">イベントベースの非同期パターンの概要</span><span class="sxs-lookup"><span data-stu-id="ce1c4-188">Event-based Asynchronous Pattern Overview</span></span>](/dotnet/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview)
- [<span data-ttu-id="ce1c4-189">方法: バックグラウンド操作を使用するフォームを実装する</span><span class="sxs-lookup"><span data-stu-id="ce1c4-189">How to: Implement a Form That Uses a Background Operation</span></span>](how-to-implement-a-form-that-uses-a-background-operation.md)
- [<span data-ttu-id="ce1c4-190">チュートリアル: 操作をバックグラウンドで実行する</span><span class="sxs-lookup"><span data-stu-id="ce1c4-190">Walkthrough: Running an Operation in the Background</span></span>](walkthrough-running-an-operation-in-the-background.md)
- [<span data-ttu-id="ce1c4-191">BackgroundWorker コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ce1c4-191">BackgroundWorker Component</span></span>](backgroundworker-component.md)
