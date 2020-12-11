---
title: 行テンプレートを使用して DataGridView コントロールの行をカスタマイズする
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], customizing rows
- DataGridView control [Windows Forms], customizing rows
ms.assetid: 6db61607-7e57-4a84-8d63-9d6a7ed7f9ff
ms.openlocfilehash: 35cb95f22c0caa654bf149b5fc4fd0395696a411
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982776"
---
# <a name="how-to-use-the-row-template-to-customize-rows-in-the-windows-forms-datagridview-control"></a>方法: 行テンプレートを使用して Windows フォーム DataGridView コントロールの行をカスタマイズする
コントロールは、 <xref:System.Windows.Forms.DataGridView> データバインディングを使用してコントロールに追加するすべての行の基礎として、または <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> 使用する既存の行を指定せずにメソッドを呼び出すと、行テンプレートを使用します。  
  
 行テンプレートを使用すると、プロパティよりも行の外観と動作をより細かく制御でき <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> ます。 行テンプレートを使用して、などの <xref:System.Windows.Forms.DataGridViewRow> プロパティを設定でき <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A> ます。  
  
 場合によっては、行テンプレートを使用して特定の効果を実現する必要があります。 たとえば、行の高さ情報をに格納することはできません <xref:System.Windows.Forms.DataGridViewCellStyle> 。そのため、行テンプレートを使用して、すべての行で使用される既定の高さを変更する必要があります。 行テンプレートは、から派生した独自のクラスを作成 <xref:System.Windows.Forms.DataGridViewRow> し、新しい行がコントロールに追加されたときにカスタム型を使用する場合にも役立ちます。  
  
> [!NOTE]
> 行テンプレートは、行が追加された場合にのみ使用されます。 行テンプレートを変更して既存の行を変更することはできません。  
  
### <a name="to-use-the-row-template"></a>行テンプレートを使用するには  
  
- プロパティから取得したオブジェクトのプロパティを設定 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> します。  
  
     [!code-cpp[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CPP/datagridviewrowtemplate.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CS/datagridviewrowtemplate.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/VB/datagridviewrowtemplate.vb#1)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 この例で必要な要素は次のとおりです。  
  
- `dataGridView1` という名前の <xref:System.Windows.Forms.DataGridView> コントロール。  
  
- <xref:System?displayProperty=nameWithType>、<xref:System.Drawing?displayProperty=nameWithType>、および <xref:System.Windows.Forms?displayProperty=nameWithType> の各アセンブリへの参照。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridViewRow>
- <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType>
- [Windows フォームの DataGridView コントロールの基本的な書式設定およびスタイル設定](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [Windows フォーム DataGridView コントロールでのセルのスタイル](cell-styles-in-the-windows-forms-datagridview-control.md)
