---
title: Windows フォーム アプリを .NET 5 に移行する
description: .NET Framework Windows フォーム アプリケーションを .NET 5 に移植する方法について学習します。
ms.date: 11/02/2020
ms.topic: how-to
ms.openlocfilehash: c855c074090c386f60e783b3a9b2bee9a7704c23
ms.sourcegitcommit: 0a512a7965f8efa476eb024208479e4432a1fa72
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/10/2021
ms.locfileid: "100101834"
---
# <a name="how-to-migrate-a-windows-forms-desktop-app-to-net-5"></a><span data-ttu-id="f214e-103">Windows フォーム デスクトップ アプリを .NET 5 に移行する方法</span><span class="sxs-lookup"><span data-stu-id="f214e-103">How to migrate a Windows Forms desktop app to .NET 5</span></span>

<span data-ttu-id="f214e-104">この記事では、Windows Forms デスクトップ アプリを、.NET Framework から .NET 5 以上に移行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f214e-104">This article describes how to migrate a Windows Forms desktop app from .NET Framework to .NET 5 or later.</span></span> <span data-ttu-id="f214e-105">.NET SDK には、Windows フォーム アプリケーションのサポートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f214e-105">The .NET SDK includes support for Windows Forms applications.</span></span> <span data-ttu-id="f214e-106">Windows Forms は、まだ Windows 専用のフレームワークであるため、Windows 上でのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="f214e-106">Windows Forms is still a Windows-only framework and only runs on Windows.</span></span>

<span data-ttu-id="f214e-107">.NET Framework から .NET 5 にアプリを移行するには、通常、新しいプロジェクト ファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="f214e-107">Migrating your app from .NET Framework to .NET 5 generally requires a new project file.</span></span> <span data-ttu-id="f214e-108">.NET 5 では SDK スタイルのプロジェクト ファイルが使用されますが、.NET Framework では通常、古い Visual Studio プロジェクト ファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="f214e-108">.NET 5 uses SDK-style project files while .NET Framework typically uses the older Visual Studio project file.</span></span> <span data-ttu-id="f214e-109">テキスト エディターで Visual Studio プロジェクト ファイルを開いたことがある場合は、それがどの程度詳細であるかはご存じでしょう。</span><span class="sxs-lookup"><span data-stu-id="f214e-109">If you've ever opened a Visual Studio project file in a text editor, you know how verbose it is.</span></span> <span data-ttu-id="f214e-110">SDK スタイルのプロジェクトはより小さく、古いプロジェクト ファイル形式の場合と同じ数のエントリは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="f214e-110">SDK-style projects are smaller and don't require as many entries as the older project file format does.</span></span>

<span data-ttu-id="f214e-111">.NET 5 の詳細については、「[.NET の概要](/dotnet/core/introduction)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f214e-111">To learn more about .NET 5, see [Introduction to .NET](/dotnet/core/introduction).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f214e-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="f214e-112">Prerequisites</span></span>

- [<span data-ttu-id="f214e-113">Visual Studio 2019 バージョン 16.8 Preview</span><span class="sxs-lookup"><span data-stu-id="f214e-113">Visual Studio 2019 version 16.8 Preview</span></span>](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+desktopguide+winforms)

  - <span data-ttu-id="f214e-114">[Visual Studio デスクトップ ワークロード](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-workloads)を選択します。</span><span class="sxs-lookup"><span data-stu-id="f214e-114">Select the [Visual Studio Desktop workload](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-workloads).</span></span>

  - <span data-ttu-id="f214e-115">[.NET 5 の個別のコンポーネント](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-individual-components)を選択します。</span><span class="sxs-lookup"><span data-stu-id="f214e-115">Select the [.NET 5 individual component](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-individual-components).</span></span>

- <span data-ttu-id="f214e-116">Visual Studio のプレビュー版 WinForms デザイナー。</span><span class="sxs-lookup"><span data-stu-id="f214e-116">Preview WinForms designer in Visual Studio.</span></span>

  <span data-ttu-id="f214e-117">デザイナーを有効にするには、 **[ツール]**  >  **[オプション]**  >  **[環境]**  >  **[プレビュー機能]** に移動し、 **[Use the preview Windows Forms designer for .NET Core apps]\(プレビュー版 Windows フォーム デザイナー (.NET Core アプリ) を使用する\)** オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="f214e-117">To enable the designer, go to **Tools** > **Options** > **Environment** > **Preview Features** and select the **Use the preview Windows Forms designer for .NET Core apps** option.</span></span>

