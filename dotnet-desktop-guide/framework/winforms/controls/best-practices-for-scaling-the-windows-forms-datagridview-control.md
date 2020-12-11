---
title: DataGridView コントロールのスケーリングのベストプラクティス
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], row sharing
- data grids [Windows Forms], best practices
- DataGridView control [Windows Forms], shared rows
- DataGridView control [Windows Forms], best practices
- best practices [Windows Forms], dataGridView control
- DataGridView control [Windows Forms], scaling
ms.assetid: 8321a8a6-6340-4fd1-b475-fa090b905aaf
ms.openlocfilehash: 63500a79def89510b4bc7a436abc4620a7265a79
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981575"
---
# <a name="best-practices-for-scaling-the-windows-forms-datagridview-control"></a>Windows フォーム DataGridView コントロールを拡張するための推奨される手順

この <xref:System.Windows.Forms.DataGridView> コントロールは、最大のスケーラビリティを提供するように設計されています。 大量のデータを表示する必要がある場合は、このトピックで説明されているガイドラインに従って、大量のメモリを消費したり、ユーザーインターフェイス (UI) の応答性を低下させたりすることは避けてください。 このトピックでは、次の問題について説明します。

- セルスタイルの効率的な使用

- ショートカットメニューの効率的な使用

- 自動サイズ変更の効率的な使用

- 選択したセル、行、および列のコレクションを効率的に使用する

- 共有行の使用

- 行が非共有になるのを防ぐ

特別なパフォーマンスのニーズがある場合は、仮想モードを実装し、独自のデータ管理操作を提供できます。 詳細については、「 [Windows フォーム DataGridView コントロールのデータ表示モード](data-display-modes-in-the-windows-forms-datagridview-control.md)」を参照してください。

## <a name="using-cell-styles-efficiently"></a>セルスタイルの効率的な使用

各セル、行、および列には、独自のスタイル情報を設定できます。 スタイル情報は、オブジェクトに格納され <xref:System.Windows.Forms.DataGridViewCellStyle> ます。 多くの個々の要素に対してセルスタイルオブジェクトを作成する <xref:System.Windows.Forms.DataGridView> ことは、特に大量のデータを扱う場合には非効率的です。 パフォーマンスへの影響を回避するには、次のガイドラインに従います。

- 個々のオブジェクトまたはオブジェクトのセルスタイルプロパティを設定しないで <xref:System.Windows.Forms.DataGridViewCell> <xref:System.Windows.Forms.DataGridViewRow> ください。 これには、プロパティによって指定された row オブジェクトが含まれ <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> ます。 行テンプレートから複製された新しい行はそれぞれ、テンプレートのセルスタイルオブジェクトの独自のコピーを受け取ります。 最大限のスケーラビリティを実現するには、レベルでセルのスタイルプロパティを設定 <xref:System.Windows.Forms.DataGridView> します。 たとえば、プロパティではなく、プロパティを設定し <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType> ます。

- 既定の書式設定以外の書式設定が必要なセルがある場合は、 <xref:System.Windows.Forms.DataGridViewCellStyle> セル、行、または列のグループ間で同じインスタンスを使用します。 <xref:System.Windows.Forms.DataGridViewCellStyle>個々のセル、行、および列に対して型のプロパティを直接設定することは避けてください。 セルスタイル共有の例については、「 [方法: Windows フォーム DataGridView コントロールの既定のセルスタイルを設定する](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)」を参照してください。 イベントハンドラーを処理することによって、セルスタイルを個別に設定するときにパフォーマンスが低下しないようにすることもでき <xref:System.Windows.Forms.DataGridView.CellFormatting> ます。 例については、「 [方法: Windows フォーム DataGridView コントロールでデータの書式をカスタマイズする](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)」を参照してください。

- セルのスタイルを決定するときは、 <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A?displayProperty=nameWithType> プロパティではなくプロパティを使用し <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType> ます。 プロパティにアクセスすると、 <xref:System.Windows.Forms.DataGridViewCell.Style%2A> <xref:System.Windows.Forms.DataGridViewCellStyle> プロパティがまだ使用されていない場合に、クラスの新しいインスタンスが作成されます。 また、行、列、またはコントロールからいくつかのスタイルが継承されている場合、このオブジェクトにはセルの完全なスタイル情報が含まれていない可能性があります。 セルスタイルの継承の詳細については、「 [Windows フォーム DataGridView コントロールのセルのスタイル](cell-styles-in-the-windows-forms-datagridview-control.md)」を参照してください。

## <a name="using-shortcut-menus-efficiently"></a>ショートカットメニューの効率的な使用

