---
title: アプリ データをキャッシュする
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthroughs [WPF], caching
- caching [.NET Framework]
- caching [WPF]
ms.assetid: dac2c9ce-042b-4d23-91eb-28f584415cef
ms.openlocfilehash: 03d54614b018c7cb8e17858eba61bb6efaa93cd0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985400"
---
# <a name="walkthrough-caching-application-data-in-a-wpf-application"></a><span data-ttu-id="a98de-102">チュートリアル: WPF アプリケーション内のアプリケーション データのキャッシュ</span><span class="sxs-lookup"><span data-stu-id="a98de-102">Walkthrough: Caching Application Data in a WPF Application</span></span>
<span data-ttu-id="a98de-103">キャッシュを使用すると、メモリにデータを格納して高速にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a98de-103">Caching enables you to store data in memory for rapid access.</span></span> <span data-ttu-id="a98de-104">アプリケーションからそのデータに再アクセスするときに、元のソースからではなく、キャッシュからデータを取得できます。</span><span class="sxs-lookup"><span data-stu-id="a98de-104">When the data is accessed again, applications can get the data from the cache instead of retrieving it from the original source.</span></span> <span data-ttu-id="a98de-105">そのため、パフォーマンスとスケーラビリティが向上します。</span><span class="sxs-lookup"><span data-stu-id="a98de-105">This can improve performance and scalability.</span></span> <span data-ttu-id="a98de-106">また、データ ソースが一時的に使用できない場合でも、キャッシュのデータを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a98de-106">In addition, caching makes data available when the data source is temporarily unavailable.</span></span>

 <span data-ttu-id="a98de-107">.NET Framework には、.NET Framework アプリケーションでキャッシュを使用できるようになるクラスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="a98de-107">The .NET Framework provides classes that enable you to use caching in .NET Framework applications.</span></span> <span data-ttu-id="a98de-108">これらのクラスは <xref:System.Runtime.Caching> 名前空間にあります。</span><span class="sxs-lookup"><span data-stu-id="a98de-108">These classes are located in the <xref:System.Runtime.Caching> namespace.</span></span>

> [!NOTE]
> <span data-ttu-id="a98de-109"><xref:System.Runtime.Caching> 名前空間は、.NET Framework 4 で新しく追加されました。</span><span class="sxs-lookup"><span data-stu-id="a98de-109">The <xref:System.Runtime.Caching> namespace is new in the .NET Framework 4.</span></span> <span data-ttu-id="a98de-110">この名前空間により、すべての .NET Framework アプリケーションでキャッシュを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="a98de-110">This namespace makes caching is available to all .NET Framework applications.</span></span> <span data-ttu-id="a98de-111">.NET Framework の以前のバージョンでは、キャッシュは <xref:System.Web> 名前空間でのみ使用可能だったため、ASP.NET クラスへの依存が必要でした。</span><span class="sxs-lookup"><span data-stu-id="a98de-111">In previous versions of the .NET Framework, caching was available only in the <xref:System.Web> namespace and therefore required a dependency on ASP.NET classes.</span></span>

 <span data-ttu-id="a98de-112">このチュートリアルでは、[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] アプリケーションの一部として .NET Framework で使用できるキャッシュ機能を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a98de-112">This walkthrough shows you how to use the caching functionality that is available in the .NET Framework as part of a [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="a98de-113">このチュートリアルでは、テキスト ファイルのコンテンツをキャッシュします。</span><span class="sxs-lookup"><span data-stu-id="a98de-113">In the walkthrough, you cache the contents of a text file.</span></span>

 <span data-ttu-id="a98de-114">このチュートリアルでは、以下のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="a98de-114">Tasks illustrated in this walkthrough include the following:</span></span>

- <span data-ttu-id="a98de-115">WPF アプリケーション プロジェクトを作成する。</span><span class="sxs-lookup"><span data-stu-id="a98de-115">Creating a WPF application project.</span></span>

- <span data-ttu-id="a98de-116">.NET Framework 4 への参照を追加する。</span><span class="sxs-lookup"><span data-stu-id="a98de-116">Adding a reference to the .NET Framework 4.</span></span>

- <span data-ttu-id="a98de-117">キャッシュを初期化する。</span><span class="sxs-lookup"><span data-stu-id="a98de-117">Initializing a cache.</span></span>

