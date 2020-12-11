---
title: DataGridView コントロールの個々のセルにツールヒントを追加する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], adding to data grids
- DataGridView control [Windows Forms], adding tooltips
- data grids [Windows Forms], adding tooltips
ms.assetid: 2a81f9de-d58b-4ea8-bc0b-8d93c2f4cf78
ms.openlocfilehash: ac86db5fa27a95adb20888cd59b5e236941d9177
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96975154"
---
# <a name="how-to-add-tooltips-to-individual-cells-in-a-windows-forms-datagridview-control"></a><span data-ttu-id="14863-102">方法: Windows フォーム DataGridView コントロールの各セルにツールヒントを追加する</span><span class="sxs-lookup"><span data-stu-id="14863-102">How to: Add ToolTips to Individual Cells in a Windows Forms DataGridView Control</span></span>
<span data-ttu-id="14863-103">既定では、ツールヒントは、 <xref:System.Windows.Forms.DataGridView> コンテンツ全体を表示するには小さすぎるセルの値を表示するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="14863-103">By default, ToolTips are used to display the values of <xref:System.Windows.Forms.DataGridView> cells that are too small to show their entire contents.</span></span> <span data-ttu-id="14863-104">ただし、この動作をオーバーライドして、個々のセルにツールヒントテキストの値を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="14863-104">You can override this behavior, however, to set ToolTip-text values for individual cells.</span></span> <span data-ttu-id="14863-105">これは、セルに関する追加情報をユーザーに表示したり、セルの内容に関する別の説明をユーザーに提供したりする場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="14863-105">This is useful to display to users additional information about a cell or to provide to users an alternate description of the cell contents.</span></span> <span data-ttu-id="14863-106">たとえば、状態アイコンを表示する行がある場合、ヒントを使用してテキストの説明を入力することができます。</span><span class="sxs-lookup"><span data-stu-id="14863-106">For example, if you have a row that displays status icons, you may want to provide text explanations using ToolTips.</span></span>  
  
 <span data-ttu-id="14863-107">また、プロパティをに設定することによって、セルレベルのツールヒントの表示を無効にすることもでき <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType> `false` ます。</span><span class="sxs-lookup"><span data-stu-id="14863-107">You can also disable the display of cell-level ToolTips by setting the <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType> property to `false`.</span></span>  
  
### <a name="to-add-a-tooltip-to-a-cell"></a><span data-ttu-id="14863-108">ヒントをセルに追加するには</span><span class="sxs-lookup"><span data-stu-id="14863-108">To add a ToolTip to a cell</span></span>  
  
- <span data-ttu-id="14863-109"><xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="14863-109">Set the <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/cpp/datagridviewcell.tooltiptext.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/CS/datagridviewcell.tooltiptext.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/VB/datagridviewcell.tooltiptext.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="14863-110">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="14863-110">Compiling the Code</span></span>  
  
- <span data-ttu-id="14863-111">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="14863-111">This example requires:</span></span>  
  
- <span data-ttu-id="14863-112">という名前のコントロール。このコントロールには、 <xref:System.Windows.Forms.DataGridView> `dataGridView1` `Rating` 1 ~ 4 個のアスタリスク ("\*") 記号の文字列値を表示するためのという名前の列があります。</span><span class="sxs-lookup"><span data-stu-id="14863-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `Rating` for displaying string values of one through four asterisk ("\*") symbols.</span></span> <span data-ttu-id="14863-113"><xref:System.Windows.Forms.DataGridView.CellFormatting>コントロールのイベントは、例に示すイベントハンドラーメソッドに関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="14863-113">The <xref:System.Windows.Forms.DataGridView.CellFormatting> event of the control must be associated with the event handler method shown in the example.</span></span>  
  
- <span data-ttu-id="14863-114"><xref:System?displayProperty=nameWithType> アセンブリおよび <xref:System.Windows.Forms?displayProperty=nameWithType> アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="14863-114">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="14863-115">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="14863-115">Robust Programming</span></span>  
 <span data-ttu-id="14863-116"><xref:System.Windows.Forms.DataGridView>コントロールを外部データソースにバインドしたり、仮想モードを実装して独自のデータソースを提供したりすると、パフォーマンスの問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="14863-116">When you bind the <xref:System.Windows.Forms.DataGridView> control to an external data source or provide your own data source by implementing virtual mode, you might encounter performance issues.</span></span> <span data-ttu-id="14863-117">大量のデータを処理するときにパフォーマンスが低下しないようにするには、 <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> 複数のセルのプロパティを設定するのではなく、イベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="14863-117">To avoid a performance penalty when working with large amounts of data, handle the <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> event rather than setting the <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> property of multiple cells.</span></span> <span data-ttu-id="14863-118">このイベントを処理するときに、セルプロパティの値を取得する <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> と、イベントが発生し、 <xref:System.Windows.Forms.DataGridViewCellToolTipTextNeededEventArgs.ToolTipText%2A?displayProperty=nameWithType> イベントハンドラーに指定されたプロパティの値が返されます。</span><span class="sxs-lookup"><span data-stu-id="14863-118">When you handle this event, getting the value of a cell <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> property raises the event and returns the value of the <xref:System.Windows.Forms.DataGridViewCellToolTipTextNeededEventArgs.ToolTipText%2A?displayProperty=nameWithType> property as specified in the event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14863-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="14863-119">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCell>
- <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType>
- [<span data-ttu-id="14863-120">Windows フォーム DataGridView コントロールのセル、行、および列を使用したプログラミング</span><span class="sxs-lookup"><span data-stu-id="14863-120">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](programming-with-cells-rows-and-columns-in-the-datagrid.md)
