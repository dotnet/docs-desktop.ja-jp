---
title: 'チュートリアル: DataGridView コントロールでのデータの検証'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- validating data [Windows Forms], Windows Forms
- data [Windows Forms], validation
- DataGridView control [Windows Forms], data validation
- data grids [Windows Forms], validating data
- data validation [Windows Forms], Windows Forms
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: a4f1d015-2969-430c-8ea2-b612d179c290
ms.openlocfilehash: 822a09565e81d308179dd0b51993a758738922bb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982692"
---
# <a name="walkthrough-validating-data-in-the-windows-forms-datagridview-control"></a>チュートリアル: Windows フォーム DataGridView コントロールのデータの妥当性検査

データ入力機能をユーザーに表示する場合は、フォームに入力されたデータを頻繁に検証する必要があります。 クラスは、データ <xref:System.Windows.Forms.DataGridView> がデータストアにコミットされる前に検証を実行する便利な方法を提供します。 <xref:System.Windows.Forms.DataGridView.CellValidating>現在のセルが変更されたときにによって発生するイベントを処理することで、データを検証でき <xref:System.Windows.Forms.DataGridView> ます。

このチュートリアルでは、Northwind サンプルデータベースのテーブルから行を取得 `Customers` し、コントロールに表示し <xref:System.Windows.Forms.DataGridView> ます。 ユーザーが列のセルを編集し、セルから離れようとすると `CompanyName` 、 <xref:System.Windows.Forms.DataGridView.CellValidating> イベントハンドラーは新しい会社名の文字列を調べて空でないことを確認します。新しい値が空の文字列の場合、は、 <xref:System.Windows.Forms.DataGridView> 空でない文字列が入力されるまで、ユーザーのカーソルがセルから離れるのを防ぐことができます。

このトピックのコードを単一のリストとしてコピーする方法については、「 [方法: Windows フォーム DataGridView コントロールでデータを検証](how-to-validate-data-in-the-windows-forms-datagridview-control.md)する」を参照してください。

## <a name="prerequisites"></a>必須コンポーネント

このチュートリアルを完了するための要件は次のとおりです。

- Northwind SQL Server サンプルデータベースを持つサーバーへのアクセス。

## <a name="creating-the-form"></a>フォームの作成

#### <a name="to-validate-data-entered-in-a-datagridview"></a>DataGridView に入力されたデータを検証するには

1. から派生するクラスを作成 <xref:System.Windows.Forms.Form> し、 <xref:System.Windows.Forms.DataGridView> コントロールとコンポーネントを格納し <xref:System.Windows.Forms.BindingSource> ます。

    次のコード例では、基本的な初期化を行い、メソッドを含めてい `Main` ます。

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#02)]

2. データベースへの接続の詳細を処理するために、フォームのクラス定義にメソッドを実装します。

    このコード例では、 `GetData` 設定されたオブジェクトを返すメソッドを使用 <xref:System.Data.DataTable> します。 `connectionString`変数には、データベースに適した値を設定してください。

    > [!IMPORTANT]
    > 接続文字列内に機密情報 (パスワードなど) を格納すると、アプリケーションのセキュリティに影響を及ぼすことがあります。 Windows 認証 (統合セキュリティとも呼ばれます) を使用すると、データベースへのアクセスをより安全に制御することができます。 詳細については、「[接続情報の保護](/dotnet/framework/data/adonet/protecting-connection-information)」を参照してください。

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#30)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#30)]

3. とを初期化し、データバインディングを設定するフォームのイベントのハンドラーを実装し <xref:System.Windows.Forms.Form.Load> <xref:System.Windows.Forms.DataGridView> <xref:System.Windows.Forms.BindingSource> ます。

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#10)]

