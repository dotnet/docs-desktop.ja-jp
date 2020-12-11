---
title: スタイラスからの入力のインターセプト
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 'architecture [WPF], '
- ', '
- ', '
- ', '
ms.assetid: 791bb2f0-4e5c-4569-ac3c-211996808d44
ms.openlocfilehash: f05a3c25a61e90ec91cd1db725ba9a40763f0a7f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974622"
---
# <a name="intercepting-input-from-the-stylus"></a><span data-ttu-id="ea585-102">スタイラスからの入力のインターセプト</span><span class="sxs-lookup"><span data-stu-id="ea585-102">Intercepting Input from the Stylus</span></span>

<span data-ttu-id="ea585-103"><xref:System.Windows.Input.StylusPlugIns> アーキテクチャには、<xref:System.Windows.Input.Stylus> の入力およびデジタル インクの <xref:System.Windows.Ink.Stroke> オブジェクトの作成に対する低レベルの制御を実装するためのメカニズムが用意されています。</span><span class="sxs-lookup"><span data-stu-id="ea585-103">The <xref:System.Windows.Input.StylusPlugIns> architecture provides a mechanism for implementing low-level control over <xref:System.Windows.Input.Stylus> input and the creation of digital ink <xref:System.Windows.Ink.Stroke> objects.</span></span> <span data-ttu-id="ea585-104"><xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> クラスでは、パフォーマンスを最適にするために、カスタム動作を実装し、スタイラス デバイスから送信されるデータ ストリームにそれを適用するためのメカニズムが提供されています。</span><span class="sxs-lookup"><span data-stu-id="ea585-104">The <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> class provides a mechanism for you to implement custom behavior and apply it to the stream of data coming from the stylus device for the optimal performance.</span></span>  
  
 <span data-ttu-id="ea585-105">このトピックは、次の内容で構成されています。</span><span class="sxs-lookup"><span data-stu-id="ea585-105">This topic contains the following subsections:</span></span>  
  
