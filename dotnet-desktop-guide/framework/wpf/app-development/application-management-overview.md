---
title: アプリケーション管理の概要
ms.date: 03/30/2017
ms.topic: overview
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application management [WPF]
ms.assetid: 32b1c054-5aca-423b-b4b5-ed8dc4dc637d
ms.openlocfilehash: a735791b00b1a8eba48f381ccac2a6325058c842
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984980"
---
# <a name="application-management-overview"></a><span data-ttu-id="dc885-102">アプリケーション管理の概要</span><span class="sxs-lookup"><span data-stu-id="dc885-102">Application Management Overview</span></span>

<span data-ttu-id="dc885-103">すべてのアプリケーションは、アプリケーションの実装と管理に適用される機能を共有することがよくあります。</span><span class="sxs-lookup"><span data-stu-id="dc885-103">All applications tend to share a common set of functionality that applies to application implementation and management.</span></span> <span data-ttu-id="dc885-104">このトピックでは、アプリケーションの作成と管理のための <xref:System.Windows.Application> クラスの機能の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="dc885-104">This topic provides an overview of the functionality in the <xref:System.Windows.Application> class for creating and managing applications.</span></span>

## <a name="the-application-class"></a><span data-ttu-id="dc885-105">Application クラス</span><span class="sxs-lookup"><span data-stu-id="dc885-105">The Application Class</span></span>

<span data-ttu-id="dc885-106">WPF では、共通のアプリケーション スコープの機能は、<xref:System.Windows.Application> クラスにカプセル化されます。</span><span class="sxs-lookup"><span data-stu-id="dc885-106">In WPF, common application-scoped functionality is encapsulated in the <xref:System.Windows.Application> class.</span></span> <span data-ttu-id="dc885-107"><xref:System.Windows.Application> クラスには、次の機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="dc885-107">The <xref:System.Windows.Application> class includes the following functionality:</span></span>

- <span data-ttu-id="dc885-108">アプリケーションの有効期間を追跡し、相互作用する。</span><span class="sxs-lookup"><span data-stu-id="dc885-108">Tracking and interacting with application lifetime.</span></span>

- <span data-ttu-id="dc885-109">コマンド ライン パラメーターを取得し、処理する。</span><span class="sxs-lookup"><span data-stu-id="dc885-109">Retrieving and processing command-line parameters.</span></span>

- <span data-ttu-id="dc885-110">未処理の例外を検出し、応答する。</span><span class="sxs-lookup"><span data-stu-id="dc885-110">Detecting and responding to unhandled exceptions.</span></span>

- <span data-ttu-id="dc885-111">アプリケーション スコープのプロパティと リソースを共有する。</span><span class="sxs-lookup"><span data-stu-id="dc885-111">Sharing application-scope properties and resources.</span></span>

- <span data-ttu-id="dc885-112">スタンドアロン アプリケーションのウィンドウを管理する。</span><span class="sxs-lookup"><span data-stu-id="dc885-112">Managing windows in standalone applications.</span></span>

- <span data-ttu-id="dc885-113">ナビゲーションを追跡し、管理する。</span><span class="sxs-lookup"><span data-stu-id="dc885-113">Tracking and managing navigation.</span></span>

<a name="The_Application_Class"></a>

## <a name="how-to-perform-common-tasks-using-the-application-class"></a><span data-ttu-id="dc885-114">アプリケーションのクラスを使用して一般的なタスクを実行する方法</span><span class="sxs-lookup"><span data-stu-id="dc885-114">How to Perform Common Tasks Using the Application Class</span></span>

<span data-ttu-id="dc885-115"><xref:System.Windows.Application> クラスのすべての詳細に興味がない場合は、<xref:System.Windows.Application> の一般的なタスクとそれらを実行する方法を示す次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc885-115">If you are not interested in all of the details of the <xref:System.Windows.Application> class, the following table lists some of the common tasks for <xref:System.Windows.Application> and how to accomplish them.</span></span> <span data-ttu-id="dc885-116">関連する API とトピックを表示することによって、詳細情報とサンプル コードを参照できます。</span><span class="sxs-lookup"><span data-stu-id="dc885-116">By viewing the related API and topics, you can find more information and sample code.</span></span>

