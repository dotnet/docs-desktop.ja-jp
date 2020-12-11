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
# <a name="how-to-attach-a-shortcut-menu-to-a-treenode-using-the-designer"></a><span data-ttu-id="31eee-102">方法: デザイナーを使用して TreeNode にショートカット メニューを割り当てる</span><span class="sxs-lookup"><span data-stu-id="31eee-102">How to: Attach a Shortcut Menu to a TreeNode Using the Designer</span></span>
<span data-ttu-id="31eee-103">Windows フォームコントロールは、 <xref:System.Windows.Forms.TreeView> windows オペレーティングシステムの Windows エクスプローラー機能の左ペインに表示されるファイルやフォルダーと同様に、ノードの階層を表示します。</span><span class="sxs-lookup"><span data-stu-id="31eee-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control displays a hierarchy of nodes, similar to the files and folders displayed in the left pane of the Windows Explorer feature in Windows operating systems.</span></span> <span data-ttu-id="31eee-104">プロパティを設定することにより、 <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> ユーザーがコントロールを右クリックしたときに、状況に応じた操作をユーザーに提供でき <xref:System.Windows.Forms.TreeView> ます。</span><span class="sxs-lookup"><span data-stu-id="31eee-104">By setting the <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property, you can provide context-sensitive operations to the user when they right-click the <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="31eee-105">コンポーネントを個々のアイテムに関連付けることにより <xref:System.Windows.Forms.ContextMenuStrip> <xref:System.Windows.Forms.TreeNode> 、カスタマイズされたレベルのショートカットメニュー機能をコントロールに追加でき <xref:System.Windows.Forms.TreeView> ます。</span><span class="sxs-lookup"><span data-stu-id="31eee-105">By associating a <xref:System.Windows.Forms.ContextMenuStrip> component with individual <xref:System.Windows.Forms.TreeNode> items, you can add a customized level of shortcut menu functionality to your <xref:System.Windows.Forms.TreeView> controls.</span></span>

## <a name="to-associate-a-shortcut-menu-with-a-treenode-at-design-time"></a><span data-ttu-id="31eee-106">デザイン時にショートカットメニューを TreeNode に関連付けるには</span><span class="sxs-lookup"><span data-stu-id="31eee-106">To associate a shortcut menu with a TreeNode at design time</span></span>

1. <span data-ttu-id="31eee-107"><xref:System.Windows.Forms.TreeView>フォームにコントロールを追加し、必要に応じてにノードを追加し <xref:System.Windows.Forms.TreeView> ます。</span><span class="sxs-lookup"><span data-stu-id="31eee-107">Add a <xref:System.Windows.Forms.TreeView> control to your form, and then add nodes to the <xref:System.Windows.Forms.TreeView> as needed.</span></span> <span data-ttu-id="31eee-108">詳細については、「 [方法: Windows フォーム TreeView コントロールを使用してノードを追加および削除](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31eee-108">For more information, see [How to: Add and Remove Nodes with the Windows Forms TreeView Control](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md).</span></span>

2. <span data-ttu-id="31eee-109"><xref:System.Windows.Forms.ContextMenuStrip>フォームにコンポーネントを追加し、実行時に使用できるようにするノードレベルの操作を表すメニュー項目をショートカットメニューに追加します。</span><span class="sxs-lookup"><span data-stu-id="31eee-109">Add a <xref:System.Windows.Forms.ContextMenuStrip> component to your form, and then add menu items to the shortcut menu that represent node-level operations you wish to make available at run time.</span></span> <span data-ttu-id="31eee-110">詳細については、「 [方法: メニュー項目を ContextMenuStrip に追加](how-to-add-menu-items-to-a-contextmenustrip.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31eee-110">For more information, see [How to: Add Menu Items to a ContextMenuStrip](how-to-add-menu-items-to-a-contextmenustrip.md).</span></span>

3. <span data-ttu-id="31eee-111">コントロールの [ **TreeNodeEditor** ] ダイアログボックス <xref:System.Windows.Forms.TreeView> を再び開き、編集するノードを選択し、 <xref:System.Windows.Forms.ContextMenuStrip> プロパティを追加したショートカットメニューに設定します。</span><span class="sxs-lookup"><span data-stu-id="31eee-111">Reopen the **TreeNodeEditor** dialog box for the <xref:System.Windows.Forms.TreeView> control, select the node to edit, and set its <xref:System.Windows.Forms.ContextMenuStrip> property to the shortcut menu that you added.</span></span>

4. <span data-ttu-id="31eee-112">このプロパティを設定すると、ノードを右クリックしたときにショートカットメニューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="31eee-112">When this property is set, the shortcut menu will be displayed when you right-click the node.</span></span>

     <span data-ttu-id="31eee-113">また、 <xref:System.Windows.Forms.ToolStripItem.Click> これらのメニュー項目のイベントを処理するコードを記述することもできます。</span><span class="sxs-lookup"><span data-stu-id="31eee-113">Additionally, you will want to write code to handle the <xref:System.Windows.Forms.ToolStripItem.Click> events for these menu items.</span></span>

## <a name="see-also"></a><span data-ttu-id="31eee-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="31eee-114">See also</span></span>

- [<span data-ttu-id="31eee-115">TreeView コントロール</span><span class="sxs-lookup"><span data-stu-id="31eee-115">TreeView Control</span></span>](treeview-control-windows-forms.md)
- [<span data-ttu-id="31eee-116">TreeView コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="31eee-116">TreeView Control Overview</span></span>](treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="31eee-117">ContextMenuStrip コントロール</span><span class="sxs-lookup"><span data-stu-id="31eee-117">ContextMenuStrip Control</span></span>](contextmenustrip-control.md)
