---
title: DataGridView コントロールのカスタマイズ
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], customization
- DataGridView control [Windows Forms], customization
ms.assetid: 01ea5d4c-a736-4596-b0e9-a67a1b86e15f
ms.openlocfilehash: 348c78d091679418f2452326555d49229bd2a8ea
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974240"
---
# <a name="customizing-the-windows-forms-datagridview-control"></a>Windows フォーム DataGridView コントロールのカスタマイズ
`DataGridView`コントロールには、セル、行、および列の外観と基本動作 (ルックアンドフィール) を調整するために使用できるいくつかのプロパティが用意されています。 ただし、クラスの機能を超える特別なニーズがある場合 <xref:System.Windows.Forms.DataGridViewCellStyle> は、コントロールのオーナー描画を実装したり、カスタムセル、列、および行を作成してその機能を拡張したりすることもできます。  
  
 セルと行を自分で描画するには、さまざまな `DataGridView` 描画イベントを処理します。 既存の機能を変更したり、新しい機能を提供したりするには、既存の型、型、および型から派生した独自の型を作成でき `DataGridViewCell` `DataGridViewColumn` `DataGridViewRow` ます。 また、セルが編集モードのときに選択したコントロールを表示する派生型を作成することによって、新しい編集機能を提供することもできます。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [方法 : Windows フォームの DataGridView コントロールのセルの外観をカスタマイズする](customize-the-appearance-of-cells-in-the-datagrid.md)  
 <xref:System.Windows.Forms.DataGridView.CellPainting>セルを手動で描画するためにイベントを処理する方法について説明します。  
  
 [方法: Windows フォームの DataGridView コントロールの行の外観をカスタマイズする](customize-the-appearance-of-rows-in-the-datagrid.md)  
 <xref:System.Windows.Forms.DataGridView.RowPrePaint> <xref:System.Windows.Forms.DataGridView.RowPostPaint> カスタム、グラデーションの背景、および複数の列にまたがるコンテンツを使用して行を描画するために、イベントとイベントを処理する方法について説明します。  
  
 [方法: Windows フォーム DataGridView コントロールのセルと列を、それぞれの動作と外観を拡張してカスタマイズする](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)  
 およびから派生したカスタム型を作成して `DataGridViewCell` `DataGridViewColumn` 、マウスポインターがセル上にあるときにセルを強調表示する方法について説明します。  
  
 [方法: Windows フォーム DataGridView コントロールのボタン列にあるボタンを無効にする](disable-buttons-in-a-button-column-in-the-datagrid.md)  
 <xref:System.Windows.Forms.DataGridViewButtonCell> <xref:System.Windows.Forms.DataGridViewButtonColumn> ボタン列に無効なボタンを表示するために、およびから派生したカスタム型を作成する方法について説明します。  
  
 [方法: Windows フォーム DataGridView Cells でコントロールをホストする](how-to-host-controls-in-windows-forms-datagridview-cells.md)  
 `IDataGridViewEditingControl` `DataGridViewCell` `DataGridViewColumn` <xref:System.Windows.Forms.DateTimePicker> セルが編集モードのときにコントロールを表示するために、インターフェイスを実装し、とから派生したカスタム型を作成する方法について説明します。  
  
## <a name="reference"></a>リファレンス  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView> コントロールのリファレンス ドキュメントを提供します。  
  
 <xref:System.Windows.Forms.DataGridViewCell>  
 クラスのリファレンスドキュメントを提供 <xref:System.Windows.Forms.DataGridViewCell> します。  
  
 <xref:System.Windows.Forms.DataGridViewRow>  
 クラスのリファレンスドキュメントを提供 <xref:System.Windows.Forms.DataGridViewRow> します。  
  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 クラスのリファレンスドキュメントを提供 <xref:System.Windows.Forms.DataGridViewColumn> します。  
  
 <xref:System.Windows.Forms.IDataGridViewEditingControl>  
 インターフェイスのリファレンスドキュメントを提供 <xref:System.Windows.Forms.IDataGridViewEditingControl> します。  
  
## <a name="related-sections"></a>関連項目  
 [Windows フォームの DataGridView コントロールの基本的な書式設定およびスタイル設定](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 コントロールの基本の外観およびセル データの書式設定を変更する方法を説明するトピックを示します。  
  
## <a name="see-also"></a>関連項目

- [DataGridView コントロール](datagridview-control-windows-forms.md)
- [Windows フォーム DataGridView コントロールの列型](column-types-in-the-windows-forms-datagridview-control.md)
