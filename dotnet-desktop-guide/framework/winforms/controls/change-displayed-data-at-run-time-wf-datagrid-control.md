---
title: 実行時に DataGrid コントロールに表示されるデータを変更する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DataGrid control [Windows Forms], dynamically changing at run time
- DataGrid control [Windows Forms], data binding
- cells [Windows Forms], changing DataGrid cell values
ms.assetid: 0c7a6d00-30de-416e-8223-0a81ddb4c1f8
ms.openlocfilehash: 41f22b3149c1d411dcfbdeec4b83c6c0c52c10df
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96975106"
---
# <a name="how-to-change-displayed-data-at-run-time-in-the-windows-forms-datagrid-control"></a><span data-ttu-id="49687-102">方法: Windows フォーム DataGrid コントロールに表示されるデータを実行時に変更する</span><span class="sxs-lookup"><span data-stu-id="49687-102">How to: Change Displayed Data at Run Time in the Windows Forms DataGrid Control</span></span>

> [!NOTE]
> <span data-ttu-id="49687-103"><xref:System.Windows.Forms.DataGridView> コントロールは、<xref:System.Windows.Forms.DataGrid> コントロールに代わると共に追加の機能を提供します。ただし、<xref:System.Windows.Forms.DataGrid> コントロールは、下位互換性を保つ目的および将来使用する目的で保持されます。</span><span class="sxs-lookup"><span data-stu-id="49687-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="49687-104">詳細については、「[Windows フォームの DataGridView コントロールと DataGrid コントロールの違いについて](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49687-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="49687-105"><xref:System.Windows.Forms.DataGrid>デザイン時の機能を使用して Windows フォームを作成した後、 <xref:System.Data.DataSet> 実行時にグリッドのオブジェクトの要素を動的に変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="49687-105">After you have created a Windows Forms <xref:System.Windows.Forms.DataGrid> using the design-time features, you may also wish to dynamically change elements of the <xref:System.Data.DataSet> object of the grid at run time.</span></span> <span data-ttu-id="49687-106">これには、テーブルの個々の値への変更や、コントロールにバインドされているデータソースの変更が含まれる場合があり <xref:System.Windows.Forms.DataGrid> ます。</span><span class="sxs-lookup"><span data-stu-id="49687-106">This can include changes to either individual values of the table or changing which data source is bound to the <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="49687-107">個々の値に対する変更は、コントロールではなく、オブジェクトを介して行われ <xref:System.Data.DataSet> <xref:System.Windows.Forms.DataGrid> ます。</span><span class="sxs-lookup"><span data-stu-id="49687-107">Changes to individual values are done through the <xref:System.Data.DataSet> object, not the <xref:System.Windows.Forms.DataGrid> control.</span></span>  
  
### <a name="to-change-data-programmatically"></a><span data-ttu-id="49687-108">プログラムによってデータを変更するには</span><span class="sxs-lookup"><span data-stu-id="49687-108">To change data programmatically</span></span>  
  
