---
title: DataGridView コントロールの選択モード
ms.date: 03/30/2017
helpviewer_keywords:
- selection [Windows Forms], modes in DataGridView control
- DataGridView control [Windows Forms], selection mode
ms.assetid: a3ebfd3d-0525-479d-9d96-d9e017289b36
ms.openlocfilehash: e20bf6307d77bf189b698e847c6b855c249dc3c1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981468"
---
# <a name="selection-modes-in-the-windows-forms-datagridview-control"></a>Windows フォーム DataGridView コントロールの選択モード

場合によっては、アプリケーションで、コントロール内のユーザーの選択に基づいてアクションを実行する必要があり <xref:System.Windows.Forms.DataGridView> ます。 アクションによっては、可能な選択の種類を制限することができます。 たとえば、現在選択されているレコードのレポートをアプリケーションで印刷できるとします。 この場合は、 <xref:System.Windows.Forms.DataGridView> 行内の任意の場所をクリックすると常に行全体が選択されるようにコントロールを構成し、一度に1行しか選択できないようにすることができます。

<xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType>プロパティを次の列挙値のいずれかに設定することによって、許可される選択を指定でき <xref:System.Windows.Forms.DataGridViewSelectionMode> ます。

|DataGridViewSelectionMode 値|説明|
|-------------------------------------|-----------------|
|<xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>|セルをクリックすると、そのセルが選択されます。 行と列のヘッダーを選択に使用することはできません。|
|<xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>|セルをクリックすると、そのセルが選択されます。 列ヘッダーをクリックすると、列全体が選択されます。 列ヘッダーを並べ替えに使用することはできません。|
|<xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>|セルまたは列ヘッダーをクリックすると、列全体が選択されます。 列ヘッダーを並べ替えに使用することはできません。|
|<xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect>|セルまたは行ヘッダーをクリックすると、行全体が選択されます。|
|<xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>|既定の選択モード。 セルをクリックすると、そのセルが選択されます。 行ヘッダーをクリックすると、行全体が選択されます。|

> [!NOTE]
> 実行時に選択モードを変更すると、現在の選択範囲が自動的にクリアされます。

既定では、複数の行、列、またはセルを選択してマウスでドラッグしたり、CTRL キーまたは SHIFT キーを押しながら選択範囲を拡張または変更したり、左上のヘッダーセルをクリックしてコントロール内のすべてのセルを選択したりすることができます。 この動作を回避するには、プロパティをに設定し <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> `false` ます。

<xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect>モードとモードでは、 <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> ユーザーが行を選択して del キーを押すことにより、行を削除できます。 ユーザーが行を削除できるのは、現在のセルが編集モードではなく、 <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A> プロパティがに設定されてい `true` て、基になるデータソースがユーザーによる行の削除をサポートしている場合のみです。 これらの設定では、プログラムによる行の削除が妨げられないことに注意してください。

## <a name="programmatic-selection"></a>プログラムによる選択

現在の選択モードでは、ユーザーが選択するだけでなく、プログラムによる選択の動作が制限されます。 `Selected`コントロールに存在するセル、行、または列のプロパティを設定することにより、現在の選択項目をプログラムで変更でき <xref:System.Windows.Forms.DataGridView> ます。 選択モードに応じて、メソッドを使用してコントロール内のすべてのセルを選択することもでき <xref:System.Windows.Forms.DataGridView.SelectAll%2A> ます。 選択範囲をクリアするには、メソッドを使用し <xref:System.Windows.Forms.DataGridView.ClearSelection%2A> ます。

<xref:System.Windows.Forms.DataGridView.MultiSelect%2A>プロパティがに設定されている場合は `true` 、 <xref:System.Windows.Forms.DataGridView> 要素のプロパティを変更することによって、要素を追加したり、選択から削除したりでき `Selected` ます。 それ以外の場合、 `Selected` 1 つの要素に対してプロパティをに設定すると、 `true` その他の要素が自動的に選択から削除されます。

プロパティの値を変更して <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> も、現在の選択内容は変更されないことに注意してください。

現在選択されているセル、行、または列のコレクションを取得する <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> には、コントロールの、、の各プロパティを使用し <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> <xref:System.Windows.Forms.DataGridView> ます。 コントロールのすべてのセルが選択されている場合、これらのプロパティへのアクセスは非効率的です。 この場合、パフォーマンスが低下しないようにするには、最初にメソッドを使用し <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> ます。 また、選択したセル、行、または列の数を決定するために、これらのコレクションにアクセスするのは効率的ではありません。 代わりに、、 <xref:System.Windows.Forms.DataGridView.GetCellCount%2A> <xref:System.Windows.Forms.DataGridViewRowCollection.GetRowCount%2A> 、またはのいずれかのメソッドを使用して、値を渡す必要があり <xref:System.Windows.Forms.DataGridViewColumnCollection.GetColumnCount%2A> <xref:System.Windows.Forms.DataGridViewElementStates.Selected> ます。

> [!TIP]
> 選択したセルのプログラムによる使用方法を示すコード例については、「クラスの概要」を参照して <xref:System.Windows.Forms.DataGridView> ください。

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>
- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>
- <xref:System.Windows.Forms.DataGridViewSelectionMode>
- [Windows フォーム DataGridView コントロールでの選択およびクリップボードの使用](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
- [方法: Windows フォーム DataGridView コントロールの選択モードを設定する](how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control.md)