4. <xref:System.Windows.Forms.DataGridView>コントロールのイベントとイベントのハンドラーを実装 <xref:System.Windows.Forms.DataGridView.CellValidating> <xref:System.Windows.Forms.DataGridView.CellEndEdit> します。

    <xref:System.Windows.Forms.DataGridView.CellValidating>イベントハンドラーでは、列のセルの値が空かどうかを判断し `CompanyName` ます。 セル値が検証に失敗した場合は、 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> クラスのプロパティを <xref:System.Windows.Forms.DataGridViewCellValidatingEventArgs?displayProperty=nameWithType> に設定 `true` します。 これにより、コントロールによって、 <xref:System.Windows.Forms.DataGridView> カーソルがセルから離れるのを防ぐことができます。 行の <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> プロパティを説明の文字列に設定します。 エラーアイコンと、エラーテキストを含むツールヒントが表示されます。 <xref:System.Windows.Forms.DataGridView.CellEndEdit>イベントハンドラーで、 <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> 行のプロパティを空の文字列に設定します。 イベントは、 <xref:System.Windows.Forms.DataGridView.CellEndEdit> セルが編集モードを終了したときにのみ発生します。これは、検証に失敗した場合には実行できません。

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#20)]

## <a name="testing-the-application"></a>アプリケーションのテスト

フォームをテストして、期待どおりに動作することを確認します。

#### <a name="to-test-the-form"></a>フォームをテストするには

- アプリケーションをコンパイルして実行します。

  テーブルのデータがいっぱいになっていることがわかり <xref:System.Windows.Forms.DataGridView> `Customers` ます。 列のセルをダブルクリックすると、 `CompanyName` 値を編集できます。 すべての文字を削除し、TAB キーを押してセルを終了すると、で <xref:System.Windows.Forms.DataGridView> 終了できなくなります。 空でない文字列をセルに入力すると、コントロールによって <xref:System.Windows.Forms.DataGridView> セルを終了できます。

## <a name="next-steps"></a>次の手順

このアプリケーションを使用すると、コントロールの機能についての基本的な理解を得ることができ <xref:System.Windows.Forms.DataGridView> ます。 コントロールの外観と動作は、 <xref:System.Windows.Forms.DataGridView> 次のいくつかの方法でカスタマイズできます。

- 罫線とヘッダーのスタイルを変更します。 詳細については、「 [方法: Windows フォーム DataGridView コントロールの境界線とグリッド線のスタイルを変更する](change-the-border-and-gridline-styles-in-the-datagrid.md)」を参照してください。

- コントロールへのユーザー入力を有効または制限 <xref:System.Windows.Forms.DataGridView> します。 詳細については、「 [方法: Windows フォーム Datagridview コントロールで行の追加と削除を回避](prevent-row-addition-and-deletion-datagridview.md)する」および「 [方法: Windows フォーム Datagridview コントロールで列を Read-Only する](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)」を参照してください。

- データベース関連のエラーについては、ユーザー入力を確認してください。 詳細については、「 [チュートリアル: Windows フォーム DataGridView コントロールでのデータ入力中に発生したエラーの処理](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)」を参照してください。

- 仮想モードを使用して非常に大きなデータセットを処理します。 詳細については、「 [チュートリアル: Windows フォーム DataGridView コントロールでの仮想モードの実装](implementing-virtual-mode-wf-datagridview-control.md)」を参照してください。

- セルの外観をカスタマイズします。 詳細については、「 [方法: Windows フォーム Datagridview コントロールのセルの外観をカスタマイズ](customize-the-appearance-of-cells-in-the-datagrid.md) する」および「 [方法: Windows フォーム Datagridview コントロールのフォントと色のスタイルを設定する](how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)」を参照してください。

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Windows フォーム DataGridView コントロールでのデータ入力](data-entry-in-the-windows-forms-datagridview-control.md)
- [方法: Windows フォーム DataGridView コントロールのデータを検証する](how-to-validate-data-in-the-windows-forms-datagridview-control.md)
- [チュートリアル: Windows フォーム DataGridView コントロールでのデータ入力中に発生したエラーの処理](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [接続情報の保護](/dotnet/framework/data/adonet/protecting-connection-information)
