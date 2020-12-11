---
title: アプリをローカライズする
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- localization [WPF], applications
- LocBaml tool [WPF]
- applications [WPF], localizing
ms.assetid: 5001227e-9326-48a4-9dcd-ba1b89ee6653
ms.openlocfilehash: dc7d8f4f56b26fffbd883e1e1d6e420026e1f94f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983280"
---
# <a name="how-to-localize-an-application"></a><span data-ttu-id="a6cea-102">方法: アプリケーションをローカライズする</span><span class="sxs-lookup"><span data-stu-id="a6cea-102">How to: Localize an application</span></span>

<span data-ttu-id="a6cea-103">このチュートリアルでは、LocBaml ツールを使用して、ローカライズされたアプリケーションを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a6cea-103">This tutorial explains how to create a localized application by using the LocBaml tool.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a6cea-104">LocBaml ツールは、実稼働可能なアプリケーションではありません。</span><span class="sxs-lookup"><span data-stu-id="a6cea-104">The LocBaml tool is not a production-ready application.</span></span> <span data-ttu-id="a6cea-105">それはローカリゼーション API の一部を使用するサンプルとして提供されており、ローカリゼーション ツールを記述する方法を例示します。</span><span class="sxs-lookup"><span data-stu-id="a6cea-105">It is presented as a sample that uses some of the localization APIs and illustrates how you might write a localization tool.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="a6cea-106">概要</span><span class="sxs-lookup"><span data-stu-id="a6cea-106">Overview</span></span>

<span data-ttu-id="a6cea-107">この記事では、アプリケーションのローカリゼーションの手順を段階を追って示します。</span><span class="sxs-lookup"><span data-stu-id="a6cea-107">This article gives you a step-by-step approach to localizing an application.</span></span> <span data-ttu-id="a6cea-108">最初に、翻訳されるテキストを抽出できるようにアプリケーションを準備します。</span><span class="sxs-lookup"><span data-stu-id="a6cea-108">First, you prepare your application so that the text that will be translated can be extracted.</span></span> <span data-ttu-id="a6cea-109">テキストの翻訳後、翻訳されたテキストを元のアプリケーションの新しいコピーにマージします。</span><span class="sxs-lookup"><span data-stu-id="a6cea-109">After the text is translated, you merge the translated text into a new copy of the original application.</span></span>
  
## <a name="create-a-sample-application"></a><span data-ttu-id="a6cea-110">サンプル アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="a6cea-110">Create a sample application</span></span>

<span data-ttu-id="a6cea-111">このステップでは、ローカリゼーション用のアプリを準備します。</span><span class="sxs-lookup"><span data-stu-id="a6cea-111">In this step, you prepare your app for localization.</span></span> <span data-ttu-id="a6cea-112">Windows Presentation Foundation (WPF) のサンプルでは、この説明のコード サンプルで使用される HelloApp のサンプルが提供されています。</span><span class="sxs-lookup"><span data-stu-id="a6cea-112">In the Windows Presentation Foundation (WPF) samples, a HelloApp sample is supplied that will be used for the code examples in this discussion.</span></span> <span data-ttu-id="a6cea-113">このサンプルを使用する場合は、Extensible Application Markup Language (XAML) のファイルを [LocBaml ツール サンプル](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml)のページからダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="a6cea-113">If you would like to use this sample, download the Extensible Application Markup Language (XAML) files from the [LocBaml Tool Sample](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml).</span></span>  
  
1. <span data-ttu-id="a6cea-114">ローカリゼーションを開始するポイントまで、アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="a6cea-114">Develop your application to the point where you want to start localization.</span></span>  
  
2. <span data-ttu-id="a6cea-115">MSBuild でメイン アセンブリとサテライト アセンブリ (.resources.dll の拡張子が付いたファイル) が生成され、ニュートラルな言語リソースを含めるように、プロジェクト ファイルの開発言語を指定します。</span><span class="sxs-lookup"><span data-stu-id="a6cea-115">Specify the development language in the project file so that MSBuild generates a main assembly and a satellite assembly (a file with the .resources.dll extension) to contain the neutral language resources.</span></span> <span data-ttu-id="a6cea-116">HelloApp サンプルのプロジェクト ファイルは HelloApp.csproj です。</span><span class="sxs-lookup"><span data-stu-id="a6cea-116">The project file in the HelloApp sample is HelloApp.csproj.</span></span> <span data-ttu-id="a6cea-117">このファイルに、以下のように特定される開発言語があります。</span><span class="sxs-lookup"><span data-stu-id="a6cea-117">In that file, you will find the development language identified as follows:</span></span>  
  
   `<UICulture>en-US</UICulture>`  
  