- <span data-ttu-id="f214e-118">この記事では、[絵合わせゲーム](https://github.com/dotnet/samples/tree/master/windowsforms/matching-game/net45/)のサンプル アプリを使用します。</span><span class="sxs-lookup"><span data-stu-id="f214e-118">This article uses the [Matching game](https://github.com/dotnet/samples/tree/master/windowsforms/matching-game/net45/) sample app.</span></span> <span data-ttu-id="f214e-119">これに従う場合は、アプリケーションをダウンロードして Visual Studio で開きます。</span><span class="sxs-lookup"><span data-stu-id="f214e-119">If you want to follow along, download and open the application in Visual Studio.</span></span> <span data-ttu-id="f214e-120">それ以外の場合は、独自のアプリを使用します。</span><span class="sxs-lookup"><span data-stu-id="f214e-120">Otherwise, use your own app.</span></span>

### <a name="consider"></a><span data-ttu-id="f214e-121">次の例を考えてみましょう</span><span class="sxs-lookup"><span data-stu-id="f214e-121">Consider</span></span>

<span data-ttu-id="f214e-122">.NET Framework Windows フォーム アプリケーションを移行するときに、考慮する必要がある点がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="f214e-122">When migrating a .NET Framework Windows Forms application, there are a few things you must consider.</span></span>

01. <span data-ttu-id="f214e-123">アプリケーションが移行に適した候補であることを確認する。</span><span class="sxs-lookup"><span data-stu-id="f214e-123">Check that your application is a good candidate for migration.</span></span>

    <span data-ttu-id="f214e-124">[.NET Portability Analyzer](/dotnet/standard/analyzers/portability-analyzer) を使用して、プロジェクトで .NET 5 に移行するかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="f214e-124">Use the [.NET Portability Analyzer](/dotnet/standard/analyzers/portability-analyzer) to determine if your project will migrate to .NET 5.</span></span> <span data-ttu-id="f214e-125">プロジェクトに .NET 5 に関する問題がある場合は、これらの問題を特定するのにアナライザーが役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f214e-125">If your project has issues with .NET 5, the analyzer helps you identify those problems.</span></span> <span data-ttu-id="f214e-126">.NET Portability Analyzer ツールは、Visual Studio の拡張機能としてインストールすることも、コマンド ラインから使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="f214e-126">The .NET Portability Analyzer tool can be installed as a Visual Studio extension or used from the command line.</span></span> <span data-ttu-id="f214e-127">詳細については、[.NET Portability Analyzer](/dotnet/standard/analyzers/portability-analyzer) に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f214e-127">For more information, see [.NET Portability Analyzer](/dotnet/standard/analyzers/portability-analyzer).</span></span>

01. <span data-ttu-id="f214e-128">Windows Forms の別のバージョンを使用している。</span><span class="sxs-lookup"><span data-stu-id="f214e-128">You're using a different version of Windows Forms.</span></span>

    <span data-ttu-id="f214e-129">.NET Core 3.0 がリリースされたときに、Windows フォームは [GitHub でオープン ソース](https://github.com/dotnet/winforms)になりました。</span><span class="sxs-lookup"><span data-stu-id="f214e-129">When .NET Core 3.0 was released, Windows Forms went [open source on GitHub](https://github.com/dotnet/winforms).</span></span> <span data-ttu-id="f214e-130">.NET 5 用の Windows フォームのコードは、.NET Framework Windows フォーム コード ベースからの 1 つの分岐です。</span><span class="sxs-lookup"><span data-stu-id="f214e-130">The code for Windows Forms for .NET 5 is a fork of the .NET Framework Windows Forms codebase.</span></span> <span data-ttu-id="f214e-131">いくつか違いがあるため、アプリの移行が困難になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f214e-131">It's possible some differences exist and your app will be difficult to migrate.</span></span>

01. <span data-ttu-id="f214e-132">[Windows 互換機能パック][compat-pack]が移行に役立つ可能性がある。</span><span class="sxs-lookup"><span data-stu-id="f214e-132">The [Windows Compatibility Pack][compat-pack] may help you migrate.</span></span>

    <span data-ttu-id="f214e-133">.NET Framework で利用できる一部の API は、.NET 5 では利用できません。</span><span class="sxs-lookup"><span data-stu-id="f214e-133">Some APIs that are available in .NET Framework aren't available in .NET 5.</span></span> <span data-ttu-id="f214e-134">[Windows 互換機能パック][compat-pack]を使用すると、これらの API の多くが追加され、Windows Forms アプリに .NET 5 との互換性を持たせるのに役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="f214e-134">The [Windows Compatibility Pack][compat-pack] adds many of these APIs and may help your Windows Forms app become compatible with .NET 5.</span></span>

01. <span data-ttu-id="f214e-135">自分のプロジェクトで使用されている NuGet パッケージを更新する。</span><span class="sxs-lookup"><span data-stu-id="f214e-135">Update the NuGet packages used by your project.</span></span>

    <span data-ttu-id="f214e-136">移行する前に、常に NuGet パッケージの最新バージョンを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f214e-136">It's always a good practice to use the latest versions of NuGet packages before any migration.</span></span> <span data-ttu-id="f214e-137">アプリケーションで NuGet パッケージを参照している場合は、最新バージョンに更新してください。</span><span class="sxs-lookup"><span data-stu-id="f214e-137">If your application is referencing any NuGet packages, update them to the latest version.</span></span> <span data-ttu-id="f214e-138">アプリケーションが正常にビルドされることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f214e-138">Ensure your application builds successfully.</span></span> <span data-ttu-id="f214e-139">アップグレード後にパッケージ エラーが発生した場合は、コードを壊さない最新のバージョンにパッケージをダウングレードします。</span><span class="sxs-lookup"><span data-stu-id="f214e-139">After upgrading, if there are any package errors, downgrade the package to the latest version that doesn't break your code.</span></span>

## <a name="back-up-your-projects"></a><span data-ttu-id="f214e-140">プロジェクトをバックアップする</span><span class="sxs-lookup"><span data-stu-id="f214e-140">Back up your projects</span></span>

<span data-ttu-id="f214e-141">プロジェクトを移行するための最初の手順は、プロジェクトをバックアップすることです。</span><span class="sxs-lookup"><span data-stu-id="f214e-141">The first step to migrating a project is to back up your project!</span></span> <span data-ttu-id="f214e-142">問題が発生した場合は、バックアップを復元することでコードを元の状態に復元できます。</span><span class="sxs-lookup"><span data-stu-id="f214e-142">If something goes wrong, you can restore your code to its original state by restoring your backup.</span></span> <span data-ttu-id="f214e-143">プロジェクトをバックアップする際に、.NET Portability Analyzer などのツールには頼らないでください (そうするように思われても)。</span><span class="sxs-lookup"><span data-stu-id="f214e-143">Don't rely on tools such as the .NET Portability Analyzer to back up your project, even if they seem to.</span></span> <span data-ttu-id="f214e-144">元のプロジェクトのコピーを個人的に作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f214e-144">It's best to personally create a copy of the original project.</span></span>

## <a name="nuget-packages"></a><span data-ttu-id="f214e-145">NuGet パッケージ</span><span class="sxs-lookup"><span data-stu-id="f214e-145">NuGet packages</span></span>

<span data-ttu-id="f214e-146">プロジェクトで NuGet パッケージが参照されている場合、プロジェクト フォルダー内に **packages.config** ファイルがある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f214e-146">If your project is referencing NuGet packages, you probably have a **packages.config** file in your project folder.</span></span> <span data-ttu-id="f214e-147">SDK スタイルのプロジェクトの場合、NuGet パッケージ参照はプロジェクト ファイルで構成されます。</span><span class="sxs-lookup"><span data-stu-id="f214e-147">With SDK-style projects, NuGet package references are configured in the project file.</span></span> <span data-ttu-id="f214e-148">Visual Studio プロジェクト ファイルでは、必要に応じて、そのプロジェクト ファイルで NuGet パッケージを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="f214e-148">Visual Studio project files can optionally define NuGet packages in the project file too.</span></span> <span data-ttu-id="f214e-149">.NET 5 では、NuGet パッケージに対して **packages.config** は使用されません。</span><span class="sxs-lookup"><span data-stu-id="f214e-149">.NET 5 doesn't use **packages.config** for NuGet packages.</span></span> <span data-ttu-id="f214e-150">移行の前に、NuGet パッケージ参照をプロジェクト ファイルに移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f214e-150">NuGet package references must be migrated into the project file before migration.</span></span>

<span data-ttu-id="f214e-151">**packages.config** ファイルを移行するには、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="f214e-151">To migrate the **packages.config** file, do the following steps:</span></span>

01. <span data-ttu-id="f214e-152">**ソリューション エクスプローラー** で、移行するプロジェクトを見つけます。</span><span class="sxs-lookup"><span data-stu-id="f214e-152">In **Solution explorer**, find the project you're migrating.</span></span>
02. <span data-ttu-id="f214e-153">右クリックで **[packages.config]**  >  **[packages.config を PackageReference に移行する]** の順に進みます。</span><span class="sxs-lookup"><span data-stu-id="f214e-153">Right-click on **packages.config** > **Migrate packages.config to PackageReference**.</span></span>
03. <span data-ttu-id="f214e-154">最上位のパッケージをすべて選択します。</span><span class="sxs-lookup"><span data-stu-id="f214e-154">Select all of the top-level packages.</span></span>

<span data-ttu-id="f214e-155">ビルド レポートは、NuGet パッケージの移行に関する問題を通知するために生成されます。</span><span class="sxs-lookup"><span data-stu-id="f214e-155">A build report is generated to let you know of any issues migrating the NuGet packages.</span></span>

## <a name="project-file"></a><span data-ttu-id="f214e-156">プロジェクト ファイル</span><span class="sxs-lookup"><span data-stu-id="f214e-156">Project file</span></span>

<span data-ttu-id="f214e-157">アプリを移行する次の手順では、プロジェクト ファイルを変換します。</span><span class="sxs-lookup"><span data-stu-id="f214e-157">The next step in migrating your app is converting the project file.</span></span> <span data-ttu-id="f214e-158">前述のように、.NET 5 では SDK スタイルのプロジェクト ファイルが使用され、.NET Framework で使用される Visual Studio プロジェクト ファイルは読み込まれません。</span><span class="sxs-lookup"><span data-stu-id="f214e-158">As previously stated, .NET 5 uses SDK-style project files and won't load the Visual Studio project files that .NET Framework uses.</span></span> <span data-ttu-id="f214e-159">しかし、SDK スタイルのプロジェクトを既に使用している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f214e-159">However, there's the possibility that you're already using SDK-style projects.</span></span> <span data-ttu-id="f214e-160">Visual Studio でその違いを簡単に見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="f214e-160">You can easily spot the difference in Visual Studio.</span></span> <span data-ttu-id="f214e-161">**ソリューション エクスプローラー** でプロジェクト ファイルを右クリックし、 **[プロジェクト ファイルの編集]** メニューオプションを探します。</span><span class="sxs-lookup"><span data-stu-id="f214e-161">Right-click on the project file in **Solution explorer** and look for the **Edit Project File** menu option.</span></span> <span data-ttu-id="f214e-162">このメニュー項目が欠落している場合は、古い Visual Studio プロジェクト形式を使用しているため、アップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f214e-162">If this menu item is missing, you're using the old Visual Studio project format and need to upgrade.</span></span>

<span data-ttu-id="f214e-163">ソリューション内の各プロジェクトを変換します。</span><span class="sxs-lookup"><span data-stu-id="f214e-163">Convert each project in your solution.</span></span> <span data-ttu-id="f214e-164">以前に参照されたサンプル アプリを使用する場合、**MatchingGame** と **MatchingGame.Logic** プロジェクトの両方が変換されます。</span><span class="sxs-lookup"><span data-stu-id="f214e-164">If you're using the sample app previously referenced, both the **MatchingGame** and **MatchingGame.Logic** projects would be converted.</span></span>

<span data-ttu-id="f214e-165">プロジェクトを変換するには、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="f214e-165">To convert a project, do the following steps:</span></span>

01. <span data-ttu-id="f214e-166">**ソリューション エクスプローラー** で、移行するプロジェクトを見つけます。</span><span class="sxs-lookup"><span data-stu-id="f214e-166">In **Solution explorer**, find the project you're migrating.</span></span>
01. <span data-ttu-id="f214e-167">プロジェクトを右クリックし、 **[プロジェクトのアンロード]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f214e-167">Right-click on the project and select **Unload Project**.</span></span>
01. <span data-ttu-id="f214e-168">プロジェクトを右クリックし、 **[プロジェクト ファイルの編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f214e-168">Right-click on the project and select **Edit Project File**.</span></span>
01. <span data-ttu-id="f214e-169">プロジェクトの XML をコピーし、テキスト エディターに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="f214e-169">Copy-and-paste the project XML into a text editor.</span></span> <span data-ttu-id="f214e-170">新しいプロジェクトに内容を簡単に移動できるようにコピーが必要になります。</span><span class="sxs-lookup"><span data-stu-id="f214e-170">You'll want a copy so that it's easy to move content into the new project.</span></span>
01. <span data-ttu-id="f214e-171">ファイルの内容を消去し、次の XML を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="f214e-171">Erase the content of the file and paste the following XML:</span></span>

    ```xml
    <Project Sdk="Microsoft.NET.Sdk">

      <PropertyGroup>
        <OutputType>WinExe</OutputType>
        <TargetFramework>net5.0-windows</TargetFramework>
        <UseWindowsForms>true</UseWindowsForms>
        <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
      </PropertyGroup>

    </Project>
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="f214e-172">ライブラリで `<OutputType>` 設定を定義する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f214e-172">Libraries don't need to define an `<OutputType>` setting.</span></span> <span data-ttu-id="f214e-173">ライブラリ プロジェクトをアップグレードする場合は、そのエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="f214e-173">Remove that entry if you're upgrading a library project.</span></span>

<span data-ttu-id="f214e-174">この XML により、プロジェクトの基本構造が提供されます。</span><span class="sxs-lookup"><span data-stu-id="f214e-174">This XML gives you the basic structure of the project.</span></span> <span data-ttu-id="f214e-175">しかし、古いプロジェクト ファイルのどの設定も含まれていません。</span><span class="sxs-lookup"><span data-stu-id="f214e-175">However, it doesn't contain any of the settings from the old project file.</span></span> <span data-ttu-id="f214e-176">以前にテキスト エディターにコピーした古いプロジェクト情報を使用して、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="f214e-176">Using the old project information you previously copied to a text editor, do the following steps:</span></span>

01. <span data-ttu-id="f214e-177">古いプロジェクト ファイルの次の要素を、新しいプロジェクト ファイルの `<PropertyGroup>` 要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="f214e-177">Copy the following elements from the old project file into the `<PropertyGroup>` element in the new project file:</span></span>

    - `<RootNamespace>`
    - `<AssemblyName>`

    <span data-ttu-id="f214e-178">プロジェクト ファイルは次の XML のようになるはずです。</span><span class="sxs-lookup"><span data-stu-id="f214e-178">Your project file should look similar to the following XML:</span></span>

    ```xml
    <Project Sdk="Microsoft.NET.Sdk">

      <PropertyGroup>
        <OutputType>WinExe</OutputType>
        <TargetFramework>net5.0-windows</TargetFramework>
        <UseWindowsForms>true</UseWindowsForms>
        <GenerateAssemblyInfo>false</GenerateAssemblyInfo>

        <RootNamespace>MatchingGame</RootNamespace>
        <AssemblyName>MatchingGame</AssemblyName>
      </PropertyGroup>

    </Project>
    ```

01. <span data-ttu-id="f214e-179">`<ProjectReference>` または `<PackageReference>` を含む古いプロジェクト ファイルの `<ItemGroup>` 要素を、`</PropertyGroup>` 終了タグの後の新しいファイルにコピーします。</span><span class="sxs-lookup"><span data-stu-id="f214e-179">Copy the `<ItemGroup>` elements from the old project file that contain `<ProjectReference>` or `<PackageReference>` into the new file after the `</PropertyGroup>` closing tag.</span></span>

    <span data-ttu-id="f214e-180">プロジェクト ファイルは次の XML のようになるはずです。</span><span class="sxs-lookup"><span data-stu-id="f214e-180">Your project file should look similar to the following XML:</span></span>

    ```xml
    <Project Sdk="Microsoft.NET.Sdk">

      <PropertyGroup>
        (contains settings previously described)
      </PropertyGroup>

      <ItemGroup>
        <ProjectReference Include="..\MatchingGame.Logic\MatchingGame.Logic.csproj">
          <Project>{36b3e6e2-a9ae-4924-89ae-7f0120ce08bd}</Project>
          <Name>MatchingGame.Logic</Name>
        </ProjectReference>
      </ItemGroup>
      <ItemGroup>
        <PackageReference Include="MetroFramework">
          <Version>1.2.0.3</Version>
        </PackageReference>
      </ItemGroup>

    </Project>
    ```

    <span data-ttu-id="f214e-181">`<ProjectReference>` 要素には子の `<Project>` と `<Name>` は必要でないため、これらの設定は削除できます。</span><span class="sxs-lookup"><span data-stu-id="f214e-181">The `<ProjectReference>` elements don't need the `<Project>` and `<Name>` children, so you can remove those settings:</span></span>

    ```xml
    <ItemGroup>
      <ProjectReference Include="..\MatchingGame.Logic\MatchingGame.Logic.csproj" />
    </ItemGroup>
    ```

### <a name="resources-and-settings"></a><span data-ttu-id="f214e-182">リソースと設定</span><span class="sxs-lookup"><span data-stu-id="f214e-182">Resources and settings</span></span>

<span data-ttu-id="f214e-183">.NET Framework プロジェクトと .NET 5 で使用される SDK スタイルのプロジェクトの違いで 1 つ注意する点は、.NET Framework プロジェクトではコード ファイルにオプトイン モデルが使用されるということです。</span><span class="sxs-lookup"><span data-stu-id="f214e-183">One thing to note about the difference between .NET Framework projects and the SDK-style projects used by .NET 5 is that .NET Framework projects use an opt-in model for code files.</span></span> <span data-ttu-id="f214e-184">コンパイルするコード ファイルはすべて、自分のプロジェクト ファイルで明示的に定義される必要があります。</span><span class="sxs-lookup"><span data-stu-id="f214e-184">Any code file you want to compile needs to be explicitly defined in your project file.</span></span> <span data-ttu-id="f214e-185">SDK スタイルのプロジェクトは逆になり、既定でオプトアウト動作に設定されます。プロジェクトのディレクトリ以下から始まるコード ファイルはすべて、自分のプロジェクトに自動的に含まれます。</span><span class="sxs-lookup"><span data-stu-id="f214e-185">SDK-style projects are reverse, they default to opt-out behavior: All code files starting from the project's directory and below are automatically included in your project.</span></span> <span data-ttu-id="f214e-186">これらのエントリがシンプルで設定されていない場合は、これらを移行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f214e-186">You don't need to migrate these entries if they are simple and without settings.</span></span> <span data-ttu-id="f214e-187">これは、_resx_ などのその他の一般的なファイルと同じです。</span><span class="sxs-lookup"><span data-stu-id="f214e-187">This is the same for other common files such as _resx_.</span></span>

<span data-ttu-id="f214e-188">Windows フォーム プロジェクトには、_Properties/Settings.settings_ や _Properties/Resources.resx_ などの特定のファイルも含まれています。</span><span class="sxs-lookup"><span data-stu-id="f214e-188">Windows Forms projects also include Windows Form project specific files, such as _Properties/Settings.settings_ and _Properties/Resources.resx_.</span></span> <span data-ttu-id="f214e-189">これらのファイルは、元のプロジェクトで宣言されているため、移行する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="f214e-189">These files may need to be migrated they are declared in your original project.</span></span>

<span data-ttu-id="f214e-190">これらのエントリを古いプロジェクト ファイルから、新しいプロジェクトの `<ItemGroup>` 要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="f214e-190">Copy those entries from the old project file into an `<ItemGroup>` element in the new project.</span></span> <span data-ttu-id="f214e-191">エントリをコピーした後、すべての `<Compile Include="value">` 要素を、`Include` ではなく代わりに `Update` 属性を使用するように変更します。</span><span class="sxs-lookup"><span data-stu-id="f214e-191">After you copy the entries, change all `<Compile Include="value">` elements to instead use the `Update` attribute instead of `Include`.</span></span>

- <span data-ttu-id="f214e-192">_Settings.settings_ ファイルの構成をインポートします。</span><span class="sxs-lookup"><span data-stu-id="f214e-192">Import the configuration for the _Settings.settings_ file.</span></span>

  ```xml
  <ItemGroup>
    <None Include="Properties\Settings.settings">
      <Generator>SettingsSingleFileGenerator</Generator>
      <LastGenOutput>Settings.Designer.cs</LastGenOutput>
    </None>
    <Compile Update="Properties\Settings.Designer.cs">
      <AutoGen>True</AutoGen>
      <DependentUpon>Settings.settings</DependentUpon>
      <DesignTimeSharedInput>True</DesignTimeSharedInput>
    </Compile>
  </ItemGroup>
  ```

  <span data-ttu-id="f214e-193">_Properties\Settings.settings_ エントリが `Include` のままになっていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="f214e-193">Notice that the _Properties\Settings.settings_ entry remained `Include`.</span></span> <span data-ttu-id="f214e-194">プロジェクトに _settings_ ファイルが自動的に含まれることはありません。</span><span class="sxs-lookup"><span data-stu-id="f214e-194">The project doesn't automatically include _settings_ files.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="f214e-195">**Visual Basic** プロジェクトの場合、通常は _My Project_ フォルダーが使用されますが、C# プロジェクトの場合は通常、既定のプロジェクト設定ファイルには _Properties_ フォルダーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="f214e-195">**Visual Basic** projects typically use the folder _My Project_ while C# projects typically use the folder _Properties_ for the default project settings file.</span></span>
  
- <span data-ttu-id="f214e-196">_properties/Resources.resx_ ファイルなど、_resx_ ファイルの構成をインポートします。</span><span class="sxs-lookup"><span data-stu-id="f214e-196">Import the configuration for any _resx_ file, such as the _properties/Resources.resx_ file.</span></span> <span data-ttu-id="f214e-197">`Include` 属性が `<Compile>` および `<EmbeddedResource>` 要素で `Update` に設定され、`<SubType>` が `<EmbeddedResource>` から削除されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f214e-197">Notice that the `Include` attribute was set to `Update` on the `<Compile>` and `<EmbeddedResource>` element, and `<SubType>` was removed from `<EmbeddedResource>`:</span></span>

  ```xml
  <ItemGroup>
    <EmbeddedResource Update="Properties\Resources.resx">
      <Generator>ResXFileCodeGenerator</Generator>
      <LastGenOutput>Resources.Designer.cs</LastGenOutput>
    </EmbeddedResource>
    <Compile Update="Properties\Resources.Designer.cs">
      <AutoGen>True</AutoGen>
      <DependentUpon>Resources.resx</DependentUpon>
      <DesignTime>True</DesignTime>
    </Compile>
  </ItemGroup>
  ```

  > [!IMPORTANT]
  > <span data-ttu-id="f214e-198">**Visual Basic** プロジェクトの場合、通常は _My Project_ フォルダーが使用されますが、C# プロジェクトの場合は通常、既定のプロジェクト リソース ファイルには _Properties_ フォルダーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="f214e-198">**Visual Basic** projects typically use the folder _My Project_ while C# projects typically use the folder _Properties_ for the default project resource file.</span></span>

### <a name="visual-basic"></a><span data-ttu-id="f214e-199">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f214e-199">Visual Basic</span></span>

<span data-ttu-id="f214e-200">Visual Basic 言語プロジェクトには追加の構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="f214e-200">Visual Basic language projects require extra configuration.</span></span>

01. <span data-ttu-id="f214e-201">構成ファイルの _My Project\Application.myapp_ 設定をインポートします。</span><span class="sxs-lookup"><span data-stu-id="f214e-201">Import the configuration file _My Project\Application.myapp_ setting.</span></span> <span data-ttu-id="f214e-202">`<Compile>` 要素から、`Include` 属性ではなく `Update` 属性が使用されていることに注目してください。</span><span class="sxs-lookup"><span data-stu-id="f214e-202">Notice that the `<Compile>` element uses the `Update` attribute instead of the `Include` attribute.</span></span>

    ```xml
    <ItemGroup>
      <None Include="My Project\Application.myapp">
        <Generator>MyApplicationCodeGenerator</Generator>
        <LastGenOutput>Application.Designer.vb</LastGenOutput>
      </None>
      <Compile Update="My Project\Application.Designer.vb">
        <AutoGen>True</AutoGen>
        <DependentUpon>Application.myapp</DependentUpon>
        <DesignTime>True</DesignTime>
      </Compile>
    </ItemGroup>
    ```

01. <span data-ttu-id="f214e-203">`<PropertyGroup>` 要素に `<MyType>WindowsForms</MyType>` 設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="f214e-203">Add the `<MyType>WindowsForms</MyType>` setting to the `<PropertyGroup>` element:</span></span>

    ```xml
    <PropertyGroup>
      (contains settings previously described)

      <MyType>WindowsForms</MyType>
    </PropertyGroup>
    ```

    <span data-ttu-id="f214e-204">この設定により、Visual Basic プログラマーが使い慣れている `My` 名前空間メンバーがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="f214e-204">This setting imports the `My` namespace members Visual Basic programmers are familiar with.</span></span>

01. <span data-ttu-id="f214e-205">プロジェクトで定義されている名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="f214e-205">Import the namespaces defined by your project.</span></span>

    <span data-ttu-id="f214e-206">Visual Basic プロジェクトでは、すべてのコード ファイルに名前空間を自動的にインポートできます。</span><span class="sxs-lookup"><span data-stu-id="f214e-206">Visual Basic projects can automatically import namespaces into every code file.</span></span> <span data-ttu-id="f214e-207">`<Import>` を含む古いプロジェクト ファイルの `<ItemGroup>` 要素を、`</PropertyGroup>` 終了タグの後の新しいファイルにコピーします。</span><span class="sxs-lookup"><span data-stu-id="f214e-207">Copy the `<ItemGroup>` elements from the old project file that contain `<Import>` into the new file after the `</PropertyGroup>` closing tag.</span></span>

    ```xml
    <ItemGroup>
      <Import Include="Microsoft.VisualBasic" />
      <Import Include="System" />
      <Import Include="System.Collections" />
      <Import Include="System.Collections.Generic" />
      <Import Include="System.Data" />
      <Import Include="System.Drawing" />
      <Import Include="System.Diagnostics" />
      <Import Include="System.Windows.Forms" />
      <Import Include="System.Linq" />
      <Import Include="System.Xml.Linq" />
      <Import Include="System.Threading.Tasks" />
    </ItemGroup>
    ```

    <span data-ttu-id="f214e-208">`<Import>` ステートメントが見つからない場合、またはプロジェクトのコンパイルに失敗した場合は、少なくともプロジェクトで次の `<Import>` ステートメントが定義されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f214e-208">If you can't find any `<Import>` statements, or your project fails to compile, make sure you at least have the following `<Import>` statements defined in your project:</span></span>

    ```xml
    <ItemGroup>
      <Import Include="System.Data" />
      <Import Include="System.Drawing" />
      <Import Include="System.Windows.Forms" />
    </ItemGroup>
    ```

01. <span data-ttu-id="f214e-209">元のプロジェクトから、`<Option*>` と `<StartupObject>` の設定を `<PropertyGroup>` 要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="f214e-209">From the original project, copy the `<Option*>` and `<StartupObject>` settings to the `<PropertyGroup>` element:</span></span>

    ```xml
    <PropertyGroup>
      (contains settings previously described)

      <OptionExplicit>On</OptionExplicit>
      <OptionCompare>Binary</OptionCompare>
      <OptionStrict>Off</OptionStrict>
      <OptionInfer>On</OptionInfer>
      <StartupObject>MatchingGame.My.MyApplication</StartupObject>
    </PropertyGroup>
    ```

### <a name="reload-the-project"></a><span data-ttu-id="f214e-210">プロジェクトを再度読み込む</span><span class="sxs-lookup"><span data-stu-id="f214e-210">Reload the project</span></span>

<span data-ttu-id="f214e-211">プロジェクトを新しい SDK スタイルの形式に変換した後、Visual Studio でそのプロジェクトを再度読み込みます。</span><span class="sxs-lookup"><span data-stu-id="f214e-211">After you convert a project to the new SDK-style format, reload the project in Visual Studio:</span></span>

01. <span data-ttu-id="f214e-212">**ソリューション エクスプローラー** で、変換したプロジェクトを見つけます。</span><span class="sxs-lookup"><span data-stu-id="f214e-212">In **Solution Explorer**, find the project you converted.</span></span>
01. <span data-ttu-id="f214e-213">プロジェクトを右クリックし、 **[プロジェクトの再読み込み]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f214e-213">Right-click on the project and select **Reload Project**.</span></span>

    <span data-ttu-id="f214e-214">プロジェクトの読み込みに失敗した場合は、そのプロジェクトの XML が間違っている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f214e-214">If the project fails to load, you may have introduced a mistake in the XML of the project.</span></span> <span data-ttu-id="f214e-215">編集のためにプロジェクト ファイルを開き、間違いを特定して修正します。</span><span class="sxs-lookup"><span data-stu-id="f214e-215">Open the project file for editing and try to identify and fix the mistake.</span></span> <span data-ttu-id="f214e-216">間違いが見つからない場合は、やり直してみてください。</span><span class="sxs-lookup"><span data-stu-id="f214e-216">If you can't find a mistake, try starting over.</span></span>

## <a name="edit-appconfig"></a><span data-ttu-id="f214e-217">App.config を編集する</span><span class="sxs-lookup"><span data-stu-id="f214e-217">Edit App.config</span></span>

<span data-ttu-id="f214e-218">アプリに _App.config_ ファイルがある場合は、`<supportedRuntime>` 要素を削除します。</span><span class="sxs-lookup"><span data-stu-id="f214e-218">If your app has an _App.config_ file, remove the `<supportedRuntime>` element:</span></span>

```xml
<supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5" />
```

<span data-ttu-id="f214e-219">*App.config* ファイルで考慮する必要がある点がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="f214e-219">There are some things you should consider with the *App.config* file.</span></span> <span data-ttu-id="f214e-220">.NET Framework の *App.config* ファイルは、アプリを構成するだけでなく、ログ記録などのランタイム設定と動作を構成するためにも使用されていました。</span><span class="sxs-lookup"><span data-stu-id="f214e-220">The *App.config* file in .NET Framework was used not only to configure the app, but to configure runtime settings and behavior, such as logging.</span></span> <span data-ttu-id="f214e-221">.NET 5 以降 (および .NET Core) の *App.config* ファイルは、ランタイム構成に使用されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="f214e-221">The *App.config* file in .NET 5+ (and .NET Core) is no longer used for runtime configuration.</span></span> <span data-ttu-id="f214e-222">*App.config* ファイルにこれらのセクションが含まれている場合、それらは考慮されません。</span><span class="sxs-lookup"><span data-stu-id="f214e-222">If your *App.config* file has these sections, they won't be respected.</span></span>

## <a name="add-the-compatibility-package"></a><span data-ttu-id="f214e-223">互換性パッケージを追加する</span><span class="sxs-lookup"><span data-stu-id="f214e-223">Add the compatibility package</span></span>

<span data-ttu-id="f214e-224">プロジェクト ファイルが正しく読み込まれていても、プロジェクトのコンパイルに失敗すると、次のようなエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f214e-224">If your project file is loading correctly, but compilation fails for your project and you receive errors similar to the following:</span></span>

- <span data-ttu-id="f214e-225">**型または名前空間 \<some name> が見つかりませんでした**</span><span class="sxs-lookup"><span data-stu-id="f214e-225">**The type or namespace \<some name> could not be found**</span></span>
- <span data-ttu-id="f214e-226">**名前 \<some name> は現在のコンテキスト内に存在しません**</span><span class="sxs-lookup"><span data-stu-id="f214e-226">**The name \<some name> does not exist in the current context**</span></span>

<span data-ttu-id="f214e-227">[`Microsoft.Windows.Compatibility`](https://www.nuget.org/packages/Microsoft.Windows.Compatibility/) パッケージをアプリに追加することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f214e-227">You may need to add the [`Microsoft.Windows.Compatibility`](https://www.nuget.org/packages/Microsoft.Windows.Compatibility/) package to your app.</span></span> <span data-ttu-id="f214e-228">このパッケージでは、Windows レジストリとやり取りするための `System.Configuration.ConfigurationManager` クラスや API など、.NET Framework から 21,000 個までの .NET API を追加します。</span><span class="sxs-lookup"><span data-stu-id="f214e-228">This package adds ~21,000 .NET APIs from .NET Framework, such as the `System.Configuration.ConfigurationManager` class and APIs for interacting with the Windows Registry.</span></span> <span data-ttu-id="f214e-229">`Microsoft.Windows.Compatibility` パッケージを追加します。</span><span class="sxs-lookup"><span data-stu-id="f214e-229">Add the `Microsoft.Windows.Compatibility` package.</span></span>

<span data-ttu-id="f214e-230">プロジェクト ファイルを編集し、次の `<ItemGroup>` 要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="f214e-230">Edit your project file and add the following `<ItemGroup>` element:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.Windows.Compatibility" Version="5.0.0" />
</ItemGroup>
```

## <a name="test-your-app"></a><span data-ttu-id="f214e-231">アプリをテストする</span><span class="sxs-lookup"><span data-stu-id="f214e-231">Test your app</span></span>

<span data-ttu-id="f214e-232">アプリの移行が完了した後、それをテストします。</span><span class="sxs-lookup"><span data-stu-id="f214e-232">After you've finished migrating your app, test it!</span></span>

## <a name="next-steps"></a><span data-ttu-id="f214e-233">次のステップ</span><span class="sxs-lookup"><span data-stu-id="f214e-233">Next steps</span></span>

- <span data-ttu-id="f214e-234">[Windows フォームでの破壊的変更](/dotnet/core/compatibility/winforms)について学習する。</span><span class="sxs-lookup"><span data-stu-id="f214e-234">Learn about [breaking changes in Windows Forms](/dotnet/core/compatibility/winforms).</span></span>
- <span data-ttu-id="f214e-235">[Windows 互換機能パック][compat-pack]の詳細を確認する。</span><span class="sxs-lookup"><span data-stu-id="f214e-235">Read more about the [Windows Compatibility Pack][compat-pack].</span></span>

[compat-pack]: /dotnet/core/porting/windows-compat-pack
