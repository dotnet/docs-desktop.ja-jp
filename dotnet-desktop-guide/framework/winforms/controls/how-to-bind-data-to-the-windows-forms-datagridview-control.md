---
title: DataGridView コントロールにデータをバインドする
ms.date: 02/08/2019
description: DataGridView コントロールが標準の Windows フォームデータバインディングモデルをサポートして、さまざまなデータソースにバインドできるようにする方法について説明します。
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [Windows Forms], grids
- data binding [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 1660f69c-5711-45d2-abc1-e25bc6779124
ms.openlocfilehash: 7daf68691ee67472ab8cfba7b396faeffa27a206
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982228"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control"></a><span data-ttu-id="9cdd1-103">方法: Windows フォーム DataGridView コントロールにデータをバインドする</span><span class="sxs-lookup"><span data-stu-id="9cdd1-103">How to: Bind data to the Windows Forms DataGridView control</span></span>

<span data-ttu-id="9cdd1-104">コントロールでは、 <xref:System.Windows.Forms.DataGridView> 標準の Windows フォームデータバインディングモデルがサポートされているため、さまざまなデータソースにバインドできます。</span><span class="sxs-lookup"><span data-stu-id="9cdd1-104">The <xref:System.Windows.Forms.DataGridView> control supports the standard Windows Forms data binding model, so it can bind to a variety of data sources.</span></span> <span data-ttu-id="9cdd1-105">通常、 <xref:System.Windows.Forms.BindingSource> データソースとの対話を管理するにバインドします。</span><span class="sxs-lookup"><span data-stu-id="9cdd1-105">Usually, you bind to a <xref:System.Windows.Forms.BindingSource> that manages the interaction with the data source.</span></span> <span data-ttu-id="9cdd1-106">には <xref:System.Windows.Forms.BindingSource> 任意の Windows フォームデータソースを指定できます。これにより、データの場所を選択または変更する際の柔軟性が向上します。</span><span class="sxs-lookup"><span data-stu-id="9cdd1-106">The <xref:System.Windows.Forms.BindingSource> can be any Windows Forms data source, which gives you great flexibility when choosing or modifying your data's location.</span></span> <span data-ttu-id="9cdd1-107">コントロールでサポートされているデータソースの詳細については <xref:System.Windows.Forms.DataGridView> 、「 [DataGridView コントロールの概要](datagridview-control-overview-windows-forms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9cdd1-107">For more information about data sources the <xref:System.Windows.Forms.DataGridView> control supports, see the [DataGridView control overview](datagridview-control-overview-windows-forms.md).</span></span>  

<span data-ttu-id="9cdd1-108">Visual Studio では、DataGridView コントロールへのデータバインドが広範囲にサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9cdd1-108">Visual Studio has extensive support for data binding to the DataGridView control.</span></span> <span data-ttu-id="9cdd1-109">詳細については、「 [方法: デザイナーを使用してデータを Windows フォーム DataGridView コントロールにバインド](bind-data-to-the-datagrid-using-the-designer.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9cdd1-109">For more information, see [How to: Bind data to the Windows Forms DataGridView control using the Designer](bind-data-to-the-datagrid-using-the-designer.md).</span></span>  

<span data-ttu-id="9cdd1-110">DataGridView コントロールをデータに接続するには:</span><span class="sxs-lookup"><span data-stu-id="9cdd1-110">To connect a DataGridView control to data:</span></span>

1. <span data-ttu-id="9cdd1-111">データの取得の詳細を処理するメソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="9cdd1-111">Implement a method to handle the details of retrieving the data.</span></span> <span data-ttu-id="9cdd1-112">次のコード例では、を `GetData` 初期化し、それを使用してを設定するメソッドを実装 <xref:System.Data.SqlClient.SqlDataAdapter> して <xref:System.Data.DataTable> います。</span><span class="sxs-lookup"><span data-stu-id="9cdd1-112">The following code example implements a `GetData` method that initializes a <xref:System.Data.SqlClient.SqlDataAdapter>, and uses it to populate a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="9cdd1-113">次 <xref:System.Data.DataTable> に、をにバインドし <xref:System.Windows.Forms.BindingSource> ます。</span><span class="sxs-lookup"><span data-stu-id="9cdd1-113">It then binds the <xref:System.Data.DataTable> to the <xref:System.Windows.Forms.BindingSource>.</span></span>

2. <span data-ttu-id="9cdd1-114">フォームのイベントハンドラーで、コントロールをに <xref:System.Windows.Forms.Form.Load> バインド <xref:System.Windows.Forms.DataGridView> し、 <xref:System.Windows.Forms.BindingSource> メソッドを呼び出して `GetData` データを取得します。</span><span class="sxs-lookup"><span data-stu-id="9cdd1-114">In the form's <xref:System.Windows.Forms.Form.Load> event handler, bind the <xref:System.Windows.Forms.DataGridView> control to the <xref:System.Windows.Forms.BindingSource>, and call the `GetData` method to retrieve the data.</span></span>  

## <a name="example"></a><span data-ttu-id="9cdd1-115">例</span><span class="sxs-lookup"><span data-stu-id="9cdd1-115">Example</span></span>

<span data-ttu-id="9cdd1-116">この完全なコード例では、データベースからデータを取得して、Windows フォームに DataGridView コントロールを設定します。</span><span class="sxs-lookup"><span data-stu-id="9cdd1-116">This complete code example retrieves data from a database to populate a DataGridView control in a Windows form.</span></span> <span data-ttu-id="9cdd1-117">フォームには、データを再読み込みし、変更をデータベースに送信するためのボタンもあります。</span><span class="sxs-lookup"><span data-stu-id="9cdd1-117">The form also has buttons to reload data and submit changes to the database.</span></span>  

<span data-ttu-id="9cdd1-118">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9cdd1-118">This example requires:</span></span>

- <span data-ttu-id="9cdd1-119">Northwind SQL Server サンプルデータベースへのアクセス。</span><span class="sxs-lookup"><span data-stu-id="9cdd1-119">Access to a Northwind SQL Server sample database.</span></span> <span data-ttu-id="9cdd1-120">Northwind サンプルデータベースのインストールの詳細については、「 [ADO.NET コードサンプルのサンプルデータベースの取得](/dotnet/framework/data/adonet/sql/linq/downloading-sample-databases)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9cdd1-120">For more information about installing the Northwind sample database, see [Get the sample databases for ADO.NET code samples](/dotnet/framework/data/adonet/sql/linq/downloading-sample-databases).</span></span>

- <span data-ttu-id="9cdd1-121">システム、system.string、system.string、および System.Xml アセンブリへの参照です。</span><span class="sxs-lookup"><span data-stu-id="9cdd1-121">References to the System, System.Windows.Forms, System.Data, and System.Xml assemblies.</span></span>  

<span data-ttu-id="9cdd1-122">この例をビルドして実行するには、新しい Windows フォームプロジェクトの *Form1* コードファイルにコードを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="9cdd1-122">To build and run this example, paste the code into the *Form1* code file in a new Windows Forms project.</span></span> <span data-ttu-id="9cdd1-123">C# または Visual Basic コマンドラインからのビルドの詳細については、「 [csc.exeを使用したコマンドライン ](/dotnet/csharp/language-reference/compiler-options/command-line-building-with-csc-exe) からのビルド」または「 [コマンドラインからのビルド](/dotnet/visual-basic/reference/command-line-compiler/building-from-the-command-line)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9cdd1-123">For information about building from the C# or Visual Basic command line, see [Command-line building with csc.exe](/dotnet/csharp/language-reference/compiler-options/command-line-building-with-csc-exe) or [Build from the command line](/dotnet/visual-basic/reference/command-line-compiler/building-from-the-command-line).</span></span>  
  
<span data-ttu-id="9cdd1-124">この例の変数に、 `connectionString` Northwind SQL Server サンプルデータベース接続の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="9cdd1-124">Populate the `connectionString` variable in the example with the values for your Northwind SQL Server sample database connection.</span></span> <span data-ttu-id="9cdd1-125">Windows 認証 (統合セキュリティとも呼ばれます) は、接続文字列にパスワードを格納するよりも、データベースに接続するより安全な方法です。</span><span class="sxs-lookup"><span data-stu-id="9cdd1-125">Windows Authentication, also called integrated security, is a more secure way to connect to the database than storing a password in the connection string.</span></span> <span data-ttu-id="9cdd1-126">接続のセキュリティの詳細については、「 [接続情報の保護](/dotnet/framework/data/adonet/protecting-connection-information)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9cdd1-126">For more information about connection security, see [Protect connection information](/dotnet/framework/data/adonet/protecting-connection-information).</span></span>  

[!code-csharp[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs)]
[!code-vb[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="9cdd1-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="9cdd1-127">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="9cdd1-128">Windows フォーム DataGridView コントロールにデータを表示する</span><span class="sxs-lookup"><span data-stu-id="9cdd1-128">Display data in the Windows Forms DataGridView control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="9cdd1-129">接続情報の保護</span><span class="sxs-lookup"><span data-stu-id="9cdd1-129">Protect connection information</span></span>](/dotnet/framework/data/adonet/protecting-connection-information)
