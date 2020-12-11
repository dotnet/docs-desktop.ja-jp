---
title: デザイナーを使用して DataGridView コントロールの列を固定する
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], freezing
- DataGridView control [Windows Forms], column freezing
- data [Windows Forms], displaying
ms.assetid: 87412dd2-478f-4751-af87-dafc591fc215
ms.openlocfilehash: 554d5eaa55401bdafc455c2dfb20d7c5d214a9be
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981052"
---
# <a name="how-to-freeze-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="e1c43-102">方法: デザイナーを使用して Windows フォーム DataGridView コントロールの列を固定する</span><span class="sxs-lookup"><span data-stu-id="e1c43-102">How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer</span></span>

<span data-ttu-id="e1c43-103">ユーザーが Windows フォームの <xref:System.Windows.Forms.DataGridView> コントロールに表示されるデータを確認するときに、1 つの列または列のセットを頻繁に参照しなければならないことがあります。</span><span class="sxs-lookup"><span data-stu-id="e1c43-103">When users view data displayed in a Windows Forms <xref:System.Windows.Forms.DataGridView> control, they sometimes need to refer to a single column or set of columns frequently.</span></span> <span data-ttu-id="e1c43-104">たとえば、多数の列が含まれている顧客情報のテーブルを表示する場合、他の列を表示可能な領域の外側にスクロールできるようにしながら、常に顧客名を表示すると便利です。</span><span class="sxs-lookup"><span data-stu-id="e1c43-104">For example, when you display a table of customer information that contains many columns, it is useful for you to display the customer name at all times while enabling other columns to scroll outside the visible region.</span></span>

 <span data-ttu-id="e1c43-105">この動作を実現するために、コントロールの列を固定することができます。</span><span class="sxs-lookup"><span data-stu-id="e1c43-105">To achieve this behavior, you can freeze columns in the control.</span></span> <span data-ttu-id="e1c43-106">列を固定すると、左側 (右から左へ記述する言語のスクリプトでは右側) のすべての列も同様に固定されます。</span><span class="sxs-lookup"><span data-stu-id="e1c43-106">When you freeze a column, all the columns to its left (or to its right in right-to-left language scripts) are frozen as well.</span></span> <span data-ttu-id="e1c43-107">固定された列は表示されたままになり、その他のすべての列はスクロールできます。</span><span class="sxs-lookup"><span data-stu-id="e1c43-107">Frozen columns remain in place while all other columns can scroll.</span></span> <span data-ttu-id="e1c43-108">列の並べ替えが有効な場合、固定された列は、固定されていない列とは異なるグループとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="e1c43-108">If column reordering is enabled, the frozen columns are treated as a group distinct from the unfrozen columns.</span></span> <span data-ttu-id="e1c43-109">ユーザーは、どちらかのグループに列を再配置できますが、1 つのグループから別のグループに列を移動することはできません。</span><span class="sxs-lookup"><span data-stu-id="e1c43-109">Users can reposition columns in either group, but they cannot move a column from one group to the other.</span></span>

 <span data-ttu-id="e1c43-110">次の手順では、コントロールを含むフォームを含む **Windows アプリケーション** プロジェクトが必要です <xref:System.Windows.Forms.DataGridView> 。</span><span class="sxs-lookup"><span data-stu-id="e1c43-110">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="e1c43-111">このようなプロジェクトの設定の詳細については、「 [方法: Windows フォームアプリケーションプロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project) する」および「 [方法: Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1c43-111">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-freeze-a-column-using-the-designer"></a><span data-ttu-id="e1c43-112">デザイナーを使用して列を固定するには</span><span class="sxs-lookup"><span data-stu-id="e1c43-112">To freeze a column using the designer</span></span>

1. <span data-ttu-id="e1c43-113">コントロールの右上隅にある [デザイナーアクション] グリフ ( ![ 小さい黒い矢印) をクリックし、[ ](./media/designer-actions-glyph.gif) 列の <xref:System.Windows.Forms.DataGridView> **編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1c43-113">Click the designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>

2. <span data-ttu-id="e1c43-114">[ **選択された列** ] ボックスの一覧から列を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1c43-114">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="e1c43-115">列の **プロパティ** グリッドで、 <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> プロパティをに設定し `true` ます。</span><span class="sxs-lookup"><span data-stu-id="e1c43-115">In the **Column Properties** grid, set the <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> property to `true`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e1c43-116">[**列の追加**] ダイアログボックスで **固定** されたボックスを選択して、列を追加するときに固定することもできます。</span><span class="sxs-lookup"><span data-stu-id="e1c43-116">You can also freeze a column when adding it by selecting the **Frozen** box in the **Add Column** dialog box.</span></span>

## <a name="see-also"></a><span data-ttu-id="e1c43-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="e1c43-117">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType>
- [<span data-ttu-id="e1c43-118">方法: デザイナーを使用して Windows フォーム DataGridView コントロールの列を追加および削除する</span><span class="sxs-lookup"><span data-stu-id="e1c43-118">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="e1c43-119">方法: デザイナーを使用して Windows フォーム DataGridView コントロールの列の並べ替えを有効にする</span><span class="sxs-lookup"><span data-stu-id="e1c43-119">How to: Enable Column Reordering in the Windows Forms DataGridView Control Using the Designer</span></span>](enable-column-reordering-in-the-datagrid-using-the-designer.md)
- <span data-ttu-id="e1c43-120">[方法 : グローバリゼーション用に Windows フォームで右から左の方向でテキストを表示する](/previous-versions/visualstudio/visual-studio-2010/7d3337xw(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="e1c43-120">[How to: Display Right-to-Left Text in Windows Forms for Globalization](/previous-versions/visualstudio/visual-studio-2010/7d3337xw(v=vs.100))</span></span>
- [<span data-ttu-id="e1c43-121">方法: Windows フォームアプリケーションプロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="e1c43-121">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="e1c43-122">方法: Windows フォームにコントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="e1c43-122">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
