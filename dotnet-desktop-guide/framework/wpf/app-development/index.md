---
title: アプリケーション開発
description: Windows Presentation Foundation (WPF) のフレームワークを使用してさまざまなアプリケーションを構築する方法について説明します。
ms.date: 01/26/2018
helpviewer_keywords:
- WPF [WPF], about application development
- application development [WPF], about
ms.assetid: 2996ce5e-81e9-49ae-881b-952db3dd1b7e
ms.openlocfilehash: af60a75736dd85c8dd94e7ee051e801e8aa66684
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96992813"
---
# <a name="application-development"></a><span data-ttu-id="007bb-103">アプリケーション開発</span><span class="sxs-lookup"><span data-stu-id="007bb-103">Application Development</span></span>
<a name="introduction"></a> <span data-ttu-id="007bb-104">Windows Presentation Foundation (WPF) は、次のような種類のアプリケーションの開発に使用できるプレゼンテーション フレームワークです。</span><span class="sxs-lookup"><span data-stu-id="007bb-104">Windows Presentation Foundation (WPF) is a presentation framework that can be used to develop the following types of applications:</span></span>  
  
- <span data-ttu-id="007bb-105">スタンドアロン アプリケーション (クライアント コンピューターにインストールし、そこから実行できる実行可能アセンブリとしてビルドされた従来スタイルの Windows アプリケーション)。</span><span class="sxs-lookup"><span data-stu-id="007bb-105">Standalone Applications (traditional style Windows applications built as executable assemblies that are installed to and run from the client computer).</span></span>  
  
- <span data-ttu-id="007bb-106">XAML ブラウザー アプリケーション (XBAP) (Microsoft Internet Explorer や Mozilla Firefox などの Web ブラウザーでホストされ、実行可能アセンブリとしてビルドされたナビゲーション ページで構成されるアプリケーション)。</span><span class="sxs-lookup"><span data-stu-id="007bb-106">XAML browser applications (XBAPs) (applications composed of navigation pages that are built as executable assemblies and hosted by Web browsers such as Microsoft Internet Explorer or Mozilla Firefox).</span></span>  
  
- <span data-ttu-id="007bb-107">カスタム コントロール ライブラリ (再利用可能なコントロールを含む被実行可能アセンブリ)。</span><span class="sxs-lookup"><span data-stu-id="007bb-107">Custom Control Libraries (non-executable assemblies containing reusable controls).</span></span>  
  
- <span data-ttu-id="007bb-108">クラス ライブラリ (再利用可能なクラスを含む非実行可能アセンブリ)。</span><span class="sxs-lookup"><span data-stu-id="007bb-108">Class Libraries (non-executable assemblies that contain reusable classes).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="007bb-109">Windows サービスで WPF 型を使用するのは避けることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="007bb-109">Using WPF types in a Windows service is strongly discouraged.</span></span> <span data-ttu-id="007bb-110">Windows サービスでこれらの機能を使用すると、期待どおりの動作が得られない場合があります。</span><span class="sxs-lookup"><span data-stu-id="007bb-110">If you attempt to use these features in a Windows service, they may not work as expected.</span></span>  
  
 <span data-ttu-id="007bb-111">WPF では、このような一連のアプリケーションをビルドするサービスを多数実装しています。</span><span class="sxs-lookup"><span data-stu-id="007bb-111">To build this set of applications, WPF implements a host of services.</span></span> <span data-ttu-id="007bb-112">このトピックでは、これらのサービスの概要を説明し、詳細情報へのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="007bb-112">This topic provides an overview of these services and where to find more information.</span></span>  

<a name="Application_Management"></a>
## <a name="application-management"></a><span data-ttu-id="007bb-113">アプリケーション構成の管理</span><span class="sxs-lookup"><span data-stu-id="007bb-113">Application Management</span></span>  
 <span data-ttu-id="007bb-114">実行可能 WPF アプリケーションは、一般に次のコアな機能セットを必要とします。</span><span class="sxs-lookup"><span data-stu-id="007bb-114">Executable WPF applications commonly require a core set of functionality that includes the following:</span></span>  
  
