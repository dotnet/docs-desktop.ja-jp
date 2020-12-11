---
title: デザイナーを使用して DataGridView コントロールの列の順序を変更する
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], order of
- DataGridView control [Windows Forms], column order
- Windows Forms, columns
- data [Windows Forms], displaying
ms.assetid: 7fe52a98-75d6-448c-97a5-65ca2c568c1a
ms.openlocfilehash: 7540203fb1c0465caeb045275734d1a7c6f25ee8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96975109"
---
# <a name="how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="a9d20-102">方法: デザイナーを使用して Windows フォーム DataGridView コントロールの列の順序を変更する</span><span class="sxs-lookup"><span data-stu-id="a9d20-102">How to: Change the Order of Columns in the Windows Forms DataGridView Control Using the Designer</span></span>

<span data-ttu-id="a9d20-103">Windows フォーム <xref:System.Windows.Forms.DataGridView> コントロールをデータソースにバインドすると、自動的に生成された列の表示順序はデータソースによって決まります。</span><span class="sxs-lookup"><span data-stu-id="a9d20-103">When you bind a Windows Forms <xref:System.Windows.Forms.DataGridView> control to a data source, the display order of the automatically generated columns is dictated by the data source.</span></span> <span data-ttu-id="a9d20-104">この順序が希望どおりでない場合は、デザイナーを使用して列の順序を変更できます。</span><span class="sxs-lookup"><span data-stu-id="a9d20-104">If this order is not what you prefer, you can change the order of the columns using the designer.</span></span> <span data-ttu-id="a9d20-105">コントロールに非バインド列を追加して、表示順序を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="a9d20-105">You may also want to add unbound columns to the control and change their display order.</span></span> <span data-ttu-id="a9d20-106">プログラムによって列の順序を変更する方法の詳細については、「 [方法: Windows フォーム DataGridView コントロールの列の順序を変更](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9d20-106">For information about how to change the column order programmatically, see [How to: Change the Order of Columns in the Windows Forms DataGridView Control](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md).</span></span>

<span data-ttu-id="a9d20-107">次の手順では、コントロールを含むフォームを含む **Windows アプリケーション** プロジェクトが必要です <xref:System.Windows.Forms.DataGridView> 。</span><span class="sxs-lookup"><span data-stu-id="a9d20-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="a9d20-108">このようなプロジェクトの設定の詳細については、「 [方法: Windows フォームアプリケーションプロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project) する」および「 [方法: Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9d20-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-change-the-column-order-using-the-designer"></a><span data-ttu-id="a9d20-109">デザイナーを使用して列の順序を変更するには</span><span class="sxs-lookup"><span data-stu-id="a9d20-109">To change the column order using the designer</span></span>

1. <span data-ttu-id="a9d20-110">コントロールの右上隅にある [デザイナーアクション] グリフ ( ![ 小さい黒い矢印) をクリックし、[ ](./media/designer-actions-glyph.gif) 列の <xref:System.Windows.Forms.DataGridView> **編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a9d20-110">Click the designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>

2. <span data-ttu-id="a9d20-111">[ **選択された列** ] ボックスの一覧から列を選択します。</span><span class="sxs-lookup"><span data-stu-id="a9d20-111">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="a9d20-112">[ **選択さ** れた列] の一覧の右側にある上矢印または下矢印をクリックすると、選択した列が目的の位置に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a9d20-112">Click the up or down arrow to the right of the **Selected Columns** list until the selected column is in the position you want.</span></span>

## <a name="see-also"></a><span data-ttu-id="a9d20-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="a9d20-113">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="a9d20-114">方法: デザイナーを使用して Windows フォーム DataGridView コントロールの列を追加および削除する</span><span class="sxs-lookup"><span data-stu-id="a9d20-114">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="a9d20-115">方法: Windows フォームアプリケーションプロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="a9d20-115">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="a9d20-116">方法: Windows フォームにコントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="a9d20-116">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
