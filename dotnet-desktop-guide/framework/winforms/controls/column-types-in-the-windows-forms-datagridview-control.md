---
title: DataGridView コントロールの列の型
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], types
- DataGridView control [Windows Forms], column types
- data grids [Windows Forms], columns
ms.assetid: f0a0a9f1-8757-4bfd-891f-d7d12870dbed
ms.openlocfilehash: e918394cca6350854074d4c1567890138b2a1462
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974290"
---
# <a name="column-types-in-the-windows-forms-datagridview-control"></a>Windows フォーム DataGridView コントロールの列型
コントロールは、 <xref:System.Windows.Forms.DataGridView> いくつかの列の型を使用して情報を表示し、ユーザーが情報を変更または追加できるようにします。  
  
 コントロールをバインド <xref:System.Windows.Forms.DataGridView> し、プロパティをに設定すると、バインドされた <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> `true` データソースに含まれるデータ型に適した既定の列型を使用して列が自動的に生成されます。  
  
 任意の列クラスのインスタンスを自分で作成し、プロパティによって返されるコレクションに追加することもでき <xref:System.Windows.Forms.DataGridView.Columns%2A> ます。 これらのインスタンスは、バインドされていない列として使用するように作成することも、手動でバインドすることもできます。 手動でバインドされた列は、ある型の自動生成された列を別の型の列に置き換える場合などに便利です。  
  
 次の表では、コントロールで使用できるさまざまな列クラスについて説明し <xref:System.Windows.Forms.DataGridView> ます。  
  
|クラス|説明|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|テキストベースの値と共に使用されます。 数値および文字列にバインドするときに自動的に生成されます。|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|および値と共に使用され <xref:System.Boolean> <xref:System.Windows.Forms.CheckState> ます。 これらの型の値にバインドするときに自動的に生成されます。|  
|<xref:System.Windows.Forms.DataGridViewImageColumn>|画像を表示するために使用します。 バイト配列、 <xref:System.Drawing.Image> オブジェクト、またはオブジェクトにバインドするときに自動的に生成され <xref:System.Drawing.Icon> ます。|  
|<xref:System.Windows.Forms.DataGridViewButtonColumn>|セルにボタンを表示するために使用します。 バインド時に自動的に生成されません。 通常、非バインド列として使用されます。|  
|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|セル内のドロップダウンリストを表示するために使用します。 バインド時に自動的に生成されません。 通常、データバインドは手動で行います。|  
|<xref:System.Windows.Forms.DataGridViewLinkColumn>|セル内のリンクを表示するために使用します。 バインド時に自動的に生成されません。 通常、データバインドは手動で行います。|  
|カスタム列の型|クラスまたはその派生クラスを継承することによって独自の列クラスを作成し、 <xref:System.Windows.Forms.DataGridViewColumn> カスタムの外観、動作、またはホストされたコントロールを提供できます。 詳細については、「[方法: 動作と外観を拡張して Windows フォーム DataGridView コントロールのセルと列をカスタマイズする](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)」を参照してください。|  
  
 これらの列の型については、以降のセクションで詳しく説明します。  
  
## <a name="datagridviewtextboxcolumn"></a>DataGridViewTextBoxColumn  
 <xref:System.Windows.Forms.DataGridViewTextBoxColumn>は、数値や文字列などのテキストベースの値で使用される汎用の列型です。 編集モードでは、 <xref:System.Windows.Forms.TextBox> ユーザーがセル値を変更できるように、アクティブセルにコントロールが表示されます。  
  
 セル値は、自動的に文字列に変換されて表示されます。 ユーザーが入力または変更した値は、適切なデータ型のセル値を作成するために自動的に解析されます。 <xref:System.Windows.Forms.DataGridView.CellFormatting>コントロールのイベントとイベントを処理することによって、これらの変換をカスタマイズでき <xref:System.Windows.Forms.DataGridView.CellParsing> <xref:System.Windows.Forms.DataGridView> ます。  
  
 列のセル値のデータ型は、 <xref:System.Windows.Forms.DataGridViewColumn.ValueType%2A> 列のプロパティで指定します。  
  
