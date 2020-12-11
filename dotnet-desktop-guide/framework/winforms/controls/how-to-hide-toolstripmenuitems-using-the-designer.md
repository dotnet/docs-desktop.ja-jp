---
title: '方法: デザイナーを使用して ToolStripMenuItems を非表示にする'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding menu items in designer
- MenuStrip control [Windows Forms], hiding menu items in designer
- menu items [Windows Forms], hiding
ms.assetid: 8f1b057e-3d8a-4f11-88df-935f7b29a836
ms.openlocfilehash: 0e1cd7d1868adabd4d3eec9510f6ee567ba3867d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980784"
---
# <a name="how-to-hide-toolstripmenuitems-using-the-designer"></a><span data-ttu-id="2ac66-102">方法: デザイナーを使用して ToolStripMenuItems を非表示にする</span><span class="sxs-lookup"><span data-stu-id="2ac66-102">How to: Hide ToolStripMenuItems Using the Designer</span></span>
<span data-ttu-id="2ac66-103">メニュー項目を非表示にすることは、アプリケーションのユーザーインターフェイス (UI) を制御し、ユーザーコマンドを制限する方法です。</span><span class="sxs-lookup"><span data-stu-id="2ac66-103">Hiding menu items is a way to control the user interface (UI) of your application and restrict user commands.</span></span> <span data-ttu-id="2ac66-104">多くの場合、メニュー項目がすべて使用できなくなると、メニュー全体を非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="2ac66-104">Often, you will want to hide an entire menu when all of the menu items on it are unavailable.</span></span> <span data-ttu-id="2ac66-105">これにより、ユーザーの取られるが減少します。</span><span class="sxs-lookup"><span data-stu-id="2ac66-105">This presents fewer distractions for the user.</span></span> <span data-ttu-id="2ac66-106">さらに、メニューまたはメニュー項目を非表示にしたり無効にしたりすることもできます。非表示にしても、ユーザーがショートカットキーを使用してメニューコマンドにアクセスするのを防ぐことはできません。</span><span class="sxs-lookup"><span data-stu-id="2ac66-106">Furthermore, you might want to both hide and disable the menu or menu item, as hiding alone does not prevent the user from accessing a menu command by using a shortcut key.</span></span> <span data-ttu-id="2ac66-107">メニュー項目を無効にする方法の詳細については、「 [方法: デザイナーを使用して ToolStripMenuItems を無効](how-to-disable-toolstripmenuitems-using-the-designer.md)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ac66-107">For more information on disabling menu items, see [How to: Disable ToolStripMenuItems Using the Designer](how-to-disable-toolstripmenuitems-using-the-designer.md).</span></span>

## <a name="to-hide-a-top-level-menu-and-its-submenu-items"></a><span data-ttu-id="2ac66-108">トップレベルメニューとそのサブメニュー項目を非表示にするには</span><span class="sxs-lookup"><span data-stu-id="2ac66-108">To hide a top-level menu and its submenu items</span></span>

1. <span data-ttu-id="2ac66-109">トップレベルのメニュー項目を選択し、その <xref:System.Windows.Forms.ToolStripItem.Visible%2A> プロパティまたは <xref:System.Windows.Forms.ToolStripItem.Available%2A> プロパティをに設定し `false` ます。</span><span class="sxs-lookup"><span data-stu-id="2ac66-109">Select the top-level menu item and set its <xref:System.Windows.Forms.ToolStripItem.Visible%2A> or <xref:System.Windows.Forms.ToolStripItem.Available%2A> property to `false`.</span></span>

     <span data-ttu-id="2ac66-110">トップレベルメニュー項目を非表示にすると、そのメニュー内のすべてのメニュー項目も非表示になります。</span><span class="sxs-lookup"><span data-stu-id="2ac66-110">When you hide the top-level menu item, all menu items within that menu are also hidden.</span></span> <span data-ttu-id="2ac66-111">[After] をに設定している以外の場所をクリックすると <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ToolStripItem.Visible%2A> `false` 、最上位レベルのメニュー項目とそのサブメニュー項目全体がフォームから消え、アクションの実行時効果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2ac66-111">If you click somewhere other than on the <xref:System.Windows.Forms.MenuStrip> after setting <xref:System.Windows.Forms.ToolStripItem.Visible%2A> to `false`, the entire top-level menu item and its submenu items disappear from your form, thus showing you the run-time effect of your action.</span></span> <span data-ttu-id="2ac66-112">デザイン時に、表示されていないトップレベルメニュー項目を表示するに <xref:System.Windows.Forms.MenuStrip> は、 **コンポーネントトレイ**、 **ドキュメントアウトライン**、またはプロパティグリッドの上部で、をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ac66-112">To display the hidden top-level menu item at design time, click on the <xref:System.Windows.Forms.MenuStrip> in the **Component Tray**, in **Document Outline**, or at the top of the property grid.</span></span>

> [!NOTE]
> <span data-ttu-id="2ac66-113">マージシナリオでは、マルチドキュメントインターフェイス (MDI) 子メニューを除き、メニュー全体を非表示にすることはめったにありません。</span><span class="sxs-lookup"><span data-stu-id="2ac66-113">You will rarely hide an entire menu except for multiple document interface (MDI) child menus in a merging scenario.</span></span>

## <a name="to-hide-a-submenu-item"></a><span data-ttu-id="2ac66-114">サブメニュー項目を非表示にするには</span><span class="sxs-lookup"><span data-stu-id="2ac66-114">To hide a submenu item</span></span>

1. <span data-ttu-id="2ac66-115">サブメニュー項目を選択し、その <xref:System.Windows.Forms.ToolStripItem.Visible%2A> プロパティをに設定し `false` ます。</span><span class="sxs-lookup"><span data-stu-id="2ac66-115">Select the submenu item and set its <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property to `false`.</span></span>

     <span data-ttu-id="2ac66-116">サブメニュー項目を非表示にすると、デザイン時にフォームに表示されたままになり、作業のために簡単に選択できるようになります。</span><span class="sxs-lookup"><span data-stu-id="2ac66-116">When you hide a submenu item, it remains visible on your form at design time so that you can easily select it for further work.</span></span> <span data-ttu-id="2ac66-117">実際には、実行時に非表示になります。</span><span class="sxs-lookup"><span data-stu-id="2ac66-117">It will actually be hidden at run time.</span></span>

## <a name="see-also"></a><span data-ttu-id="2ac66-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ac66-118">See also</span></span>

- <xref:System.Windows.Forms.ToolStripItem.Visible%2A>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>
- <xref:System.Windows.Forms.ToolStripItem.Available%2A>
- <xref:System.Windows.Forms.ToolStripMenuItem.Overflow%2A>
- [<span data-ttu-id="2ac66-119">MenuStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="2ac66-119">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
- [<span data-ttu-id="2ac66-120">方法: デザイナーを使用して ToolStripMenuItems を無効にする</span><span class="sxs-lookup"><span data-stu-id="2ac66-120">How to: Disable ToolStripMenuItems Using the Designer</span></span>](how-to-disable-toolstripmenuitems-using-the-designer.md)
