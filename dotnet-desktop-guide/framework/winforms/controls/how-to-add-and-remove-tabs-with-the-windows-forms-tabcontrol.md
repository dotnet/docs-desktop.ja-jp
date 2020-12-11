---
title: TabControl を使用してタブを追加および削除する
description: 2つの TabPage コントロールを含む Windows フォーム TabControl コントロールを使用して、タブを追加および削除する方法について説明します。 これらのタブには、TabPages プロパティを使用してアクセスします。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tabs [Windows Forms], removing from pages
- TabPage control
- TabControl control [Windows Forms], adding and removing tabs
- tabs [Windows Forms], adding to pages
- tab pages
ms.assetid: 66d4dfca-41e8-44e3-9c80-fb7ac4cb1619
ms.openlocfilehash: 7e67d0bbc13bd7d9c8835dc6fb9b9c5c9333b8bf
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974140"
---
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol"></a><span data-ttu-id="7761b-104">方法: Windows フォーム TabControl のタブを追加および削除する</span><span class="sxs-lookup"><span data-stu-id="7761b-104">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>
<span data-ttu-id="7761b-105">既定では、 <xref:System.Windows.Forms.TabControl> コントロールには2つのコントロールが含まれてい <xref:System.Windows.Forms.TabPage> ます。</span><span class="sxs-lookup"><span data-stu-id="7761b-105">By default, a <xref:System.Windows.Forms.TabControl> control contains two <xref:System.Windows.Forms.TabPage> controls.</span></span> <span data-ttu-id="7761b-106">これらのタブには、プロパティを使用してアクセスでき <xref:System.Windows.Forms.TabControl.TabPages%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="7761b-106">You can access these tabs through the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
### <a name="to-add-a-tab-programmatically"></a><span data-ttu-id="7761b-107">プログラムによってタブを追加するには</span><span class="sxs-lookup"><span data-stu-id="7761b-107">To add a tab programmatically</span></span>  
  
- <span data-ttu-id="7761b-108"><xref:System.Windows.Forms.TabControl.TabPageCollection.Add%2A>プロパティのメソッドを使用し <xref:System.Windows.Forms.TabControl.TabPages%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="7761b-108">Use the <xref:System.Windows.Forms.TabControl.TabPageCollection.Add%2A> method of the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
    ```vb  
    Dim myTabPage As New TabPage()  
    myTabPage.Text = "TabPage" & (TabControl1.TabPages.Count + 1)  
    TabControl1.TabPages.Add(myTabPage)  
    ```  
  
    ```csharp  
    string title = "TabPage " + (tabControl1.TabCount + 1).ToString();  
    TabPage myTabPage = new TabPage(title);  
    tabControl1.TabPages.Add(myTabPage);  
    ```  
  
    ```cpp  
    String^ title = String::Concat("TabPage ",  
       (tabControl1->TabCount + 1).ToString());  
    TabPage^ myTabPage = gcnew TabPage(title);  
    tabControl1->TabPages->Add(myTabPage);  
    ```  
  
### <a name="to-remove-a-tab-programmatically"></a><span data-ttu-id="7761b-109">プログラムによってタブを削除するには</span><span class="sxs-lookup"><span data-stu-id="7761b-109">To remove a tab programmatically</span></span>  
  
- <span data-ttu-id="7761b-110">選択したタブを削除するには、 <xref:System.Windows.Forms.TabControl.TabPageCollection.Remove%2A> プロパティのメソッドを使用し <xref:System.Windows.Forms.TabControl.TabPages%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="7761b-110">To remove selected tabs, use the <xref:System.Windows.Forms.TabControl.TabPageCollection.Remove%2A> method of the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
     <span data-ttu-id="7761b-111">または</span><span class="sxs-lookup"><span data-stu-id="7761b-111">-or-</span></span>  
  
- <span data-ttu-id="7761b-112">すべてのタブを削除するには、 <xref:System.Windows.Forms.TabControl.TabPageCollection.Clear%2A> プロパティのメソッドを使用し <xref:System.Windows.Forms.TabControl.TabPages%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="7761b-112">To remove all tabs, use the <xref:System.Windows.Forms.TabControl.TabPageCollection.Clear%2A> method of the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
    ```vb  
    ' Removes the selected tab:  
    TabControl1.TabPages.Remove(TabControl1.SelectedTab)  
    ' Removes all the tabs:  
    TabControl1.TabPages.Clear()  
    ```  
  
    ```csharp  
    // Removes the selected tab:  
    tabControl1.TabPages.Remove(tabControl1.SelectedTab);  
    // Removes all the tabs:  
    tabControl1.TabPages.Clear();  
    ```  
  
    ```cpp  
    // Removes the selected tab:  
    tabControl1->TabPages->Remove(tabControl1->SelectedTab);  
    // Removes all the tabs:  
    tabControl1->TabPages->Clear();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7761b-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="7761b-113">See also</span></span>

- [<span data-ttu-id="7761b-114">TabControl コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="7761b-114">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="7761b-115">方法: タブ ページにコントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="7761b-115">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="7761b-116">方法: タブ ページを無効化する</span><span class="sxs-lookup"><span data-stu-id="7761b-116">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="7761b-117">方法: Windows フォーム TabControl の表示形式を変更する</span><span class="sxs-lookup"><span data-stu-id="7761b-117">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
