---
title: ウィンドウの概要
description: Windows Presentation Foundation (WPF) におけるスタンドアロン アプリケーションでのウィンドウの作成と管理の基本について説明します。
ms.date: 03/30/2017
ms.topic: overview
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XAML [WPF], displaying content via
- XAML pages [WPF], displaying
- content [WPF], displaying via XAML
- window objects [WPF]
- hosting [WPF], applications
- managing windows [WPF]
- dialog boxes [WPF]
- Page object [WPF]
- NavigationWindow objects [WPF]
- applications [WPF], hosting
- content [WPF], displaying
- events [WPF]
- content [WPF], displaying via procedural code
- modal windows [WPF]
- procedural code [WPF], displaying content via
- displaying content via procedural code [WPF]
- window management [WPF]
- displaying content [WPF]
- window events [WPF]
- windows [WPF]
- modal dialog boxes [WPF]
- displaying XAML pages [WPF]
ms.assetid: 737d04ec-8861-46c3-8d44-fa11d3528d23
ms.openlocfilehash: 270ae2c539a28d7d66e54aab362fe176679cd550
ms.sourcegitcommit: 7f48b9ecf8a30db42c8ecea0dd4df577736631a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2021
ms.locfileid: "99222314"
---
# <a name="wpf-windows-overview"></a><span data-ttu-id="de889-103">WPF ウィンドウの概要</span><span class="sxs-lookup"><span data-stu-id="de889-103">WPF Windows Overview</span></span>
<span data-ttu-id="de889-104">ユーザーは、ウィンドウを通じて Windows Presentation Foundation (WPF) スタンドアロン アプリケーションと対話します。</span><span class="sxs-lookup"><span data-stu-id="de889-104">Users interact with Windows Presentation Foundation (WPF) standalone applications through windows.</span></span> <span data-ttu-id="de889-105">ウィンドウの主な目的は、データを視覚化してユーザーがデータと対話できるコンテンツをホストすることです。</span><span class="sxs-lookup"><span data-stu-id="de889-105">The primary purpose of a window is to host content that visualizes data and enables users to interact with data.</span></span> <span data-ttu-id="de889-106">スタンドアロンの WPF アプリケーションには、<xref:System.Windows.Window> クラスを使用した独自のウィンドウがあります。</span><span class="sxs-lookup"><span data-stu-id="de889-106">Standalone WPF applications provide their own windows by using the <xref:System.Windows.Window> class.</span></span> <span data-ttu-id="de889-107">このトピックでは、<xref:System.Windows.Window> について説明してから、スタンドアロン アプリケーションにおけるウィンドウの作成と管理の基本について説明します。</span><span class="sxs-lookup"><span data-stu-id="de889-107">This topic introduces <xref:System.Windows.Window> before covering the fundamentals of creating and managing windows in standalone applications.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="de889-108">XAML ブラウザー アプリケーション (XBAP) や Loose [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] のページなど、ブラウザーによってホストされる WPF アプリケーションには、独自のウィンドウはありません。</span><span class="sxs-lookup"><span data-stu-id="de889-108">Browser-hosted WPF applications, including XAML browser applications (XBAPs) and loose [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] pages, don't provide their own windows.</span></span> <span data-ttu-id="de889-109">その代わり、Windows Internet Explorer で提供されるウィンドウでホストされます。</span><span class="sxs-lookup"><span data-stu-id="de889-109">Instead, they are hosted in windows provided by Windows Internet Explorer.</span></span> <span data-ttu-id="de889-110">「[WPF XAML ブラウザー アプリケーションの概要](wpf-xaml-browser-applications-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de889-110">See [WPF XAML Browser Applications Overview](wpf-xaml-browser-applications-overview.md).</span></span>  

<a name="TheWindowClass"></a>
## <a name="the-window-class"></a><span data-ttu-id="de889-111">ウィンドウ クラス</span><span class="sxs-lookup"><span data-stu-id="de889-111">The Window Class</span></span>  
 <span data-ttu-id="de889-112">次の図は、ウィンドウの構成パーツを示しています。</span><span class="sxs-lookup"><span data-stu-id="de889-112">The following figure illustrates the constituent parts of a window:</span></span>  
  
 ![ウィンドウ要素を示すスクリーンショット。](./media/wpf-windows-overview/window-constituent-elements.png)  
  
 <span data-ttu-id="de889-114">ウィンドウは、非クライアント領域とクライアント領域の 2 つに分かれます。</span><span class="sxs-lookup"><span data-stu-id="de889-114">A window is divided into two areas: the non-client area and client area.</span></span>  
  
 <span data-ttu-id="de889-115">ウィンドウの "*非クライアント領域*" は、WPF によって実装され、多くのウィンドウに共通のウィンドウのパーツが含まれます。これらのパーツには次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="de889-115">The *non-client area* of a window is implemented by WPF and includes the parts of a window that are common to most windows, including the following:</span></span>  
  
- <span data-ttu-id="de889-116">境界線。</span><span class="sxs-lookup"><span data-stu-id="de889-116">A border.</span></span>  
  
- <span data-ttu-id="de889-117">タイトル バー。</span><span class="sxs-lookup"><span data-stu-id="de889-117">A title bar.</span></span>  
  
- <span data-ttu-id="de889-118">アイコン。</span><span class="sxs-lookup"><span data-stu-id="de889-118">An icon.</span></span>  
  
- <span data-ttu-id="de889-119">最小化ボタン、最大化ボタン、および元に戻すボタン。</span><span class="sxs-lookup"><span data-stu-id="de889-119">Minimize, Maximize, and Restore buttons.</span></span>  
  
- <span data-ttu-id="de889-120">閉じるボタン。</span><span class="sxs-lookup"><span data-stu-id="de889-120">A Close button.</span></span>  
  
- <span data-ttu-id="de889-121">ウィンドウを最小化、最大化、元のサイズに戻す、移動、サイズ変更、および閉じるためのメニュー項目を含むシステム メニュー。</span><span class="sxs-lookup"><span data-stu-id="de889-121">A System menu with menu items that allow users to minimize, maximize, restore, move, resize, and close a window.</span></span>  
  
 <span data-ttu-id="de889-122">ウィンドウの "*クライアント領域*" は、ウィンドウの非クライアント領域の内側の領域であり、開発者がメニュー バー、ツール バー、コントロールなどのアプリケーション固有のコンテンツを追加するために使用します。</span><span class="sxs-lookup"><span data-stu-id="de889-122">The *client area* of a window is the area within a window's non-client area and is used by developers to add application-specific content, such as menu bars, tool bars, and controls.</span></span>  
  
 <span data-ttu-id="de889-123">WPF では、ウィンドウは <xref:System.Windows.Window> クラスでカプセル化され、これを使用して以下の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="de889-123">In WPF, a window is encapsulated by the <xref:System.Windows.Window> class that you use to do the following:</span></span>  
  
- <span data-ttu-id="de889-124">ウィンドウを表示する。</span><span class="sxs-lookup"><span data-stu-id="de889-124">Display a window.</span></span>  
  
- <span data-ttu-id="de889-125">ウィンドウのサイズ、位置、および外観を構成する。</span><span class="sxs-lookup"><span data-stu-id="de889-125">Configure the size, position, and appearance of a window.</span></span>  
  
- <span data-ttu-id="de889-126">アプリケーション固有のコンテンツをホストする。</span><span class="sxs-lookup"><span data-stu-id="de889-126">Host application-specific content.</span></span>  
  
- <span data-ttu-id="de889-127">ウィンドウの有効期間を管理する。</span><span class="sxs-lookup"><span data-stu-id="de889-127">Manage the lifetime of a window.</span></span>  
  
<a name="DefiningAWindow"></a>
## <a name="implementing-a-window"></a><span data-ttu-id="de889-128">ウィンドウの実装</span><span class="sxs-lookup"><span data-stu-id="de889-128">Implementing a Window</span></span>  
 <span data-ttu-id="de889-129">一般的なウィンドウの実装は、外観と動作で構成されます。"*外観*" では、ユーザーに対するウィンドウの表示方法を定義します。"*動作*" では、ユーザーがウィンドウと対話するときのウィンドウの動作を定義します。</span><span class="sxs-lookup"><span data-stu-id="de889-129">The implementation of a typical window comprises both appearance and behavior, where *appearance* defines how a window looks to users and *behavior* defines the way a window functions as users interact with it.</span></span> <span data-ttu-id="de889-130">WPF では、コードまたは [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] マークアップを使用して、ウィンドウの外観と動作を実装できます。</span><span class="sxs-lookup"><span data-stu-id="de889-130">In WPF, you can implement the appearance and behavior of a window using either code or [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] markup.</span></span>  
  
 <span data-ttu-id="de889-131">ただし、通常は、次の例に示すように、[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] マークアップを使用してウィンドウの外観を実装して、分離コードを使用してウィンドウの動作を実装します。</span><span class="sxs-lookup"><span data-stu-id="de889-131">In general, however, the appearance of a window is implemented using [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] markup, and its behavior is implemented using code-behind, as shown in the following example.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#MarkupAndCodeBehindWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
 <span data-ttu-id="de889-132">[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] マークアップ ファイルと分離コード ファイルを連携させるには、次のことが必要です。</span><span class="sxs-lookup"><span data-stu-id="de889-132">To enable a [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] markup file and code-behind file to work together, the following are required:</span></span>  
  
