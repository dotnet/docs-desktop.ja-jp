---
title: TabControl コントロールの概要
ms.date: 03/30/2017
f1_keywords:
- TabControl
helpviewer_keywords:
- TabControl control [Windows Forms], about TabControl control
- tab pages [Windows Forms], about tab pages
- property pages [Windows Forms], Windows Forms
- Windows Forms dialog boxes [Windows Forms], tabs
ms.assetid: 2b4ea784-a39d-463c-81d8-af74ce068476
ms.openlocfilehash: 2668169488b4087673fbf2552650c23cda780642
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980050"
---
# <a name="tabcontrol-control-overview-windows-forms"></a><span data-ttu-id="5a0e6-102">TabControl コントロールの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="5a0e6-102">TabControl Control Overview (Windows Forms)</span></span>
<span data-ttu-id="5a0e6-103">Windows フォーム <xref:System.Windows.Forms.TabControl> は、ノートの仕切りや書類キャビネットのフォルダー セットのラベルに似た、複数のタブを表示します。</span><span class="sxs-lookup"><span data-stu-id="5a0e6-103">The Windows Forms <xref:System.Windows.Forms.TabControl> displays multiple tabs, like dividers in a notebook or labels in a set of folders in a filing cabinet.</span></span> <span data-ttu-id="5a0e6-104">タブには画像やその他のコントロールを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="5a0e6-104">The tabs can contain pictures and other controls.</span></span> <span data-ttu-id="5a0e6-105">タブコントロールを使用すると、コントロールパネルの表示プロパティなど、Windows オペレーティングシステムのさまざまな場所に表示される複数ページのダイアログボックスの種類を生成できます。</span><span class="sxs-lookup"><span data-stu-id="5a0e6-105">You can use the tab control to produce the kind of multiple-page dialog box that appears many places in the Windows operating system, such as the Control Panel Display Properties.</span></span> <span data-ttu-id="5a0e6-106">また、を使用して、 <xref:System.Windows.Forms.TabControl> 関連するプロパティのグループを設定するために使用されるプロパティページを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="5a0e6-106">Additionally, the <xref:System.Windows.Forms.TabControl> can be used to create property pages, which are used to set a group of related properties.</span></span>  
  
## <a name="working-with-tabcontrol"></a><span data-ttu-id="5a0e6-107">TabControl の操作</span><span class="sxs-lookup"><span data-stu-id="5a0e6-107">Working with TabControl</span></span>  
 <span data-ttu-id="5a0e6-108">の最も重要なプロパティ <xref:System.Windows.Forms.TabControl> はです <xref:System.Windows.Forms.TabControl.TabPages%2A> 。これには、個々のタブが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5a0e6-108">The most important property of the <xref:System.Windows.Forms.TabControl> is <xref:System.Windows.Forms.TabControl.TabPages%2A>, which contains the individual tabs.</span></span> <span data-ttu-id="5a0e6-109">個々のタブは <xref:System.Windows.Forms.TabPage> オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="5a0e6-109">Each individual tab is a <xref:System.Windows.Forms.TabPage> object.</span></span> <span data-ttu-id="5a0e6-110">タブをクリックすると、その <xref:System.Windows.Forms.Control.Click> オブジェクトのイベントが発生し <xref:System.Windows.Forms.TabPage> ます。</span><span class="sxs-lookup"><span data-stu-id="5a0e6-110">When a tab is clicked, it raises the <xref:System.Windows.Forms.Control.Click> event for that <xref:System.Windows.Forms.TabPage> object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a0e6-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a0e6-111">See also</span></span>

- <xref:System.Windows.Forms.TabControl>
- [<span data-ttu-id="5a0e6-112">TabControl コントロール</span><span class="sxs-lookup"><span data-stu-id="5a0e6-112">TabControl Control</span></span>](tabcontrol-control-windows-forms.md)
- [<span data-ttu-id="5a0e6-113">方法: Windows フォーム TabControl の表示形式を変更する</span><span class="sxs-lookup"><span data-stu-id="5a0e6-113">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
- [<span data-ttu-id="5a0e6-114">方法: タブ ページにコントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="5a0e6-114">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="5a0e6-115">方法: Windows フォーム TabControl のタブを追加および削除する</span><span class="sxs-lookup"><span data-stu-id="5a0e6-115">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
- [<span data-ttu-id="5a0e6-116">方法: タブ ページを無効化する</span><span class="sxs-lookup"><span data-stu-id="5a0e6-116">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="5a0e6-117">Windows フォームのダイアログ ボックス</span><span class="sxs-lookup"><span data-stu-id="5a0e6-117">Dialog Boxes in Windows Forms</span></span>](../dialog-boxes-in-windows-forms.md)
