---
title: '方法: GridView を実装する ListView の項目をグループ化する'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], grouping items with GridViews
- grouping items in ListViews implementing GridViews [WPF]
- GridView controls [WPF], grouping items
ms.assetid: eebef25b-ddc6-424e-a66d-ea228d1bf33d
ms.openlocfilehash: b3dd6891976a942b299c87fca25e430e9ee59a51
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980470"
---
# <a name="how-to-group-items-in-a-listview-that-implements-a-gridview"></a><span data-ttu-id="e1c36-102">方法: GridView を実装する ListView の項目をグループ化する</span><span class="sxs-lookup"><span data-stu-id="e1c36-102">How to: Group Items in a ListView That Implements a GridView</span></span>
<span data-ttu-id="e1c36-103">この例からは、<xref:System.Windows.Controls.ListView> コントロールの <xref:System.Windows.Controls.GridView> 表示モードで項目グループを表示する方法がわかります。</span><span class="sxs-lookup"><span data-stu-id="e1c36-103">This example shows how to display groups of items in the <xref:System.Windows.Controls.GridView> view mode of a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1c36-104">例</span><span class="sxs-lookup"><span data-stu-id="e1c36-104">Example</span></span>  
 <span data-ttu-id="e1c36-105"><xref:System.Windows.Controls.ListView> で項目グループを表示するには、<xref:System.Windows.Data.CollectionViewSource> を定義します。</span><span class="sxs-lookup"><span data-stu-id="e1c36-105">To display groups of items in a <xref:System.Windows.Controls.ListView>, define a <xref:System.Windows.Data.CollectionViewSource>.</span></span> <span data-ttu-id="e1c36-106">次の例では、`Catalog` データ フィールドの値に基づいてデータ項目をグループ化する <xref:System.Windows.Data.CollectionViewSource> を示します。</span><span class="sxs-lookup"><span data-stu-id="e1c36-106">The following example shows a <xref:System.Windows.Data.CollectionViewSource> that groups data items according to the value of the `Catalog` data field.</span></span>  
  
 [!code-xaml[GridViewWithGroups#GroupingCollectionViewSource](~/samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#groupingcollectionviewsource)]  
  
 <span data-ttu-id="e1c36-107">次の例では、前の例で定義された <xref:System.Windows.Data.CollectionViewSource> に <xref:System.Windows.Controls.ListView> の <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> が設定されます。</span><span class="sxs-lookup"><span data-stu-id="e1c36-107">The following example sets the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> for the <xref:System.Windows.Controls.ListView> to the <xref:System.Windows.Data.CollectionViewSource> that the previous example defines.</span></span> <span data-ttu-id="e1c36-108">例ではまた、<xref:System.Windows.Controls.Expander> コントロールを実装する <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> が定義されます。</span><span class="sxs-lookup"><span data-stu-id="e1c36-108">The example also defines a <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> that implements an <xref:System.Windows.Controls.Expander> control.</span></span>  
  
 [!code-xaml[GridViewWithGroups#ListViewGroups](~/samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewgroups)]  
[!code-xaml[GridViewWithGroups#ListViewEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewend)]  
  
## <a name="see-also"></a><span data-ttu-id="e1c36-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="e1c36-109">See also</span></span>

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="e1c36-110">方法トピック</span><span class="sxs-lookup"><span data-stu-id="e1c36-110">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="e1c36-111">ListView の概要</span><span class="sxs-lookup"><span data-stu-id="e1c36-111">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="e1c36-112">GridView の概要</span><span class="sxs-lookup"><span data-stu-id="e1c36-112">GridView Overview</span></span>](gridview-overview.md)
