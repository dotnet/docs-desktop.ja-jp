---
title: 'チュートリアル: DataGridView コントロールでのデータの検証'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- validating data [Windows Forms], Windows Forms
- data [Windows Forms], validation
- DataGridView control [Windows Forms], data validation
- data grids [Windows Forms], validating data
- data validation [Windows Forms], Windows Forms
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: a4f1d015-2969-430c-8ea2-b612d179c290
ms.openlocfilehash: 822a09565e81d308179dd0b51993a758738922bb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982692"
---
# <a name="walkthrough-validating-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="29585-102">チュートリアル: Windows フォーム DataGridView コントロールのデータの妥当性検査</span><span class="sxs-lookup"><span data-stu-id="29585-102">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>

<span data-ttu-id="29585-103">データ入力機能をユーザーに表示する場合は、フォームに入力されたデータを頻繁に検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29585-103">When you display data entry functionality to users, you frequently have to validate the data entered into your form.</span></span> <span data-ttu-id="29585-104">クラスは、データ <xref:System.Windows.Forms.DataGridView> がデータストアにコミットされる前に検証を実行する便利な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="29585-104">The <xref:System.Windows.Forms.DataGridView> class provides a convenient way to perform validation before data is committed to the data store.</span></span> <span data-ttu-id="29585-105"><xref:System.Windows.Forms.DataGridView.CellValidating>現在のセルが変更されたときにによって発生するイベントを処理することで、データを検証でき <xref:System.Windows.Forms.DataGridView> ます。</span><span class="sxs-lookup"><span data-stu-id="29585-105">You can validate data by handling the <xref:System.Windows.Forms.DataGridView.CellValidating> event, which is raised by the <xref:System.Windows.Forms.DataGridView> when the current cell changes.</span></span>

<span data-ttu-id="29585-106">このチュートリアルでは、Northwind サンプルデータベースのテーブルから行を取得 `Customers` し、コントロールに表示し <xref:System.Windows.Forms.DataGridView> ます。</span><span class="sxs-lookup"><span data-stu-id="29585-106">In this walkthrough, you will retrieve rows from the `Customers` table in the Northwind sample database and display them in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="29585-107">ユーザーが列のセルを編集し、セルから離れようとすると `CompanyName` 、 <xref:System.Windows.Forms.DataGridView.CellValidating> イベントハンドラーは新しい会社名の文字列を調べて空でないことを確認します。新しい値が空の文字列の場合、は、 <xref:System.Windows.Forms.DataGridView> 空でない文字列が入力されるまで、ユーザーのカーソルがセルから離れるのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="29585-107">When a user edits a cell in the `CompanyName` column and tries to leave the cell, the <xref:System.Windows.Forms.DataGridView.CellValidating> event handler will examine new company name string to make sure it is not empty; if the new value is an empty string, the <xref:System.Windows.Forms.DataGridView> will prevent the user's cursor from leaving the cell until a non-empty string is entered.</span></span>

