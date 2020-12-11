---
title: デジタル インクを収集する
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ink [WPF], collecting
- InkCanvas element [WPF]
- properties [WPF], DrawingAttributes
- collecting digital ink [WPF]
- digital ink [WPF], collecting
- properties [WPF], DefaultDrawingAttributes
- DefaultDrawingAttributes property [WPF]
ms.assetid: 66a3129d-9577-43eb-acbd-56c147282016
ms.openlocfilehash: 813a5313a6fbf83c36cdbed1f64ce69a217ad788
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982363"
---
# <a name="collect-ink"></a><span data-ttu-id="5e6ea-102">インクを収集する</span><span class="sxs-lookup"><span data-stu-id="5e6ea-102">Collect Ink</span></span>

<span data-ttu-id="5e6ea-103">[Windows Presentation Foundation](../index.md) プラットフォームでは、その機能の中核としてデジタル インクが収集されます。</span><span class="sxs-lookup"><span data-stu-id="5e6ea-103">The [Windows Presentation Foundation](../index.md) platform collects digital ink as a core part of its functionality.</span></span> <span data-ttu-id="5e6ea-104">このトピックでは、Windows Presentation Foundation (WPF) でインクを収集する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5e6ea-104">This topic discusses methods for collection of ink in Windows Presentation Foundation (WPF).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5e6ea-105">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="5e6ea-105">Prerequisites</span></span>

