---
title: DataGridView コントロールの既定のキーボード操作とマウス処理
ms.date: 02/13/2018
helpviewer_keywords:
- data grids [Windows Forms], mouse handling
- DataGridView control [Windows Forms], navigation keys
- keyboards [Windows Forms], default handling in DataGridView control
- DataGridView control [Windows Forms], keyboard handling
- mouse [Windows Forms], default handling in DataGridView control
- DataGridView control [Windows Forms], mouse handling
- navigation keys [Windows Forms], DataGridView control
ms.assetid: 4519b928-bfc8-4e8b-bb9c-b1e76a0ca552
ms.openlocfilehash: 36defff02450b40265c9b6801380cab78eabe5f3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974201"
---
# <a name="default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control"></a>Windows フォーム DataGridView コントロールでの既定のキーボード操作とマウス処理

次の表では、ユーザーがキーボードとマウスを使用してコントロールを操作する方法について説明し <xref:System.Windows.Forms.DataGridView> ます。  
  
> [!NOTE]
> キーボードの動作をカスタマイズするには、などの標準のキーボードイベントを処理し <xref:System.Windows.Forms.Control.KeyDown> ます。 ただし、編集モードでは、ホストされている編集コントロールはキーボード入力を受け取り、キーボードイベントはコントロールに対して発生しません <xref:System.Windows.Forms.DataGridView> 。 コントロールイベントの編集を処理するには、ハンドラーをイベントハンドラーの編集コントロールにアタッチし <xref:System.Windows.Forms.DataGridView.EditingControlShowing> ます。 または、 <xref:System.Windows.Forms.DataGridView> メソッドとメソッドをオーバーライドして、サブクラスのキーボード動作をカスタマイズすることもでき <xref:System.Windows.Forms.DataGridView.ProcessDialogKey%2A> <xref:System.Windows.Forms.DataGridView.ProcessDataGridViewKey%2A> ます。  
  
## <a name="default-keyboard-handling"></a>既定のキーボード処理  
  
### <a name="basic-navigation-and-entry-keys"></a>基本的なナビゲーションキーとエントリキー  
  
