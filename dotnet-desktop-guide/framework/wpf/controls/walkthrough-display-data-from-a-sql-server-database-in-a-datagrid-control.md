---
title: 'チュートリアル: DataGrid コントロールで SQL Server データベースのデータを表示する'
description: このチュートリアルを使用して、SQL Server データベースからデータを取得し、それを Windows Presentation Foundation の DataGrid コントロールに表示する方法について説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], displaying data from SQL Server
- controls [WPF], DataGrid
ms.assetid: 6810b048-0a23-4f86-bfa5-97f92b3cfab4
ms.openlocfilehash: 23aee2dcbd9fc22a8c88bd2e03dcbc6552279ce6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985568"
---
# <a name="walkthrough-display-data-from-a-sql-server-database-in-a-datagrid-control"></a><span data-ttu-id="ef3fe-103">チュートリアル: DataGrid コントロールで SQL Server データベースのデータを表示する</span><span class="sxs-lookup"><span data-stu-id="ef3fe-103">Walkthrough: Display data from a SQL Server database in a DataGrid control</span></span>

<span data-ttu-id="ef3fe-104">このチュートリアルでは、SQL Server データベースからデータを取得し、そのデータを <xref:System.Windows.Controls.DataGrid> コントロールに表示します。</span><span class="sxs-lookup"><span data-stu-id="ef3fe-104">In this walkthrough, you retrieve data from a SQL Server database and display that data in a <xref:System.Windows.Controls.DataGrid> control.</span></span> <span data-ttu-id="ef3fe-105">ADO.NET Entity Framework を使用して、データを表すエンティティ クラスを作成し、LINQ を使用して、指定されたデータをエンティティ クラスから取得するクエリを記述します。</span><span class="sxs-lookup"><span data-stu-id="ef3fe-105">You use the ADO.NET Entity Framework to create the entity classes that represent the data, and use LINQ to write a query that retrieves the specified data from an entity class.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ef3fe-106">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ef3fe-106">Prerequisites</span></span>

<span data-ttu-id="ef3fe-107">このチュートリアルを実行するには、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="ef3fe-107">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="ef3fe-108">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ef3fe-108">Visual Studio.</span></span>

