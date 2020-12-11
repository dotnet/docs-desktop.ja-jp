---
title: DataGridView コントロールでの列の Read-Only の作成
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], read-only columns
- DataGridView control [Windows Forms], read-only columns
ms.assetid: 2bb73ebb-1a55-4362-9fda-e50574c087d5
ms.openlocfilehash: 11d008d47ec5edb594d3d862c68ff3b9920e0e25
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974821"
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control"></a>方法: Windows フォームの DataGridView コントロールで列を読み取り専用にする
すべてのデータが編集できるわけではありません。 <xref:System.Windows.Forms.DataGridView> コントロールでは、列の <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> プロパティの値はユーザーがその列のセルを編集できるかどうかを決定します。 コントロールを完全に読み取り専用にする方法については、「 [方法: Windows フォーム DataGridView コントロールで行の追加と削除を回避](prevent-row-addition-and-deletion-datagridview.md)する」を参照してください。  
  
 Visual Studio では、このタスクに対するサポートが用意されています。  「 [方法: デザイナーを使用して Windows フォーム DataGridView コントロールで列を Read-Only する](make-columns-read-only-in-the-datagrid-using-the-designer.md)」も参照してください。  
  
### <a name="to-make-a-column-read-only-programmatically"></a>プログラムで列を読み取り専用にするには  
  
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType> プロパティを `true`に設定します。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#064](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#064)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#064](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#064)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 この例で必要な要素は次のとおりです。  
  
- `CompanyName` という名前の列を持つ `dataGridView1` という名前の <xref:System.Windows.Forms.DataGridView> コントロール。  
  
- <xref:System?displayProperty=nameWithType> アセンブリおよび <xref:System.Windows.Forms?displayProperty=nameWithType> アセンブリへの参照。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- [Windows フォーム DataGridView コントロールでの列、行、およびセルの基本機能](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [方法: Windows フォーム DataGridView コントロールで行が追加および削除されないようにする](prevent-row-addition-and-deletion-datagridview.md)
