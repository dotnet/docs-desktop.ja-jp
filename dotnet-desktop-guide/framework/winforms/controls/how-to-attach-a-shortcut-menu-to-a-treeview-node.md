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
# <a name="how-to-attach-a-shortcut-menu-to-a-treeview-node"></a><span data-ttu-id="e07ff-102">方法: ショートカット メニューを TreeView ノードに追加する</span><span class="sxs-lookup"><span data-stu-id="e07ff-102">How to: Attach a ShortCut Menu to a TreeView Node</span></span>
<span data-ttu-id="e07ff-103">Windows フォームコントロールは、 <xref:System.Windows.Forms.TreeView> Windows エクスプローラーの左側のウィンドウに表示されるファイルやフォルダーと同様に、ノードの階層を表示します。</span><span class="sxs-lookup"><span data-stu-id="e07ff-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control displays a hierarchy of nodes, similar to the files and folders displayed in the left pane of Windows Explorer.</span></span> <span data-ttu-id="e07ff-104">プロパティを設定することにより、 <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> ユーザーがコントロールを右クリックしたときに、状況に応じた操作をユーザーに提供でき <xref:System.Windows.Forms.TreeView> ます。</span><span class="sxs-lookup"><span data-stu-id="e07ff-104">By setting the <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property, you can provide context-sensitive operations to the user when they right-click the <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="e07ff-105">コンポーネントを個々のアイテムに関連付けることにより <xref:System.Windows.Forms.ContextMenuStrip> <xref:System.Windows.Forms.TreeNode> 、カスタマイズされたレベルのショートカットメニュー機能をコントロールに追加でき <xref:System.Windows.Forms.TreeView> ます。</span><span class="sxs-lookup"><span data-stu-id="e07ff-105">By associating a <xref:System.Windows.Forms.ContextMenuStrip> component with individual <xref:System.Windows.Forms.TreeNode> items, you can add a customized level of shortcut menu functionality to your <xref:System.Windows.Forms.TreeView> controls.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-a-treenode-programmatically"></a><span data-ttu-id="e07ff-106">ショートカットメニューをプログラムによって TreeNode に関連付けるには</span><span class="sxs-lookup"><span data-stu-id="e07ff-106">To associate a shortcut menu with a TreeNode programmatically</span></span>  
  
1. <span data-ttu-id="e07ff-107"><xref:System.Windows.Forms.TreeView>適切なプロパティ設定を使用してコントロールをインスタンス化し、ルートを作成 <xref:System.Windows.Forms.TreeNode> して、サブノードを追加します。</span><span class="sxs-lookup"><span data-stu-id="e07ff-107">Instantiate a <xref:System.Windows.Forms.TreeView> control with the appropriate property settings, create a root <xref:System.Windows.Forms.TreeNode>, and then add subnodes.</span></span>  
  
2. <span data-ttu-id="e07ff-108">コンポーネントをインスタンス化し <xref:System.Windows.Forms.ContextMenuStrip> 、実行時に <xref:System.Windows.Forms.ToolStripMenuItem> 使用できるようにする各操作のを追加します。</span><span class="sxs-lookup"><span data-stu-id="e07ff-108">Instantiate a <xref:System.Windows.Forms.ContextMenuStrip> component, and then add a <xref:System.Windows.Forms.ToolStripMenuItem> for each operation you want to make available at run time.</span></span>  
  
3. <span data-ttu-id="e07ff-109"><xref:System.Windows.Forms.TreeNode.ContextMenuStrip%2A>適切なのプロパティを、 <xref:System.Windows.Forms.TreeNode> 作成するショートカットメニューに設定します。</span><span class="sxs-lookup"><span data-stu-id="e07ff-109">Set the <xref:System.Windows.Forms.TreeNode.ContextMenuStrip%2A> property of the appropriate <xref:System.Windows.Forms.TreeNode> to the shortcut menu you create.</span></span>  
  
4. <span data-ttu-id="e07ff-110">このプロパティを設定すると、ノードを右クリックしたときにショートカットメニューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e07ff-110">When this property is set, the shortcut menu will be displayed when you right-click the node.</span></span>  
  
 <span data-ttu-id="e07ff-111">次のコード例では、 <xref:System.Windows.Forms.TreeView> <xref:System.Windows.Forms.ContextMenuStrip> のルートに関連付けられた基本とを作成し <xref:System.Windows.Forms.TreeNode> <xref:System.Windows.Forms.TreeView> ます。</span><span class="sxs-lookup"><span data-stu-id="e07ff-111">The following code example creates a basic <xref:System.Windows.Forms.TreeView> and <xref:System.Windows.Forms.ContextMenuStrip> associated with the root <xref:System.Windows.Forms.TreeNode> of the <xref:System.Windows.Forms.TreeView>.</span></span> <span data-ttu-id="e07ff-112">メニューの選択肢は、開発中のに適したものにカスタマイズする必要があり <xref:System.Windows.Forms.TreeView> ます。</span><span class="sxs-lookup"><span data-stu-id="e07ff-112">You will need to customize the menu choices to those that fit the <xref:System.Windows.Forms.TreeView> you are developing.</span></span> <span data-ttu-id="e07ff-113">また、 <xref:System.Windows.Forms.ToolStripItem.Click> これらのメニュー項目のイベントを処理するコードを記述することもできます。</span><span class="sxs-lookup"><span data-stu-id="e07ff-113">Additionally, you will want to write code to handle the <xref:System.Windows.Forms.ToolStripItem.Click> events for these menu items.</span></span>  
  
 [!code-cpp[System.Windows.Forms.TreeNodeContextMenuStrip#1](~/samples/snippets/cpp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/cpp/Form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.TreeNodeContextMenuStrip#1](~/samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.TreeNodeContextMenuStrip#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e07ff-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="e07ff-114">See also</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip>
- [<span data-ttu-id="e07ff-115">TreeView コントロール</span><span class="sxs-lookup"><span data-stu-id="e07ff-115">TreeView Control</span></span>](treeview-control-windows-forms.md)