<span data-ttu-id="29585-108">このトピックのコードを単一のリストとしてコピーする方法については、「 [方法: Windows フォーム DataGridView コントロールでデータを検証](how-to-validate-data-in-the-windows-forms-datagridview-control.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29585-108">To copy the code in this topic as a single listing, see [How to: Validate Data in the Windows Forms DataGridView Control](how-to-validate-data-in-the-windows-forms-datagridview-control.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="29585-109">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="29585-109">Prerequisites</span></span>

<span data-ttu-id="29585-110">このチュートリアルを完了するための要件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="29585-110">In order to complete this walkthrough, you will need:</span></span>

- <span data-ttu-id="29585-111">Northwind SQL Server サンプルデータベースを持つサーバーへのアクセス。</span><span class="sxs-lookup"><span data-stu-id="29585-111">Access to a server that has the Northwind SQL Server sample database.</span></span>

## <a name="creating-the-form"></a><span data-ttu-id="29585-112">フォームの作成</span><span class="sxs-lookup"><span data-stu-id="29585-112">Creating the Form</span></span>

#### <a name="to-validate-data-entered-in-a-datagridview"></a><span data-ttu-id="29585-113">DataGridView に入力されたデータを検証するには</span><span class="sxs-lookup"><span data-stu-id="29585-113">To validate data entered in a DataGridView</span></span>

1. <span data-ttu-id="29585-114">から派生するクラスを作成 <xref:System.Windows.Forms.Form> し、 <xref:System.Windows.Forms.DataGridView> コントロールとコンポーネントを格納し <xref:System.Windows.Forms.BindingSource> ます。</span><span class="sxs-lookup"><span data-stu-id="29585-114">Create a class that derives from <xref:System.Windows.Forms.Form> and contains a <xref:System.Windows.Forms.DataGridView> control and a <xref:System.Windows.Forms.BindingSource> component.</span></span>

    <span data-ttu-id="29585-115">次のコード例では、基本的な初期化を行い、メソッドを含めてい `Main` ます。</span><span class="sxs-lookup"><span data-stu-id="29585-115">The following code example provides basic initialization and includes a `Main` method.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#02)]

2. <span data-ttu-id="29585-116">データベースへの接続の詳細を処理するために、フォームのクラス定義にメソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="29585-116">Implement a method in your form's class definition for handling the details of connecting to the database.</span></span>

    <span data-ttu-id="29585-117">このコード例では、 `GetData` 設定されたオブジェクトを返すメソッドを使用 <xref:System.Data.DataTable> します。</span><span class="sxs-lookup"><span data-stu-id="29585-117">This code example uses a `GetData` method that returns a populated <xref:System.Data.DataTable> object.</span></span> <span data-ttu-id="29585-118">`connectionString`変数には、データベースに適した値を設定してください。</span><span class="sxs-lookup"><span data-stu-id="29585-118">Be sure that you set the `connectionString` variable to a value that is appropriate for your database.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="29585-119">接続文字列内に機密情報 (パスワードなど) を格納すると、アプリケーションのセキュリティに影響を及ぼすことがあります。</span><span class="sxs-lookup"><span data-stu-id="29585-119">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="29585-120">Windows 認証 (統合セキュリティとも呼ばれます) を使用すると、データベースへのアクセスをより安全に制御することができます。</span><span class="sxs-lookup"><span data-stu-id="29585-120">Using Windows Authentication, also known as integrated security, is a more secure way to control access to a database.</span></span> <span data-ttu-id="29585-121">詳細については、「[接続情報の保護](/dotnet/framework/data/adonet/protecting-connection-information)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29585-121">For more information, see [Protecting Connection Information](/dotnet/framework/data/adonet/protecting-connection-information).</span></span>

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#30)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#30)]

3. <span data-ttu-id="29585-122">とを初期化し、データバインディングを設定するフォームのイベントのハンドラーを実装し <xref:System.Windows.Forms.Form.Load> <xref:System.Windows.Forms.DataGridView> <xref:System.Windows.Forms.BindingSource> ます。</span><span class="sxs-lookup"><span data-stu-id="29585-122">Implement a handler for your form's <xref:System.Windows.Forms.Form.Load> event that initializes the <xref:System.Windows.Forms.DataGridView> and <xref:System.Windows.Forms.BindingSource> and sets up the data binding.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#10)]

4. <span data-ttu-id="29585-123"><xref:System.Windows.Forms.DataGridView>コントロールのイベントとイベントのハンドラーを実装 <xref:System.Windows.Forms.DataGridView.CellValidating> <xref:System.Windows.Forms.DataGridView.CellEndEdit> します。</span><span class="sxs-lookup"><span data-stu-id="29585-123">Implement handlers for the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CellValidating> and <xref:System.Windows.Forms.DataGridView.CellEndEdit> events.</span></span>

    <span data-ttu-id="29585-124"><xref:System.Windows.Forms.DataGridView.CellValidating>イベントハンドラーでは、列のセルの値が空かどうかを判断し `CompanyName` ます。</span><span class="sxs-lookup"><span data-stu-id="29585-124">The <xref:System.Windows.Forms.DataGridView.CellValidating> event handler is where you determine whether the value of a cell in the `CompanyName` column is empty.</span></span> <span data-ttu-id="29585-125">セル値が検証に失敗した場合は、 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> クラスのプロパティを <xref:System.Windows.Forms.DataGridViewCellValidatingEventArgs?displayProperty=nameWithType> に設定 `true` します。</span><span class="sxs-lookup"><span data-stu-id="29585-125">If the cell value fails validation, set the <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> property of the <xref:System.Windows.Forms.DataGridViewCellValidatingEventArgs?displayProperty=nameWithType> class to `true`.</span></span> <span data-ttu-id="29585-126">これにより、コントロールによって、 <xref:System.Windows.Forms.DataGridView> カーソルがセルから離れるのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="29585-126">This causes the <xref:System.Windows.Forms.DataGridView> control to prevent the cursor from leaving the cell.</span></span> <span data-ttu-id="29585-127">行の <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> プロパティを説明の文字列に設定します。</span><span class="sxs-lookup"><span data-stu-id="29585-127">Set the <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> property on the row to an explanatory string.</span></span> <span data-ttu-id="29585-128">エラーアイコンと、エラーテキストを含むツールヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="29585-128">This displays an error icon with a ToolTip that contains the error text.</span></span> <span data-ttu-id="29585-129"><xref:System.Windows.Forms.DataGridView.CellEndEdit>イベントハンドラーで、 <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> 行のプロパティを空の文字列に設定します。</span><span class="sxs-lookup"><span data-stu-id="29585-129">In the <xref:System.Windows.Forms.DataGridView.CellEndEdit> event handler, set the <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> property on the row to the empty string.</span></span> <span data-ttu-id="29585-130">イベントは、 <xref:System.Windows.Forms.DataGridView.CellEndEdit> セルが編集モードを終了したときにのみ発生します。これは、検証に失敗した場合には実行できません。</span><span class="sxs-lookup"><span data-stu-id="29585-130">The <xref:System.Windows.Forms.DataGridView.CellEndEdit> event occurs only when the cell exits edit mode, which it cannot do if it fails validation.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#20)]

## <a name="testing-the-application"></a><span data-ttu-id="29585-131">アプリケーションのテスト</span><span class="sxs-lookup"><span data-stu-id="29585-131">Testing the Application</span></span>

<span data-ttu-id="29585-132">フォームをテストして、期待どおりに動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="29585-132">You can now test the form to make sure it behaves as expected.</span></span>

#### <a name="to-test-the-form"></a><span data-ttu-id="29585-133">フォームをテストするには</span><span class="sxs-lookup"><span data-stu-id="29585-133">To test the form</span></span>

- <span data-ttu-id="29585-134">アプリケーションをコンパイルして実行します。</span><span class="sxs-lookup"><span data-stu-id="29585-134">Compile and run the application.</span></span>

  <span data-ttu-id="29585-135">テーブルのデータがいっぱいになっていることがわかり <xref:System.Windows.Forms.DataGridView> `Customers` ます。</span><span class="sxs-lookup"><span data-stu-id="29585-135">You will see a <xref:System.Windows.Forms.DataGridView> filled with data from the `Customers` table.</span></span> <span data-ttu-id="29585-136">列のセルをダブルクリックすると、 `CompanyName` 値を編集できます。</span><span class="sxs-lookup"><span data-stu-id="29585-136">When you double-click a cell in the `CompanyName` column, you can edit the value.</span></span> <span data-ttu-id="29585-137">すべての文字を削除し、TAB キーを押してセルを終了すると、で <xref:System.Windows.Forms.DataGridView> 終了できなくなります。</span><span class="sxs-lookup"><span data-stu-id="29585-137">If you delete all the characters and hit the TAB key to exit the cell, the <xref:System.Windows.Forms.DataGridView> prevents you from exiting.</span></span> <span data-ttu-id="29585-138">空でない文字列をセルに入力すると、コントロールによって <xref:System.Windows.Forms.DataGridView> セルを終了できます。</span><span class="sxs-lookup"><span data-stu-id="29585-138">When you type a non-empty string into the cell, the <xref:System.Windows.Forms.DataGridView> control lets you exit the cell.</span></span>

## <a name="next-steps"></a><span data-ttu-id="29585-139">次の手順</span><span class="sxs-lookup"><span data-stu-id="29585-139">Next Steps</span></span>

<span data-ttu-id="29585-140">このアプリケーションを使用すると、コントロールの機能についての基本的な理解を得ることができ <xref:System.Windows.Forms.DataGridView> ます。</span><span class="sxs-lookup"><span data-stu-id="29585-140">This application gives you a basic understanding of the <xref:System.Windows.Forms.DataGridView> control's capabilities.</span></span> <span data-ttu-id="29585-141">コントロールの外観と動作は、 <xref:System.Windows.Forms.DataGridView> 次のいくつかの方法でカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="29585-141">You can customize the appearance and behavior of the <xref:System.Windows.Forms.DataGridView> control in several ways:</span></span>

- <span data-ttu-id="29585-142">罫線とヘッダーのスタイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="29585-142">Change border and header styles.</span></span> <span data-ttu-id="29585-143">詳細については、「 [方法: Windows フォーム DataGridView コントロールの境界線とグリッド線のスタイルを変更する](change-the-border-and-gridline-styles-in-the-datagrid.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29585-143">For more information, see [How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control](change-the-border-and-gridline-styles-in-the-datagrid.md).</span></span>

- <span data-ttu-id="29585-144">コントロールへのユーザー入力を有効または制限 <xref:System.Windows.Forms.DataGridView> します。</span><span class="sxs-lookup"><span data-stu-id="29585-144">Enable or restrict user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="29585-145">詳細については、「 [方法: Windows フォーム Datagridview コントロールで行の追加と削除を回避](prevent-row-addition-and-deletion-datagridview.md)する」および「 [方法: Windows フォーム Datagridview コントロールで列を Read-Only する](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29585-145">For more information, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md), and [How to: Make Columns Read-Only in the Windows Forms DataGridView Control](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).</span></span>

- <span data-ttu-id="29585-146">データベース関連のエラーについては、ユーザー入力を確認してください。</span><span class="sxs-lookup"><span data-stu-id="29585-146">Check user input for database-related errors.</span></span> <span data-ttu-id="29585-147">詳細については、「 [チュートリアル: Windows フォーム DataGridView コントロールでのデータ入力中に発生したエラーの処理](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29585-147">For more information, see [Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control](handling-errors-that-occur-during-data-entry-in-the-datagrid.md).</span></span>

- <span data-ttu-id="29585-148">仮想モードを使用して非常に大きなデータセットを処理します。</span><span class="sxs-lookup"><span data-stu-id="29585-148">Handle very large data sets using virtual mode.</span></span> <span data-ttu-id="29585-149">詳細については、「 [チュートリアル: Windows フォーム DataGridView コントロールでの仮想モードの実装](implementing-virtual-mode-wf-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29585-149">For more information, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](implementing-virtual-mode-wf-datagridview-control.md).</span></span>

- <span data-ttu-id="29585-150">セルの外観をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="29585-150">Customize the appearance of cells.</span></span> <span data-ttu-id="29585-151">詳細については、「 [方法: Windows フォーム Datagridview コントロールのセルの外観をカスタマイズ](customize-the-appearance-of-cells-in-the-datagrid.md) する」および「 [方法: Windows フォーム Datagridview コントロールのフォントと色のスタイルを設定する](how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29585-151">For more information, see [How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control](customize-the-appearance-of-cells-in-the-datagrid.md) and [How to: Set Font and Color Styles in the Windows Forms DataGridView Control](how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="29585-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="29585-152">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="29585-153">Windows フォーム DataGridView コントロールでのデータ入力</span><span class="sxs-lookup"><span data-stu-id="29585-153">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="29585-154">方法: Windows フォーム DataGridView コントロールのデータを検証する</span><span class="sxs-lookup"><span data-stu-id="29585-154">How to: Validate Data in the Windows Forms DataGridView Control</span></span>](how-to-validate-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="29585-155">チュートリアル: Windows フォーム DataGridView コントロールでのデータ入力中に発生したエラーの処理</span><span class="sxs-lookup"><span data-stu-id="29585-155">Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control</span></span>](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [<span data-ttu-id="29585-156">接続情報の保護</span><span class="sxs-lookup"><span data-stu-id="29585-156">Protecting Connection Information</span></span>](/dotnet/framework/data/adonet/protecting-connection-information)
