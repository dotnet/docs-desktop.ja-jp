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
# <a name="how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control"></a><span data-ttu-id="c799e-102">方法: Windows フォーム DataGrid コントロールの列を削除するまたは非表示にする</span><span class="sxs-lookup"><span data-stu-id="c799e-102">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>
> [!NOTE]
> <span data-ttu-id="c799e-103"><xref:System.Windows.Forms.DataGridView> コントロールは、<xref:System.Windows.Forms.DataGrid> コントロールに代わると共に追加の機能を提供します。ただし、<xref:System.Windows.Forms.DataGrid> コントロールは、下位互換性を保つ目的および将来使用する目的で保持されます。</span><span class="sxs-lookup"><span data-stu-id="c799e-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="c799e-104">詳細については、「[Windows フォームの DataGridView コントロールと DataGrid コントロールの違いについて](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c799e-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="c799e-105"><xref:System.Windows.Forms.DataGrid> <xref:System.Windows.Forms.GridColumnStylesCollection> <xref:System.Windows.Forms.DataGridColumnStyle> オブジェクトおよびオブジェクト (クラスのメンバー) のプロパティとメソッドを使用して、Windows フォームコントロールの列をプログラムによって削除または非表示にすることができ <xref:System.Windows.Forms.DataGridTableStyle> ます。</span><span class="sxs-lookup"><span data-stu-id="c799e-105">You can programmatically delete or hide columns in the Windows Forms <xref:System.Windows.Forms.DataGrid> control by using the properties and methods of the <xref:System.Windows.Forms.GridColumnStylesCollection> and <xref:System.Windows.Forms.DataGridColumnStyle> objects (which are members of the <xref:System.Windows.Forms.DataGridTableStyle> class).</span></span>  
  
 <span data-ttu-id="c799e-106">削除された列または非表示の列は、グリッドがバインドされているデータソースにまだ存在し、プログラムによってアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c799e-106">The deleted or hidden columns still exist in the data source the grid is bound to, and can still be accessed programmatically.</span></span> <span data-ttu-id="c799e-107">これらは、datagrid に表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="c799e-107">They are just no longer visible in the datagrid.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c799e-108">アプリケーションが特定のデータ列にアクセスせず、datagrid に表示させたくない場合は、最初にデータソースにそれらを含める必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c799e-108">If your application does not access certain columns of data, and you do not want them displayed in the datagrid, then it is probably not necessary to include them in the data source in the first place.</span></span>  
  
### <a name="to-delete-a-column-from-the-datagrid-programmatically"></a><span data-ttu-id="c799e-109">プログラムによって DataGrid から列を削除するには</span><span class="sxs-lookup"><span data-stu-id="c799e-109">To delete a column from the DataGrid programmatically</span></span>  
  
1. <span data-ttu-id="c799e-110">フォームの宣言領域で、クラスの新しいインスタンスを宣言し <xref:System.Windows.Forms.DataGridTableStyle> ます。</span><span class="sxs-lookup"><span data-stu-id="c799e-110">In the declarations area of your form, declare a new instance of the <xref:System.Windows.Forms.DataGridTableStyle> class.</span></span>  
  
2. <span data-ttu-id="c799e-111">プロパティを、 <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A?displayProperty=nameWithType> スタイルを適用するデータソース内のテーブルに設定します。</span><span class="sxs-lookup"><span data-stu-id="c799e-111">Set the <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A?displayProperty=nameWithType> property to the table in your data source that you want to apply the style to.</span></span> <span data-ttu-id="c799e-112">次の例で <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> は、プロパティを使用します。これは既に設定されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="c799e-112">The following example uses the <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> property, which it assumes is already set.</span></span>  
  
3. <span data-ttu-id="c799e-113">新しい <xref:System.Windows.Forms.DataGridTableStyle> オブジェクトを datagrid のテーブルスタイルのコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="c799e-113">Add the new <xref:System.Windows.Forms.DataGridTableStyle> object to the datagrid's table styles collection.</span></span>  
  
4. <span data-ttu-id="c799e-114"><xref:System.Windows.Forms.GridColumnStylesCollection.RemoveAt%2A> <xref:System.Windows.Forms.DataGrid> <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> 削除する列の列インデックスを指定して、のコレクションのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="c799e-114">Call the <xref:System.Windows.Forms.GridColumnStylesCollection.RemoveAt%2A> method of the <xref:System.Windows.Forms.DataGrid>'s <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> collection, specifying the column index of the column to delete.</span></span>  
  
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
  
### <a name="to-hide-a-column-in-the-datagrid-programmatically"></a><span data-ttu-id="c799e-115">プログラムによって DataGrid の列を非表示にするには</span><span class="sxs-lookup"><span data-stu-id="c799e-115">To hide a column in the DataGrid programmatically</span></span>  
  
1. <span data-ttu-id="c799e-116">フォームの宣言領域で、クラスの新しいインスタンスを宣言し <xref:System.Windows.Forms.DataGridTableStyle> ます。</span><span class="sxs-lookup"><span data-stu-id="c799e-116">In the declarations area of your form, declare a new instance of the <xref:System.Windows.Forms.DataGridTableStyle> class.</span></span>  
  
2. <span data-ttu-id="c799e-117"><xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A>のプロパティを、 <xref:System.Windows.Forms.DataGridTableStyle> スタイルを適用するデータソース内のテーブルに設定します。</span><span class="sxs-lookup"><span data-stu-id="c799e-117">Set the <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> property of the <xref:System.Windows.Forms.DataGridTableStyle> to the table in your data source that you want to apply the style to.</span></span> <span data-ttu-id="c799e-118">次のコード例では、 <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> プロパティを使用します。これは既に設定されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="c799e-118">The following code example uses the <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> property, which it assumes is already set.</span></span>  
  
3. <span data-ttu-id="c799e-119">新しい <xref:System.Windows.Forms.DataGridTableStyle> オブジェクトを datagrid のテーブルスタイルのコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="c799e-119">Add the new <xref:System.Windows.Forms.DataGridTableStyle> object to the datagrid's table styles collection.</span></span>  
  
4. <span data-ttu-id="c799e-120">列のプロパティを0に設定して、列を非表示 `Width` にします。非表示にする列の列インデックスを指定します。</span><span class="sxs-lookup"><span data-stu-id="c799e-120">Hide the column by setting its `Width` property to 0, specifying the column index of the column to hide.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c799e-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="c799e-121">See also</span></span>

- [<span data-ttu-id="c799e-122">方法: Windows フォーム DataGrid コントロールに表示されるデータを実行時に変更する</span><span class="sxs-lookup"><span data-stu-id="c799e-122">How to: Change Displayed Data at Run Time in the Windows Forms DataGrid Control</span></span>](change-displayed-data-at-run-time-wf-datagrid-control.md)
- [<span data-ttu-id="c799e-123">方法: Windows フォーム DataGrid コントロールにテーブルと列を追加する</span><span class="sxs-lookup"><span data-stu-id="c799e-123">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
