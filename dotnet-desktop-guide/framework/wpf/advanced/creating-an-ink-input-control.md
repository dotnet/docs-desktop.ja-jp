---
title: インク入力コントロールの作成
ms.date: 03/30/2017
helpviewer_keywords:
- ink strokes [WPF], managing
- managing ink strokes [WPF]
- ink input control [WPF]
- input from mouse [WPF], accepting
- mouse input [WPF], accepting
- ink [WPF], rendering
- ink strokes [WPF], collecting
- rendering ink [WPF]
- collecting ink strokes [WPF]
- DynamicRenderer objects [WPF]
- StylusPlugIn objects [WPF]
ms.assetid: c31f3a67-cb3f-4ded-af9e-ed21f6575b26
ms.openlocfilehash: d9b18054154e6871925f423f539d44f12adca1f5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982339"
---
# <a name="creating-an-ink-input-control"></a><span data-ttu-id="46d06-102">インク入力コントロールの作成</span><span class="sxs-lookup"><span data-stu-id="46d06-102">Creating an Ink Input Control</span></span>

<span data-ttu-id="46d06-103">インクを動的および静的にレンダリングするカスタム コントロールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="46d06-103">You can create a custom control that dynamically and statically renders ink.</span></span> <span data-ttu-id="46d06-104">つまり、ユーザーがストロークを描画するのに合わせてインクをレンダリングすることで、インクがタブレット ペンから "流れ出している" ように見えます。また、タブレット ペンの使用、クリップボードからの貼り付け、またはファイルからの読み込みにより、インクがコントロールに追加された後で、インクを表示します。</span><span class="sxs-lookup"><span data-stu-id="46d06-104">That is, render ink as a user draws a stroke, causing the ink to appear to "flow" from the tablet pen, and display ink after it is added to the control, either via the tablet pen, pasted from the Clipboard, or loaded from a file.</span></span> <span data-ttu-id="46d06-105">インクを動的にレンダリングするには、コントロールで <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46d06-105">To dynamically render ink, your control must use a <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>.</span></span> <span data-ttu-id="46d06-106">インクを静的にレンダリングするには、スタイラス イベント メソッド (<xref:System.Windows.UIElement.OnStylusDown%2A>、<xref:System.Windows.UIElement.OnStylusMove%2A>、<xref:System.Windows.UIElement.OnStylusUp%2A>) をオーバーライドして、<xref:System.Windows.Input.StylusPoint> データを収集し、ストロークを作成して、それらを <xref:System.Windows.Controls.InkPresenter> (コントロールのインクをレンダリングします) に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46d06-106">To statically render ink, you must override the stylus event methods (<xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusMove%2A>, and <xref:System.Windows.UIElement.OnStylusUp%2A>) to collect <xref:System.Windows.Input.StylusPoint> data, create strokes, and add them to an <xref:System.Windows.Controls.InkPresenter> (which renders the ink on the control).</span></span>  
  
 <span data-ttu-id="46d06-107">このトピックは、次の内容で構成されています。</span><span class="sxs-lookup"><span data-stu-id="46d06-107">This topic contains the following subsections:</span></span>  
  
