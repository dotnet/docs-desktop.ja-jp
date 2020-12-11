---
title: Visual Studio 2019 で最初の WPF アプリを作成する - .NET Framework
titleSuffix: ''
description: ほとんどの WPF アプリケーションに共通する要素を含む、Windows Presentation Foundation (WPF) デスクトップ アプリケーションを開発します。
ms.date: 09/06/2019
ms.topic: tutorial
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting started [WPF], WPF
- WPF [WPF], getting started
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
ms.custom: mvc,vs-dotnet
ms.openlocfilehash: 4954e76d2df3ad15466b4d81aa1f92346d465505
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974478"
---
# <a name="tutorial-create-your-first-wpf-application-in-visual-studio-2019"></a><span data-ttu-id="8095d-103">チュートリアル: Visual Studio 2019 で最初の WPF アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="8095d-103">Tutorial: Create your first WPF application in Visual Studio 2019</span></span>

<span data-ttu-id="8095d-104">この記事では、ほとんどの WPF アプリケーションに共通する次の要素が含まれる Windows Presentation Foundation (WPF) デスクトップ アプリケーションを開発する方法について説明します: Extensible Application Markup Language (XAML) マークアップ、コードビハインド、アプリケーション定義、コントロール、レイアウト、データ バインディング、スタイル。</span><span class="sxs-lookup"><span data-stu-id="8095d-104">This article shows you how to develop a Windows Presentation Foundation (WPF) desktop application that includes the elements that are common to most WPF applications: Extensible Application Markup Language (XAML) markup, code-behind, application definitions, controls, layout, data binding, and styles.</span></span> <span data-ttu-id="8095d-105">アプリケーションを開発するには、Visual Studio を使用します。</span><span class="sxs-lookup"><span data-stu-id="8095d-105">To develop the application, you'll use Visual Studio.</span></span>

<span data-ttu-id="8095d-106">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8095d-106">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="8095d-107">WPF プロジェクトを作成する。</span><span class="sxs-lookup"><span data-stu-id="8095d-107">Create a WPF project.</span></span>
> - <span data-ttu-id="8095d-108">XAML を使用して、アプリケーションのユーザー インターフェイス (UI) の外観をデザインする。</span><span class="sxs-lookup"><span data-stu-id="8095d-108">Use XAML to design the appearance of the application's user interface (UI).</span></span>
> - <span data-ttu-id="8095d-109">アプリケーションの動作を構築するコードを記述する。</span><span class="sxs-lookup"><span data-stu-id="8095d-109">Write code to build the application's behavior.</span></span>
> - <span data-ttu-id="8095d-110">アプリケーションを管理するためのアプリケーション定義を作成する。</span><span class="sxs-lookup"><span data-stu-id="8095d-110">Create an application definition to manage the application.</span></span>
> - <span data-ttu-id="8095d-111">コントロールを追加し、レイアウトを作成して、アプリケーションの UI を構成する。</span><span class="sxs-lookup"><span data-stu-id="8095d-111">Add controls and create the layout to compose the application UI.</span></span>
> - <span data-ttu-id="8095d-112">アプリケーションの UI 全体に一貫性のある外観を持たせるためのスタイルを作成する。</span><span class="sxs-lookup"><span data-stu-id="8095d-112">Create styles for a consistent appearance throughout the application's UI.</span></span>
> - <span data-ttu-id="8095d-113">UI にデータを設定し、データと UI の同期を保つために、UI をデータにバインドする。</span><span class="sxs-lookup"><span data-stu-id="8095d-113">Bind the UI to data, both to populate the UI from data and to keep the data and UI synchronized.</span></span>

<span data-ttu-id="8095d-114">このチュートリアルの最後には、ユーザーが選択した個人の経費報告書を表示できる、スタンドアロンの Windows アプリケーションが完成します。</span><span class="sxs-lookup"><span data-stu-id="8095d-114">By the end of the tutorial, you'll have built a standalone Windows application that allows users to view expense reports for selected people.</span></span> <span data-ttu-id="8095d-115">このアプリケーションは、ブラウザー スタイルのウィンドウでホストされる、複数の WPF ページから構成されます。</span><span class="sxs-lookup"><span data-stu-id="8095d-115">The application is composed of several WPF pages that are hosted in a browser-style window.</span></span>

> [!TIP]
> <span data-ttu-id="8095d-116">このチュートリアルで使用するサンプル コードには Visual Basic 版と C# 版があり、[WPF アプリ チュートリアルのサンプル コード](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp)で入手できます。</span><span class="sxs-lookup"><span data-stu-id="8095d-116">The sample code that is used in this tutorial is available for both Visual Basic and C# at [Tutorial WPF App Sample Code](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span></span>
>
> <span data-ttu-id="8095d-117">このページの先頭にある言語セレクターを使用して、サンプル コードのコード言語を C# と Visual Basic の間で切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="8095d-117">You can toggle the code language of the sample code between C# and Visual Basic by using the language selector on top of this page.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8095d-118">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="8095d-118">Prerequisites</span></span>

- <span data-ttu-id="8095d-119">**.NET デスクトップ開発** ワークロードがインストールされた [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)。</span><span class="sxs-lookup"><span data-stu-id="8095d-119">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET desktop development** workload installed.</span></span>

   <span data-ttu-id="8095d-120">Visual Studio の最新バージョンのインストールの詳細については、「[Visual Studio のインストール](/visualstudio/install/install-visual-studio)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8095d-120">For more information about installing the latest version of Visual Studio, see [Install Visual Studio](/visualstudio/install/install-visual-studio).</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="8095d-121">アプリケーション プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="8095d-121">Create the application project</span></span>

<span data-ttu-id="8095d-122">最初のステップでは、アプリケーション定義、2 つのページ、および 1 つの画像が含まれる、アプリケーション インフラストラクチャを作成します。</span><span class="sxs-lookup"><span data-stu-id="8095d-122">The first step is to create the application infrastructure, which includes an application definition, two pages, and an image.</span></span>