## <a name="datagridviewcheckboxcolumn"></a>DataGridViewCheckBoxColumn  
 は、 <xref:System.Windows.Forms.DataGridViewCheckBoxColumn> およびの値と共に使用され <xref:System.Boolean> <xref:System.Windows.Forms.CheckState> ます。 <xref:System.Boolean> 値は、プロパティの値に応じて、2つの状態または3つの状態のチェックボックスとして表示さ <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A> れます。 列が値にバインドされている場合 <xref:System.Windows.Forms.CheckState> 、 <xref:System.Windows.Forms.DataGridViewCheckBoxColumn.ThreeState%2A> プロパティの値は `true` 既定でになります。  
  
 通常、チェックボックスのセル値は、他のデータと同様にストレージ用、または一括操作を実行する目的で使用されます。 ユーザーがチェックボックスのセルをクリックしたときにすぐに応答する場合は、イベントを処理でき <xref:System.Windows.Forms.DataGridView.CellClick> ますが、このイベントはセルの値が更新される前に発生します。 クリック時に新しい値が必要な場合は、現在の値に基づいて期待される値を計算する方法があります。 もう1つの方法は、変更を直ちにコミットし、 <xref:System.Windows.Forms.DataGridView.CellValueChanged> 応答するイベントを処理することです。 セルがクリックされたときに変更をコミットするには、イベントを処理する必要があり <xref:System.Windows.Forms.DataGridView.CurrentCellDirtyStateChanged> ます。 ハンドラーで、現在のセルがチェックボックスセルの場合は、メソッドを呼び出し、 <xref:System.Windows.Forms.DataGridView.CommitEdit%2A> 値を渡し <xref:System.Windows.Forms.DataGridViewDataErrorContexts.Commit> ます。  
  
## <a name="datagridviewimagecolumn"></a>DataGridViewImageColumn  
 <xref:System.Windows.Forms.DataGridViewImageColumn>は、イメージの表示に使用されます。 画像列は、データソースから自動的に設定することも、バインドされていない列に対して手動で設定することも、イベントのハンドラーに動的に設定することもでき <xref:System.Windows.Forms.DataGridView.CellFormatting> ます。  
  
 データソースからのイメージ列の自動作成では、さまざまなイメージ形式のバイト配列が使用されます。これには、クラスでサポートされるすべての形式 <xref:System.Drawing.Image> や、Microsoft® access および Northwind サンプルデータベースで使用される OLE 画像形式などが含まれます。  
  
 イメージ列を手動で設定すると、の機能がカスタマイズされた外観で提供される場合に便利です <xref:System.Windows.Forms.DataGridViewButtonColumn> 。 イベントを処理して、 <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> 画像セル内のクリックに応答することができます。  
  
 イベントのハンドラーでイメージ列のセルを設定すると、画像 <xref:System.Windows.Forms.DataGridView.CellFormatting> 以外の形式で計算値または値のイメージを提供する場合に便利です。 たとえば、、、など、アイコンとして表示する文字列値を含む "リスク" 列がある `"high"` `"middle"` とし `"low"` ます。 また、イメージのバイナリコンテンツではなく、読み込む必要のあるイメージの場所を含む "イメージ" 列がある場合もあります。  
  
## <a name="datagridviewbuttoncolumn"></a>DataGridViewButtonColumn  
 を使用すると <xref:System.Windows.Forms.DataGridViewButtonColumn> 、ボタンを含むセルの列を表示できます。 これは、ユーザーが特定のレコードに対して簡単にアクションを実行できるようにする場合に便利です。たとえば、注文を配置したり、子レコードを別のウィンドウに表示したりすることができます。  
  
 コントロールをデータバインドするときに、ボタン列が自動的に生成されることはありません <xref:System.Windows.Forms.DataGridView> 。 ボタン列を使用するには、それらを手動で作成し、プロパティによって返されるコレクションに追加する必要があり <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=nameWithType> ます。  
  
 イベントを処理することにより、ボタンのセルのユーザークリックに応答でき <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> ます。  
  
