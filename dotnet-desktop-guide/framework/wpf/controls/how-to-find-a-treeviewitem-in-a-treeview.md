---
title: '方法: TreeView での TreeViewItem の検索'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TreeView control [WPF], finding a TreeViewItem
- TreeViewItem [WPF], finding
ms.assetid: 72ecd40c-3939-4e01-b617-5e9daa6074d9
ms.openlocfilehash: ad72c7a7fb11dfe605db4119dde831b47dd7c5a4
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980500"
---
# <a name="how-to-find-a-treeviewitem-in-a-treeview"></a><span data-ttu-id="e6aed-102">方法: TreeView での TreeViewItem の検索</span><span class="sxs-lookup"><span data-stu-id="e6aed-102">How to: Find a TreeViewItem in a TreeView</span></span>
<span data-ttu-id="e6aed-103"><xref:System.Windows.Controls.TreeView> コントロールは、階層データを表示するための便利な方法です。</span><span class="sxs-lookup"><span data-stu-id="e6aed-103">The <xref:System.Windows.Controls.TreeView> control provides a convenient way to display hierarchical data.</span></span> <span data-ttu-id="e6aed-104"><xref:System.Windows.Controls.TreeView> がデータ ソースにバインドされている場合、<xref:System.Windows.Controls.TreeView.SelectedItem%2A> プロパティを使用すると、選択したデータ オブジェクトをすばやく簡単に取得できます。</span><span class="sxs-lookup"><span data-stu-id="e6aed-104">If your <xref:System.Windows.Controls.TreeView> is bound to a data source, the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> property provides a convenient way for you to quickly retrieve the selected data object.</span></span> <span data-ttu-id="e6aed-105">通常は、基になるデータ オブジェクトを操作することをお勧めしますが、<xref:System.Windows.Controls.TreeViewItem> を含むデータをプログラムで操作することが必要になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="e6aed-105">It is typically best to work with the underlying data object, but sometimes you may need to programmatically manipulate the data's containing <xref:System.Windows.Controls.TreeViewItem>.</span></span> <span data-ttu-id="e6aed-106">たとえば、プログラムを使用して <xref:System.Windows.Controls.TreeViewItem> を展開したり、<xref:System.Windows.Controls.TreeView> で別の項目を選択したりすることが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e6aed-106">For example, you may need to programmatically expand the <xref:System.Windows.Controls.TreeViewItem>, or select a different item in the <xref:System.Windows.Controls.TreeView>.</span></span>  
  
 <span data-ttu-id="e6aed-107">特定のデータ オブジェクトを含む <xref:System.Windows.Controls.TreeViewItem> を検索するには、<xref:System.Windows.Controls.TreeView> の各レベルを走査する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6aed-107">To find a <xref:System.Windows.Controls.TreeViewItem> that contains a specific data object, you must traverse each level of the <xref:System.Windows.Controls.TreeView>.</span></span> <span data-ttu-id="e6aed-108"><xref:System.Windows.Controls.TreeView> 内の項目は、パフォーマンスを向上させるために仮想化することもできます。</span><span class="sxs-lookup"><span data-stu-id="e6aed-108">The items in a <xref:System.Windows.Controls.TreeView> can also be virtualized to improve performance.</span></span> <span data-ttu-id="e6aed-109">項目が仮想化される可能性がある場合は、データ オブジェクトが含まれているかどうかを確認するために <xref:System.Windows.Controls.TreeViewItem> も認識する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6aed-109">In the case where items might be virtualized, you also must realize a <xref:System.Windows.Controls.TreeViewItem> to check whether it contains the data object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6aed-110">例</span><span class="sxs-lookup"><span data-stu-id="e6aed-110">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="e6aed-111">説明</span><span class="sxs-lookup"><span data-stu-id="e6aed-111">Description</span></span>  
 <span data-ttu-id="e6aed-112">次の例では、特定のオブジェクトの <xref:System.Windows.Controls.TreeView> が検索され、<xref:System.Windows.Controls.TreeViewItem> が含まれるオブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="e6aed-112">The following example searches a <xref:System.Windows.Controls.TreeView> for a specific object and returns the object's containing <xref:System.Windows.Controls.TreeViewItem>.</span></span> <span data-ttu-id="e6aed-113">この例では、各 <xref:System.Windows.Controls.TreeViewItem> がインスタンス化され、その子項目を検索できるようになっています。</span><span class="sxs-lookup"><span data-stu-id="e6aed-113">The example ensures that each <xref:System.Windows.Controls.TreeViewItem> is instantiated so that its child items can be searched.</span></span> <span data-ttu-id="e6aed-114">この例は、<xref:System.Windows.Controls.TreeView> で仮想化された項目が使用されていない場合にも機能します。</span><span class="sxs-lookup"><span data-stu-id="e6aed-114">This example also works if the <xref:System.Windows.Controls.TreeView> does not use virtualized items.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e6aed-115">次の例は、基になるデータ モデルに関係なく、すべての <xref:System.Windows.Controls.TreeView> に対して機能し、オブジェクトが見つかるまですべての <xref:System.Windows.Controls.TreeViewItem> が検索されます。</span><span class="sxs-lookup"><span data-stu-id="e6aed-115">The following example works for any <xref:System.Windows.Controls.TreeView>, regardless of the underlying data model, and searches every <xref:System.Windows.Controls.TreeViewItem> until the object is found.</span></span> <span data-ttu-id="e6aed-116">パフォーマンスがより優れたもう 1 つの方法は、指定されたオブジェクトのデータ モデルを検索し、データ階層内での位置を追跡して、<xref:System.Windows.Controls.TreeView> 内の対応する <xref:System.Windows.Controls.TreeViewItem> を見つけることです。</span><span class="sxs-lookup"><span data-stu-id="e6aed-116">Another technique that has better performance is to search the data model for the specified object, keep track of its location within the data hierarchy, and then find the corresponding <xref:System.Windows.Controls.TreeViewItem> in the <xref:System.Windows.Controls.TreeView>.</span></span> <span data-ttu-id="e6aed-117">ただし、このパフォーマンスがより優れた方法では、データ モデルに関する知識が必要であり、あらゆる <xref:System.Windows.Controls.TreeView> に対して一般化することはできません。</span><span class="sxs-lookup"><span data-stu-id="e6aed-117">However, the technique that has better performance requires knowledge of the data model and cannot be generalized for any given <xref:System.Windows.Controls.TreeView>.</span></span>  
  
