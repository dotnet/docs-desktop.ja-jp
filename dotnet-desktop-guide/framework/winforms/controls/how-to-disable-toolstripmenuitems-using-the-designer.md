---
title: '方法: デザイナーを使用して ToolStripMenuItems を無効にする'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], disabling in designer
- MenuStrip control [Windows Forms], disabling menu items in designer
- menu items [Windows Forms], disabling
- menus [Windows Forms], disabling items
ms.assetid: 985e311e-7d67-4205-b5a3-d045b68a4a03
ms.openlocfilehash: 692b6c11f6d58c52a0af29ed04ada45c48cae058
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980843"
---
# <a name="how-to-disable-toolstripmenuitems-using-the-designer"></a><span data-ttu-id="97afd-102">方法: デザイナーを使用して ToolStripMenuItems を無効にする</span><span class="sxs-lookup"><span data-stu-id="97afd-102">How to: Disable ToolStripMenuItems Using the Designer</span></span>
<span data-ttu-id="97afd-103">ユーザーの操作に応じてメニュー項目を有効または無効にすることによって、ユーザーが実行できるコマンドを制限または拡大できます。</span><span class="sxs-lookup"><span data-stu-id="97afd-103">You can limit or broaden the commands a user may make by enabling and disabling menu items in response to user activities.</span></span> <span data-ttu-id="97afd-104">メニュー項目は、作成時に既定で有効になりますが、プロパティを使用して調整でき <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="97afd-104">Menu items are enabled by default when they are created, but this can be adjusted through the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property.</span></span> <span data-ttu-id="97afd-105">このプロパティは、デザイン時に [ **プロパティ** ] ウィンドウで操作することも、コードで設定することによってプログラムで操作することもできます。</span><span class="sxs-lookup"><span data-stu-id="97afd-105">You can manipulate this property at design time in the **Properties** window or programmatically by setting it in code.</span></span> <span data-ttu-id="97afd-106">詳細については、「 [How to: Disable ToolStripMenuItems](how-to-disable-toolstripmenuitems.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97afd-106">For more information, see [How to: Disable ToolStripMenuItems](how-to-disable-toolstripmenuitems.md).</span></span>

## <a name="to-disable-a-menu-item-at-design-time"></a><span data-ttu-id="97afd-107">デザイン時にメニュー項目を無効にするには</span><span class="sxs-lookup"><span data-stu-id="97afd-107">To disable a menu item at design time</span></span>

1. <span data-ttu-id="97afd-108">フォームでメニュー項目を選択した状態で、 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> プロパティをに設定し `false` ます。</span><span class="sxs-lookup"><span data-stu-id="97afd-108">With the menu item selected on the form, set the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property to `false`.</span></span>

    > [!TIP]
    > <span data-ttu-id="97afd-109">メニューの1つ目または最上位レベルのメニュー項目を無効にすると、メニュー内に含まれるすべてのメニュー項目が無効になります。</span><span class="sxs-lookup"><span data-stu-id="97afd-109">Disabling the first or top-level menu item in a menu disables all the menu items contained within the menu.</span></span> <span data-ttu-id="97afd-110">同様に、サブメニュー項目を含むメニュー項目を無効にすると、サブメニュー項目が無効になります。</span><span class="sxs-lookup"><span data-stu-id="97afd-110">Likewise, disabling a menu item that has submenu items disables the submenu items.</span></span> <span data-ttu-id="97afd-111">特定のメニューのすべてのコマンドをユーザーが使用できない場合は、そのメニュー全体を非表示にして無効にすることをお勧めします。これにより、クリーンなユーザーインターフェイスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="97afd-111">If all the commands on a given menu are unavailable to the user, it is considered good programming practice to both hide and disable the entire menu, as this presents a clean user interface.</span></span> <span data-ttu-id="97afd-112">非表示にすると、ショートカットキーを使用してメニューコマンドにアクセスできなくなるため、メニューを非表示にしたり無効にしたりする必要があります。</span><span class="sxs-lookup"><span data-stu-id="97afd-112">You should both hide and disable the menu, as hiding alone does not prevent access to a menu command via a shortcut key.</span></span> <span data-ttu-id="97afd-113"><xref:System.Windows.Forms.ToolStripItem.Visible%2A>トップレベルメニュー項目のプロパティをに設定すると `false` 、メニュー全体が非表示になります。</span><span class="sxs-lookup"><span data-stu-id="97afd-113">Set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of a top-level menu item to `false` to hide the entire menu.</span></span>

## <a name="see-also"></a><span data-ttu-id="97afd-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="97afd-114">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="97afd-115">方法: ToolStripMenuItems を非表示にする</span><span class="sxs-lookup"><span data-stu-id="97afd-115">How to: Hide ToolStripMenuItems</span></span>](how-to-hide-toolstripmenuitems.md)
- [<span data-ttu-id="97afd-116">MenuStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="97afd-116">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
