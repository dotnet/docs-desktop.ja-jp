---
title: DataGrid コントロールにテーブルと列を追加する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 2fe661b9-aa06-49b9-a314-a0d3cbfdcb4d
ms.openlocfilehash: 2db2e38c326cbcd78c58ee4fe00cd9ed20ae0e8a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982263"
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control"></a>方法: Windows フォーム DataGrid コントロールにテーブルと列を追加する

> [!NOTE]
> <xref:System.Windows.Forms.DataGridView> コントロールは、<xref:System.Windows.Forms.DataGrid> コントロールに代わると共に追加の機能を提供します。ただし、<xref:System.Windows.Forms.DataGrid> コントロールは、下位互換性を保つ目的および将来使用する目的で保持されます。 詳細については、「[Windows フォームの DataGridView コントロールと DataGrid コントロールの違いについて](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)」を参照してください。

<xref:System.Windows.Forms.DataGrid> **DataGridTableStyle** オブジェクトを作成し、コントロールの system.windows.forms.datagrid.tablestyles プロパティを使用してアクセスする **gridtable collection** オブジェクトに追加することによって Windows フォーム、テーブルと列にデータを表示できます <xref:System.Windows.Forms.DataGrid> 。  各テーブルスタイルには、 **DataGridTableStyle** オブジェクトの **MappingName** プロパティで指定されているデータテーブルの内容が表示されます。 既定では、列スタイルが指定されていないテーブルスタイルには、そのデータテーブル内のすべての列が表示されます。 **System.windows.forms.datagridcolumnstyle>** オブジェクトを **Gridcolumnstyles collection** オブジェクトに追加することによって、テーブル内のどの列を表示するかを制限できます。このオブジェクトには、各 **DataGridTableStyle** オブジェクトの **gridcolumnstyles** プロパティを使用してアクセスします。

### <a name="to-add-a-table-and-column-to-a-datagrid-programmatically"></a>プログラムで DataGrid にテーブルと列を追加するには

1. テーブルにデータを表示するには、最初にコントロールをデータセットにバインドする必要があり <xref:System.Windows.Forms.DataGrid> ます。 詳細については、「 [方法: Windows フォーム DataGrid コントロールをデータソースにバインドする](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)」を参照してください。

    > [!CAUTION]
    > 列のスタイルをプログラムで指定する場合は、 **DataGridTableStyle** オブジェクトを **gridtablestyles collection** オブジェクトに追加する前に、常に **system.windows.forms.datagridcolumnstyle>** オブジェクトを作成し、 **gridcolumnstyles collection** オブジェクトに追加します。 空の **DataGridTableStyle** オブジェクトをコレクションに追加すると、 **system.windows.forms.datagridcolumnstyle>** オブジェクトが自動的に生成されます。 その結果、重複する **MappingName** 値を持つ新しい **System.windows.forms.datagridcolumnstyle>** オブジェクトを **gridcolumn collection** オブジェクトに追加しようとすると、例外がスローされます。

2. 新しいテーブルスタイルを宣言し、そのマッピング名を設定します。

    ```vb
    Dim ts1 As New DataGridTableStyle()
    ts1.MappingName = "Customers"
    ```

    ```csharp
    DataGridTableStyle ts1 = new DataGridTableStyle();
    ts1.MappingName = "Customers";
    ```

    ```cpp
    DataGridTableStyle* ts1 = new DataGridTableStyle();
    ts1->MappingName = S"Customers";
    ```

3. 新しい列スタイルを宣言し、そのマッピング名とその他のプロパティを設定します。

    ```vb
    Dim myDataCol As New DataGridBoolColumn()
    myDataCol.HeaderText = "My New Column"
    myDataCol.MappingName = "Current"
    ```

    ```csharp
    DataGridBoolColumn myDataCol = new DataGridBoolColumn();
    myDataCol.HeaderText = "My New Column";
    myDataCol.MappingName = "Current";
    ```

    ```cpp
    DataGridBoolColumn^ myDataCol = gcnew DataGridBoolColumn();
    myDataCol->HeaderText = "My New Column";
    myDataCol->MappingName = "Current";
    ```

4. **Gridcolumnstylescollection** オブジェクトの **Add** メソッドを呼び出して、列をテーブルのスタイルに追加します。

    ```vb
    ts1.GridColumnStyles.Add(myDataCol)
    ```

    ```csharp
    ts1.GridColumnStyles.Add(myDataCol);
    ```

    ```cpp
    ts1->GridColumnStyles->Add(myDataCol);
    ```

5. テーブルスタイルをデータグリッドに追加するには、 **Gridtablestylescollection** オブジェクトの **Add** メソッドを呼び出します。

    ```vb
    DataGrid1.TableStyles.Add(ts1)
    ```

    ```csharp
    dataGrid1.TableStyles.Add(ts1);
    ```

    ```cpp
    dataGrid1->TableStyles->Add(ts1);
    ```

## <a name="see-also"></a>関連項目

- [DataGrid コントロール](datagrid-control-windows-forms.md)
- [方法: Windows フォーム DataGrid コントロールの列を削除するまたは非表示にする](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