- <span data-ttu-id="a98de-118">テキスト ファイルのコンテンツを含むキャッシュ エントリを追加する。</span><span class="sxs-lookup"><span data-stu-id="a98de-118">Adding a cache entry that contains the contents of a text file.</span></span>

- <span data-ttu-id="a98de-119">キャッシュ エントリの削除ポリシーを指定する。</span><span class="sxs-lookup"><span data-stu-id="a98de-119">Providing an eviction policy for the cache entry.</span></span>

- <span data-ttu-id="a98de-120">キャッシュされたファイルのパスを監視し、監視対象の項目に対する変更についてキャッシュ インスタンスに通知する。</span><span class="sxs-lookup"><span data-stu-id="a98de-120">Monitoring the path of the cached file and notifying the cache instance about changes to the monitored item.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a98de-121">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a98de-121">Prerequisites</span></span>
 <span data-ttu-id="a98de-122">このチュートリアルを完了するための要件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a98de-122">In order to complete this walkthrough, you will need:</span></span>

- <span data-ttu-id="a98de-123">Visual Studio 2010。</span><span class="sxs-lookup"><span data-stu-id="a98de-123">Visual Studio 2010.</span></span>

- <span data-ttu-id="a98de-124">少量のテキストを含むテキスト ファイル</span><span class="sxs-lookup"><span data-stu-id="a98de-124">A text file that contains a small amount of text.</span></span> <span data-ttu-id="a98de-125">(テキスト ファイルのコンテンツをメッセージ ボックスに表示します)。このチュートリアルで示すコードは、次のファイルで作業していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="a98de-125">(You will display the contents of the text file in a message box.) The code illustrated in the walkthrough assumes that you are working with the following file:</span></span>

     `c:\cache\cacheText.txt`

     <span data-ttu-id="a98de-126">ただし、任意のテキスト ファイルを使用して、このチュートリアルのコードに小さな変更を加えることができます。</span><span class="sxs-lookup"><span data-stu-id="a98de-126">However, you can use any text file and make small changes to the code in this walkthrough.</span></span>

## <a name="creating-a-wpf-application-project"></a><span data-ttu-id="a98de-127">WPF アプリケーション プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="a98de-127">Creating a WPF Application Project</span></span>
 <span data-ttu-id="a98de-128">まず、WPF アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="a98de-128">You will start by creating a WPF application project.</span></span>

#### <a name="to-create-a-wpf-application"></a><span data-ttu-id="a98de-129">WPF アプリケーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="a98de-129">To create a WPF application</span></span>

1. <span data-ttu-id="a98de-130">Visual Studio を起動します。</span><span class="sxs-lookup"><span data-stu-id="a98de-130">Start Visual Studio.</span></span>

