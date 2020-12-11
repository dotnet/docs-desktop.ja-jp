---
title: DataGridView コントロールのセルに画像を表示する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], displaying images
- data grids [Windows Forms], displaying in grids
- DataGridView control [Windows Forms], displaying images
- data grids [Windows Forms], displaying images in cells
ms.assetid: 53b13d31-1b56-476d-9ab4-18bfac138a22
ms.openlocfilehash: e0e125c816877875b80e0f20887d9beee443577a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980836"
---
# <a name="how-to-display-images-in-cells-of-the-windows-forms-datagridview-control"></a>方法: Windows フォーム DataGridView コントロールのセルにイメージを表示する
画像またはグラフィックは、データ行に表示できる値の1つです。 多くの場合、これらのグラフィックは従業員の写真または会社のロゴの形になります。  
  
 画像の組み込みは、コントロール内にデータを表示するときに簡単に行うことができ <xref:System.Windows.Forms.DataGridView> ます。 コントロールは、 <xref:System.Windows.Forms.DataGridView> クラスでサポートされているすべてのイメージ形式に <xref:System.Drawing.Image> 加え、一部のデータベースで使用される OLE ピクチャ形式をネイティブで処理します。  
  
 <xref:System.Windows.Forms.DataGridView>コントロールのデータソースに画像の列がある場合、コントロールによって自動的に表示され <xref:System.Windows.Forms.DataGridView> ます。  
  
 次のコード例では、埋め込みリソースからアイコンを抽出し、イメージ列のすべてのセルに表示するビットマップに変換する方法を示します。 テキストのセル値を対応する画像に置き換える別の例については、「 [方法: Windows フォーム DataGridView コントロールでデータの書式をカスタマイズ](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)する」を参照してください。  
  
## <a name="example"></a>例  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#050](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#050)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#050](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#050)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 この例で必要な要素は次のとおりです。  
  
- `dataGridView1` という名前の <xref:System.Windows.Forms.DataGridView> コントロール。  
  
- という名前の埋め込みアイコンリソース `tree.ico` 。  
  
- <xref:System?displayProperty=nameWithType>、<xref:System.Windows.Forms?displayProperty=nameWithType>、および <xref:System.Drawing?displayProperty=nameWithType> の各アセンブリへの参照。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.DataGridView>
- [Windows フォーム DataGridView コントロールでの列、行、およびセルの基本機能](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [方法: Windows フォーム DataGridView コントロールのデータの書式設定をカスタマイズする](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
