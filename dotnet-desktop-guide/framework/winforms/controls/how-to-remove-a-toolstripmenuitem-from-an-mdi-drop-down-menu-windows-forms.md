---
title: '方法: ToolStripMenuItem を MDI ドロップダウン メニューから削除する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- menu items [Windows Forms], removing from MDI drop-down menus
- MenuStrip control [Windows Forms], merging
- MenuStrip control [Windows Forms], removing
- MDI [Windows Forms], merging menu items
ms.assetid: bdafe60d-82ee-45bc-97fe-eeefca6e54c1
ms.openlocfilehash: 3198195cf0991734826508aa65818505bf2038c8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980732"
---
# <a name="how-to-remove-a-toolstripmenuitem-from-an-mdi-drop-down-menu-windows-forms"></a><span data-ttu-id="a6492-102">方法 : ToolStripMenuItem を MDI ドロップダウン メニューから削除する (Windows フォーム) </span><span class="sxs-lookup"><span data-stu-id="a6492-102">How to: Remove a ToolStripMenuItem from an MDI Drop-Down Menu (Windows Forms)</span></span>
<span data-ttu-id="a6492-103">アプリケーションの中には、マルチ ドキュメント インターフェイス (MDI) 子ウィンドウの種類が MDI 親ウィンドウと異なるものがあります。</span><span class="sxs-lookup"><span data-stu-id="a6492-103">In some applications, the kind of a multiple-document interface (MDI) child window can be different from the MDI parent window.</span></span> <span data-ttu-id="a6492-104">たとえば、MDI 親がスプレッドシートで、MDI 子がグラフの場合があります。</span><span class="sxs-lookup"><span data-stu-id="a6492-104">For example, the MDI parent might be a spreadsheet, and the MDI child might be a chart.</span></span> <span data-ttu-id="a6492-105">そのような場合は、異なる種類の MDI 子ウィンドウがアクティブになったときに、MDI 子メニューの内容で MDI 親メニューの内容を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6492-105">In that case, you want to update the contents of the MDI parent's menu with the contents of the MDI child's menu as MDI child windows of different kinds are activated.</span></span>  
  
 <span data-ttu-id="a6492-106">次の手順では <xref:System.Windows.Forms.Form.IsMdiContainer%2A> 、、、、およびの各プロパティを使用して、 <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> <xref:System.Windows.Forms.MergeAction> <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> MDI 親メニューのドロップダウン部分からメニュー項目を削除します。</span><span class="sxs-lookup"><span data-stu-id="a6492-106">The following procedure uses the <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction>, and <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> properties to remove a menu item from the drop-down part of the MDI parent menu.</span></span> <span data-ttu-id="a6492-107">MDI 子ウィンドウを閉じると、削除されたメニュー項目が MDI 親メニューに復元されます。</span><span class="sxs-lookup"><span data-stu-id="a6492-107">Closing the MDI child window restores the removed menu items to the MDI parent menu.</span></span>  
  
### <a name="to-remove-a-menustrip-from-an-mdi-drop-down-menu"></a><span data-ttu-id="a6492-108">MDI ドロップダウンメニューから MenuStrip を削除するには</span><span class="sxs-lookup"><span data-stu-id="a6492-108">To remove a MenuStrip from an MDI drop-down menu</span></span>  
  
1. <span data-ttu-id="a6492-109">フォームを作成し、その <xref:System.Windows.Forms.Form.IsMdiContainer%2A> プロパティを `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="a6492-109">Create a form and set its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`.</span></span>  
  
