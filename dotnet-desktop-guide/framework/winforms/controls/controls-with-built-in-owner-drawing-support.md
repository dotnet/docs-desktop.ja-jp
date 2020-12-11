---
title: 組み込みのオーナー描画サポートを備えたコントロール
ms.date: 03/30/2017
ms.topic: overview
helpviewer_keywords:
- drawing [Windows Forms], owner
- drawing [Windows Forms], custom
- controls [Windows Forms], changing appearance
- custom drawing
- owner drawing
ms.assetid: 3823d01e-9610-43e6-864d-99f9b7c2b351
ms.openlocfilehash: a3c7b9eb2b7b19c8fe57cc656df64d0d0fdc4fdb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974267"
---
# <a name="controls-with-built-in-owner-drawing-support"></a>組み込みのオーナー描画サポートを備えたコントロール
Windows フォームのオーナー描画 (カスタム描画とも呼ばれます) は、特定のコントロールの外観を変更するための手法です。  
  
> [!NOTE]
> このトピックの "コントロール" という語は、またはから派生したクラスを意味するために使用され <xref:System.Windows.Forms.Control> <xref:System.ComponentModel.Component> ます。  
  
 通常、 <xref:System.Windows.Forms.Control.BackColor%2A> コントロールの外観を決定するためになどのプロパティ設定を使用して、ウィンドウの描画を自動的に処理します。 オーナー描画では、描画プロセスを引き継いで、プロパティでは設定できない外観の要素を変更できます。 たとえば、多くのコントロールでは表示されるテキストの色を設定できますが、1 つの色に制限されます。 オーナー描画では、テキストの一部分を黒で表示し、別の部分を赤で表示する、といったことができます。  
  
 実際には、オーナー描画はフォームでのグラフィックスの描画に似ています。 たとえば、フォームのイベントのハンドラーでグラフィックスメソッドを使用して <xref:System.Windows.Forms.Control.Paint> コントロールをエミュレートすること `ListBox` ができますが、すべてのユーザー操作を処理する独自のコードを記述する必要があります。 オーナー描画では、コントロールは独自のコードを使って内容を描画しますが、それ以外については組み込み機能がすべて保持されます。 グラフィックス メソッドを使うと、コントロール内の各項目を描画したり、各項目の一部だけカスタマイズして他の部分は既定の外観を使ったりすることができます。  
  
## <a name="owner-drawing-in-windows-forms-controls"></a>Windows フォーム コントロールでのオーナー描画  
 オーナー描画をサポートしているコントロールでオーナー描画を実行するには、通常、1 つのプロパティを設定し、1 つまたは複数のイベントを処理します。  
  
 オーナー描画をサポートしているほとんどのコントロールには、コントロールの描画時に描画関連のイベントが発生するかどうかを示す `OwnerDraw` または `DrawMode` プロパティがあります。  
  
 `OwnerDraw` または `DrawMode` プロパティを持たないコントロールには、自動的に発生する描画イベントを提供する `DataGridView` コントロールと、独自の描画関連イベントを持つ外部レンダリング クラスを使って描画される `ToolStrip` コントロールが含まれます。  
  
 さまざまな種類の描画イベントがありますが、標準的な描画イベントはコントロール内の 1 つの項目を描画するために発生します。 イベント ハンドラーは、描画される項目に関する情報と、その描画に使用できるツールを含む、`EventArgs` オブジェクトを受け取ります。 たとえば、このオブジェクトには通常、親コレクション内の項目のインデックス番号、 <xref:System.Drawing.Rectangle> 項目の表示境界を示す、および <xref:System.Drawing.Graphics> 描画メソッドを呼び出すためのオブジェクトが含まれます。 一部のイベントの `EventArgs` オブジェクトでは、項目に関する追加情報と、背景やフォーカス四角形などの項目の一部分を既定で描画するために呼び出すことができるメソッドが提供されます。  
  
 オーナー描画のカスタマイズを含む再利用可能なコントロールを作成するには、オーナー描画をサポートするコントロール クラスから派生する新しいクラスを作成します。 描画イベントを処理するのではなく、新しいクラスの適切な `On`<*イベント名*> メソッドのオーバーライドにオーナー描画のコードを組み込みます。 この場合、コントロールのユーザーがオーナー描画イベントを処理して追加のカスタマイズを提供できるように、基底クラスの `On`<*イベント名*> メソッドを呼び出す必要があります。  
  
 次の Windows フォーム コントロールは、すべてのバージョンの .NET Framework でオーナー描画をサポートします。  
  
- <xref:System.Windows.Forms.ListBox>  
  
- <xref:System.Windows.Forms.ComboBox>  
  
- <xref:System.Windows.Forms.MenuItem> (およびで <xref:System.Windows.Forms.MainMenu> 使用 <xref:System.Windows.Forms.ContextMenu> )  
  
- <xref:System.Windows.Forms.TabControl>  
  
 次のコントロールは、.NET Framework 2.0 でのみ所有者の描画をサポートします。  
  