- <span data-ttu-id="007bb-115">共通アプリケーション インフラストラクチャを作成し、管理する (エントリ ポイント メソッドと、システム メッセージおよび入力メッセージを受け取るための Windows メッセージ ループの作成を含む)。</span><span class="sxs-lookup"><span data-stu-id="007bb-115">Creating and managing common application infrastructure (including creating an entry point method and a Windows message loop to receive system and input messages).</span></span>  
  
- <span data-ttu-id="007bb-116">アプリケーションの有効期間を追跡し、これと相互作用する。</span><span class="sxs-lookup"><span data-stu-id="007bb-116">Tracking and interacting with the lifetime of an application.</span></span>  
  
- <span data-ttu-id="007bb-117">コマンド ライン パラメーターを取得し、処理する。</span><span class="sxs-lookup"><span data-stu-id="007bb-117">Retrieving and processing command-line parameters.</span></span>  
  
- <span data-ttu-id="007bb-118">アプリケーション スコープのプロパティと [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] リソースを共有する。</span><span class="sxs-lookup"><span data-stu-id="007bb-118">Sharing application-scope properties and [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] resources.</span></span>  
  
- <span data-ttu-id="007bb-119">未処理の例外を検出し、処理する。</span><span class="sxs-lookup"><span data-stu-id="007bb-119">Detecting and processing unhandled exceptions.</span></span>  
  
- <span data-ttu-id="007bb-120">終了コードを返す。</span><span class="sxs-lookup"><span data-stu-id="007bb-120">Returning exit codes.</span></span>  
  
- <span data-ttu-id="007bb-121">スタンドアロン アプリケーションのウィンドウを管理する。</span><span class="sxs-lookup"><span data-stu-id="007bb-121">Managing windows in standalone applications.</span></span>  
  
