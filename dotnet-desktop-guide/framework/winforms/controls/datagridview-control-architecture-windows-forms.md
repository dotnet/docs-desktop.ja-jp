---
title: DataGridView コントロールのアーキテクチャ
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], architecture
ms.assetid: 1c6cabf0-02ee-4bbc-9574-b54bb7f5b19e
ms.openlocfilehash: 2e1884383cca87f8d4ff84f486e2b29761a0c55d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974223"
---
# <a name="datagridview-control-architecture-windows-forms"></a>DataGridView コントロールのアーキテクチャ (Windows フォーム)
<xref:System.Windows.Forms.DataGridView>コントロールとその関連クラスは、表形式データを表示および編集するための柔軟で拡張可能なシステムとして設計されています。 これらのクラスはすべて、名前空間に含まれ <xref:System.Windows.Forms?displayProperty=nameWithType> ており、すべて "DataGridView" プレフィックスで名前が付けられています。  
  
## <a name="architecture-elements"></a>アーキテクチャの要素  
 プライマリ <xref:System.Windows.Forms.DataGridView> コンパニオンクラスは、から派生 <xref:System.Windows.Forms.DataGridViewElement> します。 次のオブジェクトモデルは、継承階層を示してい <xref:System.Windows.Forms.DataGridViewElement> ます。  
  
 ![DataGridViewElement オブジェクトモデル階層を示す図。](./media/datagridview-control-architecture-windows-forms/datagridviewelement-object-model.gif)  
  
 クラスは、 <xref:System.Windows.Forms.DataGridViewElement> 親コントロールへの参照を提供 <xref:System.Windows.Forms.DataGridView> し、プロパティを持ち <xref:System.Windows.Forms.DataGridViewElement.State%2A> ます。このプロパティには、列挙体の値の組み合わせを表す値が格納され <xref:System.Windows.Forms.DataGridViewElementStates> ます。  
  
 以下のセクションでは、関連するクラスについて詳しく説明し <xref:System.Windows.Forms.DataGridView> ます。  
  
### <a name="datagridviewelementstates"></a>DataGridViewElementStates  
 <xref:System.Windows.Forms.DataGridViewElementStates> 列挙体には次の値が含まれます。  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.None>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.ReadOnly>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Resizable>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.ResizableSet>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Selected>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Visible>  
  
 この列挙体の値はビットごとの論理演算子と組み合わせることができるため、 <xref:System.Windows.Forms.DataGridViewElement.State%2A> プロパティは一度に複数の状態を表すことができます。 たとえば、は <xref:System.Windows.Forms.DataGridViewElement> 同時に、、およびにすることができ <xref:System.Windows.Forms.DataGridViewElementStates.Frozen> <xref:System.Windows.Forms.DataGridViewElementStates.Selected> <xref:System.Windows.Forms.DataGridViewElementStates.Visible> ます。  
  
### <a name="cells-and-bands"></a>セルとバンド  
 コントロールは、 <xref:System.Windows.Forms.DataGridView> セルとバンドの2つの基本的な種類のオブジェクトで構成されています。 すべてのセルは、 <xref:System.Windows.Forms.DataGridViewCell> 基本クラスから派生します。 2種類のバンド ( <xref:System.Windows.Forms.DataGridViewColumn> と) は、 <xref:System.Windows.Forms.DataGridViewRow> どちらも基本クラスから派生し <xref:System.Windows.Forms.DataGridViewBand> ます。  
  
 <xref:System.Windows.Forms.DataGridView>コントロールは複数のクラスと相互運用しますが、最も一般的に発生するのは、、、 <xref:System.Windows.Forms.DataGridViewCell> <xref:System.Windows.Forms.DataGridViewColumn> <xref:System.Windows.Forms.DataGridViewRow> です。  
  
