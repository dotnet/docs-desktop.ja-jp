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
# <a name="how-to-change-displayed-data-at-run-time-in-the-windows-forms-datagrid-control"></a>方法: Windows フォーム DataGrid コントロールに表示されるデータを実行時に変更する

> [!NOTE]
> <xref:System.Windows.Forms.DataGridView> コントロールは、<xref:System.Windows.Forms.DataGrid> コントロールに代わると共に追加の機能を提供します。ただし、<xref:System.Windows.Forms.DataGrid> コントロールは、下位互換性を保つ目的および将来使用する目的で保持されます。 詳細については、「[Windows フォームの DataGridView コントロールと DataGrid コントロールの違いについて](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)」を参照してください。  
  
 <xref:System.Windows.Forms.DataGrid>デザイン時の機能を使用して Windows フォームを作成した後、 <xref:System.Data.DataSet> 実行時にグリッドのオブジェクトの要素を動的に変更することもできます。 これには、テーブルの個々の値への変更や、コントロールにバインドされているデータソースの変更が含まれる場合があり <xref:System.Windows.Forms.DataGrid> ます。 個々の値に対する変更は、コントロールではなく、オブジェクトを介して行われ <xref:System.Data.DataSet> <xref:System.Windows.Forms.DataGrid> ます。  
  
### <a name="to-change-data-programmatically"></a>プログラムによってデータを変更するには  
  
1. オブジェクトから目的のテーブルを指定し、 <xref:System.Data.DataSet> 目的の行とフィールドをテーブルから指定して、セルを新しい値に設定します。  
  
    > [!NOTE]
    > <xref:System.Data.DataSet>テーブルの最初の行または最初の行を指定するには、0を使用します。  
  
     次の例では、をクリックして、データセットの最初のテーブルの最初の行の2番目のエントリを変更する方法を示し `Button1` ます。 <xref:System.Data.DataSet>( `ds` ) とテーブル ( `0` および) は、以前に `1` 作成されています。  
  
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
  
     (Visual C#、Visual C++)フォームのコンストラクターに次のコードを配置して、イベントハンドラーを登録します。  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=  
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     実行時に、メソッドを使用し <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> て、 <xref:System.Windows.Forms.DataGrid> コントロールを別のデータソースにバインドできます。 たとえば、複数の ADO.NET データコントロールがあり、それぞれが別のデータベースに接続されている場合があります。  
  
### <a name="to-change-the-datasource-programmatically"></a>プログラムによってデータソースを変更するには  
  
1. メソッドに、 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> バインド先のデータソースおよびテーブルの名前を設定します。  
  
     次の例では、メソッドを使用して日付ソースを変更し、 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> Pubs データベースの Authors テーブルに接続されている ADO.NET data control (adoPubsAuthors) に変換する方法を示します。  
  
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
  
## <a name="see-also"></a>関連項目

- [ADO.NET データセット](/dotnet/framework/data/adonet/ado-net-datasets)
- [方法: Windows フォーム DataGrid コントロールの列を削除するまたは非表示にする](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [方法: Windows フォーム DataGrid コントロールにテーブルと列を追加する](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [方法: データ ソースに Windows フォーム DataGrid コントロールをバインドする](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
