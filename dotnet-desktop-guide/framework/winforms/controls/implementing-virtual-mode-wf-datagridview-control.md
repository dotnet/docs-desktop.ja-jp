---
title: 'チュートリアル: DataGridView コントロールでの仮想モードの実装'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- virtual mode [Windows Forms], walkthroughs
- DataGridView control [Windows Forms], large data sets
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 74eb5276-5ab8-4ce0-8005-dae751d85f7c
ms.openlocfilehash: 5db97b321238bc371c94e627a387bd83ca31b58a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982971"
---
# <a name="walkthrough-implementing-virtual-mode-in-the-windows-forms-datagridview-control"></a>チュートリアル: Windows フォーム DataGridView コントロールでの仮想モードを実装する
非常に大量の表形式データをコントロールに表示する場合は、 <xref:System.Windows.Forms.DataGridView> プロパティをに設定 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> し、 `true` コントロールとそのデータストアとの対話を明示的に管理できます。 これにより、このような場合にコントロールのパフォーマンスを微調整できます。  
  
 <xref:System.Windows.Forms.DataGridView>コントロールには、カスタムデータストアと対話するために処理できるいくつかのイベントが用意されています。 このチュートリアルでは、これらのイベントハンドラーを実装する手順について説明します。 このトピックのコード例では、簡単に説明するために、非常に単純なデータソースを使用します。 運用環境の設定では、通常、表示する必要のある行だけをキャッシュに読み込み、 <xref:System.Windows.Forms.DataGridView> キャッシュとの対話および更新のためのイベントを処理します。 詳細については、「 [Windows フォーム DataGridView コントロールでの Just-in-time データ読み込みによる仮想モードの実装](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)」を参照してください。  
  
 このトピックのコードを単一のリストとしてコピーする方法については、「 [方法: Windows フォーム DataGridView コントロールで仮想モードを実装](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)する」を参照してください。  
  
## <a name="creating-the-form"></a>フォームの作成  
  
#### <a name="to-implement-virtual-mode"></a>仮想モードを実装するには  
  