- <span data-ttu-id="ef3fe-109">AdventureWorks サンプル データベースが添付された、SQL Server または SQL Server Express の実行中のインスタンスへのアクセス権。</span><span class="sxs-lookup"><span data-stu-id="ef3fe-109">Access to a running instance of SQL Server or SQL Server Express that has the AdventureWorks sample database attached to it.</span></span> <span data-ttu-id="ef3fe-110">AdventureWorks データベースは [GitHub](https://github.com/Microsoft/sql-server-samples/releases) からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="ef3fe-110">You can download the AdventureWorks database from the [GitHub](https://github.com/Microsoft/sql-server-samples/releases).</span></span>

## <a name="create-entity-classes"></a><span data-ttu-id="ef3fe-111">エンティティ クラスを作成する</span><span class="sxs-lookup"><span data-stu-id="ef3fe-111">Create entity classes</span></span>

1. <span data-ttu-id="ef3fe-112">Visual Basic または C# で新しい WPF アプリケーション プロジェクトを作成し、`DataGridSQLExample` という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="ef3fe-112">Create a new WPF Application project in Visual Basic or C#, and name it `DataGridSQLExample`.</span></span>

2. <span data-ttu-id="ef3fe-113">ソリューション エクスプローラーでプロジェクトを右クリックし、 **[追加]** をポイントし、 **[新しい項目]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ef3fe-113">In Solution Explorer, right-click your project, point to **Add**, and then select **New Item**.</span></span>

     <span data-ttu-id="ef3fe-114">[新しい項目の追加] ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ef3fe-114">The Add New Item dialog box appears.</span></span>

3. <span data-ttu-id="ef3fe-115">[インストール済みのテンプレート] ペインで **[データ]** を選択し、テンプレート一覧で **[ADO.NET Entity Data Model]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ef3fe-115">In the Installed Templates pane, select **Data** and in the list of templates, select **ADO.NET Entity Data Model**.</span></span>

     ![ADO.NET Entity Data Model 項目テンプレート](/dotnet/framework/wcf/feature-details/media/ado-net-entity-data-model-item-template.png)

4. <span data-ttu-id="ef3fe-117">ファイルに `AdventureWorksModel.edmx` と名前を付け、 **[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ef3fe-117">Name the file `AdventureWorksModel.edmx` and then click **Add**.</span></span>

     <span data-ttu-id="ef3fe-118">Entity Data Model ウィザードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ef3fe-118">The Entity Data Model Wizard appears.</span></span>

5. <span data-ttu-id="ef3fe-119">[モデルのコンテンツの選択] 画面で、 **[データベースから EF Designer]** をクリックし、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ef3fe-119">In the Choose Model Contents screen, select **EF Designer from database** and then click **Next**.</span></span>

6. <span data-ttu-id="ef3fe-120">[データ接続の選択] 画面で、AdventureWorksLT2008 データベースへの接続を指定します。</span><span class="sxs-lookup"><span data-stu-id="ef3fe-120">In the Choose Your Data Connection screen, provide the connection to your AdventureWorksLT2008 database.</span></span> <span data-ttu-id="ef3fe-121">詳細については、「[[データ接続の選択] ダイアログ ボックス](/previous-versions/dotnet/netframework-4.0/bb399244(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef3fe-121">For more information, see [Choose Your Data Connection Dialog Box](/previous-versions/dotnet/netframework-4.0/bb399244(v=vs.100)).</span></span>

    <span data-ttu-id="ef3fe-122">名前が `AdventureWorksLT2008Entities` であり、 **[エンティティ接続設定に名前を付けて App.Config に保存]** チェック ボックスがオンであることを確認してから、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ef3fe-122">Make sure that the name is `AdventureWorksLT2008Entities` and that the **Save entity connection settings in App.Config as** check box is selected, and then click **Next**.</span></span>

7. <span data-ttu-id="ef3fe-123">[データベース オブジェクトの選択] 画面で、[テーブル] ノードを展開し、**Product** および **ProductCategory** テーブルを選択します。</span><span class="sxs-lookup"><span data-stu-id="ef3fe-123">In the Choose Your Database Objects screen, expand the Tables node, and select the **Product** and **ProductCategory** tables.</span></span>

     <span data-ttu-id="ef3fe-124">すべてのテーブルのエンティティ クラスを生成できます。ただし、この例では、これら 2 つのテーブルからのみデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="ef3fe-124">You can generate entity classes for all of the tables; however, in this example you only retrieve data from those two tables.</span></span>

     <span data-ttu-id="ef3fe-125">![テーブルから Product および ProductCategory を選択する](./media/datagrid-sql-ef-step4.png "DataGrid_SQL_EF_Step4")</span><span class="sxs-lookup"><span data-stu-id="ef3fe-125">![Select Product and ProductCategory from tables](./media/datagrid-sql-ef-step4.png "DataGrid_SQL_EF_Step4")</span></span>

8. <span data-ttu-id="ef3fe-126">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ef3fe-126">Click **Finish**.</span></span>

     <span data-ttu-id="ef3fe-127">Entity Designer に Product および ProductCategory エンティティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ef3fe-127">The Product and ProductCategory entities are displayed in the Entity Designer.</span></span>

     <span data-ttu-id="ef3fe-128">![Product および ProductCategory エンティティ モデル](./media/datagrid-sql-ef-step5.png "DataGrid_SQL_EF_Step5")</span><span class="sxs-lookup"><span data-stu-id="ef3fe-128">![Product and ProductCategory entity models](./media/datagrid-sql-ef-step5.png "DataGrid_SQL_EF_Step5")</span></span>

## <a name="retrieve-and-present-the-data"></a><span data-ttu-id="ef3fe-129">データの取得と表示</span><span class="sxs-lookup"><span data-stu-id="ef3fe-129">Retrieve and present the data</span></span>

1. <span data-ttu-id="ef3fe-130">MainWindow.xaml ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="ef3fe-130">Open the MainWindow.xaml file.</span></span>

2. <span data-ttu-id="ef3fe-131"><xref:System.Windows.Window> の <xref:System.Windows.FrameworkElement.Width%2A> プロパティを 450 に設定します。</span><span class="sxs-lookup"><span data-stu-id="ef3fe-131">Set the <xref:System.Windows.FrameworkElement.Width%2A> property on the <xref:System.Windows.Window> to 450.</span></span>

3. <span data-ttu-id="ef3fe-132">XAML エディターで、`<Grid>` タグと `</Grid>` タグの間に次の <xref:System.Windows.Controls.DataGrid> タグを追加して、`dataGrid1` という名前の <xref:System.Windows.Controls.DataGrid> を追加します。</span><span class="sxs-lookup"><span data-stu-id="ef3fe-132">In the XAML editor, add the following <xref:System.Windows.Controls.DataGrid> tag between the `<Grid>` and `</Grid>` tags to add a <xref:System.Windows.Controls.DataGrid> named `dataGrid1`.</span></span>

     [!code-xaml[DataGrid_SQL_EF_Walkthrough#3](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml#3)]

     <span data-ttu-id="ef3fe-133">![DataGrid が表示されたウィンドウ](./media/datagrid-sql-ef-step6.png "DataGrid_SQL_EF_Step6")</span><span class="sxs-lookup"><span data-stu-id="ef3fe-133">![Window with DataGrid](./media/datagrid-sql-ef-step6.png "DataGrid_SQL_EF_Step6")</span></span>

4. <span data-ttu-id="ef3fe-134"><xref:System.Windows.Window>を選択します。</span><span class="sxs-lookup"><span data-stu-id="ef3fe-134">Select the <xref:System.Windows.Window>.</span></span>

5. <span data-ttu-id="ef3fe-135">プロパティ ウィンドウまたは XAML エディターを使用して、<xref:System.Windows.FrameworkElement.Loaded> イベントの `Window_Loaded` という名前の <xref:System.Windows.Window> のイベント ハンドラーを作成します。</span><span class="sxs-lookup"><span data-stu-id="ef3fe-135">Using the Properties window or XAML editor, create an event handler for the <xref:System.Windows.Window> named `Window_Loaded` for the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span> <span data-ttu-id="ef3fe-136">詳細については、[方法: 単純なイベント ハンドラーを作成する](/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef3fe-136">For more information, see [How to: Create a Simple Event Handler](/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span></span>

     <span data-ttu-id="ef3fe-137">MainWindow.xaml の XAML を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ef3fe-137">The following shows the XAML for MainWindow.xaml.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ef3fe-138">Visual Basic を使用する場合は、MainWindow.xaml の最初の行の `x:Class="DataGridSQLExample.MainWindow"` を `x:Class="MainWindow"` に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="ef3fe-138">If you are using Visual Basic, in the first line of MainWindow.xaml, replace `x:Class="DataGridSQLExample.MainWindow"` with `x:Class="MainWindow"`.</span></span>

     [!code-xaml[DataGrid_SQL_EF_Walkthrough#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml#1)]

6. <span data-ttu-id="ef3fe-139"><xref:System.Windows.Window> の分離コード ファイル (MainWindow.xaml.vb または MainWindow.xaml.cs) を開きます。</span><span class="sxs-lookup"><span data-stu-id="ef3fe-139">Open the code-behind file (MainWindow.xaml.vb or MainWindow.xaml.cs) for the <xref:System.Windows.Window>.</span></span>

7. <span data-ttu-id="ef3fe-140">次のコードを追加して、結合されたテーブルから特定の値のみを取得し、<xref:System.Windows.Controls.DataGrid> の <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> プロパティをクエリの結果に設定します。</span><span class="sxs-lookup"><span data-stu-id="ef3fe-140">Add the following code to retrieve only specific values from the joined tables and set the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.DataGrid> to the results of the query.</span></span>

     [!code-csharp[DataGrid_SQL_EF_Walkthrough#2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml.cs#2)]
     [!code-vb[DataGrid_SQL_EF_Walkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/VB/MainWindow.xaml.vb#2)]

8. <span data-ttu-id="ef3fe-141">例を実行します。</span><span class="sxs-lookup"><span data-stu-id="ef3fe-141">Run the example.</span></span>

     <span data-ttu-id="ef3fe-142">データを表示する <xref:System.Windows.Controls.DataGrid> が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ef3fe-142">You should see a <xref:System.Windows.Controls.DataGrid> that displays data.</span></span>

     <span data-ttu-id="ef3fe-143">![SQL Database のデータが表示された DataGrid](./media/datagrid-sql-ef-step7.png "DataGrid_SQL_EF_Step7")</span><span class="sxs-lookup"><span data-stu-id="ef3fe-143">![DataGrid with data from SQL database](./media/datagrid-sql-ef-step7.png "DataGrid_SQL_EF_Step7")</span></span>

## <a name="see-also"></a><span data-ttu-id="ef3fe-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="ef3fe-144">See also</span></span>

- <xref:System.Windows.Controls.DataGrid>