## <a name="code"></a><span data-ttu-id="e6aed-118">コード</span><span class="sxs-lookup"><span data-stu-id="e6aed-118">Code</span></span>  
 [!code-csharp[TreeViewFindTVI#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[TreeViewFindTVI#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#1)]  
  
 <span data-ttu-id="e6aed-119">上記のコードは、`BringIntoView` という名前のメソッドを公開するカスタム <xref:System.Windows.Controls.VirtualizingStackPanel> に依存しています。</span><span class="sxs-lookup"><span data-stu-id="e6aed-119">The previous code relies on a custom <xref:System.Windows.Controls.VirtualizingStackPanel> that exposes a method named `BringIntoView`.</span></span> <span data-ttu-id="e6aed-120">次のコードでは、カスタム <xref:System.Windows.Controls.VirtualizingStackPanel> が定義されます。</span><span class="sxs-lookup"><span data-stu-id="e6aed-120">The following code defines the custom <xref:System.Windows.Controls.VirtualizingStackPanel>.</span></span>  
  
 [!code-csharp[TreeViewFindTVI#2](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#2)]
 [!code-vb[TreeViewFindTVI#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#2)]  
  
 <span data-ttu-id="e6aed-121">次の XAML は、カスタム <xref:System.Windows.Controls.VirtualizingStackPanel> を使用する <xref:System.Windows.Controls.TreeView> の作成方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e6aed-121">The following XAML shows how to create a <xref:System.Windows.Controls.TreeView> that uses the custom <xref:System.Windows.Controls.VirtualizingStackPanel>.</span></span>  
  
 [!code-xaml[TreeViewFindTVI#3](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml#3)]  
  
## <a name="see-also"></a><span data-ttu-id="e6aed-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="e6aed-122">See also</span></span>

- [<span data-ttu-id="e6aed-123">TreeView のパフォーマンスを改善する</span><span class="sxs-lookup"><span data-stu-id="e6aed-123">Improve the Performance of a TreeView</span></span>](how-to-improve-the-performance-of-a-treeview.md)