3. <span data-ttu-id="a6cea-118">XAML のファイルに UID を追加します。</span><span class="sxs-lookup"><span data-stu-id="a6cea-118">Add Uids to your XAML files.</span></span> <span data-ttu-id="a6cea-119">UID は、ファイルへの変更を追跡して、翻訳する必要がある項目を識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="a6cea-119">Uids are used to keep track of changes to files and to identify items that must be translated.</span></span> <span data-ttu-id="a6cea-120">UID をファイルに追加するには、プロジェクト ファイルで `updateuid` を実行します。</span><span class="sxs-lookup"><span data-stu-id="a6cea-120">To add Uids to your files, run `updateuid` on your project file:</span></span>  

   `msbuild -t:updateuid helloapp.csproj`

   <span data-ttu-id="a6cea-121">不足している UID または重複する UID がないことを確認するには、次のように `checkuid` を実行します。</span><span class="sxs-lookup"><span data-stu-id="a6cea-121">To verify that you have no missing or duplicate Uids, run `checkuid`:</span></span>  

   `msbuild -t:checkuid helloapp.csproj`

   <span data-ttu-id="a6cea-122">`updateuid` を実行すると、ファイルに UID が含まれているはずです。</span><span class="sxs-lookup"><span data-stu-id="a6cea-122">After running `updateuid`, your files should contain Uids.</span></span> <span data-ttu-id="a6cea-123">たとえば、HelloApp の *Pane1.xaml* ファイルに、次のブロックがあるはずです。</span><span class="sxs-lookup"><span data-stu-id="a6cea-123">For example, in the *Pane1.xaml* file of HelloApp, you should find the following:</span></span>  

   ```xaml
   <StackPanel x:Uid="StackPanel_1">
     <TextBlock x:Uid="TextBlock_1">Hello World</TextBlock>
     <TextBlock x:Uid="TextBlock_2">Goodbye World</TextBlock>
   </StackPanel>
   ```

## <a name="create-the-neutral-language-resources-satellite-assembly"></a><span data-ttu-id="a6cea-124">ニュートラル言語リソースのサテライト アセンブリを作成する</span><span class="sxs-lookup"><span data-stu-id="a6cea-124">Create the neutral-language resources satellite assembly</span></span>

<span data-ttu-id="a6cea-125">ニュートラル言語リソースのサテライト アセンブリを生成するようにアプリケーションを構成した後、アプリケーションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="a6cea-125">After the application is configured to generate a neutral-language resources satellite assembly, you build the application.</span></span> <span data-ttu-id="a6cea-126">これにより、メイン アプリケーション アセンブリだけでなく、ローカリゼーションで LocBaml が必要とするニュートラル言語リソースのサテライト アセンブリが生成されます。</span><span class="sxs-lookup"><span data-stu-id="a6cea-126">This generates the main application assembly as well as the neutral-language resources satellite assembly that's required by LocBaml for localization.</span></span>

<span data-ttu-id="a6cea-127">アプリケーションをビルドするには</span><span class="sxs-lookup"><span data-stu-id="a6cea-127">To build the application:</span></span>  
  
1. <span data-ttu-id="a6cea-128">次のように HelloApp をコンパイルして、ダイナミックリンク ライブラリ (DLL) を作成します。</span><span class="sxs-lookup"><span data-stu-id="a6cea-128">Compile HelloApp to create a dynamic-link library (DLL):</span></span>  
  
   `msbuild helloapp.csproj`
  
2. <span data-ttu-id="a6cea-129">新規作成されたメインのアプリケーション アセンブリ HelloApp.exe は、次のフォルダーに作成されます。*C:\HelloApp\Bin\Debug*</span><span class="sxs-lookup"><span data-stu-id="a6cea-129">The newly created main application assembly, HelloApp.exe, is created in the following folder: *C:\HelloApp\Bin\Debug*</span></span>
  
3. <span data-ttu-id="a6cea-130">新規作成されたニュートラル言語リソースのサテライト アセンブリ HelloApp.resources.dll は次のフォルダーに作成されます。*C:\HelloApp\Bin\Debug\en-US*</span><span class="sxs-lookup"><span data-stu-id="a6cea-130">The newly created neutral-language resources satellite assembly, HelloApp.resources.dll, is created in the following folder: *C:\HelloApp\Bin\Debug\en-US*</span></span>
  
