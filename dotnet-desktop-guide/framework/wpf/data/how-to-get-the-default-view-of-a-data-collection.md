---
title: '方法: データ コレクションの既定のビューを取得する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], creating views of
- data binding [WPF], creating views of data collections
ms.assetid: b641e96c-c2f6-42ea-9c5d-bac81176ad65
ms.openlocfilehash: 17ec2a40bf2c274f50b39875a23541932438a317
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985803"
---
# <a name="how-to-get-the-default-view-of-a-data-collection"></a><span data-ttu-id="9879c-102">方法: データ コレクションの既定のビューを取得する</span><span class="sxs-lookup"><span data-stu-id="9879c-102">How to: Get the Default View of a Data Collection</span></span>
<span data-ttu-id="9879c-103">ビューでは、並べ替え、フィルター処理、グループ化の条件に応じて、同じデータ コレクションを異なる方法で表示できます。</span><span class="sxs-lookup"><span data-stu-id="9879c-103">Views allow the same data collection to be viewed in different ways, depending on sorting, filtering, or grouping criteria.</span></span> <span data-ttu-id="9879c-104">すべてのコレクションには既定の共有ビューが 1 つあり、バインディングでソースとしてコレクションが指定されているときに、実際のバインディング ソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="9879c-104">Every collection has one shared default view, which is used as the actual binding source when a binding specifies a collection as its source.</span></span> <span data-ttu-id="9879c-105">この例では、コレクションの既定のビューを取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9879c-105">This example shows how to get the default view of a collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9879c-106">例</span><span class="sxs-lookup"><span data-stu-id="9879c-106">Example</span></span>  
 <span data-ttu-id="9879c-107">ビューを作成するには、コレクションへのオブジェクト参照が必要です。</span><span class="sxs-lookup"><span data-stu-id="9879c-107">To create the view, you need an object reference to the collection.</span></span> <span data-ttu-id="9879c-108">このデータ オブジェクトは、独自のコードビハインド オブジェクトの参照、データ コンテキストの取得、データ ソースのプロパティの取得、またはバインディングのプロパティの取得によって、取得することができます。</span><span class="sxs-lookup"><span data-stu-id="9879c-108">This data object can be obtained by referencing your own code-behind object, by getting the data context, by getting a property of the data source, or by getting a property of the binding.</span></span> <span data-ttu-id="9879c-109">この例では、データ オブジェクトの <xref:System.Windows.FrameworkElement.DataContext%2A> を取得し、それを使用してこのコレクションの既定のコレクション ビューを直接取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9879c-109">This example shows how to get the <xref:System.Windows.FrameworkElement.DataContext%2A> of a data object and use it to directly obtain the default collection view for this collection.</span></span>  
  
 [!code-csharp[CollectionView#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#2)]
 [!code-vb[CollectionView#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#2)]  
  
 <span data-ttu-id="9879c-110">この例では、ルート要素は <xref:System.Windows.Controls.StackPanel> です。</span><span class="sxs-lookup"><span data-stu-id="9879c-110">In this example, the root element is a <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="9879c-111"><xref:System.Windows.FrameworkElement.DataContext%2A> は *myDataSource* に設定されています。これは、*Order* オブジェクトの <xref:System.Collections.ObjectModel.ObservableCollection%601> であるデータ プロバイダーを参照します。</span><span class="sxs-lookup"><span data-stu-id="9879c-111">The <xref:System.Windows.FrameworkElement.DataContext%2A> is set to *myDataSource*, which refers to a data provider that is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of *Order* objects.</span></span>  
  
 [!code-xaml[CollectionView#CollectionViewDataContext](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml#collectionviewdatacontext)]  
  
 <span data-ttu-id="9879c-112">または、<xref:System.Windows.Data.CollectionViewSource> クラスを使用して、独自のコレクション ビューをインスタンス化し、それにバインドすることもできます。</span><span class="sxs-lookup"><span data-stu-id="9879c-112">Alternatively, you can instantiate and bind to your own collection view using the <xref:System.Windows.Data.CollectionViewSource> class.</span></span> <span data-ttu-id="9879c-113">このコレクション ビューは、それに直接バインドするコントロールによってのみ共有されます。</span><span class="sxs-lookup"><span data-stu-id="9879c-113">This collection view is only shared by controls that bind to it directly.</span></span> <span data-ttu-id="9879c-114">例については、「[データ バインディングの概要](/dotnet/desktop-wpf/data/data-binding-overview)」の「ビューの作成方法」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9879c-114">For an example, see the How to Create a View section in the [Data Binding Overview](/dotnet/desktop-wpf/data/data-binding-overview).</span></span>  
  
 <span data-ttu-id="9879c-115">コレクション ビューによって提供される機能の例については、「[ビュー内のデータの並べ替え](how-to-sort-data-in-a-view.md)」、「[ビュー内のデータをフィルター処理する](how-to-filter-data-in-a-view.md)」、および「[データ CollectionView のオブジェクト間を移動する](how-to-navigate-through-the-objects-in-a-data-collectionview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9879c-115">For examples of the functionality provided by a collection view, see [Sort Data in a View](how-to-sort-data-in-a-view.md), [Filter Data in a View](how-to-filter-data-in-a-view.md), and [Navigate Through the Objects in a Data CollectionView](how-to-navigate-through-the-objects-in-a-data-collectionview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9879c-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="9879c-116">See also</span></span>

- [<span data-ttu-id="9879c-117">XAML でビューを使用してデータの並べ替えおよびグループ化を行う</span><span class="sxs-lookup"><span data-stu-id="9879c-117">Sort and Group Data Using a View in XAML</span></span>](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [<span data-ttu-id="9879c-118">方法トピック</span><span class="sxs-lookup"><span data-stu-id="9879c-118">How-to Topics</span></span>](data-binding-how-to-topics.md)
