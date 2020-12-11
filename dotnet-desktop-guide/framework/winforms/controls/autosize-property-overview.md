---
title: AutoSize プロパティの概要
ms.date: 03/30/2017
helpviewer_keywords:
- sizing [Windows Forms], automatic
- layout [Windows Forms], AutoSize
- automatic sizing
- AutoSizeMode property
ms.assetid: 62fd82a2-9565-4f65-925b-9d1e66dc4e7d
ms.openlocfilehash: eb87616c2ddcf9a4ab62245d365763ee57ffb964
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96975146"
---
# <a name="autosize-property-overview"></a>AutoSize プロパティの概要
プロパティを使用すると、 <xref:System.Windows.Forms.Control.AutoSize%2A> 必要に応じてコントロールのサイズを変更し、プロパティで指定された値を得ることができ <xref:System.Windows.Forms.Control.PreferredSize%2A> ます。 特定のコントロールのサイズ変更動作を調整するには、プロパティを設定し `AutoSizeMode` ます。

## <a name="autosize-behavior"></a>AutoSize 動作
 一部のコントロールのみが <xref:System.Windows.Forms.Control.AutoSize%2A> プロパティをサポートしています。 また、プロパティをサポートする一部のコントロールは、 <xref:System.Windows.Forms.Control.AutoSize%2A> プロパティもサポートし `AutoSizeMode` ます。

 プロパティは、プロパティが <xref:System.Windows.Forms.Control.AutoSize%2A> 存在する場合に、特定のコントロールの種類とプロパティの値に応じて、多少異なる動作をし `AutoSizeMode` ます。 次の表では、常に true になる動作について説明し、それぞれの簡単な説明を示します。

|常に真の動作|説明|
|--------------------------|-----------------|
|自動サイズ変更は、実行時の機能です。|これは、コントロールが拡大または縮小されず、それ以上の効果がないことを意味します。|
|コントロールのサイズが変更された場合、プロパティの値は <xref:System.Windows.Forms.Control.Location%2A> 常に一定のままになります。|コントロールのコンテンツのサイズが大きくなると、コントロールは右および下方向に拡大します。 コントロールが左に拡大されることはありません。|
|<xref:System.Windows.Forms.Control.Dock%2A>プロパティと <xref:System.Windows.Forms.Control.Anchor%2A> プロパティは、がの場合に受け入れられ <xref:System.Windows.Forms.Control.AutoSize%2A> `true` ます。|コントロールのプロパティの値 <xref:System.Windows.Forms.Control.Location%2A> は、正しい値に調整されます。<br /><br /> **メモ**<xref:System.Windows.Forms.Label>コントロールは、このルールの例外です。 ドッキングされた <xref:System.Windows.Forms.Label> コントロールのプロパティの値をに設定すると <xref:System.Windows.Forms.Control.AutoSize%2A> `true` 、 <xref:System.Windows.Forms.Label> コントロールは伸縮しません。|
|コントロールの <xref:System.Windows.Forms.Control.MaximumSize%2A> プロパティと <xref:System.Windows.Forms.Control.MinimumSize%2A> プロパティは、プロパティの値に関係なく、常に受け入れられ <xref:System.Windows.Forms.Control.AutoSize%2A> ます。|<xref:System.Windows.Forms.Control.MaximumSize%2A>プロパティと <xref:System.Windows.Forms.Control.MinimumSize%2A> プロパティは、プロパティの影響を受けません <xref:System.Windows.Forms.Control.AutoSize%2A> 。|
|既定では、最小サイズは設定されていません。|これは、コントロールが [圧縮] に設定されていて、 <xref:System.Windows.Forms.Control.AutoSize%2A> 内容がない場合、 <xref:System.Windows.Forms.Control.Size%2A> プロパティの値が0、0になることを意味します。 この場合、コントロールはポイントまで縮小され、すぐには表示されません。|
|コントロールがメソッドを実装していない場合 <xref:System.Windows.Forms.Control.GetPreferredSize%2A> 、メソッドは、 <xref:System.Windows.Forms.Control.GetPreferredSize%2A> プロパティに割り当てられた最後の値を返し <xref:System.Windows.Forms.Control.Size%2A> ます。|これは、をに設定しても効果がないことを意味 <xref:System.Windows.Forms.Control.AutoSize%2A> `true` します。|
|セル内のコントロールは、 <xref:System.Windows.Forms.TableLayoutPanel> に到達するまでセルに合わせて縮小 <xref:System.Windows.Forms.Control.MinimumSize%2A> されます。|このサイズは、最大サイズとして適用されます。 これは、セルが <xref:System.Windows.Forms.SizeType.AutoSize> 行または列の一部である場合には当てはまりません。|