各セル、行、および列には、独自のショートカットメニューを設定できます。 コントロールのショートカットメニュー <xref:System.Windows.Forms.DataGridView> は、コントロールによって表され <xref:System.Windows.Forms.ContextMenuStrip> ます。 セルスタイルオブジェクトと同様に、多くの個々の要素のショートカットメニューを作成すると、 <xref:System.Windows.Forms.DataGridView> パフォーマンスが低下します。 このようにペナルティを回避するには、次のガイドラインに従います。

- 個々のセルおよび行のショートカットメニューを作成しないようにします。 これには、新しい行がコントロールに追加されたときに、そのショートカットメニューと共に複製される行テンプレートが含まれます。 最大限のスケーラビリティを実現するには、コントロールのプロパティのみを使用して、 <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> コントロール全体に対して1つのショートカットメニューを指定します。

- 複数の行またはセルに複数のショートカットメニューが必要な場合は、 <xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded> イベントまたはイベントを処理し <xref:System.Windows.Forms.DataGridView.RowContextMenuStripNeeded> ます。 これらのイベントを使用すると、ショートカットメニューオブジェクトを自分で管理できるため、パフォーマンスを調整できます。

## <a name="using-automatic-resizing-efficiently"></a>自動サイズ変更の効率的な使用

セルの内容全体がクリッピングなしで表示されるように、行、列、およびヘッダーをセルの内容の変更に合わせて自動的にサイズ変更することができます。 サイズ変更モードを変更すると、行、列、およびヘッダーのサイズも変更される可能性があります。 正しいサイズを判断するには、コントロールが、 <xref:System.Windows.Forms.DataGridView> 対応する必要がある各セルの値を調べる必要があります。 大きなデータセットを使用する場合、自動サイズ変更が発生すると、この分析によってコントロールのパフォーマンスが低下する可能性があります。 パフォーマンスの低下を回避するには、次のガイドラインに従います。

- 大量の行を持つコントロールでは、自動サイズ設定を使用しないようにして <xref:System.Windows.Forms.DataGridView> ください。 自動サイズ変更を使用する場合は、表示されている行に基づいてサイズを変更するだけです。 仮想モードでも表示されている行のみを使用します。

  - 行と列の場合 `DisplayedCells` は `DisplayedCellsExceptHeaders` <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode> 、、、およびの各列挙体のまたはフィールドを使用し <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode> <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode> ます。

  - 行ヘッダーの場合は、 <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode.AutoSizeToDisplayedHeaders> 列挙体のまたはフィールドを使用し <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode.AutoSizeToFirstHeader> <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode> ます。

- 最大限のスケーラビリティを実現するには、自動サイズ変更をオフにし、プログラムによるサイズ変更を使用します。

詳細については、「 [Windows フォーム DataGridView コントロールのサイズ変更オプション](sizing-options-in-the-windows-forms-datagridview-control.md)」を参照してください。

## <a name="using-the-selected-cells-rows-and-columns-collections-efficiently"></a>選択したセル、行、および列のコレクションを効率的に使用する

コレクションは、 <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> 大きな選択によって効率的には実行されません。 <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> 一般的なコントロールのセルよりも多くの行があり、 <xref:System.Windows.Forms.DataGridView> 行よりも多くの列が少ないため、コレクションおよびコレクションも非効率的です。 これらのコレクションを操作するときのパフォーマンスの低下を回避するには、次のガイドラインに従います。

- コレクションの内容にアクセスする前に、内のすべてのセルが選択されているかどうかを確認するには、 <xref:System.Windows.Forms.DataGridView> <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> メソッドの戻り値を確認し <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> ます。 ただし、この方法では、行が共有されなくなる可能性があることに注意してください。 詳細については、次のセクションを参照してください。

- <xref:System.Collections.ICollection.Count%2A> <xref:System.Windows.Forms.DataGridViewSelectedCellCollection?displayProperty=nameWithType> 選択されたセルの数を決定するために、のプロパティを使用しないようにしてください。 代わりに、メソッドを使用 <xref:System.Windows.Forms.DataGridView.GetCellCount%2A?displayProperty=nameWithType> し、値を渡し <xref:System.Windows.Forms.DataGridViewElementStates.Selected?displayProperty=nameWithType> ます。 同様に、選択した <xref:System.Windows.Forms.DataGridViewRowCollection.GetRowCount%2A?displayProperty=nameWithType> <xref:System.Windows.Forms.DataGridViewColumnCollection.GetColumnCount%2A?displayProperty=nameWithType> 行および列のコレクションにアクセスするのではなく、メソッドとメソッドを使用して、選択した要素の数を決定します。

- セルベースの選択モードは避けてください。 代わりに、プロパティを <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> またはに設定し <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType> <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect?displayProperty=nameWithType> ます。

## <a name="using-shared-rows"></a>共有行の使用

効率的なメモリ使用は、 <xref:System.Windows.Forms.DataGridView> 共有行によって制御されます。 行は、クラスのインスタンスを共有することで、その外観と動作に関する情報を可能な限り共有し <xref:System.Windows.Forms.DataGridViewRow> ます。

