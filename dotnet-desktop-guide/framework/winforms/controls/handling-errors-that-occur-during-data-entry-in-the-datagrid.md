---
title: 'チュートリアル: DataGridView コントロールでのデータ入力中に発生したエラーの処理'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- error handling [Windows Forms], dataGridView control
- data grids [Windows Forms], error handling
- DataGridView control [Windows Forms], error handling
- data entry [Windows Forms], error handling
- error handling [Windows Forms], data entry
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 30a68b85-d3af-4946-83c1-1e2d010d0511
ms.openlocfilehash: d65dd038ddc276ec09a1db3af4f14fc87fec56f2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981487"
---
# <a name="walkthrough-handling-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a>チュートリアル: Windows フォーム DataGridView コントロールでのデータ入力中に発生したエラーの処理

データ入力アプリケーションでは、基になるデータストアからのエラーを処理する必要があります。 Windows フォームコントロールは、 <xref:System.Windows.Forms.DataGridView> イベントを公開することによってこれを簡単にし <xref:System.Windows.Forms.DataGridView.DataError> ます。これは、データストアが制約違反または分割されたビジネスルールを検出したときに発生します。

このチュートリアルでは、Northwind サンプルデータベースのテーブルから行を取得 `Customers` し、コントロールに表示し <xref:System.Windows.Forms.DataGridView> ます。 `CustomerID`新しい行または編集済みの既存の行で重複する値が検出されると、 <xref:System.Windows.Forms.DataGridView.DataError> イベントが発生します。これは、例外を説明するを表示することによって処理され <xref:System.Windows.Forms.MessageBox> ます。

このトピックのコードを単一のリストとしてコピーする方法については、「 [方法: Windows フォーム DataGridView コントロールでのデータ入力中に発生したエラーを処理](handle-errors-that-occur-during-data-entry-in-the-datagrid.md)する」を参照してください。

## <a name="prerequisites"></a>必須コンポーネント

このチュートリアルを完了するための要件は次のとおりです。

- Northwind SQL Server サンプルデータベースを持つサーバーへのアクセス。

## <a name="creating-the-form"></a>フォームの作成

#### <a name="to-handle-data-entry-errors-in-the-datagridview-control"></a>DataGridView コントロールでのデータ入力エラーを処理するには

1. から派生するクラスを作成 <xref:System.Windows.Forms.Form> し、 <xref:System.Windows.Forms.DataGridView> コントロールとコンポーネントを格納し <xref:System.Windows.Forms.BindingSource> ます。

    次のコード例では、基本的な初期化を行い、メソッドを含めてい `Main` ます。

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#02)]

2. データベースへの接続の詳細を処理するために、フォームのクラス定義にメソッドを実装します。

    このコード例では、 `GetData` 設定されたオブジェクトを返すメソッドを使用 <xref:System.Data.DataTable> します。 `connectionString`変数には、データベースに適した値を設定してください。

    > [!IMPORTANT]
    > 接続文字列内に機密情報 (パスワードなど) を格納すると、アプリケーションのセキュリティに影響を及ぼすことがあります。 データベースへのアクセスを制御する方法としては、Windows 認証 (統合セキュリティとも呼ばれます) を使用する方が安全です。 詳細については、「[接続情報の保護](/dotnet/framework/data/adonet/protecting-connection-information)」を参照してください。

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#30)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#30)]

3. とを初期化し、データバインディングを設定するフォームのイベントのハンドラーを実装し <xref:System.Windows.Forms.Form.Load> <xref:System.Windows.Forms.DataGridView> <xref:System.Windows.Forms.BindingSource> ます。

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#10)]

4. <xref:System.Windows.Forms.DataGridView.DataError>でイベントを処理し <xref:System.Windows.Forms.DataGridView> ます。

    エラーのコンテキストがコミット操作の場合は、エラーをに表示 <xref:System.Windows.Forms.MessageBox> します。

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#20)]

## <a name="testing-the-application"></a>アプリケーションのテスト

フォームをテストして、期待どおりに動作することを確認します。

#### <a name="to-test-the-form"></a>フォームをテストするには

- F5 キーを押してアプリケーションを実行します。

  Customers テーブルのデータが入力されたコントロールが表示され <xref:System.Windows.Forms.DataGridView> ます。 に重複する値を入力して編集をコミットすると、 `CustomerID` セルの値は自動的に元に戻り、データエントリエラーを示すが表示され <xref:System.Windows.Forms.MessageBox> ます。

## <a name="next-steps"></a>次の手順

このアプリケーションを使用すると、コントロールの機能についての基本的な理解を得ることができ <xref:System.Windows.Forms.DataGridView> ます。 コントロールの外観と動作は、 <xref:System.Windows.Forms.DataGridView> 次のいくつかの方法でカスタマイズできます。

- 罫線とヘッダーのスタイルを変更します。 詳細については、「 [方法: Windows フォーム DataGridView コントロールの境界線とグリッド線のスタイルを変更する](change-the-border-and-gridline-styles-in-the-datagrid.md)」を参照してください。

- コントロールへのユーザー入力を有効または制限 <xref:System.Windows.Forms.DataGridView> します。 詳細については、「 [方法: Windows フォーム Datagridview コントロールで行の追加と削除を回避](prevent-row-addition-and-deletion-datagridview.md)する」および「 [方法: Windows フォーム Datagridview コントロールで列を Read-Only する](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)」を参照してください。

- コントロールへのユーザー入力を検証 <xref:System.Windows.Forms.DataGridView> します。 詳細については、「 [チュートリアル: Windows フォーム DataGridView コントロールでのデータの検証](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)」を参照してください。

- 仮想モードを使用して非常に大きなデータセットを処理します。 詳細については、「 [チュートリアル: Windows フォーム DataGridView コントロールでの仮想モードの実装](implementing-virtual-mode-wf-datagridview-control.md)」を参照してください。

- セルの外観をカスタマイズします。 詳細については、「 [方法: Windows フォーム Datagridview コントロールのセルの外観をカスタマイズ](customize-the-appearance-of-cells-in-the-datagrid.md) する」および「 [方法: Windows フォーム Datagridview コントロールの既定のセルスタイルを設定する](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)」を参照してください。

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Windows フォーム DataGridView コントロールでのデータ入力](data-entry-in-the-windows-forms-datagridview-control.md)
- [方法: Windows フォーム DataGridView コントロールでのデータ入力中に発生したエラーを処理する](handle-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [チュートリアル: Windows フォーム DataGridView コントロールのデータの妥当性検査](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [接続情報の保護](/dotnet/framework/data/adonet/protecting-connection-information)
