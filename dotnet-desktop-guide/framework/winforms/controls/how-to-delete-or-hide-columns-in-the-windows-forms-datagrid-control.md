---
title: DataGrid コントロールの列の削除または非表示
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], deleting columns
- DataGrid control [Windows Forms], deleting columns
- data grids [Windows Forms], hiding columns
- columns [Windows Forms], hiding
- columns [Windows Forms], deleting in data grids
- DataGrid control [Windows Forms], hiding columns
ms.assetid: bcd0dd96-6687-4c48-b0e1-d5287b93ac91
ms.openlocfilehash: c730be934e9b978bdaf09bc7e668b4318077fba5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980872"
---
# <a name="how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control"></a>方法: Windows フォーム DataGrid コントロールの列を削除するまたは非表示にする
> [!NOTE]
> <xref:System.Windows.Forms.DataGridView> コントロールは、<xref:System.Windows.Forms.DataGrid> コントロールに代わると共に追加の機能を提供します。ただし、<xref:System.Windows.Forms.DataGrid> コントロールは、下位互換性を保つ目的および将来使用する目的で保持されます。 詳細については、「[Windows フォームの DataGridView コントロールと DataGrid コントロールの違いについて](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)」を参照してください。  
  
 <xref:System.Windows.Forms.DataGrid> <xref:System.Windows.Forms.GridColumnStylesCollection> <xref:System.Windows.Forms.DataGridColumnStyle> オブジェクトおよびオブジェクト (クラスのメンバー) のプロパティとメソッドを使用して、Windows フォームコントロールの列をプログラムによって削除または非表示にすることができ <xref:System.Windows.Forms.DataGridTableStyle> ます。  
  
 削除された列または非表示の列は、グリッドがバインドされているデータソースにまだ存在し、プログラムによってアクセスできます。 これらは、datagrid に表示されなくなります。  
  
> [!NOTE]
> アプリケーションが特定のデータ列にアクセスせず、datagrid に表示させたくない場合は、最初にデータソースにそれらを含める必要はありません。  
  
### <a name="to-delete-a-column-from-the-datagrid-programmatically"></a>プログラムによって DataGrid から列を削除するには  
  
1. フォームの宣言領域で、クラスの新しいインスタンスを宣言し <xref:System.Windows.Forms.DataGridTableStyle> ます。  
  
2. プロパティを、 <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A?displayProperty=nameWithType> スタイルを適用するデータソース内のテーブルに設定します。 次の例で <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> は、プロパティを使用します。これは既に設定されていることを前提としています。  
  
3. 新しい <xref:System.Windows.Forms.DataGridTableStyle> オブジェクトを datagrid のテーブルスタイルのコレクションに追加します。  
  
4. <xref:System.Windows.Forms.GridColumnStylesCollection.RemoveAt%2A> <xref:System.Windows.Forms.DataGrid> <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> 削除する列の列インデックスを指定して、のコレクションのメソッドを呼び出します。  
  
    ```vb  
    ' Declare a new DataGridTableStyle in the  
    ' declarations area of your form.  
    Dim ts As DataGridTableStyle = New DataGridTableStyle()  
  
    Sub DeleteColumn()  
       ' Set the DataGridTableStyle.MappingName property  
       ' to the table in the data source to map to.  
       ts.MappingName = DataGrid1.DataMember  
  
       ' Add it to the datagrid's TableStyles collection  
       DataGrid1.TableStyles.Add(ts)  
  
       ' Delete the first column (index 0)  
       DataGrid1.TableStyles(0).GridColumnStyles.RemoveAt(0)  
    End Sub  
    ```  
  
    ```csharp  
    // Declare a new DataGridTableStyle in the  
    // declarations area of your form.  
    DataGridTableStyle ts = new DataGridTableStyle();  
  
    private void deleteColumn()  
    {  
       // Set the DataGridTableStyle.MappingName property  
       // to the table in the data source to map to.  
       ts.MappingName = dataGrid1.DataMember;  
  
       // Add it to the datagrid's TableStyles collection  
       dataGrid1.TableStyles.Add(ts);  
  
       // Delete the first column (index 0)  
       dataGrid1.TableStyles[0].GridColumnStyles.RemoveAt(0);  
    }  
    ```  
  
### <a name="to-hide-a-column-in-the-datagrid-programmatically"></a>プログラムによって DataGrid の列を非表示にするには  
  
1. フォームの宣言領域で、クラスの新しいインスタンスを宣言し <xref:System.Windows.Forms.DataGridTableStyle> ます。  
  
2. <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A>のプロパティを、 <xref:System.Windows.Forms.DataGridTableStyle> スタイルを適用するデータソース内のテーブルに設定します。 次のコード例では、 <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> プロパティを使用します。これは既に設定されていることを前提としています。  
  
3. 新しい <xref:System.Windows.Forms.DataGridTableStyle> オブジェクトを datagrid のテーブルスタイルのコレクションに追加します。  
  
4. 列のプロパティを0に設定して、列を非表示 `Width` にします。非表示にする列の列インデックスを指定します。  
  
    ```vb  
    ' Declare a new DataGridTableStyle in the  
    ' declarations area of your form.  
    Dim ts As DataGridTableStyle = New DataGridTableStyle()  
  
    Sub HideColumn()  
       ' Set the DataGridTableStyle.MappingName property  
       ' to the table in the data source to map to.  
       ts.MappingName = DataGrid1.DataMember  
  
       ' Add it to the datagrid's TableStyles collection  
       DataGrid1.TableStyles.Add(ts)  
  
       ' Hide the first column (index 0)  
       DataGrid1.TableStyles(0).GridColumnStyles(0).Width = 0  
    End Sub  
    ```  
  
    ```csharp  
    // Declare a new DataGridTableStyle in the  
    // declarations area of your form.  
    DataGridTableStyle ts = new DataGridTableStyle();  
  
    private void hideColumn()  
    {  
       // Set the DataGridTableStyle.MappingName property  
       // to the table in the data source to map to.  
       ts.MappingName = dataGrid1.DataMember;  
  
       // Add it to the datagrid's TableStyles collection  
       dataGrid1.TableStyles.Add(ts);  
  
       // Hide the first column (index 0)  
       dataGrid1.TableStyles[0].GridColumnStyles[0].Width = 0;  
    }  
    ```  
  
## <a name="see-also"></a>関連項目

- [方法: Windows フォーム DataGrid コントロールに表示されるデータを実行時に変更する](change-displayed-data-at-run-time-wf-datagrid-control.md)
- [方法: Windows フォーム DataGrid コントロールにテーブルと列を追加する](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
