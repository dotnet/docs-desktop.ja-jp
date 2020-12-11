---
title: '方法: ビュー内のデータをフィルター処理する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- views [WPF], filtering data
- filtering data in views [WPF]
- data binding [WPF], filtering data in views
ms.assetid: c76e8606-4cc4-45a8-9110-e2ec66dc6afd
ms.openlocfilehash: c015194609de507725a17fbe5d72e41d7027c68f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985811"
---
# <a name="how-to-filter-data-in-a-view"></a><span data-ttu-id="6942a-102">方法: ビュー内のデータをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="6942a-102">How to: Filter Data in a View</span></span>
<span data-ttu-id="6942a-103">この例では、ビュー内のデータをフィルター処理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6942a-103">This example shows how to filter data in a view.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6942a-104">例</span><span class="sxs-lookup"><span data-stu-id="6942a-104">Example</span></span>  
 <span data-ttu-id="6942a-105">フィルターを作成するには、フィルター処理ロジックを提供するメソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="6942a-105">To create a filter, define a method that provides the filtering logic.</span></span> <span data-ttu-id="6942a-106">メソッドは、コールバックとして使用され、`object` 型のパラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="6942a-106">The method is used as a callback and accepts a parameter of type `object`.</span></span> <span data-ttu-id="6942a-107">次のメソッドでは、`filled` プロパティが "No" に設定されているすべての `Order` オブジェクトが返され、残りのオブジェクトはフィルターで除外されます。</span><span class="sxs-lookup"><span data-stu-id="6942a-107">The following method returns all the `Order` objects with the `filled` property set to "No", filtering out the rest of the objects.</span></span>  
  
 [!code-csharp[SortFilter#2](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#2)]
 [!code-vb[SortFilter#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#2)]  
  
 <span data-ttu-id="6942a-108">次の例で示すように、フィルターを適用できます。</span><span class="sxs-lookup"><span data-stu-id="6942a-108">You can then apply the filter, as shown in the following example.</span></span> <span data-ttu-id="6942a-109">この例では、`myCollectionView` は <xref:System.Windows.Data.ListCollectionView> オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="6942a-109">In this example, `myCollectionView` is a <xref:System.Windows.Data.ListCollectionView> object.</span></span>  
  
 [!code-csharp[SortFilter#Filter](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#filter)]
 [!code-vb[SortFilter#Filter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#filter)]  
  
 <span data-ttu-id="6942a-110">フィルター処理を元に戻すには、<xref:System.Windows.Data.CollectionView.Filter%2A> プロパティを `null` に設定します。</span><span class="sxs-lookup"><span data-stu-id="6942a-110">To undo filtering, you can set the <xref:System.Windows.Data.CollectionView.Filter%2A> property to `null`:</span></span>  
  
 [!code-csharp[SortFilter#Unfilter](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#unfilter)]
 [!code-vb[SortFilter#Unfilter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#unfilter)]  
  
 <span data-ttu-id="6942a-111">ビューを作成または取得する方法については、「[データ コレクションの既定のビューを取得する](how-to-get-the-default-view-of-a-data-collection.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6942a-111">For information about how to create or obtain a view, see [Get the Default View of a Data Collection](how-to-get-the-default-view-of-a-data-collection.md).</span></span> <span data-ttu-id="6942a-112">完全な例については、「[ビュー サンプルの項目の並べ替えとフィルター処理](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/SortFilter)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6942a-112">For the complete example, see [Sorting and Filtering Items in a View Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/SortFilter).</span></span>  
  
 <span data-ttu-id="6942a-113">ビュー オブジェクトの元が <xref:System.Windows.Data.CollectionViewSource> オブジェクトの場合は、<xref:System.Windows.Data.CollectionViewSource.Filter> イベントのイベント ハンドラーを設定することによって、フィルター処理ロジックを適用します。</span><span class="sxs-lookup"><span data-stu-id="6942a-113">If your view object comes from a <xref:System.Windows.Data.CollectionViewSource> object, you apply filtering logic by setting an event handler for the <xref:System.Windows.Data.CollectionViewSource.Filter> event.</span></span> <span data-ttu-id="6942a-114">次の例では、`listingDataView` は <xref:System.Windows.Data.CollectionViewSource> のインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="6942a-114">In the following example, `listingDataView` is an instance of <xref:System.Windows.Data.CollectionViewSource>.</span></span>  
  
 [!code-csharp[DataBindingLab#10](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#10)]
 [!code-vb[DataBindingLab#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#10)]  
  
 <span data-ttu-id="6942a-115">次に示すのは、`ShowOnlyBargainsFilter` フィルター イベント ハンドラーの例の実装です。</span><span class="sxs-lookup"><span data-stu-id="6942a-115">The following shows the implementation of the example `ShowOnlyBargainsFilter` filter event handler.</span></span> <span data-ttu-id="6942a-116">このイベント ハンドラーでは、<xref:System.Windows.Data.FilterEventArgs.Accepted%2A> プロパティを使用して、`CurrentPrice` が $25 以上である `AuctionItem` オブジェクトを除外します。</span><span class="sxs-lookup"><span data-stu-id="6942a-116">This event handler uses the <xref:System.Windows.Data.FilterEventArgs.Accepted%2A> property to filter out `AuctionItem` objects that have a `CurrentPrice` of $25 or greater.</span></span>  
  
 [!code-csharp[DataBindingLab#5](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#5)]
 [!code-vb[DataBindingLab#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="6942a-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="6942a-117">See also</span></span>

- <xref:System.Windows.Data.CollectionView.CanFilter%2A>
- <xref:System.Windows.Data.BindingListCollectionView.CustomFilter%2A>
- [<span data-ttu-id="6942a-118">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="6942a-118">Data Binding Overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
- [<span data-ttu-id="6942a-119">ビュー内のデータの並べ替え</span><span class="sxs-lookup"><span data-stu-id="6942a-119">Sort Data in a View</span></span>](how-to-sort-data-in-a-view.md)
- [<span data-ttu-id="6942a-120">方法トピック</span><span class="sxs-lookup"><span data-stu-id="6942a-120">How-to Topics</span></span>](data-binding-how-to-topics.md)
