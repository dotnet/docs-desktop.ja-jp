---
title: DataGrid コントロールを使用して Master-Detail リストを作成する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 20388c6a-94f9-4d96-be18-8c200491247f
ms.openlocfilehash: e8ab63d52d97a8a6e6f60da741186e3937350e1e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980884"
---
# <a name="how-to-create-masterdetail-lists-with-the-windows-forms-datagrid-control"></a><span data-ttu-id="f4e0a-102">方法: Windows フォーム DataGrid コントロールを使用してマスター/詳細リストを作成する</span><span class="sxs-lookup"><span data-stu-id="f4e0a-102">How to: Create Master/Detail Lists with the Windows Forms DataGrid Control</span></span>
> [!NOTE]
> <span data-ttu-id="f4e0a-103"><xref:System.Windows.Forms.DataGridView> コントロールは、<xref:System.Windows.Forms.DataGrid> コントロールに代わると共に追加の機能を提供します。ただし、<xref:System.Windows.Forms.DataGrid> コントロールは、下位互換性を保つ目的および将来使用する目的で保持されます。</span><span class="sxs-lookup"><span data-stu-id="f4e0a-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="f4e0a-104">詳細については、「[Windows フォームの DataGridView コントロールと DataGrid コントロールの違いについて](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4e0a-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="f4e0a-105">に <xref:System.Data.DataSet> 一連の関連テーブルが含まれている場合は、2つのコントロールを使用して <xref:System.Windows.Forms.DataGrid> 、マスター/詳細形式でデータを表示できます。</span><span class="sxs-lookup"><span data-stu-id="f4e0a-105">If your <xref:System.Data.DataSet> contains a series of related tables, you can use two <xref:System.Windows.Forms.DataGrid> controls to display the data in a master/detail format.</span></span> <span data-ttu-id="f4e0a-106">1つ <xref:System.Windows.Forms.DataGrid> はマスターグリッドとして指定され、2番目は詳細グリッドとして指定されます。</span><span class="sxs-lookup"><span data-stu-id="f4e0a-106">One <xref:System.Windows.Forms.DataGrid> is designated to be the master grid, and the second is designated to be the details grid.</span></span> <span data-ttu-id="f4e0a-107">マスターリストでエントリを選択すると、関連するすべての子エントリが詳細一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f4e0a-107">When you select an entry in the master list, all of the related child entries are shown in the details list.</span></span> <span data-ttu-id="f4e0a-108">たとえば、に <xref:System.Data.DataSet> customers テーブルと関連する orders テーブルが含まれている場合は、customers テーブルをマスターグリッドに指定し、orders テーブルを詳細グリッドとして指定します。</span><span class="sxs-lookup"><span data-stu-id="f4e0a-108">For example, if your <xref:System.Data.DataSet> contains a Customers table and a related Orders table, you would specify the Customers table to be the master grid and the Orders table to be the details grid.</span></span> <span data-ttu-id="f4e0a-109">マスターグリッドから顧客を選択すると、Orders テーブル内のその顧客に関連付けられているすべての注文が詳細グリッドに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f4e0a-109">When a customer is selected from the master grid, all of the orders associated with that customer in the Orders table would be displayed in the details grid.</span></span>  
  
### <a name="to-set-a-masterdetail-relationship-programmatically"></a><span data-ttu-id="f4e0a-110">マスター/詳細関係をプログラムによって設定するには</span><span class="sxs-lookup"><span data-stu-id="f4e0a-110">To set a master/detail relationship programmatically</span></span>  
  
1. <span data-ttu-id="f4e0a-111">2つ <xref:System.Windows.Forms.DataGrid> の新しいコントロールを作成し、そのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="f4e0a-111">Create two new <xref:System.Windows.Forms.DataGrid> controls and set their properties.</span></span>  
  
2. <span data-ttu-id="f4e0a-112">テーブルをデータセットに追加します。</span><span class="sxs-lookup"><span data-stu-id="f4e0a-112">Add tables to the dataset.</span></span>  
  
