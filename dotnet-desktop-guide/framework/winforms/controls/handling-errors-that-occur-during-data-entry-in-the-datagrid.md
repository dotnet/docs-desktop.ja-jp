---
title: 'チュートリアル: DataGridView コントロールでのデータ入力中に発生したエラーの処理'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- error handling [Windows Forms], dataGridView control
- data grids [Windows Forms], error handling
- DataGridView control [Windows Forms], error handling
- data entry [Windows Forms], error handling
- error handling [Windows Forms], data entry
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 30a68b85-d3af-4946-83c1-1e2d010d0511
ms.openlocfilehash: d65dd038ddc276ec09a1db3af4f14fc87fec56f2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981487"
---
# <a name="walkthrough-handling-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="31b2d-102">チュートリアル: Windows フォーム DataGridView コントロールでのデータ入力中に発生したエラーの処理</span><span class="sxs-lookup"><span data-stu-id="31b2d-102">Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control</span></span>

<span data-ttu-id="31b2d-103">データ入力アプリケーションでは、基になるデータストアからのエラーを処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="31b2d-103">Handling errors from the underlying data store is a required feature for a data-entry application.</span></span> <span data-ttu-id="31b2d-104">Windows フォームコントロールは、 <xref:System.Windows.Forms.DataGridView> イベントを公開することによってこれを簡単にし <xref:System.Windows.Forms.DataGridView.DataError> ます。これは、データストアが制約違反または分割されたビジネスルールを検出したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="31b2d-104">The Windows Forms <xref:System.Windows.Forms.DataGridView> control makes this easy by exposing the <xref:System.Windows.Forms.DataGridView.DataError> event, which is raised when the data store detects a constraint violation or a broken business rule.</span></span>

<span data-ttu-id="31b2d-105">このチュートリアルでは、Northwind サンプルデータベースのテーブルから行を取得 `Customers` し、コントロールに表示し <xref:System.Windows.Forms.DataGridView> ます。</span><span class="sxs-lookup"><span data-stu-id="31b2d-105">In this walkthrough, you will retrieve rows from the `Customers` table in the Northwind sample database and display them in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="31b2d-106">`CustomerID`新しい行または編集済みの既存の行で重複する値が検出されると、 <xref:System.Windows.Forms.DataGridView.DataError> イベントが発生します。これは、例外を説明するを表示することによって処理され <xref:System.Windows.Forms.MessageBox> ます。</span><span class="sxs-lookup"><span data-stu-id="31b2d-106">When a duplicate `CustomerID` value is detected in a new row or an edited existing row, the <xref:System.Windows.Forms.DataGridView.DataError> event will occur, which will be handled by displaying a <xref:System.Windows.Forms.MessageBox> that describes the exception.</span></span>