- <span data-ttu-id="de889-133">マークアップの `Window` 要素に `x:Class` 属性を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="de889-133">In markup, the `Window` element must include the `x:Class` attribute.</span></span> <span data-ttu-id="de889-134">アプリケーションのビルド時にマークアップ ファイルに `x:Class` が含まれていると、Microsoft Build Engine (MSBuild) により、`x:Class` 属性で指定された名前を持つ、<xref:System.Windows.Window> から派生した `partial` クラスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="de889-134">When the application is built, the existence of `x:Class` in the markup file causes Microsoft build engine (MSBuild) to create a `partial` class that derives from <xref:System.Windows.Window> and has the name that is specified by the `x:Class` attribute.</span></span> <span data-ttu-id="de889-135">そのためには、[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] スキーマ (`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`) に XML 名前空間宣言を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de889-135">This requires the addition of an XML namespace declaration for the [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] schema ( `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"` ).</span></span> <span data-ttu-id="de889-136">生成された `partial` クラスでは `InitializeComponent` メソッドが実装されます。このメソッドを呼び出すとイベントが登録され、マークアップで実装されるプロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="de889-136">The generated `partial` class implements the `InitializeComponent` method, which is called to register the events and set the properties that are implemented in markup.</span></span>  
  
- <span data-ttu-id="de889-137">分離コードでは、クラスは、マークアップ内の `x:Class` 属性で指定されている名前を持つ `partial` クラスでなければなりません。また、<xref:System.Windows.Window> から派生する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de889-137">In code-behind, the class must be a `partial` class with the same name that is specified by the `x:Class` attribute in markup, and it must derive from <xref:System.Windows.Window>.</span></span> <span data-ttu-id="de889-138">これによって、分離コード ファイルと、アプリケーションのビルド時にマークアップ ファイル用に生成される `partial` クラスとが関連付けられます (「[WPF アプリケーションのビルド](building-a-wpf-application-wpf.md)」を参照)。</span><span class="sxs-lookup"><span data-stu-id="de889-138">This allows the code-behind file to be associated with the `partial` class that is generated for the markup file when the application is built (see [Building a WPF Application](building-a-wpf-application-wpf.md)).</span></span>  
  
- <span data-ttu-id="de889-139">分離コードでは、<xref:System.Windows.Window> クラスによって実装されるコンストラクターで `InitializeComponent` メソッドが呼び出される必要があります。</span><span class="sxs-lookup"><span data-stu-id="de889-139">In code-behind, the <xref:System.Windows.Window> class must implement a constructor that calls the `InitializeComponent` method.</span></span> <span data-ttu-id="de889-140">`InitializeComponent` は、マークアップ ファイル用に生成された `partial` クラスによって実装されるもので、イベントの登録と、マークアップで定義されたプロパティの設定を実行します。</span><span class="sxs-lookup"><span data-stu-id="de889-140">`InitializeComponent` is implemented by the markup file's generated `partial` class to register events and set properties that are defined in markup.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="de889-141">Visual Studio を使用してプロジェクトに新しい <xref:System.Windows.Window> を追加すると、ここで説明したように、マークアップと分離コードの両方を使用して <xref:System.Windows.Window> が実装され、マークアップ ファイルと分離コード ファイル間の関連付けの作成に必要な構成が組み込まれます。</span><span class="sxs-lookup"><span data-stu-id="de889-141">When you add a new <xref:System.Windows.Window> to your project by using Visual Studio, the <xref:System.Windows.Window> is implemented using both markup and code-behind, and includes the necessary configuration to create the association between the markup and code-behind files as described here.</span></span>  
  
 <span data-ttu-id="de889-142">この構成が組み込まれると、[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] マークアップ内でウィンドウの外観を定義し、分離コード内でウィンドウの動作を実装することに集中できます。</span><span class="sxs-lookup"><span data-stu-id="de889-142">With this configuration in place, you can focus on defining the appearance of the window in [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] markup and implementing its behavior in code-behind.</span></span> <span data-ttu-id="de889-143">ボタンを含むウィンドウを [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] マークアップで実装し、そのボタンの <xref:System.Windows.Controls.Primitives.ButtonBase.Click> イベントのイベント ハンドラーを分離コードで実装する例を、次に示します。</span><span class="sxs-lookup"><span data-stu-id="de889-143">The following example shows a window with a button, implemented in [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] markup, and an event handler for the button's <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event, implemented in code-behind.</span></span>  
  
 [!code-xaml[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
<a name="ConfiguringWindowForMSBuild"></a>
## <a name="configuring-a-window-definition-for-msbuild"></a><span data-ttu-id="de889-144">MSBuild 用のウィンドウ定義の構成</span><span class="sxs-lookup"><span data-stu-id="de889-144">Configuring a Window Definition for MSBuild</span></span>  
 <span data-ttu-id="de889-145">ウィンドウを実装する方法によって、MSBuild を構成する方法が決定されます。</span><span class="sxs-lookup"><span data-stu-id="de889-145">How you implement your window determines how it is configured for MSBuild.</span></span> <span data-ttu-id="de889-146">[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] マークアップと分離コードの両方を使用して定義したウィンドウの場合:</span><span class="sxs-lookup"><span data-stu-id="de889-146">For a window that is defined using both [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] markup and code-behind:</span></span>  
  
- <span data-ttu-id="de889-147">XAML マークアップ ファイルは、MSBuild `Page` 項目として構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de889-147">XAML markup files are configured as MSBuild `Page` items.</span></span>  
  
- <span data-ttu-id="de889-148">分離コード ファイルは、MSBuild `Compile` 項目として構成されます。</span><span class="sxs-lookup"><span data-stu-id="de889-148">Code-behind files are configured as MSBuild `Compile` items.</span></span>  
  
 <span data-ttu-id="de889-149">これを次の MSBuild プロジェクト ファイルに示します。</span><span class="sxs-lookup"><span data-stu-id="de889-149">This is shown in the following MSBuild project file.</span></span>  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
    ...  
    <Page Include="MarkupAndCodeBehindWindow.xaml" />  
    <Compile Include=" MarkupAndCodeBehindWindow.xaml.cs" />  
    ...  
</Project>  
```  
  
 <span data-ttu-id="de889-150">WPF アプリケーションのビルドの詳細については、「[WPF アプリケーションのビルド](building-a-wpf-application-wpf.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de889-150">For information about building WPF applications, see [Building a WPF Application](building-a-wpf-application-wpf.md).</span></span>  
  
<a name="WindowLifetime"></a>
## <a name="window-lifetime"></a><span data-ttu-id="de889-151">ウィンドウの有効期間</span><span class="sxs-lookup"><span data-stu-id="de889-151">Window Lifetime</span></span>  
 <span data-ttu-id="de889-152">クラスと同様に、ウィンドウにも有効期間があります。有効期間は、ウィンドウが開いて最初にインスタンス化されたときに開始し、アクティブ化と非アクティブ化を経て、最後に閉じられるまで継続します。</span><span class="sxs-lookup"><span data-stu-id="de889-152">As with any class, a window has a lifetime that begins when it is first instantiated, after which it is opened, activated and deactivated, and eventually closed.</span></span>  

<a name="Opening_a_Window"></a>
### <a name="opening-a-window"></a><span data-ttu-id="de889-153">ウィンドウを開く</span><span class="sxs-lookup"><span data-stu-id="de889-153">Opening a Window</span></span>  
 <span data-ttu-id="de889-154">ウィンドウを開くには、次の例に示すように最初にインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="de889-154">To open a window, you first create an instance of it, which is demonstrated in the following example.</span></span>  
  
 [!code-xaml[WindowsOverviewStartupEventSnippets#AppMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml#appmarkup)]  
  
 [!code-csharp[WindowsOverviewStartupEventSnippets#AppCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml.cs#appcodebehind)]  
  
 <span data-ttu-id="de889-155">この例では、<xref:System.Windows.Application.Startup> イベントが発生してアプリケーションが開始するときに `MarkupAndCodeBehindWindow` がインスタンス化されます。</span><span class="sxs-lookup"><span data-stu-id="de889-155">In this example, the `MarkupAndCodeBehindWindow` is instantiated when the application starts, which occurs when the <xref:System.Windows.Application.Startup> event is raised.</span></span>  
  
 <span data-ttu-id="de889-156">ウィンドウがインスタンス化されると、<xref:System.Windows.Application> オブジェクトによって管理されるウィンドウのリストにそのウィンドウへの参照が自動的に追加されます (「<xref:System.Windows.Application.Windows%2A?displayProperty=nameWithType>」を参照)。</span><span class="sxs-lookup"><span data-stu-id="de889-156">When a window is instantiated, a reference to it is automatically added to a list of windows that is managed by the <xref:System.Windows.Application> object (see <xref:System.Windows.Application.Windows%2A?displayProperty=nameWithType>).</span></span> <span data-ttu-id="de889-157">さらに、インスタンス化される最初のウィンドウは、既定で <xref:System.Windows.Application> によってメイン アプリケーション ウィンドウとして設定されます (「<xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType>」を参照)。</span><span class="sxs-lookup"><span data-stu-id="de889-157">Additionally, the first window to be instantiated is, by default, set by <xref:System.Windows.Application> as the main application window (see <xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType>).</span></span>  
  
 <span data-ttu-id="de889-158">最後に <xref:System.Windows.Window.Show%2A> メソッドを呼び出すことによってウィンドウが開き、次の図に示すような結果になります。</span><span class="sxs-lookup"><span data-stu-id="de889-158">The window is finally opened by calling the <xref:System.Windows.Window.Show%2A> method; the result is shown in the following figure.</span></span>  
  
 ![Window.Show の呼び出しによって開いたウィンドウ](./media/wpf-windows-overview//window-opened-show-method.png)  
  
 <span data-ttu-id="de889-160"><xref:System.Windows.Window.Show%2A> を呼び出すことによって開いたウィンドウは、モードレス ウィンドウです。これは、ユーザーが同じアプリケーションで他のウィンドウをアクティブ化できるモードでアプリケーションが動作することを意味します。</span><span class="sxs-lookup"><span data-stu-id="de889-160">A window that is opened by calling <xref:System.Windows.Window.Show%2A> is a modeless window, which means that the application operates in a mode that allows users to activate other windows in the same application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="de889-161"><xref:System.Windows.Window.ShowDialog%2A> は、ダイアログ ボックスなどのウィンドウをモーダルで開くために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="de889-161"><xref:System.Windows.Window.ShowDialog%2A> is called to open windows such as dialog boxes modally.</span></span> <span data-ttu-id="de889-162">詳細については、「[ダイアログ ボックスの概要](dialog-boxes-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de889-162">See [Dialog Boxes Overview](dialog-boxes-overview.md) for more information.</span></span>  
  
 <span data-ttu-id="de889-163"><xref:System.Windows.Window.Show%2A> を呼び出すと、ウィンドウでは表示される前に初期化処理が実行され、ユーザーの入力を受け取ることのできるインフラストラクチャが確立されます。</span><span class="sxs-lookup"><span data-stu-id="de889-163">When <xref:System.Windows.Window.Show%2A> is called, a window performs initialization work before it is shown to establish infrastructure that allows it to receive user input.</span></span> <span data-ttu-id="de889-164">ウィンドウが初期化されると、<xref:System.Windows.Window.SourceInitialized> イベントが発生し、ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="de889-164">When the window is initialized, the <xref:System.Windows.Window.SourceInitialized> event is raised and the window is shown.</span></span>  
  
 <span data-ttu-id="de889-165">簡単な方法として、<xref:System.Windows.Application.StartupUri%2A> を設定し、アプリケーションの開始時に自動的に開く最初のウィンドウを指定できます。</span><span class="sxs-lookup"><span data-stu-id="de889-165">As a shortcut, <xref:System.Windows.Application.StartupUri%2A> can be set to specify the first window that is opened automatically when an application starts.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#ApplicationStartupUriMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/App.xaml#applicationstartupurimarkup)]  
  
 <span data-ttu-id="de889-166">アプリケーションが開始したら、<xref:System.Windows.Application.StartupUri%2A> の値で指定されたウィンドウがモードレスで開きます。内部的には、ウィンドウはその <xref:System.Windows.Window.Show%2A> メソッドを呼び出すことによって開かれます。</span><span class="sxs-lookup"><span data-stu-id="de889-166">When the application starts, the window specified by the value of <xref:System.Windows.Application.StartupUri%2A> is opened modelessly; internally, the window is opened by calling its <xref:System.Windows.Window.Show%2A> method.</span></span>  
  
<a name="Ownership"></a>
#### <a name="window-ownership"></a><span data-ttu-id="de889-167">ウィンドウの所有権</span><span class="sxs-lookup"><span data-stu-id="de889-167">Window Ownership</span></span>  
 <span data-ttu-id="de889-168"><xref:System.Windows.Window.Show%2A> メソッドを使用して開いたウィンドウと、そのウィンドウを作成したウィンドウには、暗黙的な関係はありません。ユーザーは、どちらのウィンドウとも、もう一方のウィンドウに関係なく対話できます。つまり、どちらのウィンドウでも次の作業ができます。</span><span class="sxs-lookup"><span data-stu-id="de889-168">A window that is opened by using the <xref:System.Windows.Window.Show%2A> method does not have an implicit relationship with the window that created it; users can interact with either window independently of the other, which means that either window can do the following:</span></span>  
  
- <span data-ttu-id="de889-169">もう一方の上に表示する (いずれかのウィンドウの <xref:System.Windows.Window.Topmost%2A> プロパティが `true` に設定されている場合を除く)。</span><span class="sxs-lookup"><span data-stu-id="de889-169">Cover the other (unless one of the windows has its <xref:System.Windows.Window.Topmost%2A> property set to `true`).</span></span>  
  
- <span data-ttu-id="de889-170">もう一方のウィンドウに影響を与えずに、最小化/最大化し、元のサイズに戻す。</span><span class="sxs-lookup"><span data-stu-id="de889-170">Be minimized, maximized, and restored without affecting the other.</span></span>  
  
 <span data-ttu-id="de889-171">一部のウィンドウには、そのウィンドウを開いたウィンドウとの関係が必要です。</span><span class="sxs-lookup"><span data-stu-id="de889-171">Some windows require a relationship with the window that opens them.</span></span> <span data-ttu-id="de889-172">たとえば、統合開発環境 (IDE) アプリケーションでは、プロパティ ウィンドウやツール ウィンドウのように、一般的に作成元のウィンドウの上に表示されるウィンドウが開く場合があります。</span><span class="sxs-lookup"><span data-stu-id="de889-172">For example, an Integrated Development Environment (IDE) application may open property windows and tool windows whose typical behavior is to cover the window that creates them.</span></span> <span data-ttu-id="de889-173">また、そのようなウィンドウは、必ず作成元のウィンドウと一緒に閉じ、最小化/最大化し、元のサイズに戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="de889-173">Furthermore, such windows should always close, minimize, maximize, and restore in concert with the window that created them.</span></span> <span data-ttu-id="de889-174">このような関係を確立するには、あるウィンドウが別のウィンドウを "*所有*" するようにします。そのためには、"*所有されているウィンドウ*" の <xref:System.Windows.Window.Owner%2A> プロパティに、"*オーナー ウィンドウ*" への参照を設定します。</span><span class="sxs-lookup"><span data-stu-id="de889-174">Such a relationship can be established by making one window *own* another, and is achieved by setting the <xref:System.Windows.Window.Owner%2A> property of the *owned window* with a reference to the *owner window*.</span></span> <span data-ttu-id="de889-175">これを次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="de889-175">This is shown in the following example.</span></span>  
  
 [!code-csharp[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/CSharp/MainWindow.xaml.cs#setwindowownercode)]
 [!code-vb[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/visualbasic/mainwindow.xaml.vb#setwindowownercode)]  
  
 <span data-ttu-id="de889-176">所有権が確立されると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="de889-176">After ownership is established:</span></span>  
  
- <span data-ttu-id="de889-177">所有されているウィンドウでは、<xref:System.Windows.Window.Owner%2A> プロパティの値を検査することによってオーナー ウィンドウを参照できます。</span><span class="sxs-lookup"><span data-stu-id="de889-177">The owned window can reference its owner window by inspecting the value of its <xref:System.Windows.Window.Owner%2A> property.</span></span>  
  
- <span data-ttu-id="de889-178">オーナー ウィンドウでは、<xref:System.Windows.Window.OwnedWindows%2A> プロパティの値を検査することによって、所有するすべてのウィンドウを検出できます。</span><span class="sxs-lookup"><span data-stu-id="de889-178">The owner window can discover all the windows it owns by inspecting the value of its <xref:System.Windows.Window.OwnedWindows%2A> property.</span></span>  
  
<a name="Preventing"></a>
#### <a name="preventing-window-activation"></a><span data-ttu-id="de889-179">ウィンドウのアクティブ化の防止</span><span class="sxs-lookup"><span data-stu-id="de889-179">Preventing Window Activation</span></span>  
 <span data-ttu-id="de889-180">表示されてもアクティブにしないことが適切なウィンドウもあります。インターネット メッセンジャーのようなアプリケーションの対話ウィンドウや、電子メール アプリケーションの通知ウィンドウなどです。</span><span class="sxs-lookup"><span data-stu-id="de889-180">There are scenarios where windows should not be activated when shown, such as conversation windows of an Internet messenger-style application or notification windows of an email application.</span></span>  
  
 <span data-ttu-id="de889-181">表示されるときにアクティブにしないウィンドウがアプリケーションにある場合は、<xref:System.Windows.Window.Show%2A> メソッドの初回呼び出し前に、<xref:System.Windows.Window.ShowActivated%2A> プロパティを `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="de889-181">If your application has a window that shouldn't be activated when shown, you can set its <xref:System.Windows.Window.ShowActivated%2A> property to `false` before calling the <xref:System.Windows.Window.Show%2A> method for the first time.</span></span> <span data-ttu-id="de889-182">結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="de889-182">As a consequence:</span></span>  
  
- <span data-ttu-id="de889-183">ウィンドウはアクティブになりません。</span><span class="sxs-lookup"><span data-stu-id="de889-183">The window is not activated.</span></span>  
  
- <span data-ttu-id="de889-184">ウィンドウの <xref:System.Windows.Window.Activated> イベントは発生しません。</span><span class="sxs-lookup"><span data-stu-id="de889-184">The window's <xref:System.Windows.Window.Activated> event is not raised.</span></span>  
  
- <span data-ttu-id="de889-185">現在アクティブなウィンドウは、アクティブのままです。</span><span class="sxs-lookup"><span data-stu-id="de889-185">The currently activated window remains activated.</span></span>  
  
 <span data-ttu-id="de889-186">ただし、ユーザーがクライアント領域または非クライアント領域をクリックすると、ウィンドウは直ちにアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="de889-186">The window will become activated, however, as soon as the user activates it by clicking either the client or non-client area.</span></span> <span data-ttu-id="de889-187">この場合、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="de889-187">In this case:</span></span>  
  
- <span data-ttu-id="de889-188">ウィンドウはアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="de889-188">The window is activated.</span></span>  
  
- <span data-ttu-id="de889-189">ウィンドウの <xref:System.Windows.Window.Activated> イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="de889-189">The window's <xref:System.Windows.Window.Activated> event is raised.</span></span>  
  
- <span data-ttu-id="de889-190">直前にアクティブだったウィンドウは非アクティブになります。</span><span class="sxs-lookup"><span data-stu-id="de889-190">The previously activated window is deactivated.</span></span>  
  
- <span data-ttu-id="de889-191">その後、ウィンドウの <xref:System.Windows.Window.Deactivated> イベントと <xref:System.Windows.Window.Activated> イベントが、ユーザーの操作への応答として想定どおりに発生します。</span><span class="sxs-lookup"><span data-stu-id="de889-191">The window's <xref:System.Windows.Window.Deactivated> and <xref:System.Windows.Window.Activated> events are subsequently raised as expected in response to user actions.</span></span>  
  
<a name="Window_Activation"></a>
### <a name="window-activation"></a><span data-ttu-id="de889-192">ウィンドウのアクティブ化</span><span class="sxs-lookup"><span data-stu-id="de889-192">Window Activation</span></span>  
 <span data-ttu-id="de889-193">ウィンドウを最初に開いたときは、そのウィンドウがアクティブ ウィンドウになります (<xref:System.Windows.Window.ShowActivated%2A> が `false` に設定されている場合を除く)。</span><span class="sxs-lookup"><span data-stu-id="de889-193">When a window is first opened, it becomes the active window (unless it is shown with <xref:System.Windows.Window.ShowActivated%2A> set to `false`).</span></span> <span data-ttu-id="de889-194">"*アクティブ ウィンドウ*" は、キー ストロークやマウス クリックなどのユーザー入力を現在キャプチャしているウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="de889-194">The *active window* is the window that is currently capturing user input, such as key strokes and mouse clicks.</span></span> <span data-ttu-id="de889-195">ウィンドウがアクティブになると、<xref:System.Windows.Window.Activated> イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="de889-195">When a window becomes active, it raises the <xref:System.Windows.Window.Activated> event.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="de889-196">ウィンドウが最初に開かれるとき、<xref:System.Windows.FrameworkElement.Loaded> イベントと <xref:System.Windows.Window.ContentRendered> イベントは、<xref:System.Windows.Window.Activated> イベントが発生した後にのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="de889-196">When a window is first opened, the <xref:System.Windows.FrameworkElement.Loaded> and <xref:System.Windows.Window.ContentRendered> events are raised only after the <xref:System.Windows.Window.Activated> event is raised.</span></span> <span data-ttu-id="de889-197">そのため、事実上、ウィンドウは <xref:System.Windows.Window.ContentRendered> が発生した場合にのみ開いたと見なすことができます。</span><span class="sxs-lookup"><span data-stu-id="de889-197">With this in mind, a window can effectively be considered opened when <xref:System.Windows.Window.ContentRendered> is raised.</span></span>  
  
 <span data-ttu-id="de889-198">ウィンドウがアクティブになった後で、ユーザーは同じアプリケーションの別のウィンドウをアクティブ化したり、別のアプリケーションをアクティブ化したりできます。</span><span class="sxs-lookup"><span data-stu-id="de889-198">After a window becomes active, a user can activate another window in the same application, or activate another application.</span></span> <span data-ttu-id="de889-199">このとき、現在アクティブなウィンドウが非アクティブ化され、<xref:System.Windows.Window.Deactivated> イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="de889-199">When that happens, the currently active window becomes deactivated and raises the <xref:System.Windows.Window.Deactivated> event.</span></span> <span data-ttu-id="de889-200">同様に、ユーザーが現在非アクティブなウィンドウを選択すると、ウィンドウは再びアクティブになり、<xref:System.Windows.Window.Activated> が発生します。</span><span class="sxs-lookup"><span data-stu-id="de889-200">Likewise, when the user selects a currently deactivated window, the window becomes active again and <xref:System.Windows.Window.Activated> is raised.</span></span>  
  
 <span data-ttu-id="de889-201">一般に、<xref:System.Windows.Window.Activated> と <xref:System.Windows.Window.Deactivated> を処理するのは、ウィンドウがアクティブなときにのみ実行できる機能を有効または無効にするためです。</span><span class="sxs-lookup"><span data-stu-id="de889-201">One common reason to handle <xref:System.Windows.Window.Activated> and <xref:System.Windows.Window.Deactivated> is to enable and disable functionality that can only run when a window is active.</span></span> <span data-ttu-id="de889-202">たとえば、ゲームやビデオ プレーヤーなど、ユーザーの一定の入力や介入が必要な対話型コンテンツが表示されるウィンドウがあります。</span><span class="sxs-lookup"><span data-stu-id="de889-202">For example, some windows display interactive content that requires constant user input or attention, including games and video players.</span></span> <span data-ttu-id="de889-203">この動作を実装するために <xref:System.Windows.Window.Activated> と <xref:System.Windows.Window.Deactivated> を処理する方法を、次の簡単なビデオ プレーヤーの例で示します。</span><span class="sxs-lookup"><span data-stu-id="de889-203">The following example is a simplified video player that demonstrates how to handle <xref:System.Windows.Window.Activated> and <xref:System.Windows.Window.Deactivated> to implement this behavior.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#ActivationDeactivationMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml#activationdeactivationmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml.cs#activationdeactivationcodebehind)]
 [!code-vb[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/CustomMediaPlayerWindow.xaml.vb#activationdeactivationcodebehind)]  
  
 <span data-ttu-id="de889-204">ウィンドウが非アクティブでも、バックグラウンドでコードを実行できる種類のアプリケーションもあります。</span><span class="sxs-lookup"><span data-stu-id="de889-204">Other types of applications may still run code in the background when a window is deactivated.</span></span> <span data-ttu-id="de889-205">たとえば、メール クライアントは、ユーザーが他のアプリケーションを使用している間もメール サーバーへのポーリングを続けています。</span><span class="sxs-lookup"><span data-stu-id="de889-205">For example, a mail client may continue polling the mail server while the user is using other applications.</span></span> <span data-ttu-id="de889-206">このようなアプリケーションは、メイン ウィンドウが非アクティブのときにも、別の動作や追加の動作を頻繁に実行します。</span><span class="sxs-lookup"><span data-stu-id="de889-206">Applications like these often provide different or additional behavior while the main window is deactivated.</span></span> <span data-ttu-id="de889-207">メール プログラムでは、新しいメール アイテムを受信トレイに追加し、通知アイコンをシステム トレイに追加することがあります。</span><span class="sxs-lookup"><span data-stu-id="de889-207">With respect to the mail program, this may mean both adding the new mail item to the inbox and adding a notification icon to the system tray.</span></span> <span data-ttu-id="de889-208">通知アイコンは、メール ウィンドウがアクティブでないときにのみ表示する必要があります。メール ウィンドウがアクティブかどうかは、<xref:System.Windows.Window.IsActive%2A> プロパティを検査することで確認できます。</span><span class="sxs-lookup"><span data-stu-id="de889-208">A notification icon need only be displayed when the mail window isn't active, which can be determined by inspecting the <xref:System.Windows.Window.IsActive%2A> property.</span></span>  
  
 <span data-ttu-id="de889-209">バックグラウンド タスクの完了時に、ユーザーに緊急に通知する必要がある場合は、<xref:System.Windows.Window.Activate%2A> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="de889-209">If a background task completes, a window may want to notify the user more urgently by calling <xref:System.Windows.Window.Activate%2A> method.</span></span> <span data-ttu-id="de889-210"><xref:System.Windows.Window.Activate%2A> を呼び出したときに、ユーザーが別のアクティブなアプリケーションと対話している場合は、ウィンドウのタスク バー ボタンが点滅します。</span><span class="sxs-lookup"><span data-stu-id="de889-210">If the user is interacting with another application activated when <xref:System.Windows.Window.Activate%2A> is called, the window's taskbar button flashes.</span></span> <span data-ttu-id="de889-211">ユーザーが現在のアプリケーションと対話している場合は、<xref:System.Windows.Window.Activate%2A> を呼び出すと、ウィンドウが前面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="de889-211">If a user is interacting with the current application, calling <xref:System.Windows.Window.Activate%2A> will bring the window to the foreground.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="de889-212"><xref:System.Windows.Application.Activated?displayProperty=nameWithType> イベントと <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> イベントを使用して、アプリケーションスコープのアクティベーションを処理できます。</span><span class="sxs-lookup"><span data-stu-id="de889-212">You can handle application-scope activation using the <xref:System.Windows.Application.Activated?displayProperty=nameWithType> and <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> events.</span></span>  
  
<a name="Closing_a_Window"></a>
### <a name="closing-a-window"></a><span data-ttu-id="de889-213">ウィンドウを閉じる</span><span class="sxs-lookup"><span data-stu-id="de889-213">Closing a Window</span></span>  
 <span data-ttu-id="de889-214">ウィンドウの有効期間は、表示されたときに開始し、ユーザーが閉じたときに終了します。</span><span class="sxs-lookup"><span data-stu-id="de889-214">The life of a window starts coming to an end when a user closes it.</span></span> <span data-ttu-id="de889-215">ウィンドウを閉じるには、非クライアント領域の要素を使用します。これには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="de889-215">A window can be closed by using elements in the non-client area, including the following:</span></span>  
  
- <span data-ttu-id="de889-216">**[システム]** メニューの **[閉じる]** 項目。</span><span class="sxs-lookup"><span data-stu-id="de889-216">The **Close** item of the **System** menu.</span></span>  
  
- <span data-ttu-id="de889-217">Alt キーを押しながら F4 キーを押す。</span><span class="sxs-lookup"><span data-stu-id="de889-217">Pressing ALT+F4.</span></span>  
  
- <span data-ttu-id="de889-218">**[閉じる]** ボタンを押す。</span><span class="sxs-lookup"><span data-stu-id="de889-218">Pressing the **Close** button.</span></span>  
  
 <span data-ttu-id="de889-219">クライアント領域にさらに機構を追加してウィンドウを閉じることもできます。その一般的な例を、次に示します。</span><span class="sxs-lookup"><span data-stu-id="de889-219">You can provide additional mechanisms to the client area to close a window, the more common of which include the following:</span></span>  
  
- <span data-ttu-id="de889-220">一般にメイン アプリケーション ウィンドウにある、 **[ファイル]** メニューの **[終了]** 項目。</span><span class="sxs-lookup"><span data-stu-id="de889-220">An **Exit** item in the **File** menu, typically for main application windows.</span></span>  
  
- <span data-ttu-id="de889-221">一般にアプリケーションの 2 次ウィンドウにある、 **[ファイル]** メニューの **[閉じる]** 項目。</span><span class="sxs-lookup"><span data-stu-id="de889-221">A **Close** item in the **File** menu, typically on a secondary application window.</span></span>  
  
- <span data-ttu-id="de889-222">一般にモーダル ダイアログ ボックスにある **[キャンセル]** ボタン。</span><span class="sxs-lookup"><span data-stu-id="de889-222">A **Cancel** button, typically on a modal dialog box.</span></span>  
  
- <span data-ttu-id="de889-223">一般にモードレス ダイアログ ボックスにある **[閉じる]** ボタン。</span><span class="sxs-lookup"><span data-stu-id="de889-223">A **Close** button, typically on a modeless dialog box.</span></span>  
  
 <span data-ttu-id="de889-224">これらのカスタム機構のいずれかに対応してウィンドウを閉じるには、<xref:System.Windows.Window.Close%2A> メソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="de889-224">To close a window in response to one of these custom mechanisms, you need to call the <xref:System.Windows.Window.Close%2A> method.</span></span> <span data-ttu-id="de889-225">**[ファイル]** メニューの **[終了]** をクリックすることでウィンドウを閉じる機能を実装する方法を、次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="de889-225">The following example implements the ability to close a window by choosing the **Exit** on the **File** menu.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#WindowWithFileExitMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml#windowwithfileexitmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml.cs#windowwithfileexitcodebehind)]
 [!code-vb[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/WindowWithFileExit.xaml.vb#windowwithfileexitcodebehind)]  
  
 <span data-ttu-id="de889-226">ウィンドウが閉じるとき、<xref:System.Windows.Window.Closing> と <xref:System.Windows.Window.Closed> の 2 つのイベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="de889-226">When a window closes, it raises two events: <xref:System.Windows.Window.Closing> and <xref:System.Windows.Window.Closed>.</span></span>  
  
 <span data-ttu-id="de889-227"><xref:System.Windows.Window.Closing> はウィンドウが閉じる前に発生し、ウィンドウが閉じるのを防ぐことができる機構を提供します。</span><span class="sxs-lookup"><span data-stu-id="de889-227"><xref:System.Windows.Window.Closing> is raised before the window closes, and it provides a mechanism by which window closure can be prevented.</span></span> <span data-ttu-id="de889-228">ウィンドウが閉じるのを防ぐのは、一般的に、ウィンドウ コンテンツに変更したデータが含まれている場合です。</span><span class="sxs-lookup"><span data-stu-id="de889-228">One common reason to prevent window closure is if window content contains modified data.</span></span> <span data-ttu-id="de889-229">この場合、<xref:System.Windows.Window.Closing> イベントを処理して、データが変更されているかどうかを確認できます。変更されている場合は、ユーザーにデータを保存しないでこのままウィンドウを閉じるか、またはウィンドウを閉じる操作を取り消すかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="de889-229">In this situation, the <xref:System.Windows.Window.Closing> event can be handled to determine whether data is dirty and, if so, to ask the user whether to either continue closing the window without saving the data or to cancel window closure.</span></span> <span data-ttu-id="de889-230"><xref:System.Windows.Window.Closing> を処理するときの要点を、次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="de889-230">The following example shows the key aspects of handling <xref:System.Windows.Window.Closing>.</span></span>  
  
 [!code-csharp[WindowClosingSnippets](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowClosingSnippets/CSharp/DataWindow.xaml.cs)]
 [!code-vb[WindowClosingSnippets](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowClosingSnippets/visualbasic/datawindow.xaml.vb)]  

 <span data-ttu-id="de889-231"><xref:System.Windows.Window.Closing> イベント ハンドラーに <xref:System.ComponentModel.CancelEventArgs> が渡されます。これにより、ウィンドウが閉じるのを防ぐために `true` に設定する `Boolean`<xref:System.ComponentModel.CancelEventArgs.Cancel%2A> プロパティが実装されます。</span><span class="sxs-lookup"><span data-stu-id="de889-231">The <xref:System.Windows.Window.Closing> event handler is passed a <xref:System.ComponentModel.CancelEventArgs>, which implements the `Boolean`<xref:System.ComponentModel.CancelEventArgs.Cancel%2A> property that you set to `true` to prevent a window from closing.</span></span>  
  
 <span data-ttu-id="de889-232"><xref:System.Windows.Window.Closing> が処理されない場合、または処理されたがキャンセルされていない場合、ウィンドウは閉じられます。</span><span class="sxs-lookup"><span data-stu-id="de889-232">If <xref:System.Windows.Window.Closing> is not handled, or it is handled but not canceled, the window will close.</span></span> <span data-ttu-id="de889-233">ウィンドウが実際に閉じられる直前に、<xref:System.Windows.Window.Closed> が発生します。</span><span class="sxs-lookup"><span data-stu-id="de889-233">Just before a window actually closes, <xref:System.Windows.Window.Closed> is raised.</span></span> <span data-ttu-id="de889-234">この時点で、ウィンドウが閉じるのを防ぐことはできません。</span><span class="sxs-lookup"><span data-stu-id="de889-234">At this point, a window cannot be prevented from closing.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="de889-235">メイン アプリケーション ウィンドウを閉じるか、最後のウィンドウを閉じるときに、アプリケーションが自動的にシャットダウンされるように構成することができます (「<xref:System.Windows.Application.MainWindow%2A>」を参照)。</span><span class="sxs-lookup"><span data-stu-id="de889-235">An application can be configured to shut down automatically when either the main application window closes (see <xref:System.Windows.Application.MainWindow%2A>) or the last window closes.</span></span> <span data-ttu-id="de889-236">詳細については、「<xref:System.Windows.Application.ShutdownMode%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de889-236">For details, see <xref:System.Windows.Application.ShutdownMode%2A>.</span></span>  
  
 <span data-ttu-id="de889-237">非クライアント領域およびクライアント領域に提供される機構によって、ウィンドウを明示的に閉じることができます。また、次のような場合に、アプリケーションまたは Windows の他の部分の動作の結果として、ウィンドウを暗黙的に閉じることもできます。</span><span class="sxs-lookup"><span data-stu-id="de889-237">While a window can be explicitly closed through mechanisms provided in the non-client and client areas, a window can also be implicitly closed as a result of behavior in other parts of the application or Windows, including the following:</span></span>  
  
- <span data-ttu-id="de889-238">ユーザーが Windows からログオフしたか、Windows をシャットダウンした場合。</span><span class="sxs-lookup"><span data-stu-id="de889-238">A user logs off or shuts down Windows.</span></span>  
  
- <span data-ttu-id="de889-239">ウィンドウのオーナーが閉じた場合 (「<xref:System.Windows.Window.Owner%2A>」を参照)。</span><span class="sxs-lookup"><span data-stu-id="de889-239">A window's owner closes (see <xref:System.Windows.Window.Owner%2A>).</span></span>  
  
- <span data-ttu-id="de889-240">メイン アプリケーション ウィンドウが閉じられ、<xref:System.Windows.Application.ShutdownMode%2A> が <xref:System.Windows.ShutdownMode.OnMainWindowClose> である場合。</span><span class="sxs-lookup"><span data-stu-id="de889-240">The main application window is closed and <xref:System.Windows.Application.ShutdownMode%2A> is <xref:System.Windows.ShutdownMode.OnMainWindowClose>.</span></span>  
  
- <span data-ttu-id="de889-241"><xref:System.Windows.Application.Shutdown%2A> が呼ばれたとき。</span><span class="sxs-lookup"><span data-stu-id="de889-241"><xref:System.Windows.Application.Shutdown%2A> is called.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="de889-242">ウィンドウを閉じると、再度開くことはできません。</span><span class="sxs-lookup"><span data-stu-id="de889-242">A window cannot be reopened after it is closed.</span></span>  
  
<a name="Window_Lifetime_Events"></a>
### <a name="window-lifetime-events"></a><span data-ttu-id="de889-243">ウィンドウの有効期間イベント</span><span class="sxs-lookup"><span data-stu-id="de889-243">Window Lifetime Events</span></span>  
 <span data-ttu-id="de889-244">次の図は、ウィンドウの有効期間内における主要なイベントのシーケンスを示しています。</span><span class="sxs-lookup"><span data-stu-id="de889-244">The following illustration shows the sequence of the principal events in the lifetime of a window:</span></span>  
  
 ![ウィンドウの有効期間内のイベントを示す図。](./media/wpf-windows-overview/window-lifetime-events.png)  
  
 <span data-ttu-id="de889-246">次の図は、アクティブ化しないで表示されるウィンドウの有効期間内における主要なイベントのシーケンスを示しています (ウィンドウが表示される前に <xref:System.Windows.Window.ShowActivated%2A> は `false` に設定されています)。</span><span class="sxs-lookup"><span data-stu-id="de889-246">The following illustration shows the sequence of the principal events in the lifetime of a window that is shown without activation (<xref:System.Windows.Window.ShowActivated%2A> is set to `false` before the window is shown):</span></span>  
  
 ![アクティブ化なしでのウィンドウの有効期間内のイベントを示す図。](./media/wpf-windows-overview/window-lifetime-no-activation.png)  
  
<a name="WindowLocation"></a>
## <a name="window-location"></a><span data-ttu-id="de889-248">ウィンドウの位置</span><span class="sxs-lookup"><span data-stu-id="de889-248">Window Location</span></span>  
 <span data-ttu-id="de889-249">ウィンドウが開いているとき、ウィンドウはデスクトップに対して相対的な x ディメンションと y ディメンションの位置にあります。</span><span class="sxs-lookup"><span data-stu-id="de889-249">While a window is open, it has a location in the x and y dimensions relative to the desktop.</span></span> <span data-ttu-id="de889-250">この位置は、<xref:System.Windows.Window.Left%2A> プロパティと <xref:System.Windows.Window.Top%2A> プロパティをそれぞれ検査することで確認できます。</span><span class="sxs-lookup"><span data-stu-id="de889-250">This location can be determined by inspecting the <xref:System.Windows.Window.Left%2A> and <xref:System.Windows.Window.Top%2A> properties, respectively.</span></span> <span data-ttu-id="de889-251">これらのプロパティを設定して、ウィンドウの位置を変更できます。</span><span class="sxs-lookup"><span data-stu-id="de889-251">You can set these properties to change the location of the window.</span></span>  
  
 <span data-ttu-id="de889-252"><xref:System.Windows.Window.WindowStartupLocation%2A> プロパティを次の <xref:System.Windows.WindowStartupLocation> 列挙値のいずれかに設定して、<xref:System.Windows.Window> が最初に表示されるときの初期位置を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="de889-252">You can also specify the initial location of a <xref:System.Windows.Window> when it first appears by setting the <xref:System.Windows.Window.WindowStartupLocation%2A> property with one of the following <xref:System.Windows.WindowStartupLocation> enumeration values:</span></span>  
  
- <span data-ttu-id="de889-253"><xref:System.Windows.WindowStartupLocation.CenterOwner> (既定値)</span><span class="sxs-lookup"><span data-stu-id="de889-253"><xref:System.Windows.WindowStartupLocation.CenterOwner> (default)</span></span>  
  
- <xref:System.Windows.WindowStartupLocation.CenterScreen>  
  
- <xref:System.Windows.WindowStartupLocation.Manual>  
  
 <span data-ttu-id="de889-254">開始位置が <xref:System.Windows.WindowStartupLocation.Manual> と指定され、<xref:System.Windows.Window.Left%2A> プロパティと <xref:System.Windows.Window.Top%2A> プロパティが設定されていない場合、<xref:System.Windows.Window> では、ウィンドウに表示位置が問い合わされます。</span><span class="sxs-lookup"><span data-stu-id="de889-254">If the startup location is specified as <xref:System.Windows.WindowStartupLocation.Manual>, and the <xref:System.Windows.Window.Left%2A> and <xref:System.Windows.Window.Top%2A> properties have not been set, <xref:System.Windows.Window> will ask Windows for a location to appear in.</span></span>  
  
<a name="Topmost_Windows_and_Z_Order"></a>
### <a name="topmost-windows-and-z-order"></a><span data-ttu-id="de889-255">最上位ウィンドウと Z オーダー</span><span class="sxs-lookup"><span data-stu-id="de889-255">Topmost Windows and Z-Order</span></span>  
 <span data-ttu-id="de889-256">ウィンドウには、x 位置と y 位置に加えて、他のウィンドウを基準にして垂直位置を決定する z ディメンションの位置もあります。</span><span class="sxs-lookup"><span data-stu-id="de889-256">Besides having an x and y location, a window also has a location in the z dimension, which determines its vertical position with respect to other windows.</span></span> <span data-ttu-id="de889-257">これはウィンドウの z オーダーともいい、標準 z オーダーと最上位 z オーダーの 2 種類があります。</span><span class="sxs-lookup"><span data-stu-id="de889-257">This is known as the window's z-order, and there are two types: normal z-order and topmost z-order.</span></span> <span data-ttu-id="de889-258">"*標準 z オーダー*" にあるウィンドウの位置は、そのウィンドウが現在アクティブかどうかによって決まります。</span><span class="sxs-lookup"><span data-stu-id="de889-258">The location of a window in the *normal z-order* is determined by whether it is currently active or not.</span></span> <span data-ttu-id="de889-259">既定では、ウィンドウは標準 z オーダーにあります。</span><span class="sxs-lookup"><span data-stu-id="de889-259">By default, a window is located in the normal z-order.</span></span> <span data-ttu-id="de889-260">"*最上位 z オーダー*" にあるウィンドウの位置も、そのウィンドウが現在アクティブかどうかによって決まります。</span><span class="sxs-lookup"><span data-stu-id="de889-260">The location of a window in the *topmost z-order* is also determined by whether it is currently active or not.</span></span> <span data-ttu-id="de889-261">また、最上位 z オーダーにあるウィンドウは、常に、標準 z オーダーにあるウィンドウの上に位置します。</span><span class="sxs-lookup"><span data-stu-id="de889-261">Furthermore, windows in the topmost z-order are always located above windows in the normal z-order.</span></span> <span data-ttu-id="de889-262">ウィンドウを最上位 z オーダーに配置するには、ウィンドウの <xref:System.Windows.Window.Topmost%2A> プロパティを `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="de889-262">A window is located in the topmost z-order by setting its <xref:System.Windows.Window.Topmost%2A> property to `true`.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#TopmostWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TopmostWindow.xaml#topmostwindowmarkup1)]  
  
 <span data-ttu-id="de889-263">各 z オーダー内では、現在アクティブなウィンドウは、同じ z オーダーにある他のすべてのウィンドウの上に表示されます。</span><span class="sxs-lookup"><span data-stu-id="de889-263">Within each z-order, the currently active window appears above all other windows in the same z-order.</span></span>  
  
<a name="WindowSize"></a>
## <a name="window-size"></a><span data-ttu-id="de889-264">ウィンドウ サイズ</span><span class="sxs-lookup"><span data-stu-id="de889-264">Window Size</span></span>  
 <span data-ttu-id="de889-265">ウィンドウには、デスクトップの位置に加えて、さまざまな幅と高さのプロパティや <xref:System.Windows.Window.SizeToContent%2A> など、複数のプロパティによって決定されるサイズがあります。</span><span class="sxs-lookup"><span data-stu-id="de889-265">Besides having a desktop location, a window has a size that is determined by several properties, including the various width and height properties and <xref:System.Windows.Window.SizeToContent%2A>.</span></span>  
  
 <span data-ttu-id="de889-266"><xref:System.Windows.FrameworkElement.MinWidth%2A>、<xref:System.Windows.FrameworkElement.Width%2A>、および <xref:System.Windows.FrameworkElement.MaxWidth%2A> を使用して、有効期間中にウィンドウに指定できる幅の範囲を管理します。これは、次の例に示すように構成します。</span><span class="sxs-lookup"><span data-stu-id="de889-266"><xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, and <xref:System.Windows.FrameworkElement.MaxWidth%2A> are used to manage the range of widths that a window can have during its lifetime, and are configured as shown in the following example.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#WidthWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WidthWindow.xaml#widthwindowmarkup1)]  
  
 <span data-ttu-id="de889-267">ウィンドウの高さは、<xref:System.Windows.FrameworkElement.MinHeight%2A>、<xref:System.Windows.FrameworkElement.Height%2A>、および <xref:System.Windows.FrameworkElement.MaxHeight%2A> によって管理します。これは、次の例に示すように構成します。</span><span class="sxs-lookup"><span data-stu-id="de889-267">Window height is managed by <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.Height%2A>, and <xref:System.Windows.FrameworkElement.MaxHeight%2A>, and are configured as shown in the following example.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#HeightWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/HeightWindow.xaml#heightwindowmarkup1)]  
  
 <span data-ttu-id="de889-268">さまざまな幅の値と高さの値はそれぞれ範囲を指定しているため、サイズを変更できるウィンドウの幅と高さは、それぞれの寸法に指定された範囲内のいずれかの値を取ります。</span><span class="sxs-lookup"><span data-stu-id="de889-268">Because the various width values and height values each specify a range, it is possible for the width and height of a resizable window to be anywhere within the specified range for the respective dimension.</span></span> <span data-ttu-id="de889-269">現在の幅と高さを検出するには、それぞれ <xref:System.Windows.FrameworkElement.ActualWidth%2A> と <xref:System.Windows.FrameworkElement.ActualHeight%2A> を検査します。</span><span class="sxs-lookup"><span data-stu-id="de889-269">To detect its current width and height, inspect <xref:System.Windows.FrameworkElement.ActualWidth%2A> and <xref:System.Windows.FrameworkElement.ActualHeight%2A>, respectively.</span></span>  
  
 <span data-ttu-id="de889-270">ウィンドウの幅と高さを、ウィンドウのコンテンツのサイズに合わせたサイズにする場合は、<xref:System.Windows.Window.SizeToContent%2A> プロパティを使用できます。これは、次の値を取ります。</span><span class="sxs-lookup"><span data-stu-id="de889-270">If you'd like the width and height of your window to have a size that fits to the size of the window's content, you can use the <xref:System.Windows.Window.SizeToContent%2A> property, which has the following values:</span></span>  
  
- <span data-ttu-id="de889-271"><xref:System.Windows.SizeToContent.Manual>。</span><span class="sxs-lookup"><span data-stu-id="de889-271"><xref:System.Windows.SizeToContent.Manual>.</span></span> <span data-ttu-id="de889-272">効果 (既定値)。</span><span class="sxs-lookup"><span data-stu-id="de889-272">No effect (default).</span></span>  
  
- <span data-ttu-id="de889-273"><xref:System.Windows.SizeToContent.Width>。</span><span class="sxs-lookup"><span data-stu-id="de889-273"><xref:System.Windows.SizeToContent.Width>.</span></span> <span data-ttu-id="de889-274">コンテンツの幅に合わせます。これは、<xref:System.Windows.FrameworkElement.MinWidth%2A> と <xref:System.Windows.FrameworkElement.MaxWidth%2A> の両方をコンテンツの幅に設定するのと同じ効果があります。</span><span class="sxs-lookup"><span data-stu-id="de889-274">Fit to content width, which has the same effect as setting both <xref:System.Windows.FrameworkElement.MinWidth%2A> and <xref:System.Windows.FrameworkElement.MaxWidth%2A> to the width of the content.</span></span>  
  
- <span data-ttu-id="de889-275"><xref:System.Windows.SizeToContent.Height>。</span><span class="sxs-lookup"><span data-stu-id="de889-275"><xref:System.Windows.SizeToContent.Height>.</span></span> <span data-ttu-id="de889-276">コンテンツの高さに合わせます。これは、<xref:System.Windows.FrameworkElement.MinHeight%2A> と <xref:System.Windows.FrameworkElement.MaxHeight%2A> の両方をコンテンツの高さに設定するのと同じ効果があります。</span><span class="sxs-lookup"><span data-stu-id="de889-276">Fit to content height, which has the same effect as setting both <xref:System.Windows.FrameworkElement.MinHeight%2A> and <xref:System.Windows.FrameworkElement.MaxHeight%2A> to the height of the content.</span></span>  
  
- <span data-ttu-id="de889-277"><xref:System.Windows.SizeToContent.WidthAndHeight>。</span><span class="sxs-lookup"><span data-stu-id="de889-277"><xref:System.Windows.SizeToContent.WidthAndHeight>.</span></span> <span data-ttu-id="de889-278">コンテンツの幅と高さに合わせます。これは、<xref:System.Windows.FrameworkElement.MinHeight%2A> と <xref:System.Windows.FrameworkElement.MaxHeight%2A> の両方をコンテンツの高さに設定し、<xref:System.Windows.FrameworkElement.MinWidth%2A> と <xref:System.Windows.FrameworkElement.MaxWidth%2A> の両方をコンテンツの幅に設定するのと同じ効果があります。</span><span class="sxs-lookup"><span data-stu-id="de889-278">Fit to content width and height, which has the same effect as setting both <xref:System.Windows.FrameworkElement.MinHeight%2A> and <xref:System.Windows.FrameworkElement.MaxHeight%2A> to the height of the content, and setting both <xref:System.Windows.FrameworkElement.MinWidth%2A> and <xref:System.Windows.FrameworkElement.MaxWidth%2A> to the width of the content.</span></span>  
  
 <span data-ttu-id="de889-279">次の例では、ウィンドウを最初に表示するときに、そのコンテンツに合わせて垂直方向と水平方向の両方のサイズを自動的に変更するウィンドウを示しています。</span><span class="sxs-lookup"><span data-stu-id="de889-279">The following example shows a window that automatically sizes to fit its content, both vertically and horizontally, when first shown.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#SizeToContentWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/SizeToContentWindow.xaml#sizetocontentwindowmarkup1)]  
  
 <span data-ttu-id="de889-280">次の例では、ウィンドウをそのコンテンツに合わせてサイズ変更する方法を指定するために、コード内に <xref:System.Windows.Window.SizeToContent%2A> プロパティを設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="de889-280">The following example shows how to set the <xref:System.Windows.Window.SizeToContent%2A> property in code to specify how a window resizes to fit its content    .</span></span>
  
 [!code-csharp[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#setwindowsizetocontentpropertycode)]
 [!code-vb[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#setwindowsizetocontentpropertycode)]  
  
<a name="OrderOfPrecedence"></a>
## <a name="order-of-precedence-for-sizing-properties"></a><span data-ttu-id="de889-281">サイズ変更プロパティの優先順位</span><span class="sxs-lookup"><span data-stu-id="de889-281">Order of Precedence for Sizing Properties</span></span>  
 <span data-ttu-id="de889-282">基本的に、ウィンドウのさまざまなサイズのプロパティを組み合わせて、サイズを変更できるウィンドウの幅と高さの範囲を定義します。</span><span class="sxs-lookup"><span data-stu-id="de889-282">Essentially, the various sizes properties of a window combine to define the range of width and height for a resizable window.</span></span> <span data-ttu-id="de889-283">有効な範囲が維持されていることを確認するために、<xref:System.Windows.Window> では次の優先順位でサイズ プロパティの値が評価されます。</span><span class="sxs-lookup"><span data-stu-id="de889-283">To ensure a valid range is maintained, <xref:System.Windows.Window> evaluates the values of the size properties using the following orders of precedence.</span></span>  
  
 <span data-ttu-id="de889-284">**高さのプロパティ:**</span><span class="sxs-lookup"><span data-stu-id="de889-284">**For Height Properties:**</span></span>  
  
1. <xref:System.Windows.FrameworkElement.MinHeight%2A?displayProperty=nameWithType>
  
2. <xref:System.Windows.FrameworkElement.MaxHeight%2A?displayProperty=nameWithType>
  
3. <xref:System.Windows.SizeToContent.Height?displayProperty=nameWithType>/<xref:System.Windows.SizeToContent.WidthAndHeight?displayProperty=nameWithType>
  
4. <xref:System.Windows.FrameworkElement.Height%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="de889-285">**幅のプロパティ:**</span><span class="sxs-lookup"><span data-stu-id="de889-285">**For Width Properties:**</span></span>  
  
1. <xref:System.Windows.FrameworkElement.MinWidth%2A?displayProperty=nameWithType>
  
2. <xref:System.Windows.FrameworkElement.MaxWidth%2A?displayProperty=nameWithType>
  
3. <xref:System.Windows.SizeToContent.Width?displayProperty=nameWithType>/<xref:System.Windows.SizeToContent.WidthAndHeight?displayProperty=nameWithType>
  
4. <xref:System.Windows.FrameworkElement.Width%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="de889-286">優先順位では、ウィンドウが最大化されたときのサイズも決定されます。これは、<xref:System.Windows.Window.WindowState%2A> プロパティで管理します。</span><span class="sxs-lookup"><span data-stu-id="de889-286">The order of precedence can also determine the size of a window when it is maximized, which is managed with the <xref:System.Windows.Window.WindowState%2A> property.</span></span>  
  
<a name="WindowState"></a>
## <a name="window-state"></a><span data-ttu-id="de889-287">ウィンドウの状態</span><span class="sxs-lookup"><span data-stu-id="de889-287">Window State</span></span>  
 <span data-ttu-id="de889-288">サイズを変更できるウィンドウには、有効期間中、通常、最小化、最大化の 3 つの状態があります。</span><span class="sxs-lookup"><span data-stu-id="de889-288">During the lifetime of a resizable window, it can have three states: normal, minimized, and maximized.</span></span> <span data-ttu-id="de889-289">"*通常*" の状態のウィンドウは、ウィンドウの既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="de889-289">A window with a *normal* state is the default state of a window.</span></span> <span data-ttu-id="de889-290">この状態のウィンドウは、サイズ変更グリップ、またはサイズ変更可能な場合は境界線を使用して、ユーザーが移動したりサイズ変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="de889-290">A window with this state allows a user to move and resize it by using a resize grip or the border, if it is resizable.</span></span>  
  
 <span data-ttu-id="de889-291">"*最小化*" された状態のウィンドウは、<xref:System.Windows.Window.ShowInTaskbar%2A> が `true` に設定されている場合は、折りたたまれてタスク バー ボタンになります。それ以外の場合は、折りたたまれて、可能な最小のサイズになり、デスクトップの左下隅に自動的に再配置されます。</span><span class="sxs-lookup"><span data-stu-id="de889-291">A window with a *minimized* state collapses to its task bar button if <xref:System.Windows.Window.ShowInTaskbar%2A> is set to `true`; otherwise, it collapses to the smallest possible size it can be and relocates itself to the bottom-left corner of the desktop.</span></span> <span data-ttu-id="de889-292">最小化されたウィンドウはいずれの種類も、境界線またはサイズ変更グリップを使用してサイズ変更できません。ただし、タスク バーに表示されていない最小化されたウィンドウはデスクトップの任意の場所にドラッグできます。</span><span class="sxs-lookup"><span data-stu-id="de889-292">Neither type of minimized window can be resized using a border or resize grip, although a minimized window that isn't shown in the task bar can be dragged around the desktop.</span></span>  
  
 <span data-ttu-id="de889-293">"*最大化*" された状態のウィンドウは、拡大されて、可能な最大のサイズになります。これは、<xref:System.Windows.FrameworkElement.MaxWidth%2A> プロパティ、<xref:System.Windows.FrameworkElement.MaxHeight%2A> プロパティ、および <xref:System.Windows.Window.SizeToContent%2A> プロパティが指定するのと同じサイズです。</span><span class="sxs-lookup"><span data-stu-id="de889-293">A window with a *maximized* state expands to the maximum size it can be, which will only be as large as its <xref:System.Windows.FrameworkElement.MaxWidth%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, and <xref:System.Windows.Window.SizeToContent%2A> properties dictate.</span></span> <span data-ttu-id="de889-294">最小化されたウィンドウと同様、最大化されたウィンドウは、サイズ変更グリップを使用したり、境界線をドラッグしたりすることによってサイズ変更できません。</span><span class="sxs-lookup"><span data-stu-id="de889-294">Like a minimized window, a maximized window cannot be resized by using a resize grip or by dragging the border.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="de889-295">ウィンドウが現在最大化または最小化されている場合でも、ウィンドウの <xref:System.Windows.Window.Top%2A>、<xref:System.Windows.Window.Left%2A>、<xref:System.Windows.FrameworkElement.Width%2A>、および <xref:System.Windows.FrameworkElement.Height%2A> の各プロパティの値は、通常の状態の値を常に表します。</span><span class="sxs-lookup"><span data-stu-id="de889-295">The values of the <xref:System.Windows.Window.Top%2A>, <xref:System.Windows.Window.Left%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, and <xref:System.Windows.FrameworkElement.Height%2A> properties of a window always represent the values for the normal state, even when the window is currently maximized or minimized.</span></span>  
  
 <span data-ttu-id="de889-296">ウィンドウの状態は、<xref:System.Windows.Window.WindowState%2A> プロパティを設定することによって構成できます。これは、次の <xref:System.Windows.WindowState> 列挙値のいずれかを取ります。</span><span class="sxs-lookup"><span data-stu-id="de889-296">The state of a window can be configured by setting its <xref:System.Windows.Window.WindowState%2A> property, which can have one of the following <xref:System.Windows.WindowState> enumeration values:</span></span>  
  
- <span data-ttu-id="de889-297"><xref:System.Windows.WindowState.Normal> (既定値)</span><span class="sxs-lookup"><span data-stu-id="de889-297"><xref:System.Windows.WindowState.Normal> (default)</span></span>  
  
- <xref:System.Windows.WindowState.Maximized>  
  
- <xref:System.Windows.WindowState.Minimized>  
  
 <span data-ttu-id="de889-298">開くときに最大化されて表示されるウィンドウを作成する方法を、次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="de889-298">The following example shows how to create a window that is shown as maximized when it opens.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#WindowStateWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStateWindow.xaml#windowstatewindowmarkup1)]  
  
 <span data-ttu-id="de889-299">通常は、<xref:System.Windows.Window.WindowState%2A> を設定してウィンドウの初期状態を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de889-299">In general, you should set <xref:System.Windows.Window.WindowState%2A> to configure the initial state of a window.</span></span> <span data-ttu-id="de889-300">サイズ変更可能なウィンドウが表示されると、ユーザーはウィンドウのタイトル バーにある最小化ボタン、最大化ボタン、および元に戻すボタンを使用して、ウィンドウの状態を変更できます。</span><span class="sxs-lookup"><span data-stu-id="de889-300">Once a resizable window is shown, users can press the minimize, maximize, and restore buttons on the window's title bar to change the window state.</span></span>  
  
<a name="WindowAppearance"></a>
## <a name="window-appearance"></a><span data-ttu-id="de889-301">ウィンドウの外観</span><span class="sxs-lookup"><span data-stu-id="de889-301">Window Appearance</span></span>  
 <span data-ttu-id="de889-302">ウィンドウのクライアント領域の外観を変更するために、ボタン、ラベル、テキスト ボックスなど、ウィンドウ固有のコンテンツを追加します。</span><span class="sxs-lookup"><span data-stu-id="de889-302">You change the appearance of the client area of a window by adding window-specific content to it, such as buttons, labels, and text boxes.</span></span> <span data-ttu-id="de889-303">非クライアント領域を構成するために、<xref:System.Windows.Window> には、ウィンドウのアイコンを設定する <xref:System.Windows.Window.Icon%2A>、タイトルを設定する <xref:System.Windows.Window.Title%2A> など、いくつかのプロパティが用意されています。</span><span class="sxs-lookup"><span data-stu-id="de889-303">To configure the non-client area, <xref:System.Windows.Window> provides several properties, which include <xref:System.Windows.Window.Icon%2A> to set a window's icon and <xref:System.Windows.Window.Title%2A> to set its title.</span></span>  
  
 <span data-ttu-id="de889-304">また、ウィンドウのサイズ変更モード、ウィンドウ スタイル、デスクトップのタスク バーにボタンとして表示するかどうかを構成して、非クライアント領域の境界線の外観と動作も変更できます。</span><span class="sxs-lookup"><span data-stu-id="de889-304">You can also change the appearance and behavior of non-client area border by configuring a window's resize mode, window style, and whether it appears as a button in the desktop task bar.</span></span>  

<a name="Resize_Mode"></a>
### <a name="resize-mode"></a><span data-ttu-id="de889-305">サイズ変更モード</span><span class="sxs-lookup"><span data-stu-id="de889-305">Resize Mode</span></span>  
 <span data-ttu-id="de889-306"><xref:System.Windows.Window.WindowStyle%2A> プロパティに応じて、ユーザーがどのようにウィンドウのサイズを変更するか、またはウィンドウのサイズを変更できるかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="de889-306">Depending on the <xref:System.Windows.Window.WindowStyle%2A> property, you can control how (and if) users can resize the window.</span></span> <span data-ttu-id="de889-307">ウィンドウ スタイルの選択は、ユーザーがマウスで境界線をドラッグすることによってウィンドウのサイズを変更できるかどうか、 **[最小化]** ボタン、 **[最大化]** ボタン、および **[サイズ変更]** ボタンが非クライアント領域に表示されるかどうか、表示される場合にボタンが有効かどうかに影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="de889-307">The choice of window style affects whether a user can resize the window by dragging its border with the mouse, whether the **Minimize**, **Maximize**, and **Resize** buttons appear on the non-client area, and, if they do appear, whether they are enabled.</span></span>  
  
 <span data-ttu-id="de889-308">ウィンドウのサイズ変更方法は、<xref:System.Windows.Window.ResizeMode%2A> プロパティを設定することによって構成できます。これは、次の <xref:System.Windows.ResizeMode> 列挙値のいずれかを取ります。</span><span class="sxs-lookup"><span data-stu-id="de889-308">You can configure how a window resizes by setting its <xref:System.Windows.Window.ResizeMode%2A> property, which can be one of the following <xref:System.Windows.ResizeMode> enumeration values:</span></span>  
  
- <xref:System.Windows.ResizeMode.NoResize>  
  
- <xref:System.Windows.ResizeMode.CanMinimize>  
  
- <span data-ttu-id="de889-309"><xref:System.Windows.ResizeMode.CanResize> (既定値)</span><span class="sxs-lookup"><span data-stu-id="de889-309"><xref:System.Windows.ResizeMode.CanResize> (default)</span></span>  
  
- <xref:System.Windows.ResizeMode.CanResizeWithGrip>  
  
 <span data-ttu-id="de889-310">[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] と同様に、ウィンドウのサイズ変更モードは、有効期間中に変更される可能性はほとんどありません。したがって、多くの場合は <xref:System.Windows.Window.WindowStyle%2A> マークアップから設定します。</span><span class="sxs-lookup"><span data-stu-id="de889-310">As with <xref:System.Windows.Window.WindowStyle%2A>, the resize mode of a window is unlikely to change during its lifetime, which means that you'll most likely set it from [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] markup.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#ResizeModeWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ResizeModeWindow.xaml#resizemodewindowmarkup1)]  
  
 <span data-ttu-id="de889-311"><xref:System.Windows.Window.WindowState%2A> プロパティを検査することによって、ウィンドウが最大化されているか、最小化されているか、元のサイズに戻されているかを検出できることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="de889-311">Note that you can detect whether a window is maximized, minimized, or restored by inspecting the <xref:System.Windows.Window.WindowState%2A> property.</span></span>  
  
<a name="Window_Style"></a>
### <a name="window-style"></a><span data-ttu-id="de889-312">ウィンドウ スタイル</span><span class="sxs-lookup"><span data-stu-id="de889-312">Window Style</span></span>  
 <span data-ttu-id="de889-313">ウィンドウの非クライアント領域から公開される境界線は、多くのアプリケーションに適しています。</span><span class="sxs-lookup"><span data-stu-id="de889-313">The border that is exposed from the non-client area of a window is suitable for most applications.</span></span> <span data-ttu-id="de889-314">ただし、ウィンドウの種類によって、異なる種類の境界線が必要な状況や、境界線がまったく必要ない状況があります。</span><span class="sxs-lookup"><span data-stu-id="de889-314">However, there are circumstances where different types of borders are needed, or no borders are needed at all, depending on the type of window.</span></span>  
  
 <span data-ttu-id="de889-315">ウィンドウの境界線の種類を制御するには、<xref:System.Windows.Window.WindowStyle%2A> プロパティを次の <xref:System.Windows.WindowStyle> 列挙値のいずれかに設定します。</span><span class="sxs-lookup"><span data-stu-id="de889-315">To control what type of border a window gets, you set its <xref:System.Windows.Window.WindowStyle%2A> property with one of the following values of the <xref:System.Windows.WindowStyle> enumeration:</span></span>  
  
- <xref:System.Windows.WindowStyle.None>  
  
- <span data-ttu-id="de889-316"><xref:System.Windows.WindowStyle.SingleBorderWindow> (既定値)</span><span class="sxs-lookup"><span data-stu-id="de889-316"><xref:System.Windows.WindowStyle.SingleBorderWindow> (default)</span></span>  
  
- <xref:System.Windows.WindowStyle.ThreeDBorderWindow>  
  
- <xref:System.Windows.WindowStyle.ToolWindow>  
  
 <span data-ttu-id="de889-317">これらのウィンドウ スタイルの効果については、次の図で説明します。</span><span class="sxs-lookup"><span data-stu-id="de889-317">The effect of these window styles are illustrated in the following figure:</span></span>  
  
 ![ウィンドウの境界線スタイルの図。](./media/wpf-windows-overview/window-border-styles.png)  
  
 <span data-ttu-id="de889-319">[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] マークアップまたはコードのいずれかを使用して <xref:System.Windows.Window.WindowStyle%2A> を設定できます。ウィンドウの有効期間中に変更される可能性はほとんどないため、多くの場合は [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] マークアップを使用して構成します。</span><span class="sxs-lookup"><span data-stu-id="de889-319">You can set <xref:System.Windows.Window.WindowStyle%2A> using either [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] markup or code; because it is unlikely to change during the lifetime of a window, you will most likely configure it using [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] markup.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#WindowStyleWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStyleWindow.xaml#windowstylewindowmarkup1)]  
  
#### <a name="non-rectangular-window-style"></a><span data-ttu-id="de889-320">四角形以外のウィンドウ スタイル</span><span class="sxs-lookup"><span data-stu-id="de889-320">Non-Rectangular Window Style</span></span>  
 <span data-ttu-id="de889-321"><xref:System.Windows.Window.WindowStyle%2A> で使用できる境界線のスタイルでは十分ではない状況もあります。</span><span class="sxs-lookup"><span data-stu-id="de889-321">There are also situations where the border styles that <xref:System.Windows.Window.WindowStyle%2A> allows you to have are not sufficient.</span></span> <span data-ttu-id="de889-322">たとえば、Microsoft Windows Media Player で使用されるような、四角形以外の境界線を持つアプリケーションを作成する場合があります。</span><span class="sxs-lookup"><span data-stu-id="de889-322">For example, you may want to create an application with a non-rectangular border, like Microsoft Windows Media Player uses.</span></span>  
  
 <span data-ttu-id="de889-323">たとえば、次の図に示す吹き出しウィンドウを想定します。</span><span class="sxs-lookup"><span data-stu-id="de889-323">For example, consider the speech bubble window shown in the following figure:</span></span>  
  
 !["ここをドラッグしてください" という吹き出しウィンドウ。](./media/wpf-windows-overview/non-rectangular-window-figure.png)  
  
 <span data-ttu-id="de889-325">この種類のウィンドウは、<xref:System.Windows.Window.WindowStyle%2A> プロパティを <xref:System.Windows.WindowStyle.None> に設定し、<xref:System.Windows.Window> が透明度に対して持つ特殊なサポートを使用することによって作成できます。</span><span class="sxs-lookup"><span data-stu-id="de889-325">This type of window can be created by setting the <xref:System.Windows.Window.WindowStyle%2A> property to <xref:System.Windows.WindowStyle.None>, and by using special support that <xref:System.Windows.Window> has for transparency.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#TransparentWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TransparentWindow.xaml#transparentwindowmarkup1)]  
  
 <span data-ttu-id="de889-326">値をこの組み合わせで使用し、ウィンドウが完全に透明にレンダリングされるように設定します。</span><span class="sxs-lookup"><span data-stu-id="de889-326">This combination of values instructs the window to render completely transparent.</span></span> <span data-ttu-id="de889-327">この状態では、ウィンドウの非クライアント領域の表示要素 (閉じるメニュー、最小化ボタン、最大化ボタン、元に戻すボタンなど) は使用できません。</span><span class="sxs-lookup"><span data-stu-id="de889-327">In this state, the window's non-client area adornments (the Close menu, Minimize, Maximize, and Restore buttons, and so on) cannot be used.</span></span> <span data-ttu-id="de889-328">したがって、独自の表示要素を用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de889-328">Consequently, you need to provide your own.</span></span>  
  
<a name="Task_Bar_Presence"></a>
### <a name="task-bar-presence"></a><span data-ttu-id="de889-329">タスク バーのプレゼンス</span><span class="sxs-lookup"><span data-stu-id="de889-329">Task Bar Presence</span></span>  

<span data-ttu-id="de889-330">ウィンドウの既定の外観には、次の図に示すような、タスク バー ボタンも含まれます。</span><span class="sxs-lookup"><span data-stu-id="de889-330">The default appearance of a window includes a taskbar button, like the one shown in the following figure:</span></span>

 ![タスク バー ボタンのあるウィンドウを示すスクリーンショット。](./media/wpf-windows-overview/window-taskbar-button.png)  
  
 <span data-ttu-id="de889-332">メッセージ ボックスやダイアログ ボックスなど、ウィンドウの種類によっては、タスク バー ボタンがありません (「[ダイアログ ボックスの概要](dialog-boxes-overview.md)」を参照)。</span><span class="sxs-lookup"><span data-stu-id="de889-332">Some types of windows don't have a task bar button, such as message boxes and dialog boxes (see [Dialog Boxes Overview](dialog-boxes-overview.md)).</span></span> <span data-ttu-id="de889-333">ウィンドウのタスク バー ボタンを表示するかどうかは、<xref:System.Windows.Window.ShowInTaskbar%2A> プロパティを設定することによって制御できます (既定値は `true`)。</span><span class="sxs-lookup"><span data-stu-id="de889-333">You can control whether the task bar button for a window is shown by setting the <xref:System.Windows.Window.ShowInTaskbar%2A> property (`true` by default).</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#ShowInTaskbarWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ShowInTaskbarWindow.xaml#showintaskbarwindowmarkup1)]  
  
<a name="SecurityConsiderations"></a>
## <a name="security-considerations"></a><span data-ttu-id="de889-334">セキュリティの考慮事項</span><span class="sxs-lookup"><span data-stu-id="de889-334">Security Considerations</span></span>  
 <span data-ttu-id="de889-335"><xref:System.Windows.Window> をインスタンス化するには、`UnmanagedCode` セキュリティ アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="de889-335"><xref:System.Windows.Window> requires `UnmanagedCode` security permission to be instantiated.</span></span> <span data-ttu-id="de889-336">ローカル コンピューターにインストールされ、ローカル コンピューターから起動されるアプリケーションの場合は、アプリケーションに付与されるアクセス許可セットの範囲内になります。</span><span class="sxs-lookup"><span data-stu-id="de889-336">For applications installed on and launched from the local machine, this falls within the set of permissions that are granted to the application.</span></span>  
  
 <span data-ttu-id="de889-337">ただし、これは、ClickOnce を使用して、インターネット ゾーンまたはローカル イントラネット ゾーンから起動されるアプリケーションに付与されるアクセス許可セットの範囲外になります。</span><span class="sxs-lookup"><span data-stu-id="de889-337">However, this falls outside the set of permissions granted to applications that are launched from the Internet or Local intranet zone using ClickOnce.</span></span> <span data-ttu-id="de889-338">そのため、ユーザーは ClickOnce セキュリティ警告を受け取り、アプリケーションのアクセス許可セットを完全信頼に昇格させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="de889-338">Consequently, users will receive a ClickOnce security warning and will need to elevate the permission set for the application to full trust.</span></span>  
  
 <span data-ttu-id="de889-339">さらに、XBAP では、既定でウィンドウまたはダイアログ ボックスを表示できません。</span><span class="sxs-lookup"><span data-stu-id="de889-339">Additionally, XBAPs cannot show windows or dialog boxes by default.</span></span> <span data-ttu-id="de889-340">スタンドアロン アプリケーションのセキュリティに関する考慮事項については、「[WPF のセキュリティ方針 - プラットフォーム セキュリティ](../wpf-security-strategy-platform-security.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de889-340">For a discussion on standalone application security considerations, see [WPF Security Strategy - Platform Security](../wpf-security-strategy-platform-security.md).</span></span>  
  
<a name="Other_Types_of_Windows"></a>
## <a name="other-types-of-windows"></a><span data-ttu-id="de889-341">その他の種類のウィンドウ</span><span class="sxs-lookup"><span data-stu-id="de889-341">Other Types of Windows</span></span>  
 <span data-ttu-id="de889-342"><xref:System.Windows.Navigation.NavigationWindow> は、ナビゲーション可能なコンテンツをホストするように設計されたウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="de889-342"><xref:System.Windows.Navigation.NavigationWindow> is a window that is designed to host navigable content.</span></span> <span data-ttu-id="de889-343">詳しくは、「[ナビゲーションの概要](navigation-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="de889-343">For more information, see [Navigation Overview](navigation-overview.md)).</span></span>  
  
 <span data-ttu-id="de889-344">ダイアログ ボックスは、ユーザーから情報を収集して機能を完了するためによく使用されるウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="de889-344">Dialog boxes are windows that are often used to gather information from a user to complete a function.</span></span> <span data-ttu-id="de889-345">たとえば、ユーザーがファイルを開く場合は、通常、ユーザーからファイル名を取得するために、アプリケーションによって **[ファイルを開く]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="de889-345">For example, when a user wants to open a file, the **Open File** dialog box is usually displayed by an application to get the file name from the user.</span></span> <span data-ttu-id="de889-346">詳細については、「[ダイアログ ボックスの概要](dialog-boxes-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de889-346">For more information, see [Dialog Boxes Overview](dialog-boxes-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de889-347">関連項目</span><span class="sxs-lookup"><span data-stu-id="de889-347">See also</span></span>

- <xref:System.Windows.Window>
- <xref:System.Windows.MessageBox>
- <xref:System.Windows.Navigation.NavigationWindow>
- <xref:System.Windows.Application>
- [<span data-ttu-id="de889-348">ダイアログ ボックスの概要</span><span class="sxs-lookup"><span data-stu-id="de889-348">Dialog Boxes Overview</span></span>](dialog-boxes-overview.md)
- [<span data-ttu-id="de889-349">WPF アプリケーションのビルド</span><span class="sxs-lookup"><span data-stu-id="de889-349">Building a WPF Application</span></span>](building-a-wpf-application-wpf.md)
