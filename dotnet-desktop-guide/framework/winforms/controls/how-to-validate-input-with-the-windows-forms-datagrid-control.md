---
title: DataGrid コントロールを使用した入力の検証
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid control [Windows Forms], examples
- user input [Windows Forms], validating
- examples [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], validating input
- validation [Windows Forms], user input
ms.assetid: f1e9c3a0-d0a1-4893-a615-b4b0db046c63
ms.openlocfilehash: 3958089007401d2e977c9c96f07c9196e6216596
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983000"
---
# <a name="how-to-validate-input-with-the-windows-forms-datagrid-control"></a>方法: Windows フォームの DataGrid コントロールを使用して入力データを検証する

> [!NOTE]
> <xref:System.Windows.Forms.DataGridView> コントロールは、<xref:System.Windows.Forms.DataGrid> コントロールに代わると共に追加の機能を提供します。ただし、<xref:System.Windows.Forms.DataGrid> コントロールは、下位互換性を保つ目的および将来使用する目的で保持されます。 詳細については、「[Windows フォームの DataGridView コントロールと DataGrid コントロールの違いについて](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)」を参照してください。

Windows フォームコントロールで使用できる入力検証には2種類あり <xref:System.Windows.Forms.DataGrid> ます。 整数の文字列など、許容できないデータ型の値をセルに入力しようとすると、新しい無効な値が古い値に置き換えられます。 この種類の入力検証は自動的に行われ、カスタマイズすることはできません。

その他の種類の入力検証を使用すると、許容できないデータを拒否することができます。たとえば、1以上である必要があるフィールドの0値、または不適切な文字列です。 これは、イベントまたはイベントのイベントハンドラーを記述することによって、データセットで実行され <xref:System.Data.DataTable.ColumnChanging> <xref:System.Data.DataTable.RowChanging> ます。 次の例では、イベントを使用し <xref:System.Data.DataTable.ColumnChanging> ます。これは、特に "Product" 列に対して許容できない値が許可されていないためです。 <xref:System.Data.DataTable.RowChanging>"終了日" 列の値が同じ行の "開始日" 列より後であるかどうかを確認するには、イベントを使用します。

## <a name="to-validate-user-input"></a>ユーザー入力を検証するには

1. 適切なテーブルのイベントを処理するコードを記述 <xref:System.Data.DataTable.ColumnChanging> します。 不適切な入力が検出された場合は、 <xref:System.Data.DataRow.SetColumnError%2A> オブジェクトのメソッドを呼び出し <xref:System.Data.DataRow> ます。

    ```vb
    Private Sub Customers_ColumnChanging(ByVal sender As Object, _
    ByVal e As System.Data.DataColumnChangeEventArgs)
       ' Only check for errors in the Product column
       If (e.Column.ColumnName.Equals("Product")) Then
          ' Do not allow "Automobile" as a product.
          If CType(e.ProposedValue, String) = "Automobile" Then
             Dim badValue As Object = e.ProposedValue
             e.ProposedValue = "Bad Data"
             e.Row.RowError = "The Product column contains an error"
             e.Row.SetColumnError(e.Column, "Product cannot be " & _
             CType(badValue, String))
          End If
       End If
    End Sub
    ```

    ```csharp
    //Handle column changing events on the Customers table
    private void Customers_ColumnChanging(object sender, System.Data.DataColumnChangeEventArgs e) {

       //Only check for errors in the Product column
       if (e.Column.ColumnName.Equals("Product")) {

          //Do not allow "Automobile" as a product
          if (e.ProposedValue.Equals("Automobile")) {
             object badValue = e.ProposedValue;
             e.ProposedValue = "Bad Data";
             e.Row.RowError = "The Product column contains an error";
             e.Row.SetColumnError(e.Column, "Product cannot be " + badValue);
          }
       }
    }
    ```

2. イベントハンドラーをイベントに接続します。

    フォームのイベントまたはそのコンストラクター内に次のコードを配置 <xref:System.Windows.Forms.Form.Load> します。

    ```vb
    ' Assumes the grid is bound to a dataset called customersDataSet1
    ' with a table called Customers.
    ' Put this code in the form's Load event or its constructor.
    AddHandler customersDataSet1.Tables("Customers").ColumnChanging, AddressOf Customers_ColumnChanging
    ```

    ```csharp
    // Assumes the grid is bound to a dataset called customersDataSet1
    // with a table called Customers.
    // Put this code in the form's Load event or its constructor.
    customersDataSet1.Tables["Customers"].ColumnChanging += new DataColumnChangeEventHandler(this.Customers_ColumnChanging);
    ```

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.DataGrid>
- <xref:System.Data.DataTable.ColumnChanging>
- <xref:System.Data.DataRow.SetColumnError%2A>
- [DataGrid コントロール](datagrid-control-windows-forms.md)
