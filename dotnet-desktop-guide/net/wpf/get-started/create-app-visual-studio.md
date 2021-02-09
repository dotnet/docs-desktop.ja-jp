---
title: Visual Studio での新しいアプリの作成に関するチュートリアル
description: このチュートリアルに従って、Visual Studio 2019 を使用して .NET 用の新しい WPF アプリを作成する方法について学習します。
ms.date: 01/18/2021
ms.topic: tutorial
dev_langs:
- csharp
- vb
ms.openlocfilehash: b2769d4901b211cf5bc7cffbe4c1bf65d26a0758
ms.sourcegitcommit: 455923e44f1e8df30a233807a54ded94ddc1cf62
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "99510065"
---
# <a name="tutorial-create-a-new-wpf-app-wpf-net"></a><span data-ttu-id="463df-103">チュートリアル: 新しい WPF アプリを作成する (WPF .NET)</span><span class="sxs-lookup"><span data-stu-id="463df-103">Tutorial: Create a new WPF app (WPF .NET)</span></span>

<span data-ttu-id="463df-104">この短いチュートリアルでは、Visual Studio で新しい Windows Presentation Foundation (WPF) アプリを作成する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="463df-104">In this short tutorial, you'll learn how to create a new Windows Presentation Foundation (WPF) app with Visual Studio.</span></span> <span data-ttu-id="463df-105">最初のアプリが生成された後、コントロールを追加する方法と、イベントを処理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="463df-105">Once the initial app has been generated, you'll learn how to add controls and how to handle events.</span></span> <span data-ttu-id="463df-106">このチュートリアルを終了すると、リスト ボックスに名前を追加する簡単なアプリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="463df-106">By the end of this tutorial, you'll have a simple app that adds names to a list box.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

<span data-ttu-id="463df-107">このチュートリアルでは、以下の内容を学習します。</span><span class="sxs-lookup"><span data-stu-id="463df-107">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="463df-108">新しい WPF アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="463df-108">Create a new WPF app</span></span>
> - <span data-ttu-id="463df-109">フォームにコントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="463df-109">Add controls to a form</span></span>
> - <span data-ttu-id="463df-110">コントロール イベントを処理してアプリの機能を提供する</span><span class="sxs-lookup"><span data-stu-id="463df-110">Handle control events to provide app functionality</span></span>
> - <span data-ttu-id="463df-111">アプリを実行する</span><span class="sxs-lookup"><span data-stu-id="463df-111">Run the app</span></span>

<span data-ttu-id="463df-112">このチュートリアルに従ってビルドするアプリのプレビューを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="463df-112">Here's a preview of the app you'll build while following this tutorial:</span></span>

:::image type="content" source="media/create-app-visual-studio/app-finished.png" alt-text="チュートリアルで完成した WPF 用のサンプル アプリ":::

## <a name="prerequisites"></a><span data-ttu-id="463df-114">前提条件</span><span class="sxs-lookup"><span data-stu-id="463df-114">Prerequisites</span></span>

- [<span data-ttu-id="463df-115">Visual Studio 2019 バージョン 16.8.4 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="463df-115">Visual Studio 2019 version 16.8.4 or later versions</span></span>](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+desktopguide+wpf)
  - <span data-ttu-id="463df-116">[Visual Studio デスクトップ ワークロード](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-workloads)を選択します</span><span class="sxs-lookup"><span data-stu-id="463df-116">Select the [Visual Studio Desktop workload](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-workloads)</span></span>
  - <span data-ttu-id="463df-117">[.NET 5 の個別のコンポーネント](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-individual-components)を選択します</span><span class="sxs-lookup"><span data-stu-id="463df-117">Select the [.NET 5 individual component](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-individual-components)</span></span>

## <a name="create-a-wpf-app"></a><span data-ttu-id="463df-118">WPF アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="463df-118">Create a WPF app</span></span>

<span data-ttu-id="463df-119">新しいアプリを作成するための最初のステップは、Visual Studio を開き、テンプレートからアプリを生成することです。</span><span class="sxs-lookup"><span data-stu-id="463df-119">The first step to creating a new app is opening Visual Studio and generating the app from a template.</span></span>