## <a name="datagridviewcomboboxcolumn"></a>DataGridViewComboBoxColumn  
 を使用すると <xref:System.Windows.Forms.DataGridViewComboBoxColumn> 、ドロップダウンリストボックスを含むセルの列を表示できます。 これは、Northwind サンプルデータベース内の Products テーブルの Category 列など、特定の値のみを含むことができるフィールドのデータ入力に便利です。  
  
 すべてのセルに使用されるドロップダウンリストには、 <xref:System.Windows.Forms.ComboBox> プロパティによって返されたコレクションを通じて手動で、 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A> または、、およびの各プロパティを使用してデータソースにバインドすることによって、ドロップダウンリストに入力するのと同じ方法で使用できます <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> 。 詳細については、「 [ComboBox コントロール](combobox-control-windows-forms.md)」を参照してください。  
  
 のプロパティを設定することによって、コントロールで使用されるデータソースに実際のセル値をバインドでき <xref:System.Windows.Forms.DataGridView> <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A> <xref:System.Windows.Forms.DataGridViewComboBoxColumn?displayProperty=nameWithType> ます。  
  
 コンボボックスの列は、コントロールのデータバインディング時に自動的には生成されません <xref:System.Windows.Forms.DataGridView> 。 コンボボックス列を使用するには、それらを手動で作成し、プロパティによって返されるコレクションに追加する必要があり <xref:System.Windows.Forms.DataGridView.Columns%2A> ます。  
  
## <a name="datagridviewlinkcolumn"></a>DataGridViewLinkColumn  
 を使用 <xref:System.Windows.Forms.DataGridViewLinkColumn> すると、ハイパーリンクを含むセルの列を表示できます。 これは、データソース内の URL 値や、子レコードを含むウィンドウを開くなどの特殊な動作のボタン列の代わりに使用できます。  
  
 コントロールをデータバインドするときに、リンク列が自動的に生成されることはありません <xref:System.Windows.Forms.DataGridView> 。 リンク列を使用するには、それらを手動で作成し、プロパティによって返されるコレクションに追加する必要があり <xref:System.Windows.Forms.DataGridView.Columns%2A> ます。  
  
 イベントを処理することによって、リンク上のユーザークリックに応答でき <xref:System.Windows.Forms.DataGridView.CellContentClick> ます。 このイベントは、ユーザーが <xref:System.Windows.Forms.DataGridView.CellClick> <xref:System.Windows.Forms.DataGridView.CellMouseClick> セル内の任意の場所をクリックしたときに発生するイベントとイベントとは異なります。  
  
 クラスには、 <xref:System.Windows.Forms.DataGridViewLinkColumn> リンクの表示を変更するためのプロパティが用意されています  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- <xref:System.Windows.Forms.DataGridViewButtonColumn>
- <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn>
- <xref:System.Windows.Forms.DataGridViewImageColumn>
- <xref:System.Windows.Forms.DataGridViewTextBoxColumn>
- <xref:System.Windows.Forms.DataGridViewLinkColumn>
- [DataGridView コントロール](datagridview-control-windows-forms.md)
- [方法: Windows フォーム DataGridView コントロールのセルにイメージを表示する](how-to-display-images-in-cells-of-the-windows-forms-datagridview-control.md)
- [方法: Windows フォーム DataGridView コントロールのイメージ列を操作する](how-to-work-with-image-columns-in-the-windows-forms-datagridview-control.md)
- [Windows フォーム DataGridView コントロールのカスタマイズ](customizing-the-windows-forms-datagridview-control.md)