### <a name="datagridviewcell"></a>DataGridViewCell  
 セルは、の相互作用の基本単位です <xref:System.Windows.Forms.DataGridView> 。 表示はセルの中央に配置され、多くの場合、データ入力はセルを通じて実行されます。 クラスのコレクションを使用してセルにアクセスでき <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> <xref:System.Windows.Forms.DataGridViewRow> ます。また、コントロールのコレクションを使用して、選択したセルにアクセスでき <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> <xref:System.Windows.Forms.DataGridView> ます。 次のオブジェクトモデルは、この使用方法を示し、継承階層を示してい <xref:System.Windows.Forms.DataGridViewCell> ます。  
  
 ![DataGridViewCell オブジェクトモデル階層を示す図。](./media/datagridview-control-architecture-windows-forms/datagridviewcell-object-model.gif)  
  
 この <xref:System.Windows.Forms.DataGridViewCell> 型は、すべてのセル型の派生元である抽象基本クラスです。 <xref:System.Windows.Forms.DataGridViewCell> とその派生型は Windows フォームコントロールではなく、一部のホスト Windows フォームコントロールです。 セルでサポートされる編集機能は、通常、ホストされるコントロールによって処理されます。  
  
 <xref:System.Windows.Forms.DataGridViewCell> オブジェクトは、Windows フォームコントロールと同じように、独自の外観および描画機能を制御しません。 代わりに、は <xref:System.Windows.Forms.DataGridView> オブジェクトの外観を担い <xref:System.Windows.Forms.DataGridViewCell> ます。 コントロールのプロパティとイベントを操作することによって、セルの外観と動作に大きな影響を与えることができ <xref:System.Windows.Forms.DataGridView> ます。 コントロールの機能を超えるカスタマイズに特別な要件がある場合 <xref:System.Windows.Forms.DataGridView> <xref:System.Windows.Forms.DataGridViewCell> は、またはその子クラスの1つから派生する独自のクラスを実装できます。  
  
 から派生したクラスを次に示し <xref:System.Windows.Forms.DataGridViewCell> ます。  
  
- <xref:System.Windows.Forms.DataGridViewTextBoxCell>  
  
- <xref:System.Windows.Forms.DataGridViewButtonCell>  
  
- <xref:System.Windows.Forms.DataGridViewLinkCell>  
  
- <xref:System.Windows.Forms.DataGridViewCheckBoxCell>  
  
- <xref:System.Windows.Forms.DataGridViewComboBoxCell>  
  
- <xref:System.Windows.Forms.DataGridViewImageCell>  
  
- <xref:System.Windows.Forms.DataGridViewHeaderCell>  
  
- <xref:System.Windows.Forms.DataGridViewRowHeaderCell>  
  
- <xref:System.Windows.Forms.DataGridViewColumnHeaderCell>  
  
- <xref:System.Windows.Forms.DataGridViewTopLeftHeaderCell>  
  
- カスタムセルの種類  
  
### <a name="datagridviewcolumn"></a>DataGridViewColumn  
 <xref:System.Windows.Forms.DataGridView>コントロールのアタッチされたデータストアのスキーマは、コントロールの列で表現され <xref:System.Windows.Forms.DataGridView> ます。 <xref:System.Windows.Forms.DataGridView>コントロールの列にアクセスするには、コレクションを使用し <xref:System.Windows.Forms.DataGridView.Columns%2A> ます。 選択した列には、コレクションを使用してアクセスでき <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> ます。 次のオブジェクトモデルは、この使用方法を示し、継承階層を示してい <xref:System.Windows.Forms.DataGridViewColumn> ます。  
  
 ![DataGridViewColumn オブジェクトモデル階層を示す図。](./media/datagridview-control-architecture-windows-forms/datagridviewcolumn-object-model.gif)  
  
 主なセル型には、対応する列の型があります。 これらは <xref:System.Windows.Forms.DataGridViewColumn> 基本クラスから派生します。  
  
 から派生したクラスを次に示し <xref:System.Windows.Forms.DataGridViewColumn> ます。  
  
- <xref:System.Windows.Forms.DataGridViewButtonColumn>  
  