- <xref:System.Windows.Forms.ToolTip>  
  
- <xref:System.Windows.Forms.ListView>  
  
- <xref:System.Windows.Forms.TreeView>  
  
 次のコントロールはオーナー描画をサポートしており、.NET Framework 2.0 で新しく追加されています。  
  
- <xref:System.Windows.Forms.DataGridView>  
  
- <xref:System.Windows.Forms.ToolStrip>  
  
 以下のセクションでは、これらの各コントロールについてさらに詳しく説明します。  
  
### <a name="listbox-and-combobox-controls"></a>ListBox コントロールと ComboBox コントロール  
 <xref:System.Windows.Forms.ListBox>コントロールとコントロールを使用すると、 <xref:System.Windows.Forms.ComboBox> コントロール内の個々の項目を1つのサイズで、またはさまざまなサイズで描画できます。  
  
> [!NOTE]
> コントロールはコントロール <xref:System.Windows.Forms.CheckedListBox> から派生し <xref:System.Windows.Forms.ListBox> ますが、オーナー描画をサポートしていません。  
  
 各項目を同じサイズで描画するには、 `DrawMode` プロパティをに設定し、イベントを処理し <xref:System.Windows.Forms.DrawMode.OwnerDrawFixed> `DrawItem` ます。  
  
 異なるサイズを使用して各項目を描画するには、 `DrawMode` プロパティをに設定 <xref:System.Windows.Forms.DrawMode.OwnerDrawVariable> し、イベントとイベントの両方を処理し `MeasureItem` `DrawItem` ます。 `MeasureItem` イベントを使うと、項目の `DrawItem` イベントが発生する前に、その項目のサイズを指定できます。  
  
 サンプル コードなど詳細については、次のトピックをご覧ください。  
  
- <xref:System.Windows.Forms.ListBox.DrawMode%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListBox.MeasureItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListBox.DrawItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ComboBox.DrawMode%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ComboBox.MeasureItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ComboBox.DrawItem?displayProperty=nameWithType>  
  
- [方法: ComboBox コントロールにサイズ変更可能なテキストを作成する](how-to-create-variable-sized-text-in-a-combobox-control.md)  
  
### <a name="menuitem-component"></a>MenuItem コンポーネント  
 コンポーネントは、 <xref:System.Windows.Forms.MenuItem> <xref:System.Windows.Forms.MainMenu> コンポーネントまたはコンポーネントの1つのメニュー項目を表し <xref:System.Windows.Forms.ContextMenu> ます。  
  
 を描画するには <xref:System.Windows.Forms.MenuItem> 、その `OwnerDraw` プロパティをに設定し、イベントを処理し `true` `DrawItem` ます。 `DrawItem` イベントが発生する前にメニュー項目のサイズをカスタマイズするには、項目の`MeasureItem` イベントを処理します。  
  
 サンプル コードなど詳細については、次のトピックをご覧ください。  
  
- <xref:System.Windows.Forms.MenuItem.OwnerDraw%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.MenuItem.DrawItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.MenuItem.MeasureItem?displayProperty=nameWithType>  
  
### <a name="tabcontrol-control"></a>TabControl コントロール  
 <xref:System.Windows.Forms.TabControl>コントロールを使用すると、コントロールに個々のタブを描画できます。 オーナー描画は、タブのみに影響します。 <xref:System.Windows.Forms.TabPage> コンテンツは影響を受けません。  
  
 で各タブを描画するには <xref:System.Windows.Forms.TabControl> 、 `DrawMode` プロパティをに設定 <xref:System.Windows.Forms.TabDrawMode.OwnerDrawFixed> し、イベントを処理し `DrawItem` ます。 このイベントは、コントロールにタブが表示されている場合にのみ、タブごとに 1 回発生します。  
  
 サンプル コードなど詳細については、次のトピックをご覧ください。  
  
- <xref:System.Windows.Forms.TabControl.DrawMode%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.TabControl.DrawItem?displayProperty=nameWithType>  
  
### <a name="tooltip-component"></a>ToolTip コンポーネント  
 <xref:System.Windows.Forms.ToolTip>コンポーネントを使用すると、表示されるときにツールヒント全体を描画できます。  
  
 を描画するには <xref:System.Windows.Forms.ToolTip> 、その `OwnerDraw` プロパティをに設定し、イベントを処理し `true` `Draw` ます。 イベントが発生する前にのサイズをカスタマイズするには、イベントを <xref:System.Windows.Forms.ToolTip> `Draw` 処理 `Popup` し、イベントハンドラーのプロパティを設定し <xref:System.Windows.Forms.PopupEventArgs.ToolTipSize%2A> ます。  
  
 サンプル コードなど詳細については、次のトピックをご覧ください。  
  
- <xref:System.Windows.Forms.ToolTip.OwnerDraw%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ToolTip.Draw?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ToolTip.Popup?displayProperty=nameWithType>  
  
