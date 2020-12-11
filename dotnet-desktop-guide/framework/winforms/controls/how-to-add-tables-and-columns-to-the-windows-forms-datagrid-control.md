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
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control"></a><span data-ttu-id="eaf1f-102">方法: Windows フォーム DataGrid コントロールにテーブルと列を追加する</span><span class="sxs-lookup"><span data-stu-id="eaf1f-102">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>

> [!NOTE]
> <span data-ttu-id="eaf1f-103"><xref:System.Windows.Forms.DataGridView> コントロールは、<xref:System.Windows.Forms.DataGrid> コントロールに代わると共に追加の機能を提供します。ただし、<xref:System.Windows.Forms.DataGrid> コントロールは、下位互換性を保つ目的および将来使用する目的で保持されます。</span><span class="sxs-lookup"><span data-stu-id="eaf1f-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="eaf1f-104">詳細については、「[Windows フォームの DataGridView コントロールと DataGrid コントロールの違いについて](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eaf1f-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>

<span data-ttu-id="eaf1f-105"><xref:System.Windows.Forms.DataGrid> **DataGridTableStyle** オブジェクトを作成し、コントロールの system.windows.forms.datagrid.tablestyles プロパティを使用してアクセスする **gridtable collection** オブジェクトに追加することによって Windows フォーム、テーブルと列にデータを表示できます <xref:System.Windows.Forms.DataGrid> 。 </span><span class="sxs-lookup"><span data-stu-id="eaf1f-105">You can display data in the Windows Forms <xref:System.Windows.Forms.DataGrid> control in tables and columns by creating **DataGridTableStyle** objects and adding them to the **GridTableStylesCollection** object, which is accessed through the <xref:System.Windows.Forms.DataGrid> control's **TableStyles** property.</span></span> <span data-ttu-id="eaf1f-106">各テーブルスタイルには、 **DataGridTableStyle** オブジェクトの **MappingName** プロパティで指定されているデータテーブルの内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="eaf1f-106">Each table style displays the contents of whatever data table is specified in the **DataGridTableStyle** object's **MappingName** property.</span></span> <span data-ttu-id="eaf1f-107">既定では、列スタイルが指定されていないテーブルスタイルには、そのデータテーブル内のすべての列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="eaf1f-107">By default, a table style with no column styles specified will display all the columns within that data table.</span></span> <span data-ttu-id="eaf1f-108">**System.windows.forms.datagridcolumnstyle>** オブジェクトを **Gridcolumnstyles collection** オブジェクトに追加することによって、テーブル内のどの列を表示するかを制限できます。このオブジェクトには、各 **DataGridTableStyle** オブジェクトの **gridcolumnstyles** プロパティを使用してアクセスします。</span><span class="sxs-lookup"><span data-stu-id="eaf1f-108">You can restrict which columns from the table appear by adding **DataGridColumnStyle** objects to the **GridColumnStylesCollection** object, which is accessed through the **GridColumnStyles** property of each **DataGridTableStyle** object.</span></span>

### <a name="to-add-a-table-and-column-to-a-datagrid-programmatically"></a><span data-ttu-id="eaf1f-109">プログラムで DataGrid にテーブルと列を追加するには</span><span class="sxs-lookup"><span data-stu-id="eaf1f-109">To add a table and column to a DataGrid programmatically</span></span>

1. <span data-ttu-id="eaf1f-110">テーブルにデータを表示するには、最初にコントロールをデータセットにバインドする必要があり <xref:System.Windows.Forms.DataGrid> ます。</span><span class="sxs-lookup"><span data-stu-id="eaf1f-110">In order to display data in the table, you must first bind the <xref:System.Windows.Forms.DataGrid> control to a dataset.</span></span> <span data-ttu-id="eaf1f-111">詳細については、「 [方法: Windows フォーム DataGrid コントロールをデータソースにバインドする](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eaf1f-111">For more information, see [How to: Bind the Windows Forms DataGrid Control to a Data Source](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).</span></span>

    > [!CAUTION]
    > <span data-ttu-id="eaf1f-112">列のスタイルをプログラムで指定する場合は、 **DataGridTableStyle** オブジェクトを **gridtablestyles collection** オブジェクトに追加する前に、常に **system.windows.forms.datagridcolumnstyle>** オブジェクトを作成し、 **gridcolumnstyles collection** オブジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="eaf1f-112">When programmatically specifying column styles, always create **DataGridColumnStyle** objects and add them to the **GridColumnStylesCollection** object before adding **DataGridTableStyle** objects to the **GridTableStylesCollection** object.</span></span> <span data-ttu-id="eaf1f-113">空の **DataGridTableStyle** オブジェクトをコレクションに追加すると、 **system.windows.forms.datagridcolumnstyle>** オブジェクトが自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="eaf1f-113">When you add an empty **DataGridTableStyle** object to the collection, **DataGridColumnStyle** objects are automatically generated for you.</span></span> <span data-ttu-id="eaf1f-114">その結果、重複する **MappingName** 値を持つ新しい **System.windows.forms.datagridcolumnstyle>** オブジェクトを **gridcolumn collection** オブジェクトに追加しようとすると、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="eaf1f-114">Consequently, an exception will be thrown if you try to add new **DataGridColumnStyle** objects with duplicate **MappingName** values to the **GridColumnStylesCollection** object.</span></span>

2. <span data-ttu-id="eaf1f-115">新しいテーブルスタイルを宣言し、そのマッピング名を設定します。</span><span class="sxs-lookup"><span data-stu-id="eaf1f-115">Declare a new table style and set its mapping name.</span></span>

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

3. <span data-ttu-id="eaf1f-116">新しい列スタイルを宣言し、そのマッピング名とその他のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="eaf1f-116">Declare a new column style and set its mapping name and other properties.</span></span>

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

4. <span data-ttu-id="eaf1f-117">**Gridcolumnstylescollection** オブジェクトの **Add** メソッドを呼び出して、列をテーブルのスタイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="eaf1f-117">Call the **Add** method of the **GridColumnStylesCollection** object to add the column to the table style</span></span>

    ```vb
    ts1.GridColumnStyles.Add(myDataCol)
    ```

    ```csharp
    ts1.GridColumnStyles.Add(myDataCol);
    ```

    ```cpp
    ts1->GridColumnStyles->Add(myDataCol);
    ```

5. <span data-ttu-id="eaf1f-118">テーブルスタイルをデータグリッドに追加するには、 **Gridtablestylescollection** オブジェクトの **Add** メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="eaf1f-118">Call the **Add** method of the **GridTableStylesCollection** object to add the table style to the data grid.</span></span>

    ```vb
    DataGrid1.TableStyles.Add(ts1)
    ```

    ```csharp
    dataGrid1.TableStyles.Add(ts1);
    ```

    ```cpp
    dataGrid1->TableStyles->Add(ts1);
    ```

## <a name="see-also"></a><span data-ttu-id="eaf1f-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="eaf1f-119">See also</span></span>

- [<span data-ttu-id="eaf1f-120">DataGrid コントロール</span><span class="sxs-lookup"><span data-stu-id="eaf1f-120">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
- [<span data-ttu-id="eaf1f-121">方法: Windows フォーム DataGrid コントロールの列を削除するまたは非表示にする</span><span class="sxs-lookup"><span data-stu-id="eaf1f-121">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
