---
title: '方法: DataGrid コントロールでデータをグループ化、並べ替え、およびフィルター処理する'
description: ビューでのデータのグループ化、並べ替え、フィルター処理をサポートする CollectionView に、Windows Presentation Foundation の DataGrid コントロールをバインドする方法について学習します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], sort
- DataGrid [WPF], group
- DataGrid [WPF], filter
ms.assetid: 03345e85-89e3-4aec-9ed0-3b80759df770
ms.openlocfilehash: 1621ab8040842d26cfa7601e66dd6337b7953413
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985079"
---
# <a name="how-to-group-sort-and-filter-data-in-the-datagrid-control"></a><span data-ttu-id="8934b-103">方法: DataGrid コントロールでデータをグループ化、並べ替え、およびフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="8934b-103">How to: Group, sort, and filter data in the DataGrid control</span></span>

<span data-ttu-id="8934b-104">データをグループ化、並べ替え、およびフィルター処理して、さまざまな方法で <xref:System.Windows.Controls.DataGrid> にデータを表示すると便利です。</span><span class="sxs-lookup"><span data-stu-id="8934b-104">It is often useful to view data in a <xref:System.Windows.Controls.DataGrid> in different ways by grouping, sorting, and filtering the data.</span></span> <span data-ttu-id="8934b-105"><xref:System.Windows.Controls.DataGrid> でデータをグループ化、並べ替え、およびフィルター処理するには、これらの関数をサポートする <xref:System.Windows.Data.CollectionView> にバインドします。</span><span class="sxs-lookup"><span data-stu-id="8934b-105">To group, sort, and filter the data in a <xref:System.Windows.Controls.DataGrid>, you bind it to a <xref:System.Windows.Data.CollectionView> that supports these functions.</span></span> <span data-ttu-id="8934b-106">そうすると、基になるソース データに影響を与えることなく、<xref:System.Windows.Data.CollectionView> 内でデータを操作できます。</span><span class="sxs-lookup"><span data-stu-id="8934b-106">You can then work with the data in the <xref:System.Windows.Data.CollectionView> without affecting the underlying source data.</span></span> <span data-ttu-id="8934b-107">コレクション ビューでの変更は、<xref:System.Windows.Controls.DataGrid> ユーザー インターフェイス (UI) に反映されます。</span><span class="sxs-lookup"><span data-stu-id="8934b-107">The changes in the collection view are reflected in the <xref:System.Windows.Controls.DataGrid> user interface (UI).</span></span>

<span data-ttu-id="8934b-108"><xref:System.Windows.Data.CollectionView> クラスは、<xref:System.Collections.IEnumerable> インターフェイスを実装するデータ ソースに対してグループ化と並べ替えの機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="8934b-108">The <xref:System.Windows.Data.CollectionView> class provides grouping and sorting functionality for a data source that implements the <xref:System.Collections.IEnumerable> interface.</span></span> <span data-ttu-id="8934b-109"><xref:System.Windows.Data.CollectionViewSource> クラスを使用すると、XAML から <xref:System.Windows.Data.CollectionView> のプロパティを設定できます。</span><span class="sxs-lookup"><span data-stu-id="8934b-109">The <xref:System.Windows.Data.CollectionViewSource> class enables you to set the properties of a <xref:System.Windows.Data.CollectionView> from XAML.</span></span>

<span data-ttu-id="8934b-110">この例では、`Task` オブジェクトのコレクションが <xref:System.Windows.Data.CollectionViewSource> にバインドされます。</span><span class="sxs-lookup"><span data-stu-id="8934b-110">In this example, a collection of `Task` objects is bound to a <xref:System.Windows.Data.CollectionViewSource>.</span></span> <span data-ttu-id="8934b-111"><xref:System.Windows.Data.CollectionViewSource> は、<xref:System.Windows.Controls.DataGrid> の <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> として使用されます。</span><span class="sxs-lookup"><span data-stu-id="8934b-111">The <xref:System.Windows.Data.CollectionViewSource> is used as the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> for the <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="8934b-112">グループ化、並べ替え、およびフィルター処理は <xref:System.Windows.Data.CollectionViewSource> に対して実行され、<xref:System.Windows.Controls.DataGrid> UI に表示されます。</span><span class="sxs-lookup"><span data-stu-id="8934b-112">Grouping, sorting, and filtering are performed on the <xref:System.Windows.Data.CollectionViewSource> and are displayed in the <xref:System.Windows.Controls.DataGrid> UI.</span></span>

