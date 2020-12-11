---
title: 'チュートリアル: 2 つの DataGridView コントロールを使用してマスター/詳細フォームを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], master/detail form
- parent-child tables [Windows Forms], displaying on Windows Forms
- master-details lists [Windows Forms], displaying on Windows Forms
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: c5fa29e8-47f7-4691-829b-0e697a691f36
ms.openlocfilehash: d6057eb16e8fc32c269d3013ee99cc1f276ecab6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974255"
---
# <a name="walkthrough-creating-a-masterdetail-form-using-two-windows-forms-datagridview-controls"></a>チュートリアル: Windows フォームの 2 つの DataGridView コントロールを使用したマスター/詳細形式のフォームを作成する

コントロールを使用する最も一般的なシナリオの1つ <xref:System.Windows.Forms.DataGridView> は、 *マスター/詳細* 形式です。このフォームでは、2つのデータベーステーブル間の親子関係が表示されます。 マスターテーブル内の行を選択すると、対応する子データで詳細テーブルが更新されます。

マスター/詳細フォームの実装は、コントロールとコンポーネントの間の相互作用を使用して簡単に行うことが <xref:System.Windows.Forms.DataGridView> <xref:System.Windows.Forms.BindingSource> できます。 このチュートリアルでは、2つのコントロールと2つのコンポーネントを使用してフォームをビルドし <xref:System.Windows.Forms.DataGridView> <xref:System.Windows.Forms.BindingSource> ます。 フォームでは、Northwind SQL Server サンプルデータベースにとという2つの関連テーブルが表示されます。 `Customers` `Orders` 完了すると、マスター内のデータベースのすべての顧客 <xref:System.Windows.Forms.DataGridView> と、選択した顧客のすべての注文が詳細に表示され <xref:System.Windows.Forms.DataGridView> ます。

このトピックのコードを単一のリストとしてコピーする方法については、「 [方法: 2 つの Windows フォーム DataGridView コントロールを使用してマスター/詳細フォームを作成](create-a-master-detail-form-using-two-datagridviews.md)する」を参照してください。

## <a name="prerequisites"></a>必須コンポーネント

このチュートリアルを完了するための要件は次のとおりです。

- Northwind SQL Server サンプルデータベースを持つサーバーへのアクセス。

## <a name="creating-the-form"></a>フォームの作成

#### <a name="to-create-a-masterdetail-form"></a>マスター/詳細フォームを作成するには

1. から派生するクラスを作成し、 <xref:System.Windows.Forms.Form> 2 つの <xref:System.Windows.Forms.DataGridView> コントロールと2つのコンポーネントを格納し <xref:System.Windows.Forms.BindingSource> ます。 次のコードは、基本的なフォームの初期化を提供し、メソッドを含んでい `Main` ます。 Visual Studio デザイナーを使用してフォームを作成する場合は、このコードの代わりにデザイナーで生成されたコードを使用できますが、ここでは変数宣言に示されている名前を使用してください。

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#02)]

2. データベースへの接続の詳細を処理するために、フォームのクラス定義にメソッドを実装します。 この例では、オブジェクトを設定し、 `GetData` <xref:System.Data.DataSet> オブジェクトを <xref:System.Data.DataRelation> データセットに追加して、コンポーネントをバインドするメソッドを使用し <xref:System.Windows.Forms.BindingSource> ます。 `connectionString` 変数は、使用しているデータベースに合った値に設定してください。

    > [!IMPORTANT]
    > 接続文字列内に機密情報 (パスワードなど) を格納すると、アプリケーションのセキュリティに影響を及ぼすことがあります。 データベースへのアクセスを制御する方法としては、Windows 認証 (統合セキュリティとも呼ばれます) を使用する方が安全です。 詳細については、「[接続情報の保護](/dotnet/framework/data/adonet/protecting-connection-information)」を参照してください。

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#20)]

3. <xref:System.Windows.Forms.Form.Load> <xref:System.Windows.Forms.DataGridView> コントロールをコンポーネントにバインドし、メソッドを呼び出すフォームのイベントのハンドラーを実装 <xref:System.Windows.Forms.BindingSource> し `GetData` ます。 次の例には、表示されるデータに合わせて列のサイズを変更するコードが含まれてい <xref:System.Windows.Forms.DataGridView> ます。

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#10)]

## <a name="testing-the-application"></a>アプリケーションのテスト

フォームをテストして、期待どおりに動作することを確認します。

#### <a name="to-test-the-form"></a>フォームをテストするには

- アプリケーションをコンパイルして実行します。

  2つのコントロールが1つ上に表示され <xref:System.Windows.Forms.DataGridView> ます。 [上位] は Northwind テーブルの顧客であり、 `Customers` 一番下には `Orders` 選択した顧客に対応するがあります。 上部で異なる行を選択すると、 <xref:System.Windows.Forms.DataGridView> それに応じて下位の内容が <xref:System.Windows.Forms.DataGridView> 変化します。

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
- [Windows フォーム DataGridView コントロールでのデータの表示](displaying-data-in-the-windows-forms-datagridview-control.md)
- [方法: Windows フォームの 2 つの DataGridView コントロールを使用してマスター/詳細形式のフォームを作成する](create-a-master-detail-form-using-two-datagridviews.md)
- [接続情報の保護](/dotnet/framework/data/adonet/protecting-connection-information)
