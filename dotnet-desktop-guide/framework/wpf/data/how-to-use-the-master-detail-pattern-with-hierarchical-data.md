---
title: '方法: 階層データでマスター詳細パターンを使用する'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: 11429b9e-058d-4084-bfb6-2cf209c8ddf7
ms.openlocfilehash: dd3ecff2593c88505a1d301f14fe3456e8e4dc85
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982615"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-data"></a><span data-ttu-id="7b5eb-102">方法: 階層データでマスター詳細パターンを使用する</span><span class="sxs-lookup"><span data-stu-id="7b5eb-102">How to: Use the Master-Detail Pattern with Hierarchical Data</span></span>
<span data-ttu-id="7b5eb-103">この例では、マスター詳細シナリオを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7b5eb-103">This example shows how to implement the master-detail scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b5eb-104">例</span><span class="sxs-lookup"><span data-stu-id="7b5eb-104">Example</span></span>  
 <span data-ttu-id="7b5eb-105">この例では、`LeagueList` は `Leagues` のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="7b5eb-105">In this example, `LeagueList` is a collection of `Leagues`.</span></span> <span data-ttu-id="7b5eb-106">各 `League` には `Name` と `Divisions` のコレクションがあり、各 `Division` には名前と `Teams` のコレクションがあります。</span><span class="sxs-lookup"><span data-stu-id="7b5eb-106">Each `League` has a `Name` and a collection of `Divisions`, and each `Division` has a name and a collection of `Teams`.</span></span> <span data-ttu-id="7b5eb-107">各 `Team` にはチーム名が格納されています。</span><span class="sxs-lookup"><span data-stu-id="7b5eb-107">Each `Team` has a team name.</span></span>  
  
 [!code-xaml[MasterDetail#HowTo1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto1)]  
[!code-xaml[MasterDetail#HowTo2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto2)]  
  
 <span data-ttu-id="7b5eb-108">次に示すのは、この例のスクリーンショットです。</span><span class="sxs-lookup"><span data-stu-id="7b5eb-108">The following is a screenshot of the example.</span></span> <span data-ttu-id="7b5eb-109">`Divisions` の <xref:System.Windows.Controls.ListBox> によって、`Leagues` の <xref:System.Windows.Controls.ListBox> での選択が自動的に追跡され、対応するデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7b5eb-109">The `Divisions` <xref:System.Windows.Controls.ListBox> automatically tracks selections in the `Leagues` <xref:System.Windows.Controls.ListBox> and display the corresponding data.</span></span> <span data-ttu-id="7b5eb-110">`Teams` の <xref:System.Windows.Controls.ListBox> では、他の 2 つの <xref:System.Windows.Controls.ListBox> コントロールでの選択が追跡されます。</span><span class="sxs-lookup"><span data-stu-id="7b5eb-110">The `Teams` <xref:System.Windows.Controls.ListBox> tracks selections in the other two <xref:System.Windows.Controls.ListBox> controls.</span></span>  
  
 ![マスター詳細シナリオの例を示すスクリーンショット。](./media/how-to-use-the-master-detail-pattern-with-hierarchical-data/databinding-master-detail-scenario.png)  
  
 <span data-ttu-id="7b5eb-112">この例では、次の 2 つの点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="7b5eb-112">The two things to notice in this example are:</span></span>  
  
1. <span data-ttu-id="7b5eb-113">3 つの <xref:System.Windows.Controls.ListBox> コントロールは、同じソースにバインドされています。</span><span class="sxs-lookup"><span data-stu-id="7b5eb-113">The three <xref:System.Windows.Controls.ListBox> controls bind to the same source.</span></span> <span data-ttu-id="7b5eb-114">バインディングの <xref:System.Windows.Data.Binding.Path%2A> プロパティを設定して、<xref:System.Windows.Controls.ListBox> に表示するデータのレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="7b5eb-114">You set the <xref:System.Windows.Data.Binding.Path%2A> property of the binding to specify which level of data you want the <xref:System.Windows.Controls.ListBox> to display.</span></span>  
  
2. <span data-ttu-id="7b5eb-115">選択を追跡する <xref:System.Windows.Controls.ListBox> コントロールで、<xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> プロパティを `true` に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b5eb-115">You must set the <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> property to `true` on the <xref:System.Windows.Controls.ListBox> controls of which the selection you are tracking.</span></span> <span data-ttu-id="7b5eb-116">このプロパティを設定すると、選択された項目が常に <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A> として設定されます。</span><span class="sxs-lookup"><span data-stu-id="7b5eb-116">Setting this property ensures that the selected item is always set as the <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span></span> <span data-ttu-id="7b5eb-117">または、<xref:System.Windows.Controls.ListBox> で <xref:System.Windows.Data.CollectionViewSource> からデータが取得される場合は、選択と通貨が自動的に同期されます。</span><span class="sxs-lookup"><span data-stu-id="7b5eb-117">Alternatively, if the <xref:System.Windows.Controls.ListBox> gets it data from a <xref:System.Windows.Data.CollectionViewSource>, it synchronizes selection and currency automatically.</span></span>  
  
 <span data-ttu-id="7b5eb-118">XML データを使用する場合、この手法は少し異なります。</span><span class="sxs-lookup"><span data-stu-id="7b5eb-118">The technique is slightly different when you are using XML data.</span></span> <span data-ttu-id="7b5eb-119">例については、「[階層 XML データでマスター詳細パターンを使用する](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b5eb-119">For an example, see [Use the Master-Detail Pattern with Hierarchical XML Data](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b5eb-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="7b5eb-120">See also</span></span>

- <xref:System.Windows.HierarchicalDataTemplate>
- [<span data-ttu-id="7b5eb-121">コレクションにバインドして選択に基づく情報を表示する</span><span class="sxs-lookup"><span data-stu-id="7b5eb-121">Bind to a Collection and Display Information Based on Selection</span></span>](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [<span data-ttu-id="7b5eb-122">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="7b5eb-122">Data Binding Overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
- [<span data-ttu-id="7b5eb-123">データ テンプレートの概要</span><span class="sxs-lookup"><span data-stu-id="7b5eb-123">Data Templating Overview</span></span>](data-templating-overview.md)
- [<span data-ttu-id="7b5eb-124">方法トピック</span><span class="sxs-lookup"><span data-stu-id="7b5eb-124">How-to Topics</span></span>](data-binding-how-to-topics.md)