- [<span data-ttu-id="46d06-108">方法: スタイラス ポイント データを収集してインク ストロークを作成する</span><span class="sxs-lookup"><span data-stu-id="46d06-108">How to: Collect Stylus Point Data and Create Ink Strokes</span></span>](#CollectingStylusPointDataAndCreatingInkStrokes)  
  
- [<span data-ttu-id="46d06-109">方法: コントロールがマウスからの入力を受け入れられるようにする</span><span class="sxs-lookup"><span data-stu-id="46d06-109">How to: Enable Your Control to Accept Input from the Mouse</span></span>](#EnablingYourControlToAcceptInputTromTheMouse)  
  
- [<span data-ttu-id="46d06-110">組み合わせる</span><span class="sxs-lookup"><span data-stu-id="46d06-110">Putting it together</span></span>](#PuttingItTogether)  
  
- [<span data-ttu-id="46d06-111">追加のプラグインと DynamicRenderers を使用する</span><span class="sxs-lookup"><span data-stu-id="46d06-111">Using Additional Plug-ins and DynamicRenderers</span></span>](#UsingAdditionalPluginsAndDynamicRenderers)  
  
- [<span data-ttu-id="46d06-112">まとめ</span><span class="sxs-lookup"><span data-stu-id="46d06-112">Conclusion</span></span>](#AdvancedInkHandling_Conclusion)  
  
<a name="CollectingStylusPointDataAndCreatingInkStrokes"></a>

## <a name="how-to-collect-stylus-point-data-and-create-ink-strokes"></a><span data-ttu-id="46d06-113">方法: スタイラス ポイント データを収集してインク ストロークを作成する</span><span class="sxs-lookup"><span data-stu-id="46d06-113">How to: Collect Stylus Point Data and Create Ink Strokes</span></span>  

 <span data-ttu-id="46d06-114">インクストロークを収集して管理するコントロールを作成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="46d06-114">To create a control that collects and manages ink strokes do the following:</span></span>  
  
1. <span data-ttu-id="46d06-115"><xref:System.Windows.Controls.Control> または <xref:System.Windows.Controls.Control> の派生クラスのいずれか (<xref:System.Windows.Controls.Label> など) からクラスを派生します。</span><span class="sxs-lookup"><span data-stu-id="46d06-115">Derive a class from <xref:System.Windows.Controls.Control> or one of the classes derived from <xref:System.Windows.Controls.Control>, such as <xref:System.Windows.Controls.Label>.</span></span>  
  
     [!code-csharp[AdvancedInkTopicsSamples#20](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
    [!code-csharp[AdvancedInkTopicsSamples#14](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#14)]  
    [!code-csharp[AdvancedInkTopicsSamples#15](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#15)]  
  
2. <span data-ttu-id="46d06-116">クラスに <xref:System.Windows.Controls.InkPresenter> を追加し、<xref:System.Windows.Controls.ContentControl.Content%2A> プロパティに新しい <xref:System.Windows.Controls.InkPresenter> を設定します。</span><span class="sxs-lookup"><span data-stu-id="46d06-116">Add an <xref:System.Windows.Controls.InkPresenter> to the class and set the <xref:System.Windows.Controls.ContentControl.Content%2A> property to the new <xref:System.Windows.Controls.InkPresenter>.</span></span>  
  
     [!code-csharp[AdvancedInkTopicsSamples#16](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#16)]  
  
3. <span data-ttu-id="46d06-117"><xref:System.Windows.Controls.InkPresenter.AttachVisuals%2A> メソッドを呼び出すことによって <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> の <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> を <xref:System.Windows.Controls.InkPresenter> にアタッチし、<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> を <xref:System.Windows.UIElement.StylusPlugIns%2A> コレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="46d06-117">Attach the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> of the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> to the <xref:System.Windows.Controls.InkPresenter> by calling the <xref:System.Windows.Controls.InkPresenter.AttachVisuals%2A> method, and add the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> to the <xref:System.Windows.UIElement.StylusPlugIns%2A> collection.</span></span> <span data-ttu-id="46d06-118">これにより、コントロールによってスタイラス ポイント データが収集されたら、<xref:System.Windows.Controls.InkPresenter> でインクを表示できるようになります。</span><span class="sxs-lookup"><span data-stu-id="46d06-118">This allows the <xref:System.Windows.Controls.InkPresenter> to display the ink as the stylus point data is collected by your control.</span></span>  
  
     [!code-csharp[AdvancedInkTopicsSamples#17](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#17)]  
    [!code-csharp[AdvancedInkTopicsSamples#18](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#18)]  
  
4. <span data-ttu-id="46d06-119"><xref:System.Windows.UIElement.OnStylusDown%2A> メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="46d06-119">Override the <xref:System.Windows.UIElement.OnStylusDown%2A> method.</span></span>  <span data-ttu-id="46d06-120">このメソッドでは、<xref:System.Windows.Input.Stylus.Capture%2A> を呼び出してスタイラスをキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="46d06-120">In this method, capture the stylus with a call to <xref:System.Windows.Input.Stylus.Capture%2A>.</span></span> <span data-ttu-id="46d06-121">スタイラスをキャプチャすることにより、スタイラスがコントロールの境界から出た場合でも、コントロールは <xref:System.Windows.UIElement.StylusMove> イベントと <xref:System.Windows.UIElement.StylusUp> イベントを引き続き受け取ります。</span><span class="sxs-lookup"><span data-stu-id="46d06-121">By capturing the stylus, your control will to continue to receive <xref:System.Windows.UIElement.StylusMove> and <xref:System.Windows.UIElement.StylusUp> events even if the stylus leaves the control's boundaries.</span></span> <span data-ttu-id="46d06-122">これは絶対に必要なわけではありませんが、優れたユーザー エクスペリエンスを実現するためにほとんどの場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="46d06-122">This is not strictly mandatory, but almost always desired for a good user experience.</span></span> <span data-ttu-id="46d06-123">新しい <xref:System.Windows.Input.StylusPointCollection> を作成して <xref:System.Windows.Input.StylusPoint> データを収集します。</span><span class="sxs-lookup"><span data-stu-id="46d06-123">Create a new <xref:System.Windows.Input.StylusPointCollection> to gather <xref:System.Windows.Input.StylusPoint> data.</span></span> <span data-ttu-id="46d06-124">最後に、<xref:System.Windows.Input.StylusPoint> データの初期セットを <xref:System.Windows.Input.StylusPointCollection> に追加します。</span><span class="sxs-lookup"><span data-stu-id="46d06-124">Finally, add the initial set of <xref:System.Windows.Input.StylusPoint> data to the <xref:System.Windows.Input.StylusPointCollection>.</span></span>  
  
     [!code-csharp[AdvancedInkTopicsSamples#7](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#7)]  
  
5. <span data-ttu-id="46d06-125"><xref:System.Windows.UIElement.OnStylusMove%2A> メソッドをオーバーライドし、前に作成した <xref:System.Windows.Input.StylusPointCollection> オブジェクトに <xref:System.Windows.Input.StylusPoint> データを追加します。</span><span class="sxs-lookup"><span data-stu-id="46d06-125">Override the <xref:System.Windows.UIElement.OnStylusMove%2A> method and add the <xref:System.Windows.Input.StylusPoint> data to the <xref:System.Windows.Input.StylusPointCollection> object that you created earlier.</span></span>  
  
     [!code-csharp[AdvancedInkTopicsSamples#8](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#8)]  
  
6. <span data-ttu-id="46d06-126"><xref:System.Windows.UIElement.OnStylusUp%2A> メソッドをオーバーライドし、<xref:System.Windows.Input.StylusPointCollection> データを使用して新しい <xref:System.Windows.Ink.Stroke> を作成します。</span><span class="sxs-lookup"><span data-stu-id="46d06-126">Override the <xref:System.Windows.UIElement.OnStylusUp%2A> method and create a new <xref:System.Windows.Ink.Stroke> with the <xref:System.Windows.Input.StylusPointCollection> data.</span></span> <span data-ttu-id="46d06-127">作成した新しい <xref:System.Windows.Ink.Stroke> を <xref:System.Windows.Controls.InkPresenter> の <xref:System.Windows.Controls.InkPresenter.Strokes%2A> コレクションに追加し、スタイラスのキャプチャを解放します。</span><span class="sxs-lookup"><span data-stu-id="46d06-127">Add the new <xref:System.Windows.Ink.Stroke> you created to the <xref:System.Windows.Controls.InkPresenter.Strokes%2A> collection of the <xref:System.Windows.Controls.InkPresenter> and release stylus capture.</span></span>  
  
     [!code-csharp[AdvancedInkTopicsSamples#10](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#10)]  
  
<a name="EnablingYourControlToAcceptInputTromTheMouse"></a>

## <a name="how-to-enable-your-control-to-accept-input-from-the-mouse"></a><span data-ttu-id="46d06-128">方法: コントロールがマウスからの入力を受け入れられるようにする</span><span class="sxs-lookup"><span data-stu-id="46d06-128">How to: Enable Your Control to Accept Input from the Mouse</span></span>  

 <span data-ttu-id="46d06-129">前に示したコントロールをアプリケーションに追加して実行し、マウスを入力デバイスとして使用した場合、ストロークが永続化されないことがわかります。</span><span class="sxs-lookup"><span data-stu-id="46d06-129">If you add the preceding control to your application, run it, and use the mouse as an input device, you will notice that the strokes are not persisted.</span></span> <span data-ttu-id="46d06-130">入力デバイスとしてマウスを使用したときにストロークを保持するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="46d06-130">To persist the strokes when the mouse is used as the input device do the following:</span></span>  
  
1. <span data-ttu-id="46d06-131"><xref:System.Windows.UIElement.OnMouseLeftButtonDown%2A> をオーバーライドして、新しい <xref:System.Windows.Input.StylusPointCollection> 作成します。イベントが発生したときのマウスの位置を取得し、ポイント データを使用して <xref:System.Windows.Input.StylusPoint> を作成し、<xref:System.Windows.Input.StylusPoint> を <xref:System.Windows.Input.StylusPointCollection> に追加します。</span><span class="sxs-lookup"><span data-stu-id="46d06-131">Override the <xref:System.Windows.UIElement.OnMouseLeftButtonDown%2A> and create a new <xref:System.Windows.Input.StylusPointCollection> Get the position of the mouse when the event occurred and create a <xref:System.Windows.Input.StylusPoint> using the point data and add the <xref:System.Windows.Input.StylusPoint> to the <xref:System.Windows.Input.StylusPointCollection>.</span></span>  
  
     [!code-csharp[AdvancedInkTopicsSamples#11](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#11)]  
  
2. <span data-ttu-id="46d06-132"><xref:System.Windows.UIElement.OnMouseMove%2A> メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="46d06-132">Override the <xref:System.Windows.UIElement.OnMouseMove%2A> method.</span></span> <span data-ttu-id="46d06-133">イベントが発生したときのマウスの位置を取得し、ポイント データを使用して <xref:System.Windows.Input.StylusPoint> を作成します。</span><span class="sxs-lookup"><span data-stu-id="46d06-133">Get the position of the mouse when the event occurred and create a <xref:System.Windows.Input.StylusPoint> using the point data.</span></span>  <span data-ttu-id="46d06-134">前に作成した <xref:System.Windows.Input.StylusPointCollection> オブジェクトに <xref:System.Windows.Input.StylusPoint> を追加します。</span><span class="sxs-lookup"><span data-stu-id="46d06-134">Add the <xref:System.Windows.Input.StylusPoint> to the <xref:System.Windows.Input.StylusPointCollection> object that you created earlier.</span></span>  
  
     [!code-csharp[AdvancedInkTopicsSamples#12](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#12)]  
  
3. <span data-ttu-id="46d06-135"><xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="46d06-135">Override the <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> method.</span></span>  <span data-ttu-id="46d06-136"><xref:System.Windows.Input.StylusPointCollection> データを使用して新しい <xref:System.Windows.Ink.Stroke> を作成し、作成した新しい <xref:System.Windows.Ink.Stroke> を <xref:System.Windows.Controls.InkPresenter> の <xref:System.Windows.Controls.InkPresenter.Strokes%2A> コレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="46d06-136">Create a new <xref:System.Windows.Ink.Stroke> with the <xref:System.Windows.Input.StylusPointCollection> data, and add the new <xref:System.Windows.Ink.Stroke> you created to the <xref:System.Windows.Controls.InkPresenter.Strokes%2A> collection of the <xref:System.Windows.Controls.InkPresenter>.</span></span>  
  
     [!code-csharp[AdvancedInkTopicsSamples#13](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#13)]  
  
<a name="PuttingItTogether"></a>

## <a name="putting-it-together"></a><span data-ttu-id="46d06-137">組み合わせる</span><span class="sxs-lookup"><span data-stu-id="46d06-137">Putting it together</span></span>  

 <span data-ttu-id="46d06-138">次の例は、ユーザーがマウスまたはペンを使用したときにインクを収集するカスタム コントロールです。</span><span class="sxs-lookup"><span data-stu-id="46d06-138">The following example is a custom control that collects ink when the user uses either the mouse or the pen.</span></span>  
  
 [!code-csharp[AdvancedInkTopicsSamples#20](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
[!code-csharp[AdvancedInkTopicsSamples#6](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#6)]  
  
<a name="UsingAdditionalPluginsAndDynamicRenderers"></a>

## <a name="using-additional-plug-ins-and-dynamicrenderers"></a><span data-ttu-id="46d06-139">追加のプラグインと DynamicRenderers を使用する</span><span class="sxs-lookup"><span data-stu-id="46d06-139">Using Additional Plug-ins and DynamicRenderers</span></span>  

 <span data-ttu-id="46d06-140">InkCanvas と同様に、カスタム コントロールでは、カスタム <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> オブジェクトと追加の <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> オブジェクトを使用できます。</span><span class="sxs-lookup"><span data-stu-id="46d06-140">Like the InkCanvas, your custom control can have custom <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> and additional <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> objects.</span></span> <span data-ttu-id="46d06-141">これらを <xref:System.Windows.UIElement.StylusPlugIns%2A> コレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="46d06-141">Add these to the <xref:System.Windows.UIElement.StylusPlugIns%2A> collection.</span></span> <span data-ttu-id="46d06-142"><xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> 内の <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> オブジェクトの順序は、レンダリング時のインクの外観に影響します。</span><span class="sxs-lookup"><span data-stu-id="46d06-142">The order of the <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> objects in the <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> affects the appearance of the ink when it is rendered.</span></span> <span data-ttu-id="46d06-143">`dynamicRenderer` という名前の <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> と、タブレット ペンからのインクをオフセットする `translatePlugin` という名前のカスタム <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> があるとします。</span><span class="sxs-lookup"><span data-stu-id="46d06-143">Suppose you have a <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> called `dynamicRenderer` and a custom <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> called `translatePlugin` that offsets the ink from the tablet pen.</span></span> <span data-ttu-id="46d06-144">`translatePlugin` が <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> 内の最初の <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> であり、`dynamicRenderer` が 2 番目の場合は、ユーザーがペンを動かすと、"流れ出す" インクはオフセットされます。</span><span class="sxs-lookup"><span data-stu-id="46d06-144">If `translatePlugin` is the first <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> in the <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>, and `dynamicRenderer` is the second, the ink that "flows" will be offset as the user moves the pen.</span></span> <span data-ttu-id="46d06-145">`dynamicRenderer` が最初で、`translatePlugin` が 2 番目の場合は、ユーザーがペンを持ち上げるまでインクはオフセットされません。</span><span class="sxs-lookup"><span data-stu-id="46d06-145">If `dynamicRenderer` is first, and `translatePlugin` is second, the ink will not be offset until the user lifts the pen.</span></span>  
  
<a name="AdvancedInkHandling_Conclusion"></a>

## <a name="conclusion"></a><span data-ttu-id="46d06-146">まとめ</span><span class="sxs-lookup"><span data-stu-id="46d06-146">Conclusion</span></span>  

 <span data-ttu-id="46d06-147">スタイラス イベント メソッドをオーバーライドすることにより、インクを収集してレンダリングするコントロールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="46d06-147">You can create a control that collects and renders ink by overriding the stylus event methods.</span></span> <span data-ttu-id="46d06-148">独自のコントロールを作成し、独自の <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> クラスを派生させ、それを <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> に挿入することにより、デジタル インクで想像できるほとんどどのような動作でも実装できます。</span><span class="sxs-lookup"><span data-stu-id="46d06-148">By creating your own control, deriving your own <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> classes, and inserting them the into <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>, you can implement virtually any behavior imaginable with digital ink.</span></span> <span data-ttu-id="46d06-149">生成された <xref:System.Windows.Input.StylusPoint> データにアクセスできるため、<xref:System.Windows.Input.Stylus> の入力をカスタマイズし、アプリケーションに適した方法で画面にレンダリングする機会があります。</span><span class="sxs-lookup"><span data-stu-id="46d06-149">You have access to the <xref:System.Windows.Input.StylusPoint> data as it is generated, giving you the opportunity to  customize <xref:System.Windows.Input.Stylus> input and render it on the screen as appropriate for your application.</span></span> <span data-ttu-id="46d06-150">そのように低いレベルで <xref:System.Windows.Input.StylusPoint> のデータにアクセスできるため、アプリケーションに最適なパフォーマンスでインクのコレクションとレンダリングを実装できます。</span><span class="sxs-lookup"><span data-stu-id="46d06-150">Because you have such low-level access to the <xref:System.Windows.Input.StylusPoint> data, you can implement ink collection and render it with optimal performance for your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46d06-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="46d06-151">See also</span></span>

- [<span data-ttu-id="46d06-152">高度なインク処理</span><span class="sxs-lookup"><span data-stu-id="46d06-152">Advanced Ink Handling</span></span>](advanced-ink-handling.md)
- <span data-ttu-id="46d06-153">[ペン入力へのアクセスとその操作](/previous-versions/ms818317(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="46d06-153">[Accessing and Manipulating Pen Input](/previous-versions/ms818317(v=msdn.10))</span></span>