|キーまたはキーの組み合わせ|説明|  
|----------------------------|-----------------|  
|↓|現在のセルのすぐ下のセルにフォーカスを移動します。 フォーカスが最後の行にある場合、は何も行いません。|  
|←|行の前のセルにフォーカスを移動します。 フォーカスが行の最初のセルにある場合、は何も行いません。|  
|→|行の次のセルにフォーカスを移動します。 フォーカスが行の最後のセルにある場合、は何も行いません。|  
|↑|現在のセルのすぐ上のセルにフォーカスを移動します。 フォーカスが最初の行にある場合、は何も行いません。|  
|ホーム|現在の行の最初のセルにフォーカスを移動します。|  
|End|現在の行の最後のセルにフォーカスを移動します。|  
|PageDown|コントロールを、完全に表示されている行の数だけ下にスクロールします。 列を変更せずに、完全に表示されている最後の行にフォーカスを移動します。|  
|PageUp|コントロールを、完全に表示されている行の数だけ上にスクロールします。 列を変更せずに、表示されている最初の行にフォーカスを移動します。|  
|Tab|<xref:System.Windows.Forms.DataGridView.StandardTab%2A>プロパティ値がの場合は `false` 、現在の行の次のセルにフォーカスを移動します。 フォーカスが行の最後のセルに既に存在する場合、は、フォーカスを次の行の最初のセルに移動します。 フォーカスがコントロールの最後のセルにある場合は、親コンテナーのタブ オーダーで次のコントロールにフォーカスを移動します。<br /><br /> <xref:System.Windows.Forms.DataGridView.StandardTab%2A>プロパティ値がの場合 `true` 、親コンテナーのタブオーダーの次のコントロールにフォーカスを移動します。|  
|Shift + Tab|<xref:System.Windows.Forms.DataGridView.StandardTab%2A>プロパティ値がの場合は `false` 、現在の行の前のセルにフォーカスを移動します。 フォーカスが既に行の最初のセルにある場合は、前の行の最後のセルにフォーカスを移動します。 フォーカスがコントロールの最初のセルにある場合は、親コンテナーのタブ オーダーで前のコントロールにフォーカスを移動します。<br /><br /> <xref:System.Windows.Forms.DataGridView.StandardTab%2A>プロパティ値がの場合は `true` 、親コンテナーのタブオーダーで前のコントロールにフォーカスを移動します。|  
|Ctrl + Tab|<xref:System.Windows.Forms.DataGridView.StandardTab%2A>プロパティ値がの場合 `false` 、親コンテナーのタブオーダーの次のコントロールにフォーカスを移動します。<br /><br /> <xref:System.Windows.Forms.DataGridView.StandardTab%2A>プロパティ値がの場合は `true` 、現在の行の次のセルにフォーカスを移動します。 フォーカスが行の最後のセルに既に存在する場合、は、フォーカスを次の行の最初のセルに移動します。 フォーカスがコントロールの最後のセルにある場合は、親コンテナーのタブ オーダーで次のコントロールにフォーカスを移動します。|  
|Ctrl + Shift + Tab|<xref:System.Windows.Forms.DataGridView.StandardTab%2A>プロパティ値がの場合は `false` 、親コンテナーのタブオーダーで前のコントロールにフォーカスを移動します。<br /><br /> <xref:System.Windows.Forms.DataGridView.StandardTab%2A>プロパティ値がの場合は `true` 、現在の行の前のセルにフォーカスを移動します。 フォーカスが既に行の最初のセルにある場合は、前の行の最後のセルにフォーカスを移動します。 フォーカスがコントロールの最初のセルにある場合は、親コンテナーのタブ オーダーで前のコントロールにフォーカスを移動します。|  
|CTRL + 方向キー|矢印の方向にある最も遠いセルにフォーカスを移動します。|  
|Ctrl&lt;/localizedText&gt; + &lt;localizedText&gt;Home|コントロールの最初のセルにフォーカスを移動します。|  
|Ctrl&lt;/localizedText&gt; + &lt;localizedText&gt;End|コントロールの最後のセルにフォーカスを移動します。|  
|CTRL + PAGEDOWN/UP|PAGEUP または pageup と同じです。|  
|F2|<xref:System.Windows.Forms.DataGridView.EditMode%2A>プロパティ値がまたはの場合、現在のセルをセル編集モードにし <xref:System.Windows.Forms.DataGridViewEditMode.EditOnF2> <xref:System.Windows.Forms.DataGridViewEditMode.EditOnKeystrokeOrF2> ます。|
|F3|プロパティ値がの場合、現在の列を並べ替え <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType> <xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic> ます。 これは、現在の列ヘッダーをクリックした場合と同じです。 .NET Framework 4.7.2 以降で利用できます。 この機能を有効にするには、アプリケーションで .NET Framework 4.7.2 以降のバージョンを対象にするか、AppContext スイッチを使用してユーザー補助機能の強化を明示的に選択する必要があります。|  
|F4|現在のセルがの場合は <xref:System.Windows.Forms.DataGridViewComboBoxCell> 、セルを編集モードにし、ドロップダウンリストを表示します。|  
|ALT + ↑/↓|現在のセルがの場合は <xref:System.Windows.Forms.DataGridViewComboBoxCell> 、セルを編集モードにし、ドロップダウンリストを表示します。|  
|SPACE|現在のセルが、、またはの場合は、 <xref:System.Windows.Forms.DataGridViewButtonCell> <xref:System.Windows.Forms.DataGridViewLinkCell> <xref:System.Windows.Forms.DataGridViewCheckBoxCell> イベントとイベントを発生させ <xref:System.Windows.Forms.DataGridView.CellClick> <xref:System.Windows.Forms.DataGridView.CellContentClick> ます。 現在のセルがの場合は、 <xref:System.Windows.Forms.DataGridViewButtonCell> もボタンを押します。 現在のセルがの場合は <xref:System.Windows.Forms.DataGridViewCheckBoxCell> 、もチェックの状態を変更します。|  
|Enter|現在のセルと行に対するすべての変更をコミットし、現在のセルのすぐ下にあるセルにフォーカスを移動します。 フォーカスが最後の行にある場合は、フォーカスを移動せずにすべての変更をコミットします。|  
|ESC|コントロールが編集モードの場合は、編集をキャンセルします。 コントロールが編集モードでない場合、は、編集をサポートするデータソースにコントロールがバインドされているか、行レベルのコミットスコープで仮想モードが実装されている場合に、現在の行に加えられたすべての変更を元に戻します。|  
|BackSpace|セルを編集するときに、挿入位置の前の文字を削除します。|  
|DELETE|セルを編集するときに、挿入位置の後の文字を削除します。|  
|Ctrl + Enter|フォーカスを移動せずに、現在のセルに対するすべての変更をコミットします。 また、は、編集をサポートするデータソースにコントロールがバインドされている場合、または行レベルのコミットスコープで仮想モードが実装されている場合に、現在の行に対するすべての変更をコミットします。|  
|Ctrl + 0|セルを <xref:System.DBNull.Value?displayProperty=nameWithType> 編集できる場合は、現在のセルに値を入力します。 既定では、セル値の表示値 <xref:System.DBNull> は <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> 、現在の <xref:System.Windows.Forms.DataGridViewCellStyle> セルに対して有効になっているのプロパティの値です。|  
  
