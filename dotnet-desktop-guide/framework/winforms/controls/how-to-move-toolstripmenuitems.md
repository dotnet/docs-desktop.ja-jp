---
title: '方法: ToolStripMenuItems を移動する'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], moving
- menus [Windows Forms], arranging items
- ToolStripMenuItems [Windows Forms], dragging and dropping
- menu items [Windows Forms], moving
- menu items [Windows Forms], cutting and pasting
- menu items [Windows Forms], dragging and dropping
- MenuStrip control [Windows Forms], arranging items
- ToolStripMenuItems [Windows Forms], cutting and pasting
ms.assetid: cab9e03e-4edd-4c25-b3e3-bd1edc602bd9
ms.openlocfilehash: adf25973fde790937461007bd0106cca02dd83be
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980747"
---
# <a name="how-to-move-toolstripmenuitems"></a><span data-ttu-id="e365f-102">方法: ToolStripMenuItems を移動する</span><span class="sxs-lookup"><span data-stu-id="e365f-102">How to: Move ToolStripMenuItems</span></span>
<span data-ttu-id="e365f-103">デザイン時に、トップレベルのメニューとそのメニュー項目全体を上の別の場所に移動でき <xref:System.Windows.Forms.MenuStrip> ます。</span><span class="sxs-lookup"><span data-stu-id="e365f-103">At design time, you can move entire top-level menus and their menu items to a different place on the <xref:System.Windows.Forms.MenuStrip>.</span></span> <span data-ttu-id="e365f-104">また、トップレベルメニュー間で個々のメニュー項目を移動したり、メニュー内のメニュー項目の位置を変更したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="e365f-104">You can also move individual menu items between top-level menus or change the position of menu items within a menu.</span></span>

## <a name="to-move-a-top-level-menu-and-its-menu-items-to-another-top-level-location"></a><span data-ttu-id="e365f-105">トップレベルメニューとそのメニュー項目を別のトップレベルの場所に移動するには</span><span class="sxs-lookup"><span data-stu-id="e365f-105">To move a top-level menu and its menu items to another top-level location</span></span>

1. <span data-ttu-id="e365f-106">移動するメニューのマウスの左ボタンをクリックして、押したままにします。</span><span class="sxs-lookup"><span data-stu-id="e365f-106">Click and hold down the left mouse button on the menu that you want to move.</span></span>

2. <span data-ttu-id="e365f-107">挿入ポイントを、目的の新しい位置の前にあるトップレベルメニューにドラッグし、マウスの左ボタンを離します。</span><span class="sxs-lookup"><span data-stu-id="e365f-107">Drag the insertion point to the top-level menu that is before the intended new location and release the left mouse button.</span></span>

     <span data-ttu-id="e365f-108">選択したメニューがカーソル位置の右に移動します。</span><span class="sxs-lookup"><span data-stu-id="e365f-108">The selected menu moves to the right of the insertion point.</span></span>

## <a name="to-move-a-top-level-menu-and-its-menu-items-to-a-drop-down-location"></a><span data-ttu-id="e365f-109">トップレベルメニューとそのメニュー項目をドロップダウン位置に移動するには</span><span class="sxs-lookup"><span data-stu-id="e365f-109">To move a top-level menu and its menu items to a drop-down location</span></span>