1. <span data-ttu-id="8095d-123">**`ExpenseIt`** という名前の新しい WPF アプリケーション プロジェクトを Visual Basic または Visual C# で作成します。</span><span class="sxs-lookup"><span data-stu-id="8095d-123">Create a new WPF Application project in Visual Basic or Visual C# named **`ExpenseIt`**:</span></span>

   1. <span data-ttu-id="8095d-124">Visual Studio を開き、 **[作業の開始]** メニューの **[新しいプロジェクトの作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8095d-124">Open Visual Studio and select **Create a new project** under the **Get started** menu.</span></span>

      <span data-ttu-id="8095d-125">**[新しいプロジェクトの作成]** ダイアログが開きます。</span><span class="sxs-lookup"><span data-stu-id="8095d-125">The **Create a new project** dialog opens.</span></span>

   2. <span data-ttu-id="8095d-126">**[言語]** ドロップダウンで、 **[C#]** または **[Visual Basic]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8095d-126">In the **Language** dropdown, select either **C#** or **Visual Basic**.</span></span>

   3. <span data-ttu-id="8095d-127">**[WPF アプリ (.NET Framework)]** テンプレートを選択し、 **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8095d-127">Select the **WPF App (.NET Framework)** template and then select **Next**.</span></span>

      ![[新しいプロジェクトの作成] ダイアログ](./media/walkthrough-my-first-wpf-desktop-application/create-new-project-dialog.png)

      <span data-ttu-id="8095d-129">**[新しいプロジェクトを構成します]** ダイアログが開きます。</span><span class="sxs-lookup"><span data-stu-id="8095d-129">The **Configure your new project** dialog opens.</span></span>

   4. <span data-ttu-id="8095d-130">プロジェクトの名前に「 **`ExpenseIt`** 」と入力して、 **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8095d-130">Enter the project name **`ExpenseIt`** and then select **Create**.</span></span>

      ![[新しいプロジェクトを構成します] ダイアログ](./media/walkthrough-my-first-wpf-desktop-application/configure-new-project-dialog.png)

      <span data-ttu-id="8095d-132">Visual Studio によってプロジェクトが作成され、デザイナーで **MainWindow.xaml** という名前の既定のアプリケーション ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="8095d-132">Visual Studio creates the project and opens the designer for the default application window named **MainWindow.xaml**.</span></span>

2. <span data-ttu-id="8095d-133">*Application.xaml* (Visual Basic) または *App.xaml* (C#) を開きます。</span><span class="sxs-lookup"><span data-stu-id="8095d-133">Open *Application.xaml* (Visual Basic) or *App.xaml* (C#).</span></span>

    <span data-ttu-id="8095d-134">この XAML ファイルでは、WPF アプリケーションとすべてのアプリケーション リソースを定義します。</span><span class="sxs-lookup"><span data-stu-id="8095d-134">This XAML file defines a WPF application and any application resources.</span></span> <span data-ttu-id="8095d-135">また、このファイルを使用して、アプリケーションの起動時に自動的に表示される UI (この例では *MainWindow.xaml*) も指定します。</span><span class="sxs-lookup"><span data-stu-id="8095d-135">You also use this file to specify the UI, in this case *MainWindow.xaml*, that automatically shows when the application starts.</span></span>

    <span data-ttu-id="8095d-136">XAML は、Visual Basic では次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8095d-136">Your XAML should look like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#1_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    <span data-ttu-id="8095d-137">C# では次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8095d-137">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. <span data-ttu-id="8095d-138">*MainWindow.xaml* を開きます。</span><span class="sxs-lookup"><span data-stu-id="8095d-138">Open *MainWindow.xaml*.</span></span>

    <span data-ttu-id="8095d-139">この XAML ファイルは、アプリケーションのメイン ウィンドウです。このファイルには、ページで作成されたコンテンツが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8095d-139">This XAML file is the main window of your application and displays content created in pages.</span></span> <span data-ttu-id="8095d-140"><xref:System.Windows.Window> クラスでは、ウィンドウのプロパティ (タイトル、サイズ、アイコンなど) が定義されており、イベント (ウィンドウを閉じたり非表示にしたりするなど) が処理されます。</span><span class="sxs-lookup"><span data-stu-id="8095d-140">The <xref:System.Windows.Window> class defines the properties of a window, such as its title, size, or icon, and handles events, such as closing or hiding.</span></span>

4. <span data-ttu-id="8095d-141">次の XAML で示されているように、<xref:System.Windows.Window> 要素を <xref:System.Windows.Navigation.NavigationWindow> に変更します。</span><span class="sxs-lookup"><span data-stu-id="8095d-141">Change the <xref:System.Windows.Window> element to a <xref:System.Windows.Navigation.NavigationWindow>, as shown in the following XAML:</span></span>

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   <span data-ttu-id="8095d-142">このアプリでは、ユーザーの入力に応じて画面がさまざまなコンテンツに移動します。</span><span class="sxs-lookup"><span data-stu-id="8095d-142">This app navigates to different content depending on the user input.</span></span> <span data-ttu-id="8095d-143">このため、メインの <xref:System.Windows.Window> を <xref:System.Windows.Navigation.NavigationWindow> に変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8095d-143">This is why the main <xref:System.Windows.Window> needs to be changed to a <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="8095d-144"><xref:System.Windows.Navigation.NavigationWindow> では、<xref:System.Windows.Window> のすべてのプロパティを継承します。</span><span class="sxs-lookup"><span data-stu-id="8095d-144"><xref:System.Windows.Navigation.NavigationWindow> inherits all the properties of <xref:System.Windows.Window>.</span></span> <span data-ttu-id="8095d-145">XAML ファイル内の <xref:System.Windows.Navigation.NavigationWindow> 要素では、<xref:System.Windows.Navigation.NavigationWindow> クラスのインスタンスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="8095d-145">The <xref:System.Windows.Navigation.NavigationWindow> element in the XAML file creates an instance of the <xref:System.Windows.Navigation.NavigationWindow> class.</span></span> <span data-ttu-id="8095d-146">詳しくは、「[ナビゲーションの概要](../app-development/navigation-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8095d-146">For more information, see [Navigation overview](../app-development/navigation-overview.md).</span></span>

5. <span data-ttu-id="8095d-147"><xref:System.Windows.Navigation.NavigationWindow> タグの間から <xref:System.Windows.Controls.Grid> 要素を削除します。</span><span class="sxs-lookup"><span data-stu-id="8095d-147">Remove the <xref:System.Windows.Controls.Grid> elements from between the <xref:System.Windows.Navigation.NavigationWindow> tags.</span></span>

6. <span data-ttu-id="8095d-148">XAML コードで、<xref:System.Windows.Navigation.NavigationWindow> 要素に対する次のプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="8095d-148">Change the following properties in the XAML code for the <xref:System.Windows.Navigation.NavigationWindow> element:</span></span>

    - <span data-ttu-id="8095d-149"><xref:System.Windows.Window.Title%2A> プロパティを "`ExpenseIt`" に設定します。</span><span class="sxs-lookup"><span data-stu-id="8095d-149">Set the <xref:System.Windows.Window.Title%2A> property to "`ExpenseIt`".</span></span>

    - <span data-ttu-id="8095d-150"><xref:System.Windows.FrameworkElement.Height%2A> プロパティを 350 ピクセルに設定します。</span><span class="sxs-lookup"><span data-stu-id="8095d-150">Set the <xref:System.Windows.FrameworkElement.Height%2A> property to 350 pixels.</span></span>

    - <span data-ttu-id="8095d-151"><xref:System.Windows.FrameworkElement.Width%2A> プロパティを 500 ピクセルに設定します。</span><span class="sxs-lookup"><span data-stu-id="8095d-151">Set the <xref:System.Windows.FrameworkElement.Width%2A> property to 500 pixels.</span></span>

    <span data-ttu-id="8095d-152">XAML は、Visual Basic では次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8095d-152">Your XAML should look like the following for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#2_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    <span data-ttu-id="8095d-153">C# では次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8095d-153">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

7. <span data-ttu-id="8095d-154">*MainWindow.xaml.vb* または *MainWindow.xaml.cs* を開きます。</span><span class="sxs-lookup"><span data-stu-id="8095d-154">Open *MainWindow.xaml.vb* or *MainWindow.xaml.cs*.</span></span>

    <span data-ttu-id="8095d-155">このファイルは、*MainWindow.xaml* で宣言されたイベントを処理するコードが含まれる分離コード ファイルです。</span><span class="sxs-lookup"><span data-stu-id="8095d-155">This file is a code-behind file that contains code to handle the events declared in *MainWindow.xaml*.</span></span> <span data-ttu-id="8095d-156">このファイルには、XAML で定義されたウィンドウの部分クラスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8095d-156">This file contains a partial class for the window defined in XAML.</span></span>

8. <span data-ttu-id="8095d-157">C# を使用している場合は、<xref:System.Windows.Navigation.NavigationWindow> から派生するように `MainWindow` クラスを変更します。</span><span class="sxs-lookup"><span data-stu-id="8095d-157">If you're using C#, change the `MainWindow` class to derive from <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="8095d-158">(Visual Basic では、XAML でウィンドウを変更すると自動的にこの処理が行われます)。これで、C# のコードは次のようになっているはずです。</span><span class="sxs-lookup"><span data-stu-id="8095d-158">(In Visual Basic, this happens automatically when you change the window in XAML.) Your C# code should now look like this:</span></span>

   [!code-csharp[ExpenseIt#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/MainWindow.xaml.cs?highlight=21)]

## <a name="add-files-to-the-application"></a><span data-ttu-id="8095d-159">ファイルをアプリケーションに追加する</span><span class="sxs-lookup"><span data-stu-id="8095d-159">Add files to the application</span></span>

<span data-ttu-id="8095d-160">このセクションでは、アプリケーションに 2 つのページと 1 つのイメージを追加します。</span><span class="sxs-lookup"><span data-stu-id="8095d-160">In this section, you'll add two pages and an image to the application.</span></span>

1. <span data-ttu-id="8095d-161">新しいページをプロジェクトに追加し、名前を *`ExpenseItHome.xaml`* に設定します。</span><span class="sxs-lookup"><span data-stu-id="8095d-161">Add a new page to the project, and name it *`ExpenseItHome.xaml`*:</span></span>

   1. <span data-ttu-id="8095d-162">**ソリューション エクスプローラー** で、 **`ExpenseIt`** プロジェクト ノードを右クリックして、 **[追加]**  >  **[ページ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8095d-162">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="8095d-163">**[新しい項目の追加]** ダイアログでは、 **[ページ (WPF)]** テンプレートが既に選択されています。</span><span class="sxs-lookup"><span data-stu-id="8095d-163">In the **Add New Item** dialog, the **Page (WPF)** template is already selected.</span></span> <span data-ttu-id="8095d-164">名前に「 **`ExpenseItHome`** 」と入力し、 **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8095d-164">Enter the name **`ExpenseItHome`**, and then select **Add**.</span></span>

    <span data-ttu-id="8095d-165">このページが、アプリケーションの起動時に表示される最初のページになります。</span><span class="sxs-lookup"><span data-stu-id="8095d-165">This page is the first page that's displayed when the application is launched.</span></span> <span data-ttu-id="8095d-166">経費報告書の表示対象として選択するユーザーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8095d-166">It will show a list of people to select from, to show an expense report for.</span></span>

1. <span data-ttu-id="8095d-167">*`ExpenseItHome.xaml`* を開きます。</span><span class="sxs-lookup"><span data-stu-id="8095d-167">Open *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="8095d-168"><xref:System.Windows.Controls.Page.Title%2A> を "`ExpenseIt - Home`" に設定します。</span><span class="sxs-lookup"><span data-stu-id="8095d-168">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - Home`".</span></span>

1. <span data-ttu-id="8095d-169">`DesignHeight` を 350 ピクセルに設定し、`DesignWidth` を 500 ピクセルに設定します。</span><span class="sxs-lookup"><span data-stu-id="8095d-169">Set the `DesignHeight` to 350 pixels and the `DesignWidth` to 500 pixels.</span></span>

    <span data-ttu-id="8095d-170">XAML は、Visual Basic では次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8095d-170">The XAML now appears as follows for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#6_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    <span data-ttu-id="8095d-171">C# では次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8095d-171">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

1. <span data-ttu-id="8095d-172">*MainWindow.xaml* を開きます。</span><span class="sxs-lookup"><span data-stu-id="8095d-172">Open *MainWindow.xaml*.</span></span>

1. <span data-ttu-id="8095d-173"><xref:System.Windows.Navigation.NavigationWindow.Source%2A> プロパティを <xref:System.Windows.Navigation.NavigationWindow> 要素に追加し、それを "`ExpenseItHome.xaml`" に設定します。</span><span class="sxs-lookup"><span data-stu-id="8095d-173">Add a <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property to the <xref:System.Windows.Navigation.NavigationWindow> element and set it to "`ExpenseItHome.xaml`".</span></span>

    <span data-ttu-id="8095d-174">これにより、 *`ExpenseItHome.xaml`* が、アプリケーションの起動時に最初に開くページとして設定されます。</span><span class="sxs-lookup"><span data-stu-id="8095d-174">This sets *`ExpenseItHome.xaml`* to be the first page opened when the application starts.</span></span>

    <span data-ttu-id="8095d-175">Visual Basic での XAML の例:</span><span class="sxs-lookup"><span data-stu-id="8095d-175">Example XAML in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#7_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    <span data-ttu-id="8095d-176">C# の場合:</span><span class="sxs-lookup"><span data-stu-id="8095d-176">And in C#:</span></span>

    [!code-xaml[ExpenseIt#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > <span data-ttu-id="8095d-177">また、 **[プロパティ]** ウィンドウの **[Miscellaneous]** カテゴリで、 **[Source]** プロパティを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="8095d-177">You can also set the **Source** property in the **Miscellaneous** category of the **Properties** window.</span></span>
   >
   > ![[プロパティ] ウィンドウでの Source プロパティ](./media/properties-source.png)

1. <span data-ttu-id="8095d-179">別の新しい WPF ページをプロジェクトに追加し、*ExpenseReportPage.xaml* という名前にします。</span><span class="sxs-lookup"><span data-stu-id="8095d-179">Add another new WPF page to the project, and name it *ExpenseReportPage.xaml*::</span></span>

   1. <span data-ttu-id="8095d-180">**ソリューション エクスプローラー** で、 **`ExpenseIt`** プロジェクト ノードを右クリックして、 **[追加]**  >  **[ページ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8095d-180">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="8095d-181">**[新しい項目の追加]** ダイアログで、 **[ページ (WPF)]** テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="8095d-181">In the **Add New Item** dialog, select the **Page (WPF)** template.</span></span> <span data-ttu-id="8095d-182">名前に「**ExpenseReportPage**」と入力し、 **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8095d-182">Enter the name **ExpenseReportPage**, and then select **Add**.</span></span>

    <span data-ttu-id="8095d-183">このページには、 **`ExpenseItHome`** ページで選択されたユーザーの経費報告書が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8095d-183">This page will show the expense report for the person that is selected on the **`ExpenseItHome`** page.</span></span>

1. <span data-ttu-id="8095d-184">*ExpenseReportPage.xaml* を開きます。</span><span class="sxs-lookup"><span data-stu-id="8095d-184">Open *ExpenseReportPage.xaml*.</span></span>

1. <span data-ttu-id="8095d-185"><xref:System.Windows.Controls.Page.Title%2A> を "`ExpenseIt - View Expense`" に設定します。</span><span class="sxs-lookup"><span data-stu-id="8095d-185">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - View Expense`".</span></span>

1. <span data-ttu-id="8095d-186">`DesignHeight` を 350 ピクセルに設定し、`DesignWidth` を 500 ピクセルに設定します。</span><span class="sxs-lookup"><span data-stu-id="8095d-186">Set the `DesignHeight` to 350 pixels and the `DesignWidth` to 500 pixels.</span></span>

    <span data-ttu-id="8095d-187">*ExpenseReportPage.xaml* は、Visual Basic では次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8095d-187">*ExpenseReportPage.xaml* now looks like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#4_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    <span data-ttu-id="8095d-188">C# では次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8095d-188">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

1. <span data-ttu-id="8095d-189">*ExpenseItHome.xaml.vb* と *ExpenseReportPage.xaml.vb* を開くか、または *ExpenseItHome.xaml.cs* と *ExpenseReportPage.xaml.cs* を開きます。</span><span class="sxs-lookup"><span data-stu-id="8095d-189">Open *ExpenseItHome.xaml.vb* and *ExpenseReportPage.xaml.vb*, or *ExpenseItHome.xaml.cs* and *ExpenseReportPage.xaml.cs*.</span></span>

    <span data-ttu-id="8095d-190">新しいページ ファイルを作成すると、Visual Studio によってその "*分離コード*" ファイルが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="8095d-190">When you create a new Page file, Visual Studio automatically creates its *code-behind* file.</span></span> <span data-ttu-id="8095d-191">これらの分離コード ファイルでは、ユーザー入力に対応するためのロジックを処理します。</span><span class="sxs-lookup"><span data-stu-id="8095d-191">These code-behind files handle the logic for responding to user input.</span></span>

    <span data-ttu-id="8095d-192">**`ExpenseItHome`** のコードは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8095d-192">Your code should look like the following for **`ExpenseItHome`**:</span></span>

    [!code-csharp[ExpenseIt#2_5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]

    [!code-vb[ExpenseIt#2_5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    <span data-ttu-id="8095d-193">**ExpenseReportPage** は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8095d-193">And like the following for **ExpenseReportPage**:</span></span>

    [!code-csharp[ExpenseIt#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]

    [!code-vb[ExpenseIt#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

1. <span data-ttu-id="8095d-194">*watermark.png* という名前の画像をプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="8095d-194">Add an image named *watermark.png* to the project.</span></span> <span data-ttu-id="8095d-195">独自の画像を作成したり、サンプル コードからファイルをコピーしたり、[microsoft/WPF-Samples](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png) GitHub リポジトリから取得したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="8095d-195">You can create your own image, copy the file from the sample code, or get it from the [microsoft/WPF-Samples](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png) GitHub repository.</span></span>

    1. <span data-ttu-id="8095d-196">プロジェクト ノードを右クリックし、 **[追加]**  >  **[既存の項目]** を選択するか、**Shift** + **Alt** + **A** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="8095d-196">Right-click on the project node and select **Add** > **Existing Item**, or press **Shift**+**Alt**+**A**.</span></span>

    2. <span data-ttu-id="8095d-197">**[Add Existing Item]\(既存項目の追加\)** ダイアログで、ファイル フィルターを **[すべてのファイル]** または **[画像ファイル]** に設定し、使用する画像ファイルを参照して、 **[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8095d-197">In the **Add Existing Item** dialog, set the file filter to either **All Files** or **Image Files**, browse to the image file you want to use, and then select **Add**.</span></span>

## <a name="build-and-run-the-application"></a><span data-ttu-id="8095d-198">アプリケーションのビルドと実行</span><span class="sxs-lookup"><span data-stu-id="8095d-198">Build and run the application</span></span>

1. <span data-ttu-id="8095d-199">アプリケーションをビルドして実行するには、**F5** キーを押すか、 **[デバッグ]** メニューの **[デバッグの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8095d-199">To build and run the application, press **F5** or select **Start Debugging** from the **Debug** menu.</span></span>

    <span data-ttu-id="8095d-200"><xref:System.Windows.Navigation.NavigationWindow> ボタンが含まれるアプリケーションは、次の図のようになります。</span><span class="sxs-lookup"><span data-stu-id="8095d-200">The following illustration shows the application with the <xref:System.Windows.Navigation.NavigationWindow> buttons:</span></span>

    ![ビルドして実行した後のアプリケーション。](./media/walkthrough-my-first-wpf-desktop-application/build-run-application.png)

2. <span data-ttu-id="8095d-202">アプリケーションを閉じて Visual Studio に戻ります。</span><span class="sxs-lookup"><span data-stu-id="8095d-202">Close the application to return to Visual Studio.</span></span>

## <a name="create-the-layout"></a><span data-ttu-id="8095d-203">レイアウトを作成する</span><span class="sxs-lookup"><span data-stu-id="8095d-203">Create the layout</span></span>

<span data-ttu-id="8095d-204">レイアウトを使用すると、順序付けされた方法で UI 要素を配置できます。また、UI のサイズが変更された場合の要素のサイズと位置が管理されます。</span><span class="sxs-lookup"><span data-stu-id="8095d-204">Layout provides an ordered way to place UI elements, and also manages the size and position of those elements when a UI is resized.</span></span> <span data-ttu-id="8095d-205">通常、レイアウトを作成するには、次のいずれかのレイアウト コントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="8095d-205">You typically create a layout with one of the following layout controls:</span></span>

- <span data-ttu-id="8095d-206"><xref:System.Windows.Controls.Canvas> - キャンバス領域に対する相対座標を使用して子要素を明示的に配置する領域を定義します。</span><span class="sxs-lookup"><span data-stu-id="8095d-206"><xref:System.Windows.Controls.Canvas> - Defines an area within which you can explicitly position child elements by using coordinates that are relative to the Canvas area.</span></span>
- <span data-ttu-id="8095d-207"><xref:System.Windows.Controls.DockPanel> - 子要素を互いに水平方向または垂直方向に整列する領域を定義します。</span><span class="sxs-lookup"><span data-stu-id="8095d-207"><xref:System.Windows.Controls.DockPanel> - Defines an area where you can arrange child elements either horizontally or vertically, relative to each other.</span></span>
- <span data-ttu-id="8095d-208"><xref:System.Windows.Controls.Grid> - 行と列で構成される柔軟性のあるグリッド領域を定義します。</span><span class="sxs-lookup"><span data-stu-id="8095d-208"><xref:System.Windows.Controls.Grid> - Defines a flexible grid area that consists of columns and rows.</span></span>
- <span data-ttu-id="8095d-209"><xref:System.Windows.Controls.StackPanel> - 子要素を水平方向または垂直方向の単一行に整列します。</span><span class="sxs-lookup"><span data-stu-id="8095d-209"><xref:System.Windows.Controls.StackPanel> - Arranges child elements into a single line that can be oriented horizontally or vertically.</span></span>
- <span data-ttu-id="8095d-210"><xref:System.Windows.Controls.VirtualizingStackPanel> - 水平方向または垂直方向の単一行でコンテンツを整列し、仮想化します。</span><span class="sxs-lookup"><span data-stu-id="8095d-210"><xref:System.Windows.Controls.VirtualizingStackPanel> - Arranges and virtualizes content on a single line that is oriented either horizontally or vertically.</span></span>
- <span data-ttu-id="8095d-211"><xref:System.Windows.Controls.WrapPanel> - 左から右へ順に子要素を配置し、ボックスの端で改行してコンテンツを次の行へ送ります。</span><span class="sxs-lookup"><span data-stu-id="8095d-211"><xref:System.Windows.Controls.WrapPanel> - Positions child elements in sequential position from left to right, breaking content to the next line at the edge of the containing box.</span></span> <span data-ttu-id="8095d-212">後続の配置は、Orientation プロパティの値に応じて、上から下または右から左に向かって行われます。</span><span class="sxs-lookup"><span data-stu-id="8095d-212">Subsequent ordering happens sequentially from top to bottom or from right to left, depending on the value of the Orientation property.</span></span>

<span data-ttu-id="8095d-213">これらの各レイアウト コントロールでは、その子要素に対する特定の種類のレイアウトがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8095d-213">Each of these layout controls supports a particular type of layout for its child elements.</span></span> <span data-ttu-id="8095d-214">`ExpenseIt` のページはサイズの変更が可能で、各ページの要素は縦にも横にも他の要素と揃えられます。</span><span class="sxs-lookup"><span data-stu-id="8095d-214">`ExpenseIt` pages can be resized, and each page has elements that are arranged horizontally and vertically alongside other elements.</span></span> <span data-ttu-id="8095d-215">この例では、アプリケーションのレイアウト要素として <xref:System.Windows.Controls.Grid> を使用します。</span><span class="sxs-lookup"><span data-stu-id="8095d-215">In this example, the <xref:System.Windows.Controls.Grid> is used as  layout element for the application.</span></span>

> [!TIP]
> <span data-ttu-id="8095d-216"><xref:System.Windows.Controls.Panel> 要素の詳細については、「[パネルの概要](../controls/panels-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8095d-216">For more information about <xref:System.Windows.Controls.Panel> elements, see [Panels overview](../controls/panels-overview.md).</span></span> <span data-ttu-id="8095d-217">レイアウトの詳細については、「[レイアウト](../advanced/layout.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8095d-217">For more information about layout, see [Layout](../advanced/layout.md).</span></span>

<span data-ttu-id="8095d-218">このセクションでは、 *`ExpenseItHome.xaml`* の <xref:System.Windows.Controls.Grid> に列と行の定義を追加して、10 ピクセルのマージンを持つ 3 行 1 列のテーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="8095d-218">In this section, you create a single-column table with three rows and a 10-pixel margin by adding column and row definitions to the <xref:System.Windows.Controls.Grid> in *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="8095d-219">*`ExpenseItHome.xaml`* で、<xref:System.Windows.Controls.Grid> 要素の <xref:System.Windows.FrameworkElement.Margin%2A> プロパティを "10,0,10,10" に設定します。これは、左、上、右、下の余白に対応しています。</span><span class="sxs-lookup"><span data-stu-id="8095d-219">In *`ExpenseItHome.xaml`*, set the <xref:System.Windows.FrameworkElement.Margin%2A> property on the <xref:System.Windows.Controls.Grid> element to "10,0,10,10", which corresponds to left, top, right and bottom margins:</span></span>

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > <span data-ttu-id="8095d-220">また、 **[プロパティ]** ウィンドウの **[レイアウト]** カテゴリで、**Margin** の値を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="8095d-220">You can also set the **Margin** values in the **Properties** window, under the **Layout** category:</span></span>
   >
   > ![プロパティ ウィンドウでの余白の値](./media/properties-margin.png)

2. <span data-ttu-id="8095d-222"><xref:System.Windows.Controls.Grid> タグの間に次の XAML を追加して、行と列の定義を作成します。</span><span class="sxs-lookup"><span data-stu-id="8095d-222">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags to create the row and column definitions:</span></span>

    [!code-xaml[ExpenseIt#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    <span data-ttu-id="8095d-223">2 行の <xref:System.Windows.Controls.RowDefinition.Height%2A> は <xref:System.Windows.GridLength.Auto%2A> に設定されます。つまり、行のサイズは、行の内容に基づいて設定されます。</span><span class="sxs-lookup"><span data-stu-id="8095d-223">The <xref:System.Windows.Controls.RowDefinition.Height%2A> of two rows is set to <xref:System.Windows.GridLength.Auto%2A>, which means that the rows are sized based on the content in the rows.</span></span> <span data-ttu-id="8095d-224">既定の <xref:System.Windows.Controls.RowDefinition.Height%2A> は <xref:System.Windows.GridUnitType.Star> のサイズ設定です。これは、行の高さが使用可能な領域の加重比率であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="8095d-224">The default <xref:System.Windows.Controls.RowDefinition.Height%2A> is <xref:System.Windows.GridUnitType.Star> sizing, which means that the row height is a weighted proportion of the available space.</span></span> <span data-ttu-id="8095d-225">たとえば、2 つの行それぞれの <xref:System.Windows.Controls.RowDefinition.Height%2A> が "\*" の場合、各行の高さは、使用可能なスペースの半分になります。</span><span class="sxs-lookup"><span data-stu-id="8095d-225">For example if two rows each have a <xref:System.Windows.Controls.RowDefinition.Height%2A> of "\*", they each have a height that is half of the available space.</span></span>

    <span data-ttu-id="8095d-226"><xref:System.Windows.Controls.Grid> は次の XAML のようになっているはずです。</span><span class="sxs-lookup"><span data-stu-id="8095d-226">Your <xref:System.Windows.Controls.Grid> should now contain the following XAML:</span></span>

    [!code-xaml[ExpenseIt#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a><span data-ttu-id="8095d-227">コントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="8095d-227">Add controls</span></span>

<span data-ttu-id="8095d-228">このセクションでは、ホームページの UI を更新して、ユーザーの一覧が表示されるようにします。ここで、経費報告書を表示するユーザーを 1 人選択します。</span><span class="sxs-lookup"><span data-stu-id="8095d-228">In this section, you'll update the home page UI to show a list of people, where you select one person to display their expense report.</span></span> <span data-ttu-id="8095d-229">コントロールとは、ユーザーがアプリケーションと対話できるようにする UI オブジェクトのことです。</span><span class="sxs-lookup"><span data-stu-id="8095d-229">Controls are UI objects that allow users to interact with your application.</span></span> <span data-ttu-id="8095d-230">詳しくは、「 [コントロール](../controls/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8095d-230">For more information, see [Controls](../controls/index.md).</span></span>

<span data-ttu-id="8095d-231">この UI を作成するには、次の要素を *`ExpenseItHome.xaml`* に追加します。</span><span class="sxs-lookup"><span data-stu-id="8095d-231">To create this UI, you'll add the following elements to *`ExpenseItHome.xaml`*:</span></span>

- <span data-ttu-id="8095d-232"><xref:System.Windows.Controls.ListBox> (個人の一覧用)。</span><span class="sxs-lookup"><span data-stu-id="8095d-232">A <xref:System.Windows.Controls.ListBox> (for the list of people).</span></span>
- <span data-ttu-id="8095d-233"><xref:System.Windows.Controls.Label> (一覧のヘッダー用)。</span><span class="sxs-lookup"><span data-stu-id="8095d-233">A <xref:System.Windows.Controls.Label> (for the list header).</span></span>
- <span data-ttu-id="8095d-234"><xref:System.Windows.Controls.Button> (クリックし、一覧で選択した個人の経費報告書を表示するため)。</span><span class="sxs-lookup"><span data-stu-id="8095d-234">A <xref:System.Windows.Controls.Button> (to click to view the expense report for the person that is selected in the list).</span></span>

<span data-ttu-id="8095d-235">各コントロールは、<xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> 添付プロパティを設定することで、<xref:System.Windows.Controls.Grid> の行に配置されます。</span><span class="sxs-lookup"><span data-stu-id="8095d-235">Each control is placed in a row of the <xref:System.Windows.Controls.Grid> by setting the <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> attached property.</span></span> <span data-ttu-id="8095d-236">添付プロパティについて詳しくは、「[添付プロパティの概要](../advanced/attached-properties-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8095d-236">For more information about attached properties, see [Attached Properties Overview](../advanced/attached-properties-overview.md).</span></span>

1. <span data-ttu-id="8095d-237">*`ExpenseItHome.xaml`* で、<xref:System.Windows.Controls.Grid> タグの間のどこかに次の XAML を追加します。</span><span class="sxs-lookup"><span data-stu-id="8095d-237">In *`ExpenseItHome.xaml`*, add the following XAML somewhere between the <xref:System.Windows.Controls.Grid> tags:</span></span>

   [!code-xaml[ExpenseIt#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > <span data-ttu-id="8095d-238">コントロールを **[ツールボックス]** ウィンドウからデザイン ウィンドウにドラッグし、 **[プロパティ]** ウィンドウでプロパティを設定することよって、コントロールを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="8095d-238">You can also create the controls by dragging them from the **Toolbox** window onto the design window, and then setting their properties in the **Properties** window.</span></span>

2. <span data-ttu-id="8095d-239">アプリケーションをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="8095d-239">Build and run the application.</span></span>

    <span data-ttu-id="8095d-240">次の図では、作成したコントロールを示します。</span><span class="sxs-lookup"><span data-stu-id="8095d-240">The following illustration shows the controls you created:</span></span>

![名前の一覧が表示されている、ExpenseIt サンプルのスクリーンショット](./media/walkthrough-my-first-wpf-desktop-application/add-application-controls.png)

## <a name="add-an-image-and-a-title"></a><span data-ttu-id="8095d-242">画像とタイトルを追加する</span><span class="sxs-lookup"><span data-stu-id="8095d-242">Add an image and a title</span></span>

<span data-ttu-id="8095d-243">このセクションでは、画像とページ タイトルでホーム ページの UI を更新します。</span><span class="sxs-lookup"><span data-stu-id="8095d-243">In this section, you'll update the home page UI with an image and a page title.</span></span>

1. <span data-ttu-id="8095d-244">*`ExpenseItHome.xaml`* で、<xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> に、<xref:System.Windows.Controls.ColumnDefinition.Width%2A> が 230 ピクセルで固定された新しい列を追加します。</span><span class="sxs-lookup"><span data-stu-id="8095d-244">In *`ExpenseItHome.xaml`*, add another column to the <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> with a fixed <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of 230 pixels:</span></span>

    [!code-xaml[ExpenseIt#11](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=2#NewColumn)]

2. <span data-ttu-id="8095d-245"><xref:System.Windows.Controls.Grid.RowDefinitions%2A> に別の行を追加します。全部で 4 行になります。</span><span class="sxs-lookup"><span data-stu-id="8095d-245">Add another row to the <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, for a total of four rows:</span></span>

    [!code-xaml[ExpenseIt#11b](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=2#NewRows)]

3. <span data-ttu-id="8095d-246">3 つの各コントロール (Border、ListBox、Button) で、<xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> プロパティを 1 に設定して、コントロールを 2 列目に移動します。</span><span class="sxs-lookup"><span data-stu-id="8095d-246">Move the controls to the second column by setting the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property to 1 in each of the three controls (Border, ListBox, and Button).</span></span>

4. <span data-ttu-id="8095d-247">3 つの各コントロール (Border、ListBox、Button) と Border 要素の <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> の値を 1 だけインクリメントして、各コントロールを 1 行下に移動します。</span><span class="sxs-lookup"><span data-stu-id="8095d-247">Move each control down a row by incrementing its <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> value by 1 for each of the three controls (Border, ListBox, and Button) and for the Border element.</span></span>

   <span data-ttu-id="8095d-248">3 つのコントロールの XAML は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8095d-248">The XAML for the three controls now looks like the following:</span></span>

    [!code-xaml[ExpenseIt#12](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

5. <span data-ttu-id="8095d-249">次の XAML をタグとタグの間に追加して、 [Background](xref:System.Windows.Controls.Panel.Background%2A) プロパティを *watermark.png* イメージファイルに設定し `<Grid>` `</Grid>` ます。</span><span class="sxs-lookup"><span data-stu-id="8095d-249">Set the [Background](xref:System.Windows.Controls.Panel.Background%2A) property to the *watermark.png* image file, by adding the following XAML anywhere between the `<Grid>` and `</Grid>` tags:</span></span>

    [!code-xaml[ExpenseIt#14](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

6. <span data-ttu-id="8095d-250"><xref:System.Windows.Controls.Border> 要素の前に、"View Expense Report" という内容の <xref:System.Windows.Controls.Label> を追加します。</span><span class="sxs-lookup"><span data-stu-id="8095d-250">Before the <xref:System.Windows.Controls.Border> element, add a <xref:System.Windows.Controls.Label> with the content "View Expense Report".</span></span> <span data-ttu-id="8095d-251">このラベルはページのタイトルです。</span><span class="sxs-lookup"><span data-stu-id="8095d-251">This label is the title of the page.</span></span>

    [!code-xaml[ExpenseIt#13](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

7. <span data-ttu-id="8095d-252">アプリケーションをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="8095d-252">Build and run the application.</span></span>

<span data-ttu-id="8095d-253">次の図では、追加した結果を示します。</span><span class="sxs-lookup"><span data-stu-id="8095d-253">The following illustration shows the results of what you just added:</span></span>

![新しい背景画像とページ タイトルが表示されている ExpenseIt サンプルのスクリーンショット](./media/walkthrough-my-first-wpf-desktop-application/add-application-image-title.png)

## <a name="add-code-to-handle-events"></a><span data-ttu-id="8095d-255">イベントを処理するコードを追加する</span><span class="sxs-lookup"><span data-stu-id="8095d-255">Add code to handle events</span></span>

1. <span data-ttu-id="8095d-256">*`ExpenseItHome.xaml`* で、<xref:System.Windows.Controls.Button> 要素に <xref:System.Windows.Controls.Primitives.ButtonBase.Click> イベント ハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="8095d-256">In *`ExpenseItHome.xaml`*, add a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to the <xref:System.Windows.Controls.Button> element.</span></span> <span data-ttu-id="8095d-257">詳細については、「[方法:単純なイベント ハンドラーを作成する](/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8095d-257">For more information, see [How to: Create a simple event handler](/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span></span>

    [!code-xaml[ExpenseIt#15](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

2. <span data-ttu-id="8095d-258">*`ExpenseItHome.xaml.vb`* または *`ExpenseItHome.xaml.cs`* を開きます。</span><span class="sxs-lookup"><span data-stu-id="8095d-258">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

3. <span data-ttu-id="8095d-259">次のコードを `ExpenseItHome` クラスに追加して、ボタン クリック イベント ハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="8095d-259">Add the following code to the `ExpenseItHome` class to add a button click event handler.</span></span> <span data-ttu-id="8095d-260">イベント ハンドラーによって、**ExpenseReportPage** ページが開かれます。</span><span class="sxs-lookup"><span data-stu-id="8095d-260">The event handler opens the **ExpenseReportPage** page.</span></span>

    [!code-csharp[ExpenseIt#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a><span data-ttu-id="8095d-261">ExpenseReportPage の UI を作成する</span><span class="sxs-lookup"><span data-stu-id="8095d-261">Create the UI for ExpenseReportPage</span></span>

<span data-ttu-id="8095d-262">*ExpenseReportPage.xaml* には、 **`ExpenseItHome`** ページで選択された個人の経費報告書が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8095d-262">*ExpenseReportPage.xaml* displays the expense report for the person that's selected on the **`ExpenseItHome`** page.</span></span> <span data-ttu-id="8095d-263">このセクションでは、**ExpenseReportPage** ページの UI を作成します。</span><span class="sxs-lookup"><span data-stu-id="8095d-263">In this section, you'll create the UI for **ExpenseReportPage**.</span></span> <span data-ttu-id="8095d-264">また、さまざまな UI 要素に背景と塗りつぶしの色も追加します。</span><span class="sxs-lookup"><span data-stu-id="8095d-264">You'll also add background and fill colors to the various UI elements.</span></span>

1. <span data-ttu-id="8095d-265">*ExpenseReportPage.xaml* を開きます。</span><span class="sxs-lookup"><span data-stu-id="8095d-265">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="8095d-266"><xref:System.Windows.Controls.Grid> タグの間に次の XAML を追加します。</span><span class="sxs-lookup"><span data-stu-id="8095d-266">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags:</span></span>

    [!code-xaml[ExpenseIt#17](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    <span data-ttu-id="8095d-267">この UI は、<xref:System.Windows.Controls.DataGrid> にレポート データが表示される点を除き、 *`ExpenseItHome.xaml`* と似ています。</span><span class="sxs-lookup"><span data-stu-id="8095d-267">This UI is similar to *`ExpenseItHome.xaml`*, except the report data is displayed in a <xref:System.Windows.Controls.DataGrid>.</span></span>

3. <span data-ttu-id="8095d-268">アプリケーションをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="8095d-268">Build and run the application.</span></span>

4. <span data-ttu-id="8095d-269">**[View]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="8095d-269">Select the **View** button.</span></span>

    <span data-ttu-id="8095d-270">経費明細書ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8095d-270">The expense report page appears.</span></span> <span data-ttu-id="8095d-271">戻るナビゲーション ボタンが有効になっていることにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="8095d-271">Also notice that the back navigation button is enabled.</span></span>

<span data-ttu-id="8095d-272">*ExpenseReportPage.xaml* に追加された UI 要素を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="8095d-272">The following illustration shows the UI elements added to *ExpenseReportPage.xaml*.</span></span>

![ExpenseReportPage に作成した UI が表示されている ExpenseIt サンプルのスクリーンショット。](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

## <a name="style-controls"></a><span data-ttu-id="8095d-274">スタイル コントロール</span><span class="sxs-lookup"><span data-stu-id="8095d-274">Style controls</span></span>

<span data-ttu-id="8095d-275">多くの場合、UI では、要素の種類が同じであれば、外観もすべて同じになります。</span><span class="sxs-lookup"><span data-stu-id="8095d-275">The appearance of various elements is often the same for all elements of the same type in a UI.</span></span> <span data-ttu-id="8095d-276">UI では、複数の要素間で外観を再利用できるように、[スタイル](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)が使用されます。</span><span class="sxs-lookup"><span data-stu-id="8095d-276">UI uses [styles](/dotnet/desktop-wpf/fundamentals/styles-templates-overview) to make appearances reusable across multiple elements.</span></span> <span data-ttu-id="8095d-277">スタイルの再利用性により、XAML の作成と管理が簡略化されます。</span><span class="sxs-lookup"><span data-stu-id="8095d-277">The reusability of styles helps to simplify XAML creation and management.</span></span> <span data-ttu-id="8095d-278">このセクションでは、これまでの手順で定義した要素ごとの属性を、スタイルに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="8095d-278">This section replaces the per-element attributes that were defined in previous steps with styles.</span></span>

1. <span data-ttu-id="8095d-279">*Application.xaml* または *App.xaml* を開きます。</span><span class="sxs-lookup"><span data-stu-id="8095d-279">Open *Application.xaml* or *App.xaml*.</span></span>

2. <span data-ttu-id="8095d-280"><xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> タグの間に次の XAML を追加します。</span><span class="sxs-lookup"><span data-stu-id="8095d-280">Add the following XAML between the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> tags:</span></span>

    [!code-xaml[ExpenseIt#18](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    <span data-ttu-id="8095d-281">この XAML は、次のスタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="8095d-281">This XAML adds the following styles:</span></span>

    - <span data-ttu-id="8095d-282">`headerTextStyle`:ページ タイトルの <xref:System.Windows.Controls.Label> の書式を設定します。</span><span class="sxs-lookup"><span data-stu-id="8095d-282">`headerTextStyle`: To format the page title <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="8095d-283">`labelStyle`:<xref:System.Windows.Controls.Label> コントロールの書式を設定します。</span><span class="sxs-lookup"><span data-stu-id="8095d-283">`labelStyle`: To format the <xref:System.Windows.Controls.Label> controls.</span></span>

    - <span data-ttu-id="8095d-284">`columnHeaderStyle`:<xref:System.Windows.Controls.Primitives.DataGridColumnHeader> の書式を設定します。</span><span class="sxs-lookup"><span data-stu-id="8095d-284">`columnHeaderStyle`: To format the <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span></span>

    - <span data-ttu-id="8095d-285">`listHeaderStyle`:リスト ヘッダーの <xref:System.Windows.Controls.Border> コントロールの書式を設定します。</span><span class="sxs-lookup"><span data-stu-id="8095d-285">`listHeaderStyle`: To format the list header <xref:System.Windows.Controls.Border> controls.</span></span>

    - <span data-ttu-id="8095d-286">`listHeaderTextStyle`:リスト ヘッダーの <xref:System.Windows.Controls.Label> の書式を設定します。</span><span class="sxs-lookup"><span data-stu-id="8095d-286">`listHeaderTextStyle`: To format the list header <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="8095d-287">`buttonStyle`:`ExpenseItHome.xaml` で <xref:System.Windows.Controls.Button> の書式を設定します。</span><span class="sxs-lookup"><span data-stu-id="8095d-287">`buttonStyle`: To format the <xref:System.Windows.Controls.Button> on `ExpenseItHome.xaml`.</span></span>

    <span data-ttu-id="8095d-288">スタイルはリソースであり、<xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> プロパティ要素の子であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8095d-288">Notice that the styles are resources and children of the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> property element.</span></span> <span data-ttu-id="8095d-289">ここでは、スタイルはアプリケーション内のすべての要素に適用されます。</span><span class="sxs-lookup"><span data-stu-id="8095d-289">In this location, the styles are applied to all the elements in an application.</span></span> <span data-ttu-id="8095d-290">.NET アプリでリソースを使用する例については、[アプリケーション リソースの使用](../advanced/how-to-use-application-resources.md)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8095d-290">For an example of using resources in a .NET app, see [Use Application Resources](../advanced/how-to-use-application-resources.md).</span></span>

3. <span data-ttu-id="8095d-291">*`ExpenseItHome.xaml`* で、<xref:System.Windows.Controls.Grid> 要素の間のすべてを次の XAML に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="8095d-291">In *`ExpenseItHome.xaml`*, replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#19](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    <span data-ttu-id="8095d-292">各コントロールの外観を定義する <xref:System.Windows.VerticalAlignment> や <xref:System.Windows.Media.FontFamily> などのプロパティは、これらのスタイルを適用することで、削除されて置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="8095d-292">The properties such as <xref:System.Windows.VerticalAlignment> and <xref:System.Windows.Media.FontFamily> that define the look of each control are removed and replaced by applying the styles.</span></span> <span data-ttu-id="8095d-293">たとえば、"View Expense Report" という <xref:System.Windows.Controls.Label> には、`headerTextStyle` が適用されます。</span><span class="sxs-lookup"><span data-stu-id="8095d-293">For example, the `headerTextStyle` is applied to the "View Expense Report" <xref:System.Windows.Controls.Label>.</span></span>

4. <span data-ttu-id="8095d-294">*ExpenseReportPage.xaml* を開きます。</span><span class="sxs-lookup"><span data-stu-id="8095d-294">Open *ExpenseReportPage.xaml*.</span></span>

5. <span data-ttu-id="8095d-295"><xref:System.Windows.Controls.Grid> 要素の間のすべてを、次の XAML に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="8095d-295">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#20](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    <span data-ttu-id="8095d-296">この XAML では、スタイルが <xref:System.Windows.Controls.Label> 要素と <xref:System.Windows.Controls.Border> 要素に追加されます。</span><span class="sxs-lookup"><span data-stu-id="8095d-296">This XAML adds styles to the <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Border> elements.</span></span>

6. <span data-ttu-id="8095d-297">アプリケーションをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="8095d-297">Build and run the application.</span></span> <span data-ttu-id="8095d-298">ウィンドウの外観は、以前と同じです。</span><span class="sxs-lookup"><span data-stu-id="8095d-298">The window appearance is the same as previously.</span></span>

    ![前回のセクションと同じ外観の ExpenseIt サンプルのスクリーンショット。](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

7. <span data-ttu-id="8095d-300">アプリケーションを閉じて Visual Studio に戻ります。</span><span class="sxs-lookup"><span data-stu-id="8095d-300">Close the application to return to Visual Studio.</span></span>

## <a name="bind-data-to-a-control"></a><span data-ttu-id="8095d-301">データをコントロールにバインドする</span><span class="sxs-lookup"><span data-stu-id="8095d-301">Bind data to a control</span></span>

<span data-ttu-id="8095d-302">このセクションでは、さまざまなコントロールにバインドされる XML データを作成します。</span><span class="sxs-lookup"><span data-stu-id="8095d-302">In this section, you'll create the XML data that is bound to various controls.</span></span>

1. <span data-ttu-id="8095d-303">*`ExpenseItHome.xaml`* で、開始 <xref:System.Windows.Controls.Grid> 要素の後に次の XAML を追加して、各個人のデータを含む <xref:System.Windows.Data.XmlDataProvider> を作成します。</span><span class="sxs-lookup"><span data-stu-id="8095d-303">In *`ExpenseItHome.xaml`*, after the opening <xref:System.Windows.Controls.Grid> element, add the following XAML to create an <xref:System.Windows.Data.XmlDataProvider> that contains the data for each person:</span></span>

    [!code-xaml[ExpenseIt#23](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,16-40,49)]

    <span data-ttu-id="8095d-304">データは <xref:System.Windows.Controls.Grid> リソースとして作成されます。</span><span class="sxs-lookup"><span data-stu-id="8095d-304">The data is created as a <xref:System.Windows.Controls.Grid> resource.</span></span> <span data-ttu-id="8095d-305">通常、このデータはファイルとして読み込まれますが、説明を簡単にするため、データをインラインで追加します。</span><span class="sxs-lookup"><span data-stu-id="8095d-305">Normally this data would be loaded as a file, but for simplicity the data is added inline.</span></span>

2. <span data-ttu-id="8095d-306">`<Grid.Resources>` 要素内の `<XmlDataProvider>` 要素の後に、<xref:System.Windows.Controls.ListBox> でのデータの表示方法を定義する次の `<xref:System.Windows.DataTemplate>` 要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="8095d-306">Within the `<Grid.Resources>` element, add the following `<xref:System.Windows.DataTemplate>` element, which defines how to display the data in the <xref:System.Windows.Controls.ListBox>, after the `<XmlDataProvider>` element:</span></span>

    [!code-xaml[ExpenseIt#24](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,43-46,49)]

    <span data-ttu-id="8095d-307">データ テンプレートについて詳しくは、「[データ テンプレートの概要](../data/data-templating-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8095d-307">For more information about data templates, see [Data templating overview](../data/data-templating-overview.md).</span></span>

3. <span data-ttu-id="8095d-308">既存の <xref:System.Windows.Controls.ListBox> を次の XAML に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="8095d-308">Replace the existing <xref:System.Windows.Controls.ListBox> with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#25](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    <span data-ttu-id="8095d-309">この XAML では、<xref:System.Windows.Controls.ListBox> の <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> プロパティがデータ ソースにバインドされ、データ テンプレートが <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> として適用されます。</span><span class="sxs-lookup"><span data-stu-id="8095d-309">This XAML binds the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to the data source and applies the data template as the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span></span>

## <a name="connect-data-to-controls"></a><span data-ttu-id="8095d-310">コントロールにデータを接続する</span><span class="sxs-lookup"><span data-stu-id="8095d-310">Connect data to controls</span></span>

<span data-ttu-id="8095d-311">次に、 **`ExpenseItHome`** ページで選択された名前を取得し、それを **ExpenseReportPage** のコンストラクターに渡すコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="8095d-311">Next, you'll add code to retrieve the name that's selected on the **`ExpenseItHome`** page and pass it to the constructor of **ExpenseReportPage**.</span></span> <span data-ttu-id="8095d-312">**ExpenseReportPage** では、渡された項目を使用してデータ コンテキストが設定されます。それが、*ExpenseReportPage.xaml* で定義されているコントロールのバインド先になります。</span><span class="sxs-lookup"><span data-stu-id="8095d-312">**ExpenseReportPage** sets its data context with the passed item, which is what the controls defined in *ExpenseReportPage.xaml* bind to.</span></span>

1. <span data-ttu-id="8095d-313">*ExpenseReportPage.xaml.vb* または *ExpenseReportPage.xaml.cs* を開きます。</span><span class="sxs-lookup"><span data-stu-id="8095d-313">Open *ExpenseReportPage.xaml.vb* or *ExpenseReportPage.xaml.cs*.</span></span>

2. <span data-ttu-id="8095d-314">オブジェクトを取得するコンストラクターを追加して、選択した個人の経費報告書データを渡せるようにします。</span><span class="sxs-lookup"><span data-stu-id="8095d-314">Add a constructor that takes an object so you can pass the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#26](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. <span data-ttu-id="8095d-315">*`ExpenseItHome.xaml.vb`* または *`ExpenseItHome.xaml.cs`* を開きます。</span><span class="sxs-lookup"><span data-stu-id="8095d-315">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

4. <span data-ttu-id="8095d-316">選択された個人の経費報告書データを渡す新しいコンストラクターを呼び出すように、<xref:System.Windows.Controls.Primitives.ButtonBase.Click> イベント ハンドラーを変更します。</span><span class="sxs-lookup"><span data-stu-id="8095d-316">Change the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to call the new constructor passing the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#27](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a><span data-ttu-id="8095d-317">データ テンプレートを使用したデータのスタイル設定</span><span class="sxs-lookup"><span data-stu-id="8095d-317">Style data with data templates</span></span>

<span data-ttu-id="8095d-318">このセクションでは、データ テンプレートを使用して、データ バインド リスト内の各項目の UI を更新します。</span><span class="sxs-lookup"><span data-stu-id="8095d-318">In this section, you'll update the UI for each item in the data-bound lists by using data templates.</span></span>

1. <span data-ttu-id="8095d-319">*ExpenseReportPage.xaml* を開きます。</span><span class="sxs-lookup"><span data-stu-id="8095d-319">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="8095d-320">"Name" および "Department" の <xref:System.Windows.Controls.Label> 要素の内容を、適切なデータ ソース プロパティにバインドします。</span><span class="sxs-lookup"><span data-stu-id="8095d-320">Bind the content of the "Name" and "Department" <xref:System.Windows.Controls.Label> elements to the appropriate data source property.</span></span> <span data-ttu-id="8095d-321">データ バインディングの詳細については、「[データ バインディングの概要](/dotnet/desktop-wpf/data/data-binding-overview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8095d-321">For more information about data binding, see [Data binding overview](/dotnet/desktop-wpf/data/data-binding-overview).</span></span>

    [!code-xaml[ExpenseIt#31](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. <span data-ttu-id="8095d-322">開始の <xref:System.Windows.Controls.Grid> 要素の後に、経費報告書データの表示方法を定義する、次のデータ テンプレートを追加します。</span><span class="sxs-lookup"><span data-stu-id="8095d-322">After the opening <xref:System.Windows.Controls.Grid> element, add the following data templates, which define how to display the expense report data:</span></span>

    [!code-xaml[ExpenseIt#30](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. <span data-ttu-id="8095d-323"><xref:System.Windows.Controls.DataGrid> 要素の下の <xref:System.Windows.Controls.DataGridTextColumn> 要素を <xref:System.Windows.Controls.DataGridTemplateColumn> に置き換えて、それらにテンプレートを適用します。</span><span class="sxs-lookup"><span data-stu-id="8095d-323">Replace the <xref:System.Windows.Controls.DataGridTextColumn> elements with <xref:System.Windows.Controls.DataGridTemplateColumn> under the <xref:System.Windows.Controls.DataGrid> element and apply the templates to them.</span></span>

    [!code-xaml[ExpenseIt#32](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. <span data-ttu-id="8095d-324">アプリケーションをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="8095d-324">Build and run the application.</span></span>

6. <span data-ttu-id="8095d-325">個人を選択し、 **[View]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="8095d-325">Select a person and then select the **View** button.</span></span>

<span data-ttu-id="8095d-326">次の図には、コントロール、レイアウト、スタイル、データ バインディング、データ テンプレートが適用された `ExpenseIt` アプリケーションの両方のページが示されています。</span><span class="sxs-lookup"><span data-stu-id="8095d-326">The following illustration shows both pages of the `ExpenseIt` application with controls, layout, styles, data binding, and data templates applied:</span></span>

![名前の一覧と経費報告書が表示されているアプリの両方のページ。](./media/walkthrough-my-first-wpf-desktop-application/application-data-templates.png)

> [!NOTE]
> <span data-ttu-id="8095d-328">このサンプルは、WPF の特定の機能について説明するものであり、セキュリティ、ローカライズ、アクセシビリティなどのベスト プラクティスには従っていません。</span><span class="sxs-lookup"><span data-stu-id="8095d-328">This sample demonstrates a specific feature of WPF and doesn't follow all best practices for things like security, localization, and accessibility.</span></span> <span data-ttu-id="8095d-329">WPF と .NET アプリの開発に関する包括的なベスト プラクティスについては、次のトピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8095d-329">For comprehensive coverage of WPF and the .NET app development best practices, see the following topics:</span></span>
>
> - [<span data-ttu-id="8095d-330">ユーザー補助</span><span class="sxs-lookup"><span data-stu-id="8095d-330">Accessibility</span></span>](/dotnet/framework/ui-automation/accessibility-best-practices)
> - [<span data-ttu-id="8095d-331">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="8095d-331">Security</span></span>](../security-wpf.md)
> - [<span data-ttu-id="8095d-332">WPF のグローバリゼーションとローカライズ</span><span class="sxs-lookup"><span data-stu-id="8095d-332">WPF globalization and localization</span></span>](../advanced/wpf-globalization-and-localization-overview.md)
> - [<span data-ttu-id="8095d-333">WPF のパフォーマンス</span><span class="sxs-lookup"><span data-stu-id="8095d-333">WPF performance</span></span>](../advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a><span data-ttu-id="8095d-334">次の手順</span><span class="sxs-lookup"><span data-stu-id="8095d-334">Next steps</span></span>

<span data-ttu-id="8095d-335">このチュートリアルでは、Windows Presentation Foundation (WPF) を使用して UI を作成するためのいくつかの手法について学習しました。</span><span class="sxs-lookup"><span data-stu-id="8095d-335">In this walkthrough you learned a number of techniques for creating a UI using Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="8095d-336">データ バインドされた .NET アプリの構成要素についての基本を理解することもできました。</span><span class="sxs-lookup"><span data-stu-id="8095d-336">You should now have a basic understanding of the building blocks of a data-bound .NET app.</span></span> <span data-ttu-id="8095d-337">WPF のアーキテクチャおよびプログラミング モデルの詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8095d-337">For more information about the WPF architecture and programming models, see the following topics:</span></span>

- [<span data-ttu-id="8095d-338">WPF のアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="8095d-338">WPF architecture</span></span>](../advanced/wpf-architecture.md)
- [<span data-ttu-id="8095d-339">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="8095d-339">XAML overview (WPF)</span></span>](/dotnet/desktop-wpf/fundamentals/xaml)
- [<span data-ttu-id="8095d-340">依存関係プロパティの概要</span><span class="sxs-lookup"><span data-stu-id="8095d-340">Dependency properties overview</span></span>](../advanced/dependency-properties-overview.md)
- [<span data-ttu-id="8095d-341">レイアウト</span><span class="sxs-lookup"><span data-stu-id="8095d-341">Layout</span></span>](../advanced/layout.md)

<span data-ttu-id="8095d-342">アプリケーションの作成の詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8095d-342">For more information about creating applications, see the following topics:</span></span>

- [<span data-ttu-id="8095d-343">アプリケーション開発</span><span class="sxs-lookup"><span data-stu-id="8095d-343">Application development</span></span>](../app-development/index.md)
- [<span data-ttu-id="8095d-344">コントロール</span><span class="sxs-lookup"><span data-stu-id="8095d-344">Controls</span></span>](../controls/index.md)
- [<span data-ttu-id="8095d-345">データバインディングの概要</span><span class="sxs-lookup"><span data-stu-id="8095d-345">Data binding overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
- [<span data-ttu-id="8095d-346">グラフィックスとマルチメディア</span><span class="sxs-lookup"><span data-stu-id="8095d-346">Graphics and multimedia</span></span>](../graphics-multimedia/index.md)
- [<span data-ttu-id="8095d-347">WPF のドキュメント</span><span class="sxs-lookup"><span data-stu-id="8095d-347">Documents in WPF</span></span>](../advanced/documents-in-wpf.md)

## <a name="see-also"></a><span data-ttu-id="8095d-348">関連項目</span><span class="sxs-lookup"><span data-stu-id="8095d-348">See also</span></span>

- [<span data-ttu-id="8095d-349">パネルの概要</span><span class="sxs-lookup"><span data-stu-id="8095d-349">Panels overview</span></span>](../controls/panels-overview.md)
- [<span data-ttu-id="8095d-350">データ テンプレートの概要</span><span class="sxs-lookup"><span data-stu-id="8095d-350">Data templating overview</span></span>](../data/data-templating-overview.md)
- [<span data-ttu-id="8095d-351">WPF アプリケーションのビルド</span><span class="sxs-lookup"><span data-stu-id="8095d-351">Build a WPF application</span></span>](../app-development/building-a-wpf-application-wpf.md)
- [<span data-ttu-id="8095d-352">スタイルおよびテンプレート</span><span class="sxs-lookup"><span data-stu-id="8095d-352">Styles and templates</span></span>](../controls/styles-and-templates.md)
