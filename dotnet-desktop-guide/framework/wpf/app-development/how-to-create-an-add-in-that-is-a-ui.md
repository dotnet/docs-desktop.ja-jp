---
title: '方法: UI であるアドインを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating an add-in that is a UI [WPF]
- add-ins [WPF], UI
- creating UI add-ins [WPF]
- UI add-ins [WPF], creating
- implementing UI add-ins [WPF]
- pipeline segments [WPF], creating add-ins
ms.assetid: 86375525-282b-4039-8352-8680051a10ea
ms.openlocfilehash: fd37e651dc94485becf972533bc095f9ad253335
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983768"
---
# <a name="how-to-create-an-add-in-that-is-a-ui"></a><span data-ttu-id="99937-102">方法: UI であるアドインを作成する</span><span class="sxs-lookup"><span data-stu-id="99937-102">How to: Create an Add-In That Is a UI</span></span>

<span data-ttu-id="99937-103">この例では、WPF スタンドアロン アプリケーションによってホストされる、Windows Presentation Foundation (WPF) であるアドインを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="99937-103">This example shows how to create an add-in that is a Windows Presentation Foundation (WPF) which is hosted by a WPF standalone application.</span></span>  
  
 <span data-ttu-id="99937-104">このアドインは、WPF ユーザー コントロール である UI です。</span><span class="sxs-lookup"><span data-stu-id="99937-104">The add-in is a UI that is a WPF user control.</span></span> <span data-ttu-id="99937-105">ユーザー コントロールの中身は 1 つのボタンであり、クリックすると、メッセージ ボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="99937-105">The content of the user control is a single button that, when clicked, displays a message box.</span></span> <span data-ttu-id="99937-106">WPF スタンドアロン アプリケーションでは、メイン アプリケーション ウィンドウのコンテンツとして、アドイン UI がホストされます。</span><span class="sxs-lookup"><span data-stu-id="99937-106">The WPF standalone application hosts the add-in UI as the content of the main application window.</span></span>  
  
 <span data-ttu-id="99937-107">**必須コンポーネント**</span><span class="sxs-lookup"><span data-stu-id="99937-107">**Prerequisites**</span></span>  
  
 <span data-ttu-id="99937-108">この例では、このシナリオを実現する .NET Framework アドイン モデルの WPF 拡張機能に焦点を当てます。前提条件は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="99937-108">This example highlights the WPF extensions to the .NET Framework add-in model that enable this scenario, and assumes the following:</span></span>  
  
