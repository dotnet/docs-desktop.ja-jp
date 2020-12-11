---
title: '方法: LINQ クエリの結果にバインドする'
ms.date: 03/30/2017
helpviewer_keywords:
- running a LINQ query [WPF], bind to results
- binding to LINQ query results [WPF]
ms.assetid: ff2844d9-17ed-4ea6-aab1-5111af0bc684
ms.openlocfilehash: 47f39319f2d6a6c67361157afaceb6d605ce01d1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974654"
---
# <a name="how-to-bind-to-the-results-of-a-linq-query"></a><span data-ttu-id="d8edd-102">方法: LINQ クエリの結果にバインドする</span><span class="sxs-lookup"><span data-stu-id="d8edd-102">How to: Bind to the Results of a LINQ Query</span></span>

<span data-ttu-id="d8edd-103">この例では、LINQ クエリを実行し、その結果にバインドする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d8edd-103">This example demonstrates how to run a LINQ query and then bind to the results.</span></span>

## <a name="example"></a><span data-ttu-id="d8edd-104">例</span><span class="sxs-lookup"><span data-stu-id="d8edd-104">Example</span></span>

<span data-ttu-id="d8edd-105">次の例では、2 つのリスト ボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="d8edd-105">The following example creates two list boxes.</span></span> <span data-ttu-id="d8edd-106">最初のリスト ボックスには、3 つのリスト項目が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d8edd-106">The first list box contains three list items.</span></span>

[!code-xaml[LinqExample#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml#ui)]

<span data-ttu-id="d8edd-107">最初のリスト ボックスで項目を選択すると、次のイベント ハンドラーが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d8edd-107">Selecting an item from the first list box invokes the following event handler.</span></span> <span data-ttu-id="d8edd-108">この例では、`Tasks` は `Task` オブジェクトのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="d8edd-108">In this example, `Tasks` is a collection of `Task` objects.</span></span> <span data-ttu-id="d8edd-109">`Task` クラスには、`Priority` という名前のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="d8edd-109">The `Task` class has a property named `Priority`.</span></span> <span data-ttu-id="d8edd-110">このイベント ハンドラーでは、選択した優先順位値を持つ `Task` オブジェクトのコレクションを返す LINQ クエリが実行された後、それが <xref:System.Windows.FrameworkElement.DataContext%2A> として設定されます。</span><span class="sxs-lookup"><span data-stu-id="d8edd-110">This event handler runs a LINQ query that returns the collection of `Task` objects that have the selected priority value, and then sets that as the <xref:System.Windows.FrameworkElement.DataContext%2A>:</span></span>

[!code-csharp[LinqExample#Using](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#using)]
[!code-csharp[LinqExample#Tasks](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#tasks)]
[!code-csharp[LinqExample#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#handler)]

<span data-ttu-id="d8edd-111">2 番目のリスト ボックスは、<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 値が `{Binding}` に設定されているため、そのコレクションにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="d8edd-111">The second list box binds to that collection because its <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> value is set to `{Binding}`.</span></span> <span data-ttu-id="d8edd-112">その結果、返されたコレクションが (`myTaskTemplate` <xref:System.Windows.DataTemplate> に基づいて) 表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8edd-112">As a result, it displays the returned collection (based on the `myTaskTemplate` <xref:System.Windows.DataTemplate>).</span></span>

## <a name="see-also"></a><span data-ttu-id="d8edd-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8edd-113">See also</span></span>

- [<span data-ttu-id="d8edd-114">XAML でデータをバインディング可能にする</span><span class="sxs-lookup"><span data-stu-id="d8edd-114">Make Data Available for Binding in XAML</span></span>](how-to-make-data-available-for-binding-in-xaml.md)
- [<span data-ttu-id="d8edd-115">コレクションにバインドして選択に基づく情報を表示する</span><span class="sxs-lookup"><span data-stu-id="d8edd-115">Bind to a Collection and Display Information Based on Selection</span></span>](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [<span data-ttu-id="d8edd-116">WPF Version 4.5 の新機能</span><span class="sxs-lookup"><span data-stu-id="d8edd-116">What's New in WPF Version 4.5</span></span>](../getting-started/whats-new.md)
- [<span data-ttu-id="d8edd-117">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="d8edd-117">Data Binding Overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