## <a name="build-the-locbaml-tool"></a><span data-ttu-id="a6cea-131">LocBaml ツールをビルドする</span><span class="sxs-lookup"><span data-stu-id="a6cea-131">Build the LocBaml tool</span></span>  
  
1. <span data-ttu-id="a6cea-132">LocBaml のビルドに必要なすべてのファイルは WPF サンプルに配置されています。</span><span class="sxs-lookup"><span data-stu-id="a6cea-132">All the files necessary to build LocBaml are located in the WPF samples.</span></span> <span data-ttu-id="a6cea-133">C# のファイルを [LocBaml ツール サンプル](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml)のページからダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="a6cea-133">Download the C# files from the [LocBaml Tool Sample](https://github.com/microsoft/WPF-Samples/tree/master/Tools/LocBaml).</span></span>  
  
2. <span data-ttu-id="a6cea-134">ツールをビルドするには、コマンド ラインでプロジェクト ファイル (locbaml.csproj) を実行します。</span><span class="sxs-lookup"><span data-stu-id="a6cea-134">From the command line, run the project file (locbaml.csproj) to build the tool:</span></span>  

   `msbuild locbaml.csproj`
  
3. <span data-ttu-id="a6cea-135">*Bin\Release* ディレクトリに移動して、新しく作成された実行可能ファイル (locbaml.exe) を探します。</span><span class="sxs-lookup"><span data-stu-id="a6cea-135">Go to the *Bin\Release* directory to find the newly created executable file (locbaml.exe).</span></span> <span data-ttu-id="a6cea-136">例:*C:\LocBaml\Bin\Release\locbaml.exe*</span><span class="sxs-lookup"><span data-stu-id="a6cea-136">Example: *C:\LocBaml\Bin\Release\locbaml.exe*</span></span>
  
4. <span data-ttu-id="a6cea-137">LocBaml を実行するときに指定できるオプションは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a6cea-137">The options that you can specify when you run LocBaml are as follows.</span></span>

   | <span data-ttu-id="a6cea-138">オプション</span><span class="sxs-lookup"><span data-stu-id="a6cea-138">Option</span></span> | <span data-ttu-id="a6cea-139">説明</span><span class="sxs-lookup"><span data-stu-id="a6cea-139">Description</span></span>|
   | - | - |
   | <span data-ttu-id="a6cea-140">`parse` または `-p`</span><span class="sxs-lookup"><span data-stu-id="a6cea-140">`parse` or `-p`</span></span> | <span data-ttu-id="a6cea-141">Baml、リソース、または DLL ファイルを解析して、.csv または .txt ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="a6cea-141">Parses Baml, resources, or DLL files to generate a .csv or .txt file.</span></span> |
   | <span data-ttu-id="a6cea-142">`generate` または `-g`</span><span class="sxs-lookup"><span data-stu-id="a6cea-142">`generate` or `-g`</span></span> | <span data-ttu-id="a6cea-143">翻訳されたファイルを使用して、ローカライズされたバイナリ ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="a6cea-143">Generates a localized binary file by using a translated file.</span></span> |
   | <span data-ttu-id="a6cea-144">`out` または `-o` {*filedirectory*]</span><span class="sxs-lookup"><span data-stu-id="a6cea-144">`out` or `-o` {*filedirectory*]</span></span> | <span data-ttu-id="a6cea-145">出力ファイル名。</span><span class="sxs-lookup"><span data-stu-id="a6cea-145">Output file name.</span></span> |
   | <span data-ttu-id="a6cea-146">`culture` または `-cul` {*culture*]</span><span class="sxs-lookup"><span data-stu-id="a6cea-146">`culture` or `-cul` {*culture*]</span></span> | <span data-ttu-id="a6cea-147">出力アセンブリのロケール。</span><span class="sxs-lookup"><span data-stu-id="a6cea-147">Locale of output assemblies.</span></span> |
   | <span data-ttu-id="a6cea-148">`translation` または `-trans` {*translation.csv*]</span><span class="sxs-lookup"><span data-stu-id="a6cea-148">`translation` or `-trans` {*translation.csv*]</span></span> | <span data-ttu-id="a6cea-149">翻訳またはローカライズされたファイル。</span><span class="sxs-lookup"><span data-stu-id="a6cea-149">Translated or localized file.</span></span> |
   | <span data-ttu-id="a6cea-150">`asmpath` または `-asmpath` {*filedirectory*]</span><span class="sxs-lookup"><span data-stu-id="a6cea-150">`asmpath` or `-asmpath` {*filedirectory*]</span></span> | <span data-ttu-id="a6cea-151">XAML コードにカスタム コントロールが含まれている場合、カスタム コントロール アセンブリに `asmpath` を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6cea-151">If your XAML code contains custom controls, you must supply the `asmpath` to the custom control assembly.</span></span> |
   | `nologo` | <span data-ttu-id="a6cea-152">ロゴまたは著作権情報は表示されません。</span><span class="sxs-lookup"><span data-stu-id="a6cea-152">Displays no logo or copyright information.</span></span> |
   | `verbose` | <span data-ttu-id="a6cea-153">詳細モードの情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a6cea-153">Displays verbose mode information.</span></span> |
  
   > [!NOTE]
   > <span data-ttu-id="a6cea-154">このツールを実行しているときにオプションの一覧が必要な場合は、`LocBaml.exe` を入力してから **Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="a6cea-154">If you need a list of the options when you are running the tool, enter `LocBaml.exe` and then press **Enter**.</span></span>
  
