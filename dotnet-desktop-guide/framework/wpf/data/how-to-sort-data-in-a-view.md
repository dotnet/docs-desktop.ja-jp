---
title: '方法: ビュー内のデータの並べ替え'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], sorting data in views
- data binding [WPF], grouping data in views
- grouping data in views [WPF]
- views [WPF], sorting data
- views [WPF], grouping data
- sorting data in views [WPF]
ms.assetid: f4c43578-01b7-4774-a953-acb95a13b94a
ms.openlocfilehash: 4ff90cc58cb3d7ceee0be2fd7f6ddaaa27df4cef
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984183"
---
# <a name="how-to-sort-data-in-a-view"></a><span data-ttu-id="06de4-102">方法: ビュー内のデータの並べ替え</span><span class="sxs-lookup"><span data-stu-id="06de4-102">How to: Sort Data in a View</span></span>
<span data-ttu-id="06de4-103">この例では、ビュー内のデータを並べ替える方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="06de4-103">This example describes how to sort data in a view.</span></span>  
  
## <a name="example"></a><span data-ttu-id="06de4-104">例</span><span class="sxs-lookup"><span data-stu-id="06de4-104">Example</span></span>  
 <span data-ttu-id="06de4-105">次の例では、簡単な <xref:System.Windows.Controls.ListBox> と <xref:System.Windows.Controls.Button> を作成します。</span><span class="sxs-lookup"><span data-stu-id="06de4-105">The following example creates a simple <xref:System.Windows.Controls.ListBox> and a <xref:System.Windows.Controls.Button>:</span></span>  
  
 [!code-xaml[ListBoxSort_snip#HowTo](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml#howto)]  
  
 <span data-ttu-id="06de4-106">ボタンの <xref:System.Windows.Controls.Primitives.ButtonBase.Click> イベント ハンドラーには、<xref:System.Windows.Controls.ListBox> 内の項目を降順で並べ替えるためのロジックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="06de4-106">The <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler of the button contains logic to sort the items in the <xref:System.Windows.Controls.ListBox> in the descending order.</span></span> <span data-ttu-id="06de4-107">この方法で <xref:System.Windows.Controls.ListBox> に項目を追加すると、<xref:System.Windows.Controls.ListBox> の <xref:System.Windows.Controls.ItemCollection> に項目が追加され、<xref:System.Windows.Controls.ItemCollection> は <xref:System.Windows.Data.CollectionView> クラスから派生しているため、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="06de4-107">You can do this because adding items to a <xref:System.Windows.Controls.ListBox> this way adds them to the <xref:System.Windows.Controls.ItemCollection> of the <xref:System.Windows.Controls.ListBox>, and <xref:System.Windows.Controls.ItemCollection> derives from the <xref:System.Windows.Data.CollectionView> class.</span></span> <span data-ttu-id="06de4-108"><xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> プロパティを使用して <xref:System.Windows.Controls.ListBox> をコレクションにバインドしている場合は、同じ手法を使用して並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="06de4-108">If you are binding your <xref:System.Windows.Controls.ListBox> to a collection using the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property, you can use the same technique to sort.</span></span>  
  
 [!code-csharp[ListBoxSort_snip#HowToCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml.cs#howtocode)]
 [!code-vb[ListBoxSort_snip#HowToCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxSort_snip/visualbasic/window1.xaml.vb#howtocode)]  
  
 <span data-ttu-id="06de4-109">ビュー オブジェクトへの参照がある限り、同じ手法を使用して、他のコレクション ビューの内容を並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="06de4-109">As long as you have a reference to the view object, you can use the same technique to sort the content of other collection views.</span></span> <span data-ttu-id="06de4-110">ビューを取得する方法の例については、「[データ コレクションの既定のビューを取得する](how-to-get-the-default-view-of-a-data-collection.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06de4-110">For an example of how to obtain a view, see [Get the Default View of a Data Collection](how-to-get-the-default-view-of-a-data-collection.md).</span></span> <span data-ttu-id="06de4-111">別の例については、「[ヘッダーがクリックされたときに GridView 列を並べ替える](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06de4-111">For another example, see [Sort a GridView Column When a Header Is Clicked](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md).</span></span> <span data-ttu-id="06de4-112">ビューについて詳しくは、「[データ バインディングの概要](/dotnet/desktop-wpf/data/data-binding-overview)」の「コレクションへのバインド」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="06de4-112">For more information about views, see Binding to Collections in [Data Binding Overview](/dotnet/desktop-wpf/data/data-binding-overview).</span></span>  
  
 <span data-ttu-id="06de4-113">[!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] で並べ替えロジックを適用する方法の例については、「[XAML でビューを使用してデータの並べ替えおよびグループ化を行う](how-to-sort-and-group-data-using-a-view-in-xaml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06de4-113">For an example of how to apply sorting logic in [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)], see [Sort and Group Data Using a View in XAML](how-to-sort-and-group-data-using-a-view-in-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06de4-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="06de4-114">See also</span></span>

- <xref:System.Windows.Data.ListCollectionView.CustomSort%2A>
- [<span data-ttu-id="06de4-115">ヘッダーがクリックされたときに GridView 列を並べ替える</span><span class="sxs-lookup"><span data-stu-id="06de4-115">Sort a GridView Column When a Header Is Clicked</span></span>](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)
- [<span data-ttu-id="06de4-116">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="06de4-116">Data Binding Overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
- [<span data-ttu-id="06de4-117">ビュー内のデータをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="06de4-117">Filter Data in a View</span></span>](how-to-filter-data-in-a-view.md)
- [<span data-ttu-id="06de4-118">方法トピック</span><span class="sxs-lookup"><span data-stu-id="06de4-118">How-to Topics</span></span>](data-binding-how-to-topics.md)
