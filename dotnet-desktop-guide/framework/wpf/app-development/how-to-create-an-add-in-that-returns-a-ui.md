---
title: '方法: UI を返すアドインを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating an add-in that returns a UI [WPF]
- implementing add-in pipeline segments [WPF]
- add-in [WPF], returns a UI
ms.assetid: 57f274b7-4c66-4b72-92eb-81939a393776
ms.openlocfilehash: 8e26a77fcf0d265444316ee374d835791a10749e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985500"
---
# <a name="how-to-create-an-add-in-that-returns-a-ui"></a><span data-ttu-id="d48c0-102">方法: UI を返すアドインを作成する</span><span class="sxs-lookup"><span data-stu-id="d48c0-102">How to: Create an Add-In That Returns a UI</span></span>

<span data-ttu-id="d48c0-103">この例では、ホスト WPF スタンドアロン アプリケーションに Windows Presentation Foundation (WPF) を返すアドインの作成方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d48c0-103">This example shows how to create an add-in that returns a Windows Presentation Foundation (WPF) to a host WPF standalone application.</span></span>  
  
 <span data-ttu-id="d48c0-104">このアドインは、WPF ユーザー コントロールである UI を返します。</span><span class="sxs-lookup"><span data-stu-id="d48c0-104">The add-in returns a UI that is a WPF user control.</span></span> <span data-ttu-id="d48c0-105">ユーザー コントロールの中身は 1 つのボタンであり、クリックすると、メッセージ ボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="d48c0-105">The content of the user control is a single button that, when clicked, displays a message box.</span></span> <span data-ttu-id="d48c0-106">WPF スタンドアロン アプリケーションは、アドインをホストし、(アドインによって返された) ユーザー コントロールをメイン アプリケーション ウィンドウのコンテンツとして表示します。</span><span class="sxs-lookup"><span data-stu-id="d48c0-106">The WPF standalone application hosts the add-in and displays the user control (returned by the add-in) as the content of the main application window.</span></span>  
  
 <span data-ttu-id="d48c0-107">**必須コンポーネント**</span><span class="sxs-lookup"><span data-stu-id="d48c0-107">**Prerequisites**</span></span>  
  
 <span data-ttu-id="d48c0-108">この例では、このシナリオを実現する .NET Framework アドイン モデルの WPF 拡張機能に焦点を当てます。前提条件は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d48c0-108">This example highlights the WPF extensions to the .NET Framework add-in model that enable this scenario, and assumes the following:</span></span>  
  
