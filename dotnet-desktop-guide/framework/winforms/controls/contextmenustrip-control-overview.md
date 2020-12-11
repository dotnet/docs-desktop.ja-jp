---
title: ContextMenuStrip コントロールの概要
ms.date: 03/30/2017
f1_keywords:
- ContextMenuStrip
helpviewer_keywords:
- context menus [Windows Forms], ContextMenuStrip control [Windows Forms]
- shortcut menus [Windows Forms], ContextMenuStrip control [Windows Forms]
- ContextMenuStrip control [Windows Forms], about ContextMenuStrip control
ms.assetid: 9787cdb3-88f1-4198-972f-eefd9524ce39
ms.openlocfilehash: e4a6add5297ba7db606ca1891e9279141f8d6d20
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974277"
---
# <a name="contextmenustrip-control-overview"></a><span data-ttu-id="74313-102">ContextMenuStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="74313-102">ContextMenuStrip Control Overview</span></span>
> [!NOTE]
> <span data-ttu-id="74313-103">コントロールは、コントロール <xref:System.Windows.Forms.ContextMenuStrip> に置き換えられ、機能が追加されます。ただし、コントロールは <xref:System.Windows.Forms.ContextMenu> <xref:System.Windows.Forms.ContextMenu> 旧バージョンとの互換性を維持するために残されています。</span><span class="sxs-lookup"><span data-stu-id="74313-103">The <xref:System.Windows.Forms.ContextMenuStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ContextMenu> control; however, the <xref:System.Windows.Forms.ContextMenu> control is retained for backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="74313-104">ショートカットメニュー (コンテキストメニューとも呼ばれます) は、ユーザーがマウスの右ボタンをクリックしたときにマウスの位置に表示されます。</span><span class="sxs-lookup"><span data-stu-id="74313-104">Shortcut menus, also called context menus, appear at the mouse position when the user clicks the right mouse button.</span></span> <span data-ttu-id="74313-105">ショートカット *メニュー* では、クライアント領域またはマウスポインターの位置にあるコントロールのオプションが提供されます。</span><span class="sxs-lookup"><span data-stu-id="74313-105">Shortcut *menus* provide options for the client area or the control at the mouse pointer location.</span></span>  
  
 <span data-ttu-id="74313-106">コントロールは、 <xref:System.Windows.Forms.ContextMenuStrip> 新しいおよび関連するコントロールとシームレスに連携するように設計されてい <xref:System.Windows.Forms.ToolStrip> ますが、他のコントロールとも簡単に関連付けることができ <xref:System.Windows.Forms.ContextMenuStrip> ます。</span><span class="sxs-lookup"><span data-stu-id="74313-106">The <xref:System.Windows.Forms.ContextMenuStrip> control is designed to work seamlessly with the new <xref:System.Windows.Forms.ToolStrip> and related controls, but you can associate a <xref:System.Windows.Forms.ContextMenuStrip> with other controls just as easily.</span></span>  
  
 <span data-ttu-id="74313-107">次の表は、重要な関連クラスを示して <xref:System.Windows.Forms.ContextMenuStrip> います。</span><span class="sxs-lookup"><span data-stu-id="74313-107">The following table shows the important <xref:System.Windows.Forms.ContextMenuStrip> companion classes.</span></span>  
  
|<span data-ttu-id="74313-108">クラス</span><span class="sxs-lookup"><span data-stu-id="74313-108">Class</span></span>|<span data-ttu-id="74313-109">説明</span><span class="sxs-lookup"><span data-stu-id="74313-109">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|<span data-ttu-id="74313-110"><xref:System.Windows.Forms.MenuStrip> または <xref:System.Windows.Forms.ContextMenuStrip> に表示される選択可能なオプションを表します。</span><span class="sxs-lookup"><span data-stu-id="74313-110">Represents a selectable option displayed on a <xref:System.Windows.Forms.MenuStrip> or <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDown>|<span data-ttu-id="74313-111">ユーザーが <xref:System.Windows.Forms.ToolStripDropDownButton> または上位レベルのメニュー項目をクリックしたときに表示される一覧から1つの項目を選択できるようにするコントロールを表します。</span><span class="sxs-lookup"><span data-stu-id="74313-111">Represents a control that enables the user to select a single item from a list that is displayed when the user clicks a <xref:System.Windows.Forms.ToolStripDropDownButton> or a higher-level menu item.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|<span data-ttu-id="74313-112"><xref:System.Windows.Forms.ToolStripItem>クリックしたときに表示されるドロップダウン項目から派生したコントロールの基本機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="74313-112">Provides basic functionality for controls derived from <xref:System.Windows.Forms.ToolStripItem> that display drop-down items when clicked.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="74313-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="74313-113">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