<span data-ttu-id="5e6ea-106">次の例を使用するには、まず Visual Studio と Windows SDK をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e6ea-106">To use the following examples, you must first install Visual Studio and the Windows SDK.</span></span> <span data-ttu-id="5e6ea-107">また、WPF に対応するアプリケーションの作成方法も理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e6ea-107">You should also understand how to write applications for the WPF.</span></span> <span data-ttu-id="5e6ea-108">WPF の概要については、「[チュートリアル: 初めての WPF デスクトップ アプリケーション](../getting-started/walkthrough-my-first-wpf-desktop-application.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e6ea-108">For more information about getting started with WPF, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

## <a name="use-the-inkcanvas-element"></a><span data-ttu-id="5e6ea-109">InkCanvas 要素を使用する</span><span class="sxs-lookup"><span data-stu-id="5e6ea-109">Use the InkCanvas Element</span></span>

<span data-ttu-id="5e6ea-110"><xref:System.Windows.Controls.InkCanvas?displayProperty=fullName> 要素を使用すると、最も簡単に WPF でインクを収集できます。</span><span class="sxs-lookup"><span data-stu-id="5e6ea-110">The <xref:System.Windows.Controls.InkCanvas?displayProperty=fullName> element provides the easiest way to collect ink in WPF.</span></span> <span data-ttu-id="5e6ea-111"><xref:System.Windows.Controls.InkCanvas> 要素を使用して、インク入力を受け取って表示します。</span><span class="sxs-lookup"><span data-stu-id="5e6ea-111">Use an <xref:System.Windows.Controls.InkCanvas> element to receive and display ink input.</span></span> <span data-ttu-id="5e6ea-112">インクは一般的に、スタイラスを使用して入力します。スタイラスはデジタイザーとの対話により、インク ストロークを生成します。</span><span class="sxs-lookup"><span data-stu-id="5e6ea-112">You commonly input ink through the use of a stylus, which interacts with a digitizer to produce ink strokes.</span></span> <span data-ttu-id="5e6ea-113">また、スタイラスの代わりにマウスを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="5e6ea-113">In addition, a mouse can be used in place of a stylus.</span></span> <span data-ttu-id="5e6ea-114">作成されたストロークは <xref:System.Windows.Ink.Stroke> オブジェクトとして表され、プログラムとユーザー入力の両方で操作できます。</span><span class="sxs-lookup"><span data-stu-id="5e6ea-114">The created strokes are represented as <xref:System.Windows.Ink.Stroke> objects, and they can be manipulated both programmatically and by user input.</span></span> <span data-ttu-id="5e6ea-115"><xref:System.Windows.Controls.InkCanvas> を使用すると、ユーザーは既存の <xref:System.Windows.Ink.Stroke> を選択、変更、または削除できます。</span><span class="sxs-lookup"><span data-stu-id="5e6ea-115">The <xref:System.Windows.Controls.InkCanvas> enables users to select, modify, or delete an existing <xref:System.Windows.Ink.Stroke>.</span></span>

<span data-ttu-id="5e6ea-116">XAML を使用して、**InkCanvas** 要素をツリーに追加するだけで簡単にインク収集を設定できます。</span><span class="sxs-lookup"><span data-stu-id="5e6ea-116">By using XAML, you can set up ink collection as easily as adding an **InkCanvas** element to your tree.</span></span> <span data-ttu-id="5e6ea-117">次の例では、Visual Studio で作成された既定の WPF プロジェクトに <xref:System.Windows.Controls.InkCanvas> を追加します。</span><span class="sxs-lookup"><span data-stu-id="5e6ea-117">The following example adds an <xref:System.Windows.Controls.InkCanvas> to a default WPF project created in Visual Studio:</span></span>

[!code-xaml[DigitalInkTopics#6](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#6)]

<span data-ttu-id="5e6ea-118">**InkCanvas** 要素には子要素を含めることもできます。これにより、ほとんどすべての XAML 要素にインク注釈機能を追加できます。</span><span class="sxs-lookup"><span data-stu-id="5e6ea-118">The **InkCanvas** element can also contain child elements, making it possible to add ink annotation capabilities to almost any type of XAML element.</span></span> <span data-ttu-id="5e6ea-119">たとえば、テキスト要素にインク機能を追加するには、単にそれを <xref:System.Windows.Controls.InkCanvas> の子にします。</span><span class="sxs-lookup"><span data-stu-id="5e6ea-119">For example, to add inking capabilities to a text element, simply make it a child of an <xref:System.Windows.Controls.InkCanvas>:</span></span>

[!code-xaml[DigitalInkTopics#5](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#5)]

<span data-ttu-id="5e6ea-120">インクを使用したイメージのマークアップのサポートも、簡単に追加できます。</span><span class="sxs-lookup"><span data-stu-id="5e6ea-120">Adding support for marking up an image with ink is just as easy:</span></span>

[!code-xaml[DigitalInkTopics#7](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#7)]

### <a name="inkcollection-modes"></a><span data-ttu-id="5e6ea-121">InkCollection モード</span><span class="sxs-lookup"><span data-stu-id="5e6ea-121">InkCollection Modes</span></span>

<span data-ttu-id="5e6ea-122"><xref:System.Windows.Controls.InkCanvas> は、<xref:System.Windows.Controls.InkCanvas.EditingMode%2A> プロパティを介したさまざまな入力モードをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5e6ea-122">The <xref:System.Windows.Controls.InkCanvas> provides support for various input modes through its <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> property.</span></span>

### <a name="manipulate-ink"></a><span data-ttu-id="5e6ea-123">インクを操作する</span><span class="sxs-lookup"><span data-stu-id="5e6ea-123">Manipulate Ink</span></span>

<span data-ttu-id="5e6ea-124"><xref:System.Windows.Controls.InkCanvas> は、多くのインク編集操作をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5e6ea-124">The <xref:System.Windows.Controls.InkCanvas> provides support for many ink editing operations.</span></span> <span data-ttu-id="5e6ea-125">たとえば、<xref:System.Windows.Controls.InkCanvas> は消しゴム付きペンの機能をサポートしており、この機能を要素に追加するために追加のコードは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="5e6ea-125">For example, <xref:System.Windows.Controls.InkCanvas> supports back-of-pen erase, and no additional code is needed to add the functionality to the element.</span></span>

#### <a name="selection"></a><span data-ttu-id="5e6ea-126">選択ツール</span><span class="sxs-lookup"><span data-stu-id="5e6ea-126">Selection</span></span>

<span data-ttu-id="5e6ea-127">選択モードの設定は、<xref:System.Windows.Controls.InkCanvasEditingMode> プロパティを **Select** に設定する場合と同じくらい簡単です。</span><span class="sxs-lookup"><span data-stu-id="5e6ea-127">Setting selection mode is as simple as setting the <xref:System.Windows.Controls.InkCanvasEditingMode> property to **Select**.</span></span>

<span data-ttu-id="5e6ea-128">次のコードでは、<xref:System.Windows.Forms.CheckBox> の値に基づいて編集モードを設定します。</span><span class="sxs-lookup"><span data-stu-id="5e6ea-128">The following code sets the editing mode based on the value of a <xref:System.Windows.Forms.CheckBox>:</span></span>

[!code-csharp[DigitalInkTopics#8](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#8)]
[!code-vb[DigitalInkTopics#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#8)]

#### <a name="drawingattributes"></a><span data-ttu-id="5e6ea-129">DrawingAttributes</span><span class="sxs-lookup"><span data-stu-id="5e6ea-129">DrawingAttributes</span></span>

<span data-ttu-id="5e6ea-130">インク ストロークの外観を変更するには、<xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="5e6ea-130">Use the <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> property to change the appearance of ink strokes.</span></span> <span data-ttu-id="5e6ea-131">たとえば、<xref:System.Windows.Ink.DrawingAttributes> の <xref:System.Windows.Ink.DrawingAttributes.Color%2A> メンバーを使用して、レンダリングされた <xref:System.Windows.Ink.Stroke> の色を設定できます。</span><span class="sxs-lookup"><span data-stu-id="5e6ea-131">For instance, the <xref:System.Windows.Ink.DrawingAttributes.Color%2A> member of <xref:System.Windows.Ink.DrawingAttributes> sets the color of the rendered <xref:System.Windows.Ink.Stroke>.</span></span>

<span data-ttu-id="5e6ea-132">次の例では、選択されたストロークの色を赤に変更します。</span><span class="sxs-lookup"><span data-stu-id="5e6ea-132">The following example changes the color of the selected strokes to red:</span></span>

[!code-csharp[DigitalInkTopics#9](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#9)]
[!code-vb[DigitalInkTopics#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#9)]

### <a name="defaultdrawingattributes"></a><span data-ttu-id="5e6ea-133">DefaultDrawingAttributes</span><span class="sxs-lookup"><span data-stu-id="5e6ea-133">DefaultDrawingAttributes</span></span>

<span data-ttu-id="5e6ea-134"><xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> プロパティを使用すると、<xref:System.Windows.Controls.InkCanvas> で作成されるストロークの高さ、幅、色などのプロパティにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5e6ea-134">The <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> property provides access to properties such as the height, width, and color of the strokes to be created in an <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="5e6ea-135"><xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> を変更すると、以降、<xref:System.Windows.Controls.InkCanvas> に入力されるすべてのストロークは、新しいプロパティ値でレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="5e6ea-135">Once you change the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, all future strokes entered into the <xref:System.Windows.Controls.InkCanvas> are rendered with the new property values.</span></span>

<span data-ttu-id="5e6ea-136">分離コード ファイルの <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> を変更するだけでなく、XAML 構文を使用して <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> プロパティを指定できます。</span><span class="sxs-lookup"><span data-stu-id="5e6ea-136">In addition to modifying the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> in the code-behind file, you can use XAML syntax for specifying <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> properties.</span></span>

<span data-ttu-id="5e6ea-137">次の例は、<xref:System.Windows.Ink.DrawingAttributes.Color%2A> プロパティを設定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="5e6ea-137">The next example demonstrates how to set the <xref:System.Windows.Ink.DrawingAttributes.Color%2A> property.</span></span> <span data-ttu-id="5e6ea-138">このコードを使用するには、Visual Studio で "HelloInkCanvas" という新しい WPF プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="5e6ea-138">To use this code, create a new WPF project called "HelloInkCanvas" in Visual Studio.</span></span> <span data-ttu-id="5e6ea-139">*MainWindow.xaml* ファイル内のコードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="5e6ea-139">Replace the code in the *MainWindow.xaml* file with the following code:</span></span>

[!code-xaml[HelloInkCanvas#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml#1)]

<span data-ttu-id="5e6ea-140">次に、以下のボタン イベント ハンドラーを、分離コード ファイルの MainWindow クラス内に追加します。</span><span class="sxs-lookup"><span data-stu-id="5e6ea-140">Next, add the following button event handlers to the code behind file, inside the MainWindow class:</span></span>

[!code-csharp[HelloInkCanvas#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml.cs#2)]

<span data-ttu-id="5e6ea-141">このコードをコピーしたら、Visual Studio で **F5** キーを押して、デバッガーでプログラムを実行します。</span><span class="sxs-lookup"><span data-stu-id="5e6ea-141">After copying this code, press **F5** in Visual Studio to run the program in the debugger.</span></span>

<span data-ttu-id="5e6ea-142"><xref:System.Windows.Controls.StackPanel> によってボタンが <xref:System.Windows.Controls.InkCanvas> の上に配置されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5e6ea-142">Notice how the <xref:System.Windows.Controls.StackPanel> places the buttons on top of the <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="5e6ea-143">ボタンの上にインクを塗ろうとすると、<xref:System.Windows.Controls.InkCanvas> によってボタンの背後にインクが収集され、レンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="5e6ea-143">If you try to ink over the top of the buttons, the <xref:System.Windows.Controls.InkCanvas> collects and renders the ink behind the buttons.</span></span> <span data-ttu-id="5e6ea-144">これは、ボタンが <xref:System.Windows.Controls.InkCanvas> の子ではなく兄弟であるためです。</span><span class="sxs-lookup"><span data-stu-id="5e6ea-144">This is because the buttons are siblings of the <xref:System.Windows.Controls.InkCanvas> as opposed to children.</span></span> <span data-ttu-id="5e6ea-145">また、ボタンは z オーダーの上位に位置するため、インクはその背後で描画されます。</span><span class="sxs-lookup"><span data-stu-id="5e6ea-145">Also, the buttons are higher in the z-order, so the ink is rendered behind them.</span></span>

## <a name="see-also"></a><span data-ttu-id="5e6ea-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="5e6ea-146">See also</span></span>

- <xref:System.Windows.Ink.DrawingAttributes>
- <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>
- <xref:System.Windows.Ink>