1. から派生するクラスを作成 <xref:System.Windows.Forms.Form> し、コントロールを格納し <xref:System.Windows.Forms.DataGridView> ます。  
  
     次のコードには、いくつかの基本的な初期化が含まれています。 これは、後の手順で使用されるいくつかの変数を宣言し、メソッドを提供 `Main` し、クラスコンストラクターに単純なフォームレイアウトを提供します。  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#001)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#001)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#001)]  
    [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#002)]
    [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#002)]
    [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#002)]  
  
2. <xref:System.Windows.Forms.Form.Load>コントロールを初期化 <xref:System.Windows.Forms.DataGridView> し、データストアにサンプル値を設定するフォームのイベントのハンドラーを実装します。  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#110)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#110)]  
  
3. <xref:System.Windows.Forms.DataGridView.CellValueNeeded>データストアまたは `Customer` 現在編集中のオブジェクトから要求されたセル値を取得するイベントのハンドラーを実装します。  
  
     このイベント <xref:System.Windows.Forms.DataGridView> は、コントロールがセルを描画する必要があるときに常に発生します。  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#120)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#120)]  
  
4. 編集された <xref:System.Windows.Forms.DataGridView.CellValuePushed> 行を表すオブジェクトに、編集されたセル値を格納するイベントのハンドラーを実装し `Customer` ます。 このイベントは、ユーザーがセル値の変更をコミットするたびに発生します。  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#130)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#130)]  
  
5. <xref:System.Windows.Forms.DataGridView.NewRowNeeded>新しく作成された行を表す新しいオブジェクトを作成するイベントのハンドラーを実装し `Customer` ます。  
  
     このイベントは、ユーザーが新しいレコードの行を入力するたびに発生します。  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#140)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#140)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#140)]  
  
6. <xref:System.Windows.Forms.DataGridView.RowValidated>新しい行または変更された行をデータストアに保存するイベントのハンドラーを実装します。  
  
     このイベントは、ユーザーが現在の行を変更するたびに発生します。  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#150)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#150)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#150)]  
  
7. <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> <xref:System.Windows.Forms.DataGridView.CancelRowEdit> 編集モードで ESC キーを2回押すか、編集モードの外部で1回押すことによって、ユーザーが行再設定を通知するときにイベントを発生させるかどうかを示すイベントのハンドラーを実装します。  
  
     既定では、 <xref:System.Windows.Forms.DataGridView.CancelRowEdit> <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> イベントハンドラーでプロパティがに設定されていない限り、現在の行のセルが変更されたときに、行再設定に対してが発生し `true` <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> ます。 このイベントは、実行時にコミットスコープが決定される場合に役立ちます。  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#160)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#160)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#160)]  
  
8. <xref:System.Windows.Forms.DataGridView.CancelRowEdit>現在の行を表すオブジェクトの値を破棄するイベントのハンドラーを実装 `Customer` します。  
  
     このイベントは、編集モードで ESC キーを2回押すか、編集モードの外側で1回押すことによって、ユーザーが行再設定を通知するときに発生します。 現在の行にセルが変更されていない場合、または <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> `false` イベントハンドラーでプロパティの値がに設定されている場合、このイベントは発生しません <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> 。  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#170)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#170)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#170)]  
  
9. イベントのハンドラーを実装 <xref:System.Windows.Forms.DataGridView.UserDeletingRow> します。このハンドラーは、データストアから既存のオブジェクトを削除する `Customer` か、 `Customer` 新しく作成された行を表す未保存のオブジェクトを破棄します。  
  
     このイベントは、ユーザーが行ヘッダーをクリックし、DEL キーを押して行を削除するたびに発生します。  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#180)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#180)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#180)]  
  
10. `Customers`このコード例で使用されるデータ項目を表す単純なクラスを実装します。  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#200)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#200)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#200)]  
  
## <a name="testing-the-application"></a>アプリケーションのテスト  
 フォームをテストして、期待どおりに動作することを確認します。  
  
#### <a name="to-test-the-form"></a>フォームをテストするには  
  
- アプリケーションをコンパイルして実行します。  
  
     <xref:System.Windows.Forms.DataGridView>3 つの顧客レコードが設定されたコントロールが表示されます。 行の複数のセルの値を変更して、編集モードで ESC キーを2回押すと、編集モードの外に1回押して、行全体を元の値に戻すことができます。 コントロール内の行を変更、追加、または削除すると、 `Customer` データストア内のオブジェクトも変更、追加、または削除されます。  
  
## <a name="next-steps"></a>次の手順  
 このアプリケーションを使用すると、コントロールに仮想モードを実装するために処理する必要があるイベントについての基本的な理解を得ることができ <xref:System.Windows.Forms.DataGridView> ます。 この基本的なアプリケーションは、さまざまな方法で改善できます。  
  
- 外部データベースからの値をキャッシュするデータストアを実装します。 キャッシュは必要に応じて値を取得および破棄する必要があります。これにより、クライアントコンピューターで少量のメモリを消費しているときに、表示に必要なものだけが格納されます。  
  
- 要件に応じて、データストアのパフォーマンスを微調整します。 たとえば、より大きなキャッシュサイズを使用してデータベースクエリの数を最小限に抑えることで、クライアントコンピューターのメモリ制限ではなく、低速のネットワーク接続を補正することができます。  
  
 外部データベースからの値のキャッシュの詳細については、「 [方法: Windows フォーム DataGridView コントロールで Just-in-time データ読み込みを使用して仮想モードを実装する](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- <xref:System.Windows.Forms.DataGridView.CellValueNeeded>
- <xref:System.Windows.Forms.DataGridView.CellValuePushed>
- <xref:System.Windows.Forms.DataGridView.NewRowNeeded>
- <xref:System.Windows.Forms.DataGridView.RowValidated>
- <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>
- <xref:System.Windows.Forms.DataGridView.CancelRowEdit>
- <xref:System.Windows.Forms.DataGridView.UserDeletingRow>
- [Windows フォーム DataGridView コントロールでのパフォーマンス チューニング](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [Windows フォーム DataGridView コントロールを拡張するための推奨される手順](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [Windows フォーム DataGridView コントロールでの Just-In-Time データ読み込みによる仮想モードの実装](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)
- [方法: Windows フォーム DataGridView コントロールで仮想モードを実装する](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)
