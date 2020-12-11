---
title: データソースへの DataGrid コントロールのバインド
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- datasets [Windows Forms], binding to DataGrid control
- data binding [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], data binding
- bound controls [Windows Forms], DataGrid control
- Windows Forms controls, data binding
- bound controls [Windows Forms]
- data-bound controls [Windows Forms], DataGrid
ms.assetid: 128cdb07-dfd3-4d60-9d6a-902847667c36
ms.openlocfilehash: 42514c6a0ab9cf912a32b13675a069976632ece5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982571"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source"></a><span data-ttu-id="39bf9-102">方法: データ ソースに Windows フォーム DataGrid コントロールをバインドする</span><span class="sxs-lookup"><span data-stu-id="39bf9-102">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>
> [!NOTE]
> <span data-ttu-id="39bf9-103"><xref:System.Windows.Forms.DataGridView> コントロールは、<xref:System.Windows.Forms.DataGrid> コントロールに代わると共に追加の機能を提供します。ただし、<xref:System.Windows.Forms.DataGrid> コントロールは、下位互換性を保つ目的および将来使用する目的で保持されます。</span><span class="sxs-lookup"><span data-stu-id="39bf9-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="39bf9-104">詳細については、「[Windows フォームの DataGridView コントロールと DataGrid コントロールの違いについて](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39bf9-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="39bf9-105">Windows フォーム <xref:System.Windows.Forms.DataGrid> コントロールは、特にデータソースからの情報を表示するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="39bf9-105">The Windows Forms <xref:System.Windows.Forms.DataGrid> control is specifically designed to display information from a data source.</span></span> <span data-ttu-id="39bf9-106">実行時にコントロールをバインドするには、 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="39bf9-106">You bind the control at run time by calling the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method.</span></span> <span data-ttu-id="39bf9-107">さまざまなデータソースのデータを表示できますが、最も一般的なソースはデータセットとデータビューです。</span><span class="sxs-lookup"><span data-stu-id="39bf9-107">Although you can display data from a variety of data sources, the most typical sources are datasets and data views.</span></span>  
  
### <a name="to-data-bind-the-datagrid-control-programmatically"></a><span data-ttu-id="39bf9-108">プログラムによって DataGrid コントロールをデータバインドするには</span><span class="sxs-lookup"><span data-stu-id="39bf9-108">To data-bind the DataGrid control programmatically</span></span>  
  
1. <span data-ttu-id="39bf9-109">データセットを埋めるコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="39bf9-109">Write code to fill the dataset.</span></span>  
  
     <span data-ttu-id="39bf9-110">データソースがデータセットまたはデータセットテーブルに基づくデータビューの場合は、データセットを埋めるためのコードをフォームに追加します。</span><span class="sxs-lookup"><span data-stu-id="39bf9-110">If the data source is a dataset or a data view based on a dataset table, add code to the form to fill the dataset.</span></span>  
  
     <span data-ttu-id="39bf9-111">実際に使用するコードは、データセットがデータを取得している場所によって異なります。</span><span class="sxs-lookup"><span data-stu-id="39bf9-111">The exact code you use depends on where the dataset is getting data.</span></span> <span data-ttu-id="39bf9-112">データセットがデータベースから直接作成されている場合は、通常、 `Fill` 次の例のようにデータアダプターのメソッドを呼び出します。この例では、というデータセットを設定し `DsCategories1` ます。</span><span class="sxs-lookup"><span data-stu-id="39bf9-112">If the dataset is being populated directly from a database, you typically call the `Fill` method of a data adapter, as in the following example, which populates a dataset called `DsCategories1`:</span></span>  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
     <span data-ttu-id="39bf9-113">データセットが XML Web サービスから読み込まれている場合は、通常、コード内にサービスのインスタンスを作成し、そのメソッドの1つを呼び出してデータセットを返します。</span><span class="sxs-lookup"><span data-stu-id="39bf9-113">If the dataset is being filled from an XML Web service, you typically create an instance of the service in your code and then call one of its methods to return a dataset.</span></span> <span data-ttu-id="39bf9-114">次に、データセットを XML Web サービスからローカルデータセットにマージします。</span><span class="sxs-lookup"><span data-stu-id="39bf9-114">You then merge the dataset from the XML Web service into your local dataset.</span></span> <span data-ttu-id="39bf9-115">次の例は、という名前の XML Web サービスのインスタンスを作成し `CategoriesService` 、その `GetCategories` メソッドを呼び出し、結果のデータセットをというローカルデータセットにマージする方法を示してい `DsCategories1` ます。</span><span class="sxs-lookup"><span data-stu-id="39bf9-115">The following example shows how you can create an instance of an XML Web service called `CategoriesService`, call its `GetCategories` method, and merge the resulting dataset into a local dataset called `DsCategories1`:</span></span>  
  
    ```vb  
    Dim ws As New MyProject.localhost.CategoriesService()  
    ws.Credentials = System.Net.CredentialCache.DefaultCredentials  
    DsCategories1.Merge(ws.GetCategories())  
    ```  
  
    ```csharp  
    MyProject.localhost.CategoriesService ws = new MyProject.localhost.CategoriesService();  
    ws.Credentials = System.Net.CredentialCache.DefaultCredentials;  
    DsCategories1.Merge(ws.GetCategories());  
    ```  
  
    ```cpp  
    MyProject::localhost::CategoriesService^ ws =
       new MyProject::localhost::CategoriesService();  
    ws->Credentials = System::Net::CredentialCache::DefaultCredentials;  
    dsCategories1->Merge(ws->GetCategories());  
    ```  
  
