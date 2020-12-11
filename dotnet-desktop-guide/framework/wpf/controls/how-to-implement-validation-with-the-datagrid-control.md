---
title: '方法: DataGrid コントロールを使用して検証を実装する'
description: Windows Presentation Foundation の DataGrid コントロールによって、セルおよび行の両方のレベルで検証が実行され、検証エラーに関するフィードバックが提供されるしくみについて説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], validation
- validation [WPF], DataGrid
ms.assetid: ec6078a8-1e42-4648-b414-f4348e81bda1
ms.openlocfilehash: c45535a08d8c11450e8614c100b94c9b67ea2272
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985851"
---
# <a name="how-to-implement-validation-with-the-datagrid-control"></a><span data-ttu-id="a79b2-103">方法: DataGrid コントロールを使用して検証を実装する</span><span class="sxs-lookup"><span data-stu-id="a79b2-103">How to: Implement Validation with the DataGrid Control</span></span>
<span data-ttu-id="a79b2-104"><xref:System.Windows.Controls.DataGrid> コントロールを使用すると、セル レベルと行レベルの両方で検証を実行できます。</span><span class="sxs-lookup"><span data-stu-id="a79b2-104">The <xref:System.Windows.Controls.DataGrid> control enables you to perform validation at both the cell and row level.</span></span> <span data-ttu-id="a79b2-105">セル レベルの検証では、ユーザーが値を更新するときに、バインドされたデータ オブジェクトの個々のプロパティが検証されます。</span><span class="sxs-lookup"><span data-stu-id="a79b2-105">With cell-level validation, you validate individual properties of a bound data object when a user updates a value.</span></span> <span data-ttu-id="a79b2-106">行レベルの検証では、ユーザーが変更を行にコミットするときに、データ オブジェクト全体が検証されます。</span><span class="sxs-lookup"><span data-stu-id="a79b2-106">With row-level validation, you validate entire data objects when a user commits changes to a row.</span></span> <span data-ttu-id="a79b2-107">また、検証エラーに対してカスタマイズした視覚的フィードバックを提供したり、<xref:System.Windows.Controls.DataGrid> コントロールで提供される既定の視覚的フィードバックを使用したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a79b2-107">You can also provide customized visual feedback for validation errors, or use the default visual feedback that the <xref:System.Windows.Controls.DataGrid> control provides.</span></span>  
  
 <span data-ttu-id="a79b2-108">次の手順では、<xref:System.Windows.Controls.DataGrid> のバインディングに検証規則を適用する方法、および視覚的なフィードバックをカスタマイズする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a79b2-108">The following procedures describe how to apply validation rules to <xref:System.Windows.Controls.DataGrid> bindings and customize the visual feedback.</span></span>  
  
### <a name="to-validate-individual-cell-values"></a><span data-ttu-id="a79b2-109">個々のセルの値を検証するには</span><span class="sxs-lookup"><span data-stu-id="a79b2-109">To validate individual cell values</span></span>  
  