1. <span data-ttu-id="e365f-110">移動するメニューを左クリックし、CTRL + X キーを押します。または、メニューを右クリックし、ショートカットメニューの [ **切り取り** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e365f-110">Left-click the menu that you want to move and press CTRL+X, or right-click the menu and select **Cut** from the shortcut menu.</span></span>

2. <span data-ttu-id="e365f-111">移動先のトップレベルメニューで、目的の新しい場所の上にあるメニュー項目を左クリックし、CTRL + V キーを押すか、または目的の新しい場所の上にあるメニュー項目を右クリックして、ショートカットメニューから [ **貼り付け** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e365f-111">In the destination top-level menu, left-click the menu item above the intended new location and press CTRL+V, or right-click the menu item above the intended new location and select **Paste** from the shortcut menu.</span></span>

     <span data-ttu-id="e365f-112">切り取ったメニューは、選択したメニュー項目の後に挿入されます。</span><span class="sxs-lookup"><span data-stu-id="e365f-112">The menu that you cut is inserted after the selected menu item.</span></span>

## <a name="to-move-a-menu-item-within-a-menu-using-the-items-collection-editor"></a><span data-ttu-id="e365f-113">項目コレクションエディターを使用してメニュー内のメニュー項目を移動するには</span><span class="sxs-lookup"><span data-stu-id="e365f-113">To move a menu item within a menu using the Items Collection Editor</span></span>

1. <span data-ttu-id="e365f-114">移動するメニュー項目が含まれているメニューを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="e365f-114">Right-click the menu that contains the menu item you want to move.</span></span>

2. <span data-ttu-id="e365f-115">ショートカットメニューの [ **DropDownItems の編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e365f-115">From the shortcut menu, choose **Edit DropDownItems**.</span></span>

3. <span data-ttu-id="e365f-116">**Items コレクションエディター** で、移動するメニュー項目を左クリックします。</span><span class="sxs-lookup"><span data-stu-id="e365f-116">In the **Items Collection Editor**, left-click the menu item you want to move.</span></span>

4. <span data-ttu-id="e365f-117">メニュー内のメニュー項目を移動するには、上下の方向キーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e365f-117">Click the UP and DOWN ARROW keys to move the menu item within the menu.</span></span>

5. <span data-ttu-id="e365f-118">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e365f-118">Click **OK**.</span></span>

## <a name="to-move-a-menu-item-within-a-menu-using-the-keyboard"></a><span data-ttu-id="e365f-119">キーボードを使用してメニュー内のメニュー項目を移動するには</span><span class="sxs-lookup"><span data-stu-id="e365f-119">To move a menu item within a menu using the keyboard</span></span>

1. <span data-ttu-id="e365f-120">ALT キーを押したままにします。</span><span class="sxs-lookup"><span data-stu-id="e365f-120">Press and hold down the ALT key.</span></span>

2. <span data-ttu-id="e365f-121">移動するメニュー項目のマウスの左ボタンをクリックしたままにします。</span><span class="sxs-lookup"><span data-stu-id="e365f-121">Click and hold the left mouse button on the menu item that you want to move.</span></span>

3. <span data-ttu-id="e365f-122">メニュー項目を新しい位置にドラッグし、マウスの左ボタンを離します。</span><span class="sxs-lookup"><span data-stu-id="e365f-122">Drag the menu item to the new location and release the left mouse button.</span></span>

## <a name="to-move-a-menu-item-to-another-menu"></a><span data-ttu-id="e365f-123">メニュー項目を別のメニューに移動するには</span><span class="sxs-lookup"><span data-stu-id="e365f-123">To move a menu item to another menu</span></span>

1. <span data-ttu-id="e365f-124">移動するメニュー項目を左クリックし、CTRL + X キーを押します。または、メニュー項目を右クリックし、ショートカットメニューの [ **切り取り** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e365f-124">Left-click the menu item that you want to move and press CTRL+X, or right-click the menu item and choose **Cut** from the shortcut menu.</span></span>

2. <span data-ttu-id="e365f-125">切り取ったメニュー項目を含むメニューを左クリックします。</span><span class="sxs-lookup"><span data-stu-id="e365f-125">Left-click the menu that will contain the menu item that you cut.</span></span>

3. <span data-ttu-id="e365f-126">目的の新しい場所の前にあるメニュー項目を左クリックし、CTRL + V キーを押します。または、新しい場所の前にあるメニュー項目を右クリックし、ショートカットメニューから [ **貼り付け** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e365f-126">Left-click the menu item that is before the intended new location and press CTRL+V, or right-click the menu item that is before the intended new location and select **Paste** from the shortcut menu.</span></span>

     <span data-ttu-id="e365f-127">切り取ったメニュー項目は、選択したメニュー項目の後に挿入されます。</span><span class="sxs-lookup"><span data-stu-id="e365f-127">The menu item that you cut is inserted after the selected menu item.</span></span>

## <a name="see-also"></a><span data-ttu-id="e365f-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="e365f-128">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="e365f-129">MenuStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="e365f-129">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