## <a name="autosizemode-property"></a>System.windows.forms.datagridviewcolumn.autosizemode プロパティ
 `AutoSizeMode`プロパティを使用すると、既定の動作をより細かく制御 <xref:System.Windows.Forms.Control.AutoSize%2A> できます。 プロパティは、 `AutoSizeMode` コントロールがそのコンテンツに対してどのようにサイズを調整するかを指定します。 たとえば、コンテンツには、コントロールのテキスト <xref:System.Windows.Forms.Button> やコンテナーの子コントロールなどがあります。

 次の表に、 <xref:System.Windows.Forms.AutoSizeMode> 各設定 elicits の動作の設定と説明を示します。

|System.windows.forms.datagridviewcolumn.autosizemode の設定|動作|
|--------------------------|--------------|
|GrowAndShrink|コントロールは、コンテンツを囲むように拡大または縮小されます。<br /><br /> <xref:System.Windows.Forms.Control.MinimumSize%2A>値と <xref:System.Windows.Forms.Control.MaximumSize%2A> 値は受け入れられますが、プロパティの現在の値 <xref:System.Windows.Forms.Control.Size%2A> は無視されます。<br /><br /> これは、プロパティを持つコントロールと同じ動作 <xref:System.Windows.Forms.Control.AutoSize%2A> `AutoSizeMode` です。プロパティはありません。|
|GrowOnly|コントロールは、コンテンツを含めるために必要なだけ拡大されますが、プロパティで指定された値より小さくなることはありません <xref:System.Windows.Forms.Control.Size%2A> 。<br /><br /> これは、`AutoSizeMode` の既定値です。|

## <a name="controls-that-support-the-autosize-property"></a>AutoSize プロパティをサポートするコントロール
 次の表に、プロパティおよびプロパティをサポートするコントロールを示し <xref:System.Windows.Forms.Control.AutoSize%2A> `AutoSizeMode` ます。

|AutoSize のサポート|コントロール型|
|----------------------|------------------|
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> サポートされるプロパティ。<br />-プロパティがありません `AutoSizeMode` 。|<xref:System.Windows.Forms.CheckBox><br /><br /> <xref:System.Windows.Forms.DomainUpDown><br /><br /> <xref:System.Windows.Forms.Label><br /><br /> <xref:System.Windows.Forms.LinkLabel><br /><br /> <xref:System.Windows.Forms.MaskedTextBox> ( <xref:System.Windows.Forms.TextBox> ベース)<br /><br /> <xref:System.Windows.Forms.NumericUpDown><br /><br /> <xref:System.Windows.Forms.RadioButton><br /><br /> <xref:System.Windows.Forms.TextBox><br /><br /> <xref:System.Windows.Forms.TrackBar>|
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> サポートされるプロパティ。<br />-   `AutoSizeMode` サポートされるプロパティ。|<xref:System.Windows.Forms.Button><br /><br /> <xref:System.Windows.Forms.CheckedListBox><br /><br /> <xref:System.Windows.Forms.FlowLayoutPanel><br /><br /> <xref:System.Windows.Forms.Form><br /><br /> <xref:System.Windows.Forms.GroupBox><br /><br /> <xref:System.Windows.Forms.Panel><br /><br /> <xref:System.Windows.Forms.TableLayoutPanel>|
|-プロパティがありません <xref:System.Windows.Forms.Control.AutoSize%2A> 。|<xref:System.Windows.Forms.CheckedListBox><br /><br /> <xref:System.Windows.Forms.ComboBox><br /><br /> <xref:System.Windows.Forms.DataGridView><br /><br /> <xref:System.Windows.Forms.DateTimePicker><br /><br /> <xref:System.Windows.Forms.ListBox><br /><br /> <xref:System.Windows.Forms.ListView><br /><br /> <xref:System.Windows.Forms.MaskedTextBox><br /><br /> <xref:System.Windows.Forms.MonthCalendar><br /><br /> <xref:System.Windows.Forms.ProgressBar><br /><br /> <xref:System.Windows.Forms.PropertyGrid><br /><br /> <xref:System.Windows.Forms.RichTextBox><br /><br /> <xref:System.Windows.Forms.SplitContainer><br /><br /> <xref:System.Windows.Forms.TabControl><br /><br /> <xref:System.Windows.Forms.TabPage><br /><br /> <xref:System.Windows.Forms.TreeView><br /><br /> <xref:System.Windows.Forms.WebBrowser><br /><br /> <xref:System.Windows.Forms.ScrollBar>|

