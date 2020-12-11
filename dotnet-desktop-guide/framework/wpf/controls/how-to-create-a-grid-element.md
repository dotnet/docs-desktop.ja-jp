---
title: '方法: グリッド要素を作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], creating [WPF], grid instance
ms.assetid: b2f07626-9df8-43b8-8d36-492f3cb42837
ms.openlocfilehash: c87ca1d6642bd18fa85806c92caab049d259d45e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985659"
---
# <a name="how-to-create-a-grid-element"></a><span data-ttu-id="dbd5e-102">方法: グリッド要素を作成する</span><span class="sxs-lookup"><span data-stu-id="dbd5e-102">How to: Create a Grid Element</span></span>
## <a name="example"></a><span data-ttu-id="dbd5e-103">例</span><span class="sxs-lookup"><span data-stu-id="dbd5e-103">Example</span></span>  
 <span data-ttu-id="dbd5e-104">次の例では、[!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] またはコードを使用して <xref:System.Windows.Controls.Grid> のインスタンスを作成して使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="dbd5e-104">The following example shows how to create and use an instance of <xref:System.Windows.Controls.Grid> by using either [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] or code.</span></span> <span data-ttu-id="dbd5e-105">この例では、3 つの <xref:System.Windows.Controls.ColumnDefinition> オブジェクトと 3 つの <xref:System.Windows.Controls.RowDefinition> オブジェクトを使用して、ワークシートなどで 9 つのセルが含まれるグリッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="dbd5e-105">This example uses three <xref:System.Windows.Controls.ColumnDefinition> objects and three <xref:System.Windows.Controls.RowDefinition> objects to create a grid that has nine cells, such as in a worksheet.</span></span> <span data-ttu-id="dbd5e-106">各セルには、データを表す <xref:System.Windows.Controls.TextBlock> 要素が含まれています。一番上の行には、<xref:System.Windows.Controls.Grid.ColumnSpan%2A> プロパティが適用された <xref:System.Windows.Controls.TextBlock> が含まれています。</span><span class="sxs-lookup"><span data-stu-id="dbd5e-106">Each cell contains a <xref:System.Windows.Controls.TextBlock> element that represents data, and the top row contains a <xref:System.Windows.Controls.TextBlock> with the <xref:System.Windows.Controls.Grid.ColumnSpan%2A> property applied.</span></span> <span data-ttu-id="dbd5e-107">各セルの境界を表示するには、<xref:System.Windows.Controls.Grid.ShowGridLines%2A> プロパティを有効にします。</span><span class="sxs-lookup"><span data-stu-id="dbd5e-107">To show the boundaries of each cell, the <xref:System.Windows.Controls.Grid.ShowGridLines%2A> property is enabled.</span></span>  
  
 [!code-csharp[Grid#3](~/samples/snippets/csharp/VS_Snippets_Wpf/Grid/CSharp/Grid_Code.cs#3)]
 [!code-vb[Grid#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Grid/VisualBasic/grid_vb.vb#3)]
 [!code-xaml[Grid#3](~/samples/snippets/xaml/VS_Snippets_Wpf/Grid/XAML/default.xaml#3)]  
  
  <span data-ttu-id="dbd5e-108">どちらの方法でも、次のようにまったく同じ外観のユーザー インターフェイスが生成されます。</span><span class="sxs-lookup"><span data-stu-id="dbd5e-108">Either approach will generate a user interface that looks much the same, like the one below.</span></span>

  ![スクリーンショットは、3 つの列に分割されたグリッドを含む WPF ユーザー インターフェイスを示しています。](././media/how-to-create-a-grid-element/how-to-create-a-grid-element.png)
## <a name="see-also"></a><span data-ttu-id="dbd5e-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="dbd5e-112">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- [<span data-ttu-id="dbd5e-113">パネルの概要</span><span class="sxs-lookup"><span data-stu-id="dbd5e-113">Panels Overview</span></span>](panels-overview.md)