<span data-ttu-id="8934b-113">![DataGrid 内のグループ化されたデータ](././media/wpf-datagridgroups.png "WPF_DataGridGroups") DataGrid 内のグループ化されたデータ</span><span class="sxs-lookup"><span data-stu-id="8934b-113">![Grouped data in a DataGrid](././media/wpf-datagridgroups.png "WPF_DataGridGroups") Grouped data in a DataGrid</span></span>

## <a name="using-a-collectionviewsource-as-an-itemssource"></a><span data-ttu-id="8934b-114">ItemsSource としての CollectionViewSource の使用</span><span class="sxs-lookup"><span data-stu-id="8934b-114">Using a CollectionViewSource as an ItemsSource</span></span>

<span data-ttu-id="8934b-115"><xref:System.Windows.Controls.DataGrid> コントロールでデータをグループ化、並べ替え、およびフィルター処理するには、これらの関数をサポートする <xref:System.Windows.Data.CollectionView> に <xref:System.Windows.Controls.DataGrid> をバインドします。</span><span class="sxs-lookup"><span data-stu-id="8934b-115">To group, sort, and filter data in a <xref:System.Windows.Controls.DataGrid> control, you bind the <xref:System.Windows.Controls.DataGrid> to a <xref:System.Windows.Data.CollectionView> that supports these functions.</span></span> <span data-ttu-id="8934b-116">この例で、<xref:System.Windows.Controls.DataGrid> は、`Task` オブジェクトの <xref:System.Collections.Generic.List%601> のためにこれらの関数を提供する <xref:System.Windows.Data.CollectionViewSource> にバインドされます。</span><span class="sxs-lookup"><span data-stu-id="8934b-116">In this example, the <xref:System.Windows.Controls.DataGrid> is bound to a <xref:System.Windows.Data.CollectionViewSource> that provides these functions for a <xref:System.Collections.Generic.List%601> of `Task` objects.</span></span>

### <a name="to-bind-a-datagrid-to-a-collectionviewsource"></a><span data-ttu-id="8934b-117">DataGrid を CollectionViewSource にバインドするには</span><span class="sxs-lookup"><span data-stu-id="8934b-117">To bind a DataGrid to a CollectionViewSource</span></span>

