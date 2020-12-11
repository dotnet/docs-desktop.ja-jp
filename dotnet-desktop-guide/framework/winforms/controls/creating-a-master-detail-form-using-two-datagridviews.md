---
title: 'チュートリアル: 2 つの DataGridView コントロールを使用してマスター/詳細フォームを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], master/detail form
- parent-child tables [Windows Forms], displaying on Windows Forms
- master-details lists [Windows Forms], displaying on Windows Forms
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: c5fa29e8-47f7-4691-829b-0e697a691f36
ms.openlocfilehash: d6057eb16e8fc32c269d3013ee99cc1f276ecab6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974255"
---
# <a name="walkthrough-creating-a-masterdetail-form-using-two-windows-forms-datagridview-controls"></a><span data-ttu-id="88af4-102">チュートリアル: Windows フォームの 2 つの DataGridView コントロールを使用したマスター/詳細形式のフォームを作成する</span><span class="sxs-lookup"><span data-stu-id="88af4-102">Walkthrough: Creating a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>

<span data-ttu-id="88af4-103">コントロールを使用する最も一般的なシナリオの1つ <xref:System.Windows.Forms.DataGridView> は、 *マスター/詳細* 形式です。このフォームでは、2つのデータベーステーブル間の親子関係が表示されます。</span><span class="sxs-lookup"><span data-stu-id="88af4-103">One of the most common scenarios for using the <xref:System.Windows.Forms.DataGridView> control is the *master/detail* form, in which a parent/child relationship between two database tables is displayed.</span></span> <span data-ttu-id="88af4-104">マスターテーブル内の行を選択すると、対応する子データで詳細テーブルが更新されます。</span><span class="sxs-lookup"><span data-stu-id="88af4-104">Selecting rows in the master table causes the detail table to update with the corresponding child data.</span></span>

<span data-ttu-id="88af4-105">マスター/詳細フォームの実装は、コントロールとコンポーネントの間の相互作用を使用して簡単に行うことが <xref:System.Windows.Forms.DataGridView> <xref:System.Windows.Forms.BindingSource> できます。</span><span class="sxs-lookup"><span data-stu-id="88af4-105">Implementing a master/detail form is easy using the interaction between the <xref:System.Windows.Forms.DataGridView> control and the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="88af4-106">このチュートリアルでは、2つのコントロールと2つのコンポーネントを使用してフォームをビルドし <xref:System.Windows.Forms.DataGridView> <xref:System.Windows.Forms.BindingSource> ます。</span><span class="sxs-lookup"><span data-stu-id="88af4-106">In this walkthrough, you will build the form using two <xref:System.Windows.Forms.DataGridView> controls and two <xref:System.Windows.Forms.BindingSource> components.</span></span> <span data-ttu-id="88af4-107">フォームでは、Northwind SQL Server サンプルデータベースにとという2つの関連テーブルが表示されます。 `Customers` `Orders`</span><span class="sxs-lookup"><span data-stu-id="88af4-107">The form will show two related tables in the Northwind SQL Server sample database: `Customers` and `Orders`.</span></span> <span data-ttu-id="88af4-108">完了すると、マスター内のデータベースのすべての顧客 <xref:System.Windows.Forms.DataGridView> と、選択した顧客のすべての注文が詳細に表示され <xref:System.Windows.Forms.DataGridView> ます。</span><span class="sxs-lookup"><span data-stu-id="88af4-108">When you are finished, you will have a form that shows all the customers in the database in the master <xref:System.Windows.Forms.DataGridView> and all the orders for the selected customer in the detail <xref:System.Windows.Forms.DataGridView>.</span></span>

