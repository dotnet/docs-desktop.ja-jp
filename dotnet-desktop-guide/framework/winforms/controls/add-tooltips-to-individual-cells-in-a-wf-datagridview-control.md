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
# <a name="how-to-add-tooltips-to-individual-cells-in-a-windows-forms-datagridview-control"></a>方法: Windows フォーム DataGridView コントロールの各セルにツールヒントを追加する
既定では、ツールヒントは、 <xref:System.Windows.Forms.DataGridView> コンテンツ全体を表示するには小さすぎるセルの値を表示するために使用されます。 ただし、この動作をオーバーライドして、個々のセルにツールヒントテキストの値を設定することもできます。 これは、セルに関する追加情報をユーザーに表示したり、セルの内容に関する別の説明をユーザーに提供したりする場合に便利です。 たとえば、状態アイコンを表示する行がある場合、ヒントを使用してテキストの説明を入力することができます。  
  
 また、プロパティをに設定することによって、セルレベルのツールヒントの表示を無効にすることもでき <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType> `false` ます。  
  
### <a name="to-add-a-tooltip-to-a-cell"></a>ヒントをセルに追加するには  
  
- <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType> プロパティを設定します。  
  
     [!code-cpp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/cpp/datagridviewcell.tooltiptext.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/CS/datagridviewcell.tooltiptext.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/VB/datagridviewcell.tooltiptext.vb#1)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
  
- この例で必要な要素は次のとおりです。  
  
- という名前のコントロール。このコントロールには、 <xref:System.Windows.Forms.DataGridView> `dataGridView1` `Rating` 1 ~ 4 個のアスタリスク ("*") 記号の文字列値を表示するためのという名前の列があります。 <xref:System.Windows.Forms.DataGridView.CellFormatting>コントロールのイベントは、例に示すイベントハンドラーメソッドに関連付けられている必要があります。  
  
- <xref:System?displayProperty=nameWithType> アセンブリおよび <xref:System.Windows.Forms?displayProperty=nameWithType> アセンブリへの参照。  
  
## <a name="robust-programming"></a>信頼性の高いプログラミング  
 <xref:System.Windows.Forms.DataGridView>コントロールを外部データソースにバインドしたり、仮想モードを実装して独自のデータソースを提供したりすると、パフォーマンスの問題が発生する可能性があります。 大量のデータを処理するときにパフォーマンスが低下しないようにするには、 <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> 複数のセルのプロパティを設定するのではなく、イベントを処理します。 このイベントを処理するときに、セルプロパティの値を取得する <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> と、イベントが発生し、 <xref:System.Windows.Forms.DataGridViewCellToolTipTextNeededEventArgs.ToolTipText%2A?displayProperty=nameWithType> イベントハンドラーに指定されたプロパティの値が返されます。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCell>
- <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType>
- [Windows フォーム DataGridView コントロールのセル、行、および列を使用したプログラミング](programming-with-cells-rows-and-columns-in-the-datagrid.md)
