---
title: '方法: ToolStripMenuItems を非表示にする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding
- MenuStrip control [Windows Forms], hiding menu items
- menus [Windows Forms], hiding menu items
- menu items [Windows Forms], hiding
- hiding menu items
ms.assetid: 418a768f-808a-44cd-8cef-f4e161883621
ms.openlocfilehash: 64c0f093063357c1e8db5933c035cc8295ad4f1e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982104"
---
# <a name="how-to-hide-toolstripmenuitems"></a><span data-ttu-id="48446-102">方法: ToolStripMenuItems を非表示にする</span><span class="sxs-lookup"><span data-stu-id="48446-102">How to: Hide ToolStripMenuItems</span></span>
<span data-ttu-id="48446-103">メニュー項目を非表示にすることは、アプリケーションのユーザーインターフェイスを制御し、ユーザーコマンドを制限する方法です。</span><span class="sxs-lookup"><span data-stu-id="48446-103">Hiding menu items is a way to control the user interface of your application and restrict user commands.</span></span> <span data-ttu-id="48446-104">多くの場合、メニュー項目がすべて使用できなくなると、メニュー全体を非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="48446-104">Often, you will want to hide an entire menu when all of the menu items on it are unavailable.</span></span> <span data-ttu-id="48446-105">これにより、ユーザーの取られるが減少します。</span><span class="sxs-lookup"><span data-stu-id="48446-105">This presents fewer distractions for the user.</span></span> <span data-ttu-id="48446-106">さらに、メニューまたはメニュー項目を非表示にしたり無効にしたりすることもできます。非表示にしても、ユーザーがショートカットキーを使用してメニューコマンドにアクセスするのを防ぐことはできません。</span><span class="sxs-lookup"><span data-stu-id="48446-106">Furthermore, you might want to both hide and disable the menu or menu item, as hiding alone does not prevent the user from accessing a menu command by using a shortcut key.</span></span>  
  
### <a name="to-hide-any-menu-item-programmatically"></a><span data-ttu-id="48446-107">プログラムによってメニュー項目を非表示にするには</span><span class="sxs-lookup"><span data-stu-id="48446-107">To hide any menu item programmatically</span></span>  
  
- <span data-ttu-id="48446-108">メニュー項目のプロパティを設定するメソッド内で、プロパティをに設定するコードを追加し <xref:System.Windows.Forms.ToolStripItem.Visible%2A> `false` ます。</span><span class="sxs-lookup"><span data-stu-id="48446-108">Within the method where you set the properties of the menu item, add code to set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property to `false`.</span></span>  
  
    ```vb  
    MenuItem3.Visible = False  
    ```  
  
    ```csharp  
    menuItem3.Visible = false;  
    ```  
  
    ```cpp  
    menuItem3->Visible = false;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="48446-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="48446-109">See also</span></span>

- <xref:System.Windows.Forms.ToolStripItem.Visible%2A>
- <xref:System.Windows.Forms.MenuStrip>
- [<span data-ttu-id="48446-110">MenuStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="48446-110">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
- [<span data-ttu-id="48446-111">方法: ToolStripMenuItems を無効にする</span><span class="sxs-lookup"><span data-stu-id="48446-111">How to: Disable ToolStripMenuItems</span></span>](how-to-disable-toolstripmenuitems.md)
