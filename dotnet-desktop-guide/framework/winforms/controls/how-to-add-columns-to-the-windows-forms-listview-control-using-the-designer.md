---
title: デザイナーを使用して ListView コントロールに列を追加する
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
ms.assetid: 5b1a8b4d-587e-479a-95c1-f9b90884f13a
ms.openlocfilehash: 627f8627aac861877a05c13def07427199807754
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981475"
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="5236e-102">方法: デザイナーを使って Windows フォーム ListView コントロールに列を追加する</span><span class="sxs-lookup"><span data-stu-id="5236e-102">How to: Add Columns to the Windows Forms ListView Control Using the Designer</span></span>

<span data-ttu-id="5236e-103">Windows フォーム <xref:System.Windows.Forms.ListView> コントロールでは、 **詳細** ビューで各リスト項目に対して複数の列を表示できます。</span><span class="sxs-lookup"><span data-stu-id="5236e-103">The Windows Forms <xref:System.Windows.Forms.ListView> control can display multiple columns for each list item when in the **Details** view.</span></span> <span data-ttu-id="5236e-104">列を使用して、各リスト項目に関するいくつかの種類の情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="5236e-104">You can use the columns to display several types of information about each list item.</span></span> <span data-ttu-id="5236e-105">たとえば、ファイルの一覧には、ファイル名、ファイルの種類、サイズ、ファイルが最後に変更された日付が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5236e-105">For example, a list of files could display the file name, file type, size, and date the file was last modified.</span></span> <span data-ttu-id="5236e-106">作成後に列を設定する方法の詳細については、「 [方法: Windows フォーム ListView コントロールを使用して列にサブ項目を表示する](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5236e-106">For information on populating the columns once they are created, see [How to: Display Subitems in Columns with the Windows Forms ListView Control](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).</span></span>

<span data-ttu-id="5236e-107">次の手順では、コントロールを含むフォームを含む **Windows アプリケーション** プロジェクトが必要です <xref:System.Windows.Forms.ListView> 。</span><span class="sxs-lookup"><span data-stu-id="5236e-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="5236e-108">このようなプロジェクトの設定の詳細については、「 [方法: Windows フォームアプリケーションプロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project) する」および「 [方法: Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5236e-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

### <a name="to-add-columns-in-the-designer"></a><span data-ttu-id="5236e-109">デザイナーで列を追加するには</span><span class="sxs-lookup"><span data-stu-id="5236e-109">To add columns in the designer</span></span>

1. <span data-ttu-id="5236e-110">[ **プロパティ** ] ウィンドウで、コントロールの <xref:System.Windows.Forms.ListView.View%2A> プロパティをに設定し <xref:System.Windows.Forms.View.Details> ます。</span><span class="sxs-lookup"><span data-stu-id="5236e-110">In the **Properties** window, set the control's <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Details>.</span></span>

2. <span data-ttu-id="5236e-111">[ **プロパティ** ] ウィンドウで、プロパティの横に **ある省略記号ボタン (** ![ Visual Studio のプロパティウィンドウの省略記号ボタン (...)) をクリックし ](./media/visual-studio-ellipsis-button.png) <xref:System.Windows.Forms.ListView.Columns%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="5236e-111">In the **Properties** window, click the **Ellipsis** button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.ListView.Columns%2A> property.</span></span>

     <span data-ttu-id="5236e-112">**Columnheader コレクションエディター** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5236e-112">The **ColumnHeader Collection Editor** appears.</span></span>

3. <span data-ttu-id="5236e-113">新しい列を追加するには、[ **追加** ] ボタンを使用します。</span><span class="sxs-lookup"><span data-stu-id="5236e-113">Use the **Add** button to add new columns.</span></span> <span data-ttu-id="5236e-114">次に、列ヘッダーを選択し、そのテキスト (列のキャプション)、テキストの配置、および幅を設定できます。</span><span class="sxs-lookup"><span data-stu-id="5236e-114">You can then select the column header and set its text (the caption of the column), text alignment, and width.</span></span>

## <a name="see-also"></a><span data-ttu-id="5236e-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="5236e-115">See also</span></span>

- [<span data-ttu-id="5236e-116">ListView コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="5236e-116">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="5236e-117">方法: Windows フォーム ListView コントロールで項目を追加および削除する</span><span class="sxs-lookup"><span data-stu-id="5236e-117">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="5236e-118">方法: Windows フォーム ListView コントロールの列にサブ項目を表示する</span><span class="sxs-lookup"><span data-stu-id="5236e-118">How to: Display Subitems in Columns with the Windows Forms ListView Control</span></span>](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="5236e-119">方法: Windows フォーム ListView コントロールのアイコンを表示する</span><span class="sxs-lookup"><span data-stu-id="5236e-119">How to: Display Icons for the Windows Forms ListView Control</span></span>](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [<span data-ttu-id="5236e-120">方法: TreeView コントロールまたは ListView コントロール (Windows フォーム) にカスタム情報を追加する</span><span class="sxs-lookup"><span data-stu-id="5236e-120">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
