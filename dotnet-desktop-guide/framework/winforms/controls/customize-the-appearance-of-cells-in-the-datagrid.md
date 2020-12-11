---
title: DataGridView コントロールのセルの外観をカスタマイズする
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing cells
- DataGridView control [Windows Forms], customizing cells
- cells [Windows Forms], customizing in DataGridView control
ms.assetid: 478b20c9-625c-4116-9c5c-5a16e6f4ec67
ms.openlocfilehash: 754932427a365a7b032c1ac9627d3237d1f7d0c6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974243"
---
# <a name="how-to-customize-the-appearance-of-cells-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="99e8a-102">方法 : Windows フォームの DataGridView コントロールのセルの外観をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="99e8a-102">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="99e8a-103">コントロールのイベントを処理することで、任意のセルの外観をカスタマイズでき <xref:System.Windows.Forms.DataGridView> <xref:System.Windows.Forms.DataGridView.CellPainting> ます。</span><span class="sxs-lookup"><span data-stu-id="99e8a-103">You can customize the appearance of any cell by handling the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CellPainting> event.</span></span> <span data-ttu-id="99e8a-104"><xref:System.Windows.Forms.DataGridView>コントロールのは <xref:System.Drawing.Graphics> 、のプロパティから抽出でき <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> ます。</span><span class="sxs-lookup"><span data-stu-id="99e8a-104">You can extract the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Drawing.Graphics> from the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> property of the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>.</span></span> <span data-ttu-id="99e8a-105">これにより、 <xref:System.Drawing.Graphics> コントロール全体の外観に影響を与えることができ <xref:System.Windows.Forms.DataGridView> ますが、通常は、現在描画されているセルの外観のみに影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="99e8a-105">With this <xref:System.Drawing.Graphics>, you can affect the appearance of the entire <xref:System.Windows.Forms.DataGridView> control, but you will usually want to affect only the appearance of the cell that is currently being painted.</span></span> <span data-ttu-id="99e8a-106"><xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A>のプロパティを <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> 使用すると、描画操作を、現在描画されているセルに制限できます。</span><span class="sxs-lookup"><span data-stu-id="99e8a-106">The <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> property of the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> enables you to restrict your painting operations to the cell that is currently being painted.</span></span>  
  
 <span data-ttu-id="99e8a-107">次のコード例では、 `ContactName` コントロールの配色を使用して、列のすべてのセルを塗りつぶし <xref:System.Windows.Forms.DataGridView> ます。</span><span class="sxs-lookup"><span data-stu-id="99e8a-107">In the following code example, you will paint all the cells in a `ContactName` column using the <xref:System.Windows.Forms.DataGridView> control's color scheme.</span></span> <span data-ttu-id="99e8a-108">各セルのテキストコンテンツはで描画され、 <xref:System.Drawing.Color.Crimson%2A> 埋め込み四角形はコントロールのプロパティと同じ色で描画され <xref:System.Windows.Forms.DataGridView> <xref:System.Windows.Forms.DataGridView.GridColor%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="99e8a-108">Each cell's text content is painted in <xref:System.Drawing.Color.Crimson%2A>, and an inset rectangle is drawn in the same color as the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.GridColor%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99e8a-109">例</span><span class="sxs-lookup"><span data-stu-id="99e8a-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="99e8a-110">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="99e8a-110">Compiling the Code</span></span>  
 <span data-ttu-id="99e8a-111">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="99e8a-111">This example requires:</span></span>  
  
- <span data-ttu-id="99e8a-112"><xref:System.Windows.Forms.DataGridView> `dataGridView1` `ContactName` Northwind サンプルデータベースの Customers テーブル内の列などの列を持つという名前のコントロール。</span><span class="sxs-lookup"><span data-stu-id="99e8a-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` with a `ContactName` column such as the one in the Customers table in the Northwind sample database.</span></span>  
  
- <span data-ttu-id="99e8a-113">System、System.Windows.Forms、および System.Drawing の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="99e8a-113">References to the System, System.Windows.Forms, and System.Drawing assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99e8a-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="99e8a-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellPainting>
- [<span data-ttu-id="99e8a-115">Windows フォーム DataGridView コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="99e8a-115">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