01. <span data-ttu-id="463df-120">Visual Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="463df-120">Open Visual Studio.</span></span>
01. <span data-ttu-id="463df-121">**[新しいプロジェクトの作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="463df-121">Select **Create a new project**.</span></span>

    :::image type="content" source="media/create-app-visual-studio/vs-create-new-project.png" alt-text="Visual Studio 2019 for .NET で新しい WPF プロジェクトを作成する":::

01. <span data-ttu-id="463df-123">**[テンプレートの検索]** ボックスに「**wpf**」と入力してから、<kbd>Enter</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="463df-123">In the **Search for templates** box, type **wpf**, and then press <kbd>Enter</kbd>.</span></span>
01. <span data-ttu-id="463df-124">**[コード言語]** ドロップダウンで、 **[C#]** または **[Visual Basic]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="463df-124">In the **code language** dropdown, choose **C#** or **Visual Basic**.</span></span>
01. <span data-ttu-id="463df-125">テンプレートの一覧で、 **[WPF アプリケーション]** を選んでから、 **[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="463df-125">In the templates list, select **WPF Application** and then select **Next**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="463df-126">**[WPF Application (.NET _Framework_)]\(WPF アプリケーション (.NET Framework)\)** テンプレートは選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="463df-126">Don't select the **WPF Application (.NET _Framework_)** template.</span></span>

    :::image type="content" source="media/create-app-visual-studio/vs-template-search-16.8.png" alt-text="Visual Studio 2019 for .NET で WPF テンプレートを検索する":::

01. <span data-ttu-id="463df-128">**[新しいプロジェクトの構成]** ウィンドウで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="463df-128">In the **Configure your new project** window, do the following:</span></span>

    01. <span data-ttu-id="463df-129">**[プロジェクト名]** ボックスに、「**Names**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="463df-129">In the **Project name** box, enter **Names**.</span></span>
    01. <span data-ttu-id="463df-130">**[ソリューションとプロジェクトを同じディレクトリに配置する]** チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="463df-130">Select the **Place solution and project in the same directory** check box.</span></span>
    01. <span data-ttu-id="463df-131">必要に応じて、別の **[場所]** を選んでコードを保存します。</span><span class="sxs-lookup"><span data-stu-id="463df-131">Optionally, choose a different **Location** to save your code.</span></span>
    01. <span data-ttu-id="463df-132">**[作成]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="463df-132">Select the **Create** button.</span></span>

    :::image type="content" source="media/create-app-visual-studio/vs-config-new-project-16.8.png" alt-text="Visual Studio 2019 for .NET で新しい WPF プロジェクトを構成する":::

<!-- THIS IS FOR 16.9 when it's released. Also, change the last child step of the previous step to **Next**

01. In the **Additional information** window, select **.NET 5.0 (Current)** for **Target Framework** and make sure that the **Run on .NET Framework** check box is cleared. Select the **Create** button.

    :::image type="content" source="media/create-app-visual-studio/vs-config-new-project-next.png" alt-text="Select target framework for new WPF project in Visual Studio 2019 for .NET":::
-->

<span data-ttu-id="463df-134">アプリが生成されると、Visual Studio で既定のウィンドウ _MainWindow_ の XAML デザイナー ペインが開くはずです。</span><span class="sxs-lookup"><span data-stu-id="463df-134">Once the app is generated, Visual Studio should open the XAML designer pane for the default window, _MainWindow_.</span></span> <span data-ttu-id="463df-135">デザイナーが表示されない場合は、 **[ソリューション エクスプローラー]** ペインで _MainWindow.xaml_ ファイルをダブルクリックしてデザイナーを開きます。</span><span class="sxs-lookup"><span data-stu-id="463df-135">If the designer isn't visible, double-click on the _MainWindow.xaml_ file in the **Solution Explorer** pane to open the designer.</span></span>

### <a name="important-parts-of-visual-studio"></a><span data-ttu-id="463df-136">Visual Studio の重要な部分</span><span class="sxs-lookup"><span data-stu-id="463df-136">Important parts of Visual Studio</span></span>

<span data-ttu-id="463df-137">Visual Studio での WPF のサポートには、アプリを作成するときにやりとりする 5 つの重要なコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="463df-137">Support for WPF in Visual Studio has five important components that you'll interact with as you create an app:</span></span>

:::image type="content" source="media/create-app-visual-studio/vs-main-window.png" alt-text=".NET 用の WPF プロジェクトを作成するときに理解しておく必要のある Visual Studio の重要なコンポーネント":::

01. <span data-ttu-id="463df-139">ソリューション エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="463df-139">Solution Explorer</span></span>

    <span data-ttu-id="463df-140">プロジェクトのファイル、コード、ウィンドウ、リソースのすべてがこのペインに表示されます。</span><span class="sxs-lookup"><span data-stu-id="463df-140">All of your project files, code, windows, resources, will appear in this pane.</span></span>

02. <span data-ttu-id="463df-141">Properties</span><span class="sxs-lookup"><span data-stu-id="463df-141">Properties</span></span>

    <span data-ttu-id="463df-142">このペインには、選択した項目に基づいて構成できるプロパティ設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="463df-142">This pane shows property settings you can configure based on the item selected.</span></span> <span data-ttu-id="463df-143">たとえば、 **[ソリューション エクスプローラー]** から項目を選択した場合、そのファイルに関連するプロパティ設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="463df-143">For example, if you select an item from **Solution Explorer**, you'll see property settings related to the file.</span></span> <span data-ttu-id="463df-144">**[デザイナー]** でオブジェクトを選択した場合は、その項目の設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="463df-144">If you select an object in the **Designer**, you'll see settings for that item.</span></span>

03. <span data-ttu-id="463df-145">ツールボックス</span><span class="sxs-lookup"><span data-stu-id="463df-145">Toolbox</span></span>

    <span data-ttu-id="463df-146">ツールボックスには、フォームに追加できるすべてのコントロールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="463df-146">The toolbox contains all of the controls you can add to a form.</span></span> <span data-ttu-id="463df-147">現在のフォームにコントロールを追加するには、コントロールをダブルクリックするか、コントロールをドラッグ アンド ドロップします。</span><span class="sxs-lookup"><span data-stu-id="463df-147">To add a control to the current form, double-click a control or drag-and-drop the control.</span></span>

04. <span data-ttu-id="463df-148">XAML デザイナー</span><span class="sxs-lookup"><span data-stu-id="463df-148">XAML designer</span></span>

    <span data-ttu-id="463df-149">これは、XAML ドキュメント用のデザイナーです。</span><span class="sxs-lookup"><span data-stu-id="463df-149">This is the designer for a XAML document.</span></span> <span data-ttu-id="463df-150">対話型であり、 **[ツールボックス]** からオブジェクトをドラッグ アンド ドロップすることができます。</span><span class="sxs-lookup"><span data-stu-id="463df-150">It's interactive and you can drag-and-drop objects from the **Toolbox**.</span></span> <span data-ttu-id="463df-151">デザイナーで項目を選択して移動することにより、アプリのユーザー インターフェイス (UI) を視覚的に作成できます。</span><span class="sxs-lookup"><span data-stu-id="463df-151">By selecting and moving items in the designer, you can visually compose the user interface (UI) for your app.</span></span>

    <span data-ttu-id="463df-152">デザイナーとエディターの両方が表示されている場合は、一方に対する変更がもう一方に反映されます。</span><span class="sxs-lookup"><span data-stu-id="463df-152">When both the designer and editor are visible, changes to one is reflected in the other.</span></span> <span data-ttu-id="463df-153">デザイナーで項目を選択すると、 **[プロパティ]** ペインに、そのオブジェクトに関するプロパティと属性が表示されます。</span><span class="sxs-lookup"><span data-stu-id="463df-153">When you select items in the designer, the **Properties** pane displays the properties and attributes about that object.</span></span>

05. <span data-ttu-id="463df-154">XAML コード エディター</span><span class="sxs-lookup"><span data-stu-id="463df-154">XAML code editor</span></span>

    <span data-ttu-id="463df-155">これは、XAML ドキュメント用の XAML コード エディターです。</span><span class="sxs-lookup"><span data-stu-id="463df-155">This is the XAML code editor for a XAML document.</span></span> <span data-ttu-id="463df-156">XAML コード エディターは、デザイナーを使用せずに手動で UI を作成する手段です。</span><span class="sxs-lookup"><span data-stu-id="463df-156">The XAML code editor is a way to craft your UI by hand without a designer.</span></span> <span data-ttu-id="463df-157">デザイナーにコントロールが追加されたときに、そのデザイナーによってコントロールのプロパティの値が推論される場合があります。</span><span class="sxs-lookup"><span data-stu-id="463df-157">The designer may infer the values of properties on a control when the control is added in the designer.</span></span> <span data-ttu-id="463df-158">XAML コード エディターを使用すると、より多くの制御を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="463df-158">The XAML code editor gives you a lot more control.</span></span>

    <span data-ttu-id="463df-159">デザイナーとエディターの両方が表示されている場合は、一方に対する変更がもう一方に反映されます。</span><span class="sxs-lookup"><span data-stu-id="463df-159">When both the designer and editor are visible, changes to one is reflected in the other.</span></span> <span data-ttu-id="463df-160">コード エディターでテキスト キャレットを移動すると、 **[プロパティ]** ペインに、そのオブジェクトに関するプロパティと属性が表示されます。</span><span class="sxs-lookup"><span data-stu-id="463df-160">As you navigate the text caret in the code editor, the **Properties** pane displays the properties and attributes about that object.</span></span>

## <a name="target-net-50"></a><span data-ttu-id="463df-161">ターゲット .NET 5.0</span><span class="sxs-lookup"><span data-stu-id="463df-161">Target .NET 5.0</span></span>

<span data-ttu-id="463df-162">プロジェクトを作成した後、ターゲット フレームワークを .NET 5.0 に変更します。</span><span class="sxs-lookup"><span data-stu-id="463df-162">After you create your project, change the target framework to .NET 5.0.</span></span> <span data-ttu-id="463df-163">**[ソリューション エクスプローラー]** で、_Names_ プロジェクト ファイルをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="463df-163">Double-click on the _Names_ project file in the **Solution Explorer**.</span></span> <span data-ttu-id="463df-164">これにより、プロジェクト ファイルが開き、編集できます。</span><span class="sxs-lookup"><span data-stu-id="463df-164">This opens up the project file for editing.</span></span> <span data-ttu-id="463df-165">`<TargetFramework>` 要素を `net5.0-windows` に設定します。</span><span class="sxs-lookup"><span data-stu-id="463df-165">Set the `<TargetFramework>` element to `net5.0-windows`:</span></span>

```xml
<TargetFramework>net5.0-windows</TargetFramework>
```

<span data-ttu-id="463df-166">プロジェクト ファイルを保存してから、エディター タブを閉じます。</span><span class="sxs-lookup"><span data-stu-id="463df-166">Save the project file and then close the editor tab.</span></span>

## <a name="examine-the-xaml"></a><span data-ttu-id="463df-167">XAML を確認する</span><span class="sxs-lookup"><span data-stu-id="463df-167">Examine the XAML</span></span>

<span data-ttu-id="463df-168">プロジェクトが作成された後、XAML コード エディターが表示されます。ここには、ウィンドウを表示するための最小限の XAML コードがあります。</span><span class="sxs-lookup"><span data-stu-id="463df-168">After your project is created, the XAML code editor is visible with a minimal amount of XAML code to display the window.</span></span> <span data-ttu-id="463df-169">エディターが開いていない場合は、 **[ソリューション エクスプローラー]** で _MainWindow.xaml_ 項目をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="463df-169">If the editor isn't open, double-click the _MainWindow.xaml_ item in the **Solution Explorer**.</span></span> <span data-ttu-id="463df-170">次のような XAML が表示されるはずです。</span><span class="sxs-lookup"><span data-stu-id="463df-170">You should see XAML similar to the following:</span></span>

```xaml
<Window x:Class="Names.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:Names"
        mc:Ignorable="d"
        Title="MainWindow" Height="450" Width="800">
    <Grid>

    </Grid>
</Window>
```

<span data-ttu-id="463df-171">わかりやすくするために、この XAML コードを分割してみましょう。</span><span class="sxs-lookup"><span data-stu-id="463df-171">Let's break down this XAML code to understand it better.</span></span> <span data-ttu-id="463df-172">XAML は、WPF で使用されるコンパイラによって処理できるシンプルな XML です。</span><span class="sxs-lookup"><span data-stu-id="463df-172">XAML is simply XML that can be processed by the compilers that WPF uses.</span></span> <span data-ttu-id="463df-173">WPF UI を記述し、.NET コードとやりとりします。</span><span class="sxs-lookup"><span data-stu-id="463df-173">It describes the WPF UI and interacts with .NET code.</span></span> <span data-ttu-id="463df-174">XAML を理解するには、少なくとも XML の基本をよく理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="463df-174">To understand XAML, you should, at a minimum, be familiar with the basics of XML.</span></span>

<span data-ttu-id="463df-175">ドキュメントのルート `<Window>` は、XAML ファイルによって記述されるオブジェクトの型を表します。</span><span class="sxs-lookup"><span data-stu-id="463df-175">The document root `<Window>` represents the type of object being described by the XAML file.</span></span> <span data-ttu-id="463df-176">次の 8 つの属性が宣言されており、これらは一般的に 3 つのカテゴリに属しています。</span><span class="sxs-lookup"><span data-stu-id="463df-176">There are eight attributes declared, and they generally belong to three categories:</span></span>

- <span data-ttu-id="463df-177">名前空間</span><span class="sxs-lookup"><span data-stu-id="463df-177">Namespaces</span></span>

  <span data-ttu-id="463df-178">XML 名前空間で XML に構造体が提供され、これにより、ファイル内での宣言が許可されるものとされないものが決まります。</span><span class="sxs-lookup"><span data-stu-id="463df-178">An XML namespace provides structure to the XML, determining what is or isn't allowed to be declared in the file.</span></span>

  <span data-ttu-id="463df-179">メインの `xmlns` 属性で、ファイル全体の XML 名前空間がインポートされます。この場合、WPF によって宣言される型にマップされます。</span><span class="sxs-lookup"><span data-stu-id="463df-179">The main `xmlns` attribute imports the XML namespace for the entire file, and in this case, maps to the types declared by WPF.</span></span> <span data-ttu-id="463df-180">その他の XML 名前空間でプレフィックスが宣言され、XAML ファイル用のその他の型とオブジェクトがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="463df-180">The other XML namespaces declare a prefix and import other types and objects for the XAML file.</span></span> <span data-ttu-id="463df-181">たとえば、`xmlns:local` 名前空間の場合、`local` プレフィックスが宣言され、プロジェクトによって宣言されたオブジェクト (`Names` コード名前空間で宣言されたもの) にマップされます。</span><span class="sxs-lookup"><span data-stu-id="463df-181">For example, the `xmlns:local` namespace declares the `local` prefix and maps to the objects declared by your project, the ones declared in the `Names` code namespace.</span></span>

- <span data-ttu-id="463df-182">`x:Class` 属性</span><span class="sxs-lookup"><span data-stu-id="463df-182">`x:Class` attribute</span></span>

  <span data-ttu-id="463df-183">この属性で、`<Window>` がコードによって定義された型にマップされます。これは、`Names.MainWindow` クラスである _MainWindow.xaml.cs_ または _MainWindow.xaml.vb_ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="463df-183">This attribute maps the `<Window>` to the type defined by your code: the _MainWindow.xaml.cs_ or _MainWindow.xaml.vb_ file, which is the `Names.MainWindow` class.</span></span>

- <span data-ttu-id="463df-184">`Title` 属性</span><span class="sxs-lookup"><span data-stu-id="463df-184">`Title` attribute</span></span>

  <span data-ttu-id="463df-185">XAML オブジェクトで宣言される通常の属性により、そのオブジェクトのプロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="463df-185">Any normal attribute declared on the XAML object sets a property of that object.</span></span> <span data-ttu-id="463df-186">この場合、`Title` 属性によって `Window.Title` プロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="463df-186">In this case the `Title` attribute sets the `Window.Title` property.</span></span>

## <a name="change-the-window"></a><span data-ttu-id="463df-187">ウィンドウを変更する</span><span class="sxs-lookup"><span data-stu-id="463df-187">Change the window</span></span>

<span data-ttu-id="463df-188">まず、プロジェクトを実行して、既定の出力を確認してみましょう。</span><span class="sxs-lookup"><span data-stu-id="463df-188">First, let's run the project and see the default output.</span></span> <span data-ttu-id="463df-189">ポップアップ表示されるウィンドウには、コントロールはなく、**MainWindow** というタイトルが示されます。</span><span class="sxs-lookup"><span data-stu-id="463df-189">You'll see that a window that pops up, without any controls, and a title of **MainWindow**:</span></span>

:::image type="content" source="media/create-app-visual-studio/app-default.png" alt-text="空の WPF アプリ":::

<span data-ttu-id="463df-191">例のアプリの場合、このウィンドウは大きすぎて、タイトル バーがわかりにくくなっています。</span><span class="sxs-lookup"><span data-stu-id="463df-191">For our example app, this window is too large, and the title bar isn't descriptive.</span></span> <span data-ttu-id="463df-192">XAML の適切な属性を次の値に変更して、ウィンドウのタイトルとサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="463df-192">Change the title and size of the window by changing the appropriate attributes in the XAML to the following values:</span></span>

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/Start.xaml" highlight="8":::

## <a name="prepare-the-layout"></a><span data-ttu-id="463df-193">レイアウトを準備する</span><span class="sxs-lookup"><span data-stu-id="463df-193">Prepare the layout</span></span>

<span data-ttu-id="463df-194">WPF には、さまざまなレイアウト コントロールを持つ強力なレイアウト システムが用意されています。</span><span class="sxs-lookup"><span data-stu-id="463df-194">WPF provides a powerful layout system with many different layout controls.</span></span> <span data-ttu-id="463df-195">レイアウト コントロールは、子コントロールを配置したりサイズを設定したりするのに役立ち、自動的に実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="463df-195">Layout controls help place and size child controls, and can even do so automatically.</span></span> <span data-ttu-id="463df-196">この XAML に用意されている既定のレイアウト コントロールは、`<Grid>` コントロールです。</span><span class="sxs-lookup"><span data-stu-id="463df-196">The default layout control provided to you in this XAML is the `<Grid>` control.</span></span>

<span data-ttu-id="463df-197">`Grid` コントロールを使用すると、テーブルと同じように行と列を定義し、特定の行と列の組み合わせの境界内にコントロールを配置できます。</span><span class="sxs-lookup"><span data-stu-id="463df-197">The `Grid` control lets you define rows and columns, much like a table, and place controls within the bounds of a specific row and column combination.</span></span> <span data-ttu-id="463df-198">`Grid` には、任意の数の子コントロールまたはその他のレイアウト コントロールを追加できます。</span><span class="sxs-lookup"><span data-stu-id="463df-198">You can have any number of child controls or other layout controls added to the `Grid`.</span></span> <span data-ttu-id="463df-199">たとえば、特定の行と列の組み合わせに別の `Grid` コントロールを配置できます。その後、新しい `Grid` でより多くの行と列を定義し、独自の子を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="463df-199">For example, you can place another `Grid` control in a specific row and column combination, and that new `Grid` can then define more rows and columns and have its own children.</span></span>

<span data-ttu-id="463df-200">`<Grid>` コントロールにより、コントロールが配置される行と列が定義されます。</span><span class="sxs-lookup"><span data-stu-id="463df-200">The `<Grid>` control defines rows and columns in which your controls will be.</span></span> <span data-ttu-id="463df-201">グリッドには常に単一の行と列が宣言されています。つまり、グリッドは既定で単一のセルになります。</span><span class="sxs-lookup"><span data-stu-id="463df-201">A grid always has a single row and column declared, meaning, the grid by default is a single cell.</span></span> <span data-ttu-id="463df-202">その場合、実際にはそれほど柔軟にコントロールを配置できません。</span><span class="sxs-lookup"><span data-stu-id="463df-202">That doesn't really give you much flexibility in placing controls.</span></span>

<span data-ttu-id="463df-203">新しい行と列を追加する前に、`<Grid>` 要素に新しい属性 (`Margin="10"`) を追加します。</span><span class="sxs-lookup"><span data-stu-id="463df-203">Before we add the new rows and columns, add a new attribute to the `<Grid>` element: `Margin="10"`.</span></span> <span data-ttu-id="463df-204">これでウィンドウからグリッドがインセットされ、少し見栄えが良くなります。</span><span class="sxs-lookup"><span data-stu-id="463df-204">This insets the grid from the window and makes it look a little nicer.</span></span>

<span data-ttu-id="463df-205">次に、2 つの行と 2 つの列を定義し、グリッドを 4 つのセルに分割します。</span><span class="sxs-lookup"><span data-stu-id="463df-205">Next, define two rows and two columns, dividing the grid into four cells:</span></span>

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/LayoutStep2.xaml" highlight="9-21":::

<span data-ttu-id="463df-206">XAML コード エディターまたは XAML デザイナーでグリッドを選択すると、XAML デザイナーに各行と列が表示されることがわかります。</span><span class="sxs-lookup"><span data-stu-id="463df-206">Select the grid in either the XAML code editor or XAML designer, you'll see that the XAML designer shows each row and column:</span></span>

:::image type="content" source="media/create-app-visual-studio/vs-designer-grid-rows-columns.png" alt-text="グリッドに余白が設定されている WPF アプリ":::

## <a name="add-the-first-control"></a><span data-ttu-id="463df-208">最初のコントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="463df-208">Add the first control</span></span>

<span data-ttu-id="463df-209">これでグリッドが作成されたので、コントロールの追加を開始できます。</span><span class="sxs-lookup"><span data-stu-id="463df-209">Now that the grid has been created, we can start adding controls to it.</span></span> <span data-ttu-id="463df-210">まず、ラベル コントロールから始めます。</span><span class="sxs-lookup"><span data-stu-id="463df-210">First, start with the label control.</span></span> <span data-ttu-id="463df-211">`<Grid>` 要素内で、行と列の定義の後に新しい `<Label>` 要素を作成し、`Names` の文字列値を指定します。</span><span class="sxs-lookup"><span data-stu-id="463df-211">Create a new `<Label>` element inside the `<Grid>` element, after the row and column definitions, and give it a string value of `Names`:</span></span>

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/LayoutStep3.xaml" range="9-23" highlight="13":::

<span data-ttu-id="463df-212">`<Label>Names</Label>` でコンテンツ `Names` が定義されます。</span><span class="sxs-lookup"><span data-stu-id="463df-212">The `<Label>Names</Label>` defines the content `Names`.</span></span> <span data-ttu-id="463df-213">コントロールによっては、コンテンツの処理方法が理解されるものとされないものがあります。</span><span class="sxs-lookup"><span data-stu-id="463df-213">Some controls understand how to handle content, others don't.</span></span> <span data-ttu-id="463df-214">コントロールのコンテンツは、`Content` プロパティにマップされます。</span><span class="sxs-lookup"><span data-stu-id="463df-214">The content of a control maps to the `Content` property.</span></span> <span data-ttu-id="463df-215">コンテンツを XAML 属性構文で設定する場合は、この `<Label Content="Names" />` 形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="463df-215">Setting the content through XAML attribute syntax, you would use this format: `<Label Content="Names" />`.</span></span> <span data-ttu-id="463df-216">どちらの方法でも、テキスト `Names` を表示するようにラベルのコンテンツを設定することで同じことが行われます。</span><span class="sxs-lookup"><span data-stu-id="463df-216">Both ways accomplish the same thing, setting the content of the label to display the text `Names`.</span></span>

<span data-ttu-id="463df-217">しかし、問題があります。グリッドの最初の行と列に自動的に割り当てられたラベルが、ウィンドウの半分を占めています。</span><span class="sxs-lookup"><span data-stu-id="463df-217">We have a problem though, the label takes up half the window as it was automatically assigned to the first row and column of the grid.</span></span> <span data-ttu-id="463df-218">最初の行では、その行をラベルに使用するだけなので、それほど多くのスペースは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="463df-218">For our first row, we don't need that much space because we're only going to use that row for the label.</span></span> <span data-ttu-id="463df-219">最初の `<RowDefinition>` の `Height` 属性を `*` から `Auto` に変更します。</span><span class="sxs-lookup"><span data-stu-id="463df-219">Change the `Height` attribute of the first `<RowDefinition>` from `*` to `Auto`.</span></span> <span data-ttu-id="463df-220">`Auto` 値を指定すると、グリッド行のサイズがそのコンテンツ (この場合はラベル コントロール) のサイズに自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="463df-220">The `Auto` value automatically sizes the grid row to the size of its contents, in this case, the label control.</span></span>

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/LayoutStep4.xaml" range="11-14" highlight="2":::

<span data-ttu-id="463df-221">デザイナーに、使用可能な高さを占める量が少なくなったラベルが表示されるようになったことに注目してださい。</span><span class="sxs-lookup"><span data-stu-id="463df-221">Notice that the designer now shows the label occupying a small amount of the available height.</span></span> <span data-ttu-id="463df-222">これで、次の行の占有スペースが増えました。</span><span class="sxs-lookup"><span data-stu-id="463df-222">There's now more room for the next row to occupy.</span></span> <span data-ttu-id="463df-223">ほとんどのコントロールで、見栄えを最高のものにするために占有する必要がある何らかの高さと幅の値が定義されます。</span><span class="sxs-lookup"><span data-stu-id="463df-223">Most controls define some sort of height and width value that they should occupy that looks best for them.</span></span> <span data-ttu-id="463df-224">ラベル コントロールの場合、高さの値があるため、確実に読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="463df-224">In the case of the label control, it has a height value that ensures that you can read it.</span></span>

:::image type="content" source="media/create-app-visual-studio/vs-designer-grid-rows-columns-label.png" alt-text="グリッドに余白が設定され、最初の行にラベル コントロールがある WPF アプリ":::

### <a name="control-placement"></a><span data-ttu-id="463df-226">コントロールの配置</span><span class="sxs-lookup"><span data-stu-id="463df-226">Control placement</span></span>

<span data-ttu-id="463df-227">それでは、コントロールの配置について説明します。</span><span class="sxs-lookup"><span data-stu-id="463df-227">Let's talk about control placement.</span></span> <span data-ttu-id="463df-228">上のセクションで作成されたラベルは、グリッドの行 0 と列 0 に自動的に配置されました。</span><span class="sxs-lookup"><span data-stu-id="463df-228">The label created in the section above was automatically placed in row 0 and column 0 of the grid.</span></span> <span data-ttu-id="463df-229">行と列の番号付けは 0 から始まり、新しい行または列ごとに 1 ずつ増加します。</span><span class="sxs-lookup"><span data-stu-id="463df-229">The numbering for rows and columns starts at 0 and increments by 1 for each new row or column.</span></span> <span data-ttu-id="463df-230">コントロールにグリッドに関する知識はないため、コントロールでグリッド内の配置を制御するプロパティは定義されません。</span><span class="sxs-lookup"><span data-stu-id="463df-230">The control doesn't know anything about the grid, and the control doesn't define any properties to control its placement within the grid.</span></span> <span data-ttu-id="463df-231">コントロールは、コントロールを配置する方法を定義する独自の規則セットを持つ他のレイアウト コントロール内に配置されている場合もあります。</span><span class="sxs-lookup"><span data-stu-id="463df-231">The control could have even been placed within some other layout control which has its own set of rules defining how to place controls.</span></span>

<span data-ttu-id="463df-232">コントロールにグリッドに関する知識がない場合に、別の行または列を使用するようにコントロールに指示するにはどうすればよいでしょうか?</span><span class="sxs-lookup"><span data-stu-id="463df-232">How do you tell a control to use a different row or column when the control has no knowledge of the grid?</span></span> <span data-ttu-id="463df-233">添付プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="463df-233">Attached properties!</span></span> <span data-ttu-id="463df-234">グリッドでは、WPF によって提供される強力なプロパティ システムを利用します。</span><span class="sxs-lookup"><span data-stu-id="463df-234">The grid takes advantage of the powerful property system provided by WPF.</span></span> <span data-ttu-id="463df-235">そのグリッドにより、子コントロールで宣言および使用できる新しいプロパティが定義されます。</span><span class="sxs-lookup"><span data-stu-id="463df-235">The grid defines new properties that the child controls can declare and use.</span></span> <span data-ttu-id="463df-236">これらのプロパティは実際にはコントロール自体には存在せず、コントロールがグリッドに追加されたときにそのグリッドによって添付されます。</span><span class="sxs-lookup"><span data-stu-id="463df-236">The properties don't actually exist on the control itself, they're attached by the grid when the control is added to the grid.</span></span>

<span data-ttu-id="463df-237">グリッドにより、子コントロールの行と列の配置を決定する 2 つのプロパティ (`Grid.Row` と `Grid.Column`) が定義されます。</span><span class="sxs-lookup"><span data-stu-id="463df-237">The grid defines two properties to determine the row and column placement of a child control: `Grid.Row` and `Grid.Column`.</span></span> <span data-ttu-id="463df-238">これらのプロパティがコントロールから省略されている場合、既定値の 0 が設定されていることが示されるため、コントロールはグリッドの行 `0` と列 `0` に配置されます。</span><span class="sxs-lookup"><span data-stu-id="463df-238">If these properties are omitted from the control, it's implied that they have the default values of 0, so, the control is placed in row `0` and column `0` of the grid.</span></span> <span data-ttu-id="463df-239">`Grid.Column` 属性を `1` に設定し、`<Label>` コントロールの配置を変更してみてください。</span><span class="sxs-lookup"><span data-stu-id="463df-239">Try changing the placement of the `<Label>` control by setting the `Grid.Column` attribute to `1`:</span></span>

```xaml
<Label Grid.Column="1">Names</Label>
```

<span data-ttu-id="463df-240">これでラベルが 2 番目の列にどのように移動されたかに注目してください。</span><span class="sxs-lookup"><span data-stu-id="463df-240">Notice how your label now moved to the second column.</span></span> <span data-ttu-id="463df-241">`Grid.Row` および `Grid.Column` 添付プロパティを使用して、次に作成するコントロールを配置できます。</span><span class="sxs-lookup"><span data-stu-id="463df-241">You can use the `Grid.Row` and `Grid.Column` attached properties to place the next controls we'll create.</span></span> <span data-ttu-id="463df-242">しかしここでは、ラベルを行 0 に復元します。</span><span class="sxs-lookup"><span data-stu-id="463df-242">For now though, restore the label to row 0.</span></span>

## <a name="create-the-name-list-box"></a><span data-ttu-id="463df-243">名前リスト ボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="463df-243">Create the name list box</span></span>

<span data-ttu-id="463df-244">これでグリッドのサイズが正しく設定され、ラベルが作成されたので、そのラベルの下の行にリスト ボックス コントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="463df-244">Now that the grid is correctly sized and the label created, add a list box control on the row below the label.</span></span> <span data-ttu-id="463df-245">リスト ボックスは、行 `1` と列 `0` に配置されます。</span><span class="sxs-lookup"><span data-stu-id="463df-245">The list box will be in row `1` and column `0`.</span></span> <span data-ttu-id="463df-246">また、このコントロールに `lstNames` という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="463df-246">We'll also give this control the name of `lstNames`.</span></span> <span data-ttu-id="463df-247">コントロールに名前を付けたら、分離コードで参照できます。</span><span class="sxs-lookup"><span data-stu-id="463df-247">Once a control is named, it can be referenced in the code behind.</span></span> <span data-ttu-id="463df-248">名前は、`x:Name` 属性を使用してコントロールに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="463df-248">The name is assigned to the control with the `x:Name` attribute.</span></span>

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/MoreControls1.xaml" range="9-24" highlight="14":::

## <a name="add-the-remaining-controls"></a><span data-ttu-id="463df-249">残りのコントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="463df-249">Add the remaining controls</span></span>

<span data-ttu-id="463df-250">追加する最後の 2 つのコントロールは、テキスト ボックスとボタンです。ユーザーはこれらを使用して、リスト ボックスに追加する名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="463df-250">The last two controls we'll add are a text box and a button, which the user will use to enter a name to add to the list box.</span></span> <span data-ttu-id="463df-251">しかし、グリッド用にさらに多くの行と列を作成してみるのではなく、これらのコントロールを `<StackPanel>` レイアウト コントロールに配置します。</span><span class="sxs-lookup"><span data-stu-id="463df-251">However, instead of trying to create more rows and columns for the grid, we'll put these controls into the `<StackPanel>` layout control.</span></span>

<span data-ttu-id="463df-252">スタック パネルとグリッドでは、コントロールの配置方法が異なります。</span><span class="sxs-lookup"><span data-stu-id="463df-252">The stack panel differs from the grid in how the controls are placed.</span></span> <span data-ttu-id="463df-253">グリッドには `Grid.Row` および `Grid.Column` 添付プロパティを使用してコントロールを配置する場所を指示しますが、スタック パネルは、最初のコントロールを配置し、その後に次のコントロールを配置して、すべてのコントロールが配置されるまで続行することで自動的に動作します。</span><span class="sxs-lookup"><span data-stu-id="463df-253">While you tell the grid where you want the controls to be with the `Grid.Row` and `Grid.Column` attached properties, the stack panel works automatically by placing the first control, then placing the next control after it, continuing until all controls have been placed.</span></span> <span data-ttu-id="463df-254">各コントロールは他のものの下に "スタック" されます。</span><span class="sxs-lookup"><span data-stu-id="463df-254">It "stacks" each control below the other.</span></span>

<span data-ttu-id="463df-255">リスト ボックスの後に `<StackPanel>` コントロールを作成し、グリッド行 `1` 列 `1` に配置します。</span><span class="sxs-lookup"><span data-stu-id="463df-255">Create the `<StackPanel>` control after the list box and put it in grid row `1` column `1`.</span></span> <span data-ttu-id="463df-256">値が `5,0,0,0` の `Margin` という名前の別の属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="463df-256">Add another attribute named `Margin` with a value of `5,0,0,0`:</span></span>

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/MoreControls2.xaml" id="StackPanel1":::

<span data-ttu-id="463df-257">その `Margin` 属性はグリッドで以前に使用されたものですが、入力したのは単一の値 `10` のみです。</span><span class="sxs-lookup"><span data-stu-id="463df-257">The `Margin` attribute was previously used on the grid, but we only put in a single value, `10`.</span></span> <span data-ttu-id="463df-258">ここでは、スタック パネルで `5,0,0,0` という値を使用しました。</span><span class="sxs-lookup"><span data-stu-id="463df-258">Now we've used a value of `5,0,0,0` on the stack panel.</span></span> <span data-ttu-id="463df-259">余白は `Thickness` 型で、両方の値を解釈できます。</span><span class="sxs-lookup"><span data-stu-id="463df-259">The margin is a `Thickness` type and can interpret both values.</span></span> <span data-ttu-id="463df-260">太さでは、四角形のフレームの各辺の **左**、**上**、**右**、**下** の周囲のスペースがそれぞれ定義されます。</span><span class="sxs-lookup"><span data-stu-id="463df-260">A thickness defines the space around each side of a rectangular frame, **left**, **top**, **right**, **bottom**, respectively.</span></span> <span data-ttu-id="463df-261">余白の値が単一の値の場合は、4 辺すべてにその値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="463df-261">If the value for the margin is a single value, it uses that value for all four sides.</span></span>

<span data-ttu-id="463df-262">次に、`<StackPanel>` に `<TextBox>` および `<Button>` コントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="463df-262">Next, create a `<TextBox>` and `<Button>` control in the `<StackPanel>`.</span></span>

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/MoreControls2.xaml" id="StackPanel2":::

<span data-ttu-id="463df-263">ウィンドウのレイアウトが完了しました。</span><span class="sxs-lookup"><span data-stu-id="463df-263">The layout for the window is complete.</span></span> <span data-ttu-id="463df-264">しかし、アプリには実際に機能するロジックがありません。</span><span class="sxs-lookup"><span data-stu-id="463df-264">However, our app doesn't have any logic in it to actually be functional.</span></span> <span data-ttu-id="463df-265">次は、コントロール イベントをコードにフックし、アプリに実際に何かを実行させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="463df-265">Next, we need to hook up the control events to code and get the app to actually do something.</span></span>

## <a name="add-code-for-the-click-event"></a><span data-ttu-id="463df-266">Click イベントのコードを追加する</span><span class="sxs-lookup"><span data-stu-id="463df-266">Add code for the Click event</span></span>

<span data-ttu-id="463df-267">作成した `<Button>` には、ユーザーがボタンを押したときに発生する `Click` イベントがあります。</span><span class="sxs-lookup"><span data-stu-id="463df-267">The `<Button>` we created has a `Click` event that is raised when the user presses the button.</span></span> <span data-ttu-id="463df-268">このイベントをサブスクライブし、リスト ボックスに名前を追加するコードを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="463df-268">You can subscribe to this event and add code to add a name to the list box.</span></span> <span data-ttu-id="463df-269">XAML 属性を追加することによってコントロールのプロパティを設定するのと同じように、XAML 属性を使用してイベントをサブスクライブできます。</span><span class="sxs-lookup"><span data-stu-id="463df-269">Just like you set a property on a control by adding a XAML attribute, you can use a XAML attribute to subscribe to an event.</span></span> <span data-ttu-id="463df-270">`Click` 属性を `ButtonAddName_Click` に設定します</span><span class="sxs-lookup"><span data-stu-id="463df-270">Set the `Click` attribute to `ButtonAddName_Click`</span></span>

:::code language="xaml" source="snippets/create-app-visual-studio/csharp/MoreControls3.xaml" id="ButtonEvent" highlight="3":::

<span data-ttu-id="463df-271">ここで、ハンドラー コードを生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="463df-271">Now you need to generate the handler code.</span></span> <span data-ttu-id="463df-272">`ButtonAddName_Click` を右クリックし、 **[定義へ移動]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="463df-272">Right-click on `ButtonAddName_Click` and select **Go To Definition**.</span></span> <span data-ttu-id="463df-273">これにより、入力したハンドラー名と一致するメソッドが分離コードで自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="463df-273">This will generate a method in the code behind for you that matches the handler name you've entered.</span></span>

:::code language="csharp" source="snippets/create-app-visual-studio/csharp/MoreControls3.xaml.cs" id="ButtonEvent":::
:::code language="vb" source="snippets/create-app-visual-studio/vb/MoreControls3.xaml.vb" id="ButtonEvent":::

<span data-ttu-id="463df-274">次は、これらの 3 つの手順を行うために以下のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="463df-274">Next, add the following code to do these three steps:</span></span>

01. <span data-ttu-id="463df-275">テキスト ボックスに名前が含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="463df-275">Make sure that the text box contains a name.</span></span>
01. <span data-ttu-id="463df-276">テキスト ボックスに入力された名前がまだ存在しないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="463df-276">Validate that the name entered in the text box doesn't already exist.</span></span>
01. <span data-ttu-id="463df-277">リスト ボックスに名前を追加します。</span><span class="sxs-lookup"><span data-stu-id="463df-277">Add the name to the list box.</span></span>

:::code language="csharp" source="snippets/create-app-visual-studio/csharp/Final.xaml.cs" id="FinalCode":::
:::code language="vb" source="snippets/create-app-visual-studio/vb/Final.xaml.vb" id="FinalCode":::

## <a name="run-the-app"></a><span data-ttu-id="463df-278">アプリを実行する</span><span class="sxs-lookup"><span data-stu-id="463df-278">Run the app</span></span>

<span data-ttu-id="463df-279">イベントをコーディングしたので、<kbd>F5</kbd> キーを押すか、メニューから **[デバッグ]**  >  **[デバッグの開始]** を選択して、アプリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="463df-279">Now that the event has been coded, you can run the app by pressing the <kbd>F5</kbd> key or by selecting **Debug** > **Start Debugging** from the menu.</span></span> <span data-ttu-id="463df-280">ウィンドウが表示され、テキスト ボックスに名前を入力し、ボタンをクリックすることでそれを追加できます。</span><span class="sxs-lookup"><span data-stu-id="463df-280">The window is displayed and you can enter a name in the textbox and then add it by clicking the button.</span></span>

:::image type="content" source="media/create-app-visual-studio/app-finished.png" alt-text=".NET アプリ用の Windows Presentation Foundation (WPF) の実行。":::

## <a name="next-steps"></a><span data-ttu-id="463df-282">次のステップ</span><span class="sxs-lookup"><span data-stu-id="463df-282">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="463df-283">Windows Presentation Foundation についてさらに学習する</span><span class="sxs-lookup"><span data-stu-id="463df-283">Learn more about Windows Presentation Foundation</span></span>](../overview/index.md)