<span data-ttu-id="31b2d-107">このトピックのコードを単一のリストとしてコピーする方法については、「 [方法: Windows フォーム DataGridView コントロールでのデータ入力中に発生したエラーを処理](handle-errors-that-occur-during-data-entry-in-the-datagrid.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31b2d-107">To copy the code in this topic as a single listing, see [How to: Handle Errors That Occur During Data Entry in the Windows Forms DataGridView Control](handle-errors-that-occur-during-data-entry-in-the-datagrid.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="31b2d-108">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="31b2d-108">Prerequisites</span></span>

<span data-ttu-id="31b2d-109">このチュートリアルを完了するための要件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="31b2d-109">In order to complete this walkthrough, you will need:</span></span>

- <span data-ttu-id="31b2d-110">Northwind SQL Server サンプルデータベースを持つサーバーへのアクセス。</span><span class="sxs-lookup"><span data-stu-id="31b2d-110">Access to a server that has the Northwind SQL Server sample database.</span></span>

## <a name="creating-the-form"></a><span data-ttu-id="31b2d-111">フォームの作成</span><span class="sxs-lookup"><span data-stu-id="31b2d-111">Creating the Form</span></span>

#### <a name="to-handle-data-entry-errors-in-the-datagridview-control"></a><span data-ttu-id="31b2d-112">DataGridView コントロールでのデータ入力エラーを処理するには</span><span class="sxs-lookup"><span data-stu-id="31b2d-112">To handle data-entry errors in the DataGridView control</span></span>

1. <span data-ttu-id="31b2d-113">から派生するクラスを作成 <xref:System.Windows.Forms.Form> し、 <xref:System.Windows.Forms.DataGridView> コントロールとコンポーネントを格納し <xref:System.Windows.Forms.BindingSource> ます。</span><span class="sxs-lookup"><span data-stu-id="31b2d-113">Create a class that derives from <xref:System.Windows.Forms.Form> and contains a <xref:System.Windows.Forms.DataGridView> control and a <xref:System.Windows.Forms.BindingSource> component.</span></span>

    <span data-ttu-id="31b2d-114">次のコード例では、基本的な初期化を行い、メソッドを含めてい `Main` ます。</span><span class="sxs-lookup"><span data-stu-id="31b2d-114">The following code example provides basic initialization and includes a `Main` method.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#02)]

2. <span data-ttu-id="31b2d-115">データベースへの接続の詳細を処理するために、フォームのクラス定義にメソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="31b2d-115">Implement a method in your form's class definition for handling the details of connecting to the database.</span></span>

    <span data-ttu-id="31b2d-116">このコード例では、 `GetData` 設定されたオブジェクトを返すメソッドを使用 <xref:System.Data.DataTable> します。</span><span class="sxs-lookup"><span data-stu-id="31b2d-116">This code example uses a `GetData` method that returns a populated <xref:System.Data.DataTable> object.</span></span> <span data-ttu-id="31b2d-117">`connectionString`変数には、データベースに適した値を設定してください。</span><span class="sxs-lookup"><span data-stu-id="31b2d-117">Be sure that you set the `connectionString` variable to a value that is appropriate for your database.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="31b2d-118">接続文字列内に機密情報 (パスワードなど) を格納すると、アプリケーションのセキュリティに影響を及ぼすことがあります。</span><span class="sxs-lookup"><span data-stu-id="31b2d-118">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="31b2d-119">データベースへのアクセスを制御する方法としては、Windows 認証 (統合セキュリティとも呼ばれます) を使用する方が安全です。</span><span class="sxs-lookup"><span data-stu-id="31b2d-119">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="31b2d-120">詳細については、「[接続情報の保護](/dotnet/framework/data/adonet/protecting-connection-information)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31b2d-120">For more information, see [Protecting Connection Information](/dotnet/framework/data/adonet/protecting-connection-information).</span></span>

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#30)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#30)]

3. <span data-ttu-id="31b2d-121">とを初期化し、データバインディングを設定するフォームのイベントのハンドラーを実装し <xref:System.Windows.Forms.Form.Load> <xref:System.Windows.Forms.DataGridView> <xref:System.Windows.Forms.BindingSource> ます。</span><span class="sxs-lookup"><span data-stu-id="31b2d-121">Implement a handler for your form's <xref:System.Windows.Forms.Form.Load> event that initializes the <xref:System.Windows.Forms.DataGridView> and <xref:System.Windows.Forms.BindingSource> and sets up the data binding.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#10)]

4. <span data-ttu-id="31b2d-122"><xref:System.Windows.Forms.DataGridView.DataError>でイベントを処理し <xref:System.Windows.Forms.DataGridView> ます。</span><span class="sxs-lookup"><span data-stu-id="31b2d-122">Handle the <xref:System.Windows.Forms.DataGridView.DataError> event on the <xref:System.Windows.Forms.DataGridView>.</span></span>

    <span data-ttu-id="31b2d-123">エラーのコンテキストがコミット操作の場合は、エラーをに表示 <xref:System.Windows.Forms.MessageBox> します。</span><span class="sxs-lookup"><span data-stu-id="31b2d-123">If the context for the error is a commit operation, display the error in a <xref:System.Windows.Forms.MessageBox>.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#20)]

## <a name="testing-the-application"></a><span data-ttu-id="31b2d-124">アプリケーションのテスト</span><span class="sxs-lookup"><span data-stu-id="31b2d-124">Testing the Application</span></span>

<span data-ttu-id="31b2d-125">フォームをテストして、期待どおりに動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="31b2d-125">You can now test the form to make sure it behaves as expected.</span></span>

#### <a name="to-test-the-form"></a><span data-ttu-id="31b2d-126">フォームをテストするには</span><span class="sxs-lookup"><span data-stu-id="31b2d-126">To test the form</span></span>

- <span data-ttu-id="31b2d-127">F5 キーを押してアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="31b2d-127">Press F5 to run the application.</span></span>

  <span data-ttu-id="31b2d-128">Customers テーブルのデータが入力されたコントロールが表示され <xref:System.Windows.Forms.DataGridView> ます。</span><span class="sxs-lookup"><span data-stu-id="31b2d-128">You will see a <xref:System.Windows.Forms.DataGridView> control filled with data from the Customers table.</span></span> <span data-ttu-id="31b2d-129">に重複する値を入力して編集をコミットすると、 `CustomerID` セルの値は自動的に元に戻り、データエントリエラーを示すが表示され <xref:System.Windows.Forms.MessageBox> ます。</span><span class="sxs-lookup"><span data-stu-id="31b2d-129">If you enter a duplicate value for `CustomerID` and commit the edit, the cell value will revert automatically and you will see a <xref:System.Windows.Forms.MessageBox> that displays the data entry error.</span></span>

## <a name="next-steps"></a><span data-ttu-id="31b2d-130">次の手順</span><span class="sxs-lookup"><span data-stu-id="31b2d-130">Next Steps</span></span>

<span data-ttu-id="31b2d-131">このアプリケーションを使用すると、コントロールの機能についての基本的な理解を得ることができ <xref:System.Windows.Forms.DataGridView> ます。</span><span class="sxs-lookup"><span data-stu-id="31b2d-131">This application gives you a basic understanding of the <xref:System.Windows.Forms.DataGridView> control's capabilities.</span></span> <span data-ttu-id="31b2d-132">コントロールの外観と動作は、 <xref:System.Windows.Forms.DataGridView> 次のいくつかの方法でカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="31b2d-132">You can customize the appearance and behavior of the <xref:System.Windows.Forms.DataGridView> control in several ways:</span></span>

- <span data-ttu-id="31b2d-133">罫線とヘッダーのスタイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="31b2d-133">Change border and header styles.</span></span> <span data-ttu-id="31b2d-134">詳細については、「 [方法: Windows フォーム DataGridView コントロールの境界線とグリッド線のスタイルを変更する](change-the-border-and-gridline-styles-in-the-datagrid.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31b2d-134">For more information, see [How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control](change-the-border-and-gridline-styles-in-the-datagrid.md).</span></span>

- <span data-ttu-id="31b2d-135">コントロールへのユーザー入力を有効または制限 <xref:System.Windows.Forms.DataGridView> します。</span><span class="sxs-lookup"><span data-stu-id="31b2d-135">Enable or restrict user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="31b2d-136">詳細については、「 [方法: Windows フォーム Datagridview コントロールで行の追加と削除を回避](prevent-row-addition-and-deletion-datagridview.md)する」および「 [方法: Windows フォーム Datagridview コントロールで列を Read-Only する](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31b2d-136">For more information, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md), and [How to: Make Columns Read-Only in the Windows Forms DataGridView Control](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).</span></span>

- <span data-ttu-id="31b2d-137">コントロールへのユーザー入力を検証 <xref:System.Windows.Forms.DataGridView> します。</span><span class="sxs-lookup"><span data-stu-id="31b2d-137">Validate user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="31b2d-138">詳細については、「 [チュートリアル: Windows フォーム DataGridView コントロールでのデータの検証](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31b2d-138">For more information, see [Walkthrough: Validating Data in the Windows Forms DataGridView Control](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).</span></span>

- <span data-ttu-id="31b2d-139">仮想モードを使用して非常に大きなデータセットを処理します。</span><span class="sxs-lookup"><span data-stu-id="31b2d-139">Handle very large data sets using virtual mode.</span></span> <span data-ttu-id="31b2d-140">詳細については、「 [チュートリアル: Windows フォーム DataGridView コントロールでの仮想モードの実装](implementing-virtual-mode-wf-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31b2d-140">For more information, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](implementing-virtual-mode-wf-datagridview-control.md).</span></span>

- <span data-ttu-id="31b2d-141">セルの外観をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="31b2d-141">Customize the appearance of cells.</span></span> <span data-ttu-id="31b2d-142">詳細については、「 [方法: Windows フォーム Datagridview コントロールのセルの外観をカスタマイズ](customize-the-appearance-of-cells-in-the-datagrid.md) する」および「 [方法: Windows フォーム Datagridview コントロールの既定のセルスタイルを設定する](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31b2d-142">For more information, see [How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control](customize-the-appearance-of-cells-in-the-datagrid.md) and [How to: Set Default Cell Styles for the Windows Forms DataGridView Control](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="31b2d-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="31b2d-143">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="31b2d-144">Windows フォーム DataGridView コントロールでのデータ入力</span><span class="sxs-lookup"><span data-stu-id="31b2d-144">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="31b2d-145">方法: Windows フォーム DataGridView コントロールでのデータ入力中に発生したエラーを処理する</span><span class="sxs-lookup"><span data-stu-id="31b2d-145">How to: Handle Errors That Occur During Data Entry in the Windows Forms DataGridView Control</span></span>](handle-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [<span data-ttu-id="31b2d-146">チュートリアル: Windows フォーム DataGridView コントロールのデータの妥当性検査</span><span class="sxs-lookup"><span data-stu-id="31b2d-146">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="31b2d-147">接続情報の保護</span><span class="sxs-lookup"><span data-stu-id="31b2d-147">Protecting Connection Information</span></span>](/dotnet/framework/data/adonet/protecting-connection-information)
