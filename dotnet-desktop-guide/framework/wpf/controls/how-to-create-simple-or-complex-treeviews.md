---
title: '方法: 単純または複雑な TreeView を作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- TreeView control [WPF], creating
- Control class [WPF], TreeView [WPF], creating
ms.assetid: 1defbb78-b8e7-4c0e-b650-576453ac828d
ms.openlocfilehash: 7edb4933ebcc0f0d2cb02754238c2342ee9dd4a2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985151"
---
# <a name="how-to-create-simple-or-complex-treeviews"></a><span data-ttu-id="548fc-102">方法: 単純または複雑な TreeView を作成する</span><span class="sxs-lookup"><span data-stu-id="548fc-102">How to: Create Simple or Complex TreeViews</span></span>
<span data-ttu-id="548fc-103">この例では、単純または複雑な <xref:System.Windows.Controls.TreeView> コントロールを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="548fc-103">This example shows how to create simple or complex <xref:System.Windows.Controls.TreeView> controls.</span></span>  
  
 <span data-ttu-id="548fc-104"><xref:System.Windows.Controls.TreeView> は <xref:System.Windows.Controls.TreeViewItem> コントロールの階層から構成されます。このコントロールには、単純なテキスト文字列が含まれることもあれば、<xref:System.Windows.Controls.Button> コントロールやコンテンツが埋め込まれた <xref:System.Windows.Controls.StackPanel> など、もっと複雑なコンテンツが含まれることもあります。</span><span class="sxs-lookup"><span data-stu-id="548fc-104">A <xref:System.Windows.Controls.TreeView> consists of a hierarchy of <xref:System.Windows.Controls.TreeViewItem> controls, which can contain simple text strings and also more complex content, such as <xref:System.Windows.Controls.Button> controls or a <xref:System.Windows.Controls.StackPanel> with embedded content.</span></span> <span data-ttu-id="548fc-105"><xref:System.Windows.Controls.TreeView> コンテンツは明示的に定義できます。あるいは、データ ソースからコンテンツを提供できます。</span><span class="sxs-lookup"><span data-stu-id="548fc-105">You can explicitly define the <xref:System.Windows.Controls.TreeView> content or a data source can provide the content.</span></span> <span data-ttu-id="548fc-106">このトピックではこうした概念の例を提供します。</span><span class="sxs-lookup"><span data-stu-id="548fc-106">This topic provides examples of these concepts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="548fc-107">例</span><span class="sxs-lookup"><span data-stu-id="548fc-107">Example</span></span>  
 <span data-ttu-id="548fc-108"><xref:System.Windows.Controls.TreeViewItem> の <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> プロパティには、その項目に対して <xref:System.Windows.Controls.TreeView> で表示されるコンテンツが含まれます。</span><span class="sxs-lookup"><span data-stu-id="548fc-108">The <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> property of the <xref:System.Windows.Controls.TreeViewItem> contains the content that the <xref:System.Windows.Controls.TreeView> displays for that item.</span></span> <span data-ttu-id="548fc-109"><xref:System.Windows.Controls.TreeViewItem> には、その子要素として <xref:System.Windows.Controls.TreeViewItem> コントロールが与えられることもあります。また、これらの子要素は <xref:System.Windows.Controls.ItemsControl.Items%2A> プロパティを利用して定義できます。</span><span class="sxs-lookup"><span data-stu-id="548fc-109">A <xref:System.Windows.Controls.TreeViewItem> can also have <xref:System.Windows.Controls.TreeViewItem> controls as its child elements and you can define these child elements by using the <xref:System.Windows.Controls.ItemsControl.Items%2A> property.</span></span>  
  
 <span data-ttu-id="548fc-110">次の例では、<xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> プロパティをテキスト文字列に設定することで <xref:System.Windows.Controls.TreeViewItem> コンテンツを明示的に定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="548fc-110">The following example shows how to explicitly define <xref:System.Windows.Controls.TreeViewItem> content by setting the <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> property to a text string.</span></span>  
  
 [!code-xaml[TreeViewSimple#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#1)]  
  
 <span data-ttu-id="548fc-111">次の例では、<xref:System.Windows.Controls.Button> コントロールである <xref:System.Windows.Controls.ItemsControl.Items%2A> を定義することで <xref:System.Windows.Controls.TreeViewItem> の子要素を定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="548fc-111">The following example show how to define child elements of a <xref:System.Windows.Controls.TreeViewItem> by defining <xref:System.Windows.Controls.ItemsControl.Items%2A> that are <xref:System.Windows.Controls.Button> controls.</span></span>  
  
 [!code-xaml[TreeViewSimple#3](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#3)]  
  
 <span data-ttu-id="548fc-112">次の例では、<xref:System.Windows.Data.XmlDataProvider> によって <xref:System.Windows.Controls.TreeViewItem> コンテンツが提供され、<xref:System.Windows.HierarchicalDataTemplate> によってコンテンツの外観が定義される <xref:System.Windows.Controls.TreeView> を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="548fc-112">The following example shows how to create a <xref:System.Windows.Controls.TreeView> where an <xref:System.Windows.Data.XmlDataProvider> provides <xref:System.Windows.Controls.TreeViewItem> content and a <xref:System.Windows.HierarchicalDataTemplate> defines the appearance of the content.</span></span>  
  
 [!code-xaml[TreeViewSimple#6](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#6)]  
  
 [!code-xaml[TreeViewSimple#7](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#7)]  
  
 [!code-xaml[TreeViewSimple#5](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#5)]  
  
 <span data-ttu-id="548fc-113">次の例では、<xref:System.Windows.Controls.TreeViewItem> コンテンツには、コンテンツが埋め込まれている <xref:System.Windows.Controls.DockPanel> コントロールが含まれる <xref:System.Windows.Controls.TreeView> を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="548fc-113">The following example shows how to create a <xref:System.Windows.Controls.TreeView> where the <xref:System.Windows.Controls.TreeViewItem> content contains <xref:System.Windows.Controls.DockPanel> controls that have embedded content.</span></span>  
  
 [!code-xaml[TreeViewSimple#9](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#9)]  
  
## <a name="see-also"></a><span data-ttu-id="548fc-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="548fc-114">See also</span></span>

- <xref:System.Windows.Controls.TreeView>
- <xref:System.Windows.Controls.TreeViewItem>
- [<span data-ttu-id="548fc-115">TreeView の概要</span><span class="sxs-lookup"><span data-stu-id="548fc-115">TreeView Overview</span></span>](treeview-overview.md)
- [<span data-ttu-id="548fc-116">方法トピック</span><span class="sxs-lookup"><span data-stu-id="548fc-116">How-to Topics</span></span>](treeview-how-to-topics.md)
