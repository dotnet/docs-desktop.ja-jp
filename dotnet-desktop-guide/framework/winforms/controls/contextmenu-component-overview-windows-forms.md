---
title: ContextMenu コンポーネントの概要
ms.date: 03/30/2017
f1_keywords:
- ContextMenu
helpviewer_keywords:
- ContextMenu component [Windows Forms], about ContextMenu component
- context menus [Windows Forms], ContextMenu component
- shortcut menus [Windows Forms], ContextMenu component
ms.assetid: 49d6398f-d3c4-4679-84fa-1de07b68b05e
ms.openlocfilehash: 83740221894941d09d1014585513043851a518e5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974282"
---
# <a name="contextmenu-component-overview-windows-forms"></a><span data-ttu-id="e2a15-102">ContextMenu コンポーネントの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="e2a15-102">ContextMenu Component Overview (Windows Forms)</span></span>
> [!IMPORTANT]
> <span data-ttu-id="e2a15-103">とは、 <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ContextMenuStrip> 以前のバージョンのとのコントロールに置き換えて機能を追加しますが、を <xref:System.Windows.Forms.MainMenu> 選択した場合は、 <xref:System.Windows.Forms.ContextMenu> <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.ContextMenu> 下位互換性と将来の使用の両方で保持されます。</span><span class="sxs-lookup"><span data-stu-id="e2a15-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="e2a15-104">Windows フォームコンポーネントを使用 <xref:System.Windows.Forms.ContextMenu> すると、選択したオブジェクトに関連付けられている頻繁に使用するコマンドのショートカットメニューをユーザーに提供できます。</span><span class="sxs-lookup"><span data-stu-id="e2a15-104">With the Windows Forms <xref:System.Windows.Forms.ContextMenu> component, you can provide users with an easily accessible shortcut menu of frequently used commands that are associated with the selected object.</span></span> <span data-ttu-id="e2a15-105">ショートカットメニューの項目は、多くの場合、アプリケーションの他の場所に表示されるメインメニューの項目のサブセットです。</span><span class="sxs-lookup"><span data-stu-id="e2a15-105">The items in a shortcut menu are frequently a subset of the items from main menus that appear elsewhere in the application.</span></span> <span data-ttu-id="e2a15-106">ユーザーは、通常、マウスを右クリックしてショートカットメニューにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="e2a15-106">A user can typically access a shortcut menu by right-clicking the mouse.</span></span> <span data-ttu-id="e2a15-107">Windows フォームでは、ショートカットメニューはコントロールに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="e2a15-107">On Windows Forms, shortcut menus are associated with controls.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="e2a15-108">キー プロパティ</span><span class="sxs-lookup"><span data-stu-id="e2a15-108">Key Properties</span></span>  
 <span data-ttu-id="e2a15-109">コントロールのプロパティをコンポーネントに設定することによって、ショートカットメニューをコントロールに関連付けることができ <xref:System.Windows.Forms.Control.ContextMenu%2A> <xref:System.Windows.Forms.ContextMenu> ます。</span><span class="sxs-lookup"><span data-stu-id="e2a15-109">You can associate a shortcut menu with a control by setting the control's <xref:System.Windows.Forms.Control.ContextMenu%2A> property to the <xref:System.Windows.Forms.ContextMenu> component.</span></span> <span data-ttu-id="e2a15-110">1つのショートカットメニューを複数のコントロールに関連付けることができますが、各コントロールにはショートカットメニューを1つしか含めることができません。</span><span class="sxs-lookup"><span data-stu-id="e2a15-110">A single shortcut menu can be associated with multiple controls, but each control can have only one shortcut menu.</span></span>  
  
 <span data-ttu-id="e2a15-111">コンポーネントのキープロパティ <xref:System.Windows.Forms.ContextMenu> は、 <xref:System.Windows.Forms.Menu.MenuItems%2A> プロパティです。</span><span class="sxs-lookup"><span data-stu-id="e2a15-111">The key property of the <xref:System.Windows.Forms.ContextMenu> component is the <xref:System.Windows.Forms.Menu.MenuItems%2A> property.</span></span> <span data-ttu-id="e2a15-112">プログラムによって <xref:System.Windows.Forms.MenuItem> オブジェクトを作成し、ショートカットメニューのに追加することによって、メニュー項目を追加でき <xref:System.Windows.Forms.Menu.MenuItemCollection> ます。</span><span class="sxs-lookup"><span data-stu-id="e2a15-112">You can add menu items by programmatically creating <xref:System.Windows.Forms.MenuItem> objects and adding them to the <xref:System.Windows.Forms.Menu.MenuItemCollection> of the shortcut menu.</span></span> <span data-ttu-id="e2a15-113">ショートカットメニュー内の項目は通常、他のメニューから描画されるので、ほとんどの場合、項目をコピーすることでショートカットメニューに追加します。</span><span class="sxs-lookup"><span data-stu-id="e2a15-113">Because the items in a shortcut menu are usually drawn from other menus, you will most frequently add items to a shortcut menu by copying them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2a15-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="e2a15-114">See also</span></span>

- <xref:System.Windows.Forms.ContextMenu>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
