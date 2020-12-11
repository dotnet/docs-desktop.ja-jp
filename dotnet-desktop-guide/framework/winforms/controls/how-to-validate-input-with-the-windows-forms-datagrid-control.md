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
# <a name="how-to-validate-input-with-the-windows-forms-datagrid-control"></a><span data-ttu-id="a0af7-102">方法: Windows フォームの DataGrid コントロールを使用して入力データを検証する</span><span class="sxs-lookup"><span data-stu-id="a0af7-102">How to: Validate Input with the Windows Forms DataGrid Control</span></span>

> [!NOTE]
> <span data-ttu-id="a0af7-103"><xref:System.Windows.Forms.DataGridView> コントロールは、<xref:System.Windows.Forms.DataGrid> コントロールに代わると共に追加の機能を提供します。ただし、<xref:System.Windows.Forms.DataGrid> コントロールは、下位互換性を保つ目的および将来使用する目的で保持されます。</span><span class="sxs-lookup"><span data-stu-id="a0af7-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="a0af7-104">詳細については、「[Windows フォームの DataGridView コントロールと DataGrid コントロールの違いについて](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0af7-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>

<span data-ttu-id="a0af7-105">Windows フォームコントロールで使用できる入力検証には2種類あり <xref:System.Windows.Forms.DataGrid> ます。</span><span class="sxs-lookup"><span data-stu-id="a0af7-105">There are two types of input validation available for the Windows Forms <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="a0af7-106">整数の文字列など、許容できないデータ型の値をセルに入力しようとすると、新しい無効な値が古い値に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="a0af7-106">If the user attempts to enter a value that is of an unacceptable data type for the cell, for example a string into an integer, the new invalid value is replaced with the old value.</span></span> <span data-ttu-id="a0af7-107">この種類の入力検証は自動的に行われ、カスタマイズすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a0af7-107">This kind of input validation is done automatically and cannot be customized.</span></span>

<span data-ttu-id="a0af7-108">その他の種類の入力検証を使用すると、許容できないデータを拒否することができます。たとえば、1以上である必要があるフィールドの0値、または不適切な文字列です。</span><span class="sxs-lookup"><span data-stu-id="a0af7-108">The other type of input validation can be used to reject any unacceptable data, for example a 0 value in a field that must be greater than or equal to 1, or an inappropriate string.</span></span> <span data-ttu-id="a0af7-109">これは、イベントまたはイベントのイベントハンドラーを記述することによって、データセットで実行され <xref:System.Data.DataTable.ColumnChanging> <xref:System.Data.DataTable.RowChanging> ます。</span><span class="sxs-lookup"><span data-stu-id="a0af7-109">This is done in the dataset by writing an event handler for the <xref:System.Data.DataTable.ColumnChanging> or <xref:System.Data.DataTable.RowChanging> event.</span></span> <span data-ttu-id="a0af7-110">次の例では、イベントを使用し <xref:System.Data.DataTable.ColumnChanging> ます。これは、特に "Product" 列に対して許容できない値が許可されていないためです。</span><span class="sxs-lookup"><span data-stu-id="a0af7-110">The example below uses the <xref:System.Data.DataTable.ColumnChanging> event because the unacceptable value is disallowed for the "Product" column in particular.</span></span> <span data-ttu-id="a0af7-111"><xref:System.Data.DataTable.RowChanging>"終了日" 列の値が同じ行の "開始日" 列より後であるかどうかを確認するには、イベントを使用します。</span><span class="sxs-lookup"><span data-stu-id="a0af7-111">You might use the <xref:System.Data.DataTable.RowChanging> event for checking that the value of an "End Date" column is later than the "Start Date" column in the same row.</span></span>

## <a name="to-validate-user-input"></a><span data-ttu-id="a0af7-112">ユーザー入力を検証するには</span><span class="sxs-lookup"><span data-stu-id="a0af7-112">To validate user input</span></span>

1. <span data-ttu-id="a0af7-113">適切なテーブルのイベントを処理するコードを記述 <xref:System.Data.DataTable.ColumnChanging> します。</span><span class="sxs-lookup"><span data-stu-id="a0af7-113">Write code to handle the <xref:System.Data.DataTable.ColumnChanging> event for the appropriate table.</span></span> <span data-ttu-id="a0af7-114">不適切な入力が検出された場合は、 <xref:System.Data.DataRow.SetColumnError%2A> オブジェクトのメソッドを呼び出し <xref:System.Data.DataRow> ます。</span><span class="sxs-lookup"><span data-stu-id="a0af7-114">When inappropriate input is detected, call the <xref:System.Data.DataRow.SetColumnError%2A> method of the <xref:System.Data.DataRow> object.</span></span>

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

2. <span data-ttu-id="a0af7-115">イベントハンドラーをイベントに接続します。</span><span class="sxs-lookup"><span data-stu-id="a0af7-115">Connect the event handler to the event.</span></span>

    <span data-ttu-id="a0af7-116">フォームのイベントまたはそのコンストラクター内に次のコードを配置 <xref:System.Windows.Forms.Form.Load> します。</span><span class="sxs-lookup"><span data-stu-id="a0af7-116">Place the following code within either the form's <xref:System.Windows.Forms.Form.Load> event or its constructor.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="a0af7-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="a0af7-117">See also</span></span>

- <xref:System.Windows.Forms.DataGrid>
- <xref:System.Data.DataTable.ColumnChanging>
- <xref:System.Data.DataRow.SetColumnError%2A>
- [<span data-ttu-id="a0af7-118">DataGrid コントロール</span><span class="sxs-lookup"><span data-stu-id="a0af7-118">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