- <span data-ttu-id="a79b2-110">列で使用されているバインディングに対して 1 つ以上の検証規則を指定します。</span><span class="sxs-lookup"><span data-stu-id="a79b2-110">Specify one or more validation rules on the binding used with a column.</span></span> <span data-ttu-id="a79b2-111">これは、[データ バインディングの概要](/dotnet/desktop-wpf/data/data-binding-overview)に関する記事で説明されている、単純なコントロールでのデータの検証に似ています。</span><span class="sxs-lookup"><span data-stu-id="a79b2-111">This is similar to validating data in simple controls, as described in [Data Binding Overview](/dotnet/desktop-wpf/data/data-binding-overview).</span></span>  
  
     <span data-ttu-id="a79b2-112">次の例では、ビジネス オブジェクトの異なるプロパティにバインドされた 4 つの列が含まれる <xref:System.Windows.Controls.DataGrid> コントロールを示します。</span><span class="sxs-lookup"><span data-stu-id="a79b2-112">The following example shows a <xref:System.Windows.Controls.DataGrid> control with four columns bound to different properties of a business object.</span></span> <span data-ttu-id="a79b2-113">3 つの列では、<xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> プロパティを `true` に設定することによって、<xref:System.Windows.Controls.ExceptionValidationRule> を指定します。</span><span class="sxs-lookup"><span data-stu-id="a79b2-113">Three of the columns specify the <xref:System.Windows.Controls.ExceptionValidationRule> by setting the <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> property to `true`.</span></span>  
  
     [!code-xaml[DataGrid_Validation#BasicXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/window1.xaml#basicxaml)]  
  
     <span data-ttu-id="a79b2-114">ユーザーが無効な値を入力すると (たとえば、[Course ID] 列に対して整数以外の値)、そのセルの周囲に赤い枠線が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a79b2-114">When a user enters an invalid value (such as a non-integer in the Course ID column), a red border appears around the cell.</span></span> <span data-ttu-id="a79b2-115">次の手順で説明するようにして、この既定の検証フィードバックを変更できます。</span><span class="sxs-lookup"><span data-stu-id="a79b2-115">You can change this default validation feedback as described in the following procedure.</span></span>  
  
### <a name="to-customize-cell-validation-feedback"></a><span data-ttu-id="a79b2-116">セルの検証のフィードバックをカスタマイズするには</span><span class="sxs-lookup"><span data-stu-id="a79b2-116">To customize cell validation feedback</span></span>  
  
- <span data-ttu-id="a79b2-117">列の <xref:System.Windows.Controls.DataGridBoundColumn.EditingElementStyle%2A> プロパティを、列の編集コントロールに適したスタイルに設定します。</span><span class="sxs-lookup"><span data-stu-id="a79b2-117">Set the column's <xref:System.Windows.Controls.DataGridBoundColumn.EditingElementStyle%2A> property to a style appropriate for the column's editing control.</span></span> <span data-ttu-id="a79b2-118">編集コントロールは実行時に作成されるため、単純なコントロールの場合のような、<xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType> 添付プロパティを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="a79b2-118">Because the editing controls are created at run time, you cannot use the <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType> attached property like you would with simple controls.</span></span>  
  
     <span data-ttu-id="a79b2-119">次の例では、前の例を更新して、検証規則のある 3 つの列によって共有されるエラー スタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="a79b2-119">The following example updates the previous example by adding an error style shared by the three columns with validation rules.</span></span> <span data-ttu-id="a79b2-120">ユーザーが無効な値を入力すると、スタイルによってセルの背景色が変更され、ツールヒントが追加されます。</span><span class="sxs-lookup"><span data-stu-id="a79b2-120">When a user enters an invalid value, the style changes the cell background color and adds a ToolTip.</span></span> <span data-ttu-id="a79b2-121">検証エラーがあるかどうかを確認するためのトリガーの使用に注意してください。</span><span class="sxs-lookup"><span data-stu-id="a79b2-121">Note the use of a trigger to determine whether there is a validation error.</span></span> <span data-ttu-id="a79b2-122">現在はセルに専用のエラー テンプレートがないため、このようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a79b2-122">This is required because there is currently no dedicated error template for cells.</span></span>  
  
     [!code-xaml[DataGrid_Validation#CellValidationXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#cellvalidationxaml)]  
  
     <span data-ttu-id="a79b2-123">列で使用されている <xref:System.Windows.Controls.DataGridColumn.CellStyle%2A> を置き換えることで、より広範なカスタマイズを実装できます。</span><span class="sxs-lookup"><span data-stu-id="a79b2-123">You can implement more extensive customization by replacing the <xref:System.Windows.Controls.DataGridColumn.CellStyle%2A> used by the column.</span></span>  
  
### <a name="to-validate-multiple-values-in-a-single-row"></a><span data-ttu-id="a79b2-124">1 つの行で複数の値を検証するには</span><span class="sxs-lookup"><span data-stu-id="a79b2-124">To validate multiple values in a single row</span></span>  
  
1. <span data-ttu-id="a79b2-125">バインドされたデータ オブジェクトの複数のプロパティを調べる <xref:System.Windows.Controls.ValidationRule> サブクラスを実装します。</span><span class="sxs-lookup"><span data-stu-id="a79b2-125">Implement a <xref:System.Windows.Controls.ValidationRule> subclass that checks multiple properties of the bound data object.</span></span> <span data-ttu-id="a79b2-126"><xref:System.Windows.Controls.ValidationRule.Validate%2A> メソッドの実装では、`value` パラメーター値を <xref:System.Windows.Data.BindingGroup> インスタンスにキャストします。</span><span class="sxs-lookup"><span data-stu-id="a79b2-126">In your <xref:System.Windows.Controls.ValidationRule.Validate%2A> method implementation, cast the `value` parameter value to a <xref:System.Windows.Data.BindingGroup> instance.</span></span> <span data-ttu-id="a79b2-127">その後は、<xref:System.Windows.Data.BindingGroup.Items%2A> プロパティを使用してデータ オブジェクトにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a79b2-127">You can then access the data object through the <xref:System.Windows.Data.BindingGroup.Items%2A> property.</span></span>  
  
     <span data-ttu-id="a79b2-128">次の例では、`Course` オブジェクトの `StartDate` プロパティ値が `EndDate` プロパティ値より前かどうかを検証するための、このプロセスを示します。</span><span class="sxs-lookup"><span data-stu-id="a79b2-128">The following example demonstrates this process to validate whether the `StartDate` property value for a `Course` object is earlier than its `EndDate` property value.</span></span>  
  
     [!code-csharp[DataGrid_Validation#CourseValidationRule](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#coursevalidationrule)]
     [!code-vb[DataGrid_Validation#CourseValidationRule](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#coursevalidationrule)]  
  
2. <span data-ttu-id="a79b2-129"><xref:System.Windows.Controls.DataGrid.RowValidationRules%2A?displayProperty=nameWithType> コレクションに検証規則を追加します。</span><span class="sxs-lookup"><span data-stu-id="a79b2-129">Add the validation rule to the <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A?displayProperty=nameWithType> collection.</span></span> <span data-ttu-id="a79b2-130"><xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> プロパティを使うと、コントロールによって使用されるすべてのバインドをグループ化する <xref:System.Windows.Data.BindingGroup> インスタンスの <xref:System.Windows.Data.BindingGroup.ValidationRules%2A> プロパティに直接アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a79b2-130">The <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> property provides direct access to the <xref:System.Windows.Data.BindingGroup.ValidationRules%2A> property of a <xref:System.Windows.Data.BindingGroup> instance that groups all the bindings used by the control.</span></span>  
  
     <span data-ttu-id="a79b2-131">次の例では、XAML で <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> プロパティを設定しています。</span><span class="sxs-lookup"><span data-stu-id="a79b2-131">The following example sets the <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> property in XAML.</span></span> <span data-ttu-id="a79b2-132">バインドされたデータ オブジェクトが更新された後でのみ検証が行われるように、<xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> プロパティは <xref:System.Windows.Controls.ValidationStep.UpdatedValue> に設定されています。</span><span class="sxs-lookup"><span data-stu-id="a79b2-132">The <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> property is set to <xref:System.Windows.Controls.ValidationStep.UpdatedValue> so that the validation occurs only after the bound data object is updated.</span></span>  
  
     [!code-xaml[DataGrid_Validation#RowValidationRulesXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationrulesxaml)]  
  
     <span data-ttu-id="a79b2-133">ユーザーが開始日より前の終了日を指定すると、行ヘッダーに赤い感嘆符 (!) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a79b2-133">When a user specifies an end date that is earlier than the start date, a red exclamation mark (!) appears in the row header.</span></span> <span data-ttu-id="a79b2-134">次の手順で説明するようにして、この既定の検証フィードバックを変更できます。</span><span class="sxs-lookup"><span data-stu-id="a79b2-134">You can change this default validation feedback as described in the following procedure.</span></span>  
  
### <a name="to-customize-row-validation-feedback"></a><span data-ttu-id="a79b2-135">行の検証のフィードバックをカスタマイズするには</span><span class="sxs-lookup"><span data-stu-id="a79b2-135">To customize row validation feedback</span></span>  
  
- <span data-ttu-id="a79b2-136"><xref:System.Windows.Controls.DataGrid.RowValidationErrorTemplate%2A?displayProperty=nameWithType> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="a79b2-136">Set the <xref:System.Windows.Controls.DataGrid.RowValidationErrorTemplate%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="a79b2-137">このプロパティを使うと、個々の <xref:System.Windows.Controls.DataGrid> コントロールに対する行の検証フィードバックをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="a79b2-137">This property enables you to customize row validation feedback for individual <xref:System.Windows.Controls.DataGrid> controls.</span></span> <span data-ttu-id="a79b2-138">また、暗黙的な行スタイルを使用して <xref:System.Windows.Controls.DataGridRow.ValidationErrorTemplate%2A?displayProperty=nameWithType> プロパティを設定することにより、複数のコントロールに影響を与えることもできます。</span><span class="sxs-lookup"><span data-stu-id="a79b2-138">You can also affect multiple controls by using an implicit row style to set the <xref:System.Windows.Controls.DataGridRow.ValidationErrorTemplate%2A?displayProperty=nameWithType> property.</span></span>  
  
     <span data-ttu-id="a79b2-139">次の例では、行の検証に関する既定のフィードバックを、よりわかりやすいインジケーターに置き換えています。</span><span class="sxs-lookup"><span data-stu-id="a79b2-139">The following example replaces the default row validation feedback with a more visible indicator.</span></span> <span data-ttu-id="a79b2-140">ユーザーが無効な値を入力すると、白い感嘆符が含まれる赤い円が、行ヘッダーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a79b2-140">When a user enters an invalid value, a red circle with a white exclamation mark appears in the row header.</span></span> <span data-ttu-id="a79b2-141">これは、行とセルの両方の検証エラーに対して発生します。</span><span class="sxs-lookup"><span data-stu-id="a79b2-141">This occurs for both row and cell validation errors.</span></span> <span data-ttu-id="a79b2-142">ツールヒントには関連するエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a79b2-142">The associated error message is displayed in a ToolTip.</span></span>  
  
     [!code-xaml[DataGrid_Validation#RowValidationFeedbackXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationfeedbackxaml)]  
  
## <a name="example"></a><span data-ttu-id="a79b2-143">例</span><span class="sxs-lookup"><span data-stu-id="a79b2-143">Example</span></span>  
 <span data-ttu-id="a79b2-144">次の例では、セルと行の検証の完全なデモを示します。</span><span class="sxs-lookup"><span data-stu-id="a79b2-144">The following example provides a complete demonstration for cell and row validation.</span></span> <span data-ttu-id="a79b2-145">`Course` クラスでは、トランザクションをサポートするための <xref:System.ComponentModel.IEditableObject> を実装するサンプル データ オブジェクトが提供されます。</span><span class="sxs-lookup"><span data-stu-id="a79b2-145">The `Course` class provides a sample data object that implements <xref:System.ComponentModel.IEditableObject> to support transactions.</span></span> <span data-ttu-id="a79b2-146">ユーザーが Esc キーを押して変更を元に戻すことができるように、<xref:System.Windows.Controls.DataGrid> コントロールと <xref:System.ComponentModel.IEditableObject> の間でやり取りが行われます。</span><span class="sxs-lookup"><span data-stu-id="a79b2-146">The <xref:System.Windows.Controls.DataGrid> control interacts with <xref:System.ComponentModel.IEditableObject> to enable users to revert changes by pressing ESC.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a79b2-147">Visual Basic を使用する場合は、MainWindow.xaml の最初の行の `x:Class="DataGridValidation.MainWindow"` を `x:Class="MainWindow"` に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="a79b2-147">If you are using Visual Basic, in the first line of MainWindow.xaml, replace `x:Class="DataGridValidation.MainWindow"` with `x:Class="MainWindow"`.</span></span>  
  
 <span data-ttu-id="a79b2-148">検証をテストするには、次のようにしてみます。</span><span class="sxs-lookup"><span data-stu-id="a79b2-148">To test the validation, try the following:</span></span>  
  
- <span data-ttu-id="a79b2-149">[Course ID] 列に、整数以外の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="a79b2-149">In the Course ID column, enter a non-integer value.</span></span>  
  
- <span data-ttu-id="a79b2-150">[End Date] 列に、[Start Date] より前の日付を入力します。</span><span class="sxs-lookup"><span data-stu-id="a79b2-150">In the End Date column, enter a date that is earlier than the Start Date.</span></span>  
  
- <span data-ttu-id="a79b2-151">[Course ID]、[Start Date]、または [End Date] の値を削除します。</span><span class="sxs-lookup"><span data-stu-id="a79b2-151">Delete the value in Course ID, Start Date, or End Date.</span></span>  
  
- <span data-ttu-id="a79b2-152">無効なセルの値を元に戻すには、セルにカーソルを戻し、Esc キーを押します。</span><span class="sxs-lookup"><span data-stu-id="a79b2-152">To undo an invalid cell value, put the cursor back in the cell and press the ESC key.</span></span>  
  
- <span data-ttu-id="a79b2-153">現在のセルが編集モードのときに行全体の変更を元に戻すには、Esc キーを 2 回押します。</span><span class="sxs-lookup"><span data-stu-id="a79b2-153">To undo changes for an entire row when the current cell is in edit mode, press the ESC key twice.</span></span>  
  
- <span data-ttu-id="a79b2-154">検証エラーが発生したら、行ヘッダーのインジケーターをマウスでポイントし、関連付けられているエラー メッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="a79b2-154">When a validation error occurs, move your mouse pointer over the indicator in the row header to see the associated error message.</span></span>  
  
 [!code-csharp[DataGrid_Validation#FullCode](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#fullcode)]
 [!code-vb[DataGrid_Validation#FullCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#fullcode)]  
  
 [!code-xaml[DataGrid_Validation#FullXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#fullxaml)]  
  
## <a name="see-also"></a><span data-ttu-id="a79b2-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="a79b2-155">See also</span></span>

- <xref:System.Windows.Controls.DataGrid>
- [<span data-ttu-id="a79b2-156">DataGrid</span><span class="sxs-lookup"><span data-stu-id="a79b2-156">DataGrid</span></span>](datagrid.md)
- [<span data-ttu-id="a79b2-157">データ バインディング</span><span class="sxs-lookup"><span data-stu-id="a79b2-157">Data Binding</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
- [<span data-ttu-id="a79b2-158">バインディングの検証の実装</span><span class="sxs-lookup"><span data-stu-id="a79b2-158">Implement Binding Validation</span></span>](../data/how-to-implement-binding-validation.md)
- [<span data-ttu-id="a79b2-159">カスタム オブジェクトに検証ロジックを実装する</span><span class="sxs-lookup"><span data-stu-id="a79b2-159">Implement Validation Logic on Custom Objects</span></span>](../data/how-to-implement-validation-logic-on-custom-objects.md)