- <span data-ttu-id="d48c0-109">パイプライン、アドイン、ホスト環境など、.NET Framework アドイン モデルの知識。</span><span class="sxs-lookup"><span data-stu-id="d48c0-109">Knowledge of the .NET Framework add-in model, including pipeline, add-in, and host development.</span></span> <span data-ttu-id="d48c0-110">これらの概念については、「[アドインおよび拡張機能](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d48c0-110">If you are unfamiliar with these concepts, see [Add-ins and Extensibility](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)).</span></span> <span data-ttu-id="d48c0-111">パイプライン、アドイン、およびホスト アプリケーションの実装例を示すチュートリアルについては、「[チュートリアル: 拡張性のあるアプリケーションの作成](/previous-versions/dotnet/netframework-4.0/bb788290(v%3dvs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d48c0-111">For a tutorial that demonstrates the implementation of a pipeline, an add-in, and a host application, see [Walkthrough: Creating an Extensible Application](/previous-versions/dotnet/netframework-4.0/bb788290(v%3dvs.100)).</span></span>  
  
- <span data-ttu-id="d48c0-112">.NET Framework アドイン モデルの WPF 拡張機能については、「[WPF アドインの概要](wpf-add-ins-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d48c0-112">Knowledge of the WPF extensions to the .NET Framework add-in model, which can be found here: [WPF Add-Ins Overview](wpf-add-ins-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d48c0-113">例</span><span class="sxs-lookup"><span data-stu-id="d48c0-113">Example</span></span>  

 <span data-ttu-id="d48c0-114">WPF UI を返すアドインを作成するには、各パイプライン セグメント、アドイン、およびホスト アプリケーションに特定のコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="d48c0-114">To create an add-in that returns a WPF UI requires specific code for each pipeline segment, the add-in, and the host application.</span></span>  

<a name="Contract"></a>

## <a name="implementing-the-contract-pipeline-segment"></a><span data-ttu-id="d48c0-115">コントラクト パイプライン セグメントの実装</span><span class="sxs-lookup"><span data-stu-id="d48c0-115">Implementing the Contract Pipeline Segment</span></span>  

 <span data-ttu-id="d48c0-116">メソッドは、UI を返すようにコントラクトによって定義する必要があり、その戻り値は <xref:System.AddIn.Contract.INativeHandleContract> 型でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="d48c0-116">A method must be defined by the contract for returning a UI, and its return value must be of type <xref:System.AddIn.Contract.INativeHandleContract>.</span></span> <span data-ttu-id="d48c0-117">これは、次のコードの `IWPFAddInContract` コントラクトの `GetAddInUI` メソッドによって示されています。</span><span class="sxs-lookup"><span data-stu-id="d48c0-117">This is demonstrated by the `GetAddInUI` method of the `IWPFAddInContract` contract in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
 [!code-vb[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]  
  
<a name="AddInView"></a>

## <a name="implementing-the-add-in-view-pipeline-segment"></a><span data-ttu-id="d48c0-118">アドイン ビュー パイプライン セグメントの実装</span><span class="sxs-lookup"><span data-stu-id="d48c0-118">Implementing the Add-In View Pipeline Segment</span></span>  

 <span data-ttu-id="d48c0-119">アドインでは UI が実装されていて、それが <xref:System.Windows.FrameworkElement> のサブクラスとして提供されるため、`IWPFAddInView.GetAddInUI` に関連するアドイン ビューのメソッドは、<xref:System.Windows.FrameworkElement> 型の値を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="d48c0-119">Because the add-in implements the UIs it provides as subclasses of <xref:System.Windows.FrameworkElement>, the method on the add-in view that correlates to `IWPFAddInView.GetAddInUI` must return a value of type <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="d48c0-120">次のコードは、コントラクトのアドイン ビューがインターフェイスとして実装されることを示しています。</span><span class="sxs-lookup"><span data-stu-id="d48c0-120">The following code shows the add-in view of the contract, implemented as an interface.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInViews/IWPFAddInView.cs#addinviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInViews/IWPFAddInView.vb#addinviewcode)]  
  
<a name="AddInSideAdapter"></a>

## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a><span data-ttu-id="d48c0-121">アドイン側アダプター パイプライン セグメントの実装</span><span class="sxs-lookup"><span data-stu-id="d48c0-121">Implementing the Add-In-Side Adapter Pipeline Segment</span></span>  

 <span data-ttu-id="d48c0-122">コントラクト メソッドでは <xref:System.AddIn.Contract.INativeHandleContract> が返されますが、アドインでは <xref:System.Windows.FrameworkElement> が返されます (アドイン ビューによって指定されたように)。</span><span class="sxs-lookup"><span data-stu-id="d48c0-122">The contract method returns an <xref:System.AddIn.Contract.INativeHandleContract>, but the add-in returns a <xref:System.Windows.FrameworkElement> (as specified by the add-in view).</span></span> <span data-ttu-id="d48c0-123">したがって、<xref:System.Windows.FrameworkElement> は、分離境界を越える前に <xref:System.AddIn.Contract.INativeHandleContract> に変換される必要があります。</span><span class="sxs-lookup"><span data-stu-id="d48c0-123">Consequently, the <xref:System.Windows.FrameworkElement> must be converted to an <xref:System.AddIn.Contract.INativeHandleContract> before crossing the isolation boundary.</span></span> <span data-ttu-id="d48c0-124">この作業は、次のコードで示されているように、アドイン側のアダプターで <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> を呼び出すことによって行われます。</span><span class="sxs-lookup"><span data-stu-id="d48c0-124">This work is performed by the add-in-side adapter by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, as shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]  
  
<a name="HostView"></a>

## <a name="implementing-the-host-view-pipeline-segment"></a><span data-ttu-id="d48c0-125">ホスト ビュー パイプライン セグメントの実装</span><span class="sxs-lookup"><span data-stu-id="d48c0-125">Implementing the Host View Pipeline Segment</span></span>  

 <span data-ttu-id="d48c0-126">ホスト アプリケーションでは <xref:System.Windows.FrameworkElement> が表示されるため、`IWPFAddInHostView.GetAddInUI` に関連するホスト ビューのメソッドでは、<xref:System.Windows.FrameworkElement> 型の値を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="d48c0-126">Because the host application will display a <xref:System.Windows.FrameworkElement>, the method on the host view that correlates to `IWPFAddInHostView.GetAddInUI` must return a value of type <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="d48c0-127">次のコードは、コントラクトのホスト ビューがインターフェイスとして実装されることを示しています。</span><span class="sxs-lookup"><span data-stu-id="d48c0-127">The following code shows the host view of the contract, implemented as an interface.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostViews/IWPFAddInHostView.cs#hostviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostViews/IWPFAddInHostView.vb#hostviewcode)]  
  
<a name="HostSideAdapter"></a>

## <a name="implementing-the-host-side-adapter-pipeline-segment"></a><span data-ttu-id="d48c0-128">ホスト側アダプター パイプライン セグメントの実装</span><span class="sxs-lookup"><span data-stu-id="d48c0-128">Implementing the Host-Side Adapter Pipeline Segment</span></span>  

 <span data-ttu-id="d48c0-129">コントラクト メソッドでは <xref:System.AddIn.Contract.INativeHandleContract> が返されますが、ホスト アプリケーションでは <xref:System.Windows.FrameworkElement> が必要です (ホスト ビューによって指定されたように)。</span><span class="sxs-lookup"><span data-stu-id="d48c0-129">The contract method returns an <xref:System.AddIn.Contract.INativeHandleContract>, but the host application expects a <xref:System.Windows.FrameworkElement> (as specified by the host view).</span></span> <span data-ttu-id="d48c0-130">したがって、<xref:System.AddIn.Contract.INativeHandleContract> は、分離境界を越えた後で、<xref:System.Windows.FrameworkElement> に変換される必要があります。</span><span class="sxs-lookup"><span data-stu-id="d48c0-130">Consequently, the <xref:System.AddIn.Contract.INativeHandleContract> must be converted to a <xref:System.Windows.FrameworkElement> after crossing the isolation boundary.</span></span> <span data-ttu-id="d48c0-131">この作業は、次のコードで示されているように、ホスト側のアダプターで <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> を呼び出すことによって行われます。</span><span class="sxs-lookup"><span data-stu-id="d48c0-131">This work is performed by the host-side adapter by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>, as shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#hostsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#hostsideadaptercode)]  
  
<a name="AddIn"></a>

## <a name="implementing-the-add-in"></a><span data-ttu-id="d48c0-132">アドインの実装</span><span class="sxs-lookup"><span data-stu-id="d48c0-132">Implementing the Add-In</span></span>  

 <span data-ttu-id="d48c0-133">アドイン側アダプターとアドイン ビューが作成されたら、アドイン (`WPFAddIn1.AddIn`) では、<xref:System.Windows.FrameworkElement> オブジェクト (この例では、<xref:System.Windows.Controls.UserControl>) を返すために `IWPFAddInView.GetAddInUI` メソッドを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d48c0-133">With the add-in-side adapter and add-in view created, the add-in (`WPFAddIn1.AddIn`) must implement the `IWPFAddInView.GetAddInUI` method to return a <xref:System.Windows.FrameworkElement> object (a <xref:System.Windows.Controls.UserControl> in this example).</span></span> <span data-ttu-id="d48c0-134"><xref:System.Windows.Controls.UserControl> (`AddInUI`) の実装を次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="d48c0-134">The implementation of the <xref:System.Windows.Controls.UserControl>, `AddInUI`, is shown by the following code.</span></span>  
  
 [!code-xaml[SimpleAddInReturnsAUISample#AddInUIMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml#addinuimarkup)]  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#addinuicodebehind)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#addinuicodebehind)]  
  
 <span data-ttu-id="d48c0-135">アドインによる `IWPFAddInView.GetAddInUI` の実装は、次のコードに示されているように、`AddInUI` の新しいインスタンスだけを返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="d48c0-135">The implementation of the `IWPFAddInView.GetAddInUI` by the add-in simply needs to return a new instance of `AddInUI`, as shown by the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddIn.cs#addincode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddIn.vb#addincode)]  
  
<a name="App"></a>

## <a name="implementing-the-host-application"></a><span data-ttu-id="d48c0-136">ホスト アプリケーションの実装</span><span class="sxs-lookup"><span data-stu-id="d48c0-136">Implementing the Host Application</span></span>  

 <span data-ttu-id="d48c0-137">ホスト側のアダプターとホスト ビューが作成されると、ホスト アプリケーションは .NET Framework アドイン モデルを使用して、パイプラインを開き、アドインのホスト ビューを取得し、`IWPFAddInHostView.GetAddInUI` メソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="d48c0-137">With the host-side adapter and host view created, the host application can use the .NET Framework add-in model to open the pipeline, acquire a host view of the add-in, and call the `IWPFAddInHostView.GetAddInUI` method.</span></span> <span data-ttu-id="d48c0-138">これらの手順を次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="d48c0-138">These steps are shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Host/MainWindow.xaml.cs#getuicode)]
 [!code-vb[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Host/MainWindow.xaml.vb#getuicode)]  
  
## <a name="see-also"></a><span data-ttu-id="d48c0-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="d48c0-139">See also</span></span>

- <span data-ttu-id="d48c0-140">[アドインおよび拡張機能](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))</span><span class="sxs-lookup"><span data-stu-id="d48c0-140">[Add-ins and Extensibility](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))</span></span>
- [<span data-ttu-id="d48c0-141">WPF のアドインの概要</span><span class="sxs-lookup"><span data-stu-id="d48c0-141">WPF Add-Ins Overview</span></span>](wpf-add-ins-overview.md)