- <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>  
  
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
  
- <xref:System.Windows.Forms.DataGridViewImageColumn>  
  
- <xref:System.Windows.Forms.DataGridViewTextBoxColumn>  
  
- <xref:System.Windows.Forms.DataGridViewLinkColumn>  
  
- カスタム列の型  
  
### <a name="datagridview-editing-controls"></a>DataGridView 編集コントロール  
 高度な編集機能をサポートするセルは、通常、Windows フォームコントロールから派生したホストされたコントロールを使用します。 これらのコントロールは、 <xref:System.Windows.Forms.IDataGridViewEditingControl> インターフェイスも実装します。 次のオブジェクトモデルは、これらのコントロールの使用方法を示しています。  
  
 ![DataGridView 編集コントロールオブジェクトモデルの階層を示す図。](./media/datagridview-control-architecture-windows-forms/datagridviewediting-object-model.gif)  
  
 コントロールには、次の編集コントロールが用意されてい <xref:System.Windows.Forms.DataGridView> ます。  
  
- <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>  
  
- <xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>  
  
 独自の編集コントロールを作成する方法については、「 [方法: Windows フォーム DataGridView セルのコントロールをホスト](how-to-host-controls-in-windows-forms-datagridview-cells.md)する」を参照してください。  
  
 次の表は、セルの種類、列の種類、および編集コントロールの関係を示しています。  
  
|セルの種類|ホストされるコントロール|列の型|  
|---------------|--------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewButtonCell>|該当なし|<xref:System.Windows.Forms.DataGridViewButtonColumn>|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxCell>|該当なし|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewComboBoxCell>|<xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewImageCell>|該当なし|<xref:System.Windows.Forms.DataGridViewImageColumn>|  
|<xref:System.Windows.Forms.DataGridViewLinkCell>|該当なし|<xref:System.Windows.Forms.DataGridViewLinkColumn>|  
|<xref:System.Windows.Forms.DataGridViewTextBoxCell>|<xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|  
  
### <a name="datagridviewrow"></a>DataGridViewRow  
 クラスは、コントロールがアタッチされている <xref:System.Windows.Forms.DataGridViewRow> データストアのレコードのデータフィールドを表示し <xref:System.Windows.Forms.DataGridView> ます。 <xref:System.Windows.Forms.DataGridView>コントロールの行にアクセスするには、コレクションを使用し <xref:System.Windows.Forms.DataGridView.Rows%2A> ます。 選択した行には、コレクションを使用してアクセスでき <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> ます。 次のオブジェクトモデルは、この使用方法を示し、継承階層を示してい <xref:System.Windows.Forms.DataGridViewRow> ます。  
  
 ![DataGridViewRow オブジェクトモデル階層を示す図。](./media/datagridview-control-architecture-windows-forms/datagridviewrow-object-model.gif)
  
 クラスから独自の型を派生させることもできますが、 <xref:System.Windows.Forms.DataGridViewRow> 通常は必要ありません。 <xref:System.Windows.Forms.DataGridView>コントロールには、オブジェクトの動作をカスタマイズするための行関連のイベントとプロパティがいくつかあり <xref:System.Windows.Forms.DataGridViewRow> ます。  
  
 コントロールのプロパティを有効にすると <xref:System.Windows.Forms.DataGridView> <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> 、新しい行を追加するための特殊な行が最後の行として表示されます。 この行はコレクションに含まれてい <xref:System.Windows.Forms.DataGridView.Rows%2A> ますが、注意が必要な特別な機能を備えています。 詳細については、「 [Windows フォーム DataGridView コントロールでの新しいレコードの行の使用](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目

- [DataGridView コントロールの概要](datagridview-control-overview-windows-forms.md)
- [Windows フォーム DataGridView コントロールのカスタマイズ](customizing-the-windows-forms-datagridview-control.md)
- [Windows フォーム DataGridView コントロールにおける新規レコード行の使用](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)
