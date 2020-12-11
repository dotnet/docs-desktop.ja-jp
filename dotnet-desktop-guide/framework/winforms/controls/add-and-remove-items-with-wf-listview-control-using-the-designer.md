---
title: デザイナーを使用して ListView コントロールで項目を追加および削除する
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], populating
- ListView control [Windows Forms], adding list items
ms.assetid: 217611ee-fd11-4d39-9a54-a37c3e781be1
ms.openlocfilehash: cab40c556d9e5d21ce15bcd3d4da367bc08f33ab
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96975161"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control-using-the-designer"></a>方法: デザイナーで Windows フォーム ListView コントロールを使って項目を追加および削除する

項目を Windows フォームコントロールに追加するプロセスは、 <xref:System.Windows.Forms.ListView> 主に項目を指定し、その項目にプロパティを割り当てることによって構成されます。 リスト項目の追加または削除は、いつでも行うことができます。

次の手順では、コントロールを含むフォームを含む **Windows アプリケーション** プロジェクトが必要です <xref:System.Windows.Forms.ListView> 。 このようなプロジェクトの設定の詳細については、「 [方法: Windows フォームアプリケーションプロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project) する」および「 [方法: Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)する」を参照してください。

### <a name="to-add-or-remove-items-using-the-designer"></a>デザイナーを使用して項目を追加または削除するには

1. <xref:System.Windows.Forms.ListView> コントロールを選択します。

2. [**プロパティ**] ウィンドウで、プロパティの横に **ある省略記号 (** ![ 省略記号ボタン ([...]) をクリックして、プロパティの横にある [プロパティウィンドウ ](./media/visual-studio-ellipsis-button.png) ] ボタンをクリックします。 <xref:System.Windows.Forms.ListView.Items%2A>

     **ListViewItem Collection エディター** が表示されます。

3. 項目を追加するには、[ **追加** ] ボタンをクリックします。 その後、プロパティやプロパティなど、新しい項目のプロパティを設定でき <xref:System.Windows.Forms.ListView.Text%2A> <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> ます。

4. 項目を削除するには、項目を選択し、[ **削除** ] ボタンをクリックします。

## <a name="see-also"></a>関連項目

- [ListView コントロールの概要](listview-control-overview-windows-forms.md)
- [方法: Windows フォーム ListView コントロールに列を追加する](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [方法: Windows フォーム ListView コントロールの列にサブ項目を表示する](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [方法: Windows フォーム ListView コントロールのアイコンを表示する](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [方法: TreeView コントロールまたは ListView コントロール (Windows フォーム) にカスタム情報を追加する](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [方法: Windows フォーム ListView コントロールの項目をグループ化する](how-to-group-items-in-a-windows-forms-listview-control.md)