## <a name="use-locbaml-to-parse-a-file"></a><span data-ttu-id="a6cea-155">LocBaml を使用してファイルを解析する</span><span class="sxs-lookup"><span data-stu-id="a6cea-155">Use LocBaml to parse a file</span></span>

<span data-ttu-id="a6cea-156">LocBaml ツールが作成されたので、これを使用して HelloApp.resources.dll を解析し、ローカライズするテキスト コンテンツを抽出できる状態になりました。</span><span class="sxs-lookup"><span data-stu-id="a6cea-156">Now that you have created the LocBaml tool, you are ready to use it to parse HelloApp.resources.dll to extract the text content that will be localized.</span></span>  
  
1. <span data-ttu-id="a6cea-157">LocBaml.exe を、メインのアプリケーション アセンブリが作成された、アプリケーションの bin \debug フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="a6cea-157">Copy LocBaml.exe to your application's bin\debug folder, where the main application assembly was created.</span></span>  
  
2. <span data-ttu-id="a6cea-158">サテライト アセンブリ ファイルを解析して、.csv ファイルとして出力を格納するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="a6cea-158">To parse the satellite assembly file and store the output as a .csv file, use the following command:</span></span>  
  
   `LocBaml.exe /parse HelloApp.resources.dll /out:Hello.csv`
  
   > [!NOTE]
   > <span data-ttu-id="a6cea-159">入力ファイル HelloApp.resources.dll が LocBaml.exe と同じディレクトリに存在しない場合は、いずれかのファイルを移動して両方のファイルが同じディレクトリにあるようにします。</span><span class="sxs-lookup"><span data-stu-id="a6cea-159">If the input file, HelloApp.resources.dll, is not in the same directory as LocBaml.exe move one of the files so that both files are in the same directory.</span></span>  
  