1. <span data-ttu-id="8934b-118"><xref:System.Collections.IEnumerable> インターフェイスを実装するデータ コレクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="8934b-118">Create a data collection that implements the <xref:System.Collections.IEnumerable> interface.</span></span>

    <span data-ttu-id="8934b-119"><xref:System.Collections.Generic.List%601> を使用してコレクションを作成する場合、<xref:System.Collections.Generic.List%601> のインスタンスをインスタンス化するのではなく、<xref:System.Collections.Generic.List%601> を継承する新しいクラスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8934b-119">If you use <xref:System.Collections.Generic.List%601> to create your collection, you should create a new class that inherits from <xref:System.Collections.Generic.List%601> instead of instantiating an instance of <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="8934b-120">これによって、XAML でコレクションにデータをバインドできるようになります。</span><span class="sxs-lookup"><span data-stu-id="8934b-120">This enables you to data bind to the collection in XAML.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8934b-121">コレクション内のオブジェクトは、<xref:System.ComponentModel.INotifyPropertyChanged> 変更済みインターフェイスと <xref:System.ComponentModel.IEditableObject> インターフェイスを実装する必要があります。これは <xref:System.Windows.Controls.DataGrid> がプロパティの変更や編集に正しく応答できるようにするためです。</span><span class="sxs-lookup"><span data-stu-id="8934b-121">The objects in the collection must implement the <xref:System.ComponentModel.INotifyPropertyChanged> changed interface and the <xref:System.ComponentModel.IEditableObject> interface in order for the <xref:System.Windows.Controls.DataGrid> to respond correctly to property changes and edits.</span></span> <span data-ttu-id="8934b-122">詳細については、「[プロパティの変更通知を実装する](../data/how-to-implement-property-change-notification.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8934b-122">For more information, see [Implement Property Change Notification](../data/how-to-implement-property-change-notification.md).</span></span>

    [!code-csharp[DataGrid_GroupSortFilter#101](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#101)]
    [!code-vb[DataGrid_GroupSortFilter#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#101)]

2. <span data-ttu-id="8934b-123">XAML で、コレクション クラスのインスタンスを作成し、[x:Key ディレクティブ](/dotnet/desktop-wpf/xaml-services/xkey-directive)を設定します。</span><span class="sxs-lookup"><span data-stu-id="8934b-123">In XAML, create an instance of the collection class and set the [x:Key Directive](/dotnet/desktop-wpf/xaml-services/xkey-directive).</span></span>

3. <span data-ttu-id="8934b-124">XAML で <xref:System.Windows.Data.CollectionViewSource> クラスのインスタンスを作成し、[x:Key ディレクティブ](/dotnet/desktop-wpf/xaml-services/xkey-directive)を設定して、コレクション クラスのインスタンスを <xref:System.Windows.Data.CollectionViewSource.Source%2A> として設定します。</span><span class="sxs-lookup"><span data-stu-id="8934b-124">In XAML, create an instance of the <xref:System.Windows.Data.CollectionViewSource> class, set the [x:Key Directive](/dotnet/desktop-wpf/xaml-services/xkey-directive), and set the instance of your collection class as the <xref:System.Windows.Data.CollectionViewSource.Source%2A>.</span></span>

    [!code-xaml[DataGrid_GroupSortFilter#201](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml#201)]

4. <span data-ttu-id="8934b-125"><xref:System.Windows.Controls.DataGrid> クラスのインスタンスを作成し、<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> プロパティを <xref:System.Windows.Data.CollectionViewSource> に設定します。</span><span class="sxs-lookup"><span data-stu-id="8934b-125">Create an instance of the <xref:System.Windows.Controls.DataGrid> class, and set the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property to the <xref:System.Windows.Data.CollectionViewSource>.</span></span>

    [!code-xaml[DataGrid_GroupSortFilter#002](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#002)]

5. <span data-ttu-id="8934b-126">コードから <xref:System.Windows.Data.CollectionViewSource> にアクセスするには、<xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> メソッドを使用して <xref:System.Windows.Data.CollectionViewSource> への参照を取得します。</span><span class="sxs-lookup"><span data-stu-id="8934b-126">To access the <xref:System.Windows.Data.CollectionViewSource> from your code, use the <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> method to get a reference to the <xref:System.Windows.Data.CollectionViewSource>.</span></span>

    [!code-csharp[DataGrid_GroupSortFilter#102](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#102)]
    [!code-vb[DataGrid_GroupSortFilter#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#102)]

## <a name="grouping-items-in-a-datagrid"></a><span data-ttu-id="8934b-127">DataGrid での項目のグループ化</span><span class="sxs-lookup"><span data-stu-id="8934b-127">Grouping items in a DataGrid</span></span>

<span data-ttu-id="8934b-128"><xref:System.Windows.Controls.DataGrid> で項目をグループ化する方法を指定するには、<xref:System.Windows.Data.PropertyGroupDescription> の型を使用して、ソース ビュー内の項目をグループ化します。</span><span class="sxs-lookup"><span data-stu-id="8934b-128">To specify how items are grouped in a <xref:System.Windows.Controls.DataGrid>, you use the <xref:System.Windows.Data.PropertyGroupDescription> type to group the items in the source view.</span></span>

### <a name="to-group-items-in-a-datagrid-using-xaml"></a><span data-ttu-id="8934b-129">XAML を使用して DataGrid の項目をグループ化するには</span><span class="sxs-lookup"><span data-stu-id="8934b-129">To group items in a DataGrid using XAML</span></span>

1. <span data-ttu-id="8934b-130">グループ化の基準となるプロパティを指定する <xref:System.Windows.Data.PropertyGroupDescription> を作成します。</span><span class="sxs-lookup"><span data-stu-id="8934b-130">Create a <xref:System.Windows.Data.PropertyGroupDescription> that specifies the property to group by.</span></span> <span data-ttu-id="8934b-131">プロパティは、XAML またはコードで指定できます。</span><span class="sxs-lookup"><span data-stu-id="8934b-131">You can specify the property in XAML or in code.</span></span>

   1. <span data-ttu-id="8934b-132">XAML では、<xref:System.Windows.Data.PropertyGroupDescription.PropertyName%2A> に、グループ化の基準とするプロパティの名前を設定します。</span><span class="sxs-lookup"><span data-stu-id="8934b-132">In XAML, set the <xref:System.Windows.Data.PropertyGroupDescription.PropertyName%2A> to the name of the property to group by.</span></span>

   2. <span data-ttu-id="8934b-133">コードでは、グループ化の基準とするプロパティの名前をコンストラクターに渡します。</span><span class="sxs-lookup"><span data-stu-id="8934b-133">In code, pass the name of the property to group by to the constructor.</span></span>

2. <span data-ttu-id="8934b-134"><xref:System.Windows.Data.PropertyGroupDescription> を <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A?displayProperty=nameWithType> コレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="8934b-134">Add the <xref:System.Windows.Data.PropertyGroupDescription> to the <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A?displayProperty=nameWithType> collection.</span></span>

3. <span data-ttu-id="8934b-135"><xref:System.Windows.Data.PropertyGroupDescription> のインスタンスをさらに <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> コレクションに追加し、グループ化のレベルを追加します。</span><span class="sxs-lookup"><span data-stu-id="8934b-135">Add additional instances of <xref:System.Windows.Data.PropertyGroupDescription> to the <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> collection to add more levels of grouping.</span></span>

    [!code-xaml[DataGrid_GroupSortFilter#012](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#012)]
    [!code-csharp[DataGrid_GroupSortFilter#112](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#112)]
    [!code-vb[DataGrid_GroupSortFilter#112](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#112)]

4. <span data-ttu-id="8934b-136">グループを削除するには、<xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> コレクションから <xref:System.Windows.Data.PropertyGroupDescription> を削除します。</span><span class="sxs-lookup"><span data-stu-id="8934b-136">To remove a group, remove the <xref:System.Windows.Data.PropertyGroupDescription> from the <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> collection.</span></span>

5. <span data-ttu-id="8934b-137">すべてのグループを削除するには、<xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> コレクションの <xref:System.Collections.ObjectModel.Collection%601.Clear%2A> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8934b-137">To remove all groups, call the <xref:System.Collections.ObjectModel.Collection%601.Clear%2A> method of the <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> collection.</span></span>

    [!code-csharp[DataGrid_GroupSortFilter#114](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#114)]
    [!code-vb[DataGrid_GroupSortFilter#114](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#114)]

<span data-ttu-id="8934b-138">項目が <xref:System.Windows.Controls.DataGrid> でグループ化されている場合は、各グループの外観を指定する <xref:System.Windows.Controls.GroupStyle> を定義できます。</span><span class="sxs-lookup"><span data-stu-id="8934b-138">When items are grouped in the <xref:System.Windows.Controls.DataGrid>, you can define a <xref:System.Windows.Controls.GroupStyle> that specifies the appearance of each group.</span></span> <span data-ttu-id="8934b-139"><xref:System.Windows.Controls.GroupStyle> を適用するには、DataGrid の <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> コレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="8934b-139">You apply the <xref:System.Windows.Controls.GroupStyle> by adding it to the <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> collection of the DataGrid.</span></span> <span data-ttu-id="8934b-140">複数のレベルのグループ化がある場合は、グループ レベルごとに異なるスタイルを適用できます。</span><span class="sxs-lookup"><span data-stu-id="8934b-140">If you have multiple levels of grouping, you can apply different styles to each group level.</span></span> <span data-ttu-id="8934b-141">スタイルは定義された順序で適用されます。</span><span class="sxs-lookup"><span data-stu-id="8934b-141">Styles are applied in the order in which they are defined.</span></span> <span data-ttu-id="8934b-142">たとえば、2 つのスタイルを定義した場合、最初のスタイルが一番上のレベルの行グループに適用されます。</span><span class="sxs-lookup"><span data-stu-id="8934b-142">For example, if you define two styles, the first will be applied to top level row groups.</span></span> <span data-ttu-id="8934b-143">2 番目のスタイルは、2 番目のレベル以下のすべての行グループに適用されます。</span><span class="sxs-lookup"><span data-stu-id="8934b-143">The second style will be applied to all row groups at the second level and lower.</span></span> <span data-ttu-id="8934b-144"><xref:System.Windows.Controls.GroupStyle>の <xref:System.Windows.FrameworkElement.DataContext%2A> は、グループが表す <xref:System.Windows.Data.CollectionViewGroup> です。</span><span class="sxs-lookup"><span data-stu-id="8934b-144">The <xref:System.Windows.FrameworkElement.DataContext%2A> of the <xref:System.Windows.Controls.GroupStyle> is the <xref:System.Windows.Data.CollectionViewGroup> that the group represents.</span></span>

### <a name="to-change-the-appearance-of-row-group-headers"></a><span data-ttu-id="8934b-145">行グループ見出しの外観を変更するには</span><span class="sxs-lookup"><span data-stu-id="8934b-145">To change the appearance of row group headers</span></span>

1. <span data-ttu-id="8934b-146">行グループの外観を定義する <xref:System.Windows.Controls.GroupStyle> を作成します。</span><span class="sxs-lookup"><span data-stu-id="8934b-146">Create a <xref:System.Windows.Controls.GroupStyle> that defines the appearance of the row group.</span></span>

2. <span data-ttu-id="8934b-147">`<DataGrid.GroupStyle>` タグ内に <xref:System.Windows.Controls.GroupStyle> を指定します。</span><span class="sxs-lookup"><span data-stu-id="8934b-147">Put the <xref:System.Windows.Controls.GroupStyle> inside the `<DataGrid.GroupStyle>` tags.</span></span>

    [!code-xaml[DataGrid_GroupSortFilter#003](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#003)]

## <a name="sorting-items-in-a-datagrid"></a><span data-ttu-id="8934b-148">DataGrid での項目の並べ替え</span><span class="sxs-lookup"><span data-stu-id="8934b-148">Sorting items in a DataGrid</span></span>

<span data-ttu-id="8934b-149"><xref:System.Windows.Controls.DataGrid> での項目の並べ替え方法を指定するには、<xref:System.ComponentModel.SortDescription> の型を使用して、ソース ビュー内の項目を並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="8934b-149">To specify how items are sorted in a <xref:System.Windows.Controls.DataGrid>, you use the <xref:System.ComponentModel.SortDescription> type to sort the items in the source view.</span></span>

### <a name="to-sort-items-in-a-datagrid"></a><span data-ttu-id="8934b-150">DataGrid の項目を並べ替えるには</span><span class="sxs-lookup"><span data-stu-id="8934b-150">To sort items in a DataGrid</span></span>

1. <span data-ttu-id="8934b-151">並べ替えの基準となるプロパティを指定する <xref:System.ComponentModel.SortDescription> を作成します。</span><span class="sxs-lookup"><span data-stu-id="8934b-151">Create a <xref:System.ComponentModel.SortDescription> that specifies the property to sort by.</span></span> <span data-ttu-id="8934b-152">プロパティは、XAML またはコードで指定できます。</span><span class="sxs-lookup"><span data-stu-id="8934b-152">You can specify the property in XAML or in code.</span></span>

    1. <span data-ttu-id="8934b-153">XAML では、<xref:System.ComponentModel.SortDescription.PropertyName%2A> に、並べ替えの基準とするプロパティの名前を設定します。</span><span class="sxs-lookup"><span data-stu-id="8934b-153">In XAML, set the <xref:System.ComponentModel.SortDescription.PropertyName%2A> to the name of the property to sort by.</span></span>

    2. <span data-ttu-id="8934b-154">コードでは、並べ替えの基準とするプロパティの名前と <xref:System.ComponentModel.ListSortDirection>をコンストラクターに渡します。</span><span class="sxs-lookup"><span data-stu-id="8934b-154">In code, pass the name of the property to sort by and the <xref:System.ComponentModel.ListSortDirection> to the constructor.</span></span>

2. <span data-ttu-id="8934b-155"><xref:System.ComponentModel.SortDescription> を <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A?displayProperty=nameWithType> コレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="8934b-155">Add the <xref:System.ComponentModel.SortDescription> to the <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A?displayProperty=nameWithType> collection.</span></span>

3. <span data-ttu-id="8934b-156"><xref:System.ComponentModel.SortDescription> のインスタンスをさらに <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A> コレクションに追加し、別のプロパティで並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="8934b-156">Add additional instances of <xref:System.ComponentModel.SortDescription> to the <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A> collection to sort by additional properties.</span></span>

    [!code-xaml[DataGrid_GroupSortFilter#011](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#011)]
    [!code-csharp[DataGrid_GroupSortFilter#211](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml.cs#211)]
    [!code-vb[DataGrid_GroupSortFilter#211](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#211)]

## <a name="filtering-items-in-a-datagrid"></a><span data-ttu-id="8934b-157">DataGrid での項目のフィルター処理</span><span class="sxs-lookup"><span data-stu-id="8934b-157">Filtering items in a DataGrid</span></span>

<span data-ttu-id="8934b-158"><xref:System.Windows.Data.CollectionViewSource>を使用して <xref:System.Windows.Controls.DataGrid> の項目をフィルター処理するには、<xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> イベントのハンドラーにフィルター処理のロジックを指定します。</span><span class="sxs-lookup"><span data-stu-id="8934b-158">To filter items in a <xref:System.Windows.Controls.DataGrid> using a <xref:System.Windows.Data.CollectionViewSource>, you provide the filtering logic in the handler for the <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> event.</span></span>

### <a name="to-filter-items-in-a-datagrid"></a><span data-ttu-id="8934b-159">DataGrid の項目をフィルター処理するには</span><span class="sxs-lookup"><span data-stu-id="8934b-159">To filter items in a DataGrid</span></span>

1. <span data-ttu-id="8934b-160"><xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> イベントのハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="8934b-160">Add a handler for the <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> event.</span></span>

2. <span data-ttu-id="8934b-161"><xref:System.Windows.Data.CollectionViewSource.Filter> イベント ハンドラーで、フィルター処理ロジックを定義します。</span><span class="sxs-lookup"><span data-stu-id="8934b-161">In the <xref:System.Windows.Data.CollectionViewSource.Filter> event handler, define the filtering logic.</span></span>

    <span data-ttu-id="8934b-162">ビューが更新されるたびにフィルターが適用されます。</span><span class="sxs-lookup"><span data-stu-id="8934b-162">The filter will be applied every time the view is refreshed.</span></span>

    [!code-xaml[DataGrid_GroupSortFilter#013](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#013)]
    [!code-csharp[DataGrid_GroupSortFilter#113](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#113)]
    [!code-vb[DataGrid_GroupSortFilter#113](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#113)]

<span data-ttu-id="8934b-163">または、フィルター処理ロジックを提供するメソッドを作成し、フィルターを適用するように <xref:System.Windows.Data.CollectionView.Filter%2A?displayProperty=nameWithType> プロパティを設定することによって、<xref:System.Windows.Controls.DataGrid> の項目をフィルター処理することができます。</span><span class="sxs-lookup"><span data-stu-id="8934b-163">Alternatively, you can filter items in a <xref:System.Windows.Controls.DataGrid> by creating a method that provides the filtering logic and setting the <xref:System.Windows.Data.CollectionView.Filter%2A?displayProperty=nameWithType> property to apply the filter.</span></span> <span data-ttu-id="8934b-164">このメソッドの例については、[ビュー内のデータをフィルター処理する方法](../data/how-to-filter-data-in-a-view.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8934b-164">To see an example of this method, see [Filter Data in a View](../data/how-to-filter-data-in-a-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="8934b-165">例</span><span class="sxs-lookup"><span data-stu-id="8934b-165">Example</span></span>

<span data-ttu-id="8934b-166">次の例では、<xref:System.Windows.Data.CollectionViewSource> の `Task` データのグループ化、並べ替え、およびフィルター処理を行い、グループ化、並べ替え、およびフィルター処理が行われた `Task` データを <xref:System.Windows.Controls.DataGrid> に表示します。</span><span class="sxs-lookup"><span data-stu-id="8934b-166">The following example demonstrates grouping, sorting, and filtering `Task` data in a <xref:System.Windows.Data.CollectionViewSource> and displaying the grouped, sorted, and filtered `Task` data in a <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="8934b-167"><xref:System.Windows.Data.CollectionViewSource> は、<xref:System.Windows.Controls.DataGrid> の <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> として使用されます。</span><span class="sxs-lookup"><span data-stu-id="8934b-167">The <xref:System.Windows.Data.CollectionViewSource> is used as the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> for the <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="8934b-168">グループ化、並べ替え、およびフィルター処理は <xref:System.Windows.Data.CollectionViewSource> に対して実行され、<xref:System.Windows.Controls.DataGrid> UI に表示されます。</span><span class="sxs-lookup"><span data-stu-id="8934b-168">Grouping, sorting, and filtering are performed on the <xref:System.Windows.Data.CollectionViewSource> and are displayed in the <xref:System.Windows.Controls.DataGrid> UI.</span></span>

<span data-ttu-id="8934b-169">この例をテストするには、プロジェクト名と一致するように DGGroupSortFilterExample 名を調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8934b-169">To test this example, you will need to adjust the DGGroupSortFilterExample name to match your project name.</span></span> <span data-ttu-id="8934b-170">Visual Basic を使用している場合は、<xref:System.Windows.Window> のクラス名を次のように変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8934b-170">If you are using Visual Basic, you will need to change the class name for <xref:System.Windows.Window> to the following.</span></span>

`<Window x:Class="MainWindow"`

[!code-xaml[DataGrid_GroupSortFilter#000](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#000)]
[!code-csharp[DataGrid_GroupSortFilter#100](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#100)]
[!code-vb[DataGrid_GroupSortFilter#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#100)]

## <a name="see-also"></a><span data-ttu-id="8934b-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="8934b-171">See also</span></span>

- [<span data-ttu-id="8934b-172">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="8934b-172">Data Binding Overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
- [<span data-ttu-id="8934b-173">ObservableCollection を作成およびバインドする</span><span class="sxs-lookup"><span data-stu-id="8934b-173">Create and Bind to an ObservableCollection</span></span>](../data/how-to-create-and-bind-to-an-observablecollection.md)
- [<span data-ttu-id="8934b-174">ビュー内のデータをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="8934b-174">Filter Data in a View</span></span>](../data/how-to-filter-data-in-a-view.md)
- [<span data-ttu-id="8934b-175">ビュー内のデータの並べ替え</span><span class="sxs-lookup"><span data-stu-id="8934b-175">Sort Data in a View</span></span>](../data/how-to-sort-data-in-a-view.md)
- [<span data-ttu-id="8934b-176">XAML でビューを使用してデータの並べ替えおよびグループ化を行う</span><span class="sxs-lookup"><span data-stu-id="8934b-176">Sort and Group Data Using a View in XAML</span></span>](../data/how-to-sort-and-group-data-using-a-view-in-xaml.md)
