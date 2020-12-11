---
title: '方法: デザイナーを使用して TreeNode にショートカット メニューを割り当てる'
ms.date: 03/30/2017
helpviewer_keywords:
- shortcut menus [Windows Forms], attaching to TreeNodes
- TreeNode [Windows Forms], attaching a shortcut menu using Designer
ms.assetid: 8e45e184-1313-4f8f-90ff-2cd5789b2268
ms.openlocfilehash: eb3240d35309e03aa8ce949b9c5000f8581d2c2f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980960"
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treenode-using-the-designer"></a>方法: デザイナーを使用して TreeNode にショートカット メニューを割り当てる
Windows フォームコントロールは、 <xref:System.Windows.Forms.TreeView> windows オペレーティングシステムの Windows エクスプローラー機能の左ペインに表示されるファイルやフォルダーと同様に、ノードの階層を表示します。 プロパティを設定することにより、 <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> ユーザーがコントロールを右クリックしたときに、状況に応じた操作をユーザーに提供でき <xref:System.Windows.Forms.TreeView> ます。 コンポーネントを個々のアイテムに関連付けることにより <xref:System.Windows.Forms.ContextMenuStrip> <xref:System.Windows.Forms.TreeNode> 、カスタマイズされたレベルのショートカットメニュー機能をコントロールに追加でき <xref:System.Windows.Forms.TreeView> ます。

## <a name="to-associate-a-shortcut-menu-with-a-treenode-at-design-time"></a>デザイン時にショートカットメニューを TreeNode に関連付けるには

1. <xref:System.Windows.Forms.TreeView>フォームにコントロールを追加し、必要に応じてにノードを追加し <xref:System.Windows.Forms.TreeView> ます。 詳細については、「 [方法: Windows フォーム TreeView コントロールを使用してノードを追加および削除](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)する」を参照してください。

2. <xref:System.Windows.Forms.ContextMenuStrip>フォームにコンポーネントを追加し、実行時に使用できるようにするノードレベルの操作を表すメニュー項目をショートカットメニューに追加します。 詳細については、「 [方法: メニュー項目を ContextMenuStrip に追加](how-to-add-menu-items-to-a-contextmenustrip.md)する」を参照してください。

3. コントロールの [ **TreeNodeEditor** ] ダイアログボックス <xref:System.Windows.Forms.TreeView> を再び開き、編集するノードを選択し、 <xref:System.Windows.Forms.ContextMenuStrip> プロパティを追加したショートカットメニューに設定します。

4. このプロパティを設定すると、ノードを右クリックしたときにショートカットメニューが表示されます。

     また、 <xref:System.Windows.Forms.ToolStripItem.Click> これらのメニュー項目のイベントを処理するコードを記述することもできます。

## <a name="see-also"></a>関連項目

- [TreeView コントロール](treeview-control-windows-forms.md)
- [TreeView コントロールの概要](treeview-control-overview-windows-forms.md)
- [ContextMenuStrip コントロール](contextmenustrip-control.md)
