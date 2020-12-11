---
title: '方法: GridSplitter を使用して列のサイズを変更する'
ms.date: 03/30/2017
helpviewer_keywords:
- grid columns [WPF], resizing
- GridSplitter control [WPF], resizing grid columns
- resizing grid columns [WPF]
ms.assetid: 47b20fe6-7adc-4aa6-9693-b4e184eef74b
ms.openlocfilehash: f743e9ccf8a984a646a4b8f05ee99162e5bc73ad
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983580"
---
# <a name="how-to-resize-columns-with-a-gridsplitter"></a><span data-ttu-id="44da0-102">方法: GridSplitter を使用して列のサイズを変更する</span><span class="sxs-lookup"><span data-stu-id="44da0-102">How to: Resize Columns with a GridSplitter</span></span>
<span data-ttu-id="44da0-103">この例からは、垂直 <xref:System.Windows.Controls.GridSplitter> を正しく作成することで、<xref:System.Windows.Controls.Grid> の寸法を変更することなく、<xref:System.Windows.Controls.Grid> 内の 2 つの列間のスペースを再配分する方法がわかります。</span><span class="sxs-lookup"><span data-stu-id="44da0-103">This example shows how to create a vertical <xref:System.Windows.Controls.GridSplitter> in order to redistribute the space between two columns in a <xref:System.Windows.Controls.Grid> without changing the dimensions of the <xref:System.Windows.Controls.Grid>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="44da0-104">例</span><span class="sxs-lookup"><span data-stu-id="44da0-104">Example</span></span>  
 <span data-ttu-id="44da0-105">**列の端に重なって表示される GridSplitter を作成する方法**</span><span class="sxs-lookup"><span data-stu-id="44da0-105">**How to create a GridSplitter that overlays the edge of a column**</span></span>  
  
 <span data-ttu-id="44da0-106"><xref:System.Windows.Controls.Grid> 内で隣接する列のサイズを変更する <xref:System.Windows.Controls.GridSplitter> を指定するには、サイズを変更する列の 1 つに <xref:System.Windows.Controls.Grid.Column%2A> 添付プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="44da0-106">To specify a <xref:System.Windows.Controls.GridSplitter> that resizes adjacent columns in a <xref:System.Windows.Controls.Grid>, set the <xref:System.Windows.Controls.Grid.Column%2A> attached property to one of the columns that you want to resize.</span></span> <span data-ttu-id="44da0-107"><xref:System.Windows.Controls.Grid> に複数の行がある場合、<xref:System.Windows.Controls.Grid.RowSpan%2A> 添付プロパティを行の数に設定します。</span><span class="sxs-lookup"><span data-stu-id="44da0-107">If your <xref:System.Windows.Controls.Grid> has more than one row, set the <xref:System.Windows.Controls.Grid.RowSpan%2A> attached property to the number of rows.</span></span> <span data-ttu-id="44da0-108">次に、<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> プロパティを <xref:System.Windows.HorizontalAlignment.Left> または <xref:System.Windows.HorizontalAlignment.Right> に設定します (どちらの配置にするかは、サイズを変更する 2 つの列によって決まります)。</span><span class="sxs-lookup"><span data-stu-id="44da0-108">Then set the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property to <xref:System.Windows.HorizontalAlignment.Left> or <xref:System.Windows.HorizontalAlignment.Right> (which alignment you set depends on which two columns you want to resize).</span></span> <span data-ttu-id="44da0-109">最後に、<xref:System.Windows.FrameworkElement.VerticalAlignment%2A> プロパティを <xref:System.Windows.VerticalAlignment.Stretch> に設定します。</span><span class="sxs-lookup"><span data-stu-id="44da0-109">Finally, set the <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> property to <xref:System.Windows.VerticalAlignment.Stretch>.</span></span>  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterColumnOverlay](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplittercolumnoverlay)]  
  
 <span data-ttu-id="44da0-110">その独自の列がない <xref:System.Windows.Controls.GridSplitter> は、<xref:System.Windows.Controls.Grid> 内の他のコントロールによって隠されることがあります。</span><span class="sxs-lookup"><span data-stu-id="44da0-110">A <xref:System.Windows.Controls.GridSplitter> that does not have its own column may be obscured by other controls in the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="44da0-111">この問題の詳しい回避方法については、[GridSplitter を表示されるようにする](how-to-make-sure-that-a-gridsplitter-is-visible.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44da0-111">For more information about how to prevent this issue, see [Make Sure That a GridSplitter Is Visible](how-to-make-sure-that-a-gridsplitter-is-visible.md).</span></span>  
  
 <span data-ttu-id="44da0-112">**列を占有する GridSplitter を作成する方法**</span><span class="sxs-lookup"><span data-stu-id="44da0-112">**How to create a GridSplitter that occupies a column**</span></span>  
  
 <span data-ttu-id="44da0-113"><xref:System.Windows.Controls.Grid> 内の列を占有する <xref:System.Windows.Controls.GridSplitter> を指定するには、サイズを変更する列の 1 つに <xref:System.Windows.Controls.Grid.Column%2A> 添付プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="44da0-113">To specify a <xref:System.Windows.Controls.GridSplitter> that occupies a column in a <xref:System.Windows.Controls.Grid>, set the <xref:System.Windows.Controls.Grid.Column%2A> attached property to one of the columns that you want to resize.</span></span> <span data-ttu-id="44da0-114">Grid に複数の行がある場合、<xref:System.Windows.Controls.Grid.RowSpan%2A> 添付プロパティを行の数に設定します。</span><span class="sxs-lookup"><span data-stu-id="44da0-114">If your Grid has more than one row, set the <xref:System.Windows.Controls.Grid.RowSpan%2A> attached property to the number of rows.</span></span> <span data-ttu-id="44da0-115">次に <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> を <xref:System.Windows.HorizontalAlignment.Center> に設定し、<xref:System.Windows.FrameworkElement.VerticalAlignment%2A> プロパティを <xref:System.Windows.VerticalAlignment.Stretch> に設定し、<xref:System.Windows.Controls.GridSplitter> が含まれる列の <xref:System.Windows.Controls.ColumnDefinition.Width%2A> を <xref:System.Windows.GridLength.Auto%2A> に設定します。</span><span class="sxs-lookup"><span data-stu-id="44da0-115">Then set the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> to <xref:System.Windows.HorizontalAlignment.Center>, set the <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> property to <xref:System.Windows.VerticalAlignment.Stretch>, and set the <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of the column that contains the <xref:System.Windows.Controls.GridSplitter> to <xref:System.Windows.GridLength.Auto%2A>.</span></span>  
  
 <span data-ttu-id="44da0-116">次の例では、ある列を占有し、その両側の列のサイズを変更する垂直 <xref:System.Windows.Controls.GridSplitter> を定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="44da0-116">The following example shows how to define a vertical <xref:System.Windows.Controls.GridSplitter> that occupies a column and resizes the columns on either side of it.</span></span>  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterEntireColumnPart1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart1)]  
[!code-xaml[GridSplitterRowColumn#GridSplitterEntireColumnPart2](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart2)]  
  
## <a name="see-also"></a><span data-ttu-id="44da0-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="44da0-117">See also</span></span>

- <xref:System.Windows.Controls.GridSplitter>
- [<span data-ttu-id="44da0-118">方法トピック</span><span class="sxs-lookup"><span data-stu-id="44da0-118">How-to Topics</span></span>](gridsplitter-how-to-topics.md)
