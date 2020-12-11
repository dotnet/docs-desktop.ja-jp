---
title: デザイナーを使用して DataGridView コントロールの列を追加および削除する
ms.date: 03/30/2017
f1_keywords:
- vs.DataGridViewAddColumnDialog
helpviewer_keywords:
- DataGridView control [Windows Forms], adding columns
- DataGridView control [Windows Forms], removing columns
ms.assetid: 9e709f35-0a8c-4e7e-b4c4-bacb7a834077
ms.openlocfilehash: 8843b1d30f3e5f31a060e27b41b0105e6584f155
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96975162"
---
# <a name="how-to-add-and-remove-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="4acbf-102">方法: デザイナーを使用して Windows フォーム DataGridView コントロールの列を追加および削除する</span><span class="sxs-lookup"><span data-stu-id="4acbf-102">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="4acbf-103">Windows フォームコントロールには、 <xref:System.Windows.Forms.DataGridView> データを表示するための列が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4acbf-103">The Windows Forms <xref:System.Windows.Forms.DataGridView> control must contain columns in order to display data.</span></span> <span data-ttu-id="4acbf-104">コントロールを手動で設定する場合は、自分で列を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4acbf-104">If you plan to populate the control manually, you must add the columns yourself.</span></span> <span data-ttu-id="4acbf-105">または、データソースにコントロールをバインドして、列を自動的に生成して設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="4acbf-105">Alternately, you can bind the control to a data source, which generates and populates the columns automatically.</span></span> <span data-ttu-id="4acbf-106">表示する列数よりも多くの列がデータソースに含まれている場合は、不要な列を削除できます。</span><span class="sxs-lookup"><span data-stu-id="4acbf-106">If the data source contains more columns than you want to display, you can remove the unwanted columns.</span></span>

 <span data-ttu-id="4acbf-107">次の手順では、コントロールを含むフォームを含む **Windows アプリケーション** プロジェクトが必要 <xref:System.Windows.Forms.DataGridView> です。</span><span class="sxs-lookup"><span data-stu-id="4acbf-107">The following procedures require a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="4acbf-108">このようなプロジェクトの設定の詳細については、「 [方法: Windows フォームアプリケーションプロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project) する」および「 [方法: Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4acbf-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-add-a-column-using-the-designer"></a><span data-ttu-id="4acbf-109">デザイナーを使用して列を追加するには</span><span class="sxs-lookup"><span data-stu-id="4acbf-109">To add a column using the designer</span></span>

1. <span data-ttu-id="4acbf-110">コントロールの右上隅にある [デザイナーアクション] グリフ ( ![ 小さい黒い矢印) をクリックし、[ ](./media/designer-actions-glyph.gif) <xref:System.Windows.Forms.DataGridView> 列の **追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4acbf-110">Click the designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Add Column**.</span></span>

2. <span data-ttu-id="4acbf-111">[ **列の追加** ] ダイアログボックスで、[データ **バインド列** ] オプションを選択し、データソースから列を選択するか、[ **非バインド列** ] オプションを選択して、提供されたフィールドを使用して列を定義します。</span><span class="sxs-lookup"><span data-stu-id="4acbf-111">In the **Add Column** dialog box, choose the **Databound Column** option and select a column from the data source, or choose the **Unbound Column** option and define the column using the fields provided.</span></span>

3. <span data-ttu-id="4acbf-112">[ **追加** ] ボタンをクリックして列を追加すると、既存の列がコントロールの表示領域にまだ表示されていない場合に、その列がデザイナーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="4acbf-112">Click the **Add** button to add the column, causing it to appear in the designer if the existing columns do not already fill the control display area.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4acbf-113">[ **列の編集** ] ダイアログボックスでは、コントロールのスマートタグからアクセスできる列のプロパティを変更できます。</span><span class="sxs-lookup"><span data-stu-id="4acbf-113">You can modify column properties in the **Edit Columns** dialog box, which you can access from the control's smart tag.</span></span>

## <a name="to-remove-a-column-using-the-designer"></a><span data-ttu-id="4acbf-114">デザイナーを使用して列を削除するには</span><span class="sxs-lookup"><span data-stu-id="4acbf-114">To remove a column using the designer</span></span>

1. <span data-ttu-id="4acbf-115">コントロールのスマートタグから [ **列の編集** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4acbf-115">Choose **Edit Columns** from the control's smart tag.</span></span>

2. <span data-ttu-id="4acbf-116">[ **選択された列** ] ボックスの一覧から列を選択します。</span><span class="sxs-lookup"><span data-stu-id="4acbf-116">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="4acbf-117">列を削除するには、[ **削除** ] ボタンをクリックします。これにより、デザイナーに表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="4acbf-117">Click the **Remove** button to delete the column, causing it to disappear from the designer.</span></span>

## <a name="see-also"></a><span data-ttu-id="4acbf-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="4acbf-118">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="4acbf-119">方法: Windows フォームアプリケーションプロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="4acbf-119">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="4acbf-120">方法: Windows フォームにコントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="4acbf-120">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