2. <span data-ttu-id="a6492-110"><xref:System.Windows.Forms.MenuStrip> を `Form1` に追加し、<xref:System.Windows.Forms.MenuStrip> の <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> プロパティを `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="a6492-110">Add a <xref:System.Windows.Forms.MenuStrip> to `Form1` and set the <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> property of the <xref:System.Windows.Forms.MenuStrip> to `true`.</span></span>  
  
3. <span data-ttu-id="a6492-111">トップレベル メニュー項目を `Form1` の <xref:System.Windows.Forms.MenuStrip> に追加し、その <xref:System.Windows.Forms.Control.Text%2A> プロパティを「`&File`」に設定しますす。</span><span class="sxs-lookup"><span data-stu-id="a6492-111">Add a top-level menu item to the `Form1`<xref:System.Windows.Forms.MenuStrip> and set its <xref:System.Windows.Forms.Control.Text%2A> property to `&File`.</span></span>  
  
4. <span data-ttu-id="a6492-112">メニュー項目に3つのサブメニュー項目を追加 `&File` し、それらのプロパティを、、およびに設定し <xref:System.Windows.Forms.ToolStripItem.Text%2A> `&Open` `&Import from` `E&xit` ます。</span><span class="sxs-lookup"><span data-stu-id="a6492-112">Add three submenu items to the `&File` menu item and set their <xref:System.Windows.Forms.ToolStripItem.Text%2A> properties to `&Open`, `&Import from`, and `E&xit`.</span></span>  
  
5. <span data-ttu-id="a6492-113">サブメニュー項目に2つのサブメニュー項目を追加 `&Import from` し、それらの <xref:System.Windows.Forms.ToolStripItem.Text%2A> プロパティをとに設定し `&Word` `&Excel` ます。</span><span class="sxs-lookup"><span data-stu-id="a6492-113">Add two submenu items to the `&Import from` submenu item and set their <xref:System.Windows.Forms.ToolStripItem.Text%2A> properties to `&Word` and `&Excel`.</span></span>  
  
6. <span data-ttu-id="a6492-114">プロジェクトにフォームを追加し、フォームに <xref:System.Windows.Forms.MenuStrip> を追加し、`Form2` の <xref:System.Windows.Forms.MenuStrip> の <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> のプロパティを `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="a6492-114">Add a form to the project, add a <xref:System.Windows.Forms.MenuStrip> to the form, and set the <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> property of the `Form2`<xref:System.Windows.Forms.MenuStrip> to `true`.</span></span>  
  
7. <span data-ttu-id="a6492-115">トップレベル メニュー項目を `Form2` の <xref:System.Windows.Forms.MenuStrip> に追加し、その <xref:System.Windows.Forms.ToolStripItem.Text%2A> プロパティを「`&File`」に設定しますす。</span><span class="sxs-lookup"><span data-stu-id="a6492-115">Add a top-level menu item to the `Form2`<xref:System.Windows.Forms.MenuStrip> and set its <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to `&File`.</span></span>  
  
8. <span data-ttu-id="a6492-116">`&Import from`のメニューにサブメニュー項目を追加 `&File` `Form2` し、 `&Word` メニューにサブメニュー項目を追加し `&File` ます。</span><span class="sxs-lookup"><span data-stu-id="a6492-116">Add an `&Import from` submenu item to the `&File` menu of `Form2`, and add an `&Word` submenu item to the `&File` menu.</span></span>  
  
9. <span data-ttu-id="a6492-117">次の <xref:System.Windows.Forms.MergeAction> <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> 表に示すように、メニュー項目のプロパティとプロパティを設定し `Form2` ます。</span><span class="sxs-lookup"><span data-stu-id="a6492-117">Set the <xref:System.Windows.Forms.MergeAction> and <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> properties of the `Form2` menu items as shown in the following table.</span></span>  
  
    |<span data-ttu-id="a6492-118">Form2 のメニュー項目</span><span class="sxs-lookup"><span data-stu-id="a6492-118">Form2 menu item</span></span>|<span data-ttu-id="a6492-119">MergeAction 値</span><span class="sxs-lookup"><span data-stu-id="a6492-119">MergeAction value</span></span>|<span data-ttu-id="a6492-120">MergeIndex 値</span><span class="sxs-lookup"><span data-stu-id="a6492-120">MergeIndex value</span></span>|  
    |---------------------|-----------------------|----------------------|  
    |<span data-ttu-id="a6492-121">ファイル</span><span class="sxs-lookup"><span data-stu-id="a6492-121">File</span></span>|<span data-ttu-id="a6492-122">MatchOnly</span><span class="sxs-lookup"><span data-stu-id="a6492-122">MatchOnly</span></span>|<span data-ttu-id="a6492-123">-1</span><span class="sxs-lookup"><span data-stu-id="a6492-123">-1</span></span>|  
    |<span data-ttu-id="a6492-124">インポート:</span><span class="sxs-lookup"><span data-stu-id="a6492-124">Import from</span></span>|<span data-ttu-id="a6492-125">MatchOnly</span><span class="sxs-lookup"><span data-stu-id="a6492-125">MatchOnly</span></span>|<span data-ttu-id="a6492-126">-1</span><span class="sxs-lookup"><span data-stu-id="a6492-126">-1</span></span>|  
    |<span data-ttu-id="a6492-127">Word</span><span class="sxs-lookup"><span data-stu-id="a6492-127">Word</span></span>|<span data-ttu-id="a6492-128">削除</span><span class="sxs-lookup"><span data-stu-id="a6492-128">Remove</span></span>|<span data-ttu-id="a6492-129">-1</span><span class="sxs-lookup"><span data-stu-id="a6492-129">-1</span></span>|  
  