### <a name="selection-keys"></a>選択キー

 プロパティが <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> に設定されて `false` いて、 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> プロパティがに設定されている場合 <xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect> 、ナビゲーションキーを使用して現在のセルを変更すると、選択内容が新しいセルに変わります。 SHIFT、CTRL、ALT の各キーは、この動作に影響しません。  
  
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>がまたはに設定されている場合 <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect> 、同じ動作が発生しますが、次の追加機能があります。  
  
|キーまたはキーの組み合わせ|説明|  
|----------------------------|-----------------|  
|SHIFT + SPACE|行または列の全体を選択します (行または列のヘッダーをクリックした場合と同じです)。|  
|ナビゲーションキー (矢印キー、pageup/DOWN、HOME、END)|行または列がすべて選択されている場合、現在のセルを新しい行または列に変更すると、選択範囲が新しい行または列に移動します (選択モードによって異なります)。|  
  
 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>がに設定さ `false` <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> れ、がまたはに設定されている場合、キーボードを使用して現在のセルを <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> 新しい行または列に変更すると、選択範囲が完全な新しい行または列に移動します。 SHIFT、CTRL、ALT の各キーは、この動作に影響しません。  
  
 がに設定されている場合、 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> `true` ナビゲーション動作は変更されませんが、shift キーを押しながら (CTRL + SHIFT を含む) キーボードで移動すると、複数セルの選択が変更されます。 ナビゲーションが開始される前に、コントロールは現在のセルをアンカーセルとしてマークします。 SHIFT キーを押しながら移動すると、アンカーセルと現在のセルの間にあるすべてのセルが選択範囲に含まれます。 コントロール内の他のセルは、既に選択されている場合は選択されたままになりますが、キーボードナビゲーションによってアンカーセルと現在のセルの間に一時的に配置されると、選択が解除されることがあります。  
  
 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>がに設定さ `true` <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> れ、がまたはに設定されている場合 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> 、アンカーセルと現在のセルの動作は同じですが、完全な行または列のみが選択または選択解除されます。  
  
## <a name="default-mouse-handling"></a>既定のマウス処理
  
### <a name="basic-mouse-handling"></a>基本的なマウス処理
  