行インスタンスを共有するとメモリが節約されますが、行は簡単に非共有になります。 たとえば、ユーザーが直接セルを操作すると、その行の共有が解除されます。 このことは避けられないため、このトピックのガイドラインは、非常に大量のデータを扱う場合、およびプログラムを実行するたびにユーザーが比較的小さなデータの一部を操作する場合にのみ役立ちます。

<xref:System.Windows.Forms.DataGridView>セルに値が含まれている場合、バインドされていないコントロールでは行を共有できません。 <xref:System.Windows.Forms.DataGridView>コントロールが外部データソースにバインドされている場合、または仮想モードを実装して独自のデータソースを指定した場合、セル値はセルオブジェクトではなく、コントロールの外部に格納されるので、行を共有することができます。

行オブジェクトを共有できるのは、すべてのセルの状態が行の状態とセルを含む列の状態から決まる場合だけです。 行と列の状態から推測できないようにセルの状態を変更すると、その行を共有することはできません。

たとえば、次のような状況では、行を共有することはできません。

- この行には、選択された列に含まれていない1つの選択されたセルが含まれています。

- この行に <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> は、プロパティまたはプロパティが設定されたセルが含まれてい <xref:System.Windows.Forms.DataGridViewCell.ContextMenuStrip%2A> ます。

- この行には、プロパティが設定されたが含まれてい <xref:System.Windows.Forms.DataGridViewComboBoxCell> <xref:System.Windows.Forms.DataGridViewComboBoxCell.Items%2A> ます。

バインドモードまたは仮想モードでは、イベントとイベントを処理することによって、個々のセルのツールヒントやショートカットメニューを提供でき <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> <xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded> ます。

<xref:System.Windows.Forms.DataGridView>コントロールは、行がに追加されるたびに、自動的に共有行を使用しようとし <xref:System.Windows.Forms.DataGridViewRowCollection> ます。 次のガイドラインを使用して、行が共有されていることを確認します。

- `Add(Object[])`メソッドのオーバーロード <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> と、 `Insert(Object[])` コレクションのメソッドのオーバーロードを呼び出さないで <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType> ください。 これらのオーバーロードは、自動的に非共有行を作成します。

- 次の場合に、プロパティで指定された行を共有できることを確認してください <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> 。

  - メソッドのまたはのオーバーロード、または `Add()` `Add(Int32)` <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> `Insert(Int32,Int32)` <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> コレクションのメソッドのオーバーロード <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType> を呼び出す場合。

  - プロパティの値を増やす場合 <xref:System.Windows.Forms.DataGridView.RowCount%2A?displayProperty=nameWithType> 。

  - プロパティを設定する場合 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType> 。

- `indexSource` <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopy%2A> <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopies%2A> コレクションの、、、の各メソッドを呼び出すときに、パラメーターによって <xref:System.Windows.Forms.DataGridViewRowCollection.InsertCopy%2A> 示さ <xref:System.Windows.Forms.DataGridViewRowCollection.InsertCopies%2A> れる行を共有できることを確認してください <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType> 。

- メソッド、メソッド、メソッド `Add(DataGridViewRow)` <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> <xref:System.Windows.Forms.DataGridViewRowCollection.AddRange%2A> `Insert(Int32,DataGridViewRow)` のオーバーロード、 <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> および <xref:System.Windows.Forms.DataGridViewRowCollection.InsertRange%2A> コレクションのメソッド <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType> のオーバーロードを呼び出すときに、指定された行または行を共有できることを確認してください。

行が共有されているかどうかを判断するには、メソッドを使用して <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> 行オブジェクトを取得し、オブジェクトのプロパティを確認し <xref:System.Windows.Forms.DataGridViewBand.Index%2A> ます。 共有行 <xref:System.Windows.Forms.DataGridViewBand.Index%2A> のプロパティ値は常に-1 です。

## <a name="preventing-rows-from-becoming-unshared"></a>行が非共有になるのを防ぐ

共有行は、コードまたはユーザー操作の結果として非共有になることがあります。 パフォーマンスへの影響を回避するには、行が共有されなくなるのを避ける必要があります。 アプリケーションの開発中に、イベントを処理して、 <xref:System.Windows.Forms.DataGridView.RowUnshared> 行が共有されなくなったことを確認できます。 これは、行共有の問題をデバッグする場合に便利です。

行が非共有にならないようにするには、次のガイドラインに従います。

- コレクションのインデックス作成 <xref:System.Windows.Forms.DataGridView.Rows%2A> やループによる反復処理は避けて `foreach` ください。 通常、行に直接アクセスする必要はありません。 <xref:System.Windows.Forms.DataGridView> 行を操作するメソッドは、行インスタンスではなく、行インデックス引数を受け取ります。 さらに、行関連のイベントのハンドラーは、行プロパティを持つイベント引数オブジェクトを受け取ります。このオブジェクトを使用して、共有を解除することなく行を操作できます。

