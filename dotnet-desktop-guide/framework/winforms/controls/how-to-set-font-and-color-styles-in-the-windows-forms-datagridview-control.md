---
title: DataGridView コントロールのフォントと色のスタイルを設定する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], cell customization
- data grids [Windows Forms], customizing cells
- data grids [Windows Forms], font styles
- data grids [Windows Forms], color styles
ms.assetid: 588f2c57-d963-41b1-9c1d-d02d71818113
ms.openlocfilehash: f1ee9131cfc0b28a5f6263dcd6254d27a092cc62
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980695"
---
# <a name="how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control"></a>方法: Windows フォーム DataGridView コントロールのフォントと色のスタイルを設定する
<xref:System.Windows.Forms.DataGridViewCellStyle> クラスのプロパティを設定して、<xref:System.Windows.Forms.DataGridView> コントロール内のセルの外観を指定できます。 <xref:System.Windows.Forms.DataGridView> クラスとコンパニオン クラスのさまざまなプロパティからこのクラスのインスタンスを取得することも、これらのプロパティの割り当てに <xref:System.Windows.Forms.DataGridViewCellStyle> オブジェクトをインスタンス化することもできます。  
  
 次の手順は、<xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> プロパティを使用したセルの外観の基本的なカスタマイズを示します。 コントロール内のすべてのセルは、列、行、またはセル レベルでオーバーライドされるのでない限り、このプロパティで指定されたスタイルを継承します。 スタイルの継承の例については、「 [方法: Windows フォーム DataGridView コントロールの既定のセルスタイルを設定する](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)」を参照してください。 <xref:System.Windows.Forms.DataGridViewCellStyle> クラスのその他の使用方法については、[参照] セクションの各トピックを参照してください。  
  
 Visual Studio では、このタスクに対する広範なサポートが用意されています。  「 [方法: デザイナーを使用して Windows フォーム DataGridView コントロールの既定のセルスタイルとデータ形式を設定する](default-cell-styles-datagridview.md)」も参照してください。  
  
### <a name="to-specify-the-font-used-by-datagridview-cells"></a>DataGridView セルで使用されるフォントを指定するには  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle> の <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> プロパティを設定します。 次のコード例では、コントロール全体のフォントを設定する <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> プロパティを使用します。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#101](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#101)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#101](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#101)]  
  
### <a name="to-specify-the-foreground-and-background-colors-of-datagridview-cells"></a>DataGridView セルの前景色と背景色を指定するには  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle> の <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> プロパティと <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A> プロパティを設定します。 次のコード例では、コントロール全体にこれらのスタイルを設定する <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> プロパティを使用します。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#102](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#102)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#102](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#102)]  
  
### <a name="to-specify-the-foreground-and-background-colors-of-selected-datagridview-cells"></a>選択された DataGridView セルの前景色と背景色を指定するには  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle> の <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionForeColor%2A> プロパティと <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionBackColor%2A> プロパティを設定します。 次のコード例では、コントロール全体にこれらのスタイルを設定する <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> プロパティを使用します。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#103](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#103)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#103](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#103)]  
  
## <a name="example"></a>例  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#100)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#100)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 この例で必要な要素は次のとおりです。  
  
- `dataGridView1` という名前の <xref:System.Windows.Forms.DataGridView> コントロール。  
  
- <xref:System?displayProperty=nameWithType>、<xref:System.Drawing?displayProperty=nameWithType>、および <xref:System.Windows.Forms?displayProperty=nameWithType> の各アセンブリへの参照。  
  
## <a name="robust-programming"></a>信頼性の高いプログラミング  
 最大限のスケーラビリティを実現するには、各要素のスタイルのプロパティを個別に設定するのではなく、同じスタイルを使用する複数の行、列、またはセルで <xref:System.Windows.Forms.DataGridViewCellStyle> オブジェクトを共有してください。 詳細については、「 [Windows フォーム DataGridView コントロールを拡張するための推奨される手順](best-practices-for-scaling-the-windows-forms-datagridview-control.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [Windows フォームの DataGridView コントロールの基本的な書式設定およびスタイル設定](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [Windows フォーム DataGridView コントロールでのセルのスタイル](cell-styles-in-the-windows-forms-datagridview-control.md)