|<span data-ttu-id="dc885-117">タスク</span><span class="sxs-lookup"><span data-stu-id="dc885-117">Task</span></span>|<span data-ttu-id="dc885-118">方法</span><span class="sxs-lookup"><span data-stu-id="dc885-118">Approach</span></span>|
|----------|--------------|
|<span data-ttu-id="dc885-119">現在のアプリケーションを表すオブジェクトを取得する</span><span class="sxs-lookup"><span data-stu-id="dc885-119">Get an object that represents the current application</span></span>|<span data-ttu-id="dc885-120"><xref:System.Windows.Application.Current%2A?displayProperty=nameWithType> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="dc885-120">Use the <xref:System.Windows.Application.Current%2A?displayProperty=nameWithType> property.</span></span>|
|<span data-ttu-id="dc885-121">起動画面をアプリケーションに追加する</span><span class="sxs-lookup"><span data-stu-id="dc885-121">Add a startup screen to an application</span></span>|<span data-ttu-id="dc885-122">「[スプラッシュ スクリーンを WPF アプリケーションに追加する](how-to-add-a-splash-screen-to-a-wpf-application.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc885-122">See [Add a Splash Screen to a WPF Application](how-to-add-a-splash-screen-to-a-wpf-application.md).</span></span>|
|<span data-ttu-id="dc885-123">アプリケーションを起動する</span><span class="sxs-lookup"><span data-stu-id="dc885-123">Start an application</span></span>|<span data-ttu-id="dc885-124"><xref:System.Windows.Application.Run%2A?displayProperty=nameWithType> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="dc885-124">Use the <xref:System.Windows.Application.Run%2A?displayProperty=nameWithType> method.</span></span>|
|<span data-ttu-id="dc885-125">アプリケーションを停止する</span><span class="sxs-lookup"><span data-stu-id="dc885-125">Stop an application</span></span>|<span data-ttu-id="dc885-126"><xref:System.Windows.Application.Shutdown%2A> オブジェクトの <xref:System.Windows.Application.Current%2A?displayProperty=nameWithType> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="dc885-126">Use the <xref:System.Windows.Application.Shutdown%2A> method of the <xref:System.Windows.Application.Current%2A?displayProperty=nameWithType> object.</span></span>|
|<span data-ttu-id="dc885-127">コマンド ラインから引数を取得する</span><span class="sxs-lookup"><span data-stu-id="dc885-127">Get arguments from the command line</span></span>|<span data-ttu-id="dc885-128"><xref:System.Windows.Application.Startup?displayProperty=nameWithType> イベントを処理し、<xref:System.Windows.StartupEventArgs.Args%2A?displayProperty=nameWithType> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="dc885-128">Handle the <xref:System.Windows.Application.Startup?displayProperty=nameWithType> event and use the <xref:System.Windows.StartupEventArgs.Args%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="dc885-129">例については、<xref:System.Windows.Application.Startup?displayProperty=nameWithType> を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc885-129">For an example, see the <xref:System.Windows.Application.Startup?displayProperty=nameWithType> event.</span></span>|
|<span data-ttu-id="dc885-130">アプリケーションの終了コードを取得し、設定する</span><span class="sxs-lookup"><span data-stu-id="dc885-130">Get and set the application exit code</span></span>|<span data-ttu-id="dc885-131"><xref:System.Windows.Application.Exit?displayProperty=nameWithType> イベント ハンドラーの <xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A?displayProperty=nameWithType> プロパティを設定するか、<xref:System.Windows.Application.Shutdown%2A> メソッドを呼び出して、整数を渡します。</span><span class="sxs-lookup"><span data-stu-id="dc885-131">Set the <xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A?displayProperty=nameWithType> property in the <xref:System.Windows.Application.Exit?displayProperty=nameWithType> event handler or call the <xref:System.Windows.Application.Shutdown%2A> method and pass in an integer.</span></span>|
|<span data-ttu-id="dc885-132">未処理の例外を検出し、応答する</span><span class="sxs-lookup"><span data-stu-id="dc885-132">Detect and respond to unhandled exceptions</span></span>|<span data-ttu-id="dc885-133"><xref:System.Windows.Application.DispatcherUnhandledException> イベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="dc885-133">Handle the <xref:System.Windows.Application.DispatcherUnhandledException> event.</span></span>|
|<span data-ttu-id="dc885-134">アプリケーション スコープのリソースを取得し、設定する</span><span class="sxs-lookup"><span data-stu-id="dc885-134">Get and set application-scoped resources</span></span>|<span data-ttu-id="dc885-135"><xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="dc885-135">Use the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> property.</span></span>|
|<span data-ttu-id="dc885-136">アプリケーション スコープのリソース ディクショナリを使用する</span><span class="sxs-lookup"><span data-stu-id="dc885-136">Use an application-scope resource dictionary</span></span>|<span data-ttu-id="dc885-137">「[アプリケーション スコープのリソース ディクショナリを使用する](how-to-use-an-application-scope-resource-dictionary.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc885-137">See [Use an Application-Scope Resource Dictionary](how-to-use-an-application-scope-resource-dictionary.md).</span></span>|
|<span data-ttu-id="dc885-138">アプリケーション スコープのプロパティを取得し、設定する</span><span class="sxs-lookup"><span data-stu-id="dc885-138">Get and set application-scoped properties</span></span>|<span data-ttu-id="dc885-139"><xref:System.Windows.Application.Properties%2A?displayProperty=nameWithType> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="dc885-139">Use the <xref:System.Windows.Application.Properties%2A?displayProperty=nameWithType> property.</span></span>|
|<span data-ttu-id="dc885-140">アプリケーションの状態を取得し、保存する</span><span class="sxs-lookup"><span data-stu-id="dc885-140">Get and save an application's state</span></span>|<span data-ttu-id="dc885-141">「[アプリケーション セッション全体でアプリケーション スコープのプロパティを永続化および復元する](persist-and-restore-application-scope-properties.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc885-141">See [Persist and Restore Application-Scope Properties Across Application Sessions](persist-and-restore-application-scope-properties.md).</span></span>|
|<span data-ttu-id="dc885-142">リソース ファイル、コンテンツ ファイル、起点ファイルなど、コード以外のデータ ファイルを管理する。</span><span class="sxs-lookup"><span data-stu-id="dc885-142">Manage non-code data files, including resource files, content files, and site-of-origin files.</span></span>|<span data-ttu-id="dc885-143">「[WPF アプリケーションのリソース、コンテンツ ファイル、およびデータ ファイル](wpf-application-resource-content-and-data-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc885-143">See [WPF Application Resource, Content, and Data Files](wpf-application-resource-content-and-data-files.md).</span></span>|
|<span data-ttu-id="dc885-144">スタンドアロン アプリケーションのウィンドウを管理する</span><span class="sxs-lookup"><span data-stu-id="dc885-144">Manage windows in standalone applications</span></span>|<span data-ttu-id="dc885-145">「[WPF ウィンドウの概要](wpf-windows-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc885-145">See [WPF Windows Overview](wpf-windows-overview.md).</span></span>|
|<span data-ttu-id="dc885-146">ナビゲーションを追跡し、管理する</span><span class="sxs-lookup"><span data-stu-id="dc885-146">Track and manage navigation</span></span>|<span data-ttu-id="dc885-147">「[ナビゲーションの概要](navigation-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc885-147">See [Navigation Overview](navigation-overview.md).</span></span>|

<a name="The_Application_Definition"></a>

## <a name="the-application-definition"></a><span data-ttu-id="dc885-148">アプリケーション定義</span><span class="sxs-lookup"><span data-stu-id="dc885-148">The Application Definition</span></span>

<span data-ttu-id="dc885-149"><xref:System.Windows.Application> クラスの機能を利用するには、アプリケーション定義を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc885-149">To utilize the functionality of the <xref:System.Windows.Application> class, you must implement an application definition.</span></span> <span data-ttu-id="dc885-150">WPF アプリケーションの定義は、<xref:System.Windows.Application> から派生したクラスであり、特別な MSBuild の設定で構成されます。</span><span class="sxs-lookup"><span data-stu-id="dc885-150">A WPF application definition is a class that derives from <xref:System.Windows.Application> and is configured with a special MSBuild setting.</span></span>

### <a name="implementing-an-application-definition"></a><span data-ttu-id="dc885-151">アプリケーション定義の実装</span><span class="sxs-lookup"><span data-stu-id="dc885-151">Implementing an Application Definition</span></span>

<span data-ttu-id="dc885-152">一般的な WPF アプリケーション定義は、マークアップと分離コードの両方を使用して実装されます。</span><span class="sxs-lookup"><span data-stu-id="dc885-152">A typical WPF application definition is implemented using both markup and code-behind.</span></span> <span data-ttu-id="dc885-153">これにより、マークアップを使用して、アプリケーションのプロパティやリソースを宣言によって設定したり、イベントを登録したりでき、分離コードでイベントを処理し、アプリケーション固有の動作を実装することができます。</span><span class="sxs-lookup"><span data-stu-id="dc885-153">This allows you to use markup to declaratively set application properties, resources, and register events, while handling events and implementing application-specific behavior in code-behind.</span></span>

<span data-ttu-id="dc885-154">次の例では、マークアップと分離コードの両方を使用してアプリケーション定義を実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="dc885-154">The following example shows how to implement an application definition using both markup and code-behind:</span></span>

[!code-xaml[ApplicationSnippets#ApplicationXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSnippets/CSharp/App.xaml#applicationxaml)]

[!code-csharp[ApplicationSnippets#ApplicationCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSnippets/CSharp/App.xaml.cs#applicationcodebehind)]
[!code-vb[ApplicationSnippets#ApplicationCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationSnippets/visualbasic/application.xaml.vb#applicationcodebehind)]

<span data-ttu-id="dc885-155">マークアップ ファイルと分離コード ファイルを連携させるには、次のようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc885-155">To allow a markup file and code-behind file to work together, the following needs to happen:</span></span>

- <span data-ttu-id="dc885-156">マークアップでは、`Application` 要素に `x:Class` 属性を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc885-156">In markup, the `Application` element must include the `x:Class` attribute.</span></span> <span data-ttu-id="dc885-157">アプリケーションのビルド時にマークアップ ファイルに `x:Class` が含まれていると、MSBuild により、`x:Class` 属性で指定された名前を持つ、<xref:System.Windows.Application> から派生した `partial` クラスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="dc885-157">When the application is built, the existence of `x:Class` in the markup file causes MSBuild to create a `partial` class that derives from <xref:System.Windows.Application> and has the name that is specified by the `x:Class` attribute.</span></span> <span data-ttu-id="dc885-158">そのためには、XAML スキーマ (`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`) に XML 名前空間宣言を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc885-158">This requires the addition of an XML namespace declaration for the XAML schema (`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`).</span></span>

- <span data-ttu-id="dc885-159">分離コードでは、クラスは、マークアップ内の `x:Class` 属性で指定されている名前を持つ `partial` クラスでなければなりません。また、<xref:System.Windows.Application> から派生する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc885-159">In code-behind, the class must be a `partial` class with the same name that is specified by the `x:Class` attribute in markup and must derive from <xref:System.Windows.Application>.</span></span> <span data-ttu-id="dc885-160">これによって、分離コード ファイルと、アプリケーションのビルド時にマークアップ ファイル用に生成される `partial` クラスとが関連付けられます (「[WPF アプリケーションのビルド](building-a-wpf-application-wpf.md)」を参照)。</span><span class="sxs-lookup"><span data-stu-id="dc885-160">This allows the code-behind file to be associated with the `partial` class that is generated for the markup file when the application is built (see [Building a WPF Application](building-a-wpf-application-wpf.md)).</span></span>

> [!NOTE]
> <span data-ttu-id="dc885-161">Visual Studio を使用して新しい WPF アプリケーション プロジェクトまたは WPF ブラウザー アプリケーション プロジェクトを作成すると、アプリケーション定義が既定で含まれ、マークアップと分離コードの両方を使用して定義されます。</span><span class="sxs-lookup"><span data-stu-id="dc885-161">When you create a new WPF Application project or WPF Browser Application project using Visual Studio, an application definition is included by default and is defined using both markup and code-behind.</span></span>

<span data-ttu-id="dc885-162">このコードは、アプリケーション定義を実装するために最低限必要です。</span><span class="sxs-lookup"><span data-stu-id="dc885-162">This code is the minimum that is required to implement an application definition.</span></span> <span data-ttu-id="dc885-163">ただし、アプリケーションをビルドして実行する前に、アプリケーション定義に対して MSBuild の追加構成を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc885-163">However, an additional MSBuild configuration needs to be made to the application definition before building and running the application.</span></span>

### <a name="configuring-the-application-definition-for-msbuild"></a><span data-ttu-id="dc885-164">MSBuild 用のアプリケーション定義の構成</span><span class="sxs-lookup"><span data-stu-id="dc885-164">Configuring the Application Definition for MSBuild</span></span>

<span data-ttu-id="dc885-165">スタンドアロン アプリケーションや XAML ブラウザー アプリケーション (XBAP) を実行できるようにするには、一定レベルのインフラストラクチャの実装が必要です。</span><span class="sxs-lookup"><span data-stu-id="dc885-165">Standalone applications and XAML browser applications (XBAPs) require the implementation of a certain level of infrastructure before they can run.</span></span> <span data-ttu-id="dc885-166">このインフラストラクチャの最も重要な部分は、エントリ ポイントです。</span><span class="sxs-lookup"><span data-stu-id="dc885-166">The most important part of this infrastructure is the entry point.</span></span> <span data-ttu-id="dc885-167">ユーザーがアプリケーションを起動するとき、オペレーティング システムはエントリ ポイントを呼び出します。これは、アプリケーションを起動するための、よく知られている機能です。</span><span class="sxs-lookup"><span data-stu-id="dc885-167">When an application is launched by a user, the operating system calls the entry point, which is a well-known function for starting applications.</span></span>

<span data-ttu-id="dc885-168">従来、開発者は、テクノロジに応じて、このコードの一部または全部を自分で記述する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="dc885-168">Traditionally, developers have needed to write some or all of this code for themselves, depending on the technology.</span></span> <span data-ttu-id="dc885-169">しかし、WPF では、次の MSBuild プロジェクト ファイルに示されているように、アプリケーション定義のマークアップ ファイルが MSBuild の `ApplicationDefinition` 項目として構成されると、このコードが自動生成されます。</span><span class="sxs-lookup"><span data-stu-id="dc885-169">However, WPF generates this code for you when the markup file of your application definition is configured as an MSBuild `ApplicationDefinition` item, as shown in the following MSBuild project file:</span></span>

```xml
<Project
  DefaultTargets="Build"
                        xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  ...
  <ApplicationDefinition Include="App.xaml" />
  <Compile Include="App.xaml.cs" />
  ...
</Project>
```

<span data-ttu-id="dc885-170">分離コード ファイルはコードを含んでいるため、通常どおり、MSBuild の `Compile` 項目としてマークされます。</span><span class="sxs-lookup"><span data-stu-id="dc885-170">Because the code-behind file contains code, it is marked as an MSBuild `Compile` item, as is normal.</span></span>

<span data-ttu-id="dc885-171">これらの MSBuild 構成をアプリケーション定義のマークアップ ファイルと分離コード ファイルに適用すると、MSBuild によって次のようなコードが生成されます。</span><span class="sxs-lookup"><span data-stu-id="dc885-171">The application of these MSBuild configurations to the markup and code-behind files of an application definition causes MSBuild to generate code like the following:</span></span>

[!code-csharp[auto-generated-code](~/samples/snippets/csharp/VS_Snippets_Wpf/AppDefAugSnippets/CSharp/App.cs)]
[!code-vb[auto-generated-code](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AppDefAugSnippets/VisualBasic/App.vb)]

<span data-ttu-id="dc885-172">生成されるコードにより、アプリケーション定義に追加のインフラストラクチャのコードが追加され、そこに `Main` というエントリ ポイント メソッドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="dc885-172">The resulting code augments your application definition with additional infrastructure code, which includes the entry-point method `Main`.</span></span> <span data-ttu-id="dc885-173"><xref:System.STAThreadAttribute> 属性が `Main` メソッドに適用されて、WPF アプリケーションのメイン UI スレッドが、WPF アプリケーションに必須の STA スレッドであることが示されます。</span><span class="sxs-lookup"><span data-stu-id="dc885-173">The <xref:System.STAThreadAttribute> attribute is applied to the `Main` method to indicate that the main UI thread for the WPF application is an STA thread, which is required for WPF applications.</span></span> <span data-ttu-id="dc885-174">呼び出されると、`Main` では、`App` の新しいインスタンスが作成されてから、`InitializeComponent` メソッドが呼び出されて、イベントが登録され、マークアップで実装されるプロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="dc885-174">When called, `Main` creates a new instance of `App` before calling the `InitializeComponent` method to register the events and set the properties that are implemented in markup.</span></span> <span data-ttu-id="dc885-175">`InitializeComponent` は自動的に生成されるので、<xref:System.Windows.Controls.Page> や <xref:System.Windows.Window> の実装のように、アプリケーション定義から `InitializeComponent` を明示的に呼び出す必要はありません。</span><span class="sxs-lookup"><span data-stu-id="dc885-175">Because `InitializeComponent` is generated for you, you don't need to explicitly call `InitializeComponent` from an application definition like you do for <xref:System.Windows.Controls.Page> and <xref:System.Windows.Window> implementations.</span></span> <span data-ttu-id="dc885-176">最後に、<xref:System.Windows.Application.Run%2A> メソッドが呼び出されて、アプリケーションが起動されます。</span><span class="sxs-lookup"><span data-stu-id="dc885-176">Finally, the <xref:System.Windows.Application.Run%2A> method is called to start the application.</span></span>

<a name="Getting_the_Current_Application"></a>

## <a name="getting-the-current-application"></a><span data-ttu-id="dc885-177">現在のアプリケーションの取得</span><span class="sxs-lookup"><span data-stu-id="dc885-177">Getting the Current Application</span></span>

<span data-ttu-id="dc885-178"><xref:System.Windows.Application> クラスの機能はアプリケーション間で共有されるため、<xref:System.Windows.Application> クラスのインスタンスは、<xref:System.AppDomain> ごとに 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="dc885-178">Because the functionality of the <xref:System.Windows.Application> class are shared across an application, there can be only one instance of the <xref:System.Windows.Application> class per <xref:System.AppDomain>.</span></span> <span data-ttu-id="dc885-179">これを強制するため、<xref:System.Windows.Application> クラスはシングルトン クラスとして実装されます (「[C# でのシングルトンの実装](/previous-versions/msp-n-p/ff650316(v=pandp.10))」を参照)。つまり、インスタンスが 1 つだけ作成され、`static` <xref:System.Windows.Application.Current%2A> プロパティを使用して、インスタンスへの共有アクセスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="dc885-179">To enforce this, the <xref:System.Windows.Application> class is implemented as a singleton class (see [Implementing Singleton in C#](/previous-versions/msp-n-p/ff650316(v=pandp.10))), which creates a single instance of itself and provides shared access to it with the `static`<xref:System.Windows.Application.Current%2A> property.</span></span>

<span data-ttu-id="dc885-180">次のコードでは、現在の <xref:System.AppDomain> の <xref:System.Windows.Application> オブジェクトへの参照を取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="dc885-180">The following code shows how to acquire a reference to the <xref:System.Windows.Application> object for the current <xref:System.AppDomain>.</span></span>

[!code-csharp[ApplicationManagementOverviewSnippets#GetCurrentAppCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/MainWindow.xaml.cs#getcurrentappcode)]
[!code-vb[ApplicationManagementOverviewSnippets#GetCurrentAppCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/VisualBasic/MainWindow.xaml.vb#getcurrentappcode)]

<span data-ttu-id="dc885-181"><xref:System.Windows.Application.Current%2A> では、<xref:System.Windows.Application> クラスのインスタンスへの参照が返されます。</span><span class="sxs-lookup"><span data-stu-id="dc885-181"><xref:System.Windows.Application.Current%2A> returns a reference to an instance of the <xref:System.Windows.Application> class.</span></span> <span data-ttu-id="dc885-182"><xref:System.Windows.Application> 派生クラスへの参照が必要な場合は、次の例で示すように、<xref:System.Windows.Application.Current%2A> プロパティの値をキャストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc885-182">If you want a reference to your <xref:System.Windows.Application> derived class you must cast the value of the <xref:System.Windows.Application.Current%2A> property, as shown in the following example.</span></span>

[!code-csharp[ApplicationManagementOverviewSnippets#GetSTCurrentAppCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/MainWindow.xaml.cs#getstcurrentappcode)]
[!code-vb[ApplicationManagementOverviewSnippets#GetSTCurrentAppCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/VisualBasic/MainWindow.xaml.vb#getstcurrentappcode)]

<span data-ttu-id="dc885-183"><xref:System.Windows.Application.Current%2A> の値は、<xref:System.Windows.Application> オブジェクトの有効期間中はいつでも調べることができます。</span><span class="sxs-lookup"><span data-stu-id="dc885-183">You can inspect the value of <xref:System.Windows.Application.Current%2A> at any point in the lifetime of an <xref:System.Windows.Application> object.</span></span> <span data-ttu-id="dc885-184">ただし、注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="dc885-184">However, you should be careful.</span></span> <span data-ttu-id="dc885-185"><xref:System.Windows.Application> クラスがインスタンス化された後、<xref:System.Windows.Application> オブジェクトの状態の一貫性が失われる期間があります。</span><span class="sxs-lookup"><span data-stu-id="dc885-185">After the <xref:System.Windows.Application> class is instantiated, there is a period during which the state of the <xref:System.Windows.Application> object is inconsistent.</span></span> <span data-ttu-id="dc885-186">この期間中、<xref:System.Windows.Application> では、アプリケーション インフラストラクチャの確立、プロパティの設定、イベントの登録など、コードの実行に必要なさまざまな初期化タスクが実行されます。</span><span class="sxs-lookup"><span data-stu-id="dc885-186">During this period, <xref:System.Windows.Application> is performing the various initialization tasks that are required by your code to run, including establishing application infrastructure, setting properties, and registering events.</span></span> <span data-ttu-id="dc885-187">この期間中に <xref:System.Windows.Application> オブジェクトを使用しようとすると、コードが予期しない結果になることがあります (特に設定中のさまざまな <xref:System.Windows.Application> プロパティに依存している場合)。</span><span class="sxs-lookup"><span data-stu-id="dc885-187">If you try to use the <xref:System.Windows.Application> object during this period, your code may have unexpected results, particularly if it depends on the various <xref:System.Windows.Application> properties being set.</span></span>

<span data-ttu-id="dc885-188"><xref:System.Windows.Application> での初期化作業を完了すると、実質的な有効期間が始まります。</span><span class="sxs-lookup"><span data-stu-id="dc885-188">When <xref:System.Windows.Application> completes its initialization work, its lifetime truly begins.</span></span>

<a name="Application_Lifetime"></a>

## <a name="application-lifetime"></a><span data-ttu-id="dc885-189">アプリケーションの有効期間</span><span class="sxs-lookup"><span data-stu-id="dc885-189">Application Lifetime</span></span>

<span data-ttu-id="dc885-190">WPF アプリケーションの有効期間は、アプリケーションが起動されたこと、アクティブになったこと、非アクティブになったこと、シャットダウンされたことなどを通知するために、<xref:System.Windows.Application> によって発生させられるいくつかのイベントによってマークされます。</span><span class="sxs-lookup"><span data-stu-id="dc885-190">The lifetime of a WPF application is marked by several events that are raised by <xref:System.Windows.Application> to let you know when your application has started, has been activated and deactivated, and has been shut down.</span></span>

<a name="Splash_Screen"></a>

### <a name="splash-screen"></a><span data-ttu-id="dc885-191">スプラッシュ スクリーン</span><span class="sxs-lookup"><span data-stu-id="dc885-191">Splash Screen</span></span>

<span data-ttu-id="dc885-192">.NET Framework 3.5 SP1 以降では、スタートアップ ウィンドウ ("*スプラッシュ スクリーン*") で使用する画像を指定できます。</span><span class="sxs-lookup"><span data-stu-id="dc885-192">Starting in the .NET Framework 3.5 SP1, you can specify an image to be used in a startup window, or *splash screen*.</span></span> <span data-ttu-id="dc885-193"><xref:System.Windows.SplashScreen> クラスを使用すると、アプリケーションを読み込んでいるときに、スタートアップ ウィンドウを簡単に表示できます。</span><span class="sxs-lookup"><span data-stu-id="dc885-193">The <xref:System.Windows.SplashScreen> class makes it easy to display a startup window while your application is loading.</span></span> <span data-ttu-id="dc885-194"><xref:System.Windows.SplashScreen> ウィンドウは、<xref:System.Windows.Application.Run%2A> が呼び出される前に作成されて表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc885-194">The <xref:System.Windows.SplashScreen> window is created and shown before <xref:System.Windows.Application.Run%2A> is called.</span></span> <span data-ttu-id="dc885-195">詳細については、「[アプリケーションの起動時間](../advanced/application-startup-time.md)」および「[スプラッシュ スクリーンを WPF アプリケーションに追加する](how-to-add-a-splash-screen-to-a-wpf-application.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc885-195">For more information, see [Application Startup Time](../advanced/application-startup-time.md) and [Add a Splash Screen to a WPF Application](how-to-add-a-splash-screen-to-a-wpf-application.md).</span></span>

<a name="Starting_an_Application"></a>

### <a name="starting-an-application"></a><span data-ttu-id="dc885-196">アプリケーションの起動</span><span class="sxs-lookup"><span data-stu-id="dc885-196">Starting an Application</span></span>

<span data-ttu-id="dc885-197"><xref:System.Windows.Application.Run%2A> が呼び出され、アプリケーションが初期化されると、アプリケーションの実行準備が整います。</span><span class="sxs-lookup"><span data-stu-id="dc885-197">After <xref:System.Windows.Application.Run%2A> is called and the application is initialized, the application is ready to run.</span></span> <span data-ttu-id="dc885-198">このタイミングは、<xref:System.Windows.Application.Startup> イベントが発生したときに通知されます。</span><span class="sxs-lookup"><span data-stu-id="dc885-198">This moment is signified when the <xref:System.Windows.Application.Startup> event is raised:</span></span>

[!code-csharp[Startup-event](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs?range=3-11,31-33)]
[!code-vb[Startup-event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb?range=5-11,30-32)]

<span data-ttu-id="dc885-199">アプリケーションの有効期間中のこの時点で最も一般的に行われるのは、UI の表示です。</span><span class="sxs-lookup"><span data-stu-id="dc885-199">At this point in an application's lifetime, the most common thing to do is to show a UI.</span></span>

<a name="Showing_a_User_Interface"></a>

### <a name="showing-a-user-interface"></a><span data-ttu-id="dc885-200">ユーザー インターフェイスの表示</span><span class="sxs-lookup"><span data-stu-id="dc885-200">Showing a User Interface</span></span>

<span data-ttu-id="dc885-201">ほとんどのスタンドアロン Windows アプリケーションでは、実行を開始するとき、<xref:System.Windows.Window> が開かれます。</span><span class="sxs-lookup"><span data-stu-id="dc885-201">Most standalone Windows applications open a <xref:System.Windows.Window> when they begin running.</span></span> <span data-ttu-id="dc885-202">次のコードに示されているように、<xref:System.Windows.Application.Startup> イベント ハンドラーは、これを行うことができる場所の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="dc885-202">The <xref:System.Windows.Application.Startup> event handler is one location from which you can do this, as demonstrated by the following code.</span></span>

[!code-xaml[AppShowWindowHardSnippets#StartupEventMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/AppShowWindowHardSnippets/CSharp/App.xaml#startupeventmarkup)]

[!code-csharp[AppShowWindowHardSnippets#StartupEventCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/AppShowWindowHardSnippets/CSharp/App.xaml.cs#startupeventcodebehind)]
[!code-vb[AppShowWindowHardSnippets#StartupEventCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AppShowWindowHardSnippets/VisualBasic/Application.xaml.vb#startupeventcodebehind)]

> [!NOTE]
> <span data-ttu-id="dc885-203">スタンドアロン アプリケーションではインスタンス化された最初の <xref:System.Windows.Window> が、既定でメイン アプリケーション ウィンドウになります。</span><span class="sxs-lookup"><span data-stu-id="dc885-203">The first <xref:System.Windows.Window> to be instantiated in a standalone application becomes the main application window by default.</span></span> <span data-ttu-id="dc885-204">この <xref:System.Windows.Window> オブジェクトは、<xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType> プロパティによって参照されます。</span><span class="sxs-lookup"><span data-stu-id="dc885-204">This <xref:System.Windows.Window> object is referenced by the <xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="dc885-205">最初にインスタンス化された <xref:System.Windows.Window> 以外のウィンドウをメイン ウィンドウにする必要がある場合は、<xref:System.Windows.Application.MainWindow%2A> プロパティの値をプログラムで変更できます。</span><span class="sxs-lookup"><span data-stu-id="dc885-205">The value of the <xref:System.Windows.Application.MainWindow%2A> property can be changed programmatically if a different window than the first instantiated <xref:System.Windows.Window> should be the main window.</span></span>

<span data-ttu-id="dc885-206">通常、XBAP は起動すると最初に、<xref:System.Windows.Controls.Page> にナビゲートします。</span><span class="sxs-lookup"><span data-stu-id="dc885-206">When an XBAP first starts, it will most likely navigate to a <xref:System.Windows.Controls.Page>.</span></span> <span data-ttu-id="dc885-207">これを次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="dc885-207">This is shown in the following code.</span></span>

[!code-xaml[XBAPAppStartupSnippets#StartupXBAPMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppStartupSnippets/CSharp/App.xaml#startupxbapmarkup)]

[!code-csharp[XBAPAppStartupSnippets#StartupXBAPCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppStartupSnippets/CSharp/App.xaml.cs#startupxbapcodebehind)]
[!code-vb[XBAPAppStartupSnippets#StartupXBAPCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppStartupSnippets/VisualBasic/Application.xaml.vb#startupxbapcodebehind)]

<span data-ttu-id="dc885-208"><xref:System.Windows.Application.Startup> の処理目的が <xref:System.Windows.Window> を開くことか、<xref:System.Windows.Controls.Page> にナビゲートすることのみの場合は、代わりに、マークアップで `StartupUri` 属性を設定できます。</span><span class="sxs-lookup"><span data-stu-id="dc885-208">If you handle <xref:System.Windows.Application.Startup> to only open a <xref:System.Windows.Window> or navigate to a <xref:System.Windows.Controls.Page>, you can set the `StartupUri` attribute in markup instead.</span></span>

<span data-ttu-id="dc885-209">次の例では、スタンドアロン アプリケーションから <xref:System.Windows.Application.StartupUri%2A> を使用して <xref:System.Windows.Window> を開く方法を示します。</span><span class="sxs-lookup"><span data-stu-id="dc885-209">The following example shows how to use the <xref:System.Windows.Application.StartupUri%2A> from a standalone application to open a <xref:System.Windows.Window>.</span></span>

[!code-xaml[ApplicationManagementOverviewSnippets#OverviewStartupUriMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/App.xaml#overviewstartupurimarkup)]

<span data-ttu-id="dc885-210">次の例では、XBAP から <xref:System.Windows.Application.StartupUri%2A> を使用して <xref:System.Windows.Controls.Page> にナビゲートする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="dc885-210">The following example shows how to use <xref:System.Windows.Application.StartupUri%2A> from an XBAP to navigate to a <xref:System.Windows.Controls.Page>.</span></span>

[!code-xaml[PageSnippets#XBAPStartupUriMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/PageSnippets/CSharp/App.xaml#xbapstartupurimarkup)]

<span data-ttu-id="dc885-211">このマークアップは、ウィンドウを開くことについて、前のコードと同じ効果があります。</span><span class="sxs-lookup"><span data-stu-id="dc885-211">This markup has the same effect as the previous code for opening a window.</span></span>

> [!NOTE]
> <span data-ttu-id="dc885-212">ナビゲーションの詳細については、「[ナビゲーションの概要](navigation-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc885-212">For more information on navigation, see [Navigation Overview](navigation-overview.md).</span></span>

<span data-ttu-id="dc885-213">パラメーターなしではないコンストラクターを使用してウィンドウをインスタンス化する必要がある場合、またはウィンドウを表示する前にウィンドウのプロパティを設定するか、イベントをサブスクライブする必要がある場合、またはアプリケーションの起動時に指定されたコマンド ライン引数を処理する必要がある場合、<xref:System.Windows.Window> を開くには、<xref:System.Windows.Application.Startup> イベントを処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc885-213">You need to handle the <xref:System.Windows.Application.Startup> event to open a <xref:System.Windows.Window> if you need to instantiate it using a non-parameterless constructor, or you need to set its properties or subscribe to its events before showing it, or you need to process any command-line arguments that were supplied when the application was launched.</span></span>

<a name="Processing_Command_Line_Arguments"></a>

### <a name="processing-command-line-arguments"></a><span data-ttu-id="dc885-214">コマンド ライン引数の処理</span><span class="sxs-lookup"><span data-stu-id="dc885-214">Processing Command-Line Arguments</span></span>

<span data-ttu-id="dc885-215">Windows では、スタンドアロン アプリケーションは、コマンド プロンプトまたはデスクトップから起動できます。</span><span class="sxs-lookup"><span data-stu-id="dc885-215">In Windows, standalone applications can be launched from either a command prompt or the desktop.</span></span> <span data-ttu-id="dc885-216">どちらの場合も、コマンド ライン引数をアプリケーションに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="dc885-216">In both cases, command-line arguments can be passed to the application.</span></span> <span data-ttu-id="dc885-217">次の例は、1 つのコマンド ライン引数 "/StartMinimized" を指定して起動されるアプリケーションを示しています。</span><span class="sxs-lookup"><span data-stu-id="dc885-217">The following example shows an application that is launched with a single command-line argument, "/StartMinimized":</span></span>

`wpfapplication.exe /StartMinimized`

<span data-ttu-id="dc885-218">アプリケーションの初期化中に、WPF によってオペレーティング システムからコマンド ライン引数が取得され、<xref:System.Windows.StartupEventArgs> パラメーターの <xref:System.Windows.StartupEventArgs.Args%2A> プロパティを介して <xref:System.Windows.Application.Startup> イベント ハンドラーに渡されます。</span><span class="sxs-lookup"><span data-stu-id="dc885-218">During application initialization, WPF retrieves the command-line arguments from the operating system and passes them to the <xref:System.Windows.Application.Startup> event handler via the <xref:System.Windows.StartupEventArgs.Args%2A> property of the <xref:System.Windows.StartupEventArgs> parameter.</span></span> <span data-ttu-id="dc885-219">次のようなコードを使用して、コマンド ライン引数を取得し、格納することができます。</span><span class="sxs-lookup"><span data-stu-id="dc885-219">You can retrieve and store the command-line arguments using code like the following.</span></span>

[!code-xaml[ApplicationStartupSnippets#HandleStartupXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml#handlestartupxaml)]

[!code-csharp[ApplicationStartupSnippets#HandleStartupCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs#handlestartupcodebehind)]
[!code-vb[ApplicationStartupSnippets#HandleStartupCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb#handlestartupcodebehind)]

<span data-ttu-id="dc885-220">このコードでは、<xref:System.Windows.Application.Startup> が処理されて、 **/StartMinimized** コマンド ライン引数が指定されたかどうかが確認されます。指定されている場合は、<xref:System.Windows.WindowState> を <xref:System.Windows.WindowState.Minimized> にしてメイン ウィンドウが開かれます。</span><span class="sxs-lookup"><span data-stu-id="dc885-220">The code handles <xref:System.Windows.Application.Startup> to check whether the **/StartMinimized** command-line argument was provided; if so, it opens the main window with a <xref:System.Windows.WindowState> of <xref:System.Windows.WindowState.Minimized>.</span></span> <span data-ttu-id="dc885-221"><xref:System.Windows.Window.WindowState%2A> プロパティはプログラムで設定する必要があるため、メイン <xref:System.Windows.Window> をコードで明示的に開く必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="dc885-221">Note that because the <xref:System.Windows.Window.WindowState%2A> property must be set programmatically, the main <xref:System.Windows.Window> must be opened explicitly in code.</span></span>

<span data-ttu-id="dc885-222">XBAP は、ClickOnce 配置を使用して起動されるため、コマンド ライン引数を処理できません (「[WPF アプリケーションの配置](deploying-a-wpf-application-wpf.md)」を参照)。</span><span class="sxs-lookup"><span data-stu-id="dc885-222">XBAPs cannot retrieve and process command-line arguments because they are launched using ClickOnce deployment (see [Deploying a WPF Application](deploying-a-wpf-application-wpf.md)).</span></span> <span data-ttu-id="dc885-223">ただし、起動に使用される URL のクエリ文字列パラメーターを取得して処理することはできます。</span><span class="sxs-lookup"><span data-stu-id="dc885-223">However, they can retrieve and process query string parameters from the URLs that are used to launch them.</span></span>

<a name="Application_Activation_and_Deactivation"></a>

### <a name="application-activation-and-deactivation"></a><span data-ttu-id="dc885-224">アプリケーションのアクティブ化と非アクティブ化</span><span class="sxs-lookup"><span data-stu-id="dc885-224">Application Activation and Deactivation</span></span>

<span data-ttu-id="dc885-225">Windows では、ユーザーがアプリケーションを切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="dc885-225">Windows allows users to switch between applications.</span></span> <span data-ttu-id="dc885-226">最も一般的な方法は、Alt キーを押しながら Tab キーを押す方法です。</span><span class="sxs-lookup"><span data-stu-id="dc885-226">The most common way is to use the ALT+TAB key combination.</span></span> <span data-ttu-id="dc885-227">アプリケーションを切り替えることができるのは、ユーザーが選択できる可視の <xref:System.Windows.Window> がある場合だけです。</span><span class="sxs-lookup"><span data-stu-id="dc885-227">An application can only be switched to if it has a visible <xref:System.Windows.Window> that a user can select.</span></span> <span data-ttu-id="dc885-228">現在選択されている <xref:System.Windows.Window> は、"*アクティブ ウィンドウ*" であり ("*フォアグラウンド ウィンドウ*" とも呼ばれます)、ユーザー入力を受け取る <xref:System.Windows.Window> です。</span><span class="sxs-lookup"><span data-stu-id="dc885-228">The currently selected <xref:System.Windows.Window> is the *active window* (also known as the *foreground window*) and is the <xref:System.Windows.Window> that receives user input.</span></span> <span data-ttu-id="dc885-229">アクティブ ウィンドウを持つアプリケーションは、"*アクティブ アプリケーション*" (または "*フォア グラウンド アプリケーション*") です。</span><span class="sxs-lookup"><span data-stu-id="dc885-229">The application with the active window is the *active application* (or *foreground application*).</span></span> <span data-ttu-id="dc885-230">アプリケーションは、次の状況でアクティブ アプリケーションになります。</span><span class="sxs-lookup"><span data-stu-id="dc885-230">An application becomes the active application in the following circumstances:</span></span>

- <span data-ttu-id="dc885-231">起動され、<xref:System.Windows.Window> を表示している。</span><span class="sxs-lookup"><span data-stu-id="dc885-231">It is launched and shows a <xref:System.Windows.Window>.</span></span>

- <span data-ttu-id="dc885-232">ユーザーがアプリケーションの <xref:System.Windows.Window> を選択することによって、別のアプリケーションから切り替えた。</span><span class="sxs-lookup"><span data-stu-id="dc885-232">A user switches from another application by selecting a <xref:System.Windows.Window> in the application.</span></span>

<span data-ttu-id="dc885-233">アプリケーションがアクティブになったことは、<xref:System.Windows.Application.Activated?displayProperty=nameWithType> イベントを処理することによって検出できます。</span><span class="sxs-lookup"><span data-stu-id="dc885-233">You can detect when an application becomes active by handling the <xref:System.Windows.Application.Activated?displayProperty=nameWithType> event.</span></span>

<span data-ttu-id="dc885-234">同様に、アプリケーションは、次の状況で非アクティブになります。</span><span class="sxs-lookup"><span data-stu-id="dc885-234">Likewise, an application can become inactive in the following circumstances:</span></span>

- <span data-ttu-id="dc885-235">ユーザーが現在のアプリケーションから別のアプリケーションに切り替えた。</span><span class="sxs-lookup"><span data-stu-id="dc885-235">A user switches to another application from the current one.</span></span>

- <span data-ttu-id="dc885-236">アプリケーションがシャットダウンされた。</span><span class="sxs-lookup"><span data-stu-id="dc885-236">When the application shuts down.</span></span>

<span data-ttu-id="dc885-237">アプリケーションが非アクティブになったことは、<xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> イベントを処理することによって検出できます。</span><span class="sxs-lookup"><span data-stu-id="dc885-237">You can detect when an application becomes inactive by handling the <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> event.</span></span>

<span data-ttu-id="dc885-238">次のコードでは、<xref:System.Windows.Application.Activated> および <xref:System.Windows.Application.Deactivated> イベントを処理して、アプリケーションがアクティブかどうかを確認する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="dc885-238">The following code shows how to handle the <xref:System.Windows.Application.Activated> and <xref:System.Windows.Application.Deactivated> events to determine whether an application is active.</span></span>

[!code-xaml[ApplicationActivationSnippets#DetectActivationStateXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationActivationSnippets/CSharp/App.xaml#detectactivationstatexaml)]

[!code-csharp[ApplicationActivationSnippets#DetectActivationStateCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationActivationSnippets/CSharp/App.xaml.cs#detectactivationstatecodebehind)]
[!code-vb[ApplicationActivationSnippets#DetectActivationStateCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationActivationSnippets/visualbasic/application.xaml.vb#detectactivationstatecodebehind)]

<span data-ttu-id="dc885-239"><xref:System.Windows.Window> もアクティブまたは非アクティブにできます。</span><span class="sxs-lookup"><span data-stu-id="dc885-239">A <xref:System.Windows.Window> can also be activated and deactivated.</span></span> <span data-ttu-id="dc885-240">詳細については、「<xref:System.Windows.Window.Activated?displayProperty=nameWithType>」および「<xref:System.Windows.Window.Deactivated?displayProperty=nameWithType>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc885-240">See <xref:System.Windows.Window.Activated?displayProperty=nameWithType> and <xref:System.Windows.Window.Deactivated?displayProperty=nameWithType> for more information.</span></span>

> [!NOTE]
> <span data-ttu-id="dc885-241"><xref:System.Windows.Application.Activated?displayProperty=nameWithType> も <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> も、XBAP については発生しません。</span><span class="sxs-lookup"><span data-stu-id="dc885-241">Neither <xref:System.Windows.Application.Activated?displayProperty=nameWithType> nor <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> is raised for XBAPs.</span></span>

<a name="Application_Shutdown"></a>

### <a name="application-shutdown"></a><span data-ttu-id="dc885-242">アプリケーションのシャットダウン</span><span class="sxs-lookup"><span data-stu-id="dc885-242">Application Shutdown</span></span>

<span data-ttu-id="dc885-243">アプリケーションの有効期間は、シャット ダウンされると終了します。シャットダウンは、次の理由で発生します。</span><span class="sxs-lookup"><span data-stu-id="dc885-243">The life of an application ends when it is shut down, which can occur for the following reasons:</span></span>

- <span data-ttu-id="dc885-244">ユーザーがすべての <xref:System.Windows.Window> を閉じた。</span><span class="sxs-lookup"><span data-stu-id="dc885-244">A user closes every <xref:System.Windows.Window>.</span></span>

- <span data-ttu-id="dc885-245">ユーザーがメイン <xref:System.Windows.Window> を閉じた。</span><span class="sxs-lookup"><span data-stu-id="dc885-245">A user closes the main <xref:System.Windows.Window>.</span></span>

- <span data-ttu-id="dc885-246">ユーザーがログオフまたはシャットダウンして、Windows セッションを終了した。</span><span class="sxs-lookup"><span data-stu-id="dc885-246">A user ends the Windows session by logging off or shutting down.</span></span>

- <span data-ttu-id="dc885-247">アプリケーション固有の条件が満たされた。</span><span class="sxs-lookup"><span data-stu-id="dc885-247">An application-specific condition has been met.</span></span>

<span data-ttu-id="dc885-248">アプリケーションのシャット ダウンの管理を支援するために、<xref:System.Windows.Application> には、<xref:System.Windows.Application.Shutdown%2A> メソッド、<xref:System.Windows.Application.ShutdownMode%2A> プロパティ、<xref:System.Windows.Application.SessionEnding> イベント、<xref:System.Windows.Application.Exit> イベントが用意されています。</span><span class="sxs-lookup"><span data-stu-id="dc885-248">To help you manage application shutdown, <xref:System.Windows.Application> provides the <xref:System.Windows.Application.Shutdown%2A> method, the <xref:System.Windows.Application.ShutdownMode%2A> property, and the <xref:System.Windows.Application.SessionEnding> and <xref:System.Windows.Application.Exit> events.</span></span>

> [!NOTE]
> <span data-ttu-id="dc885-249"><xref:System.Windows.Application.Shutdown%2A> は、<xref:System.Security.Permissions.UIPermission> を持つアプリケーションからのみ呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="dc885-249"><xref:System.Windows.Application.Shutdown%2A> can only be called from applications that have <xref:System.Security.Permissions.UIPermission>.</span></span> <span data-ttu-id="dc885-250">スタンドアロン WPF アプリケーションには、常にこのアクセス許可があります。</span><span class="sxs-lookup"><span data-stu-id="dc885-250">Standalone WPF applications always have this permission.</span></span> <span data-ttu-id="dc885-251">一方、インターネット ゾーン部分信頼セキュリティ サンド ボックスで実行される XBAP には、このアクセス許可がありません。</span><span class="sxs-lookup"><span data-stu-id="dc885-251">However, XBAPs running in the Internet zone partial-trust security sandbox do not.</span></span>

#### <a name="shutdown-mode"></a><span data-ttu-id="dc885-252">シャットダウン モード</span><span class="sxs-lookup"><span data-stu-id="dc885-252">Shutdown Mode</span></span>

<span data-ttu-id="dc885-253">ほとんどのアプリケーションは、すべてのウィンドウが閉じられるか、メイン ウィンドウが閉じられたときにシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="dc885-253">Most applications shut down either when all the windows are closed or when the main window is closed.</span></span> <span data-ttu-id="dc885-254">ただし、場合によっては、他のアプリケーションに固有の条件によって、アプリケーションがシャット ダウンするタイミングに影響します。</span><span class="sxs-lookup"><span data-stu-id="dc885-254">Sometimes, however, other application-specific conditions may determine when an application shuts down.</span></span> <span data-ttu-id="dc885-255"><xref:System.Windows.Application.ShutdownMode%2A> に次のいずれかの <xref:System.Windows.ShutdownMode> 列挙値を設定することによって、アプリケーションがシャットダウンする条件を指定できます。</span><span class="sxs-lookup"><span data-stu-id="dc885-255">You can specify the conditions under which your application will shut down by setting <xref:System.Windows.Application.ShutdownMode%2A> with one of the following <xref:System.Windows.ShutdownMode> enumeration values:</span></span>

- <xref:System.Windows.ShutdownMode.OnLastWindowClose>

- <xref:System.Windows.ShutdownMode.OnMainWindowClose>

- <xref:System.Windows.ShutdownMode.OnExplicitShutdown>

<span data-ttu-id="dc885-256"><xref:System.Windows.Application.ShutdownMode%2A> の既定値は <xref:System.Windows.ShutdownMode.OnLastWindowClose> であり、アプリケーションの最後のウィンドウがユーザーによって閉じられたときにアプリケーションが自動的にシャットダウンすることを意味します。</span><span class="sxs-lookup"><span data-stu-id="dc885-256">The default value of <xref:System.Windows.Application.ShutdownMode%2A> is <xref:System.Windows.ShutdownMode.OnLastWindowClose>, which means that an application automatically shuts down when the last window in the application is closed by the user.</span></span> <span data-ttu-id="dc885-257">一方、メイン ウィンドウが閉じられたときにアプリケーションがシャットダウンするようにする必要がある場合は、<xref:System.Windows.Application.ShutdownMode%2A> を <xref:System.Windows.ShutdownMode.OnMainWindowClose> に設定すると、WPF は自動的にシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="dc885-257">However, if your application should be shut down when the main window is closed, WPF automatically does that if you set <xref:System.Windows.Application.ShutdownMode%2A> to <xref:System.Windows.ShutdownMode.OnMainWindowClose>.</span></span> <span data-ttu-id="dc885-258">これを次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="dc885-258">This is shown in the following example.</span></span>

[!code-xaml[ApplicationShutdownModeSnippets#OnMainWindowCloseMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationShutdownModeSnippets/CS/Page1.xaml#onmainwindowclosemarkup)]

<span data-ttu-id="dc885-259">アプリケーション固有のシャットダウン条件があるときは、<xref:System.Windows.Application.ShutdownMode%2A> を <xref:System.Windows.ShutdownMode.OnExplicitShutdown> に設定します。</span><span class="sxs-lookup"><span data-stu-id="dc885-259">When you have application-specific shutdown conditions, you set <xref:System.Windows.Application.ShutdownMode%2A> to <xref:System.Windows.ShutdownMode.OnExplicitShutdown>.</span></span> <span data-ttu-id="dc885-260">この場合、明示的に <xref:System.Windows.Application.Shutdown%2A> メソッドを呼び出すことによってアプリケーションをシャット ダウンする必要があります。そうしないと、すべてのウィンドウが閉じられた場合でも、アプリケーションは実効を続けます。</span><span class="sxs-lookup"><span data-stu-id="dc885-260">In this case, it is your responsibility to shut an application down by explicitly calling the <xref:System.Windows.Application.Shutdown%2A> method; otherwise, your application will continue running even if all the windows are closed.</span></span> <span data-ttu-id="dc885-261"><xref:System.Windows.Application.Shutdown%2A> は、<xref:System.Windows.Application.ShutdownMode%2A> が <xref:System.Windows.ShutdownMode.OnLastWindowClose> または <xref:System.Windows.ShutdownMode.OnMainWindowClose> のときに暗黙的に呼び出されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="dc885-261">Note that <xref:System.Windows.Application.Shutdown%2A> is called implicitly when the <xref:System.Windows.Application.ShutdownMode%2A> is either <xref:System.Windows.ShutdownMode.OnLastWindowClose> or <xref:System.Windows.ShutdownMode.OnMainWindowClose>.</span></span>

> [!NOTE]
> <span data-ttu-id="dc885-262"><xref:System.Windows.Application.ShutdownMode%2A> は、XBAP から設定できますが、無視されます。XBAP は、ブラウザーで他にナビゲートされたか、または XBAP をホストするブラウザーが閉じられると、必ずシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="dc885-262"><xref:System.Windows.Application.ShutdownMode%2A> can be set from an XBAP, but it is ignored; an XBAP is always shut down when it is navigated away from in a browser or when the browser that hosts the XBAP is closed.</span></span> <span data-ttu-id="dc885-263">詳細については、「[ナビゲーションの概要](navigation-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc885-263">For more information, see [Navigation Overview](navigation-overview.md).</span></span>

#### <a name="session-ending"></a><span data-ttu-id="dc885-264">セッションの終了</span><span class="sxs-lookup"><span data-stu-id="dc885-264">Session Ending</span></span>

<span data-ttu-id="dc885-265"><xref:System.Windows.Application.ShutdownMode%2A> プロパティによって記述されるシャットダウン条件は、アプリケーションに固有です。</span><span class="sxs-lookup"><span data-stu-id="dc885-265">The shutdown conditions that are described by the <xref:System.Windows.Application.ShutdownMode%2A> property are specific to an application.</span></span> <span data-ttu-id="dc885-266">ただし、場合によっては、アプリケーションは、外部条件の結果としてシャットダウンすることもあります。</span><span class="sxs-lookup"><span data-stu-id="dc885-266">In some cases, though, an application may shut down as a result of an external condition.</span></span> <span data-ttu-id="dc885-267">最も一般的な外部条件は、ユーザーが次の操作によって Windows セッションを終了した場合です。</span><span class="sxs-lookup"><span data-stu-id="dc885-267">The most common external condition occurs when a user ends the Windows session by the following actions:</span></span>

- <span data-ttu-id="dc885-268">ログオフ</span><span class="sxs-lookup"><span data-stu-id="dc885-268">Logging off</span></span>

- <span data-ttu-id="dc885-269">シャット ダウン</span><span class="sxs-lookup"><span data-stu-id="dc885-269">Shutting down</span></span>

- <span data-ttu-id="dc885-270">再起動</span><span class="sxs-lookup"><span data-stu-id="dc885-270">Restarting</span></span>

- <span data-ttu-id="dc885-271">休止</span><span class="sxs-lookup"><span data-stu-id="dc885-271">Hibernating</span></span>

<span data-ttu-id="dc885-272">Windows セッションの終了を検出するには、次の例に示されているように、<xref:System.Windows.Application.SessionEnding> イベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="dc885-272">To detect when a Windows session ends, you can handle the <xref:System.Windows.Application.SessionEnding> event, as illustrated in the following example.</span></span>

[!code-xaml[ApplicationSessionEndingSnippets#HandlingSessionEndingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/CSharp/App.xaml#handlingsessionendingxaml)]

[!code-csharp[ApplicationSessionEndingSnippets#HandlingSessionEndingCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/CSharp/App.xaml.cs#handlingsessionendingcodebehind)]
[!code-vb[ApplicationSessionEndingSnippets#HandlingSessionEndingCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/visualbasic/application.xaml.vb#handlingsessionendingcodebehind)]

<span data-ttu-id="dc885-273">この例のコードでは、<xref:System.Windows.SessionEndingCancelEventArgs.ReasonSessionEnding%2A> プロパティを調べて、Windows セッションの終了方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="dc885-273">In this example, the code inspects the <xref:System.Windows.SessionEndingCancelEventArgs.ReasonSessionEnding%2A> property to determine how the Windows session is ending.</span></span> <span data-ttu-id="dc885-274">この値を使用して、ユーザーに確認メッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="dc885-274">It uses this value to display a confirmation message to the user.</span></span> <span data-ttu-id="dc885-275">ユーザーがセッションの終了を意図していない場合、コードでは <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> を `true` に設定して、Windows セッションが終了しないようにします。</span><span class="sxs-lookup"><span data-stu-id="dc885-275">If the user does not want the session to end, the code sets <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> to `true` to prevent the Windows session from ending.</span></span>

> [!NOTE]
> <span data-ttu-id="dc885-276"><xref:System.Windows.Application.SessionEnding> は、XBAP に対しては発生しません。</span><span class="sxs-lookup"><span data-stu-id="dc885-276"><xref:System.Windows.Application.SessionEnding> is not raised for XBAPs.</span></span>

#### <a name="exit"></a><span data-ttu-id="dc885-277">終了</span><span class="sxs-lookup"><span data-stu-id="dc885-277">Exit</span></span>

<span data-ttu-id="dc885-278">アプリケーションがシャット ダウンするときには、アプリケーション状態の保存など、いくつかの最終処理を実行しなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="dc885-278">When an application shuts down, it may need to perform some final processing, such as persisting application state.</span></span> <span data-ttu-id="dc885-279">このような状況では、次の例の `App_Exit` イベント ハンドラーで行われているように、<xref:System.Windows.Application.Exit> イベントを処理できます。</span><span class="sxs-lookup"><span data-stu-id="dc885-279">For these situations, you can handle the <xref:System.Windows.Application.Exit> event, as the `App_Exit` event handler does in the following example.</span></span> <span data-ttu-id="dc885-280">これは、*App.xaml* ファイル内でイベント ハンドラーとして定義されています。</span><span class="sxs-lookup"><span data-stu-id="dc885-280">It is defined as an event handler in the *App.xaml* file.</span></span> <span data-ttu-id="dc885-281">その実装は、*App.xaml.cs* ファイルと *Application.xaml.vb* ファイルで強調表示されています。</span><span class="sxs-lookup"><span data-stu-id="dc885-281">Its implementation is highlighted in the *App.xaml.cs* and *Application.xaml.vb* files.</span></span>

[!code-xaml[Defining-the-Exit-event-handler](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml?highlight=1-7)]

[!code-csharp[Handling-the-Exit-event](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs?highlight=42-55)]
[!code-vb[Handling-the-Exit-event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb?highlight=34-45)]

<span data-ttu-id="dc885-282">完全な例については、「[アプリケーション セッション全体でアプリケーション スコープのプロパティを永続化および復元する](persist-and-restore-application-scope-properties.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc885-282">For the complete example, see [Persist and Restore Application-Scope Properties Across Application Sessions](persist-and-restore-application-scope-properties.md).</span></span>

<span data-ttu-id="dc885-283"><xref:System.Windows.Application.Exit> は、スタンドアロン アプリケーションと XBAP の両方によって処理できます。</span><span class="sxs-lookup"><span data-stu-id="dc885-283"><xref:System.Windows.Application.Exit> can be handled by both standalone applications and XBAPs.</span></span> <span data-ttu-id="dc885-284">XBAP では、次の状況で <xref:System.Windows.Application.Exit> が発生します。</span><span class="sxs-lookup"><span data-stu-id="dc885-284">For XBAPs, <xref:System.Windows.Application.Exit> is raised when in the following circumstances:</span></span>

- <span data-ttu-id="dc885-285">XBAP から外部にナビゲートされた。</span><span class="sxs-lookup"><span data-stu-id="dc885-285">An XBAP is navigated away from.</span></span>

- <span data-ttu-id="dc885-286">Internet Explorer で、XBAP をホストしているタブが閉じられた。</span><span class="sxs-lookup"><span data-stu-id="dc885-286">In Internet Explorer, when the tab that is hosting the XBAP is closed.</span></span>

- <span data-ttu-id="dc885-287">ブラウザーが閉じられた。</span><span class="sxs-lookup"><span data-stu-id="dc885-287">When the browser is closed.</span></span>

#### <a name="exit-code"></a><span data-ttu-id="dc885-288">終了コード</span><span class="sxs-lookup"><span data-stu-id="dc885-288">Exit Code</span></span>

<span data-ttu-id="dc885-289">ほとんどのアプリケーションは、ユーザー要求に応じてオペレーティング システムから起動されます。</span><span class="sxs-lookup"><span data-stu-id="dc885-289">Applications are mostly launched by the operating system in response to a user request.</span></span> <span data-ttu-id="dc885-290">ただし、アプリケーションは、特定のタスクを実行するために、別のアプリケーションに起動されることもあります。</span><span class="sxs-lookup"><span data-stu-id="dc885-290">However, an application can be launched by another application to perform some specific task.</span></span> <span data-ttu-id="dc885-291">起動されたアプリケーションがシャット ダウンするとき、起動元のアプリケーションは、起動されたアプリケーションのシャット ダウン条件を知ならなければならないことがあります。</span><span class="sxs-lookup"><span data-stu-id="dc885-291">When the launched application shuts down, the launching application may want to know the condition under which the launched application shut down.</span></span> <span data-ttu-id="dc885-292">このような場合、Windows では、アプリケーションは終了時にアプリケーション終了コードを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="dc885-292">In these situations, Windows allows applications to return an application exit code on shutdown.</span></span> <span data-ttu-id="dc885-293">既定では、WPF アプリケーションは 0 の終了コード値を返します。</span><span class="sxs-lookup"><span data-stu-id="dc885-293">By default, WPF applications return an exit code value of 0.</span></span>

> [!NOTE]
> <span data-ttu-id="dc885-294">Visual Studio からデバッグする場合、アプリケーション終了コードは、アプリケーションのシャットダウン時に、 **[出力]** ウィンドウに次のようなメッセージで表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc885-294">When you debug from Visual Studio, the application exit code is displayed in the **Output** window when the application shuts down, in a message that looks like the following:</span></span>
>
> `The program '[5340] AWPFApp.vshost.exe: Managed' has exited with code 0 (0x0).`
>
> <span data-ttu-id="dc885-295">**[出力]** ウィンドウを開くには、 **[表示]** メニューの **[出力]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc885-295">You open the **Output** window by clicking **Output** on the **View** menu.</span></span>

<span data-ttu-id="dc885-296">終了コードを変更するには、<xref:System.Windows.Application.Shutdown%28System.Int32%29> オーバーロードを呼び出します。これは、終了コードとして整数引数を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="dc885-296">To change the exit code, you can call the <xref:System.Windows.Application.Shutdown%28System.Int32%29> overload, which accepts an integer argument to be the exit code:</span></span>

[!code-csharp[ApplicationExitSnippets#AppExitCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationExitSnippets/CSharp/MainWindow.xaml.cs#appexitcode)]
[!code-vb[ApplicationExitSnippets#AppExitCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationExitSnippets/visualbasic/mainwindow.xaml.vb#appexitcode)]

<span data-ttu-id="dc885-297"><xref:System.Windows.Application.Exit> イベントを処理することによって、終了コードの値を検出し、変更できます。</span><span class="sxs-lookup"><span data-stu-id="dc885-297">You can detect the value of the exit code, and change it, by handling the <xref:System.Windows.Application.Exit> event.</span></span> <span data-ttu-id="dc885-298"><xref:System.Windows.Application.Exit> イベント ハンドラーに渡される <xref:System.Windows.ExitEventArgs> では、<xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A> プロパティで終了コードへのアクセスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="dc885-298">The <xref:System.Windows.Application.Exit> event handler is passed an <xref:System.Windows.ExitEventArgs> which provides access to the exit code with the <xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A> property.</span></span> <span data-ttu-id="dc885-299">詳細については、「<xref:System.Windows.Application.Exit>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc885-299">For more information, see <xref:System.Windows.Application.Exit>.</span></span>

> [!NOTE]
> <span data-ttu-id="dc885-300">終了コードは、スタンドアロン アプリケーションと XBAP の両方で設定できます。</span><span class="sxs-lookup"><span data-stu-id="dc885-300">You can set the exit code in both standalone applications and XBAPs.</span></span> <span data-ttu-id="dc885-301">ただし、XBAP の場合、終了コード値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="dc885-301">However, the exit code value is ignored for XBAPs.</span></span>

<a name="Unhandled_Exceptions"></a>

### <a name="unhandled-exceptions"></a><span data-ttu-id="dc885-302">未処理の例外</span><span class="sxs-lookup"><span data-stu-id="dc885-302">Unhandled Exceptions</span></span>

<span data-ttu-id="dc885-303">ときには、アプリケーションは、予期しない例外がスローされたときなど、異常な条件下でシャットダウンすることがあります。</span><span class="sxs-lookup"><span data-stu-id="dc885-303">Sometimes an application may shut down under abnormal conditions, such as when an unanticipated exception is thrown.</span></span> <span data-ttu-id="dc885-304">この場合、アプリケーションには、例外を検出して処理するためのコードがありません。</span><span class="sxs-lookup"><span data-stu-id="dc885-304">In this case, the application may not have the code to detect and process the exception.</span></span> <span data-ttu-id="dc885-305">この種類の例外は、未処理の例外と呼ばれます。アプリケーションが閉じられる前に、次の図に示されているような通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc885-305">This type of exception is an unhandled exception; a notification similar to that shown in the following figure is displayed before the application is closed.</span></span>

![ハンドルされない例外通知を示すスクリーンショット。](./media/application-management-overview/unhandled-exception-notification.png)

<span data-ttu-id="dc885-307">ユーザー エクスペリエンスの観点から、アプリケーションは、次のいずれか、またはすべてを行うことによって、この既定の動作を回避することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dc885-307">From the user experience perspective, it is better for an application to avoid this default behavior by doing some or all of the following:</span></span>

- <span data-ttu-id="dc885-308">わかりやすい情報を表示する。</span><span class="sxs-lookup"><span data-stu-id="dc885-308">Displaying user-friendly information.</span></span>

- <span data-ttu-id="dc885-309">アプリケーションの続行を試みる。</span><span class="sxs-lookup"><span data-stu-id="dc885-309">Attempting to keep an application running.</span></span>

- <span data-ttu-id="dc885-310">開発者向けの詳細な例外情報を Windows イベント ログに記録する。</span><span class="sxs-lookup"><span data-stu-id="dc885-310">Recording detailed, developer-friendly exception information in the Windows event log.</span></span>

<span data-ttu-id="dc885-311">このサポートを実装するには、<xref:System.Windows.Application.DispatcherUnhandledException> イベントが発生した未処理の例外を検出できることが前提になります。</span><span class="sxs-lookup"><span data-stu-id="dc885-311">Implementing this support depends on being able to detect unhandled exceptions, which is what the <xref:System.Windows.Application.DispatcherUnhandledException> event is raised for.</span></span>

[!code-xaml[detecting-unhandled-exceptions](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml#handledispatcherunhandledexceptionxaml)]

[!code-csharp[code-to-detect-unhandled-exceptions](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml.cs)]
[!code-vb[code-to-detect-unhandled-exceptions](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/visualbasic/application.xaml.vb)]

<span data-ttu-id="dc885-312"><xref:System.Windows.Application.DispatcherUnhandledException> イベント ハンドラーには、例外そのもの (<xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Exception%2A?displayProperty=nameWithType>) も含め、未処理の例外に関するコンテキスト情報を含む <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs> パラメーターが渡されます。</span><span class="sxs-lookup"><span data-stu-id="dc885-312">The <xref:System.Windows.Application.DispatcherUnhandledException> event handler is passed a <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs> parameter that contains contextual information regarding the unhandled exception, including the exception itself (<xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Exception%2A?displayProperty=nameWithType>).</span></span> <span data-ttu-id="dc885-313">この情報を使用して、例外の処理方法を決定できます。</span><span class="sxs-lookup"><span data-stu-id="dc885-313">You can use this information to determine how to handle the exception.</span></span>

<span data-ttu-id="dc885-314"><xref:System.Windows.Application.DispatcherUnhandledException> を処理するときには、<xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A?displayProperty=nameWithType> プロパティを `true` に設定する必要があります。そうしないと、WPF は例外を未処理のままとみなし、前述の既定の動作に戻ります。</span><span class="sxs-lookup"><span data-stu-id="dc885-314">When you handle <xref:System.Windows.Application.DispatcherUnhandledException>, you should set the <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A?displayProperty=nameWithType> property to `true`; otherwise, WPF still considers the exception to be unhandled and reverts to the default behavior described earlier.</span></span> <span data-ttu-id="dc885-315">ハンドルされない例外が発生し、<xref:System.Windows.Application.DispatcherUnhandledException> イベントが処理されないか、イベントが処理されても、<xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A> が `false` に設定されていた場合、アプリケーションはただちにシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="dc885-315">If an unhandled exception is raised and either the <xref:System.Windows.Application.DispatcherUnhandledException> event is not handled, or the event is handled and <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A> is set to `false`, the application shuts down immediately.</span></span> <span data-ttu-id="dc885-316">さらに、他の <xref:System.Windows.Application> イベントは発生しません。</span><span class="sxs-lookup"><span data-stu-id="dc885-316">Furthermore, no other <xref:System.Windows.Application> events are raised.</span></span> <span data-ttu-id="dc885-317">結果として、アプリケーションに、アプリケーションがシャットダウンする前に実行しなければならないコードがある場合は、<xref:System.Windows.Application.DispatcherUnhandledException> を処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc885-317">Consequently, you need to handle <xref:System.Windows.Application.DispatcherUnhandledException> if your application has code that must run before the application shuts down.</span></span>

<span data-ttu-id="dc885-318">アプリケーションは、未処理の例外の結果としてシャットダウンすることがありますが、通常は、次のセクションで説明されているように、ユーザーの要求に応じてシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="dc885-318">Although an application may shut down as a result of an unhandled exception, an application usually shuts down in response to a user request, as discussed in the next section.</span></span>

<a name="Application_Lifetime_Events"></a>

### <a name="application-lifetime-events"></a><span data-ttu-id="dc885-319">アプリケーションの有効期間イベント</span><span class="sxs-lookup"><span data-stu-id="dc885-319">Application Lifetime Events</span></span>

<span data-ttu-id="dc885-320">スタンドアロン アプリケーションと XBAP の有効期間は、厳密に同じわけではありません。</span><span class="sxs-lookup"><span data-stu-id="dc885-320">Standalone applications and XBAPs don't have exactly the same lifetimes.</span></span> <span data-ttu-id="dc885-321">次の図は、スタンドアロン アプリケーションの有効期間中の主なイベントと発生順を示しています。</span><span class="sxs-lookup"><span data-stu-id="dc885-321">The following figure illustrates the key events in the lifetime of a standalone application and shows the sequence in which they are raised.</span></span>

<span data-ttu-id="dc885-322">![スタンドアロン アプリケーション &#45; アプリケーション オブジェクト イベント](./media/applicationmodeloverview-applicationobjectevents.png "ApplicationModelOverview_ApplicationObjectEvents")</span><span class="sxs-lookup"><span data-stu-id="dc885-322">![Standalone Application &#45; Application Object Events](./media/applicationmodeloverview-applicationobjectevents.png "ApplicationModelOverview_ApplicationObjectEvents")</span></span>

<span data-ttu-id="dc885-323">同様に、次の図では、XBAP の有効期間中の主なイベントと発生順を示します。</span><span class="sxs-lookup"><span data-stu-id="dc885-323">Likewise, the following figure illustrates the key events in the lifetime of an XBAP, and shows the sequence in which they are raised.</span></span>

<span data-ttu-id="dc885-324">![XBAP &#45; アプリケーション オブジェクト イベント](./media/applicationmodeloverview-applicationobjectevents-xbap.png "ApplicationModelOverview_ApplicationObjectEvents_xbap")</span><span class="sxs-lookup"><span data-stu-id="dc885-324">![XBAP &#45; Application Object Events](./media/applicationmodeloverview-applicationobjectevents-xbap.png "ApplicationModelOverview_ApplicationObjectEvents_xbap")</span></span>

## <a name="see-also"></a><span data-ttu-id="dc885-325">関連項目</span><span class="sxs-lookup"><span data-stu-id="dc885-325">See also</span></span>

- <xref:System.Windows.Application>
- [<span data-ttu-id="dc885-326">WPF ウィンドウの概要</span><span class="sxs-lookup"><span data-stu-id="dc885-326">WPF Windows Overview</span></span>](wpf-windows-overview.md)
- [<span data-ttu-id="dc885-327">ナビゲーションの概要</span><span class="sxs-lookup"><span data-stu-id="dc885-327">Navigation Overview</span></span>](navigation-overview.md)
- [<span data-ttu-id="dc885-328">WPF アプリケーションのリソース ファイル、コンテンツ ファイル、およびデータ ファイル</span><span class="sxs-lookup"><span data-stu-id="dc885-328">WPF Application Resource, Content, and Data Files</span></span>](wpf-application-resource-content-and-data-files.md)
- [<span data-ttu-id="dc885-329">WPF におけるパッケージの URI</span><span class="sxs-lookup"><span data-stu-id="dc885-329">Pack URIs in WPF</span></span>](pack-uris-in-wpf.md)
- <span data-ttu-id="dc885-330">[アプリケーション モデル: 方法のトピック](/previous-versions/dotnet/netframework-4.0/ms749013(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="dc885-330">[Application Model: How-to Topics](/previous-versions/dotnet/netframework-4.0/ms749013(v=vs.100))</span></span>
- [<span data-ttu-id="dc885-331">アプリケーションの開発</span><span class="sxs-lookup"><span data-stu-id="dc885-331">Application Development</span></span>](index.md)
