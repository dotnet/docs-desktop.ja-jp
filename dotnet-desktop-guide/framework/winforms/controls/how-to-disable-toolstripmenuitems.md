---
title: '方法: ToolStripMenuItems を無効にする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], enabling
- ToolStripMenuItems [Windows Forms], disabling
- menu items [Windows Forms], disabling
- disabling menu items
- menu items [Windows Forms], enabling
- menus [Windows Forms], disabling menu items
ms.assetid: bcc1da84-50fd-41d2-8475-103b581d5654
ms.openlocfilehash: f86a2934e799e4604693491dacbecc517d44d810
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982135"
---
# <a name="how-to-disable-toolstripmenuitems"></a><span data-ttu-id="5aa6c-102">方法: ToolStripMenuItems を無効にする</span><span class="sxs-lookup"><span data-stu-id="5aa6c-102">How to: Disable ToolStripMenuItems</span></span>
<span data-ttu-id="5aa6c-103">ユーザーの操作に応じてメニュー項目を有効または無効にすることによって、ユーザーが実行できるコマンドを制限または拡大できます。</span><span class="sxs-lookup"><span data-stu-id="5aa6c-103">You can limit or broaden the commands a user may make by enabling and disabling menu items in response to user activities.</span></span> <span data-ttu-id="5aa6c-104">メニュー項目は、作成時に既定で有効になりますが、プロパティを使用して調整でき <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="5aa6c-104">Menu items are enabled by default when they are created, but this can be adjusted through the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property.</span></span> <span data-ttu-id="5aa6c-105">このプロパティは、デザイン時に [ **プロパティ** ] ウィンドウで操作することも、コードで設定することによってプログラムで操作することもできます。</span><span class="sxs-lookup"><span data-stu-id="5aa6c-105">You can manipulate this property at design time in the **Properties** window or programmatically by setting it in code.</span></span>  
  
### <a name="to-disable-a-menu-item-programmatically"></a><span data-ttu-id="5aa6c-106">プログラムによってメニュー項目を無効にするには</span><span class="sxs-lookup"><span data-stu-id="5aa6c-106">To disable a menu item programmatically</span></span>  
  
- <span data-ttu-id="5aa6c-107">メニュー項目のプロパティを設定するメソッド内で、プロパティをに設定するコードを追加し <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> `false` ます。</span><span class="sxs-lookup"><span data-stu-id="5aa6c-107">Within the method where you set the properties of the menu item, add code to set the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property to `false`.</span></span>  
  
    ```vb  
    MenuItem1.Enabled = False  
    ```  
  
    ```csharp  
    menuItem1.Enabled = false;  
    ```  
  
    ```cpp  
    menuItem1->Enabled = false;  
    ```  
  
    > [!TIP]
    > <span data-ttu-id="5aa6c-108">メニューの1つ目または最上位レベルのメニュー項目を無効にすると、メニュー内に含まれるすべてのメニュー項目が非表示になりますが、無効にはなりません。</span><span class="sxs-lookup"><span data-stu-id="5aa6c-108">Disabling the first or top-level menu item in a menu hides all the menu items contained within the menu, but does not disable them.</span></span> <span data-ttu-id="5aa6c-109">同様に、サブメニュー項目を含むメニュー項目を無効にしても、サブメニュー項目は非表示になりますが、無効にはなりません。</span><span class="sxs-lookup"><span data-stu-id="5aa6c-109">Likewise, disabling a menu item that has submenu items hides the submenu items, but does not disable them.</span></span> <span data-ttu-id="5aa6c-110">特定のメニューのすべてのコマンドをユーザーが使用できない場合は、そのメニュー全体を非表示にして無効にすることをお勧めします。これにより、クリーンなユーザーインターフェイスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="5aa6c-110">If all the commands on a given menu are unavailable to the user, it is considered good programming practice to both hide and disable the entire menu, as this presents a clean user interface.</span></span> <span data-ttu-id="5aa6c-111">メニューを非表示にして無効にし、メニューのすべての項目とサブメニュー項目を無効にする必要があります。非表示にしても、ショートカットキーを使用してメニューコマンドにアクセスすることはできないためです。</span><span class="sxs-lookup"><span data-stu-id="5aa6c-111">You should hide and disable the menu, and disable every item and submenu item in the menu, because hiding alone does not prevent access to a menu command via a shortcut key.</span></span> <span data-ttu-id="5aa6c-112"><xref:System.Windows.Forms.ToolStripItem.Visible%2A>トップレベルメニュー項目のプロパティをに設定すると `false` 、メニュー全体が非表示になります。</span><span class="sxs-lookup"><span data-stu-id="5aa6c-112">Set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of a top-level menu item to `false` to hide the entire menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5aa6c-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="5aa6c-113">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="5aa6c-114">方法: ToolStripMenuItems を非表示にする</span><span class="sxs-lookup"><span data-stu-id="5aa6c-114">How to: Hide ToolStripMenuItems</span></span>](how-to-hide-toolstripmenuitems.md)
- [<span data-ttu-id="5aa6c-115">MenuStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="5aa6c-115">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
