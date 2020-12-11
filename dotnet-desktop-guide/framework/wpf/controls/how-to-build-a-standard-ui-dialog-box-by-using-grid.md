---
title: '方法: グリッドを使用して標準 UI ダイアログ ボックスをビルドする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], creating
- Grid control [WPF], creating [WPF], dialog box
ms.assetid: d6ac3d51-844b-4d29-96d8-81a696a7b960
ms.openlocfilehash: 442d69f891d53365653c01ef4dca296398ae7195
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985703"
---
# <a name="how-to-build-a-standard-ui-dialog-box-by-using-grid"></a><span data-ttu-id="15ce2-102">方法: グリッドを使用して標準 UI ダイアログ ボックスをビルドする</span><span class="sxs-lookup"><span data-stu-id="15ce2-102">How to: Build a Standard UI Dialog Box by Using Grid</span></span>
<span data-ttu-id="15ce2-103">この例では、<xref:System.Windows.Controls.Grid> 要素を使用して、標準 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] ダイアログ ボックスを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="15ce2-103">This example shows how to create a standard [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] dialog box by using the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15ce2-104">例</span><span class="sxs-lookup"><span data-stu-id="15ce2-104">Example</span></span>  
 <span data-ttu-id="15ce2-105">次の例では、Windows オペレーティング システムの **[実行]** ダイアログ ボックスのようなダイアログ ボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="15ce2-105">The following example creates a dialog box like the **Run** dialog box in the Windows operating system.</span></span>  
  
 <span data-ttu-id="15ce2-106">この例では、<xref:System.Windows.Controls.Grid> を作成し、<xref:System.Windows.Controls.ColumnDefinition> クラスと <xref:System.Windows.Controls.RowDefinition> クラスを使用して、5 つの列と 4 つの行を定義します。</span><span class="sxs-lookup"><span data-stu-id="15ce2-106">The example creates a <xref:System.Windows.Controls.Grid> and uses the <xref:System.Windows.Controls.ColumnDefinition> and <xref:System.Windows.Controls.RowDefinition> classes to define five columns and four rows.</span></span>  
  
 <span data-ttu-id="15ce2-107">次に、この例では、ダイアログ ボックスにあるイメージを表すために、<xref:System.Windows.Controls.Image>、`RunIcon.png` を追加して配置します。</span><span class="sxs-lookup"><span data-stu-id="15ce2-107">The example then adds and positions an <xref:System.Windows.Controls.Image>, `RunIcon.png`, to represent the image that is found in the dialog box.</span></span> <span data-ttu-id="15ce2-108">イメージは、<xref:System.Windows.Controls.Grid> の最初の列と行 (左上隅) に配置されます。</span><span class="sxs-lookup"><span data-stu-id="15ce2-108">The image is placed in the first column and row of the <xref:System.Windows.Controls.Grid> (the upper-left corner).</span></span>  
  
 <span data-ttu-id="15ce2-109">次に、この例では、最初の行の残りの列にまたがる <xref:System.Windows.Controls.TextBlock> 要素を最初の列に追加します。</span><span class="sxs-lookup"><span data-stu-id="15ce2-109">Next, the example adds a <xref:System.Windows.Controls.TextBlock> element to the first column, which spans the remaining columns of the first row.</span></span> <span data-ttu-id="15ce2-110">最初の列の 2 番目の行に別の <xref:System.Windows.Controls.TextBlock> 要素が追加されて、 **[開く]** テキスト ボックスが表されます。</span><span class="sxs-lookup"><span data-stu-id="15ce2-110">It adds another <xref:System.Windows.Controls.TextBlock> element to the second row in the first column, to represent the **Open** text box.</span></span> <span data-ttu-id="15ce2-111"><xref:System.Windows.Controls.TextBlock> が続き、データ入力領域が表されます。</span><span class="sxs-lookup"><span data-stu-id="15ce2-111">A <xref:System.Windows.Controls.TextBlock> follows, which represents the data entry area.</span></span>  
  
 <span data-ttu-id="15ce2-112">最後に、この例では、最後の行に 3 つの <xref:System.Windows.Controls.Button> 要素を追加します。これにより、**OK** イベント、**キャンセル** イベント、**参照** イベントが表されます。</span><span class="sxs-lookup"><span data-stu-id="15ce2-112">Finally, the example adds three <xref:System.Windows.Controls.Button> elements to the final row, which represent the **OK**, **Cancel**, and **Browse** events.</span></span>  
  
 [!code-csharp[GridRunDialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="15ce2-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="15ce2-113">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.GridUnitType>
- [<span data-ttu-id="15ce2-114">パネルの概要</span><span class="sxs-lookup"><span data-stu-id="15ce2-114">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="15ce2-115">方法トピック</span><span class="sxs-lookup"><span data-stu-id="15ce2-115">How-to Topics</span></span>](grid-how-to-topics.md)