2. <span data-ttu-id="39bf9-116"><xref:System.Windows.Forms.DataGrid>コントロールの <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> メソッドを呼び出して、データソースとデータメンバーを渡します。</span><span class="sxs-lookup"><span data-stu-id="39bf9-116">Call the <xref:System.Windows.Forms.DataGrid> control's <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method, passing it the data source and a data member.</span></span> <span data-ttu-id="39bf9-117">データメンバーを明示的に渡す必要がない場合は、空の文字列を渡します。</span><span class="sxs-lookup"><span data-stu-id="39bf9-117">If you do not need to explicitly pass a data member, pass an empty string.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="39bf9-118">グリッドを初めてバインドする場合は、コントロールのプロパティとプロパティを設定でき <xref:System.Windows.Forms.DataGrid.DataSource%2A> <xref:System.Windows.Forms.DataGrid.DataMember%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="39bf9-118">If you are binding the grid for the first time, you can set the control's <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties.</span></span> <span data-ttu-id="39bf9-119">ただし、これらのプロパティがいったん設定されると、これらのプロパティをリセットすることはできません。</span><span class="sxs-lookup"><span data-stu-id="39bf9-119">However, you cannot reset these properties once they have been set.</span></span> <span data-ttu-id="39bf9-120">したがって、常にメソッドを使用することをお勧め <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> します。</span><span class="sxs-lookup"><span data-stu-id="39bf9-120">Therefore, it is recommended that you always use the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method.</span></span>  
  
     <span data-ttu-id="39bf9-121">次の例は、というデータセットの Customers テーブルにプログラムでバインドする方法を示してい `DsCustomers1` ます。</span><span class="sxs-lookup"><span data-stu-id="39bf9-121">The following example shows how you can programmatically bind to the Customers table in a dataset called `DsCustomers1`:</span></span>  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "Customers");  
    ```  
  
     <span data-ttu-id="39bf9-122">Customers テーブルがデータセット内の唯一のテーブルである場合は、次の方法でグリッドをバインドすることもできます。</span><span class="sxs-lookup"><span data-stu-id="39bf9-122">If the Customers table is the only table in the dataset, you could alternatively bind the grid this way:</span></span>  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "");  
    ```  
  
3. <span data-ttu-id="39bf9-123">Optional適切なテーブルスタイルと列スタイルをグリッドに追加します。</span><span class="sxs-lookup"><span data-stu-id="39bf9-123">(Optional) Add the appropriate table styles and column styles to the grid.</span></span> <span data-ttu-id="39bf9-124">テーブルスタイルが存在しない場合は、テーブルが表示されますが、すべての列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="39bf9-124">If there are no table styles, you will see the table, but with minimal formatting and with all columns visible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39bf9-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="39bf9-125">See also</span></span>

- [<span data-ttu-id="39bf9-126">DataGrid コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="39bf9-126">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)
- [<span data-ttu-id="39bf9-127">方法: Windows フォーム DataGrid コントロールにテーブルと列を追加する</span><span class="sxs-lookup"><span data-stu-id="39bf9-127">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="39bf9-128">DataGrid コントロール</span><span class="sxs-lookup"><span data-stu-id="39bf9-128">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
- [<span data-ttu-id="39bf9-129">Windows フォームでのデータ バインディング</span><span class="sxs-lookup"><span data-stu-id="39bf9-129">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