3. <span data-ttu-id="f4e0a-113">作成するリレーションを表す型の変数を宣言 <xref:System.Data.DataRelation> します。</span><span class="sxs-lookup"><span data-stu-id="f4e0a-113">Declare a variable of type <xref:System.Data.DataRelation> to represent the relation you want to create.</span></span>  
  
4. <span data-ttu-id="f4e0a-114">リレーションシップの名前を指定し、2つのテーブルを関連付けるテーブル、列、およびアイテムを指定して、リレーションシップをインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="f4e0a-114">Instantiate the relationship by specifying a name for the relationship and specifying the table, column, and item that will tie the two tables.</span></span>  
  
5. <span data-ttu-id="f4e0a-115">オブジェクトのコレクションにリレーションシップを追加し <xref:System.Data.DataSet> <xref:System.Data.DataSet.Relations%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="f4e0a-115">Add the relationship to the <xref:System.Data.DataSet> object's <xref:System.Data.DataSet.Relations%2A> collection.</span></span>  
  
6. <span data-ttu-id="f4e0a-116">のメソッドを使用して、 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> <xref:System.Windows.Forms.DataGrid> 各グリッドをにバインドし <xref:System.Data.DataSet> ます。</span><span class="sxs-lookup"><span data-stu-id="f4e0a-116">Use the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method of the <xref:System.Windows.Forms.DataGrid> to bind each of the grids to the <xref:System.Data.DataSet>.</span></span>  
  
     <span data-ttu-id="f4e0a-117">次の例では、以前に生成された () の Customers テーブルと Orders テーブルの間にマスター/詳細リレーションシップを設定する方法を示し <xref:System.Data.DataSet> `ds` ます。</span><span class="sxs-lookup"><span data-stu-id="f4e0a-117">The following example shows how to set a master/detail relationship between the Customers and Orders tables in a previously generated <xref:System.Data.DataSet> (`ds`).</span></span>  
  
    ```vb  
    Dim myDataRelation As DataRelation  
    myDataRelation = New DataRelation _  
       ("CustOrd", ds.Tables("Customers").Columns("CustomerID"), _  
       ds.Tables("Orders").Columns("CustomerID"))  
    ' Add the relation to the DataSet.  
    ds.Relations.Add(myDataRelation)  
    GridOrders.SetDataBinding(ds, "Customers")  
    GridDetails.SetDataBinding(ds, "Customers.CustOrd")  
    ```  
  
    ```csharp  
    DataRelation myDataRelation;  
    myDataRelation = new DataRelation("CustOrd", ds.Tables["Customers"].Columns["CustomerID"], ds.Tables["Orders"].Columns["CustomerID"]);  
    // Add the relation to the DataSet.  
    ds.Relations.Add(myDataRelation);  
    GridOrders.SetDataBinding(ds,"Customers");  
    GridDetails.SetDataBinding(ds,"Customers.CustOrd");  
    ```  
  
    ```cpp  
    DataRelation^ myDataRelation;  
    myDataRelation = gcnew DataRelation("CustOrd",  
       ds->Tables["Customers"]->Columns["CustomerID"],  
       ds->Tables["Orders"]->Columns["CustomerID"]);  
    // Add the relation to the DataSet.  
    ds->Relations->Add(myDataRelation);  
    GridOrders->SetDataBinding(ds, "Customers");  
    GridDetails->SetDataBinding(ds, "Customers.CustOrd");  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f4e0a-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="f4e0a-118">See also</span></span>

- [<span data-ttu-id="f4e0a-119">DataGrid コントロール</span><span class="sxs-lookup"><span data-stu-id="f4e0a-119">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
- [<span data-ttu-id="f4e0a-120">DataGrid コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="f4e0a-120">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)
- [<span data-ttu-id="f4e0a-121">方法: データ ソースに Windows フォーム DataGrid コントロールをバインドする</span><span class="sxs-lookup"><span data-stu-id="f4e0a-121">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