## <a name="autosize-in-the-design-environment"></a>デザイン環境で AutoSize を作成する
 次の表では、デザイン時のコントロールのサイズ変更動作を、プロパティとプロパティの値に基づいて説明し <xref:System.Windows.Forms.Control.AutoSize%2A> `AutoSizeMode` ます。

 プロパティをオーバーライドして、 <xref:System.Windows.Forms.Design.ControlDesigner.SelectionRules%2A> 特定のコントロールがユーザーがサイズ変更可能な状態であるかどうかを判断します。 次の表では、"できません" は " <xref:System.Windows.Forms.Design.SelectionRules.Moveable> 可能" という意味です <xref:System.Windows.Forms.Design.SelectionRules.AllSizeable> <xref:System.Windows.Forms.Design.SelectionRules.Moveable> 。

|AutoSize 設定|デザイン時のサイズ変更ジェスチャ|
|-----------------------|---------------------------------|
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> = `true`<br />-プロパティがありません `AutoSizeMode` 。|ユーザーはデザイン時にコントロールのサイズを変更できません。ただし、次のコントロールは除きます。<br /><br /> -   <xref:System.Windows.Forms.TextBox><br />-   <xref:System.Windows.Forms.MaskedTextBox><br />-   <xref:System.Windows.Forms.RichTextBox><br />-   <xref:System.Windows.Forms.TrackBar>|
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> = `true`<br />-   `AutoSizeMode` = <xref:System.Windows.Forms.AutoSizeMode.GrowAndShrink>|ユーザーはデザイン時にコントロールのサイズを変更することはできません。|
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> = `true`<br />-   `AutoSizeMode` = <xref:System.Windows.Forms.AutoSizeMode.GrowOnly>|ユーザーは、デザイン時にコントロールのサイズを変更できます。 プロパティが設定されている場合、 <xref:System.Windows.Forms.Control.Size%2A> ユーザーはコントロールのサイズのみを増やすことができます。|
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> = `false`、、または <xref:System.Windows.Forms.Control.AutoSize%2A> プロパティが非表示になっています。|ユーザーはデザイン時にコントロールのサイズを変更できます。|

> [!NOTE]
> 生産性を最大限に高めるために、Visual Studio の Windows フォームデザイナーは <xref:System.Windows.Forms.Control.AutoSize%2A> クラスのプロパティをシャドウし <xref:System.Windows.Forms.Form> ます。 デザイン時には、 <xref:System.Windows.Forms.Control.AutoSize%2A> 実際の設定に関係なく、プロパティがに設定されているかのようにフォームが動作し `false` ます。 実行時に特別な特別な特別は行われず、プロパティは <xref:System.Windows.Forms.Control.AutoSize%2A> プロパティ設定によって指定されたとおりに適用されます。

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.Control.AutoSize%2A>
- <xref:System.Windows.Forms.Control.PreferredSize%2A>
- <xref:System.Windows.Forms.Control.GetPreferredSize%2A>