- <span data-ttu-id="99937-109">パイプライン、アドイン、ホスト環境など、.NET Framework アドイン モデルの知識。</span><span class="sxs-lookup"><span data-stu-id="99937-109">Knowledge of the .NET Framework add-in model, including pipeline, add-in, and host development.</span></span> <span data-ttu-id="99937-110">これらの概念については、「[アドインおよび拡張機能](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99937-110">If you are unfamiliar with these concepts, see [Add-ins and Extensibility](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)).</span></span> <span data-ttu-id="99937-111">パイプライン、アドイン、およびホスト アプリケーションの実装例を示すチュートリアルについては、「[チュートリアル: 拡張性のあるアプリケーションの作成](/previous-versions/dotnet/netframework-4.0/bb788290(v%3dvs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99937-111">For a tutorial that demonstrates the implementation of a pipeline, an add-in, and a host application, see [Walkthrough: Creating an Extensible Application](/previous-versions/dotnet/netframework-4.0/bb788290(v%3dvs.100)).</span></span>  
  
- <span data-ttu-id="99937-112">.NET Framework アドイン モデルに対する WPF 拡張機能の知識。</span><span class="sxs-lookup"><span data-stu-id="99937-112">Knowledge of the WPF extensions to the .NET Framework add-in model.</span></span> <span data-ttu-id="99937-113">「[WPF のアドインの概要](wpf-add-ins-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99937-113">See [WPF Add-Ins Overview](wpf-add-ins-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="99937-114">例</span><span class="sxs-lookup"><span data-stu-id="99937-114">Example</span></span>  

 <span data-ttu-id="99937-115">WPF UI であるアドインを作成するには、各パイプライン セグメント、アドイン、およびホスト アプリケーションに特定のコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="99937-115">To create an add-in that is a WPF UI requires specific code for each pipeline segment, the add-in, and the host application.</span></span>  

<a name="Contract"></a>

## <a name="implementing-the-contract-pipeline-segment"></a><span data-ttu-id="99937-116">コントラクト パイプライン セグメントの実装</span><span class="sxs-lookup"><span data-stu-id="99937-116">Implementing the Contract Pipeline Segment</span></span>

<span data-ttu-id="99937-117">アドインが UI のときは、アドインのコントラクトで <xref:System.AddIn.Contract.INativeHandleContract> を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99937-117">When an add-in is a UI, the contract for the add-in must implement <xref:System.AddIn.Contract.INativeHandleContract>.</span></span> <span data-ttu-id="99937-118">次のコードに示すように、この例では、`IWPFAddInContract` で <xref:System.AddIn.Contract.INativeHandleContract> が実装されています。</span><span class="sxs-lookup"><span data-stu-id="99937-118">In the example, `IWPFAddInContract` implements <xref:System.AddIn.Contract.INativeHandleContract>, as shown in the following code.</span></span>  
  
[!code-csharp[SimpleAddInIsAUISample#ContractCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
[!code-vb[SimpleAddInIsAUISample#ContractCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]

<a name="AddInViewPipeline"></a>

## <a name="implementing-the-add-in-view-pipeline-segment"></a><span data-ttu-id="99937-119">アドイン ビュー パイプライン セグメントの実装</span><span class="sxs-lookup"><span data-stu-id="99937-119">Implementing the Add-In View Pipeline Segment</span></span>

<span data-ttu-id="99937-120">アドインは <xref:System.Windows.FrameworkElement> 型のサブクラスとして実装されるため、アドイン ビューも <xref:System.Windows.FrameworkElement> のサブクラスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="99937-120">Because the add-in is implemented as a subclass of the <xref:System.Windows.FrameworkElement> type, the add-in view must also subclass <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="99937-121">次のコードでは、`WPFAddInView` クラスとして実装されるコントラクトのアドイン ビューを示します。</span><span class="sxs-lookup"><span data-stu-id="99937-121">The following code shows the add-in view of the contract, implemented as the `WPFAddInView` class.</span></span>  
  
[!code-csharp[SimpleAddInIsAUISample#AddInViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInViews/WPFAddInView.cs#addinviewcode)]  
[!code-vb[SimpleAddInIsAUISample#AddInViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/AddInViews/WPFAddInView.vb#AddInViewCode)]  
  
<span data-ttu-id="99937-122">ここでは、アドイン ビューは <xref:System.Windows.Controls.UserControl> から派生します。</span><span class="sxs-lookup"><span data-stu-id="99937-122">Here, the add-in view is derived from <xref:System.Windows.Controls.UserControl>.</span></span> <span data-ttu-id="99937-123">したがって、アドイン UI も <xref:System.Windows.Controls.UserControl> から派生する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99937-123">Consequently, the add-in UI should also derive from <xref:System.Windows.Controls.UserControl>.</span></span>  
  
<a name="AddInSideAdapter"></a>

## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a><span data-ttu-id="99937-124">アドイン側アダプター パイプライン セグメントの実装</span><span class="sxs-lookup"><span data-stu-id="99937-124">Implementing the Add-In-Side Adapter Pipeline Segment</span></span>

<span data-ttu-id="99937-125">コントラクトは <xref:System.AddIn.Contract.INativeHandleContract> ですが、アドインは <xref:System.Windows.FrameworkElement> です (アドイン ビュー パイプライン セグメントによって指定されたように)。</span><span class="sxs-lookup"><span data-stu-id="99937-125">While the contract is an <xref:System.AddIn.Contract.INativeHandleContract>, the add-in is a <xref:System.Windows.FrameworkElement> (as specified by the add-in view pipeline segment).</span></span> <span data-ttu-id="99937-126">したがって、<xref:System.Windows.FrameworkElement> は、分離境界を越える前に <xref:System.AddIn.Contract.INativeHandleContract> に変換される必要があります。</span><span class="sxs-lookup"><span data-stu-id="99937-126">Therefore, the <xref:System.Windows.FrameworkElement> must be converted to an <xref:System.AddIn.Contract.INativeHandleContract> before crossing the isolation boundary.</span></span> <span data-ttu-id="99937-127">この作業は、次のコードで示されているように、アドイン側のアダプターで <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> を呼び出すことによって行われます。</span><span class="sxs-lookup"><span data-stu-id="99937-127">This work is performed by the add-in-side adapter by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, as shown in the following code.</span></span>  
  
[!code-csharp[SimpleAddInIsAUISample#AddInSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]  
[!code-vb[SimpleAddInIsAUISample#AddInSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]

<span data-ttu-id="99937-128">アドインで UI が返されるアドイン モデルでは (「[UI を返すアドインを作成する](how-to-create-an-add-in-that-returns-a-ui.md)」を参照)、アドイン アダプターで <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> を呼び出すことによって、<xref:System.Windows.FrameworkElement> から <xref:System.AddIn.Contract.INativeHandleContract> に変換されます。</span><span class="sxs-lookup"><span data-stu-id="99937-128">In the add-in model where an add-in returns a UI (see [Create an Add-In That Returns a UI](how-to-create-an-add-in-that-returns-a-ui.md)), the add-in adapter converted the <xref:System.Windows.FrameworkElement> to an <xref:System.AddIn.Contract.INativeHandleContract> by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>.</span></span> <span data-ttu-id="99937-129">このモデルでは、<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> も呼び出す必要がありますが、これを呼び出すコードを記述するメソッドを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99937-129"><xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> must also be called in this model, although you need to implement a method from which to write the code to call it.</span></span> <span data-ttu-id="99937-130">このためには、<xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> を呼び出すコードで <xref:System.AddIn.Contract.INativeHandleContract> が予期されている場合は、<xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> をオーバーライドして、<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> を呼び出すコードを実装します。</span><span class="sxs-lookup"><span data-stu-id="99937-130">You do this by overriding <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> and implementing the code that calls <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> if the code that is calling <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> is expecting an <xref:System.AddIn.Contract.INativeHandleContract>.</span></span> <span data-ttu-id="99937-131">この場合、呼び出し元はホスト側のアダプターであり、これについては、後で説明します。</span><span class="sxs-lookup"><span data-stu-id="99937-131">In this case, the caller will be the host-side adapter, which is covered in a subsequent subsection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="99937-132">このモデルでは、<xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> もオーバーライドして、ホスト アプリケーション UI とアドイン UI の間を Tab キーで移動できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="99937-132">You also need to override <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> in this model to enable tabbing between host application UI and add-in UI.</span></span> <span data-ttu-id="99937-133">詳細については、「[WPF アドインの概要](wpf-add-ins-overview.md)」の「WPF アドインの制約」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99937-133">For more information, see "WPF Add-In Limitations" in [WPF Add-Ins Overview](wpf-add-ins-overview.md).</span></span>  
  
<span data-ttu-id="99937-134">アドイン側のアダプターでは <xref:System.AddIn.Contract.INativeHandleContract> から派生するインターフェイスを実装するため、<xref:System.AddIn.Contract.INativeHandleContract.GetHandle%2A> を実装する必要もありますが、<xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> がオーバーライドされるときは、これは無視されます。</span><span class="sxs-lookup"><span data-stu-id="99937-134">Because the add-in-side adapter implements an interface that derives from <xref:System.AddIn.Contract.INativeHandleContract>, you also need to implement <xref:System.AddIn.Contract.INativeHandleContract.GetHandle%2A>, although this is ignored when <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> is overridden.</span></span>  
  
<a name="HostViewPipeline"></a>

## <a name="implementing-the-host-view-pipeline-segment"></a><span data-ttu-id="99937-135">ホスト ビュー パイプライン セグメントの実装</span><span class="sxs-lookup"><span data-stu-id="99937-135">Implementing the Host View Pipeline Segment</span></span>

<span data-ttu-id="99937-136">このモデルのホスト アプリケーションでは、通常、ホスト ビューが <xref:System.Windows.FrameworkElement> サブクラスであることが予期されています。</span><span class="sxs-lookup"><span data-stu-id="99937-136">In this model, the host application typically expects the host view to be a <xref:System.Windows.FrameworkElement> subclass.</span></span> <span data-ttu-id="99937-137">ホスト側アダプターでは、<xref:System.AddIn.Contract.INativeHandleContract> が分離境界を越えた後で、<xref:System.AddIn.Contract.INativeHandleContract> を <xref:System.Windows.FrameworkElement> に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99937-137">The host-side adapter must convert the <xref:System.AddIn.Contract.INativeHandleContract> to a <xref:System.Windows.FrameworkElement> after the <xref:System.AddIn.Contract.INativeHandleContract> crosses the isolation boundary.</span></span> <span data-ttu-id="99937-138"><xref:System.Windows.FrameworkElement> を取得するためにホスト アプリケーションによってメソッドは呼び出されていないため、ホスト ビューでは、<xref:System.Windows.FrameworkElement> を格納することによって、"返す" 必要があります。</span><span class="sxs-lookup"><span data-stu-id="99937-138">Because a method isn't being called by the host application to get the <xref:System.Windows.FrameworkElement>, the host view must "return" the <xref:System.Windows.FrameworkElement> by containing it.</span></span> <span data-ttu-id="99937-139">したがって、ホスト ビューは、<xref:System.Windows.Controls.UserControl> など、他の UI を格納できる <xref:System.Windows.FrameworkElement> のサブクラスから派生する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99937-139">Consequently, the host view must derive from a subclass of <xref:System.Windows.FrameworkElement> that can contain other UIs, such as <xref:System.Windows.Controls.UserControl>.</span></span> <span data-ttu-id="99937-140">次のコードでは、`WPFAddInHostView` クラスとして実装されるコントラクトのホスト ビューを示します。</span><span class="sxs-lookup"><span data-stu-id="99937-140">The following code shows the host view of the contract, implemented as the `WPFAddInHostView` class.</span></span>  

[!code-csharp[WPFAddInHostView class](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/HostViews/WPFAddInHostView.cs#HostViewCode)]
[!code-vb[WPFAddInHostView class](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/HostViews/WPFAddInHostView.vb#HostViewCode)]

<a name="HostSideAdapter"></a>

## <a name="implementing-the-host-side-adapter-pipeline-segment"></a><span data-ttu-id="99937-141">ホスト側アダプター パイプライン セグメントの実装</span><span class="sxs-lookup"><span data-stu-id="99937-141">Implementing the Host-Side Adapter Pipeline Segment</span></span>

<span data-ttu-id="99937-142">コントラクトは <xref:System.AddIn.Contract.INativeHandleContract> ですが、ホスト アプリケーションでは <xref:System.Windows.Controls.UserControl> が予期されています (ホスト ビューによって指定されたように)。</span><span class="sxs-lookup"><span data-stu-id="99937-142">While the contract is an <xref:System.AddIn.Contract.INativeHandleContract>, the host application expects a <xref:System.Windows.Controls.UserControl> (as specified by the host view).</span></span> <span data-ttu-id="99937-143">したがって、<xref:System.AddIn.Contract.INativeHandleContract> は、分離境界を越えた後、ホスト ビューのコンテンツ (<xref:System.Windows.Controls.UserControl> から派生) として設定される前に、<xref:System.Windows.FrameworkElement> に変換される必要があります。</span><span class="sxs-lookup"><span data-stu-id="99937-143">Consequently, the <xref:System.AddIn.Contract.INativeHandleContract> must be converted to a <xref:System.Windows.FrameworkElement> after crossing the isolation boundary, before being set as content of the host view (which derives from <xref:System.Windows.Controls.UserControl>).</span></span>  
  
<span data-ttu-id="99937-144">この作業は、次のコードに示されているように、ホスト側アダプターによって行われます。</span><span class="sxs-lookup"><span data-stu-id="99937-144">This work is performed by the host-side adapter, as shown in the following code.</span></span>  

[!code-csharp[Host-side adapter](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#HostSideAdapterCode)]
[!code-vb[Host-side adapter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#HostSideAdapterCode)]

<span data-ttu-id="99937-145">このことからもわかるように、ホスト側のアダプターは、アドイン側のアダプターの <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> メソッドを呼び出すことによって、<xref:System.AddIn.Contract.INativeHandleContract> を取得します (ここが <xref:System.AddIn.Contract.INativeHandleContract> が分離境界を越えるポイントです)。</span><span class="sxs-lookup"><span data-stu-id="99937-145">As you can see, the host-side adapter acquires the <xref:System.AddIn.Contract.INativeHandleContract> by calling the add-in-side adapter's <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> method (this is the point where the <xref:System.AddIn.Contract.INativeHandleContract> crosses the isolation boundary).</span></span>  
  
<span data-ttu-id="99937-146">その後、ホスト側のアダプターでは、<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> を呼び出すことによって、<xref:System.AddIn.Contract.INativeHandleContract> が <xref:System.Windows.FrameworkElement> に変換されます。</span><span class="sxs-lookup"><span data-stu-id="99937-146">The host-side adapter then converts the <xref:System.AddIn.Contract.INativeHandleContract> to a <xref:System.Windows.FrameworkElement> by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>.</span></span> <span data-ttu-id="99937-147">最後に、<xref:System.Windows.FrameworkElement> がホスト ビューのコンテンツとして設定されます。</span><span class="sxs-lookup"><span data-stu-id="99937-147">Finally, the <xref:System.Windows.FrameworkElement> is set as the content of the host view.</span></span>  
  
<a name="AddIn"></a>

## <a name="implementing-the-add-in"></a><span data-ttu-id="99937-148">アドインの実装</span><span class="sxs-lookup"><span data-stu-id="99937-148">Implementing the Add-In</span></span>

<span data-ttu-id="99937-149">アドイン側アダプターとアドイン ビューが用意できると、次のコードに示されているように、アドイン ビューから派生することでアドインを実装できます。</span><span class="sxs-lookup"><span data-stu-id="99937-149">With the add-in-side adapter and add-in view in place, the add-in can be implemented by deriving from the add-in view, as shown in the following code.</span></span>  

[!code-csharp[Add-in implementation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#AddInCodeBehind)]
[!code-vb[Add-in implementation](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#AddInCodeBehind)]

<span data-ttu-id="99937-150">この例から、このモデルの興味深い利点がわかります。つまり、アドイン開発者は、アドインだけを実装すればよく (これが UI でもあるため)、アドイン クラスとアドイン UI の両方を実装する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="99937-150">From this example, you can see one interesting benefit of this model: add-in developers only need to implement the add-in (since it is the UI as well), rather than both an add-in class and an add-in UI.</span></span>  
  
<a name="HostApp"></a>

## <a name="implementing-the-host-application"></a><span data-ttu-id="99937-151">ホスト アプリケーションの実装</span><span class="sxs-lookup"><span data-stu-id="99937-151">Implementing the Host Application</span></span>

<span data-ttu-id="99937-152">ホスト側のアダプターとホスト ビューが作成されると、ホスト アプリケーションは .NET Framework アドイン モデルを使用して、パイプラインを開き、アドインのホスト ビューを取得できます。</span><span class="sxs-lookup"><span data-stu-id="99937-152">With the host-side adapter and host view created, the host application can use the .NET Framework add-in model to open the pipeline and acquire a host view of the add-in.</span></span> <span data-ttu-id="99937-153">これらの手順を次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="99937-153">These steps are shown in the following code.</span></span>  

[!code-csharp[Acquiring a host view of the add-in](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/Host/MainWindow.xaml.cs#GetUICode)]
[!code-vb[Acquiring a host view of the add-in](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/Host/MainWindow.xaml.vb#GetUICode)]

<span data-ttu-id="99937-154">ホスト アプリケーションでは、一般的な .NET Framework アドイン モデル コードを使用して、アドインをアクティブ化し、このアドインは、ホスト ビューをホスト アプリケーションに暗黙的に返します。</span><span class="sxs-lookup"><span data-stu-id="99937-154">The host application uses typical .NET Framework add-in model code to activate the add-in, which implicitly returns the host view to the host application.</span></span> <span data-ttu-id="99937-155">その後、ホスト アプリケーションはホスト ビュー (<xref:System.Windows.Controls.UserControl>) を <xref:System.Windows.Controls.Grid> から表示します。</span><span class="sxs-lookup"><span data-stu-id="99937-155">The host application subsequently displays the host view (which is a <xref:System.Windows.Controls.UserControl>) from a <xref:System.Windows.Controls.Grid>.</span></span>  
  
 <span data-ttu-id="99937-156">アドイン UI との対話を処理するコードは、アドインのアプリケーション ドメインで実行します。</span><span class="sxs-lookup"><span data-stu-id="99937-156">The code for processing interactions with the add-in UI runs in the add-in's application domain.</span></span> <span data-ttu-id="99937-157">このような対話には、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="99937-157">These interactions include the following:</span></span>  
  
- <span data-ttu-id="99937-158"><xref:System.Windows.Controls.Button> の <xref:System.Windows.Controls.Primitives.ButtonBase.Click> イベントの処理。</span><span class="sxs-lookup"><span data-stu-id="99937-158">Handling the <xref:System.Windows.Controls.Button><xref:System.Windows.Controls.Primitives.ButtonBase.Click> event.</span></span>  
  
- <span data-ttu-id="99937-159"><xref:System.Windows.MessageBox> の表示。</span><span class="sxs-lookup"><span data-stu-id="99937-159">Showing the <xref:System.Windows.MessageBox>.</span></span>  
  
 <span data-ttu-id="99937-160">このアクティビティは、ホスト アプリケーションから完全に分離されています。</span><span class="sxs-lookup"><span data-stu-id="99937-160">This activity is completely isolated from the host application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99937-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="99937-161">See also</span></span>

- <span data-ttu-id="99937-162">[アドインおよび拡張機能](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))</span><span class="sxs-lookup"><span data-stu-id="99937-162">[Add-ins and Extensibility](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))</span></span>
- [<span data-ttu-id="99937-163">WPF のアドインの概要</span><span class="sxs-lookup"><span data-stu-id="99937-163">WPF Add-Ins Overview</span></span>](wpf-add-ins-overview.md)