2. <span data-ttu-id="a98de-131">**[ファイル]** メニューの **[新規作成]** をポイントし、 **[新しいプロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a98de-131">In the **File** menu, click **New**, and then click **New Project**.</span></span>

     <span data-ttu-id="a98de-132">**[新しいプロジェクト]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a98de-132">The **New Project** dialog box is displayed.</span></span>

3. <span data-ttu-id="a98de-133">**[インストール済みのテンプレート]** で使用するプログラミング言語を選択します ( **[Visual Basic]** または **[Visual C#]** )。</span><span class="sxs-lookup"><span data-stu-id="a98de-133">Under **Installed Templates**, select the programming language you want to use (**Visual Basic** or **Visual C#**).</span></span>

4. <span data-ttu-id="a98de-134">**[新しいプロジェクト]** ダイアログ ボックスで **[WPF アプリケーション]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a98de-134">In the **New Project** dialog box, select **WPF Application**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a98de-135">**WPF アプリケーション** テンプレートが表示されない場合は、WPF をサポートする .NET Framework のバージョンをターゲットにしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a98de-135">If you do not see the **WPF Application** template, make sure that you are targeting a version of the .NET Framework that supports WPF.</span></span> <span data-ttu-id="a98de-136">**[新しいプロジェクト]** ダイアログ ボックスで、一覧から [.NET Framework 4] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a98de-136">In the **New Project** dialog box, select .NET Framework 4 from the list.</span></span>

5. <span data-ttu-id="a98de-137">**[プロジェクト名]** テキスト ボックスにプロジェクトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a98de-137">In the **Name** text box, enter a name for your project.</span></span> <span data-ttu-id="a98de-138">たとえば、「**WPFCaching**」と入力できます。</span><span class="sxs-lookup"><span data-stu-id="a98de-138">For example, you can enter **WPFCaching**.</span></span>

6. <span data-ttu-id="a98de-139">**[ソリューションのディレクトリを作成]** チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="a98de-139">Select the **Create directory for solution** check box.</span></span>

7. <span data-ttu-id="a98de-140">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a98de-140">Click **OK**.</span></span>

     <span data-ttu-id="a98de-141">WPF デザイナーが **[デザイン]** ビューで開き、MainWindow.xaml ファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a98de-141">The WPF Designer opens in **Design** view and displays the MainWindow.xaml file.</span></span> <span data-ttu-id="a98de-142">Visual Studio によって **マイ プロジェクト** フォルダー、Application.xaml ファイル、および MainWindow.xaml ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="a98de-142">Visual Studio creates the **My Project** folder, the Application.xaml file, and the MainWindow.xaml file.</span></span>

## <a name="targeting-the-net-framework-and-adding-a-reference-to-the-caching-assemblies"></a><span data-ttu-id="a98de-143">.NET Framework のターゲット設定とキャッシュ アセンブリへの参照の追加</span><span class="sxs-lookup"><span data-stu-id="a98de-143">Targeting the .NET Framework and Adding a Reference to the Caching Assemblies</span></span>
 <span data-ttu-id="a98de-144">既定で、WPF アプリケーションでは .NET Framework 4 クライアント プロファイルをターゲットとしています。</span><span class="sxs-lookup"><span data-stu-id="a98de-144">By default, WPF applications target the .NET Framework 4 Client Profile.</span></span> <span data-ttu-id="a98de-145">WPF アプリケーションで <xref:System.Runtime.Caching> 名前空間を使用するには、アプリケーションで (.NET Framework 4 クライアント プロファイルではなく).NET Framework 4 をターゲットとし、名前空間への参照を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="a98de-145">To use the <xref:System.Runtime.Caching> namespace in a WPF application, the application must target the .NET Framework 4 (not the .NET Framework 4 Client Profile) and must include a reference to the namespace.</span></span>

 <span data-ttu-id="a98de-146">そのため、次の手順は、.NET Framework のターゲットを変更し、<xref:System.Runtime.Caching> 名前空間への参照を追加することです。</span><span class="sxs-lookup"><span data-stu-id="a98de-146">Therefore, the next step is to change the .NET Framework target and add a reference to the <xref:System.Runtime.Caching> namespace.</span></span>

> [!NOTE]
> <span data-ttu-id="a98de-147">.NET Framework のターゲットを変更する手順は、Visual Basic プロジェクトと Visual C# プロジェクトとで異なります。</span><span class="sxs-lookup"><span data-stu-id="a98de-147">The procedure for changing the .NET Framework target is different in a Visual Basic project and in a Visual C# project.</span></span>

#### <a name="to-change-the-target-net-framework-in-visual-basic"></a><span data-ttu-id="a98de-148">Visual Basic でターゲットの .NET Framework を変更するには</span><span class="sxs-lookup"><span data-stu-id="a98de-148">To change the target .NET Framework in Visual Basic</span></span>

1. <span data-ttu-id="a98de-149">**ソリューション エクスプローラー** で、プロジェクト名を右クリックし、 **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a98de-149">In **Solutions Explorer**, right-click the project name, and then click **Properties**.</span></span>

     <span data-ttu-id="a98de-150">アプリケーションの [プロパティ] ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a98de-150">The properties window for the application is displayed.</span></span>

2. <span data-ttu-id="a98de-151">**[コンパイル]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a98de-151">Click the **Compile** tab.</span></span>

3. <span data-ttu-id="a98de-152">ウィンドウの下部にある **[詳細コンパイル オプション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a98de-152">At the bottom of the window, click **Advanced Compile Options…**.</span></span>

     <span data-ttu-id="a98de-153">**[コンパイラの詳細設定]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a98de-153">The **Advanced Compiler Settings** dialog box is displayed.</span></span>

4. <span data-ttu-id="a98de-154">**[ターゲット フレームワーク (すべての構成)]** 一覧で [.NET Framework 4] を選択します</span><span class="sxs-lookup"><span data-stu-id="a98de-154">In the **Target framework (all configurations)** list, select .NET Framework 4.</span></span> <span data-ttu-id="a98de-155">([.NET Framework 4 Client Profile] は選択しないでください)。</span><span class="sxs-lookup"><span data-stu-id="a98de-155">(Do not select .NET Framework 4 Client Profile.)</span></span>

5. <span data-ttu-id="a98de-156">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a98de-156">Click **OK**.</span></span>

     <span data-ttu-id="a98de-157">**[ターゲット フレームワークの変更]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a98de-157">The **Target Framework Change** dialog box is displayed.</span></span>

6. <span data-ttu-id="a98de-158">**[ターゲット フレームワークの変更]** ダイアログ ボックスで **[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a98de-158">In the **Target Framework Change** dialog box, click **Yes**.</span></span>

     <span data-ttu-id="a98de-159">プロジェクトが閉じられ、再び開かれます。</span><span class="sxs-lookup"><span data-stu-id="a98de-159">The project is closed and is then reopened.</span></span>

7. <span data-ttu-id="a98de-160">次の手順に従って、キャッシュ アセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="a98de-160">Add a reference to the caching assembly by following these steps:</span></span>

    1. <span data-ttu-id="a98de-161">**ソリューション エクスプローラー** で、プロジェクトの名前を右クリックし、 **[参照の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a98de-161">In **Solution Explorer**, right-click the name of the project and then click **Add Reference**.</span></span>

    2. <span data-ttu-id="a98de-162">**[.NET]** タブを選択し、`System.Runtime.Caching` を選択し、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a98de-162">Select the **.NET** tab, select `System.Runtime.Caching`, and then click **OK**.</span></span>

#### <a name="to-change-the-target-net-framework-in-a-visual-c-project"></a><span data-ttu-id="a98de-163">Visual C# プロジェクトでターゲットの .NET Framework を変更するには</span><span class="sxs-lookup"><span data-stu-id="a98de-163">To change the target .NET Framework in a Visual C# project</span></span>

1. <span data-ttu-id="a98de-164">**ソリューション エクスプローラー** でプロジェクト名を右クリックし、 **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a98de-164">In **Solution Explorer**, right-click the project name and then click **Properties**.</span></span>

     <span data-ttu-id="a98de-165">アプリケーションの [プロパティ] ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a98de-165">The properties window for the application is displayed.</span></span>

2. <span data-ttu-id="a98de-166">**[アプリケーション]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a98de-166">Click the **Application** tab.</span></span>

3. <span data-ttu-id="a98de-167">**[ターゲット フレームワーク]** 一覧で [.NET Framework 4] を選択します</span><span class="sxs-lookup"><span data-stu-id="a98de-167">In the **Target framework** list, select .NET Framework 4.</span></span> <span data-ttu-id="a98de-168">( **[.NET Framework 4 Client Profile]** は選択しないでください)。</span><span class="sxs-lookup"><span data-stu-id="a98de-168">(Do not select **.NET Framework 4 Client Profile**.)</span></span>

4. <span data-ttu-id="a98de-169">次の手順に従って、キャッシュ アセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="a98de-169">Add a reference to the caching assembly by following these steps:</span></span>

    1. <span data-ttu-id="a98de-170">**[参照]** フォルダーを右クリックし、 **[参照の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a98de-170">Right-click the **References** folder and then click **Add Reference**.</span></span>

    2. <span data-ttu-id="a98de-171">**[.NET]** タブを選択し、`System.Runtime.Caching` を選択し、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a98de-171">Select the **.NET** tab, select `System.Runtime.Caching`, and then click **OK**.</span></span>

## <a name="adding-a-button-to-the-wpf-window"></a><span data-ttu-id="a98de-172">WPF ウィンドウへのボタンの追加</span><span class="sxs-lookup"><span data-stu-id="a98de-172">Adding a Button to the WPF Window</span></span>
 <span data-ttu-id="a98de-173">次に、ボタン コントロールを追加し、ボタンの `Click` イベントのイベント ハンドラーを作成します。</span><span class="sxs-lookup"><span data-stu-id="a98de-173">Next, you will add a button control and create an event handler for the button's `Click` event.</span></span> <span data-ttu-id="a98de-174">後でコードを追加して、ボタンをクリックするとテキスト ファイルのコンテンツがキャッシュされ、表示されるようにします。</span><span class="sxs-lookup"><span data-stu-id="a98de-174">Later you will add code to so when you click the button, the contents of the text file are cached and displayed.</span></span>

#### <a name="to-add-a-button-control"></a><span data-ttu-id="a98de-175">ボタン コントロールを追加するには</span><span class="sxs-lookup"><span data-stu-id="a98de-175">To add a button control</span></span>

1. <span data-ttu-id="a98de-176">**ソリューション エクスプローラー** で MainWindow.xaml ファイルをダブルクリックして開きます。</span><span class="sxs-lookup"><span data-stu-id="a98de-176">In **Solution Explorer**, double-click the MainWindow.xaml file to open it.</span></span>

2. <span data-ttu-id="a98de-177">**[ツールボックス]** の **[コモン WPF コントロール]** で、`Button` コントロールを `MainWindow` ウィンドウにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="a98de-177">From the **Toolbox**, under **Common WPF Controls**, drag a `Button` control to the `MainWindow` window.</span></span>

3. <span data-ttu-id="a98de-178">**[プロパティ]** ウィンドウで、`Button` コントロールの `Content` プロパティを **[Get Cache]\(キャッシュの取得\)** に設定します。</span><span class="sxs-lookup"><span data-stu-id="a98de-178">In the **Properties** window, set the `Content` property of the `Button` control to **Get Cache**.</span></span>

## <a name="initializing-the-cache-and-caching-an-entry"></a><span data-ttu-id="a98de-179">キャッシュの初期化とエントリのキャッシュ</span><span class="sxs-lookup"><span data-stu-id="a98de-179">Initializing the Cache and Caching an Entry</span></span>
 <span data-ttu-id="a98de-180">次に、次のタスクを実行するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="a98de-180">Next, you will add the code to perform the following tasks:</span></span>

- <span data-ttu-id="a98de-181">キャッシュ クラスのインスタンスを作成します。つまり、新しい <xref:System.Runtime.Caching.MemoryCache> オブジェクトをインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="a98de-181">Create an instance of the cache class—that is, you will instantiate a new <xref:System.Runtime.Caching.MemoryCache> object.</span></span>

- <span data-ttu-id="a98de-182">キャッシュで <xref:System.Runtime.Caching.HostFileChangeMonitor> オブジェクトを使用してテキスト ファイルの変更を監視するように指定します。</span><span class="sxs-lookup"><span data-stu-id="a98de-182">Specify that the cache uses a <xref:System.Runtime.Caching.HostFileChangeMonitor> object to monitor changes in the text file.</span></span>

- <span data-ttu-id="a98de-183">テキスト ファイルを読み取り、そのコンテンツをキャッシュ エントリとしてキャッシュします。</span><span class="sxs-lookup"><span data-stu-id="a98de-183">Read the text file and cache its contents as a cache entry.</span></span>

- <span data-ttu-id="a98de-184">キャッシュされたテキスト ファイルのコンテンツを表示します。</span><span class="sxs-lookup"><span data-stu-id="a98de-184">Display the contents of the cached text file.</span></span>

#### <a name="to-create-the-cache-object"></a><span data-ttu-id="a98de-185">キャッシュ オブジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="a98de-185">To create the cache object</span></span>

1. <span data-ttu-id="a98de-186">MainWindow.xaml.cs ファイルまたは MainWindow.Xaml.vb ファイルにイベント ハンドラーを作成するために、追加したボタンをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="a98de-186">Double-click the button you just added in order to create an event handler in the MainWindow.xaml.cs or MainWindow.Xaml.vb file.</span></span>

2. <span data-ttu-id="a98de-187">ファイルの先頭 (クラス宣言の前) に、次の `Imports` (Visual Basic) または `using` (C#) ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="a98de-187">At the top of the file (before the class declaration), add the following `Imports` (Visual Basic) or `using` (C#) statements:</span></span>

    ```csharp
    using System.Runtime.Caching;
    using System.IO;
    ```

    ```vb
    Imports System.Runtime.Caching
    Imports System.IO
    ```

3. <span data-ttu-id="a98de-188">イベント ハンドラーで、次のコードを追加してキャッシュ オブジェクトをインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="a98de-188">In the event handler, add the following code to instantiate the cache object:</span></span>

    ```csharp
    ObjectCache cache = MemoryCache.Default;
    ```

    ```vb
    Dim cache As ObjectCache = MemoryCache.Default
    ```

     <span data-ttu-id="a98de-189"><xref:System.Runtime.Caching.ObjectCache> クラスは、メモリ内オブジェクト キャッシュを提供する組み込みクラスです。</span><span class="sxs-lookup"><span data-stu-id="a98de-189">The <xref:System.Runtime.Caching.ObjectCache> class is a built-in class that provides an in-memory object cache.</span></span>

4. <span data-ttu-id="a98de-190">次のコードを追加して、`filecontents` というキャッシュ エントリのコンテンツを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="a98de-190">Add the following code to read the contents of a cache entry named `filecontents`:</span></span>

    ```vb
    Dim fileContents As String = TryCast(cache("filecontents"), String)
    ```

    ```csharp
    string fileContents = cache["filecontents"] as string;
    ```

5. <span data-ttu-id="a98de-191">次のコードを追加して、`filecontents` というキャッシュ エントリが存在するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="a98de-191">Add the following code to check whether the cache entry named `filecontents` exists:</span></span>

    ```vb
    If fileContents Is Nothing Then

    End If
    ```

    ```csharp
    if (fileContents == null)
    {

    }
    ```

     <span data-ttu-id="a98de-192">指定したキャッシュ エントリが存在しない場合は、テキスト ファイルを読み取り、それをキャッシュ エントリとしてキャッシュに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a98de-192">If the specified cache entry does not exist, you must read the text file and add it as a cache entry to the cache.</span></span>

6. <span data-ttu-id="a98de-193">`if/then` ブロックで、次のコードを追加して、キャッシュ エントリが 10 秒後に期限切れになることを指定する新しい <xref:System.Runtime.Caching.CacheItemPolicy> オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="a98de-193">In the `if/then` block, add the following code to create a new <xref:System.Runtime.Caching.CacheItemPolicy> object that specifies that the cache entry expires after 10 seconds.</span></span>

    ```vb
    Dim policy As New CacheItemPolicy()
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0)
    ```

    ```csharp
    CacheItemPolicy policy = new CacheItemPolicy();
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0);
    ```

     <span data-ttu-id="a98de-194">削除または有効期限の情報が提供されていない場合、既定値は <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration> です。これは、キャッシュ エントリが絶対時間のみに基づいて期限切れになることはないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="a98de-194">If no eviction or expiration information is provided, the default is <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>, which means the cache entries never expire based only on an absolute time.</span></span> <span data-ttu-id="a98de-195">代わりに、メモリが不足している場合にのみ、キャッシュ エントリが期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="a98de-195">Instead, cache entries expire only when there is memory pressure.</span></span> <span data-ttu-id="a98de-196">ベスト プラクティスとして、絶対またはスライド式の有効期限を常に明示的に指定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a98de-196">As a best practice, you should always explicitly provide either an absolute or a sliding expiration.</span></span>

7. <span data-ttu-id="a98de-197">`if/then` ブロック内で、前の手順で追加したコードの後に、次のコードを追加し、監視するファイル パスのコレクションを作成し、テキスト ファイルのパスをコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="a98de-197">Inside the `if/then` block and following the code you added in the previous step, add the following code to create a collection for the file paths that you want to monitor, and to add the path of the text file to the collection:</span></span>

    ```vb
    Dim filePaths As New List(Of String)()
    filePaths.Add("c:\cache\cacheText.txt")
    ```

    ```csharp
    List<string> filePaths = new List<string>();
    filePaths.Add("c:\\cache\\cacheText.txt");
    ```

    > [!NOTE]
    > <span data-ttu-id="a98de-198">使用するテキスト ファイルが `c:\cache\cacheText.txt` でない場合は、使用するテキスト ファイルのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="a98de-198">If the text file you want to use is not `c:\cache\cacheText.txt`, specify the path where the text file is that you want to use.</span></span>

8. <span data-ttu-id="a98de-199">前の手順で追加したコードの後に、次のコードを追加し、新しい <xref:System.Runtime.Caching.HostFileChangeMonitor> オブジェクトをキャッシュ エントリの変更モニターのコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="a98de-199">Following the code that you added in the previous step, add the following code to add a new <xref:System.Runtime.Caching.HostFileChangeMonitor> object to the collection of change monitors for the cache entry:</span></span>

    ```vb
    policy.ChangeMonitors.Add(New HostFileChangeMonitor(filePaths))
    ```

    ```csharp
    policy.ChangeMonitors.Add(new HostFileChangeMonitor(filePaths));
    ```

     <span data-ttu-id="a98de-200"><xref:System.Runtime.Caching.HostFileChangeMonitor> オブジェクトを使用すると、テキスト ファイルのパスを監視し、変更が発生した場合はキャッシュに通知することができます。</span><span class="sxs-lookup"><span data-stu-id="a98de-200">The <xref:System.Runtime.Caching.HostFileChangeMonitor> object monitors the text file's path and notifies the cache if changes occur.</span></span> <span data-ttu-id="a98de-201">この例では、ファイルのコンテンツが変更されると、キャッシュ エントリが期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="a98de-201">In this example, the cache entry will expire if the content of the file changes.</span></span>

9. <span data-ttu-id="a98de-202">前の手順で追加したコードの後に次のコードを追加し、テキスト ファイルのコンテンツを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="a98de-202">Following the code that you added in the previous step, add the following code to read the contents of the text file:</span></span>

    ```vb
    fileContents = File.ReadAllText("c:\cache\cacheText.txt") & vbCrLf & DateTime.Now.ToString()
    ```

    ```csharp
    fileContents = File.ReadAllText("c:\\cache\\cacheText.txt") + "\n" + DateTime.Now;
    ```

     <span data-ttu-id="a98de-203">日付と時刻のタイムスタンプが追加されるので、キャッシュ エントリの有効期限がいつ切れるかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="a98de-203">The date and time timestamp is added so that you will be able to see when the cache entry expires.</span></span>

10. <span data-ttu-id="a98de-204">前の手順で追加したコードの後に次のコードを追加し、ファイルのコンテンツを <xref:System.Runtime.Caching.CacheItem> インスタンスとしてキャッシュ オブジェクトに挿入します。</span><span class="sxs-lookup"><span data-stu-id="a98de-204">Following the code that you added in the previous step, add the following code to insert the contents of the file into the cache object as a <xref:System.Runtime.Caching.CacheItem> instance:</span></span>

    ```vb
    cache.Set("filecontents", fileContents, policy)
    ```

    ```csharp
    cache.Set("filecontents", fileContents, policy);
    ```

     <span data-ttu-id="a98de-205">前の手順で作成した <xref:System.Runtime.Caching.CacheItemPolicy> オブジェクトをパラメーターとして渡すことにより、キャッシュ エントリを削除する方法に関する情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="a98de-205">You specify information about how the cache entry should be evicted by passing the <xref:System.Runtime.Caching.CacheItemPolicy> object that you created earlier as a parameter.</span></span>

11. <span data-ttu-id="a98de-206">`if/then` ブロックの後に次のコードを追加し、キャッシュされたファイルのコンテンツをメッセージ ボックスに表示します。</span><span class="sxs-lookup"><span data-stu-id="a98de-206">After the `if/then` block, add the following code to display the cached file content in a message box:</span></span>

    ```vb
    MessageBox.Show(fileContents)
    ```

    ```csharp
    MessageBox.Show(fileContents);
    ```

12. <span data-ttu-id="a98de-207">**[ビルド]** メニューで、 **[WPFCaching のビルド]** をクリックしてプロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="a98de-207">In the **Build** menu, click **Build WPFCaching** to build your project.</span></span>

## <a name="testing-caching-in-the-wpf-application"></a><span data-ttu-id="a98de-208">WPF アプリケーションでのキャッシュのテスト</span><span class="sxs-lookup"><span data-stu-id="a98de-208">Testing Caching in the WPF Application</span></span>
 <span data-ttu-id="a98de-209">これで、アプリケーションをテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="a98de-209">You can now test the application.</span></span>

#### <a name="to-test-caching-in-the-wpf-application"></a><span data-ttu-id="a98de-210">WPF アプリケーションでキャッシュをテストするには</span><span class="sxs-lookup"><span data-stu-id="a98de-210">To test caching in the WPF application</span></span>

1. <span data-ttu-id="a98de-211">Ctrl キーを押しながら F5 キーを押してアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="a98de-211">Press CTRL+F5 to run the application.</span></span>

     <span data-ttu-id="a98de-212">`MainWindow`  ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a98de-212">The `MainWindow` window is displayed.</span></span>

2. <span data-ttu-id="a98de-213">**[Get Cache]\(キャッシュの取得\)** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a98de-213">Click **Get Cache**.</span></span>

     <span data-ttu-id="a98de-214">テキスト ファイルからキャッシュされたコンテンツがメッセージ ボックスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a98de-214">The cached content from the text file is displayed in a message box.</span></span> <span data-ttu-id="a98de-215">ファイルのタイムスタンプに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a98de-215">Notice the timestamp on the file.</span></span>

3. <span data-ttu-id="a98de-216">メッセージ ボックスを閉じ、 **[Get Cache]\(キャッシュの取得\)** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a98de-216">Close the message box and then click **Get Cache** again.</span></span>

     <span data-ttu-id="a98de-217">タイムスタンプは変更されません。</span><span class="sxs-lookup"><span data-stu-id="a98de-217">The timestamp is unchanged.</span></span> <span data-ttu-id="a98de-218">これは、キャッシュされたコンテンツが表示されることを示します。</span><span class="sxs-lookup"><span data-stu-id="a98de-218">This indicates the cached content is displayed.</span></span>

4. <span data-ttu-id="a98de-219">10 秒以上待ってから、 **[Get Cache]\(キャッシュの取得\)** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a98de-219">Wait 10 seconds or more and then click **Get Cache** again.</span></span>

     <span data-ttu-id="a98de-220">今回は、新しいタイムスタンプが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a98de-220">This time a new timestamp is displayed.</span></span> <span data-ttu-id="a98de-221">これは、ポリシーによってキャッシュ エントリの有効期限が切れ、新しいキャッシュされたコンテンツが表示されることを示しています。</span><span class="sxs-lookup"><span data-stu-id="a98de-221">This indicates that the policy let the cache entry expire and that new cached content is displayed.</span></span>

5. <span data-ttu-id="a98de-222">テキスト エディターで、作成したテキスト ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a98de-222">In a text editor, open the text file that you created.</span></span> <span data-ttu-id="a98de-223">まだ変更を加えないでください。</span><span class="sxs-lookup"><span data-stu-id="a98de-223">Do not make any changes yet.</span></span>

6. <span data-ttu-id="a98de-224">メッセージ ボックスを閉じ、 **[Get Cache]\(キャッシュの取得\)** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a98de-224">Close the message box and then click **Get Cache** again.</span></span>

     <span data-ttu-id="a98de-225">タイムスタンプに再び注目してください。</span><span class="sxs-lookup"><span data-stu-id="a98de-225">Notice the timestamp again.</span></span>

7. <span data-ttu-id="a98de-226">テキスト ファイルに変更を加え、ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="a98de-226">Make a change to the text file and then save the file.</span></span>

8. <span data-ttu-id="a98de-227">メッセージ ボックスを閉じ、 **[Get Cache]\(キャッシュの取得\)** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a98de-227">Close the message box and then click **Get Cache** again.</span></span>

     <span data-ttu-id="a98de-228">このメッセージ ボックスには、テキスト ファイルの更新されたコンテンツと新しいタイムスタンプが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a98de-228">This message box contains the updated content from the text file and a new timestamp.</span></span> <span data-ttu-id="a98de-229">これは、絶対タイムアウト期間が経過していなくても、ファイルを変更した直後にホスト ファイル変更モニターによってキャッシュ エントリが削除されたことを示しています。</span><span class="sxs-lookup"><span data-stu-id="a98de-229">This indicates that the host-file change monitor evicted the cache entry immediately when you changed the file, even though the absolute timeout period had not expired.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a98de-230">削除時間を 20 秒以上に増やして、ファイルに変更を加える時間を増やすことができます。</span><span class="sxs-lookup"><span data-stu-id="a98de-230">You can increase the eviction time to 20 seconds or more to allow more time for you to make a change in the file.</span></span>

## <a name="code-example"></a><span data-ttu-id="a98de-231">コード例</span><span class="sxs-lookup"><span data-stu-id="a98de-231">Code Example</span></span>
 <span data-ttu-id="a98de-232">このチュートリアルを完了すると、作成したプロジェクトのコードは次の例のようになります。</span><span class="sxs-lookup"><span data-stu-id="a98de-232">After you have completed this walkthrough, the code for the project you created will resemble the following example.</span></span>

 [!code-csharp[CachingWPFApplications#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CachingWPFApplications/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[CachingWPFApplications#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CachingWPFApplications/VisualBasic/MainWindow.xaml.vb#1)]

## <a name="see-also"></a><span data-ttu-id="a98de-233">関連項目</span><span class="sxs-lookup"><span data-stu-id="a98de-233">See also</span></span>

- <xref:System.Runtime.Caching.MemoryCache>
- <xref:System.Runtime.Caching.ObjectCache>
- <xref:System.Runtime.Caching>
- [<span data-ttu-id="a98de-234">.NET Framework アプリケーションでのキャッシュ</span><span class="sxs-lookup"><span data-stu-id="a98de-234">Caching in .NET Framework Applications</span></span>](/dotnet/framework/performance/caching-in-net-framework-applications)