- <span data-ttu-id="007bb-122">XAML ブラウザー アプリケーション (XBAP) や、ナビゲーション ウィンドウとフレームを持つスタンドアロン アプリケーションで、ナビゲーションを追跡する。</span><span class="sxs-lookup"><span data-stu-id="007bb-122">Tracking navigation in XAML browser applications (XBAPs), and standalone applications with navigation windows and frames.</span></span>  
  
 <span data-ttu-id="007bb-123">これらの機能は <xref:System.Windows.Application> クラスで実装します。このクラスをアプリケーションに追加するには、*アプリケーション定義* を使用します。</span><span class="sxs-lookup"><span data-stu-id="007bb-123">These capabilities are implemented by the <xref:System.Windows.Application> class, which you add to your applications using an *application definition*.</span></span>  
  
 <span data-ttu-id="007bb-124">詳細については、「[アプリケーション管理の概要](application-management-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="007bb-124">For more information, see [Application Management Overview](application-management-overview.md).</span></span>  
  
<a name="WPF_Application_Resource__Content__and_Data_Files"></a>
## <a name="wpf-application-resource-content-and-data-files"></a><span data-ttu-id="007bb-125">WPF アプリケーションのリソース ファイル、コンテンツ ファイル、およびデータ ファイル</span><span class="sxs-lookup"><span data-stu-id="007bb-125">WPF Application Resource, Content, and Data Files</span></span>  
 <span data-ttu-id="007bb-126">WPF では、埋め込みリソースを扱う Microsoft .NET Framework のコア サポートが拡張され、リソース、コンテンツ、データの 3 種類の非実行可能データ ファイルを追加サポートしています。</span><span class="sxs-lookup"><span data-stu-id="007bb-126">WPF extends the core support in the Microsoft .NET Framework for embedded resources with support for three kinds of non-executable data files: resource, content, and data.</span></span> <span data-ttu-id="007bb-127">詳細については、「[WPF アプリケーションのリソース、コンテンツ ファイル、およびデータ ファイル](wpf-application-resource-content-and-data-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="007bb-127">For more information, see [WPF Application Resource, Content, and Data Files](wpf-application-resource-content-and-data-files.md).</span></span>  
  
 <span data-ttu-id="007bb-128">WPF の非実行可能データ ファイルをサポートすることの重要なコンポーネントは、一意の URI を使用して、これらのファイルを識別し、読み込むことができることです。</span><span class="sxs-lookup"><span data-stu-id="007bb-128">A key component of the support for WPF non-executable data files is the ability to identify and load them using a unique URI.</span></span> <span data-ttu-id="007bb-129">詳細については、「[WPF におけるパック URI](pack-uris-in-wpf.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="007bb-129">For more information, see [Pack URIs in WPF](pack-uris-in-wpf.md).</span></span>  
  
<a name="Windows_and_Dialog_Boxes"></a>
## <a name="windows-and-dialog-boxes"></a><span data-ttu-id="007bb-130">ウィンドウとダイアログ ボックス</span><span class="sxs-lookup"><span data-stu-id="007bb-130">Windows and Dialog Boxes</span></span>  
 <span data-ttu-id="007bb-131">ユーザーは、ウィンドウを使用して、WPF スタンドアロン アプリケーションとやり取りします。</span><span class="sxs-lookup"><span data-stu-id="007bb-131">Users interact with WPF standalone applications through windows.</span></span> <span data-ttu-id="007bb-132">ウィンドウの目的は、アプリケーションのコンテンツをホストし、コンテンツとやり取りするためにユーザーが利用できるアプリケーション機能を公開することです。</span><span class="sxs-lookup"><span data-stu-id="007bb-132">The purpose of a window is to host application content and expose application functionality that usually allows users to interact with the content.</span></span> <span data-ttu-id="007bb-133">WPF では、ウィンドウは <xref:System.Windows.Window> クラスにカプセル化されます。このクラスは、次の機能を備えています。</span><span class="sxs-lookup"><span data-stu-id="007bb-133">In WPF, windows are encapsulated by the <xref:System.Windows.Window> class, which supports:</span></span>  
  
- <span data-ttu-id="007bb-134">ウィンドウを作成し、表示する。</span><span class="sxs-lookup"><span data-stu-id="007bb-134">Creating and showing windows.</span></span>  
  
- <span data-ttu-id="007bb-135">所有者と所有ウィンドウの関係を確立する。</span><span class="sxs-lookup"><span data-stu-id="007bb-135">Establishing owner/owned window relationships.</span></span>  
  
- <span data-ttu-id="007bb-136">ウィンドウの外観を構成する (サイズ、位置、アイコン、タイトル バーのテキスト、境界など)。</span><span class="sxs-lookup"><span data-stu-id="007bb-136">Configuring window appearance (for example, size, location, icons, title bar text, border).</span></span>  
  
- <span data-ttu-id="007bb-137">ウィンドウの有効期間を追跡し、これと相互作用する。</span><span class="sxs-lookup"><span data-stu-id="007bb-137">Tracking and interacting with the lifetime of a window.</span></span>  
  
 <span data-ttu-id="007bb-138">詳細については、「[WPF ウィンドウの概要](wpf-windows-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="007bb-138">For more information, see [WPF Windows Overview](wpf-windows-overview.md).</span></span>  
  
 <span data-ttu-id="007bb-139"><xref:System.Windows.Window> では、ダイアログ ボックスと呼ばれる特別な種類のウィンドウを作成できます。</span><span class="sxs-lookup"><span data-stu-id="007bb-139"><xref:System.Windows.Window> supports the ability to create a special type of window known as a dialog box.</span></span> <span data-ttu-id="007bb-140">モーダル ダイアログ ボックスとモードレス ダイアログ ボックスの両方の種類のダイアログ ボックスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="007bb-140">Both modal and modeless types of dialog boxes can be created.</span></span>  
  
 <span data-ttu-id="007bb-141">使いやすさと、アプリケーション間での再利用性およびユーザー エクスペリエンスの整合性というメリットの実現に、WPF では、<xref:Microsoft.Win32.OpenFileDialog>、<xref:Microsoft.Win32.SaveFileDialog>、<xref:System.Windows.Controls.PrintDialog> という 3 つの一般的な Windows のダイアログ ボックスを公開しています。</span><span class="sxs-lookup"><span data-stu-id="007bb-141">For convenience, and the benefits of reusability and a consistent user experience across applications, WPF exposes three of the common Windows dialog boxes: <xref:Microsoft.Win32.OpenFileDialog>, <xref:Microsoft.Win32.SaveFileDialog>, and <xref:System.Windows.Controls.PrintDialog>.</span></span>  
  
 <span data-ttu-id="007bb-142">メッセージ ボックスは、重要な情報をテキストでユーザーに表示し、単純な [はい]、[いいえ]、[OK]、[キャンセル] の応答を求めるために使用する特別なダイアログ ボックスです。</span><span class="sxs-lookup"><span data-stu-id="007bb-142">A message box is a special type of dialog box for showing important textual information to users, and for asking simple Yes/No/OK/Cancel questions.</span></span> <span data-ttu-id="007bb-143">メッセージ ボックスを作成および表示するには <xref:System.Windows.MessageBox> クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="007bb-143">You use the <xref:System.Windows.MessageBox> class to create and show message boxes.</span></span>  
  
 <span data-ttu-id="007bb-144">詳細については、「[ダイアログ ボックスの概要](dialog-boxes-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="007bb-144">For more information, see [Dialog Boxes Overview](dialog-boxes-overview.md).</span></span>  
  
<a name="Navigation"></a>
## <a name="navigation"></a><span data-ttu-id="007bb-145">ナビゲーション</span><span class="sxs-lookup"><span data-stu-id="007bb-145">Navigation</span></span>  
 <span data-ttu-id="007bb-146">WPF では、ページ (<xref:System.Windows.Controls.Page>) およびハイパーリンク (<xref:System.Windows.Documents.Hyperlink>) を使用した Web スタイルのナビゲーションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="007bb-146">WPF supports Web-style navigation using pages (<xref:System.Windows.Controls.Page>) and hyperlinks (<xref:System.Windows.Documents.Hyperlink>).</span></span> <span data-ttu-id="007bb-147">ナビゲーションは、次のようなさまざまな方法で実装できます。</span><span class="sxs-lookup"><span data-stu-id="007bb-147">Navigation can be implemented in a variety of ways that include the following:</span></span>  
  
- <span data-ttu-id="007bb-148">Web ブラウザーでホストされるスタンドアロンのページ。</span><span class="sxs-lookup"><span data-stu-id="007bb-148">Standalone pages that are hosted in a Web browser.</span></span>  
  
- <span data-ttu-id="007bb-149">Web ブラウザーでホストされる XBAP にコンパイルされるページ。</span><span class="sxs-lookup"><span data-stu-id="007bb-149">Pages compiled into an XBAP that is hosted in a Web browser.</span></span>  
  
- <span data-ttu-id="007bb-150">スタンドアロン アプリケーションにコンパイルされ、ナビゲーション ウィンドウ (<xref:System.Windows.Navigation.NavigationWindow>) によってホストされるページ。</span><span class="sxs-lookup"><span data-stu-id="007bb-150">Pages compiled into a standalone application and hosted by a navigation window (<xref:System.Windows.Navigation.NavigationWindow>).</span></span>  
  
- <span data-ttu-id="007bb-151">フレーム (<xref:System.Windows.Controls.Frame>) によってホストされるページ。フレームは、スタンドアロン ページか、XBAP またはスタンドアロン アプリケーションにコンパイルされたページでホストできます。</span><span class="sxs-lookup"><span data-stu-id="007bb-151">Pages that are hosted by a frame (<xref:System.Windows.Controls.Frame>), which may be hosted in a standalone page, or a page compiled into either an XBAP or a standalone application.</span></span>  
  
 <span data-ttu-id="007bb-152">WPF では、ナビゲーションに役立つ次の機能が実装されています。</span><span class="sxs-lookup"><span data-stu-id="007bb-152">To facilitate navigation, WPF implements the following:</span></span>  
  
- <span data-ttu-id="007bb-153">ナビゲーション要求を処理する共有ナビゲーション エンジンである <xref:System.Windows.Navigation.NavigationService>。このエンジンは <xref:System.Windows.Controls.Frame>、<xref:System.Windows.Navigation.NavigationWindow>、XBAP で使用され、アプリケーション内ナビゲーションをサポートします。</span><span class="sxs-lookup"><span data-stu-id="007bb-153"><xref:System.Windows.Navigation.NavigationService>, the shared navigation engine for processing navigation requests that is used by <xref:System.Windows.Controls.Frame>, <xref:System.Windows.Navigation.NavigationWindow>, and XBAPs to support intra-application navigation.</span></span>  
  
- <span data-ttu-id="007bb-154">ナビゲーションを開始するためのナビゲーション メソッド。</span><span class="sxs-lookup"><span data-stu-id="007bb-154">Navigation methods to initiate navigation.</span></span>  
  
- <span data-ttu-id="007bb-155">ナビゲーションの有効期間を追跡し、これと相互作用するためのナビゲーション イベント。</span><span class="sxs-lookup"><span data-stu-id="007bb-155">Navigation events to track and interact with navigation lifetime.</span></span>  
  
- <span data-ttu-id="007bb-156">履歴を使用した前方や後方へのナビゲーションの記憶。履歴は、調べたり、操作したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="007bb-156">Remembering back and forward navigation using a journal, which can also be inspected and manipulated.</span></span>  
  
 <span data-ttu-id="007bb-157">詳細については、「[ナビゲーションの概要](navigation-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="007bb-157">For information, see [Navigation Overview](navigation-overview.md).</span></span>  
  
 <span data-ttu-id="007bb-158">WPF は、構造化ナビゲーションと呼ばれる特別な種類のナビゲーションもサポートしています。</span><span class="sxs-lookup"><span data-stu-id="007bb-158">WPF also supports a special type of navigation known as structured navigation.</span></span> <span data-ttu-id="007bb-159">構造化ナビゲーションを使用すると、呼び出し元関数との一貫性が保たれた、構造化されて予測可能な形式でデータを返す 1 つ以上のページを呼び出す事ができます。</span><span class="sxs-lookup"><span data-stu-id="007bb-159">Structured navigation can be used to call one or more pages that return data in a structured and predictable way that is consistent with calling functions.</span></span> <span data-ttu-id="007bb-160">この機能は <xref:System.Windows.Navigation.PageFunction%601> クラスに依存します。このクラスの詳細については、「[構造化ナビゲーションの概要](structured-navigation-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="007bb-160">This capability depends on the <xref:System.Windows.Navigation.PageFunction%601> class, which is described further in [Structured Navigation Overview](structured-navigation-overview.md).</span></span> <span data-ttu-id="007bb-161">また、<xref:System.Windows.Navigation.PageFunction%601> を使用すると、複雑なナビゲーション トポロジを簡単に作成することもできます。詳細については、「[ナビゲーション トポロジの概要](navigation-topologies-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="007bb-161"><xref:System.Windows.Navigation.PageFunction%601> also serves to simplify the creation of complex navigation topologies, which are described in [Navigation Topologies Overview](navigation-topologies-overview.md).</span></span>  
  
<a name="Hosting"></a>
## <a name="hosting"></a><span data-ttu-id="007bb-162">ホスト</span><span class="sxs-lookup"><span data-stu-id="007bb-162">Hosting</span></span>  
 <span data-ttu-id="007bb-163">XBAP は、Microsoft Internet Explorer または Firefox でホストできます。</span><span class="sxs-lookup"><span data-stu-id="007bb-163">XBAPs can be hosted in Microsoft Internet Explorer or Firefox.</span></span> <span data-ttu-id="007bb-164">ホストのモデルによって考慮事項や制約が異なります。詳細については、「[ホスティング](hosting-wpf-applications.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="007bb-164">Each hosting model has its own set of considerations and constraints that are covered in [Hosting](hosting-wpf-applications.md).</span></span>  
  
<a name="Build_and_Deploy"></a>
## <a name="build-and-deploy"></a><span data-ttu-id="007bb-165">ビルドと配置</span><span class="sxs-lookup"><span data-stu-id="007bb-165">Build and Deploy</span></span>  
 <span data-ttu-id="007bb-166">単純な WPF アプリケーションはコマンドライン コンパイラを使用してコマンド プロンプトでビルドできますが、WPF に Visual Studio が統合されていることで、開発とビルドのプロセスを簡略化する追加のサポートがあります。</span><span class="sxs-lookup"><span data-stu-id="007bb-166">Although simple WPF applications can be built from a command prompt using command-line compilers, WPF integrates with Visual Studio to provide additional support that simplified the development and build process.</span></span> <span data-ttu-id="007bb-167">詳細については、「[WPF アプリケーションのビルド](building-a-wpf-application-wpf.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="007bb-167">For more information, see [Building a WPF Application](building-a-wpf-application-wpf.md).</span></span>  
  
 <span data-ttu-id="007bb-168">ビルドするアプリケーションの種類によって、選択する配置オプションが異なります。</span><span class="sxs-lookup"><span data-stu-id="007bb-168">Depending on the type of application you build, there are one or more deployment options to choose from.</span></span> <span data-ttu-id="007bb-169">詳細については、「[WPF アプリケーションの配置](deploying-a-wpf-application-wpf.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="007bb-169">For more information, see [Deploying a WPF Application](deploying-a-wpf-application-wpf.md).</span></span>  
  
<a name="related_topics"></a>
## <a name="related-topics"></a><span data-ttu-id="007bb-170">関連トピック</span><span class="sxs-lookup"><span data-stu-id="007bb-170">Related Topics</span></span>  
  
|<span data-ttu-id="007bb-171">Title</span><span class="sxs-lookup"><span data-stu-id="007bb-171">Title</span></span>|<span data-ttu-id="007bb-172">説明</span><span class="sxs-lookup"><span data-stu-id="007bb-172">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="007bb-173">アプリケーション管理の概要</span><span class="sxs-lookup"><span data-stu-id="007bb-173">Application Management Overview</span></span>](application-management-overview.md)|<span data-ttu-id="007bb-174">アプリケーションの有効期間、ウィンドウ、アプリケーション リソース、ナビゲーションの管理など、<xref:System.Windows.Application> クラスの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="007bb-174">Provides an overview of the <xref:System.Windows.Application> class including managing application lifetime, windows, application resources, and navigation.</span></span>|  
|[<span data-ttu-id="007bb-175">WPF のウィンドウ</span><span class="sxs-lookup"><span data-stu-id="007bb-175">Windows in WPF</span></span>](windows-in-wpf-applications.md)|<span data-ttu-id="007bb-176"><xref:System.Windows.Window> クラスおよびダイアログ ボックスの使い方など、アプリケーション内のウィンドウ管理の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="007bb-176">Provides details of managing windows in your application including how to use the <xref:System.Windows.Window> class and dialog boxes.</span></span>|  
|[<span data-ttu-id="007bb-177">ナビゲーションの概要</span><span class="sxs-lookup"><span data-stu-id="007bb-177">Navigation Overview</span></span>](navigation-overview.md)|<span data-ttu-id="007bb-178">アプリケーション内のページ間でのナビゲーション管理の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="007bb-178">Provides an overview of managing navigation between pages of your application.</span></span>|  
|[<span data-ttu-id="007bb-179">ホスティング</span><span class="sxs-lookup"><span data-stu-id="007bb-179">Hosting</span></span>](hosting-wpf-applications.md)|<span data-ttu-id="007bb-180">XAML ブラウザー アプリケーション (XBAP) の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="007bb-180">Provides an overview of XAML browser applications (XBAPs).</span></span>|  
|[<span data-ttu-id="007bb-181">ビルドと配置</span><span class="sxs-lookup"><span data-stu-id="007bb-181">Build and Deploy</span></span>](building-and-deploying-wpf-applications.md)|<span data-ttu-id="007bb-182">WPF アプリケーションをビルドして配置する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="007bb-182">Describes how to build and deploy your WPF application.</span></span>|  
|[<span data-ttu-id="007bb-183">Visual Studio での WPF の概要</span><span class="sxs-lookup"><span data-stu-id="007bb-183">Introduction to WPF in Visual Studio</span></span>](../getting-started/introduction-to-wpf-in-vs.md)|<span data-ttu-id="007bb-184">WPF の主な機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="007bb-184">Describes the main features of WPF.</span></span>|  
|[<span data-ttu-id="007bb-185">チュートリアル: 初めての WPF デスクトップ アプリケーション</span><span class="sxs-lookup"><span data-stu-id="007bb-185">Walkthrough: My first WPF desktop application</span></span>](../getting-started/walkthrough-my-first-wpf-desktop-application.md)|<span data-ttu-id="007bb-186">ページ ナビゲーション、レイアウト、コントロール、イメージ、スタイル、バインディングを使用する WPF アプリケーションの作成方法を示すチュートリアルです。</span><span class="sxs-lookup"><span data-stu-id="007bb-186">A walkthrough that shows how to create a WPF application using page navigation, layout, controls, images, styles, and binding.</span></span>|
