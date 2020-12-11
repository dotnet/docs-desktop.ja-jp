---
title: デザイナーを使用して TabControl のタブを追加および削除する
description: デザイナーを使用して、Windows フォーム TabControl コントロールでタブを追加および削除する方法について説明します。
ms.date: 03/30/2017
helpviewer_keywords:
- tabs [Windows Forms], removing from pages
- TabPage control
- TabPage control [Windows Forms], adding and removing tabs
- tabs [Windows Forms], adding to pages
- tab pages
ms.assetid: 480633db-413a-45d2-9c8f-0427cc13adbe
ms.openlocfilehash: 955a671693243ab212180046bb60241c8113a854
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981111"
---
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol-using-the-designer"></a><span data-ttu-id="a5581-103">方法: デザイナーで Windows フォーム TabControl を使ってタブを追加および削除する</span><span class="sxs-lookup"><span data-stu-id="a5581-103">How to: Add and Remove Tabs with the Windows Forms TabControl Using the Designer</span></span>
<span data-ttu-id="a5581-104">フォームにコントロールを配置すると <xref:System.Windows.Forms.TabControl> 、既定で2つのタブが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5581-104">When you place a <xref:System.Windows.Forms.TabControl> control on your form, it contains two tabs by default.</span></span> <span data-ttu-id="a5581-105">デザイナーを使用して、タブを追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="a5581-105">You can add or remove tabs using the designer.</span></span>

 <span data-ttu-id="a5581-106">次の手順では、コントロールを含むフォームを含む **Windows アプリケーション** プロジェクトが必要です <xref:System.Windows.Forms.TabControl> 。</span><span class="sxs-lookup"><span data-stu-id="a5581-106">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.TabControl> control.</span></span> <span data-ttu-id="a5581-107">このようなプロジェクトの設定の詳細については、「 [方法: Windows フォームアプリケーションプロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project) する」および「 [方法: Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5581-107">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-add-or-remove-a-tab-using-the-designer"></a><span data-ttu-id="a5581-108">デザイナーを使用してタブを追加または削除するには</span><span class="sxs-lookup"><span data-stu-id="a5581-108">To add or remove a tab using the designer</span></span>

- <span data-ttu-id="a5581-109">コントロールのスマートタグで、[**タブの追加**] または [**タブの削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5581-109">On the control's smart tag, click **Add Tab** or **Remove Tab**</span></span>

     <span data-ttu-id="a5581-110">または</span><span class="sxs-lookup"><span data-stu-id="a5581-110">-or-</span></span>

     <span data-ttu-id="a5581-111">[ **プロパティ** ] ウィンドウで、プロパティの横に **ある省略記号ボタン (** [...] プロパティウィンドウ) をクリックして、[ ![ ](./media/visual-studio-ellipsis-button.png) <xref:System.Windows.Forms.TabControl.TabPages%2A> **TabPage コレクションエディター**] を開きます。</span><span class="sxs-lookup"><span data-stu-id="a5581-111">In the **Properties** window, click the **Ellipsis** button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.TabControl.TabPages%2A> property to open the **TabPage Collection Editor**.</span></span> <span data-ttu-id="a5581-112">[ **追加** ] または [ **削除** ] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5581-112">Click the **Add** or **Remove** button.</span></span>

## <a name="see-also"></a><span data-ttu-id="a5581-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="a5581-113">See also</span></span>

- [<span data-ttu-id="a5581-114">TabControl コントロール</span><span class="sxs-lookup"><span data-stu-id="a5581-114">TabControl Control</span></span>](tabcontrol-control-windows-forms.md)
- [<span data-ttu-id="a5581-115">TabControl コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="a5581-115">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="a5581-116">方法: タブ ページにコントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="a5581-116">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="a5581-117">方法: タブ ページを無効化する</span><span class="sxs-lookup"><span data-stu-id="a5581-117">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="a5581-118">方法: Windows フォーム TabControl の表示形式を変更する</span><span class="sxs-lookup"><span data-stu-id="a5581-118">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
