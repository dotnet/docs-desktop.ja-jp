---
title: 'チュートリアル: 操作をバックグラウンドで実行する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- background tasks
- forms [Windows Forms], multithreading
- forms [Windows Forms], background operations
- background threads
- BackgroundWorker class [Windows Forms], examples
- threading [Windows Forms], background operations
- background operations
ms.assetid: 1b9a4e0a-f134-48ff-a1be-c461446a31ba
ms.openlocfilehash: ad0955937965c89b52648e37cd151e0cd266e527
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982704"
---
# <a name="walkthrough-running-an-operation-in-the-background"></a><span data-ttu-id="ef257-102">チュートリアル: 操作をバックグラウンドで実行する</span><span class="sxs-lookup"><span data-stu-id="ef257-102">Walkthrough: Running an Operation in the Background</span></span>

<span data-ttu-id="ef257-103">完了に長い時間がかかる操作を実行しており、ユーザー インターフェイスで遅延が発生しないようにするには<xref:System.ComponentModel.BackgroundWorker> クラスを使用して別のスレッドで操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="ef257-103">If you have an operation that will take a long time to complete, and you do not want to cause delays in your user interface, you can use the <xref:System.ComponentModel.BackgroundWorker> class to run the operation on another thread.</span></span>

<span data-ttu-id="ef257-104">この例で使用されているコードの完全な一覧については、「 [方法: バックグラウンドで操作を実行する](how-to-run-an-operation-in-the-background.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef257-104">For a complete listing of the code used in this example, see [How to: Run an Operation in the Background](how-to-run-an-operation-in-the-background.md).</span></span>

## <a name="run-an-operation-in-the-background"></a><span data-ttu-id="ef257-105">バックグラウンドで操作を実行する</span><span class="sxs-lookup"><span data-stu-id="ef257-105">Run an operation in the background</span></span>

1. <span data-ttu-id="ef257-106">Visual Studio の Windows フォームデザイナーでフォームをアクティブにした状態で、2つの <xref:System.Windows.Forms.Button> コントロールを **ツールボックス** からフォームにドラッグし、 `Name` <xref:System.Windows.Forms.Control.Text%2A> 次の表に従ってボタンのプロパティとプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="ef257-106">With your form active in the Windows Forms Designer in Visual Studio, drag two <xref:System.Windows.Forms.Button> controls from the **Toolbox** to the form, and then set the `Name` and <xref:System.Windows.Forms.Control.Text%2A> properties of the buttons according to the following table.</span></span>

    |<span data-ttu-id="ef257-107">Button</span><span class="sxs-lookup"><span data-stu-id="ef257-107">Button</span></span>|<span data-ttu-id="ef257-108">名前</span><span class="sxs-lookup"><span data-stu-id="ef257-108">Name</span></span>|<span data-ttu-id="ef257-109">テキスト</span><span class="sxs-lookup"><span data-stu-id="ef257-109">Text</span></span>|
    |------------|----------|----------|
    |`button1`|`startBtn`|<span data-ttu-id="ef257-110">**Start**</span><span class="sxs-lookup"><span data-stu-id="ef257-110">**Start**</span></span>|
    |`button2`|`cancelBtn`|<span data-ttu-id="ef257-111">**キャンセル**</span><span class="sxs-lookup"><span data-stu-id="ef257-111">**Cancel**</span></span>|

2. <span data-ttu-id="ef257-112">**ツールボックス** を開き、[**コンポーネント**] タブをクリックし、コンポーネントをフォームにドラッグし <xref:System.ComponentModel.BackgroundWorker> ます。</span><span class="sxs-lookup"><span data-stu-id="ef257-112">Open the **Toolbox**, click the **Components** tab, and then drag the <xref:System.ComponentModel.BackgroundWorker> component onto your form.</span></span>

     <span data-ttu-id="ef257-113">コンポーネントが `backgroundWorker1` **コンポーネントトレイ** に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ef257-113">The `backgroundWorker1` component appears in the **Component Tray**.</span></span>

3. <span data-ttu-id="ef257-114">**[プロパティ]** ウィンドウで、 <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> プロパティを `true`に設定します。</span><span class="sxs-lookup"><span data-stu-id="ef257-114">In the **Properties** window, set the <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> property to `true`.</span></span>

4. <span data-ttu-id="ef257-115">[ **プロパティ** ] ウィンドウで、[ **イベント** ] ボタンをクリックし、イベントとイベントをダブルクリックして <xref:System.ComponentModel.BackgroundWorker.DoWork> <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> イベントハンドラーを作成します。</span><span class="sxs-lookup"><span data-stu-id="ef257-115">In the **Properties** window, click on the **Events** button, and then double-click the <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> events to create event handlers.</span></span>

5. <span data-ttu-id="ef257-116">時間のかかるコードを <xref:System.ComponentModel.BackgroundWorker.DoWork> イベントハンドラーに挿入します。</span><span class="sxs-lookup"><span data-stu-id="ef257-116">Insert your time-consuming code into the <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler.</span></span>

6. <span data-ttu-id="ef257-117">パラメーターのプロパティから、操作に必要なパラメーターを抽出 <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> <xref:System.ComponentModel.DoWorkEventArgs> します。</span><span class="sxs-lookup"><span data-stu-id="ef257-117">Extract any parameters required by the operation from the <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> property of the <xref:System.ComponentModel.DoWorkEventArgs> parameter.</span></span>

7. <span data-ttu-id="ef257-118">計算の結果をのプロパティに代入し <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> <xref:System.ComponentModel.DoWorkEventArgs> ます。</span><span class="sxs-lookup"><span data-stu-id="ef257-118">Assign the result of the computation to the <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> property of the <xref:System.ComponentModel.DoWorkEventArgs>.</span></span>

     <span data-ttu-id="ef257-119">これは、イベントハンドラーで使用できるようになり <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> ます。</span><span class="sxs-lookup"><span data-stu-id="ef257-119">This is will be available to the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler.</span></span>

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#2)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#2)]

8. <span data-ttu-id="ef257-120">イベントハンドラーで操作の結果を取得するためのコードを挿入 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> します。</span><span class="sxs-lookup"><span data-stu-id="ef257-120">Insert code for retrieving the result of your operation in the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler.</span></span>

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#3)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#3)]

9. <span data-ttu-id="ef257-121">`TimeConsumingOperation` メソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="ef257-121">Implement the `TimeConsumingOperation` method.</span></span>

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#4)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#4)]

10. <span data-ttu-id="ef257-122">Windows フォームデザイナーで、ダブルクリックし `startButton` てイベントハンドラーを作成し <xref:System.Windows.Forms.Control.Click> ます。</span><span class="sxs-lookup"><span data-stu-id="ef257-122">In the Windows Forms Designer, double-click `startButton` to create the <xref:System.Windows.Forms.Control.Click> event handler.</span></span>

11. <span data-ttu-id="ef257-123"><xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>のイベントハンドラーでメソッドを呼び出し <xref:System.Windows.Forms.Control.Click> `startButton` ます。</span><span class="sxs-lookup"><span data-stu-id="ef257-123">Call the <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> method in the <xref:System.Windows.Forms.Control.Click> event handler for `startButton`.</span></span>

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#5)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#5)]

12. <span data-ttu-id="ef257-124">Windows フォームデザイナーで、ダブルクリックし `cancelButton` てイベントハンドラーを作成し <xref:System.Windows.Forms.Control.Click> ます。</span><span class="sxs-lookup"><span data-stu-id="ef257-124">In the Windows Forms Designer, double-click `cancelButton` to create the <xref:System.Windows.Forms.Control.Click> event handler.</span></span>

13. <span data-ttu-id="ef257-125"><xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>のイベントハンドラーでメソッドを呼び出し <xref:System.Windows.Forms.Control.Click> `cancelButton` ます。</span><span class="sxs-lookup"><span data-stu-id="ef257-125">Call the <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> method in the <xref:System.Windows.Forms.Control.Click> event handler for `cancelButton`.</span></span>

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#6)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#6)]

14. <span data-ttu-id="ef257-126">ファイルの先頭に、System.componentmodel および system.object 名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="ef257-126">At the top of the file, import the System.ComponentModel and System.Threading namespaces.</span></span>

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#7)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#7)]

15. <span data-ttu-id="ef257-127">**F6** キーを押してソリューションをビルドし、 **Ctrl** F5 キーを押して + デバッガーの外部でアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="ef257-127">Press **F6** to build the solution, and then press **Ctrl**+**F5** to run the application outside the debugger.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ef257-128">**F5** キーを押してデバッガーでアプリケーションを実行すると、メソッドで発生した例外がキャッチされ、 `TimeConsumingOperation` デバッガーによって表示されます。</span><span class="sxs-lookup"><span data-stu-id="ef257-128">If you press **F5** to run the application under the debugger, the exception raised in the `TimeConsumingOperation` method is caught and displayed by the debugger.</span></span> <span data-ttu-id="ef257-129">デバッガーの外部でアプリケーションを実行すると、によって例外が処理され、の <xref:System.ComponentModel.BackgroundWorker> プロパティにキャッシュされ <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> <xref:System.ComponentModel.RunWorkerCompletedEventArgs> ます。</span><span class="sxs-lookup"><span data-stu-id="ef257-129">When you run the application outside the debugger, the <xref:System.ComponentModel.BackgroundWorker> handles the exception and caches it in the <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> property of the <xref:System.ComponentModel.RunWorkerCompletedEventArgs>.</span></span>

16. <span data-ttu-id="ef257-130">非同期操作を実行するには [ **開始** ] ボタンをクリックし、実行中の非同期操作を停止するには [ **キャンセル** ] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ef257-130">Click the **Start** button to run an asynchronous operation, and then click the **Cancel** button to stop a running asynchronous operation.</span></span>

     <span data-ttu-id="ef257-131">各操作の結果は、<xref:System.Windows.Forms.MessageBox> に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ef257-131">The outcome of each operation is displayed in a <xref:System.Windows.Forms.MessageBox>.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ef257-132">次のステップ</span><span class="sxs-lookup"><span data-stu-id="ef257-132">Next steps</span></span>

- <span data-ttu-id="ef257-133">非同期操作の進行に伴って進行状況を報告するフォームを実装します。</span><span class="sxs-lookup"><span data-stu-id="ef257-133">Implement a form that reports progress as an asynchronous operation proceeds.</span></span> <span data-ttu-id="ef257-134">詳細については、「 [方法: バックグラウンド操作を使用するフォームを実装](how-to-implement-a-form-that-uses-a-background-operation.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef257-134">For more information, see [How to: Implement a Form That Uses a Background Operation](how-to-implement-a-form-that-uses-a-background-operation.md).</span></span>

- <span data-ttu-id="ef257-135">コンポーネントの非同期パターンをサポートするクラスを実装します。</span><span class="sxs-lookup"><span data-stu-id="ef257-135">Implement a class that supports the Asynchronous Pattern for Components.</span></span> <span data-ttu-id="ef257-136">詳細については、「 [イベントベースの非同期パターンの実装](/dotnet/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef257-136">For more information, see [Implementing the Event-based Asynchronous Pattern](/dotnet/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern).</span></span>

## <a name="see-also"></a><span data-ttu-id="ef257-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="ef257-137">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [<span data-ttu-id="ef257-138">方法: バックグラウンド操作を使用するフォームを実装する</span><span class="sxs-lookup"><span data-stu-id="ef257-138">How to: Implement a Form That Uses a Background Operation</span></span>](how-to-implement-a-form-that-uses-a-background-operation.md)
- [<span data-ttu-id="ef257-139">方法: バックグラウンドで操作を実行する</span><span class="sxs-lookup"><span data-stu-id="ef257-139">How to: Run an Operation in the Background</span></span>](how-to-run-an-operation-in-the-background.md)
- [<span data-ttu-id="ef257-140">BackgroundWorker コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ef257-140">BackgroundWorker Component</span></span>](backgroundworker-component.md)
