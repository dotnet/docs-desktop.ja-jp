---
title: DataGridView コントロールの基本的な書式設定とスタイル設定
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting and styling
- data grids [Windows Forms], formatting
ms.assetid: b9b90836-1f56-4aa9-8db8-edc78fe830e8
ms.openlocfilehash: d295718b7bd4f3bc4c5f63b6e6cb911f733525fe
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96975145"
---
# <a name="basic-formatting-and-styling-in-the-windows-forms-datagridview-control"></a>Windows フォームの DataGridView コントロールの基本的な書式設定およびスタイル設定
`DataGridView`コントロールを使用すると、セルの基本的な外観と、セル値の表示形式を簡単に定義できます。 さまざまなコントロールプロパティを使用してアクセスするオブジェクトのプロパティを設定することによって、個々のセル、特定の列や行のセル、またはコントロール内のすべてのセルの外観と書式設定スタイルを定義でき `DataGridViewCellStyle` `DataGridView` ます。 また、イベントを処理することによって、セルの値などの要因に基づいて、これらのスタイルを動的に変更することもでき `CellFormatting` ます。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [方法: Windows フォーム DataGridView コントロールの境界線とグリッド線のスタイルを変更する](change-the-border-and-gridline-styles-in-the-datagrid.md)  
 `DataGridView`コントロールの境界線とセル間の境界線の外観を定義するプロパティを設定する方法について説明します。  
  
 [Windows フォーム DataGridView コントロールでのセルのスタイル](cell-styles-in-the-windows-forms-datagridview-control.md)  
 `DataGridViewCellStyle`クラスと、その型のプロパティがコントロールでのセルの表示方法を定義する方法について説明します。  
  
 [方法: Windows フォーム DataGridView コントロールの既定のセル スタイルを設定する](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)  
 プロパティを使用して、 `DataGridViewCellStyle` 特定の行と列、およびコントロール全体のセルの既定の外観を定義する方法について説明します。  
  
 [方法: Windows フォーム DataGridView コントロールのデータの書式を設定する](how-to-format-data-in-the-windows-forms-datagridview-control.md)  
 プロパティを使用してセルの表示値の書式を設定する方法について説明し `DataGridViewCellStyle` ます。  
  
 [方法: Windows フォーム DataGridView コントロールのフォントと色のスタイルを設定する](how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)  
 プロパティを使用して `DefaultCellStyle` 、コントロールのすべてのセルの基本的な表示特性を設定する方法について説明します。  
  
 [方法: Windows フォーム DataGridView コントロールに交互の行のスタイルを設定する](how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control.md)  
 別の行で表示される行を交互に使用して、コントロールに元帳に似た効果を作成する方法について説明します。  
  
 [方法: 行テンプレートを使用して Windows フォーム DataGridView コントロールの行をカスタマイズする](use-the-row-template-to-customize-rows-in-the-datagrid.md)  
 プロパティを使用して `RowTemplate` 、コントロールのすべての行に使用される行のプロパティを設定する方法について説明します。  
  
## <a name="reference"></a>リファレンス  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView> コントロールのリファレンス ドキュメントを提供します。  
  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 クラスのリファレンスドキュメントを提供 <xref:System.Windows.Forms.DataGridViewCellStyle> します。  
  
 <xref:System.Windows.Forms.DataGridView.CellFormatting>  
 イベントのリファレンスドキュメントを提供 <xref:System.Windows.Forms.DataGridView.CellFormatting> します。  
  
 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>  
 プロパティに関するリファレンスドキュメントを提供 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> します。  
  
## <a name="related-sections"></a>関連項目  
 [Windows フォーム DataGridView コントロールのカスタマイズ](customizing-the-windows-forms-datagridview-control.md)  
 <xref:System.Windows.Forms.DataGridView> のセルおよび行のカスタム描画と、セル、列、および行の派生型の作成について説明するトピックを示します。  
  
 [Windows フォーム DataGridView コントロールでの列、行、およびセルの基本機能](basic-column-row-and-cell-features-wf-datagridview-control.md)  
 一般的に使用されるセル、行、および列のプロパティについて説明するトピックを示します。  
  
## <a name="see-also"></a>関連項目

- [DataGridView コントロール](datagridview-control-windows-forms.md)