> [!NOTE]
> マウスの左ボタンを使用してセルをクリックすると、常に現在のセルが変更されます。 マウスの右ボタンを使用してセルをクリックすると、ショートカットメニューが表示されます (使用可能な場合)。  
  
|マウス操作|説明|  
|------------------|-----------------|  
|マウスの左ボタンを押す|クリックされたセルを現在のセルにし、イベントを発生させ <xref:System.Windows.Forms.DataGridView.CellMouseDown?displayProperty=nameWithType> ます。|  
|マウスの左ボタンを上へ移動|<xref:System.Windows.Forms.DataGridView.CellMouseUp?displayProperty=nameWithType> イベントを発生させます。|  
|マウスの左ボタンのクリック|<xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType>イベントとイベントを発生させます。 <xref:System.Windows.Forms.DataGridView.CellMouseClick?displayProperty=nameWithType>|  
|マウスボタンを押したままにして、列ヘッダーセルにドラッグします|プロパティがの場合は <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> `true` 、新しい位置にドロップできるように列を移動します。|  
  
### <a name="mouse-selection"></a>マウスの選択

 マウスの中央ボタンまたはマウスホイールには、選択動作が関連付けられていません。  
  
 プロパティが <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> に設定され、 `false` <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> プロパティがに設定されている場合 <xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect> 、次の動作が発生します。  
  
|マウス操作|説明|  
|------------------|-----------------|  
|マウスの左ボタンをクリック|ユーザーがセルをクリックした場合に、現在のセルのみを選択します。 ユーザーが行ヘッダーまたは列ヘッダーをクリックした場合、選択の動作はありません。|  
|マウスの右ボタンをクリック|使用できる場合は、ショートカットメニューを表示します。|  
  
 この動作は、がまたはに設定されている場合にも発生します <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect> 。ただし、選択モードによっては、行または列のヘッダーをクリックすると、行または列のすべての行または列が選択され、現在のセルが行または列の最初のセルに設定されます。  
  
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>がまたはに設定さ <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> れている場合 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> 、行または列の任意のセルをクリックすると、行または列全体が選択されます。  
  
 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>がに設定されている場合 `true` 、CTRL キーまたは SHIFT キーを押しながらセルをクリックすると、複数セルの選択が変更されます。  
  
 CTRL キーを押しながらセルをクリックすると、セルの選択状態が変化し、他のすべてのセルは現在の選択状態を保持します。  
  
 SHIFT キーを押しながらセルまたは一連のセルをクリックすると、選択範囲には、現在のセルと、最初のクリックの前の現在のセルの位置にあるアンカーセルの間のすべてのセルが含まれます。 ポインターをクリックして複数のセルにドラッグすると、アンカーセルはドラッグ操作の開始時にクリックされたセルになります。 SHIFT キーを押しながらクリックすると、現在のセルは変更されますが、アンカーセルは変更されません。 コントロール内のその他のセルは、既に選択されている場合は選択されたままになりますが、マウスのナビゲーションによってアンカーセルと現在のセルの間に一時的に配置されると、選択が解除されることがあります。  
  
 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>がに設定され `true` ていて、 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> がまたはに設定されている場合 <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect> 、(選択モードに応じて) 行または列のヘッダーをクリックすると、そのような選択が存在する場合に、行または列の既存の選択が変更されます。 それ以外の場合は、選択をクリアし、完全な行または列の新しい選択を開始します。 ただし、CTRL キーを押しながら行または列のヘッダーをクリックすると、現在の選択範囲を変更せずに、選択した行または列が現在の選択から追加または削除されます。  
  
 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>がに設定さ `true` れていて、 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> がまたはに設定されている場合 <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> 、SHIFT キーまたは CTRL キーを <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> 押しながらセルをクリックした場合と同じように動作します。ただし、完全な行と列のみが影響を受けます。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.DataGridView>
- [DataGridView コントロール](datagridview-control-windows-forms.md)
