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
# <a name="walkthrough-implementing-a-form-that-uses-a-background-operation"></a>チュートリアル: バックグラウンド操作を使用するフォームの実装

完了までに時間がかかる操作があり、ユーザーインターフェイス (UI) が応答を停止したりブロックしたりしないようにするには、クラスを使用して <xref:System.ComponentModel.BackgroundWorker> 別のスレッドで操作を実行します。

このチュートリアルでは、 <xref:System.ComponentModel.BackgroundWorker> ユーザーインターフェイスの応答性を維持したまま、クラスを使用して時間のかかる計算をバックグラウンドで実行する方法について説明します。  このチュートリアルを完了すると、フィボナッチ数を非同期に計算するアプリケーションが作成されます。 大きなフィボナッチ数の計算にはかなりの時間がかかることがありますが、この遅延によってメイン UI スレッドが中断されることはなく、計算中もフォームは応答性を維持します。

このチュートリアルでは、以下のタスクを行います。

- Windows ベースのアプリケーションの作成

- フォームでのの作成 <xref:System.ComponentModel.BackgroundWorker>

- 非同期イベント ハンドラーの追加

- 進行状況の報告とキャンセルのサポートの追加

この例で使用するコード全体については、「[方法 : バックグラウンド操作を使用するフォームを実装する](how-to-implement-a-form-that-uses-a-background-operation.md)」を参照してください。

## <a name="create-a-form-that-uses-a-background-operation"></a>バックグラウンド操作を使用するフォームを作成する

1. Visual Studio で、という名前の Windows ベースのアプリケーションプロジェクトを作成 `BackgroundWorkerExample` します ([**ファイル**] [  >  **新しい**  >  **プロジェクト**] [  >  **Visual C#** ] または [ **Visual Basic**  >  **クラシックデスクトップ**  >  **Windows フォームアプリケーション**])。

2. **ソリューション エクスプローラー** で、**[Form1]** を右クリックし、ショートカット メニューの **[名前の変更]** をクリックします。 ファイル名を `FibonacciCalculator` に変更します。 コード要素 "`Form1`" へのすべての参照の名前を変更するかどうかをたずねられたら、**[はい]** をクリックします。

3. <xref:System.Windows.Forms.NumericUpDown>**ツールボックス** からコントロールをフォームにドラッグします。 プロパティを <xref:System.Windows.Forms.NumericUpDown.Minimum%2A> に設定し `1` 、 <xref:System.Windows.Forms.NumericUpDown.Maximum%2A> プロパティをに設定し `91` ます。

4. <xref:System.Windows.Forms.Button>フォームに2つのコントロールを追加します。

5. 最初のコントロールの名前を変更 <xref:System.Windows.Forms.Button> `startAsyncButton` し、 <xref:System.Windows.Forms.Control.Text%2A> プロパティをに設定し `Start Async` ます。 2つ目のコントロールの名前を変更 <xref:System.Windows.Forms.Button> `cancelAsyncButton` し、 <xref:System.Windows.Forms.Control.Text%2A> プロパティをに設定し `Cancel Async` ます。 <xref:System.Windows.Forms.Control.Enabled%2A>プロパティをに設定 `false` します。

6. 両方のコントロールのイベントに対してイベントハンドラーを作成 <xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.Control.Click> します。 詳細については、「[方法 : デザイナーを使用してイベント ハンドラーを作成する](/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100))」を参照してください。

7. <xref:System.Windows.Forms.Label>**ツールボックス** からコントロールをフォームにドラッグし、名前を変更 `resultLabel` します。

8. <xref:System.Windows.Forms.ProgressBar>**ツールボックス** からコントロールをフォームにドラッグします。

## <a name="create-a-backgroundworker-with-the-designer"></a>デザイナーを使用して BackgroundWorker を作成する

<xref:System.ComponentModel.BackgroundWorker> **Windows** **フォームデザイナー** を使用して、非同期操作のを作成できます。

[**ツールボックス**] の [**コンポーネント**] タブから、を <xref:System.ComponentModel.BackgroundWorker> フォームにドラッグします。

## <a name="add-asynchronous-event-handlers"></a>非同期イベントハンドラーの追加

これで、 <xref:System.ComponentModel.BackgroundWorker> コンポーネントの非同期イベントのイベントハンドラーを追加する準備ができました。 バックグラウンドで実行される時間のかかる操作 (フィボナッチ数の計算) は、これらのイベント ハンドラーのいずれかによって呼び出されます。

1. [ **プロパティ** ] ウィンドウで、コンポーネントを選択した状態で、 <xref:System.ComponentModel.BackgroundWorker> [ **イベント** ] ボタンをクリックします。 イベントとイベントをダブルクリックして、 <xref:System.ComponentModel.BackgroundWorker.DoWork> <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> イベントハンドラーを作成します。 イベント ハンドラーの使用方法の詳細については、「[方法 : デザイナーを使用してイベント ハンドラーを作成する](/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100))」を参照してください。

