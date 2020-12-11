---
title: '方法: ショートカット メニューを TreeView ノードに追加する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- shortcut menus [Windows Forms], adding to TreeView controls
- TreeView control [Windows Forms], adding shortcut menus
- tree nodes in TreeView control [Windows Forms], shortcut menus
ms.assetid: a23c6752-fd8f-44ad-b781-bab37962fc7c
ms.openlocfilehash: f818cccb3103866af993f1aff527a9c1a7c82109
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980959"
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treeview-node"></a>方法: ショートカット メニューを TreeView ノードに追加する
Windows フォームコントロールは、 <xref:System.Windows.Forms.TreeView> Windows エクスプローラーの左側のウィンドウに表示されるファイルやフォルダーと同様に、ノードの階層を表示します。 プロパティを設定することにより、 <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> ユーザーがコントロールを右クリックしたときに、状況に応じた操作をユーザーに提供でき <xref:System.Windows.Forms.TreeView> ます。 コンポーネントを個々のアイテムに関連付けることにより <xref:System.Windows.Forms.ContextMenuStrip> <xref:System.Windows.Forms.TreeNode> 、カスタマイズされたレベルのショートカットメニュー機能をコントロールに追加でき <xref:System.Windows.Forms.TreeView> ます。  
  
### <a name="to-associate-a-shortcut-menu-with-a-treenode-programmatically"></a>ショートカットメニューをプログラムによって TreeNode に関連付けるには  
  
1. <xref:System.Windows.Forms.TreeView>適切なプロパティ設定を使用してコントロールをインスタンス化し、ルートを作成 <xref:System.Windows.Forms.TreeNode> して、サブノードを追加します。  
  
2. コンポーネントをインスタンス化し <xref:System.Windows.Forms.ContextMenuStrip> 、実行時に <xref:System.Windows.Forms.ToolStripMenuItem> 使用できるようにする各操作のを追加します。  
  
3. <xref:System.Windows.Forms.TreeNode.ContextMenuStrip%2A>適切なのプロパティを、 <xref:System.Windows.Forms.TreeNode> 作成するショートカットメニューに設定します。  
  
4. このプロパティを設定すると、ノードを右クリックしたときにショートカットメニューが表示されます。  
  
 次のコード例では、 <xref:System.Windows.Forms.TreeView> <xref:System.Windows.Forms.ContextMenuStrip> のルートに関連付けられた基本とを作成し <xref:System.Windows.Forms.TreeNode> <xref:System.Windows.Forms.TreeView> ます。 メニューの選択肢は、開発中のに適したものにカスタマイズする必要があり <xref:System.Windows.Forms.TreeView> ます。 また、 <xref:System.Windows.Forms.ToolStripItem.Click> これらのメニュー項目のイベントを処理するコードを記述することもできます。  
  
 [!code-cpp[System.Windows.Forms.TreeNodeContextMenuStrip#1](~/samples/snippets/cpp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/cpp/Form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.TreeNodeContextMenuStrip#1](~/samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.TreeNodeContextMenuStrip#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.ContextMenuStrip>
- [TreeView コントロール](treeview-control-windows-forms.md)