1. <span data-ttu-id="49687-109">オブジェクトから目的のテーブルを指定し、 <xref:System.Data.DataSet> 目的の行とフィールドをテーブルから指定して、セルを新しい値に設定します。</span><span class="sxs-lookup"><span data-stu-id="49687-109">Specify the desired table from the <xref:System.Data.DataSet> object and the desired row and field from the table and set the cell equal to the new value.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="49687-110"><xref:System.Data.DataSet>テーブルの最初の行または最初の行を指定するには、0を使用します。</span><span class="sxs-lookup"><span data-stu-id="49687-110">To specify the first table of the <xref:System.Data.DataSet> or the first row of the table, use 0.</span></span>  
  
     <span data-ttu-id="49687-111">次の例では、をクリックして、データセットの最初のテーブルの最初の行の2番目のエントリを変更する方法を示し `Button1` ます。</span><span class="sxs-lookup"><span data-stu-id="49687-111">The following example shows how to change the second entry of the first row of the first table of a dataset by clicking `Button1`.</span></span> <span data-ttu-id="49687-112"><xref:System.Data.DataSet>( `ds` ) とテーブル ( `0` および) は、以前に `1` 作成されています。</span><span class="sxs-lookup"><span data-stu-id="49687-112">The <xref:System.Data.DataSet> (`ds`) and Tables (`0` and `1`) were previously created.</span></span>  
  
    ```vb  
    Protected Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       ds.tables(0).rows(0)(1) = "NewEntry"  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       ds.Tables[0].Rows[0][1]="NewEntry";  
    }  
    ```  
  
    ```cpp  
    private:
       void button1_Click(System::Object^ sender, System::EventArgs^ e)  
       {  
          dataSet1->Tables[0]->Rows[0][1] = "NewEntry";  
       }  
    ```  
  
     <span data-ttu-id="49687-113">(Visual C#、Visual C++)フォームのコンストラクターに次のコードを配置して、イベントハンドラーを登録します。</span><span class="sxs-lookup"><span data-stu-id="49687-113">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=  
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     <span data-ttu-id="49687-114">実行時に、メソッドを使用し <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> て、 <xref:System.Windows.Forms.DataGrid> コントロールを別のデータソースにバインドできます。</span><span class="sxs-lookup"><span data-stu-id="49687-114">At run time you can use the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to bind the <xref:System.Windows.Forms.DataGrid> control to a different data source.</span></span> <span data-ttu-id="49687-115">たとえば、複数の ADO.NET データコントロールがあり、それぞれが別のデータベースに接続されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="49687-115">For example, you may have several ADO.NET data controls, each connected to a different database.</span></span>  
  
### <a name="to-change-the-datasource-programmatically"></a><span data-ttu-id="49687-116">プログラムによってデータソースを変更するには</span><span class="sxs-lookup"><span data-stu-id="49687-116">To change the DataSource programmatically</span></span>  
  
1. <span data-ttu-id="49687-117">メソッドに、 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> バインド先のデータソースおよびテーブルの名前を設定します。</span><span class="sxs-lookup"><span data-stu-id="49687-117">Set the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to the name of the data source and table you want to bind to.</span></span>  
  
     <span data-ttu-id="49687-118">次の例では、メソッドを使用して日付ソースを変更し、 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> Pubs データベースの Authors テーブルに接続されている ADO.NET data control (adoPubsAuthors) に変換する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="49687-118">The following example shows how to change the date source using the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to an ADO.NET data control (adoPubsAuthors) that is connected to the Authors table in the Pubs database.</span></span>  
  
    ```vb  
    Private Sub ResetSource()  
       DataGrid1.SetDataBinding(adoPubsAuthors, "Authors")  
    End Sub  
    ```  
  
    ```csharp  
    private void ResetSource()  
    {  
       DataGrid1.SetDataBinding(adoPubsAuthors, "Authors");  
    }  
    ```  
  
    ```cpp  
    private:  
       void ResetSource()  
       {  
          dataGrid1->SetDataBinding(adoPubsAuthors, "Authors");  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="49687-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="49687-119">See also</span></span>

- [<span data-ttu-id="49687-120">ADO.NET データセット</span><span class="sxs-lookup"><span data-stu-id="49687-120">ADO.NET DataSets</span></span>](/dotnet/framework/data/adonet/ado-net-datasets)
- [<span data-ttu-id="49687-121">方法: Windows フォーム DataGrid コントロールの列を削除するまたは非表示にする</span><span class="sxs-lookup"><span data-stu-id="49687-121">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="49687-122">方法: Windows フォーム DataGrid コントロールにテーブルと列を追加する</span><span class="sxs-lookup"><span data-stu-id="49687-122">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="49687-123">方法: データ ソースに Windows フォーム DataGrid コントロールをバインドする</span><span class="sxs-lookup"><span data-stu-id="49687-123">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