2. フォームで `ComputeFibonacci` という新しいメソッドを作成します。 このメソッドがバックグラウンドで実行され、実際の処理を行います。 このコードは、フィボナッチ アルゴリズムの再帰的実装を示しています。これは、非常に非効率であり、数が大きくなるにつれて、完了までの所要時間が急激に増大します。 ここでは、アプリケーションで長時間の遅延が発生する可能性のある操作を示すために、このコードを使用しています。

     [!code-cpp[System.ComponentModel.BackgroundWorker#10](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#10)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#10)]
     [!code-vb[System.ComponentModel.BackgroundWorker#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#10)]

3. <xref:System.ComponentModel.BackgroundWorker.DoWork>イベントハンドラーで、メソッドの呼び出しを追加し `ComputeFibonacci` ます。 のプロパティからの最初のパラメーターを取得し `ComputeFibonacci` <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> <xref:System.ComponentModel.DoWorkEventArgs> ます。 <xref:System.ComponentModel.BackgroundWorker>およびパラメーターは、 <xref:System.ComponentModel.DoWorkEventArgs> 後で進行状況の報告とキャンセルのサポートに使用されます。 の戻り値をの `ComputeFibonacci` プロパティに代入し <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> <xref:System.ComponentModel.DoWorkEventArgs> ます。 この結果は、イベントハンドラーで使用できるようになり <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> ます。

    > [!NOTE]
    > <xref:System.ComponentModel.BackgroundWorker.DoWork>イベントハンドラーはインスタンス変数を直接参照しません。これは、この `backgroundWorker1` イベントハンドラーをの特定のインスタンスに対して行うため <xref:System.ComponentModel.BackgroundWorker> です。 代わりに、 <xref:System.ComponentModel.BackgroundWorker> このイベントを発生させたへの参照がパラメーターから回復され `sender` ます。 これは、フォームが複数のをホストする場合に重要です <xref:System.ComponentModel.BackgroundWorker> 。 また、イベントハンドラー内のユーザーインターフェイスオブジェクトを操作しないことも重要です <xref:System.ComponentModel.BackgroundWorker.DoWork> 。 代わりに、イベントを使用してユーザーインターフェイスと通信し <xref:System.ComponentModel.BackgroundWorker> ます。

     [!code-cpp[System.ComponentModel.BackgroundWorker#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#5)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#5)]
     [!code-vb[System.ComponentModel.BackgroundWorker#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#5)]

4. `startAsyncButton`コントロールの <xref:System.Windows.Forms.Control.Click> イベントハンドラーに、非同期操作を開始するコードを追加します。

     [!code-cpp[System.ComponentModel.BackgroundWorker#13](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#13)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#13)]
     [!code-vb[System.ComponentModel.BackgroundWorker#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#13)]

5. <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>イベントハンドラーで、計算の結果をコントロールに割り当て `resultLabel` ます。

     [!code-cpp[System.ComponentModel.BackgroundWorker#6](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#6)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#6)]
     [!code-vb[System.ComponentModel.BackgroundWorker#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#6)]

## <a name="adding-progress-reporting-and-support-for-cancellation"></a>進行状況の報告とキャンセルのサポートの追加

時間のかかる非同期操作では、多くの場合、進行状況をユーザーに報告し、ユーザーが操作をキャンセルできるようにすることが望まれます。 クラスには、 <xref:System.ComponentModel.BackgroundWorker> バックグラウンド操作の進行に応じて進行状況を通知するためのイベントが用意されています。 また、ワーカーコードがの呼び出しを検出してそれ自体を中断できるようにするフラグも提供し <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> ます。

### <a name="implement-progress-reporting"></a>進行状況レポートを実装する

1. **[プロパティ]** ウィンドウで `backgroundWorker1` を選択します。 <xref:System.ComponentModel.BackgroundWorker.WorkerReportsProgress%2A> と <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> プロパティを `true` に設定します。

2. `FibonacciCalculator` フォームで 2 つの変数を宣言します。 これらの変数を使用して進行状況を追跡します。

     [!code-cpp[System.ComponentModel.BackgroundWorker#14](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#14)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#14](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#14)]
     [!code-vb[System.ComponentModel.BackgroundWorker#14](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#14)]

3. <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> イベントのイベント ハンドラーを追加します。 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged>イベントハンドラーで、 <xref:System.Windows.Forms.ProgressBar> パラメーターのプロパティを使用してを更新し <xref:System.ComponentModel.ProgressChangedEventArgs.ProgressPercentage%2A> <xref:System.ComponentModel.ProgressChangedEventArgs> ます。

     [!code-cpp[System.ComponentModel.BackgroundWorker#7](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#7)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#7)]
     [!code-vb[System.ComponentModel.BackgroundWorker#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#7)]

### <a name="implement-support-for-cancellation"></a>キャンセルのサポートを実装する

1. `cancelAsyncButton`コントロールの <xref:System.Windows.Forms.Control.Click> イベントハンドラーに、非同期操作をキャンセルするコードを追加します。

     [!code-cpp[System.ComponentModel.BackgroundWorker#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#4)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#4)]
     [!code-vb[System.ComponentModel.BackgroundWorker#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#4)]

2. `ComputeFibonacci` メソッドの次のコード フラグメントは、進行状況の報告とキャンセルのサポートを示しています。

     [!code-cpp[System.ComponentModel.BackgroundWorker#11](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#11)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#11)]
     [!code-vb[System.ComponentModel.BackgroundWorker#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#11)]
    [!code-cpp[System.ComponentModel.BackgroundWorker#12](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#12)]
    [!code-csharp[System.ComponentModel.BackgroundWorker#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#12)]
    [!code-vb[System.ComponentModel.BackgroundWorker#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#12)]

## <a name="checkpoint"></a>Checkpoint

この時点で、フィボナッチ電卓アプリケーションをコンパイルして実行できます。

**F5** キーを押して、アプリケーションをコンパイルして実行します。

計算がバックグラウンドで実行されている間、 <xref:System.Windows.Forms.ProgressBar> 計算の進行状況が完了するまで表示されます。 また、保留中の操作をキャンセルすることもできます。

数値が小さい場合、計算に時間はかかりませんが、数値が大きくなると、大幅な遅延が発生します。 30 以上の値を入力した場合、コンピューターの速度によっては数秒の遅延が発生します。 値が 40 を超えると、計算が終了するまでに数分から数時間かかることがあります。 電卓が大きなフィボナッチ数を計算している間も、フォームの移動、最小化、最大化を自由に行うことができ、フォームを閉じることもできます。 これは、メイン UI スレッドが計算の終了を待機していないためです。

## <a name="next-steps"></a>次のステップ

コンポーネントを使用してバックグラウンドで計算を実行するフォームを実装したので <xref:System.ComponentModel.BackgroundWorker> 、非同期操作の他の可能性を調べることができます。

- 複数 <xref:System.ComponentModel.BackgroundWorker> のオブジェクトを同時操作に使用します。

- マルチスレッド アプリケーションをデバッグする方法については、「[方法 : [スレッド] ウィンドウを使用する](/visualstudio/debugger/how-to-use-the-threads-window)」を参照してください。

- 非同期プログラミング モデルをサポートする独自のコンポーネントを実装する。 詳細については、「[イベント ベースの非同期パターンの概要](/dotnet/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview)」を参照してください。

    > [!CAUTION]
    > どのような種類のマルチスレッドを使用している場合でも、非常に深刻で複雑なバグを引き起こしてしまう可能性があります。 マルチスレッドを使用するソリューションを実装する前に、「[マネージド スレッド処理の実施](/dotnet/standard/threading/managed-threading-best-practices)」を参照してください。

## <a name="see-also"></a>関連項目

- <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>
- [マネージド スレッド処理](/dotnet/standard/threading/index)
- [マネージド スレッド処理の実施](/dotnet/standard/threading/managed-threading-best-practices)
- [イベントベースの非同期パターンの概要](/dotnet/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview)
- [方法: バックグラウンド操作を使用するフォームを実装する](how-to-implement-a-form-that-uses-a-background-operation.md)
- [チュートリアル: 操作をバックグラウンドで実行する](walkthrough-running-an-operation-in-the-background.md)
- [BackgroundWorker コンポーネント](backgroundworker-component.md)
