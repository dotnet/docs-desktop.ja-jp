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
# <a name="walkthrough-running-an-operation-in-the-background"></a>チュートリアル: 操作をバックグラウンドで実行する

完了に長い時間がかかる操作を実行しており、ユーザー インターフェイスで遅延が発生しないようにするには<xref:System.ComponentModel.BackgroundWorker> クラスを使用して別のスレッドで操作を実行できます。

この例で使用されているコードの完全な一覧については、「 [方法: バックグラウンドで操作を実行する](how-to-run-an-operation-in-the-background.md)」を参照してください。

## <a name="run-an-operation-in-the-background"></a>バックグラウンドで操作を実行する

1. Visual Studio の Windows フォームデザイナーでフォームをアクティブにした状態で、2つの <xref:System.Windows.Forms.Button> コントロールを **ツールボックス** からフォームにドラッグし、 `Name` <xref:System.Windows.Forms.Control.Text%2A> 次の表に従ってボタンのプロパティとプロパティを設定します。

    |Button|名前|テキスト|
    |------------|----------|----------|
    |`button1`|`startBtn`|**Start**|
    |`button2`|`cancelBtn`|**キャンセル**|

2. **ツールボックス** を開き、[**コンポーネント**] タブをクリックし、コンポーネントをフォームにドラッグし <xref:System.ComponentModel.BackgroundWorker> ます。

     コンポーネントが `backgroundWorker1` **コンポーネントトレイ** に表示されます。

3. **[プロパティ]** ウィンドウで、 <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> プロパティを `true`に設定します。

4. [ **プロパティ** ] ウィンドウで、[ **イベント** ] ボタンをクリックし、イベントとイベントをダブルクリックして <xref:System.ComponentModel.BackgroundWorker.DoWork> <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> イベントハンドラーを作成します。

5. 時間のかかるコードを <xref:System.ComponentModel.BackgroundWorker.DoWork> イベントハンドラーに挿入します。

6. パラメーターのプロパティから、操作に必要なパラメーターを抽出 <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> <xref:System.ComponentModel.DoWorkEventArgs> します。

7. 計算の結果をのプロパティに代入し <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> <xref:System.ComponentModel.DoWorkEventArgs> ます。

     これは、イベントハンドラーで使用できるようになり <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> ます。

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#2)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#2)]

8. イベントハンドラーで操作の結果を取得するためのコードを挿入 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> します。

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#3)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#3)]

9. `TimeConsumingOperation` メソッドを実装します。

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#4)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#4)]

10. Windows フォームデザイナーで、ダブルクリックし `startButton` てイベントハンドラーを作成し <xref:System.Windows.Forms.Control.Click> ます。

11. <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>のイベントハンドラーでメソッドを呼び出し <xref:System.Windows.Forms.Control.Click> `startButton` ます。

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#5)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#5)]

12. Windows フォームデザイナーで、ダブルクリックし `cancelButton` てイベントハンドラーを作成し <xref:System.Windows.Forms.Control.Click> ます。

13. <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>のイベントハンドラーでメソッドを呼び出し <xref:System.Windows.Forms.Control.Click> `cancelButton` ます。

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#6)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#6)]

14. ファイルの先頭に、System.componentmodel および system.object 名前空間をインポートします。

     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#7)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#7)]

15. **F6** キーを押してソリューションをビルドし、 **Ctrl** F5 キーを押して + デバッガーの外部でアプリケーションを実行します。

    > [!NOTE]
    > **F5** キーを押してデバッガーでアプリケーションを実行すると、メソッドで発生した例外がキャッチされ、 `TimeConsumingOperation` デバッガーによって表示されます。 デバッガーの外部でアプリケーションを実行すると、によって例外が処理され、の <xref:System.ComponentModel.BackgroundWorker> プロパティにキャッシュされ <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> <xref:System.ComponentModel.RunWorkerCompletedEventArgs> ます。

16. 非同期操作を実行するには [ **開始** ] ボタンをクリックし、実行中の非同期操作を停止するには [ **キャンセル** ] ボタンをクリックします。

     各操作の結果は、<xref:System.Windows.Forms.MessageBox> に表示されます。

## <a name="next-steps"></a>次のステップ

- 非同期操作の進行に伴って進行状況を報告するフォームを実装します。 詳細については、「 [方法: バックグラウンド操作を使用するフォームを実装](how-to-implement-a-form-that-uses-a-background-operation.md)する」を参照してください。

- コンポーネントの非同期パターンをサポートするクラスを実装します。 詳細については、「 [イベントベースの非同期パターンの実装](/dotnet/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern)」を参照してください。

## <a name="see-also"></a>関連項目

- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [方法: バックグラウンド操作を使用するフォームを実装する](how-to-implement-a-form-that-uses-a-background-operation.md)
- [方法: バックグラウンドで操作を実行する](how-to-run-an-operation-in-the-background.md)
- [BackgroundWorker コンポーネント](backgroundworker-component.md)