10. <span data-ttu-id="a6492-130">で、 `Form1` のイベントのイベントハンドラーを作成 <xref:System.Windows.Forms.Control.Click> `&Open` <xref:System.Windows.Forms.ToolStripMenuItem> します。</span><span class="sxs-lookup"><span data-stu-id="a6492-130">In `Form1`, create an event handler for the <xref:System.Windows.Forms.Control.Click> event of the `&Open`<xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
11. <span data-ttu-id="a6492-131">イベントハンドラー内で、次のコード例のようなコードを挿入して、の新しいインスタンスを `Form2` MDI 子として作成および表示し `Form1` ます。</span><span class="sxs-lookup"><span data-stu-id="a6492-131">Within the event handler, insert code similar to the following code example to create and display new instances of `Form2` as MDI children of `Form1`:</span></span>  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles openToolStripMenuItem.Click  
        Dim NewMDIChild As New Form2()  
        'Set the parent form of the child window.  
            NewMDIChild.MdiParent = Me  
        'Display the new form.  
            NewMDIChild.Show()  
    End Sub  
    ```  
  
    ```csharp  
    private void openToolStripMenuItem_Click(object sender, EventArgs e)  
    {  
        Form2 newMDIChild = new Form2();  
        // Set the parent form of the child window.  
            newMDIChild.MdiParent = this;  
        // Display the new form.  
            newMDIChild.Show();  
    }  
    ```  
  
12. <span data-ttu-id="a6492-132">`&Open`<xref:System.Windows.Forms.ToolStripMenuItem> に次のコード例のようなコードを配置し、イベント ハンドラーを登録します。</span><span class="sxs-lookup"><span data-stu-id="a6492-132">Place code similar to the following code example in the `&Open`<xref:System.Windows.Forms.ToolStripMenuItem> to register the event handler.</span></span>  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles openToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.openToolStripMenuItem.Click += new _  
    System.EventHandler(this.openToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a6492-133">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="a6492-133">Compiling the Code</span></span>  
 <span data-ttu-id="a6492-134">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a6492-134">This example requires:</span></span>  
  
- <span data-ttu-id="a6492-135">`Form1` と `Form2` という名前の 2 つの <xref:System.Windows.Forms.Form> コントロール。</span><span class="sxs-lookup"><span data-stu-id="a6492-135">Two <xref:System.Windows.Forms.Form> controls named `Form1` and `Form2`.</span></span>  
  
- <span data-ttu-id="a6492-136">`Form1` 上の `menuStrip1` という名前の <xref:System.Windows.Forms.MenuStrip> コントロールと、`Form2` 上の `menuStrip2` という名前の <xref:System.Windows.Forms.MenuStrip> コントロール。</span><span class="sxs-lookup"><span data-stu-id="a6492-136">A <xref:System.Windows.Forms.MenuStrip> control on `Form1` named `menuStrip1`, and a <xref:System.Windows.Forms.MenuStrip> control on `Form2` named `menuStrip2`.</span></span>  
  
- <span data-ttu-id="a6492-137"><xref:System?displayProperty=nameWithType> アセンブリおよび <xref:System.Windows.Forms?displayProperty=nameWithType> アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="a6492-137">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6492-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="a6492-138">See also</span></span>

- [<span data-ttu-id="a6492-139">方法: MDI 親フォームを作成する</span><span class="sxs-lookup"><span data-stu-id="a6492-139">How to: Create MDI Parent Forms</span></span>](../advanced/how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="a6492-140">方法: MDI 子フォームを作成する</span><span class="sxs-lookup"><span data-stu-id="a6492-140">How to: Create MDI Child Forms</span></span>](../advanced/how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="a6492-141">MenuStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="a6492-141">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