<span data-ttu-id="88af4-109">このトピックのコードを単一のリストとしてコピーする方法については、「 [方法: 2 つの Windows フォーム DataGridView コントロールを使用してマスター/詳細フォームを作成](create-a-master-detail-form-using-two-datagridviews.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88af4-109">To copy the code in this topic as a single listing, see [How to: Create a Master/Detail Form Using Two Windows Forms DataGridView Controls](create-a-master-detail-form-using-two-datagridviews.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="88af4-110">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="88af4-110">Prerequisites</span></span>

<span data-ttu-id="88af4-111">このチュートリアルを完了するための要件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="88af4-111">In order to complete this walkthrough, you will need:</span></span>

- <span data-ttu-id="88af4-112">Northwind SQL Server サンプルデータベースを持つサーバーへのアクセス。</span><span class="sxs-lookup"><span data-stu-id="88af4-112">Access to a server that has the Northwind SQL Server sample database.</span></span>

## <a name="creating-the-form"></a><span data-ttu-id="88af4-113">フォームの作成</span><span class="sxs-lookup"><span data-stu-id="88af4-113">Creating the form</span></span>

#### <a name="to-create-a-masterdetail-form"></a><span data-ttu-id="88af4-114">マスター/詳細フォームを作成するには</span><span class="sxs-lookup"><span data-stu-id="88af4-114">To create a master/detail form</span></span>

1. <span data-ttu-id="88af4-115">から派生するクラスを作成し、 <xref:System.Windows.Forms.Form> 2 つの <xref:System.Windows.Forms.DataGridView> コントロールと2つのコンポーネントを格納し <xref:System.Windows.Forms.BindingSource> ます。</span><span class="sxs-lookup"><span data-stu-id="88af4-115">Create a class that derives from <xref:System.Windows.Forms.Form> and contains two <xref:System.Windows.Forms.DataGridView> controls and two <xref:System.Windows.Forms.BindingSource> components.</span></span> <span data-ttu-id="88af4-116">次のコードは、基本的なフォームの初期化を提供し、メソッドを含んでい `Main` ます。</span><span class="sxs-lookup"><span data-stu-id="88af4-116">The following code provides basic form initialization and includes a `Main` method.</span></span> <span data-ttu-id="88af4-117">Visual Studio デザイナーを使用してフォームを作成する場合は、このコードの代わりにデザイナーで生成されたコードを使用できますが、ここでは変数宣言に示されている名前を使用してください。</span><span class="sxs-lookup"><span data-stu-id="88af4-117">If you use the Visual Studio designer to create your form, you can use the designer generated code instead of this code, but be sure to use the names shown in the variable declarations here.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#02)]

2. <span data-ttu-id="88af4-118">データベースへの接続の詳細を処理するために、フォームのクラス定義にメソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="88af4-118">Implement a method in your form's class definition for handling the detail of connecting to the database.</span></span> <span data-ttu-id="88af4-119">この例では、オブジェクトを設定し、 `GetData` <xref:System.Data.DataSet> オブジェクトを <xref:System.Data.DataRelation> データセットに追加して、コンポーネントをバインドするメソッドを使用し <xref:System.Windows.Forms.BindingSource> ます。</span><span class="sxs-lookup"><span data-stu-id="88af4-119">This example uses a `GetData` method that populates a <xref:System.Data.DataSet> object, adds a <xref:System.Data.DataRelation> object to the data set, and binds the <xref:System.Windows.Forms.BindingSource> components.</span></span> <span data-ttu-id="88af4-120">`connectionString` 変数は、使用しているデータベースに合った値に設定してください。</span><span class="sxs-lookup"><span data-stu-id="88af4-120">Be sure to set the `connectionString` variable to a value that is appropriate for your database.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="88af4-121">接続文字列内に機密情報 (パスワードなど) を格納すると、アプリケーションのセキュリティに影響を及ぼすことがあります。</span><span class="sxs-lookup"><span data-stu-id="88af4-121">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="88af4-122">データベースへのアクセスを制御する方法としては、Windows 認証 (統合セキュリティとも呼ばれます) を使用する方が安全です。</span><span class="sxs-lookup"><span data-stu-id="88af4-122">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="88af4-123">詳細については、「[接続情報の保護](/dotnet/framework/data/adonet/protecting-connection-information)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88af4-123">For more information, see [Protecting Connection Information](/dotnet/framework/data/adonet/protecting-connection-information).</span></span>

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#20)]

3. <span data-ttu-id="88af4-124"><xref:System.Windows.Forms.Form.Load> <xref:System.Windows.Forms.DataGridView> コントロールをコンポーネントにバインドし、メソッドを呼び出すフォームのイベントのハンドラーを実装 <xref:System.Windows.Forms.BindingSource> し `GetData` ます。</span><span class="sxs-lookup"><span data-stu-id="88af4-124">Implement a handler for your form's <xref:System.Windows.Forms.Form.Load> event that binds the <xref:System.Windows.Forms.DataGridView> controls to the <xref:System.Windows.Forms.BindingSource> components and calls the `GetData` method.</span></span> <span data-ttu-id="88af4-125">次の例には、表示されるデータに合わせて列のサイズを変更するコードが含まれてい <xref:System.Windows.Forms.DataGridView> ます。</span><span class="sxs-lookup"><span data-stu-id="88af4-125">The following example includes code that resizes <xref:System.Windows.Forms.DataGridView> columns to fit the displayed data.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#10)]

## <a name="testing-the-application"></a><span data-ttu-id="88af4-126">アプリケーションのテスト</span><span class="sxs-lookup"><span data-stu-id="88af4-126">Testing the Application</span></span>

<span data-ttu-id="88af4-127">フォームをテストして、期待どおりに動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="88af4-127">You can now test the form to make sure it behaves as expected.</span></span>

#### <a name="to-test-the-form"></a><span data-ttu-id="88af4-128">フォームをテストするには</span><span class="sxs-lookup"><span data-stu-id="88af4-128">To test the form</span></span>

- <span data-ttu-id="88af4-129">アプリケーションをコンパイルして実行します。</span><span class="sxs-lookup"><span data-stu-id="88af4-129">Compile and run the application.</span></span>

  <span data-ttu-id="88af4-130">2つのコントロールが1つ上に表示され <xref:System.Windows.Forms.DataGridView> ます。</span><span class="sxs-lookup"><span data-stu-id="88af4-130">You will see two <xref:System.Windows.Forms.DataGridView> controls, one above the other.</span></span> <span data-ttu-id="88af4-131">[上位] は Northwind テーブルの顧客であり、 `Customers` 一番下には `Orders` 選択した顧客に対応するがあります。</span><span class="sxs-lookup"><span data-stu-id="88af4-131">On top are the customers from the Northwind `Customers` table, and at the bottom are the `Orders` corresponding to the selected customer.</span></span> <span data-ttu-id="88af4-132">上部で異なる行を選択すると、 <xref:System.Windows.Forms.DataGridView> それに応じて下位の内容が <xref:System.Windows.Forms.DataGridView> 変化します。</span><span class="sxs-lookup"><span data-stu-id="88af4-132">As you select different rows in the upper <xref:System.Windows.Forms.DataGridView>, the contents of the lower <xref:System.Windows.Forms.DataGridView> change accordingly.</span></span>

## <a name="next-steps"></a><span data-ttu-id="88af4-133">次の手順</span><span class="sxs-lookup"><span data-stu-id="88af4-133">Next Steps</span></span>

<span data-ttu-id="88af4-134">このアプリケーションを使用すると、コントロールの機能についての基本的な理解を得ることができ <xref:System.Windows.Forms.DataGridView> ます。</span><span class="sxs-lookup"><span data-stu-id="88af4-134">This application gives you a basic understanding of the <xref:System.Windows.Forms.DataGridView> control's capabilities.</span></span> <span data-ttu-id="88af4-135">コントロールの外観と動作は、 <xref:System.Windows.Forms.DataGridView> 次のいくつかの方法でカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="88af4-135">You can customize the appearance and behavior of the <xref:System.Windows.Forms.DataGridView> control in several ways:</span></span>

- <span data-ttu-id="88af4-136">罫線とヘッダーのスタイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="88af4-136">Change border and header styles.</span></span> <span data-ttu-id="88af4-137">詳細については、「 [方法: Windows フォーム DataGridView コントロールの境界線とグリッド線のスタイルを変更する](change-the-border-and-gridline-styles-in-the-datagrid.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88af4-137">For more information, see [How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control](change-the-border-and-gridline-styles-in-the-datagrid.md).</span></span>

- <span data-ttu-id="88af4-138">コントロールへのユーザー入力を有効または制限 <xref:System.Windows.Forms.DataGridView> します。</span><span class="sxs-lookup"><span data-stu-id="88af4-138">Enable or restrict user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="88af4-139">詳細については、「 [方法: Windows フォーム Datagridview コントロールで行の追加と削除を回避](prevent-row-addition-and-deletion-datagridview.md)する」および「 [方法: Windows フォーム Datagridview コントロールで列を Read-Only する](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88af4-139">For more information, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md), and [How to: Make Columns Read-Only in the Windows Forms DataGridView Control](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).</span></span>

- <span data-ttu-id="88af4-140">コントロールへのユーザー入力を検証 <xref:System.Windows.Forms.DataGridView> します。</span><span class="sxs-lookup"><span data-stu-id="88af4-140">Validate user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="88af4-141">詳細については、「 [チュートリアル: Windows フォーム DataGridView コントロールでのデータの検証](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88af4-141">For more information, see [Walkthrough: Validating Data in the Windows Forms DataGridView Control](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).</span></span>

- <span data-ttu-id="88af4-142">仮想モードを使用して非常に大きなデータセットを処理します。</span><span class="sxs-lookup"><span data-stu-id="88af4-142">Handle very large data sets using virtual mode.</span></span> <span data-ttu-id="88af4-143">詳細については、「 [チュートリアル: Windows フォーム DataGridView コントロールでの仮想モードの実装](implementing-virtual-mode-wf-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88af4-143">For more information, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](implementing-virtual-mode-wf-datagridview-control.md).</span></span>

- <span data-ttu-id="88af4-144">セルの外観をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="88af4-144">Customize the appearance of cells.</span></span> <span data-ttu-id="88af4-145">詳細については、「 [方法: Windows フォーム Datagridview コントロールのセルの外観をカスタマイズ](customize-the-appearance-of-cells-in-the-datagrid.md) する」および「 [方法: Windows フォーム Datagridview コントロールの既定のセルスタイルを設定する](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88af4-145">For more information, see [How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control](customize-the-appearance-of-cells-in-the-datagrid.md) and [How to: Set Default Cell Styles for the Windows Forms DataGridView Control](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="88af4-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="88af4-146">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="88af4-147">Windows フォーム DataGridView コントロールでのデータの表示</span><span class="sxs-lookup"><span data-stu-id="88af4-147">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="88af4-148">方法: Windows フォームの 2 つの DataGridView コントロールを使用してマスター/詳細形式のフォームを作成する</span><span class="sxs-lookup"><span data-stu-id="88af4-148">How to: Create a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>](create-a-master-detail-form-using-two-datagridviews.md)
- [<span data-ttu-id="88af4-149">接続情報の保護</span><span class="sxs-lookup"><span data-stu-id="88af4-149">Protecting Connection Information</span></span>](/dotnet/framework/data/adonet/protecting-connection-information)