### <a name="listview-control"></a>ListView コントロール  
 コントロールを使用すると、 <xref:System.Windows.Forms.ListView> コントロールに個々の項目、サブ項目、および列ヘッダーを描画できます。  
  
 コントロールのオーナー描画を有効にするには、`OwnerDraw` プロパティを `true` に設定します。  
  
 コントロール内の各項目を描画するには、`DrawItem` イベントを処理します。  
  
 プロパティがに設定されている場合に、コントロール内の各サブ項目または列ヘッダーを描画するには、 <xref:System.Windows.Forms.ListView.View%2A> <xref:System.Windows.Forms.View.Details> `DrawSubItem` イベントおよびイベントを処理し `DrawColumnHeader` ます。  
  
 サンプル コードなど詳細については、次のトピックをご覧ください。  
  
- <xref:System.Windows.Forms.ListView.OwnerDraw%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListView.DrawItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListView.DrawSubItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListView.DrawColumnHeader?displayProperty=nameWithType>  
  
### <a name="treeview-control"></a>TreeView コントロール  
 <xref:System.Windows.Forms.TreeView>コントロールを使用すると、コントロールに個々のノードを描画できます。  
  
 各ノードに表示されているテキストのみを描画するには、プロパティをに設定し、イベントを処理して `DrawMode` テキストを描画し <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawText> `DrawNode` ます。  
  
 各ノードのすべての要素を描画するには、 `DrawMode` プロパティをに設定し、イベントを <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawAll> 処理して `DrawNode` 必要な要素を描画します。たとえば、テキスト、アイコン、チェックボックス、プラス記号とマイナス記号、ノードを接続する線などです。  
  
 サンプル コードなど詳細については、次のトピックをご覧ください。  
  
- <xref:System.Windows.Forms.TreeView.DrawMode%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.TreeView.DrawNode?displayProperty=nameWithType>  
  
### <a name="datagridview-control"></a>DataGridView コントロール  
 コントロールを使用すると、 <xref:System.Windows.Forms.DataGridView> コントロールに個々のセルと行を描画できます。  
  
 個別のセルを描画するには、`CellPainting` イベントを処理します。  
  
 個別の行または行の要素を描画するには、`RowPrePaint` イベントと `RowPostPaint` イベントの一方または両方を処理します。 `RowPrePaint` イベントは行内のセルが描画される前に発生し、`RowPostPaint` イベントはセルが描画された後で発生します。 両方のイベントと `CellPainting` イベントを処理して、行の背景、個々のセル、行の前景を個別に描画できます。または、必要な部分については個別にカスタマイズを提供し、行の他の要素には既定の表示を使うこともできます。  
  
 サンプル コードなど詳細については、次のトピックをご覧ください。  
  
- <xref:System.Windows.Forms.DataGridView.CellPainting>  
  
- <xref:System.Windows.Forms.DataGridView.RowPrePaint>  
  
- <xref:System.Windows.Forms.DataGridView.RowPostPaint>  
  
- [方法 : Windows フォームの DataGridView コントロールのセルの外観をカスタマイズする](customize-the-appearance-of-cells-in-the-datagrid.md)  
  
- [方法: Windows フォームの DataGridView コントロールの行の外観をカスタマイズする](customize-the-appearance-of-rows-in-the-datagrid.md)  
  
### <a name="toolstrip-control"></a>ToolStrip コントロール  
 <xref:System.Windows.Forms.ToolStrip> また、派生したコントロールを使用すると、外観の任意の側面をカスタマイズできます。  
  
 コントロールのカスタム表示を提供するには、 <xref:System.Windows.Forms.ToolStrip> `Renderer` 、、 <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.ToolStripManager> 、またはのプロパティを <xref:System.Windows.Forms.ToolStripPanel> <xref:System.Windows.Forms.ToolStripContentPanel> オブジェクトに設定 `ToolStripRenderer` し、クラスによって提供される多数の描画イベントの1つ以上を処理し `ToolStripRenderer` ます。 または、 `Renderer` `ToolStripRenderer` 特定の <xref:System.Windows.Forms.ToolStripProfessionalRenderer> <xref:System.Windows.Forms.ToolStripSystemRenderer> EventName メソッドを実装またはオーバーライドする、、またはから派生した独自 `On` のクラスのインスタンスにプロパティを設定します。  
  
 サンプル コードなど詳細については、次のトピックをご覧ください。  
  
- <xref:System.Windows.Forms.ToolStripRenderer>  
  
- [方法: Windows フォームで ToolStrip コントロールのカスタムレンダラーを作成および設定する](create-and-set-a-custom-renderer-for-the-toolstrip-control-in-wf.md)  
  
- [方法: ToolStrip コントロールをカスタム描画する](how-to-custom-draw-a-toolstrip-control.md)  
  
## <a name="see-also"></a>関連項目

- [Windows フォームで使用するコントロール](controls-to-use-on-windows-forms.md)
