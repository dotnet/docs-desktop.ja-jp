---
title: DataGridView コントロールの内容に合わせてセルのサイズをプログラムによって変更する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], resizing cells to fit content
- cells [Windows Forms], resizing to fit contents
- DataGridView control [Windows Forms], resizing cells
- grids [Windows Forms], resizing cells to fit content
ms.assetid: 63d770dc-b3f5-462b-901a-3125b2753792
ms.openlocfilehash: df3b378a8ba358fa0bfe549a7901b3d59d53f556
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983371"
---
# <a name="how-to-programmatically-resize-cells-to-fit-content-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="5fb1b-102">方法: Windows フォームの DataGridView コントロールの内容に合わせてセルのサイズをプログラムで変更する</span><span class="sxs-lookup"><span data-stu-id="5fb1b-102">How to: Programmatically Resize Cells to Fit Content in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="5fb1b-103"><xref:System.Windows.Forms.DataGridView> コントロールのさまざまなメソッドを使用すると、行、列、およびヘッダーのサイズを変更して、切り捨てることなく値の全体を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="5fb1b-103">You can use the <xref:System.Windows.Forms.DataGridView> control methods to resize rows, columns, and headers so that they display their entire values without truncation.</span></span> <span data-ttu-id="5fb1b-104">これらのメソッドを使用して、選択時に <xref:System.Windows.Forms.DataGridView> 要素のサイズを変更できます。</span><span class="sxs-lookup"><span data-stu-id="5fb1b-104">You can use these methods to resize <xref:System.Windows.Forms.DataGridView> elements at times of your choosing.</span></span> <span data-ttu-id="5fb1b-105">代わりに、コンテンツが変更されるたびに、これらの要素のサイズを自動的に変更するコントロールを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="5fb1b-105">Alternately, you can configure the control to resize these elements automatically whenever content changes.</span></span> <span data-ttu-id="5fb1b-106">ただしこれは、大規模なデータ セットを処理しているときは、データが頻繁に変更されるときは、効率的ではありません。</span><span class="sxs-lookup"><span data-stu-id="5fb1b-106">This can be inefficient, however, when you are working with large data sets or when your data changes frequently.</span></span> <span data-ttu-id="5fb1b-107">詳細については、「 [Windows フォーム DataGridView コントロールのサイズ変更オプション](sizing-options-in-the-windows-forms-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5fb1b-107">For more information, see [Sizing Options in the Windows Forms DataGridView Control](sizing-options-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="5fb1b-108">通常はデータ ソースから新しいデータを読み込むときや、ユーザーが値を編集するときにのみ、内容に合わせて <xref:System.Windows.Forms.DataGridView> 要素をプログラムで調整します。</span><span class="sxs-lookup"><span data-stu-id="5fb1b-108">Typically, you will programmatically adjust <xref:System.Windows.Forms.DataGridView> elements to fit their content only when you load new data from a data source or when the user has edited a value.</span></span> <span data-ttu-id="5fb1b-109">これは、パフォーマンスを最適化するために便利ですが、ユーザーがマウスを使って行および列のサイズを手動で変更できるようにする場合にも便利です。</span><span class="sxs-lookup"><span data-stu-id="5fb1b-109">This is useful to optimize performance, but it is also useful when you want to enable your users to manually resize rows and columns with the mouse.</span></span>  
  
 <span data-ttu-id="5fb1b-110">次のコード例は、プログラムでのサイズ変更に使用できるオプションを示します。</span><span class="sxs-lookup"><span data-stu-id="5fb1b-110">The following code example demonstrates the options available to you for programmatic resizing.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5fb1b-111">例</span><span class="sxs-lookup"><span data-stu-id="5fb1b-111">Example</span></span>  
 [!code-cpp[System.Windows.Forms.DataGridView.ProgrammaticResizing#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ProgrammaticResizing/CPP/programmaticsizing.cpp#0)]
 [!code-csharp[System.Windows.Forms.DataGridView.ProgrammaticResizing#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ProgrammaticResizing/CS/programmaticsizing.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.ProgrammaticResizing#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ProgrammaticResizing/VB/programmaticsizing.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5fb1b-112">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="5fb1b-112">Compiling the Code</span></span>  
 <span data-ttu-id="5fb1b-113">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5fb1b-113">This example requires:</span></span>  
  
- <span data-ttu-id="5fb1b-114">System、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="5fb1b-114">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fb1b-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="5fb1b-115">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumnHeadersHeight%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeRow%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeRowHeadersWidth%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewAutoSizeRowMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>
- <xref:System.Windows.Forms.DataGridViewColumnHeadersHeightSizeMode>
- <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>
- [<span data-ttu-id="5fb1b-116">Windows フォーム DataGridView コントロール内の列と行のサイズ変更</span><span class="sxs-lookup"><span data-stu-id="5fb1b-116">Resizing Columns and Rows in the Windows Forms DataGridView Control</span></span>](resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="5fb1b-117">Windows フォーム DataGridView コントロールのサイズ変更オプション</span><span class="sxs-lookup"><span data-stu-id="5fb1b-117">Sizing Options in the Windows Forms DataGridView Control</span></span>](sizing-options-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="5fb1b-118">方法 : Windows フォームの DataGridView コントロールの内容変更時にセルのサイズを自動的に変更する</span><span class="sxs-lookup"><span data-stu-id="5fb1b-118">How to: Automatically Resize Cells When Content Changes in the Windows Forms DataGridView Control</span></span>](automatically-resize-cells-when-content-changes-in-the-datagrid.md)
