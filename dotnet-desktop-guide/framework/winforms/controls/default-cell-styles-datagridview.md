---
title: デザイナーを使用して DataGridView コントロールの既定のセルスタイルとデータ形式を設定する
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], setting styles
- data formats
- data [Windows Forms], setting formats
ms.assetid: fc6da49f-8942-41da-b49f-b2afc38cc656
ms.openlocfilehash: ca602fa15e4648550bfa171a9c3abd057e930eca
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974205"
---
# <a name="how-to-set-default-cell-styles-and-data-formats-for-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="87f0d-102">方法: デザイナーを使用して Windows フォーム DataGridView コントロールの既定のセル スタイルとデータ形式を設定する</span><span class="sxs-lookup"><span data-stu-id="87f0d-102">How to: Set Default Cell Styles and Data Formats for the Windows Forms DataGridView Control Using the Designer</span></span>

<span data-ttu-id="87f0d-103">コントロールを使用すると、 <xref:System.Windows.Forms.DataGridView> コントロール全体、特定の列、行ヘッダー、列ヘッダー、および行と列のヘッダーに対して既定のセルスタイルとセルデータ形式を指定できます。また、行を交互に使用して、元帳効果を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="87f0d-103">The <xref:System.Windows.Forms.DataGridView> control lets you specify default cell styles and cell data formats for the entire control, for specific columns, for row and column headers, and for alternating rows to create a ledger effect.</span></span> <span data-ttu-id="87f0d-104">コントロール全体に対して設定されている既定のスタイルは、列および交互の行に対して設定された既定のスタイルによって上書きされます。</span><span class="sxs-lookup"><span data-stu-id="87f0d-104">Default styles set for the entire control are overridden by default styles set for columns and alternating rows.</span></span> <span data-ttu-id="87f0d-105">また、個々の行およびセルのコードで設定したスタイルは、既定のスタイルを上書きします。</span><span class="sxs-lookup"><span data-stu-id="87f0d-105">Additionally, styles that you set in code for individual rows and cells override the default styles.</span></span>

