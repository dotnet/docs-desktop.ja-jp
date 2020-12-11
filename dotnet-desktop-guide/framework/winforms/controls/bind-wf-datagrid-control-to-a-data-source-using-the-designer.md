---
title: デザイナーを使用したデータソースへの DataGrid コントロールのバインド
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- datasets [Windows Forms], binding to DataGrid control
- data binding [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], data binding
- Windows Forms controls, data binding
- bound controls [Windows Forms]
ms.assetid: 4e96e3d0-b1cc-4de1-8774-bc9970ec4554
ms.openlocfilehash: 67e1e99f404875b9945d934ef54dea3449ef6b26
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96975113"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source-using-the-designer"></a><span data-ttu-id="23d2a-102">方法: デザイナーを使ってデータ ソースに Windows フォーム DataGrid コントロールをバインドする</span><span class="sxs-lookup"><span data-stu-id="23d2a-102">How to: Bind the Windows Forms DataGrid Control to a Data Source Using the Designer</span></span>

> [!NOTE]
> <span data-ttu-id="23d2a-103"><xref:System.Windows.Forms.DataGridView> コントロールは、<xref:System.Windows.Forms.DataGrid> コントロールに代わると共に追加の機能を提供します。ただし、<xref:System.Windows.Forms.DataGrid> コントロールは、下位互換性を保つ目的および将来使用する目的で保持されます。</span><span class="sxs-lookup"><span data-stu-id="23d2a-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="23d2a-104">詳細については、「[Windows フォームの DataGridView コントロールと DataGrid コントロールの違いについて](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23d2a-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>

 <span data-ttu-id="23d2a-105">Windows フォーム <xref:System.Windows.Forms.DataGrid> コントロールは、特にデータソースからの情報を表示するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="23d2a-105">The Windows Forms <xref:System.Windows.Forms.DataGrid> control is specifically designed to display information from a data source.</span></span> <span data-ttu-id="23d2a-106">デザイン時にコントロールをバインドするには、 <xref:System.Windows.Forms.DataGrid.DataSource%2A> <xref:System.Windows.Forms.DataGrid.DataMember%2A> プロパティとプロパティを設定するか、メソッドを呼び出して実行時にコントロールをバインドし <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="23d2a-106">You bind the control at design time by setting the <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties, or at run time by calling the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method.</span></span> <span data-ttu-id="23d2a-107">さまざまなデータソースのデータを表示できますが、最も一般的なソースはデータセットとデータビューです。</span><span class="sxs-lookup"><span data-stu-id="23d2a-107">Although you can display data from a variety of data sources, the most typical sources are datasets and data views.</span></span>

 <span data-ttu-id="23d2a-108">データソースがデザイン時に使用可能な場合 (たとえば、フォームにデータセットまたはデータビューのインスタンスが含まれている場合)、デザイン時にグリッドをデータソースにバインドできます。</span><span class="sxs-lookup"><span data-stu-id="23d2a-108">If the data source is available at design time—for example, if the form contains an instance of a dataset or a data view—you can bind the grid to the data source at design time.</span></span> <span data-ttu-id="23d2a-109">これにより、データがグリッド内でどのように表示されるかをプレビューできます。</span><span class="sxs-lookup"><span data-stu-id="23d2a-109">You can then preview what the data will look like in the grid.</span></span>

 <span data-ttu-id="23d2a-110">また、実行時にプログラムによってグリッドをバインドすることもできます。</span><span class="sxs-lookup"><span data-stu-id="23d2a-110">You can also bind the grid programmatically, at run time.</span></span> <span data-ttu-id="23d2a-111">これは、実行時に取得した情報に基づいてデータソースを設定する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="23d2a-111">This is useful when you want to set a data source based on information you get at run time.</span></span> <span data-ttu-id="23d2a-112">たとえば、アプリケーションでは、表示するテーブルの名前をユーザーが指定できます。</span><span class="sxs-lookup"><span data-stu-id="23d2a-112">For example, the application might let the user specify the name of a table to view.</span></span> <span data-ttu-id="23d2a-113">また、デザイン時にデータソースが存在しない場合にも必要になります。</span><span class="sxs-lookup"><span data-stu-id="23d2a-113">It is also necessary in situations where the data source does not exist at design time.</span></span> <span data-ttu-id="23d2a-114">これには、配列、コレクション、型指定されていないデータセット、データリーダーなどのデータソースが含まれます。</span><span class="sxs-lookup"><span data-stu-id="23d2a-114">This includes data sources such as arrays, collections, untyped datasets, and data readers.</span></span>

 <span data-ttu-id="23d2a-115">次の手順では、コントロールを含むフォームを含む **Windows アプリケーション** プロジェクトが必要です <xref:System.Windows.Forms.DataGrid> 。</span><span class="sxs-lookup"><span data-stu-id="23d2a-115">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="23d2a-116">このようなプロジェクトの設定の詳細については、「 [方法: Windows フォームアプリケーションプロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project) する」および「 [方法: Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23d2a-116">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span> <span data-ttu-id="23d2a-117">Visual Studio 2005 では、 <xref:System.Windows.Forms.DataGrid> コントロールは既定では **ツールボックス** に含まれていません。</span><span class="sxs-lookup"><span data-stu-id="23d2a-117">In Visual Studio 2005, the <xref:System.Windows.Forms.DataGrid> control is not in the **Toolbox** by default.</span></span> <span data-ttu-id="23d2a-118">追加の詳細については、「 [方法: 項目をツールボックスに追加](/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100))する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23d2a-118">For information about adding it, see [How to: Add Items to the Toolbox](/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100)).</span></span> <span data-ttu-id="23d2a-119">さらに、Visual Studio 2005 では、デザイン時のデータバインディングに [ **データソース** ] ウィンドウを使用できます。</span><span class="sxs-lookup"><span data-stu-id="23d2a-119">Additionally in Visual Studio 2005, you can use the **Data Sources** window for design-time data binding.</span></span> <span data-ttu-id="23d2a-120">詳細については、「 [Visual Studio でのデータへのコントロールのバインド](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23d2a-120">For more information see [Bind controls to data in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).</span></span>

## <a name="to-data-bind-the-datagrid-control-to-a-single-table-in-the-designer"></a><span data-ttu-id="23d2a-121">デザイナーで DataGrid コントロールを1つのテーブルにデータバインドするには</span><span class="sxs-lookup"><span data-stu-id="23d2a-121">To data-bind the DataGrid control to a single table in the designer</span></span>

1. <span data-ttu-id="23d2a-122">コントロールのプロパティに、 <xref:System.Windows.Forms.DataGrid.DataSource%2A> バインド先のデータ項目を含むオブジェクトを設定します。</span><span class="sxs-lookup"><span data-stu-id="23d2a-122">Set the control's <xref:System.Windows.Forms.DataGrid.DataSource%2A> property to the object containing the data items you want to bind to.</span></span>

2. <span data-ttu-id="23d2a-123">データソースがデータセットである場合は、 <xref:System.Windows.Forms.DataGrid.DataMember%2A> バインド先のテーブルの名前にプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="23d2a-123">If the data source is a dataset, set the <xref:System.Windows.Forms.DataGrid.DataMember%2A> property to the name of the table to bind to.</span></span>

3. <span data-ttu-id="23d2a-124">データソースがデータセットまたはデータセットテーブルに基づくデータビューの場合は、データセットを埋めるためのコードをフォームに追加します。</span><span class="sxs-lookup"><span data-stu-id="23d2a-124">If the data source is a dataset or a data view based on a dataset table, add code to the form to fill the dataset.</span></span>

     <span data-ttu-id="23d2a-125">実際に使用するコードは、データセットがデータを取得している場所によって異なります。</span><span class="sxs-lookup"><span data-stu-id="23d2a-125">The exact code you use depends on where the dataset is getting data.</span></span> <span data-ttu-id="23d2a-126">データセットがデータベースから直接作成されている場合は、通常、 `Fill` 次のコード例に示すようにデータアダプターのメソッドを呼び出します。このコード例は、というデータセットを設定し `DsCategories1` ます。</span><span class="sxs-lookup"><span data-stu-id="23d2a-126">If the dataset is being populated directly from a database, you typically call the `Fill` method of a data adapter, as in the following code example, which populates a dataset called `DsCategories1`:</span></span>

    ```vb
    sqlDataAdapter1.Fill(DsCategories1)
    ```

    ```csharp
    sqlDataAdapter1.Fill(DsCategories1);
    ```

    ```cpp
    sqlDataAdapter1->Fill(dsCategories1);
    ```

4. <span data-ttu-id="23d2a-127">Optional適切なテーブルスタイルと列スタイルをグリッドに追加します。</span><span class="sxs-lookup"><span data-stu-id="23d2a-127">(Optional) Add the appropriate table styles and column styles to the grid.</span></span>

     <span data-ttu-id="23d2a-128">テーブルスタイルが存在しない場合は、テーブルが表示されますが、すべての列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="23d2a-128">If there are no table styles, you will see the table, but with minimal formatting and with all columns visible.</span></span>

## <a name="to-data-bind-the-datagrid-control-to-multiple-tables-in-a-dataset-in-the-designer"></a><span data-ttu-id="23d2a-129">デザイナーで DataGrid コントロールをデータセット内の複数のテーブルにデータバインドするには</span><span class="sxs-lookup"><span data-stu-id="23d2a-129">To data-bind the DataGrid control to multiple tables in a dataset in the designer</span></span>

1. <span data-ttu-id="23d2a-130">コントロールのプロパティに、 <xref:System.Windows.Forms.DataGrid.DataSource%2A> バインド先のデータ項目を含むオブジェクトを設定します。</span><span class="sxs-lookup"><span data-stu-id="23d2a-130">Set the control's <xref:System.Windows.Forms.DataGrid.DataSource%2A> property to the object containing the data items you want to bind to.</span></span>

2. <span data-ttu-id="23d2a-131">データセットに関連テーブルが含まれている場合 (つまり、リレーションシップオブジェクトが含まれている場合)、 <xref:System.Windows.Forms.DataGrid.DataMember%2A> プロパティを親テーブルの名前に設定します。</span><span class="sxs-lookup"><span data-stu-id="23d2a-131">If the dataset contains related tables (that is, if it contains a relation object), set the <xref:System.Windows.Forms.DataGrid.DataMember%2A> property to the name of the parent table.</span></span>

3. <span data-ttu-id="23d2a-132">データセットを埋めるコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="23d2a-132">Write code to fill the dataset.</span></span>

## <a name="see-also"></a><span data-ttu-id="23d2a-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="23d2a-133">See also</span></span>

- [<span data-ttu-id="23d2a-134">DataGrid コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="23d2a-134">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)
- [<span data-ttu-id="23d2a-135">方法: Windows フォーム DataGrid コントロールにテーブルと列を追加する</span><span class="sxs-lookup"><span data-stu-id="23d2a-135">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="23d2a-136">DataGrid コントロール</span><span class="sxs-lookup"><span data-stu-id="23d2a-136">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
- [<span data-ttu-id="23d2a-137">Windows フォームでのデータ バインディング</span><span class="sxs-lookup"><span data-stu-id="23d2a-137">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
- [<span data-ttu-id="23d2a-138">Visual Studio でのデータへのアクセス</span><span class="sxs-lookup"><span data-stu-id="23d2a-138">Accessing data in Visual Studio</span></span>](/visualstudio/data-tools/accessing-data-in-visual-studio)