3. <span data-ttu-id="a6cea-160">LocBaml を実行してファイルを解析する際、出力はコンマ区切り (.csv ファイル) またはタブ区切り (.txt ファイル) された 7 つのフィールドで構成されます。</span><span class="sxs-lookup"><span data-stu-id="a6cea-160">When you run LocBaml to parse files, the output consists of seven fields delimited by commas (.csv files) or tabs (.txt files).</span></span> <span data-ttu-id="a6cea-161">HelloApp.resources.dll の解析済みの .csv ファイルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="a6cea-161">The following shows the parsed .csv file for the HelloApp.resources.dll:</span></span>

   | |
   |-|
   |<span data-ttu-id="a6cea-162">HelloApp.g.en-US.resources:window1.baml,Stack1:System.Windows.Controls.StackPanel.$Content,Ignore,FALSE, FALSE,,#Text1;#Text2;</span><span class="sxs-lookup"><span data-stu-id="a6cea-162">HelloApp.g.en-US.resources:window1.baml,Stack1:System.Windows.Controls.StackPanel.$Content,Ignore,FALSE, FALSE,,#Text1;#Text2;</span></span>|
   |<span data-ttu-id="a6cea-163">HelloApp.g.en-US.resources:window1.baml,Text1:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Hello World</span><span class="sxs-lookup"><span data-stu-id="a6cea-163">HelloApp.g.en-US.resources:window1.baml,Text1:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Hello World</span></span>|
   |<span data-ttu-id="a6cea-164">HelloApp.g.en-US.resources:window1.baml,Text2:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Goodbye World</span><span class="sxs-lookup"><span data-stu-id="a6cea-164">HelloApp.g.en-US.resources:window1.baml,Text2:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Goodbye World</span></span>|

   <span data-ttu-id="a6cea-165">7 つのフィールドは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a6cea-165">The seven fields are:</span></span>  
  
   - <span data-ttu-id="a6cea-166">**BAML 名**。</span><span class="sxs-lookup"><span data-stu-id="a6cea-166">**BAML Name**.</span></span> <span data-ttu-id="a6cea-167">ソース言語のサテライト アセンブリに関する BAML リソースの名前。</span><span class="sxs-lookup"><span data-stu-id="a6cea-167">The name of the BAML resource with respect to the source language satellite assembly.</span></span>  
  
   - <span data-ttu-id="a6cea-168">**リソース キー**。</span><span class="sxs-lookup"><span data-stu-id="a6cea-168">**Resource Key**.</span></span> <span data-ttu-id="a6cea-169">ローカライズされたリソースの識別子。</span><span class="sxs-lookup"><span data-stu-id="a6cea-169">The localized resource identifier.</span></span>  
  
   - <span data-ttu-id="a6cea-170">**カテゴリ**。</span><span class="sxs-lookup"><span data-stu-id="a6cea-170">**Category**.</span></span> <span data-ttu-id="a6cea-171">値の型です。</span><span class="sxs-lookup"><span data-stu-id="a6cea-171">The value type.</span></span> <span data-ttu-id="a6cea-172">「[ローカリゼーション属性とコメント](localization-attributes-and-comments.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6cea-172">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   - <span data-ttu-id="a6cea-173">**読みやすさ**。</span><span class="sxs-lookup"><span data-stu-id="a6cea-173">**Readability**.</span></span> <span data-ttu-id="a6cea-174">ローカライザーによって値が読み取れるかどうか。</span><span class="sxs-lookup"><span data-stu-id="a6cea-174">Whether the value can be read by a localizer.</span></span> <span data-ttu-id="a6cea-175">「[ローカリゼーション属性とコメント](localization-attributes-and-comments.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6cea-175">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   - <span data-ttu-id="a6cea-176">**変更可能性**。</span><span class="sxs-lookup"><span data-stu-id="a6cea-176">**Modifiability**.</span></span> <span data-ttu-id="a6cea-177">ローカライザーによって値が変更できるかどうか。</span><span class="sxs-lookup"><span data-stu-id="a6cea-177">Whether the value can be modified by a localizer.</span></span> <span data-ttu-id="a6cea-178">「[ローカリゼーション属性とコメント](localization-attributes-and-comments.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6cea-178">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   - <span data-ttu-id="a6cea-179">**コメント**。</span><span class="sxs-lookup"><span data-stu-id="a6cea-179">**Comments**.</span></span> <span data-ttu-id="a6cea-180">値をローカライズする方法を決定するための値の追加の説明。</span><span class="sxs-lookup"><span data-stu-id="a6cea-180">Additional description of the value to help determine how a value is localized.</span></span> <span data-ttu-id="a6cea-181">「[ローカリゼーション属性とコメント](localization-attributes-and-comments.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6cea-181">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   - <span data-ttu-id="a6cea-182">**値**。</span><span class="sxs-lookup"><span data-stu-id="a6cea-182">**Value**.</span></span> <span data-ttu-id="a6cea-183">目的のカルチャに翻訳するテキストの値。</span><span class="sxs-lookup"><span data-stu-id="a6cea-183">The text value to translate to the desired culture.</span></span>  
  
   <span data-ttu-id="a6cea-184">次の表は、.csv ファイルの区切り記号付きの値にこれらのフィールドをマップする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a6cea-184">The following table shows how these fields map to the delimited values of the .csv file:</span></span>  
  
   |<span data-ttu-id="a6cea-185">BAML 名</span><span class="sxs-lookup"><span data-stu-id="a6cea-185">BAML name</span></span>|<span data-ttu-id="a6cea-186">リソース キー</span><span class="sxs-lookup"><span data-stu-id="a6cea-186">Resource key</span></span>|<span data-ttu-id="a6cea-187">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="a6cea-187">Category</span></span>|<span data-ttu-id="a6cea-188">読みやすさ</span><span class="sxs-lookup"><span data-stu-id="a6cea-188">Readability</span></span>|<span data-ttu-id="a6cea-189">変更可能性</span><span class="sxs-lookup"><span data-stu-id="a6cea-189">Modifiability</span></span>|<span data-ttu-id="a6cea-190">コメント</span><span class="sxs-lookup"><span data-stu-id="a6cea-190">Comments</span></span>|<span data-ttu-id="a6cea-191">[値]</span><span class="sxs-lookup"><span data-stu-id="a6cea-191">Value</span></span>|  
   |---------------|------------------|--------------|-----------------|-------------------|--------------|-----------|
   |<span data-ttu-id="a6cea-192">HelloApp.g.en-US.resources:window1.baml</span><span class="sxs-lookup"><span data-stu-id="a6cea-192">HelloApp.g.en-US.resources:window1.baml</span></span>|<span data-ttu-id="a6cea-193">Stack1:System.Windows.Controls.StackPanel.$Content</span><span class="sxs-lookup"><span data-stu-id="a6cea-193">Stack1:System.Windows.Controls.StackPanel.$Content</span></span>|<span data-ttu-id="a6cea-194">Ignore</span><span class="sxs-lookup"><span data-stu-id="a6cea-194">Ignore</span></span>|<span data-ttu-id="a6cea-195">false</span><span class="sxs-lookup"><span data-stu-id="a6cea-195">FALSE</span></span>|<span data-ttu-id="a6cea-196">false</span><span class="sxs-lookup"><span data-stu-id="a6cea-196">FALSE</span></span>||<span data-ttu-id="a6cea-197">#Text1;#Text2</span><span class="sxs-lookup"><span data-stu-id="a6cea-197">#Text1;#Text2</span></span>|
   |<span data-ttu-id="a6cea-198">HelloApp.g.en-US.resources:window1.baml</span><span class="sxs-lookup"><span data-stu-id="a6cea-198">HelloApp.g.en-US.resources:window1.baml</span></span>|<span data-ttu-id="a6cea-199">Stack1:System.Windows.Controls.StackPanel.$Content</span><span class="sxs-lookup"><span data-stu-id="a6cea-199">Text1:System.Windows.Controls.TextBlock.$Content</span></span>|<span data-ttu-id="a6cea-200">None</span><span class="sxs-lookup"><span data-stu-id="a6cea-200">None</span></span>|<span data-ttu-id="a6cea-201">true</span><span class="sxs-lookup"><span data-stu-id="a6cea-201">TRUE</span></span>|<span data-ttu-id="a6cea-202">true</span><span class="sxs-lookup"><span data-stu-id="a6cea-202">TRUE</span></span>||<span data-ttu-id="a6cea-203">Hello World</span><span class="sxs-lookup"><span data-stu-id="a6cea-203">Hello World</span></span>|
   |<span data-ttu-id="a6cea-204">HelloApp.g.en-US.resources:window1.baml</span><span class="sxs-lookup"><span data-stu-id="a6cea-204">HelloApp.g.en-US.resources:window1.baml</span></span>|<span data-ttu-id="a6cea-205">Stack1:System.Windows.Controls.StackPanel.$Content</span><span class="sxs-lookup"><span data-stu-id="a6cea-205">Text2:System.Windows.Controls.TextBlock.$Content</span></span>|<span data-ttu-id="a6cea-206">None</span><span class="sxs-lookup"><span data-stu-id="a6cea-206">None</span></span>|<span data-ttu-id="a6cea-207">true</span><span class="sxs-lookup"><span data-stu-id="a6cea-207">TRUE</span></span>|<span data-ttu-id="a6cea-208">true</span><span class="sxs-lookup"><span data-stu-id="a6cea-208">TRUE</span></span>||<span data-ttu-id="a6cea-209">Goodbye World</span><span class="sxs-lookup"><span data-stu-id="a6cea-209">Goodbye World</span></span>|
  
   <span data-ttu-id="a6cea-210">**[コメント]** フィールドのすべての値に値が含まれていないことに注意してください。フィールドに値がない場合、フィールドは空です。</span><span class="sxs-lookup"><span data-stu-id="a6cea-210">Notice that all the values for the **Comments** field contain no values; if a field doesn't have a value, it is empty.</span></span> <span data-ttu-id="a6cea-211">また、最初の行の項目は、読み取り可能でも変更可能でもありませんが、 **[カテゴリ]** の値として "Ignore" が含まれていることにも注意してください。これらはすべて、値がローカライズ可能ではないことを示します。</span><span class="sxs-lookup"><span data-stu-id="a6cea-211">Also notice that the item in the first row is neither readable nor modifiable, and has "Ignore" as its **Category** value, all of which indicates that the value is not localizable.</span></span>  
  
4. <span data-ttu-id="a6cea-212">解析済みのファイルでローカライズ可能な項目の検出を容易にするためには、項目を **カテゴリ**、**読みやすさ**、および **変更可能性** で並べ替えるかフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="a6cea-212">To facilitate discovery of localizable items in parsed files, particularly in large files, you can sort or filter the items by **Category**, **Readability**, and **Modifiability**.</span></span> <span data-ttu-id="a6cea-213">たとえば、読み取りも変更もできない値をフィルター処理することができます。</span><span class="sxs-lookup"><span data-stu-id="a6cea-213">For example, you can filter out unreadable and unmodifiable values.</span></span>  
  
## <a name="translate-the-localizable-content"></a><span data-ttu-id="a6cea-214">ローカライズ可能なコンテンツを翻訳する</span><span class="sxs-lookup"><span data-stu-id="a6cea-214">Translate the localizable content</span></span>

<span data-ttu-id="a6cea-215">抽出されたコンテンツを翻訳するために使用可能な任意のツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="a6cea-215">Use any tool that you have available to translate the extracted content.</span></span> <span data-ttu-id="a6cea-216">これを行う良い方法は、リソースを .csv ファイルに記述し、それらを Microsoft Excel に表示して、翻訳の変更内容を最後の列 (値) にすることです。</span><span class="sxs-lookup"><span data-stu-id="a6cea-216">A good way to do this is to write the resources to a .csv file and view them in Microsoft Excel, making translation changes to the last column (value).</span></span>  
  
## <a name="use-locbaml-to-generate-a-new-resourcesdll-file"></a><span data-ttu-id="a6cea-217">LocBaml を使用して新しい .resources.dll ファイルを生成する</span><span class="sxs-lookup"><span data-stu-id="a6cea-217">Use LocBaml to generate a new .resources.dll file</span></span>

<span data-ttu-id="a6cea-218">LocBaml で HelloApp.resources.dll を解析して識別されたコンテンツは翻訳済みであり、元のアプリケーションにマージする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6cea-218">The content that was identified by parsing HelloApp.resources.dll with LocBaml has been translated and must be merged back into the original application.</span></span> <span data-ttu-id="a6cea-219">新しい .resources.dll ファイルを生成するには、`generate` または `-g` オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="a6cea-219">Use the `generate` or `-g` option to generate a new .resources.dll file.</span></span>  
  
1. <span data-ttu-id="a6cea-220">新しい HelloApp.resources.dll ファイルを生成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="a6cea-220">Use the following syntax to generate a new HelloApp.resources.dll file.</span></span> <span data-ttu-id="a6cea-221">カルチャを en-US (/cul:en-US) としてマークします。</span><span class="sxs-lookup"><span data-stu-id="a6cea-221">Mark the culture as en-US (/cul:en-US).</span></span>  
  
   `LocBaml.exe /generate HelloApp.resources.dll /trans:Hello.csv /out:c:\ /cul:en-US`  

   > [!NOTE]
   > <span data-ttu-id="a6cea-222">入力ファイル Hello.csv が実行可能ファイル LocBaml.exe と同じディレクトリに存在しない場合は、いずれかのファイルを移動して、両方のファイルが同じディレクトリにあるようにします。</span><span class="sxs-lookup"><span data-stu-id="a6cea-222">If the input file, Hello.csv, is not in the same directory as the executable, LocBaml.exe, move one of the files so that both files are in the same directory.</span></span>  
  
2. <span data-ttu-id="a6cea-223">*C:\HelloApp\Bin\Debug\en-US\HelloApp.resources.dll* ディレクトリにある古い *HelloApp.resources.dll* ファイルを新規作成した *HelloApp.resources.dll* ファイルに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="a6cea-223">Replace the old *HelloApp.resources.dll* file in the *C:\HelloApp\Bin\Debug\en-US\HelloApp.resources.dll* directory with your newly created *HelloApp.resources.dll* file.</span></span>  
  
3. <span data-ttu-id="a6cea-224">ここで "Hello World" と "Goodbye World" をアプリケーション内で翻訳する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6cea-224">"Hello World" and "Goodbye World" should now be translated in your application.</span></span>  
  
4. <span data-ttu-id="a6cea-225">別のカルチャに翻訳するには、翻訳先の言語のカルチャを使用します。</span><span class="sxs-lookup"><span data-stu-id="a6cea-225">To translate to a different culture, use the culture of the language that you are translating to.</span></span> <span data-ttu-id="a6cea-226">フランス語 (カナダ) に翻訳する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a6cea-226">The following example shows how to translate to French-Canadian:</span></span>  
  
   `LocBaml.exe /generate HelloApp.resources.dll /trans:Hellofr-CA.csv /out:c:\ /cul:fr-CA`  
  
5. <span data-ttu-id="a6cea-227">メイン アプリケーション アセンブリと同じアセンブリで、新しいサテライト アセンブリを格納するために、新しいカルチャ固有のフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="a6cea-227">In the same assembly as the main application assembly, create a new culture-specific folder to house the new satellite assembly.</span></span> <span data-ttu-id="a6cea-228">フランス語 (カナダ) のフォルダーは "fr-CA" となります。</span><span class="sxs-lookup"><span data-stu-id="a6cea-228">For French-Canadian, the folder would be fr-CA.</span></span>  
  
6. <span data-ttu-id="a6cea-229">新しいフォルダーに生成されたサテライト アセンブリをコピーします。</span><span class="sxs-lookup"><span data-stu-id="a6cea-229">Copy the generated satellite assembly to the new folder.</span></span>  
  
7. <span data-ttu-id="a6cea-230">新しいサテライト アセンブリをテストするには、アプリケーションが実行するカルチャを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6cea-230">To test the new satellite assembly, you need to change the culture under which your application will run.</span></span> <span data-ttu-id="a6cea-231">2 つの方法のいずれかでこれを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a6cea-231">You can do this in one of two ways:</span></span>  
  
   - <span data-ttu-id="a6cea-232">オペレーティング システムの地域設定を変更する。</span><span class="sxs-lookup"><span data-stu-id="a6cea-232">Change your operating system's regional settings.</span></span>
  
   - <span data-ttu-id="a6cea-233">アプリケーションで、次のコードを App.xaml.cs に追加します。</span><span class="sxs-lookup"><span data-stu-id="a6cea-233">In your application, add the following code to App.xaml.cs:</span></span>  
  
     [!code-xaml[LocBamlChangeCultureSnippets#LocBamlChangeCultureMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/CSharp/App.xaml#locbamlchangeculturemarkup)]
     [!code-csharp[LocBamlChangeCultureSnippets#LocBamlChangeCultureCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/CSharp/App.xaml.cs#locbamlchangeculturecodebehind)]
     [!code-vb[LocBamlChangeCultureSnippets#LocBamlChangeCultureCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/VisualBasic/Application.xaml.vb#locbamlchangeculturecodebehind)]  
  
## <a name="tips-for-using-locbaml"></a><span data-ttu-id="a6cea-234">LocBaml を使用するためのヒント</span><span class="sxs-lookup"><span data-stu-id="a6cea-234">Tips for Using LocBaml</span></span>  
  
- <span data-ttu-id="a6cea-235">カスタム コントロールを定義するすべての依存アセンブリを LocBaml のローカル ディレクトリにコピーするか、GAC にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6cea-235">All dependent assemblies that define custom controls must be copied into the local directory of LocBaml or installed into the GAC.</span></span> <span data-ttu-id="a6cea-236">ローカリゼーション API は、バイナリ XAML (BAML) を読み取るときに、依存アセンブリにアクセスできる必要があるため、これが必要になります。</span><span class="sxs-lookup"><span data-stu-id="a6cea-236">This is necessary because the localization API must have access to the dependent assemblies when it reads the binary XAML (BAML).</span></span>  
  
- <span data-ttu-id="a6cea-237">メインのアセンブリが署名済みの場合は、生成されたリソース DLL も読み込むために署名されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6cea-237">If the main assembly is signed, the generated resource DLL must also be signed in order for it to be loaded.</span></span>  
  
- <span data-ttu-id="a6cea-238">ローカライズされたリソースの DLL は、メインのアセンブリと同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6cea-238">The version of the localized resource DLL needs to be synchronized with the main assembly.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a6cea-239">関連項目</span><span class="sxs-lookup"><span data-stu-id="a6cea-239">See also</span></span>

- [<span data-ttu-id="a6cea-240">WPF のグローバリゼーション</span><span class="sxs-lookup"><span data-stu-id="a6cea-240">Globalization for WPF</span></span>](globalization-for-wpf.md)
- [<span data-ttu-id="a6cea-241">自動レイアウトの使用の概要</span><span class="sxs-lookup"><span data-stu-id="a6cea-241">Use Automatic Layout Overview</span></span>](use-automatic-layout-overview.md)
