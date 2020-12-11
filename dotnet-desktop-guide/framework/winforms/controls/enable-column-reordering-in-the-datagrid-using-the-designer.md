---
title: デザイナーを使用して DataGridView コントロールの列の並べ替えを有効にする
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], column order
- Windows Forms, columns
- columns [Windows Forms], reordering
- data [Windows Forms], displaying
ms.assetid: d82bd69c-6799-4439-a32c-91139c5901d1
ms.openlocfilehash: 14dc1081a8608c6e6add67f641c4b55825d2fc81
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981520"
---
# <a name="how-to-enable-column-reordering-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="e88a2-102">方法: デザイナーを使用して Windows フォーム DataGridView コントロールの列の並べ替えを有効にする</span><span class="sxs-lookup"><span data-stu-id="e88a2-102">How to: Enable Column Reordering in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="e88a2-103">Windows フォームコントロールに表示されるデータを表示する場合 <xref:System.Windows.Forms.DataGridView> 、ユーザーは特定の列の値を比較することが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="e88a2-103">When viewing data displayed in a Windows Forms <xref:System.Windows.Forms.DataGridView> control, users sometimes want to compare the values in specific columns.</span></span> <span data-ttu-id="e88a2-104">これは、列がコントロール内で広く使用されている場合には不便です。特に、ユーザーが関心のあるすべての列を表示するために水平方向にスクロールする必要がある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="e88a2-104">This can be inconvenient if the columns are widely separated in the control, especially if users must scroll back and forth horizontally in order to see all the columns they are interested in.</span></span> <span data-ttu-id="e88a2-105">ユーザーが列の順序を変更できるようにすることで、列の値を簡単に比較できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e88a2-105">You can make the task of comparing column values easier by enabling your users to reorder the columns.</span></span> <span data-ttu-id="e88a2-106">列の並べ替えを有効にすると、ユーザーは列ヘッダーをマウスでドラッグすることで、列を新しい位置に移動できます。</span><span class="sxs-lookup"><span data-stu-id="e88a2-106">When you enable column reordering, users can move a column to a new position by dragging the column header with the mouse.</span></span>

 <span data-ttu-id="e88a2-107">次の手順では、コントロールを含むフォームを含む **Windows アプリケーション** プロジェクトが必要です <xref:System.Windows.Forms.DataGridView> 。</span><span class="sxs-lookup"><span data-stu-id="e88a2-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="e88a2-108">このようなプロジェクトの設定の詳細については、「 [方法: Windows フォームアプリケーションプロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project) する」および「 [方法: Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e88a2-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-enable-column-reordering"></a><span data-ttu-id="e88a2-109">列の並べ替えを有効にするには</span><span class="sxs-lookup"><span data-stu-id="e88a2-109">To enable column reordering</span></span>

- <span data-ttu-id="e88a2-110">コントロールの右上隅にある [デザイナーアクション] グリフ ( ![ 小さい黒い矢印) をクリックし、[ ](./media/designer-actions-glyph.gif) 列の <xref:System.Windows.Forms.DataGridView> **並べ替えを有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e88a2-110">Click the designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Enable Column Reordering**.</span></span>

## <a name="see-also"></a><span data-ttu-id="e88a2-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="e88a2-111">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType>
- [<span data-ttu-id="e88a2-112">方法: デザイナーを使用して Windows フォーム DataGridView コントロールの列を固定する</span><span class="sxs-lookup"><span data-stu-id="e88a2-112">How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](freeze-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="e88a2-113">方法: Windows フォームアプリケーションプロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="e88a2-113">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="e88a2-114">方法: Windows フォームにコントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="e88a2-114">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
