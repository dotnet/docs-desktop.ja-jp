---
title: DataGrid コントロールのキーボードショートカット
ms.date: 03/30/2017
helpviewer_keywords:
- keyboard shortcuts [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], navigation keys
ms.assetid: a01780f9-20d5-4f5f-808f-c790c9a007a5
ms.openlocfilehash: 6693531b8d0e820a68d75bf5da40f4169fd244f2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982968"
---
# <a name="keyboard-shortcuts-for-the-windows-forms-datagrid-control"></a>Windows フォームの DataGrid コントロール内の移動に使用できるキーボード ショートカット
> [!NOTE]
> <xref:System.Windows.Forms.DataGridView> コントロールは、<xref:System.Windows.Forms.DataGrid> コントロールに代わると共に追加の機能を提供します。ただし、<xref:System.Windows.Forms.DataGrid> コントロールは、下位互換性を保つ目的および将来使用する目的で保持されます。 詳細については、「[Windows フォームの DataGridView コントロールと DataGrid コントロールの違いについて](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)」を参照してください。  
  
 次の表に、Windows フォームコントロール内のナビゲーションに使用できるキーボードショートカットを示し <xref:System.Windows.Forms.DataGrid> ます。  
  
|アクション|ショートカット|  
|------------|--------------|  
|セルエントリを完成させ、次のセルに下へ移動します。<br /><br /> フォーカスが子テーブルのリンクにある場合は、そのテーブルに移動します。|Enter|  
|セルの編集モードの場合は、セルの編集をキャンセルします。<br /><br /> マーキーを選択した場合は、行の編集をキャンセルします。|Esc|  
|セルを編集するときに、挿入位置の前にある文字を削除します。|BackSpace|  
|セルを編集するときに、挿入位置の後の文字を削除します。|DELETE|  
|現在の行の最初のセルに移動します。|ホーム|  
|現在の行の最後のセルに移動します。|End|  
|現在のセルの文字を強調表示し、行の末尾にカーソルを置きます。 セルをダブルクリックするのと同じ動作です。|F2|  
|フォーカスがセルにある場合は、行の次のセルに移動します。<br /><br /> フォーカスが行の最後のセルにある場合は、行の最初の子テーブルリンクに移動し、それを展開します。<br /><br /> フォーカスが子リンクにある場合は、次の子リンクに移動します。<br /><br /> フォーカスが最後の子リンクにある場合は、次の行の最初のセルに移動します。|Tab|  
|フォーカスがセルにある場合は、行の前のセルに移動します。<br /><br /> フォーカスが行の最初のセルにある場合は、前の行の最後に展開された子テーブルへのリンクに移動するか、前の行の最後のセルに移動します。<br /><br /> フォーカスが子リンクにある場合は、前の子リンクに移動します。<br /><br /> 最初の子リンクにフォーカスがある場合は、前の行の最後のセルに移動します。|Shift + Tab|  
|タブオーダーの次のコントロールに移動します。|Ctrl + Tab|  
|タブオーダーで、前のコントロールに移動します。|Ctrl + Shift + Tab|  
|子テーブルの場合は、親テーブルに移動します。 [戻る] ボタンをクリックした場合と同じ動作です。|Alt + ←|  
|子テーブルのリンクを展開します。 ALT + ↓キーを押すと、選択したリンクだけでなく、すべてのリンクが展開されます。|ALT + ↓または CTRL + プラス記号 (+)|  
|子テーブルリンクを折りたたみます。 ALT + ↑キーを押すと、選択されているものだけでなく、すべてのリンクが折りたたまれます。|ALT + ↑または CTRL + マイナス記号|  
|矢印の方向にある、空白以外の最も遠いセルに移動します。|CTRL + 方向キー|  
|矢印の方向にある1行を選択します (子テーブルリンクは除く)。|SHIFT + ↑/↓|  
|矢印の方向に (子テーブルリンクを除く)、選択範囲を最も遠い空白ではない行に拡張します。|CTRL + SHIFT + ↑/↓|  
|左上隅のセルに移動します。|Ctrl&lt;/localizedText&gt; + &lt;localizedText&gt;Home|  
|右下のセルに移動します。|Ctrl&lt;/localizedText&gt; + &lt;localizedText&gt;End|  
|選択範囲を先頭行に拡張します。|Ctrl</localizedText> + <localizedText>Shift</localizedText> + <localizedText>Home|  
|選択範囲を一番下の行に拡張します。|Ctrl</localizedText> + <localizedText>Shift</localizedText> + <localizedText>End|  
|現在の行を選択します (子テーブルのリンクは除く)。|SHIFT + SPACE|  
|グリッド全体を選択します (子テーブルリンクは除く)。|Ctrl + A|  
|親の行を子テーブルに表示します。|Ctrl + PageDown|  
|子テーブルの場合は、親の行を非表示にします。|Ctrl + PageUp|  
|選択範囲を1画面下に拡張します (子テーブルリンクは除く)。|Shift + PageDown|  
|選択範囲を1画面上に拡張します (子テーブルリンクは除く)。|Shift + PageUp|  
|現在の <xref:System.Windows.Forms.DataGrid.EndEdit%2A> 行に対してメソッドを呼び出します。|Ctrl + Enter|  
|<xref:System.DBNull.Value?displayProperty=nameWithType>編集モードの場合は、セルに値を入力します。|Ctrl + 0|  
  
## <a name="see-also"></a>関連項目

- [DataGrid コントロールの概要](datagrid-control-overview-windows-forms.md)
- [DataGrid コントロール](datagrid-control-windows-forms.md)
