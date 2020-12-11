---
title: バインドしていない DataGridView コントロールを作成する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [Windows Forms], displaying without binding to data source
- DataGridView control [Windows Forms], unbound data
- DataGridView control [Windows Forms], displaying data without binding to a data source
- data [Windows Forms], unbound
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 5a8d6afa-1b4b-4b24-8db8-501086ffdebe
ms.openlocfilehash: ceb75d4ee845d1f643d4d88d5a9f1bde73edcc70
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984132"
---
# <a name="walkthrough-creating-an-unbound-windows-forms-datagridview-control"></a><span data-ttu-id="45441-102">チュートリアル: バインドされていない Windows フォーム DataGridView コントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="45441-102">Walkthrough: Creating an Unbound Windows Forms DataGridView Control</span></span>
<span data-ttu-id="45441-103">データベースから生成されていない表形式のデータを表示することがよくあります。</span><span class="sxs-lookup"><span data-stu-id="45441-103">You may frequently want to display tabular data that does not originate from a database.</span></span> <span data-ttu-id="45441-104">たとえば、文字列の2次元配列の内容を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="45441-104">For example, you may want to show the contents of a two-dimensional array of strings.</span></span> <span data-ttu-id="45441-105">クラスは、 <xref:System.Windows.Forms.DataGridView> データソースにバインドせずにデータを表示するための、簡単でカスタマイズ可能な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="45441-105">The <xref:System.Windows.Forms.DataGridView> class provides an easy and highly customizable way to display data without binding to a data source.</span></span> <span data-ttu-id="45441-106">このチュートリアルでは、 <xref:System.Windows.Forms.DataGridView> "非バインド" モードでコントロールを設定し、行の追加と削除を管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="45441-106">This walkthrough shows how to populate a <xref:System.Windows.Forms.DataGridView> control and manage the addition and deletion of rows in "unbound" mode.</span></span> <span data-ttu-id="45441-107">既定では、ユーザーは新しい行を追加できます。</span><span class="sxs-lookup"><span data-stu-id="45441-107">By default, the user can add new rows.</span></span> <span data-ttu-id="45441-108">行が追加されないようにするには、プロパティをに設定し <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> `false` ます。</span><span class="sxs-lookup"><span data-stu-id="45441-108">To prevent row addition, set the <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> property is `false`.</span></span>  
  
 <span data-ttu-id="45441-109">このトピックのコードを単一のリストとしてコピーする方法については、「方法: バインドされていない [Windows フォーム DataGridView コントロールを作成](how-to-create-an-unbound-windows-forms-datagridview-control.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45441-109">To copy the code in this topic as a single listing, see [How to: Create an Unbound Windows Forms DataGridView Control](how-to-create-an-unbound-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="creating-the-form"></a><span data-ttu-id="45441-110">フォームの作成</span><span class="sxs-lookup"><span data-stu-id="45441-110">Creating the Form</span></span>  
  
#### <a name="to-use-an-unbound-datagridview-control"></a><span data-ttu-id="45441-111">バインドされていない DataGridView コントロールを使用するには</span><span class="sxs-lookup"><span data-stu-id="45441-111">To use an unbound DataGridView control</span></span>  
  
1. <span data-ttu-id="45441-112">から派生するクラスを作成 <xref:System.Windows.Forms.Form> し、次の変数宣言と `Main` メソッドを含みます。</span><span class="sxs-lookup"><span data-stu-id="45441-112">Create a class that derives from <xref:System.Windows.Forms.Form> and contains the following variable declarations and `Main` method.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#02)]  
  
2. <span data-ttu-id="45441-113">フォームの `SetupLayout` レイアウトを設定するために、フォームのクラス定義にメソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="45441-113">Implement a `SetupLayout` method in your form's class definition to set up the form's layout.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#20)]  
  
3. <span data-ttu-id="45441-114">`SetupDataGridView`列およびプロパティを設定するメソッドを作成し <xref:System.Windows.Forms.DataGridView> ます。</span><span class="sxs-lookup"><span data-stu-id="45441-114">Create a `SetupDataGridView` method to set up the <xref:System.Windows.Forms.DataGridView> columns and properties.</span></span>  
  
     <span data-ttu-id="45441-115">このメソッドは、最初 <xref:System.Windows.Forms.DataGridView> にコントロールをフォームのコレクションに追加し <xref:System.Windows.Forms.Control.Controls%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="45441-115">This method first adds the <xref:System.Windows.Forms.DataGridView> control to the form's <xref:System.Windows.Forms.Control.Controls%2A> collection.</span></span> <span data-ttu-id="45441-116">次に、プロパティを使用して、表示する列の数を設定し <xref:System.Windows.Forms.DataGridView.ColumnCount%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="45441-116">Next, the number of columns to be displayed is set using the <xref:System.Windows.Forms.DataGridView.ColumnCount%2A> property.</span></span> <span data-ttu-id="45441-117">列ヘッダーの既定のスタイルは、 <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A> <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> <xref:System.Windows.Forms.DataGridViewCellStyle> プロパティによって返されるの、、およびの各プロパティを設定することによって設定され <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="45441-117">The default style for the column headers is set by setting the <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A>, <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>, and <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> properties of the <xref:System.Windows.Forms.DataGridViewCellStyle> returned by the <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> property.</span></span>  
  
     <span data-ttu-id="45441-118">レイアウトと外観のプロパティが設定され、列名が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="45441-118">Layout and appearance properties are set, and then the column names are assigned.</span></span> <span data-ttu-id="45441-119">このメソッドが終了すると、 <xref:System.Windows.Forms.DataGridView> コントロールの設定が可能になります。</span><span class="sxs-lookup"><span data-stu-id="45441-119">When this method exits, the <xref:System.Windows.Forms.DataGridView> control is ready to be populated.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#30)]  
  
4. <span data-ttu-id="45441-120">`PopulateDataGridView`コントロールに行を追加するメソッドを作成 <xref:System.Windows.Forms.DataGridView> します。</span><span class="sxs-lookup"><span data-stu-id="45441-120">Create a `PopulateDataGridView` method to add rows to the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
     <span data-ttu-id="45441-121">各行は、曲とそれに関連付けられた情報を表します。</span><span class="sxs-lookup"><span data-stu-id="45441-121">Each row represents a song and its associated information.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#40)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#40)]  
  
5. <span data-ttu-id="45441-122">ユーティリティメソッドを配置すると、イベントハンドラーをアタッチできます。</span><span class="sxs-lookup"><span data-stu-id="45441-122">With the utility methods in place, you can attach event handlers.</span></span>  
  
     <span data-ttu-id="45441-123">[ **追加** ] ボタンと [ **削除** ] ボタンのイベント、 <xref:System.Windows.Forms.Control.Click> フォームの <xref:System.Windows.Forms.Form.Load> イベント、およびコントロールのイベントを処理し <xref:System.Windows.Forms.DataGridView> <xref:System.Windows.Forms.DataGridView.CellFormatting> ます。</span><span class="sxs-lookup"><span data-stu-id="45441-123">You will handle the **Add** and **Delete** buttons' <xref:System.Windows.Forms.Control.Click> events, the form's <xref:System.Windows.Forms.Form.Load> event, and the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CellFormatting> event.</span></span>  
  
     <span data-ttu-id="45441-124">[ **追加** ] ボタンの <xref:System.Windows.Forms.Control.Click> イベントが発生すると、に新しい空の行が追加され <xref:System.Windows.Forms.DataGridView> ます。</span><span class="sxs-lookup"><span data-stu-id="45441-124">When the **Add** button's <xref:System.Windows.Forms.Control.Click> event is raised, a new, empty row is added to the <xref:System.Windows.Forms.DataGridView>.</span></span>  
  
     <span data-ttu-id="45441-125">[ **削除** ] ボタンのイベントが発生すると、選択した行が削除されます <xref:System.Windows.Forms.Control.Click> 。ただし、新しいレコードの行でない限り、ユーザーは新しい行を追加できます。</span><span class="sxs-lookup"><span data-stu-id="45441-125">When the **Delete** button's <xref:System.Windows.Forms.Control.Click> event is raised, the selected row is deleted, unless it is the row for new records, which enables the user add new rows.</span></span> <span data-ttu-id="45441-126">この行は、常にコントロールの最後の行です <xref:System.Windows.Forms.DataGridView> 。</span><span class="sxs-lookup"><span data-stu-id="45441-126">This row is always the last row in the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
     <span data-ttu-id="45441-127">フォームの <xref:System.Windows.Forms.Form.Load> イベントが発生すると、 `SetupLayout` 、、およびの各 `SetupDataGridView` `PopulateDataGridView` ユーティリティメソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="45441-127">When the form's <xref:System.Windows.Forms.Form.Load> event is raised, the `SetupLayout`, `SetupDataGridView`, and `PopulateDataGridView` utility methods are called.</span></span>  
  
     <span data-ttu-id="45441-128"><xref:System.Windows.Forms.DataGridView.CellFormatting>イベントが発生すると、 `Date` セルの値を解析できない場合を除き、列の各セルは長い日付として書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="45441-128">When the <xref:System.Windows.Forms.DataGridView.CellFormatting> event is raised, each cell in the `Date` column is formatted as a long date, unless the cell's value cannot be parsed.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#10)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="45441-129">アプリケーションのテスト</span><span class="sxs-lookup"><span data-stu-id="45441-129">Testing the Application</span></span>  
 <span data-ttu-id="45441-130">フォームをテストして、期待どおりに動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="45441-130">You can now test the form to make sure it behaves as expected.</span></span>  
  
#### <a name="to-test-the-form"></a><span data-ttu-id="45441-131">フォームをテストするには</span><span class="sxs-lookup"><span data-stu-id="45441-131">To test the form</span></span>  
  
- <span data-ttu-id="45441-132">F5 キーを押してアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="45441-132">Press F5 to run the application.</span></span>  
  
     <span data-ttu-id="45441-133">に示されている <xref:System.Windows.Forms.DataGridView> 曲を表示するコントロールが表示され `PopulateDataGridView` ます。</span><span class="sxs-lookup"><span data-stu-id="45441-133">You will see a <xref:System.Windows.Forms.DataGridView> control that displays the songs listed in `PopulateDataGridView`.</span></span> <span data-ttu-id="45441-134">[ **行の追加** ] ボタンを使用して新しい行を追加できます。また、[ **行の削除** ] ボタンを使用して、選択した行を削除できます。</span><span class="sxs-lookup"><span data-stu-id="45441-134">You can add new rows with the **Add Row** button, and you can delete selected rows with the **Delete Row** button.</span></span> <span data-ttu-id="45441-135">バインドされてい <xref:System.Windows.Forms.DataGridView> ないコントロールはデータストアであり、そのデータは、や配列などの外部ソースからは独立してい <xref:System.Data.DataSet> ます。</span><span class="sxs-lookup"><span data-stu-id="45441-135">The unbound <xref:System.Windows.Forms.DataGridView> control is the data store, and its data is independent of any external source, such as a <xref:System.Data.DataSet> or an array.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="45441-136">次の手順</span><span class="sxs-lookup"><span data-stu-id="45441-136">Next Steps</span></span>  
 <span data-ttu-id="45441-137">このアプリケーションを使用すると、コントロールの機能についての基本的な理解を得ることができ <xref:System.Windows.Forms.DataGridView> ます。</span><span class="sxs-lookup"><span data-stu-id="45441-137">This application gives you a basic understanding of the <xref:System.Windows.Forms.DataGridView> control's capabilities.</span></span> <span data-ttu-id="45441-138">コントロールの外観と動作は、 <xref:System.Windows.Forms.DataGridView> 次のいくつかの方法でカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="45441-138">You can customize the appearance and behavior of the <xref:System.Windows.Forms.DataGridView> control in several ways:</span></span>  
  
- <span data-ttu-id="45441-139">罫線とヘッダーのスタイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="45441-139">Change border and header styles.</span></span> <span data-ttu-id="45441-140">詳細については、「 [方法: Windows フォーム DataGridView コントロールの境界線とグリッド線のスタイルを変更する](change-the-border-and-gridline-styles-in-the-datagrid.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45441-140">For more information, see [How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control](change-the-border-and-gridline-styles-in-the-datagrid.md).</span></span>  
  
- <span data-ttu-id="45441-141">コントロールへのユーザー入力を有効または制限 <xref:System.Windows.Forms.DataGridView> します。</span><span class="sxs-lookup"><span data-stu-id="45441-141">Enable or restrict user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="45441-142">詳細については、「 [方法: Windows フォーム Datagridview コントロールで行の追加と削除を回避](prevent-row-addition-and-deletion-datagridview.md)する」および「 [方法: Windows フォーム Datagridview コントロールで列を Read-Only する](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45441-142">For more information, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md), and [How to: Make Columns Read-Only in the Windows Forms DataGridView Control](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).</span></span>  
  
- <span data-ttu-id="45441-143">データベース関連のエラーについては、ユーザー入力を確認してください。</span><span class="sxs-lookup"><span data-stu-id="45441-143">Check user input for database-related errors.</span></span> <span data-ttu-id="45441-144">詳細については、「 [チュートリアル: Windows フォーム DataGridView コントロールでのデータ入力中に発生したエラーの処理](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45441-144">For more information, see [Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control](handling-errors-that-occur-during-data-entry-in-the-datagrid.md).</span></span>  
  
- <span data-ttu-id="45441-145">仮想モードを使用して非常に大きなデータセットを処理します。</span><span class="sxs-lookup"><span data-stu-id="45441-145">Handle very large data sets using virtual mode.</span></span> <span data-ttu-id="45441-146">詳細については、「 [チュートリアル: Windows フォーム DataGridView コントロールでの仮想モードの実装](implementing-virtual-mode-wf-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45441-146">For more information, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](implementing-virtual-mode-wf-datagridview-control.md).</span></span>  
  
- <span data-ttu-id="45441-147">セルの外観をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="45441-147">Customize the appearance of cells.</span></span> <span data-ttu-id="45441-148">詳細については、「 [方法: Windows フォーム Datagridview コントロールのセルの外観をカスタマイズ](customize-the-appearance-of-cells-in-the-datagrid.md) する」および「 [方法: Windows フォーム Datagridview コントロールの既定のセルスタイルを設定する](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45441-148">For more information, see [How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control](customize-the-appearance-of-cells-in-the-datagrid.md) and [How to: Set Default Cell Styles for the Windows Forms DataGridView Control](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45441-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="45441-149">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="45441-150">Windows フォーム DataGridView コントロールでのデータの表示</span><span class="sxs-lookup"><span data-stu-id="45441-150">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="45441-151">方法: 連結されていない Windows フォーム DataGridView コントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="45441-151">How to: Create an Unbound Windows Forms DataGridView Control</span></span>](how-to-create-an-unbound-windows-forms-datagridview-control.md)
- [<span data-ttu-id="45441-152">Windows フォーム DataGridView コントロールでのデータ表示モード</span><span class="sxs-lookup"><span data-stu-id="45441-152">Data Display Modes in the Windows Forms DataGridView Control</span></span>](data-display-modes-in-the-windows-forms-datagridview-control.md)
