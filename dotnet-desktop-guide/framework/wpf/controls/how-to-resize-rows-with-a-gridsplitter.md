---
title: '方法: GridSplitter を使用して行のサイズを変更する'
ms.date: 03/30/2017
helpviewer_keywords:
- resizing grid rows [WPF]
- grid rows [WPF], resizing
- GridSplitter control [WPF], resizing grid rows
ms.assetid: 2413a9f2-1d81-46ed-95cb-95ec8233eea2
ms.openlocfilehash: 6760a7a691af4f666294556cae3bc95a4299730a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983576"
---
# <a name="how-to-resize-rows-with-a-gridsplitter"></a><span data-ttu-id="ee5ba-102">方法: GridSplitter を使用して行のサイズを変更する</span><span class="sxs-lookup"><span data-stu-id="ee5ba-102">How to: Resize Rows with a GridSplitter</span></span>
<span data-ttu-id="ee5ba-103">この例からは、水平 <xref:System.Windows.Controls.GridSplitter> を使用することで、<xref:System.Windows.Controls.Grid> の寸法を変更することなく、<xref:System.Windows.Controls.Grid> 内の 2 つの行間のスペースを再配分する方法がわかります。</span><span class="sxs-lookup"><span data-stu-id="ee5ba-103">This example shows how to use a horizontal <xref:System.Windows.Controls.GridSplitter> to redistribute the space between two rows in a <xref:System.Windows.Controls.Grid> without changing the dimensions of the <xref:System.Windows.Controls.Grid>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee5ba-104">例</span><span class="sxs-lookup"><span data-stu-id="ee5ba-104">Example</span></span>  
 <span data-ttu-id="ee5ba-105">**行の端に重なって表示される GridSplitter を作成する方法**</span><span class="sxs-lookup"><span data-stu-id="ee5ba-105">**How to create a GridSplitter that overlays the edge of a row**</span></span>  
  
 <span data-ttu-id="ee5ba-106"><xref:System.Windows.Controls.Grid> 内で隣接する行のサイズを変更する <xref:System.Windows.Controls.GridSplitter> を指定するには、サイズを変更する行の 1 つに <xref:System.Windows.Controls.Grid.Row%2A> 添付プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="ee5ba-106">To specify a <xref:System.Windows.Controls.GridSplitter> that resizes adjacent rows in a <xref:System.Windows.Controls.Grid>, set the <xref:System.Windows.Controls.Grid.Row%2A> attached property to one of the rows that you want to resize.</span></span> <span data-ttu-id="ee5ba-107"><xref:System.Windows.Controls.Grid> に複数の列がある場合は、<xref:System.Windows.Controls.Grid.ColumnSpan%2A> 添付プロパティを設定して列の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="ee5ba-107">If your <xref:System.Windows.Controls.Grid> has more than one column, set the <xref:System.Windows.Controls.Grid.ColumnSpan%2A> attached property to specify the number of columns.</span></span> <span data-ttu-id="ee5ba-108">次に、<xref:System.Windows.FrameworkElement.VerticalAlignment%2A> を <xref:System.Windows.VerticalAlignment.Top> または <xref:System.Windows.VerticalAlignment.Bottom> に設定します (どちらの配置にするかは、サイズを変更する 2 つの行によって決まります)。</span><span class="sxs-lookup"><span data-stu-id="ee5ba-108">Then set the <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> to <xref:System.Windows.VerticalAlignment.Top> or <xref:System.Windows.VerticalAlignment.Bottom> (which alignment you set depends on which two rows you want to resize).</span></span> <span data-ttu-id="ee5ba-109">最後に、<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> プロパティを <xref:System.Windows.HorizontalAlignment.Stretch> に設定します。</span><span class="sxs-lookup"><span data-stu-id="ee5ba-109">Finally, set the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property to <xref:System.Windows.HorizontalAlignment.Stretch>.</span></span>  
  
 <span data-ttu-id="ee5ba-110">次の例では、隣接する行のサイズを変更する水平 <xref:System.Windows.Controls.GridSplitter> を定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ee5ba-110">The following example shows how to define a horizontal <xref:System.Windows.Controls.GridSplitter> that resizes adjacent rows.</span></span>  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterRowOverlay](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterrowoverlay)]  
  
 <span data-ttu-id="ee5ba-111">その独自の行を占有しない <xref:System.Windows.Controls.GridSplitter> は、<xref:System.Windows.Controls.Grid> 内の他のコントロールによって隠されることがあります。</span><span class="sxs-lookup"><span data-stu-id="ee5ba-111">A <xref:System.Windows.Controls.GridSplitter> that does not occupy its own row may be obscured by other controls in the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="ee5ba-112">この問題の詳しい回避方法については、[GridSplitter を表示されるようにする](how-to-make-sure-that-a-gridsplitter-is-visible.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee5ba-112">For more information about how to prevent this issue, see [Make Sure That a GridSplitter Is Visible](how-to-make-sure-that-a-gridsplitter-is-visible.md).</span></span>  
  
 <span data-ttu-id="ee5ba-113">**行を占有する GridSplitter を作成する方法**</span><span class="sxs-lookup"><span data-stu-id="ee5ba-113">**How to create a GridSplitter that occupies a row**</span></span>  
  
 <span data-ttu-id="ee5ba-114"><xref:System.Windows.Controls.Grid> 内の行を占有する <xref:System.Windows.Controls.GridSplitter> を指定するには、サイズを変更する行の 1 つに <xref:System.Windows.Controls.Grid.Row%2A> 添付プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="ee5ba-114">To specify a <xref:System.Windows.Controls.GridSplitter> that occupies a row in a <xref:System.Windows.Controls.Grid>, set the <xref:System.Windows.Controls.Grid.Row%2A> attached property to one of the rows that you want to resize.</span></span> <span data-ttu-id="ee5ba-115"><xref:System.Windows.Controls.Grid> に複数の列がある場合、<xref:System.Windows.Controls.Grid.ColumnSpan%2A> 添付プロパティを列の数に設定します。</span><span class="sxs-lookup"><span data-stu-id="ee5ba-115">If your <xref:System.Windows.Controls.Grid> has more than one column, set the <xref:System.Windows.Controls.Grid.ColumnSpan%2A> attached property to the number of columns.</span></span> <span data-ttu-id="ee5ba-116">次に <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> を <xref:System.Windows.VerticalAlignment.Center> に設定し、<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> プロパティを <xref:System.Windows.HorizontalAlignment.Stretch> に設定し、<xref:System.Windows.Controls.GridSplitter> が含まれる行の <xref:System.Windows.Controls.RowDefinition.Height%2A> を <xref:System.Windows.GridLength.Auto%2A> に設定します。</span><span class="sxs-lookup"><span data-stu-id="ee5ba-116">Then set the <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> to <xref:System.Windows.VerticalAlignment.Center>, set the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property to <xref:System.Windows.HorizontalAlignment.Stretch>, and set the <xref:System.Windows.Controls.RowDefinition.Height%2A> of the row that contains the <xref:System.Windows.Controls.GridSplitter> to <xref:System.Windows.GridLength.Auto%2A>.</span></span>  
  
 <span data-ttu-id="ee5ba-117">次の例では、ある行を占有し、その両側の行のサイズを変更する水平 <xref:System.Windows.Controls.GridSplitter> を定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ee5ba-117">The following example shows how to define a horizontal <xref:System.Windows.Controls.GridSplitter> that occupies a row and resizes the rows on either side of it.</span></span>  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterEntireRowPart1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirerowpart1)]  
[!code-xaml[GridSplitterRowColumn#GridSplitterEntireRowPart2](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirerowpart2)]  
  
## <a name="see-also"></a><span data-ttu-id="ee5ba-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="ee5ba-118">See also</span></span>

- <xref:System.Windows.Controls.GridSplitter>
- [<span data-ttu-id="ee5ba-119">方法トピック</span><span class="sxs-lookup"><span data-stu-id="ee5ba-119">How-to Topics</span></span>](gridsplitter-how-to-topics.md)