- [<span data-ttu-id="ea585-106">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="ea585-106">Architecture</span></span>](#Architecture)  
  
- [<span data-ttu-id="ea585-107">スタイラス プラグインの実装</span><span class="sxs-lookup"><span data-stu-id="ea585-107">Implementing Stylus Plug-ins</span></span>](#ImplementingStylusPlugins)  
  
- [<span data-ttu-id="ea585-108">InkCanvas へのプラグインの追加</span><span class="sxs-lookup"><span data-stu-id="ea585-108">Adding Your Plug-in to an InkCanvas</span></span>](#AddingYourPluginToAnInkCanvas)  
  
- [<span data-ttu-id="ea585-109">まとめ</span><span class="sxs-lookup"><span data-stu-id="ea585-109">Conclusion</span></span>](#Conclusion)  
  
<a name="Architecture"></a>

## <a name="architecture"></a><span data-ttu-id="ea585-110">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="ea585-110">Architecture</span></span>  

 <span data-ttu-id="ea585-111"><xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> は、「[ペン入力へのアクセスとその操作](/previous-versions/ms818317(v%3dmsdn.10))」で説明されている [StylusInput](/previous-versions/dotnet/netframework-3.5/ms574861(v=vs.90)) API が進化したものです。</span><span class="sxs-lookup"><span data-stu-id="ea585-111">The <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> is the evolution of the [StylusInput](/previous-versions/dotnet/netframework-3.5/ms574861(v=vs.90)) APIs, described in [Accessing and Manipulating Pen Input](/previous-versions/ms818317(v%3dmsdn.10)).</span></span>  
  
 <span data-ttu-id="ea585-112">各 <xref:System.Windows.UIElement> には、<xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> である <xref:System.Windows.UIElement.StylusPlugIns%2A> プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="ea585-112">Each <xref:System.Windows.UIElement> has a <xref:System.Windows.UIElement.StylusPlugIns%2A> property that is a <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>.</span></span> <span data-ttu-id="ea585-113">要素の <xref:System.Windows.UIElement.StylusPlugIns%2A> プロパティに <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> を追加して、生成時に <xref:System.Windows.Input.StylusPoint> のデータを操作できます。</span><span class="sxs-lookup"><span data-stu-id="ea585-113">You can add a <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> to an element's <xref:System.Windows.UIElement.StylusPlugIns%2A> property to manipulate <xref:System.Windows.Input.StylusPoint> data as it is generated.</span></span> <span data-ttu-id="ea585-114"><xref:System.Windows.Input.StylusPoint> のデータは、<xref:System.Windows.Input.StylusPoint.X%2A> および <xref:System.Windows.Input.StylusPoint.Y%2A> のポイント データや <xref:System.Windows.Input.StylusPoint.PressureFactor%2A> など、システム デジタイザーによってサポートされているすべてのプロパティで構成されます。</span><span class="sxs-lookup"><span data-stu-id="ea585-114"><xref:System.Windows.Input.StylusPoint> data consists of all the properties supported by the system digitizer, including the <xref:System.Windows.Input.StylusPoint.X%2A> and <xref:System.Windows.Input.StylusPoint.Y%2A> point data, as well as <xref:System.Windows.Input.StylusPoint.PressureFactor%2A> data.</span></span>  
  
 <span data-ttu-id="ea585-115"><xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> を <xref:System.Windows.UIElement.StylusPlugIns%2A> プロパティに追加すると、<xref:System.Windows.Input.Stylus> デバイスから送信されるデータ ストリームに、<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> オブジェクトが直接挿入されます。</span><span class="sxs-lookup"><span data-stu-id="ea585-115">Your <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> objects are inserted directly into the stream of data coming from the <xref:System.Windows.Input.Stylus> device when you add the <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> to the <xref:System.Windows.UIElement.StylusPlugIns%2A> property.</span></span> <span data-ttu-id="ea585-116">プラグインが <xref:System.Windows.UIElement.StylusPlugIns%2A> コレクションに追加される順序によって、<xref:System.Windows.Input.StylusPoint> データを受信する順序が決まります。</span><span class="sxs-lookup"><span data-stu-id="ea585-116">The order in which plug-ins are added to the <xref:System.Windows.UIElement.StylusPlugIns%2A> collection dictates the order in which they will receive <xref:System.Windows.Input.StylusPoint> data.</span></span> <span data-ttu-id="ea585-117">たとえば、入力を特定の領域に制限するフィルター プラグインを追加した後、書き込まれたジェスチャを認識するプラグインを追加した場合、ジェスチャを認識するプラグインは、フィルター処理された <xref:System.Windows.Input.StylusPoint> データを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="ea585-117">For example, if you add a filter plug-in that restricts input to a particular region, and then add a plug-in that recognizes gestures as they are written, the plug-in that recognizes gestures will receive filtered <xref:System.Windows.Input.StylusPoint> data.</span></span>  
  
<a name="ImplementingStylusPlugins"></a>

## <a name="implementing-stylus-plug-ins"></a><span data-ttu-id="ea585-118">スタイラス プラグインの実装</span><span class="sxs-lookup"><span data-stu-id="ea585-118">Implementing Stylus Plug-ins</span></span>  

 <span data-ttu-id="ea585-119">プラグインを実装するには、<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> の派生クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="ea585-119">To implement a plug-in, derive a class from <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>.</span></span> <span data-ttu-id="ea585-120">このクラスは、<xref:System.Windows.Input.Stylus> から送られてくるデータのストリームに適用されます。</span><span class="sxs-lookup"><span data-stu-id="ea585-120">This class is applied o the stream of data as it comes in from the <xref:System.Windows.Input.Stylus>.</span></span> <span data-ttu-id="ea585-121">このクラスでは、<xref:System.Windows.Input.StylusPoint> データの値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="ea585-121">In this class you can modify the values of the <xref:System.Windows.Input.StylusPoint> data.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="ea585-122"><xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> で例外がスローされた場合、またはそれが例外の原因になった場合、アプリケーションは終了します。</span><span class="sxs-lookup"><span data-stu-id="ea585-122">If a <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> throws or causes an exception, the application will close.</span></span> <span data-ttu-id="ea585-123"><xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> を使用するコントロールを十分にテストし、<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> で例外がスローされないことが確実な場合にのみ、コントロールを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea585-123">You should thoroughly test controls that consume a <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> and only use a control if you are certain the <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> will not throw an exception.</span></span>  
  
 <span data-ttu-id="ea585-124">次の例では、<xref:System.Windows.Input.Stylus> デバイスから送られてきた <xref:System.Windows.Input.StylusPoint> データの <xref:System.Windows.Input.StylusPoint.X%2A> と <xref:System.Windows.Input.StylusPoint.Y%2A> の値を変更することによって、スタイラスの入力を制限するプラグインを示します。</span><span class="sxs-lookup"><span data-stu-id="ea585-124">The following example demonstrates a plug-in that restricts the stylus input by modifying the <xref:System.Windows.Input.StylusPoint.X%2A> and <xref:System.Windows.Input.StylusPoint.Y%2A> values in the <xref:System.Windows.Input.StylusPoint> data as it comes in from the <xref:System.Windows.Input.Stylus> device.</span></span>  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#3](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#3)]
[!code-vb[AdvancedInkTopicsSamples#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#3)]  
  
<a name="AddingYourPluginToAnInkCanvas"></a>

## <a name="adding-your-plug-in-to-an-inkcanvas"></a><span data-ttu-id="ea585-125">InkCanvas へのプラグインの追加</span><span class="sxs-lookup"><span data-stu-id="ea585-125">Adding Your Plug-in to an InkCanvas</span></span>  

 <span data-ttu-id="ea585-126">カスタム プラグインを使用する最も簡単な方法は、InkCanvas から派生するクラスを実装し、それを <xref:System.Windows.UIElement.StylusPlugIns%2A> プロパティに追加することです。</span><span class="sxs-lookup"><span data-stu-id="ea585-126">The easiest way to use your custom plug-in is to implement a class that derives from InkCanvas and add it to the <xref:System.Windows.UIElement.StylusPlugIns%2A> property.</span></span>  
  
 <span data-ttu-id="ea585-127">次の例では、インクをフィルター処理するカスタム <xref:System.Windows.Controls.InkCanvas> を示します。</span><span class="sxs-lookup"><span data-stu-id="ea585-127">The following example demonstrates a custom <xref:System.Windows.Controls.InkCanvas> that filters the ink.</span></span>  
  
 [!code-csharp[AdvancedInkTopicsSamples#4](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#4)]  
  
 <span data-ttu-id="ea585-128">`FilterInkCanvas` をアプリケーションに追加して実行すると、ユーザーがストロークを完了するまで、インクの領域が限定されないことがわかります。</span><span class="sxs-lookup"><span data-stu-id="ea585-128">If you add a `FilterInkCanvas` to your application and run it, you will notice that the ink isn't restricted to a region until after the user completes a stroke.</span></span> <span data-ttu-id="ea585-129">これは、<xref:System.Windows.Controls.InkCanvas> には <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> プロパティがありますが、それは <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> であり、既に <xref:System.Windows.UIElement.StylusPlugIns%2A> コレクションのメンバーになっているためです。</span><span class="sxs-lookup"><span data-stu-id="ea585-129">This is because the <xref:System.Windows.Controls.InkCanvas> has a <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> property, which is a <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> and is already a member of the <xref:System.Windows.UIElement.StylusPlugIns%2A> collection.</span></span> <span data-ttu-id="ea585-130"><xref:System.Windows.UIElement.StylusPlugIns%2A> コレクションに追加したカスタム <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> は、<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> がデータを受け取った後で、<xref:System.Windows.Input.StylusPoint> データを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="ea585-130">The custom <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> you added to the <xref:System.Windows.UIElement.StylusPlugIns%2A> collection receives the <xref:System.Windows.Input.StylusPoint> data after <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> receives data.</span></span> <span data-ttu-id="ea585-131">その結果、ユーザーがペンを上げてストロークを終了するまで、<xref:System.Windows.Input.StylusPoint> データはフィルター処理されません。</span><span class="sxs-lookup"><span data-stu-id="ea585-131">As a result, the <xref:System.Windows.Input.StylusPoint> data will not be filtered until after the user lifts the pen to end a stroke.</span></span> <span data-ttu-id="ea585-132">ユーザーが描画するのと同時にインクをフィルター処理するには、<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> の前に `FilterPlugin` を挿入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea585-132">To filter the ink as the user draws it, you must insert the `FilterPlugin` before the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>.</span></span>  
  
 <span data-ttu-id="ea585-133">次の C# コードでは、描画と同時にインクをフィルター処理するカスタム <xref:System.Windows.Controls.InkCanvas> を示します。</span><span class="sxs-lookup"><span data-stu-id="ea585-133">The following C# code demonstrates a custom <xref:System.Windows.Controls.InkCanvas> that filters the ink as it is drawn.</span></span>  
  
 [!code-csharp[AdvancedInkTopicsSamples#5](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#5)]  
  
<a name="Conclusion"></a>

## <a name="conclusion"></a><span data-ttu-id="ea585-134">まとめ</span><span class="sxs-lookup"><span data-stu-id="ea585-134">Conclusion</span></span>  

 <span data-ttu-id="ea585-135">独自の <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> クラスを派生させて <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> コレクションに挿入することにより、デジタル インクの動作を大幅に拡張できます。</span><span class="sxs-lookup"><span data-stu-id="ea585-135">By deriving your own <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> classes and inserting them into <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> collections, you can greatly enhance the behavior of your digital ink.</span></span> <span data-ttu-id="ea585-136">生成されている <xref:System.Windows.Input.StylusPoint> データにアクセスし、<xref:System.Windows.Input.Stylus> の入力をカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="ea585-136">You have access to the <xref:System.Windows.Input.StylusPoint> data as it is generated, giving you the opportunity to customize the <xref:System.Windows.Input.Stylus> input.</span></span> <span data-ttu-id="ea585-137">そのように低いレベルで <xref:System.Windows.Input.StylusPoint> のデータにアクセスできるため、アプリケーションに最適なパフォーマンスでインクのコレクションとレンダリングを実装できます。</span><span class="sxs-lookup"><span data-stu-id="ea585-137">Because you have such low-level access to the <xref:System.Windows.Input.StylusPoint> data, you can implement ink collection and rendering with optimal performance for your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea585-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="ea585-138">See also</span></span>

- [<span data-ttu-id="ea585-139">高度なインク処理</span><span class="sxs-lookup"><span data-stu-id="ea585-139">Advanced Ink Handling</span></span>](advanced-ink-handling.md)
- <span data-ttu-id="ea585-140">[ペン入力へのアクセスとその操作](/previous-versions/ms818317(v%3dmsdn.10))</span><span class="sxs-lookup"><span data-stu-id="ea585-140">[Accessing and Manipulating Pen Input](/previous-versions/ms818317(v%3dmsdn.10))</span></span>
