---
title: '方法: ADO.NET データ ソースにバインドする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], binding to ADO.NET data sources
- ADO.NET data sources [WPF], binding to
- binding [WPF], to ADO.NET data sources
ms.assetid: a70c6d7b-7b38-4fdf-b655-4804db7c8315
ms.openlocfilehash: d7ffaae472d89ebc23804c4032a75253756dc871
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974487"
---
# <a name="how-to-bind-to-an-adonet-data-source"></a><span data-ttu-id="eaec7-102">方法: ADO.NET データ ソースにバインドする</span><span class="sxs-lookup"><span data-stu-id="eaec7-102">How to: Bind to an ADO.NET Data Source</span></span>

<span data-ttu-id="eaec7-103">この例では、[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] の <xref:System.Windows.Controls.ListBox> コントロールを ADO.NET の `DataSet` にバインドする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="eaec7-103">This example shows how to bind a [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.ListBox> control to an ADO.NET `DataSet`.</span></span>

## <a name="example"></a><span data-ttu-id="eaec7-104">例</span><span class="sxs-lookup"><span data-stu-id="eaec7-104">Example</span></span>

<span data-ttu-id="eaec7-105">この例では、データ ソース (接続文字列で指定された `OleDbConnection` ファイル) に接続するために、`Access MDB` オブジェクトを使用します。</span><span class="sxs-lookup"><span data-stu-id="eaec7-105">In this example, an `OleDbConnection` object is used to connect to the data source which is an `Access MDB` file that is specified in the connection string.</span></span> <span data-ttu-id="eaec7-106">接続が確立されると、`OleDbDataAdapter` オブジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="eaec7-106">After the connection is established, an `OleDbDataAdapter` object is created.</span></span> <span data-ttu-id="eaec7-107">`OleDbDataAdapter` オブジェクトでは、構造化照会言語 (SQL) の select ステートメントを実行して、データベースからレコードセットがを取得されます。</span><span class="sxs-lookup"><span data-stu-id="eaec7-107">The `OleDbDataAdapter` object executes a select Structured Query Language (SQL) statement to retrieve the recordset from the database.</span></span> <span data-ttu-id="eaec7-108">SQL コマンドの結果は、`OleDbDataAdapter` の `Fill` メソッドを呼び出すことによって、`DataSet` の `DataTable` に格納されます。</span><span class="sxs-lookup"><span data-stu-id="eaec7-108">The results from the SQL command are stored in a `DataTable` of the `DataSet` by calling the `Fill` method of the `OleDbDataAdapter`.</span></span> <span data-ttu-id="eaec7-109">この例の `DataTable` には、`BookTable` という名前が付いています。</span><span class="sxs-lookup"><span data-stu-id="eaec7-109">The `DataTable` in this example is named `BookTable`.</span></span> <span data-ttu-id="eaec7-110">次に、<xref:System.Windows.Controls.ListBox> の <xref:System.Windows.FrameworkElement.DataContext%2A> プロパティが `DataSet` オブジェクトに設定されます。</span><span class="sxs-lookup"><span data-stu-id="eaec7-110">The example then sets the <xref:System.Windows.FrameworkElement.DataContext%2A> property of the <xref:System.Windows.Controls.ListBox> to the `DataSet` object.</span></span>

[!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
[!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]

<span data-ttu-id="eaec7-111">その後、<xref:System.Windows.Controls.ListBox> の <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> プロパティを、`DataSet` の `BookTable` にバインドできます。</span><span class="sxs-lookup"><span data-stu-id="eaec7-111">We can then bind the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to `BookTable` of the `DataSet`:</span></span>

[!code-xaml[ADODataSet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#2)]

<span data-ttu-id="eaec7-112">`BookItemTemplate` は、データの表示方法が定義されている <xref:System.Windows.DataTemplate> です。</span><span class="sxs-lookup"><span data-stu-id="eaec7-112">`BookItemTemplate` is the <xref:System.Windows.DataTemplate> that defines how the data appears:</span></span>

[!code-xaml[ADODataSet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#3)]

<span data-ttu-id="eaec7-113">`IntColorConverter` は、`int` を 1 つの色に変換します。</span><span class="sxs-lookup"><span data-stu-id="eaec7-113">The `IntColorConverter` converts an `int` to a color.</span></span> <span data-ttu-id="eaec7-114">このコンバーターを使用すると、`NumPages` の値が 350 未満の場合は、3 番目の <xref:System.Windows.Controls.TextBlock> の <xref:System.Windows.Controls.TextBlock.Background%2A> の色が緑になり、それ以外の場合は赤になります。</span><span class="sxs-lookup"><span data-stu-id="eaec7-114">With the use of this converter, the <xref:System.Windows.Controls.TextBlock.Background%2A> color of the third <xref:System.Windows.Controls.TextBlock> appears green if the value of `NumPages` is less than 350 and red otherwise.</span></span> <span data-ttu-id="eaec7-115">コンバーターの実装は、ここでは示されていません。</span><span class="sxs-lookup"><span data-stu-id="eaec7-115">The implementation of the converter is not shown here.</span></span>

## <a name="see-also"></a><span data-ttu-id="eaec7-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="eaec7-116">See also</span></span>

- <xref:System.Windows.Data.BindingListCollectionView>
- [<span data-ttu-id="eaec7-117">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="eaec7-117">Data Binding Overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
- [<span data-ttu-id="eaec7-118">方法トピック</span><span class="sxs-lookup"><span data-stu-id="eaec7-118">How-to Topics</span></span>](data-binding-how-to-topics.md)
