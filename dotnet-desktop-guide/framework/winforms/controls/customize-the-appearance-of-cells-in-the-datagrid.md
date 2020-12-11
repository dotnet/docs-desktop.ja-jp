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
# <a name="how-to-customize-the-appearance-of-cells-in-the-windows-forms-datagridview-control"></a>方法 : Windows フォームの DataGridView コントロールのセルの外観をカスタマイズする
コントロールのイベントを処理することで、任意のセルの外観をカスタマイズでき <xref:System.Windows.Forms.DataGridView> <xref:System.Windows.Forms.DataGridView.CellPainting> ます。 <xref:System.Windows.Forms.DataGridView>コントロールのは <xref:System.Drawing.Graphics> 、のプロパティから抽出でき <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> ます。 これにより、 <xref:System.Drawing.Graphics> コントロール全体の外観に影響を与えることができ <xref:System.Windows.Forms.DataGridView> ますが、通常は、現在描画されているセルの外観のみに影響を与えます。 <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A>のプロパティを <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> 使用すると、描画操作を、現在描画されているセルに制限できます。  
  
 次のコード例では、 `ContactName` コントロールの配色を使用して、列のすべてのセルを塗りつぶし <xref:System.Windows.Forms.DataGridView> ます。 各セルのテキストコンテンツはで描画され、 <xref:System.Drawing.Color.Crimson%2A> 埋め込み四角形はコントロールのプロパティと同じ色で描画され <xref:System.Windows.Forms.DataGridView> <xref:System.Windows.Forms.DataGridView.GridColor%2A> ます。  
  
## <a name="example"></a>例  
 [!code-csharp[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 この例で必要な要素は次のとおりです。  
  
- <xref:System.Windows.Forms.DataGridView> `dataGridView1` `ContactName` Northwind サンプルデータベースの Customers テーブル内の列などの列を持つという名前のコントロール。  
  
- System、System.Windows.Forms、および System.Drawing の各アセンブリへの参照。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellPainting>
- [Windows フォーム DataGridView コントロールのカスタマイズ](customizing-the-windows-forms-datagridview-control.md)
