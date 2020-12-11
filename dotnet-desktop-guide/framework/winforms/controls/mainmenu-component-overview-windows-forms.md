---
title: MainMenu コンポーネントの概要
ms.date: 03/30/2017
f1_keywords:
- MenuItem
- MainMenu
helpviewer_keywords:
- MainMenu control [Windows Forms], about MainMenu control
- menus
ms.assetid: b41cc5a3-cc59-4996-aa3c-8dd9c17d3c90
ms.openlocfilehash: 8bc35de239429214d6b493b343d1dd6c898f4d37
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980624"
---
# <a name="mainmenu-component-overview-windows-forms"></a><span data-ttu-id="f02a5-102">MainMenu コンポーネントの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="f02a5-102">MainMenu Component Overview (Windows Forms)</span></span>
> [!IMPORTANT]
> <span data-ttu-id="f02a5-103">とは、 <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ContextMenuStrip> 以前のバージョンのとのコントロールに置き換えて機能を追加しますが、を <xref:System.Windows.Forms.MainMenu> 選択した場合は、 <xref:System.Windows.Forms.ContextMenu> <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.ContextMenu> 下位互換性と将来の使用の両方で保持されます。</span><span class="sxs-lookup"><span data-stu-id="f02a5-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="f02a5-104">Windows フォームコンポーネントは、 <xref:System.Windows.Forms.MainMenu> 実行時にメニューを表示します。</span><span class="sxs-lookup"><span data-stu-id="f02a5-104">The Windows Forms <xref:System.Windows.Forms.MainMenu> component displays a menu at run time.</span></span> <span data-ttu-id="f02a5-105">メインメニューのすべてのサブメニューと個々の項目は <xref:System.Windows.Forms.MenuItem> オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="f02a5-105">All submenus of the main menu and individual items are <xref:System.Windows.Forms.MenuItem> objects.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="f02a5-106">キー プロパティ</span><span class="sxs-lookup"><span data-stu-id="f02a5-106">Key Properties</span></span>  
 <span data-ttu-id="f02a5-107">メニュー項目は、プロパティをに設定することによって、既定の項目として指定でき <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> `true` ます。</span><span class="sxs-lookup"><span data-stu-id="f02a5-107">A menu item can be designated as the default item by setting the <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> property to `true`.</span></span> <span data-ttu-id="f02a5-108">メニューがクリックされると、既定の項目が太字で表示されます。</span><span class="sxs-lookup"><span data-stu-id="f02a5-108">The default item appears in bold text when the menu is clicked.</span></span> <span data-ttu-id="f02a5-109">メニュー項目の <xref:System.Windows.Forms.MenuItem.Checked%2A> プロパティは、またはのいずれかで、 `true` `false` メニュー項目が選択されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="f02a5-109">The menu item's <xref:System.Windows.Forms.MenuItem.Checked%2A> property is either `true` or `false`, and indicates whether the menu item is selected.</span></span> <span data-ttu-id="f02a5-110">メニュー項目のプロパティは、 <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> 選択した項目の外観をカスタマイズします。がに設定されている場合 <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> `true` 、項目の横にオプションボタンが表示されます。がに設定されている場合は、 <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> `false` 項目の横にチェックマークが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f02a5-110">The menu item's <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> property customizes the appearance of the selected item: if <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> is set to `true`, a radio button appears next to the item; if <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> is set to `false`, a check mark appears next to the item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f02a5-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="f02a5-111">See also</span></span>

- <xref:System.Windows.Forms.MainMenu>
- <xref:System.Windows.Forms.Menu>
- <xref:System.Windows.Forms.MenuItem>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- [<span data-ttu-id="f02a5-112">MenuStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="f02a5-112">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
