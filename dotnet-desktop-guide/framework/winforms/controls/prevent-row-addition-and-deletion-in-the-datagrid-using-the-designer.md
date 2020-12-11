---
title: デザイナーを使用した DataGridView コントロールでの行の追加と削除の防止
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], preventing row addition or deletion
ms.assetid: a17722bd-9400-41e6-8dcc-c9c151f0a749
ms.openlocfilehash: cca497aeaedd0c9f988241092eed707ecc259859
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981947"
---
# <a name="how-to-prevent-row-addition-and-deletion-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="ac306-102">方法: デザイナーを使用して Windows フォーム DataGridView コントロールで行が追加および削除されないようにする</span><span class="sxs-lookup"><span data-stu-id="ac306-102">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="ac306-103">場合によっては、ユーザーが <xref:System.Windows.Forms.DataGridView> コントロールに新しいデータ行を入力したり、既存の行を削除したりできないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac306-103">Sometimes you will want to prevent users from entering new rows of data or deleting existing rows in your <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="ac306-104">コントロールの下部に新しいレコードがある場合は、新しい行が特別な行に入力されます。</span><span class="sxs-lookup"><span data-stu-id="ac306-104">New rows are entered in the special row for new records at the bottom of the control.</span></span> <span data-ttu-id="ac306-105">行の追加を無効にした場合、新しいレコードの行は表示されません。</span><span class="sxs-lookup"><span data-stu-id="ac306-105">When you disable row addition, the row for new records is not displayed.</span></span> <span data-ttu-id="ac306-106">行の削除とセルの編集を無効にすることで、コントロールを完全に読み取り専用にすることができます。</span><span class="sxs-lookup"><span data-stu-id="ac306-106">You can then make the control entirely read-only by disabling row deletion and cell editing.</span></span>

 <span data-ttu-id="ac306-107">次の手順では、コントロールを含むフォームを含む **Windows アプリケーション** プロジェクトが必要です <xref:System.Windows.Forms.DataGridView> 。</span><span class="sxs-lookup"><span data-stu-id="ac306-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="ac306-108">このようなプロジェクトの設定の詳細については、「 [方法: Windows フォームアプリケーションプロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project) する」および「 [方法: Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac306-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-prevent-row-addition-and-deletion"></a><span data-ttu-id="ac306-109">行の追加と削除を防止するには</span><span class="sxs-lookup"><span data-stu-id="ac306-109">To prevent row addition and deletion</span></span>

- <span data-ttu-id="ac306-110">コントロールの右上隅にある [デザイナーアクション] グリフ ( ![ 小さい黒い矢印) をクリック ](./media/designer-actions-glyph.gif) <xref:System.Windows.Forms.DataGridView> し、[**削除** の **追加** と有効化] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="ac306-110">Click the designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then clear the **Enable Adding** and **Enable Deleting** check boxes.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ac306-111">コントロールを完全に読み取り専用にするには、[ **編集を有効に** する] チェックボックスもオフにします。</span><span class="sxs-lookup"><span data-stu-id="ac306-111">To make the control entirely read-only, clear the **Enable Editing** check box as well.</span></span>

## <a name="see-also"></a><span data-ttu-id="ac306-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="ac306-112">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>
- [<span data-ttu-id="ac306-113">方法: Windows フォームアプリケーションプロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="ac306-113">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="ac306-114">方法: Windows フォームにコントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="ac306-114">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
