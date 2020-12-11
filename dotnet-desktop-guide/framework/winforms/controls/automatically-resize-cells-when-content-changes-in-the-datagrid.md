---
title: DataGridView コントロールのコンテンツの変更時にセルのサイズを自動的に変更する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], resizing cells automatically
- cells [Windows Forms], resizing automatically
- DataGridView control [Windows Forms], resizing cells
ms.assetid: 1d68934d-a04c-4b12-9e66-c856c6828131
ms.openlocfilehash: 86e3bce993aa06546e301c6d7a7e03a31013c337
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96975153"
---
# <a name="how-to-automatically-resize-cells-when-content-changes-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="13ccb-102">方法 : Windows フォームの DataGridView コントロールの内容変更時にセルのサイズを自動的に変更する</span><span class="sxs-lookup"><span data-stu-id="13ccb-102">How to: Automatically Resize Cells When Content Changes in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="13ccb-103">コンテンツが変更されたときは常に行、列、ヘッダーのサイズを自動的に変更し、クリッピングなしでセルが値を表示するのに十分な大きさになるように、 <xref:System.Windows.Forms.DataGridView> コントロールを構成できます。</span><span class="sxs-lookup"><span data-stu-id="13ccb-103">You can configure the <xref:System.Windows.Forms.DataGridView> control to resize its rows, columns, and headers automatically whenever content changes, so that cells are always large enough to display their values without clipping.</span></span>  
  
 <span data-ttu-id="13ccb-104">新しいサイズを決定するために使用するセルを制限する多くのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="13ccb-104">You have many options to restrict which cells are used to determine the new sizes.</span></span> <span data-ttu-id="13ccb-105">たとえば、現在表示されている行の値のみに基づいて、その列の幅のサイズを自動的に変更するコントロールを構成できます。</span><span class="sxs-lookup"><span data-stu-id="13ccb-105">For example, you can configure the control to automatically resize the width of its columns based only on the values in rows that are currently displayed.</span></span> <span data-ttu-id="13ccb-106">これにより、大量の行を処理するときの非効率性を回避できますが、この場合では、 <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> などのサイズ調整のメソッドを使用して、選択時にサイズを調整することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="13ccb-106">With this, you can avoid inefficiency when working with large numbers of rows, although in this case, you might want to use sizing methods such as <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> to adjust sizes at times of your choosing.</span></span>  
  
 <span data-ttu-id="13ccb-107">自動サイズ変更の詳細については、「 [Sizing Options in the Windows Forms DataGridView Control](sizing-options-in-the-windows-forms-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13ccb-107">For more information about automatic resizing, see [Sizing Options in the Windows Forms DataGridView Control](sizing-options-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="13ccb-108">次のコード例は、自動サイズ変更に使用できるオプションを示します。</span><span class="sxs-lookup"><span data-stu-id="13ccb-108">The following code example demonstrates the options available for automatic resizing.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13ccb-109">例</span><span class="sxs-lookup"><span data-stu-id="13ccb-109">Example</span></span>  
 [!code-cpp[System.Windows.Forms.DataGridView.AutoSizing#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.AutoSizing/CPP/autosizing.cpp#0)]
 [!code-csharp[System.Windows.Forms.DataGridView.AutoSizing#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.AutoSizing/CS/autosizing.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.AutoSizing#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.AutoSizing/VB/autosizing.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="13ccb-110">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="13ccb-110">Compiling the Code</span></span>  
 <span data-ttu-id="13ccb-111">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="13ccb-111">This example requires:</span></span>  
  
- <span data-ttu-id="13ccb-112">System、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="13ccb-112">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13ccb-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="13ccb-113">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoSizeRowsMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>
- <xref:System.Windows.Forms.DataGridViewColumnHeadersHeightSizeMode>
- <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>
- [<span data-ttu-id="13ccb-114">Windows フォーム DataGridView コントロール内の列と行のサイズ変更</span><span class="sxs-lookup"><span data-stu-id="13ccb-114">Resizing Columns and Rows in the Windows Forms DataGridView Control</span></span>](resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="13ccb-115">Windows フォーム DataGridView コントロールのサイズ変更オプション</span><span class="sxs-lookup"><span data-stu-id="13ccb-115">Sizing Options in the Windows Forms DataGridView Control</span></span>](sizing-options-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="13ccb-116">方法: Windows フォームの DataGridView コントロールの内容に合わせてセルのサイズをプログラムで変更する</span><span class="sxs-lookup"><span data-stu-id="13ccb-116">How to: Programmatically Resize Cells to Fit Content in the Windows Forms DataGridView Control</span></span>](programmatically-resize-cells-to-fit-content-in-the-datagrid.md)