- 行オブジェクトにアクセスする必要がある場合は、 <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> メソッドを使用して、行の実際のインデックスを渡します。 ただし、このメソッドを使用して取得した共有行オブジェクトを変更すると、このオブジェクトを共有するすべての行が変更されることに注意してください。 ただし、新しいレコードの行は他の行と共有されないため、他の行を変更しても影響はありません。 また、共有行によって表される異なる行のショートカットメニューが異なる場合もあります。 共有行インスタンスから正しいショートカットメニューを取得するには、 <xref:System.Windows.Forms.DataGridViewRow.GetContextMenuStrip%2A> メソッドを使用して、行の実際のインデックスを渡します。 代わりに共有行のプロパティにアクセスする場合 <xref:System.Windows.Forms.DataGridViewRow.ContextMenuStrip%2A> は、共有行のインデックス (-1) が使用され、正しいショートカットメニューは取得されません。

- コレクションにインデックスを作成しないように <xref:System.Windows.Forms.DataGridViewRow.Cells%2A?displayProperty=nameWithType> します。 セルに直接アクセスすると、親の行が非共有になり、新しいがインスタンス化され <xref:System.Windows.Forms.DataGridViewRow> ます。 セル関連イベントのハンドラーは、セルプロパティを使用してイベント引数オブジェクトを受け取ります。このオブジェクトを使用すると、行の共有を解除せずにセルを操作できます。 また、プロパティを使用して、 <xref:System.Windows.Forms.DataGridView.CurrentCellAddress%2A> セルに直接アクセスせずに、現在のセルの行インデックスと列インデックスを取得することもできます。

- セルベースの選択モードは避けてください。 これらのモードでは、行が共有されなくなります。 代わりに、プロパティを <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> またはに設定し <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType> <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect?displayProperty=nameWithType> ます。

- <xref:System.Windows.Forms.DataGridViewRowCollection.CollectionChanged?displayProperty=nameWithType>イベントまたはイベントを処理しません <xref:System.Windows.Forms.DataGridView.RowStateChanged?displayProperty=nameWithType> 。 これらのイベントにより、行が共有されなくなります。 また、これらのイベントを <xref:System.Windows.Forms.DataGridViewRowCollection.OnCollectionChanged%2A?displayProperty=nameWithType> 発生させるメソッドまたはメソッドを呼び出さないでください <xref:System.Windows.Forms.DataGridView.OnRowStateChanged%2A?displayProperty=nameWithType> 。

- <xref:System.Windows.Forms.DataGridView.SelectedCells%2A?displayProperty=nameWithType> <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> プロパティ値が <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> 、、 <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect> <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> 、または <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> の場合は、コレクションにアクセスしません。 これにより、選択したすべての行の共有が解除されます。

- メソッドを呼び出さないで <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A?displayProperty=nameWithType> ください。 このメソッドは、行が共有されなくなる可能性があります。

- <xref:System.Windows.Forms.DataGridView.SelectAll%2A?displayProperty=nameWithType>プロパティ値がの場合は、メソッドを呼び出さないで <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> <xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect> ください。 これにより、すべての行が非共有になります。

- <xref:System.Windows.Forms.DataGridViewCell.ReadOnly%2A> <xref:System.Windows.Forms.DataGridViewCell.Selected%2A> `false` 列内の対応するプロパティがに設定されている場合は、セルのまたはプロパティをに設定しないでください `true` 。 これにより、すべての行が非共有になります。

- プロパティにアクセスしないで <xref:System.Windows.Forms.DataGridViewRowCollection.List%2A?displayProperty=nameWithType> ください。 これにより、すべての行が非共有になります。

- `Sort(IComparer)`メソッドのオーバーロードは呼び出さないで <xref:System.Windows.Forms.DataGridView.Sort%2A> ください。 カスタム比較子を使用して並べ替えると、すべての行の共有が解除されます。

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.DataGridView>
- [Windows フォーム DataGridView コントロールでのパフォーマンス チューニング](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [Windows フォーム DataGridView コントロールでの仮想モード](virtual-mode-in-the-windows-forms-datagridview-control.md)
- [Windows フォーム DataGridView コントロールでのデータ表示モード](data-display-modes-in-the-windows-forms-datagridview-control.md)
- [Windows フォーム DataGridView コントロールでのセルのスタイル](cell-styles-in-the-windows-forms-datagridview-control.md)
- [方法: Windows フォーム DataGridView コントロールの既定のセル スタイルを設定する](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)
- [Windows フォーム DataGridView コントロールのサイズ変更オプション](sizing-options-in-the-windows-forms-datagridview-control.md)
