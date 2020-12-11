---
title: ListBox コントロールの概要
ms.date: 03/30/2017
f1_keywords:
- ListBox
helpviewer_keywords:
- list boxes [Windows Forms], about list boxes
- ListBox control [Windows Forms], about ListBox control
ms.assetid: 37ea226b-6fc8-4c70-936a-c6af4e0cad4c
ms.openlocfilehash: 1abf8bea5c786f2ce326631370fa294ada09a92c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982959"
---
# <a name="listbox-control-overview-windows-forms"></a>ListBox コントロールの概要 (Windows フォーム)
Windows フォームコントロールには、 <xref:System.Windows.Forms.ListBox> ユーザーが1つ以上の項目を選択できる一覧が表示されます。 項目の合計数が表示可能な数を超えると、スクロールバーが自動的にコントロールに追加され <xref:System.Windows.Forms.ListBox> ます。 プロパティがに設定されている場合 <xref:System.Windows.Forms.ListBox.MultiColumn%2A> `true` 、リストボックスは複数の列に項目を表示し、水平スクロールバーが表示されます。 プロパティがに設定されている場合 <xref:System.Windows.Forms.ListBox.MultiColumn%2A> `false` 、リストボックスには項目が1つの列に表示され、垂直スクロールバーが表示されます。 <xref:System.Windows.Forms.ListBox.ScrollAlwaysVisible%2A>をに設定すると、 `true` アイテムの数に関係なく、スクロールバーが表示されます。 プロパティは、 <xref:System.Windows.Forms.ListBox.SelectionMode%2A> 一度に選択できるリスト項目の数を決定します。  
  
## <a name="ways-to-change-the-listbox-control"></a>ListBox コントロールを変更する方法  
 プロパティは、 <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> リストボックスで最初に選択された項目に対応する整数値を返します。 コードの値を変更することで、選択した項目をプログラムで変更できます。 <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> リスト内の対応する項目は、Windows フォーム上で強調表示されます。 項目が選択されていない場合、 <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> 値は-1 になります。 リスト内の最初の項目が選択されている場合、 <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> 値は0です。 複数の項目が選択されている場合、値は、 <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> リストの最初に表示される選択された項目を反映します。 <xref:System.Windows.Forms.ListBox.SelectedItem%2A>プロパティはに似てい <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> ますが、項目自体 (通常は文字列値) を返します。 <xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A>プロパティはリスト内の項目の数を反映し、プロパティの値は <xref:System.Windows.Forms.ListBox.ObjectCollection.Count%2A> 常に最大値より1つ多くなり <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> ます。これは、 <xref:System.Windows.Forms.ListBox.SelectedIndex%2A> が0から始まるためです。  
  
 コントロールの項目を追加または削除するには、 <xref:System.Windows.Forms.ListBox> <xref:System.Windows.Forms.ListBox.ObjectCollection.Add%2A> 、 <xref:System.Windows.Forms.ListBox.ObjectCollection.Insert%2A> 、 <xref:System.Windows.Forms.ListBox.ObjectCollection.Clear%2A> またはメソッドを使用し <xref:System.Windows.Forms.ListBox.ObjectCollection.Remove%2A> ます。 または、デザイン時にプロパティを使用して、リストに項目を追加することもでき <xref:System.Windows.Forms.ListBox.Items%2A> ます。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.ListBox>
- [方法: Windows フォームの ComboBox、ListBox、または CheckedListBox コントロールに項目を追加または削除する](add-and-remove-items-from-a-wf-combobox.md)
- [方法: Windows フォーム ComboBox、ListBox、または CheckedListBox コントロールを並べ替える](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [方法: Windows フォームの ComboBox または ListBox コントロールをデータにバインドする](how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md)
- [ComboBox コントロールの概要](combobox-control-overview-windows-forms.md)
- [CheckedListBox コントロールの概要](checkedlistbox-control-overview-windows-forms.md)
- [オプションのリストを表示するための Windows フォーム コントロール](windows-forms-controls-used-to-list-options.md)
- [方法: Windows フォーム ComboBox、ListBox、または CheckedListBox コントロールのルックアップ テーブルを作成する](create-a-lookup-table-for-a-wf-combobox-listbox.md)