<span data-ttu-id="87f0d-106">セルスタイルの詳細については、「 [Windows フォーム DataGridView コントロールのセルのスタイル](cell-styles-in-the-windows-forms-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87f0d-106">For more information about cell styles, see [Cell Styles in the Windows Forms DataGridView Control](cell-styles-in-the-windows-forms-datagridview-control.md).</span></span> <span data-ttu-id="87f0d-107">交互の行のスタイルを設定する方法については、「 [方法: デザイナーを使用して Windows フォーム DataGridView コントロールに交互の行のスタイルを設定](set-alternating-row-styles-for-the-datagrid-using-the-designer.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87f0d-107">To set styles for alternating rows, see [How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer](set-alternating-row-styles-for-the-datagrid-using-the-designer.md).</span></span>

<span data-ttu-id="87f0d-108">また、プロパティを使用してスタイルを設定し、 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> コントロールに追加されるすべての行に影響を与えることもできます。</span><span class="sxs-lookup"><span data-stu-id="87f0d-108">You can also set styles using the <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> property to affect all rows that will be added to the control.</span></span> <span data-ttu-id="87f0d-109">行テンプレートの詳細については、「 [方法: 行テンプレートを使用して Windows フォーム DataGridView コントロールで行をカスタマイズする](use-the-row-template-to-customize-rows-in-the-datagrid.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87f0d-109">For more information about the row template, see [How to: Use the Row Template to Customize Rows in the Windows Forms DataGridView Control](use-the-row-template-to-customize-rows-in-the-datagrid.md).</span></span>

<span data-ttu-id="87f0d-110">次の手順では、コントロールを含むフォームを含む **Windows アプリケーション** プロジェクトが必要 <xref:System.Windows.Forms.DataGridView> です。</span><span class="sxs-lookup"><span data-stu-id="87f0d-110">The following procedures require a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="87f0d-111">このようなプロジェクトの設定の詳細については、「 [方法: Windows フォームアプリケーションプロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project) する」および「 [方法: Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87f0d-111">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

### <a name="to-set-default-styles-for-all-cells-in-the-control"></a><span data-ttu-id="87f0d-112">コントロール内のすべてのセルに既定のスタイルを設定するには</span><span class="sxs-lookup"><span data-stu-id="87f0d-112">To set default styles for all cells in the control</span></span>

1. <span data-ttu-id="87f0d-113"><xref:System.Windows.Forms.DataGridView>デザイナーでコントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="87f0d-113">Select the <xref:System.Windows.Forms.DataGridView> control in the designer.</span></span>

2. <span data-ttu-id="87f0d-114">[ **プロパティ** ] ウィンドウで、 ![ 、、 ](./media/visual-studio-ellipsis-button.png) <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> またはの各 <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> プロパティの横 <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> にある省略記号ボタン ([...] プロパティウィンドウ) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87f0d-114">In the **Properties** window, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>, or <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> property.</span></span> <span data-ttu-id="87f0d-115">[ **CellStyle ビルダー** ] ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="87f0d-115">The **CellStyle Builder** dialog box appears.</span></span>

3. <span data-ttu-id="87f0d-116">**プレビュー** ウィンドウを使用して選択内容を確認し、プロパティを設定してスタイルを定義します。</span><span class="sxs-lookup"><span data-stu-id="87f0d-116">Define the style by setting the properties, using the **Preview** pane to confirm your choices.</span></span>

> [!NOTE]
> <span data-ttu-id="87f0d-117">視覚スタイルが有効になっている場合、行ヘッダーと列ヘッダー (を除く <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A> ) は、現在のテーマによって自動的にスタイルが設定され、 <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> プロパティ値とプロパティ値はオーバーライドされ <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="87f0d-117">If visual styles are enabled, the row and column headers (except for the <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>) are automatically styled by the current theme, overriding the <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> and <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> property values.</span></span>
>
> <span data-ttu-id="87f0d-118">デザイナーを使用して、複数の選択したコントロールのセルスタイルを設定でき <xref:System.Windows.Forms.DataGridView> ますが、変更するセルスタイルプロパティの値が同じである場合に限られます。</span><span class="sxs-lookup"><span data-stu-id="87f0d-118">You can set cell styles for multiple selected <xref:System.Windows.Forms.DataGridView> controls using the designer, but only if they have identical values for the cell style property you want to modify.</span></span> <span data-ttu-id="87f0d-119">そのプロパティのセルスタイルが異なる場合、[ **CellStyle ビルダー** ] ダイアログボックスの [**プロパティ**] ウィンドウは空白になります。</span><span class="sxs-lookup"><span data-stu-id="87f0d-119">If any cell styles differ for that property, the **Properties** windows of the **CellStyle Builder** dialog box will be blank.</span></span>

### <a name="to-set-default-styles-for-cells-in-individual-columns"></a><span data-ttu-id="87f0d-120">個々の列のセルに既定のスタイルを設定するには</span><span class="sxs-lookup"><span data-stu-id="87f0d-120">To set default styles for cells in individual columns</span></span>

1. <span data-ttu-id="87f0d-121">デザイナーでコントロールを右クリックし、[ <xref:System.Windows.Forms.DataGridView> **列の編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="87f0d-121">Right-click the <xref:System.Windows.Forms.DataGridView> control in the designer and choose **Edit Columns**.</span></span>

2. <span data-ttu-id="87f0d-122">[ **選択された列** ] ボックスの一覧から列を選択します。</span><span class="sxs-lookup"><span data-stu-id="87f0d-122">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="87f0d-123">[ **列のプロパティ** ] グリッドで、プロパティの横にある省略記号ボタン ( ![ Visual Studio のプロパティウィンドウの省略記号ボタン (...)) をクリックし ](./media/visual-studio-ellipsis-button.png) <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="87f0d-123">In the **Column Properties** grid, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> property.</span></span> <span data-ttu-id="87f0d-124">[ **CellStyle ビルダー** ] ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="87f0d-124">The **CellStyle Builder** dialog box appears.</span></span>

4. <span data-ttu-id="87f0d-125">**プレビュー** ウィンドウを使用して選択内容を確認し、プロパティを設定してスタイルを定義します。</span><span class="sxs-lookup"><span data-stu-id="87f0d-125">Define the style by setting the properties, using the **Preview** pane to confirm your choices.</span></span>

### <a name="to-format-data-in-cells"></a><span data-ttu-id="87f0d-126">セルのデータの書式を設定するには</span><span class="sxs-lookup"><span data-stu-id="87f0d-126">To format data in cells</span></span>

1. <span data-ttu-id="87f0d-127">前の手順のいずれかを使用して、既定のセルスタイルプロパティに関連する [ **CellStyle ビルダー** ] ダイアログボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="87f0d-127">Use one of the preceding procedures to display a **CellStyle Builder** dialog box related to a default cell style property.</span></span>

2. <span data-ttu-id="87f0d-128">[ **CellStyle ビルダー** ] ダイアログボックスで、プロパティの横にある省略記号ボタン ( ![ Visual Studio のプロパティウィンドウの省略記号ボタン ([...]) をクリックし ](./media/visual-studio-ellipsis-button.png) <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="87f0d-128">In the **CellStyle Builder** dialog box, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> property.</span></span> <span data-ttu-id="87f0d-129">[ **書式文字列** ] ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="87f0d-129">The **Format String** dialog box appears.</span></span>

3. <span data-ttu-id="87f0d-130">書式の種類を選択してから、[ **サンプル** ] ボックスを使用して選択内容を確認し、種類の詳細 (表示する小数点以下の桁数など) を変更します。</span><span class="sxs-lookup"><span data-stu-id="87f0d-130">Select a format type, then modify the details of the type (such as the number of decimal places to display), using the **Sample** box to confirm your choices.</span></span>

4. <span data-ttu-id="87f0d-131"><xref:System.Windows.Forms.DataGridView>Null 値が含まれる可能性のあるデータソースにコントロールをバインドする場合は、[ **null 値**] ボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="87f0d-131">If you are binding the <xref:System.Windows.Forms.DataGridView> control to a data source that is likely to contain null values, fill in the **Null Value** text box.</span></span> <span data-ttu-id="87f0d-132">この値は、セルの値が null 参照 ( `Nothing` Visual Basic) またはである場合に表示され <xref:System.DBNull.Value?displayProperty=nameWithType> ます。</span><span class="sxs-lookup"><span data-stu-id="87f0d-132">This value is displayed when the cell value is equal to a null reference (`Nothing` in Visual Basic) or <xref:System.DBNull.Value?displayProperty=nameWithType>.</span></span>

## <a name="see-also"></a><span data-ttu-id="87f0d-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="87f0d-133">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A?displayProperty=nameWithType>
- [<span data-ttu-id="87f0d-134">Windows フォーム DataGridView コントロールでのセルのスタイル</span><span class="sxs-lookup"><span data-stu-id="87f0d-134">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="87f0d-135">方法: デザイナーを使用して Windows フォーム DataGridView コントロールに交互の行のスタイルを設定する</span><span class="sxs-lookup"><span data-stu-id="87f0d-135">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer</span></span>](set-alternating-row-styles-for-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="87f0d-136">方法: Windows フォームアプリケーションプロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="87f0d-136">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="87f0d-137">方法: Windows フォームにコントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="87f0d-137">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
