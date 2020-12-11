---
title: '方法: カスタム コントロールからインクを選択する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], ink selection
- ink [WPF], selecting from custom control
- custom controls [WPF], ink selection
ms.assetid: 5f3a45c6-6d40-4017-9b47-933f134ceba3
ms.openlocfilehash: 5c9b2f3d64e4cbb309772d6a1d9fa88f589df84c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985096"
---
# <a name="how-to-select-ink-from-a-custom-control"></a><span data-ttu-id="fcbe0-102">方法: カスタム コントロールからインクを選択する</span><span class="sxs-lookup"><span data-stu-id="fcbe0-102">How to: Select Ink from a Custom Control</span></span>
<span data-ttu-id="fcbe0-103">カスタム コントロールに <xref:System.Windows.Ink.IncrementalLassoHitTester> を追加すると、<xref:System.Windows.Controls.InkCanvas> でなげなわを使ってインクを選択する場合と同様に、ユーザーがなげなわツールを使ってインクを選択できるようにコントロールを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="fcbe0-103">By adding an <xref:System.Windows.Ink.IncrementalLassoHitTester> to your custom control, you can enable your control so that a user can select ink with a lasso tool, similar to the way the <xref:System.Windows.Controls.InkCanvas> selects ink with a lasso.</span></span>  
  
 <span data-ttu-id="fcbe0-104">この例では、インクを有効にしたカスタム コントロールの作成に慣れていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="fcbe0-104">This example assumes you are familiar with creating an ink-enabled custom control.</span></span>  <span data-ttu-id="fcbe0-105">インク入力を受け入れるカスタム コントロールを作成するには、「[インク入力コントロールの作成](creating-an-ink-input-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fcbe0-105">To create a custom control that accepts ink input, see [Creating an Ink Input Control](creating-an-ink-input-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fcbe0-106">例</span><span class="sxs-lookup"><span data-stu-id="fcbe0-106">Example</span></span>  
 <span data-ttu-id="fcbe0-107">ユーザーがなげなわを描画すると、ユーザーがなげなわを完了した後に、<xref:System.Windows.Ink.IncrementalLassoHitTester> によってなげなわパスの境界内にあるストロークが予測されます。</span><span class="sxs-lookup"><span data-stu-id="fcbe0-107">When the user draws a lasso, the <xref:System.Windows.Ink.IncrementalLassoHitTester> predicts which strokes will be within the lasso path's boundaries after the user completes the lasso.</span></span>  <span data-ttu-id="fcbe0-108">なげなわパスの境界内にあると判断されたストロークは、選択対象と考えることができます。</span><span class="sxs-lookup"><span data-stu-id="fcbe0-108">Strokes that are determined to be within the lasso path's boundaries can be thought of as being selected.</span></span>  <span data-ttu-id="fcbe0-109">選択されたストロークを選択解除することもできます。</span><span class="sxs-lookup"><span data-stu-id="fcbe0-109">Selected strokes can also become unselected.</span></span>  <span data-ttu-id="fcbe0-110">たとえば、なげなわを描画しているときにユーザーが方向を反転させると、<xref:System.Windows.Ink.IncrementalLassoHitTester> によって一部のストロークの選択が解除されることがあります。</span><span class="sxs-lookup"><span data-stu-id="fcbe0-110">For example, if the user reverses direction while drawing the lasso, the <xref:System.Windows.Ink.IncrementalLassoHitTester> may unselect some strokes.</span></span>  
  
 <span data-ttu-id="fcbe0-111"><xref:System.Windows.Ink.IncrementalLassoHitTester> によって <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> イベントが発生します。これにより、ユーザーがなげなわを描画している間にカスタム コントロールが応答できるようになります。</span><span class="sxs-lookup"><span data-stu-id="fcbe0-111">The <xref:System.Windows.Ink.IncrementalLassoHitTester> raises the <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> event, which enables your custom control to respond while the user is drawing the lasso.</span></span>  <span data-ttu-id="fcbe0-112">たとえば、ユーザーがストロークを選択または選択解除するときに、ストロークの外観を変更できます。</span><span class="sxs-lookup"><span data-stu-id="fcbe0-112">For example, you can change the appearance of strokes as the user selects and unselects them.</span></span>  
  
## <a name="managing-the-ink-mode"></a><span data-ttu-id="fcbe0-113">インク モードの管理</span><span class="sxs-lookup"><span data-stu-id="fcbe0-113">Managing the Ink Mode</span></span>  
 <span data-ttu-id="fcbe0-114">なげなわをコントロールのインクとは異なる外観にすると、ユーザーにとって便利です。</span><span class="sxs-lookup"><span data-stu-id="fcbe0-114">It is helpful to the user if the lasso appears differently than the ink on your control.</span></span> <span data-ttu-id="fcbe0-115">これを実現するには、ユーザーがインクを書き込んでいるか、選択しているかをカスタム コントロールで追跡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcbe0-115">To accomplish this, your custom control must keep track of whether the user is writing or selecting ink.</span></span> <span data-ttu-id="fcbe0-116">これを行う最も簡単な方法は、2 つの値を使用して列挙型を宣言することです。1 つはユーザーがインクを書き込んでいることを示すものと、もう 1 つはユーザーがインクを選択していることを示すものです。</span><span class="sxs-lookup"><span data-stu-id="fcbe0-116">The easiest way to do this is to declare an enumeration with two values: one to indicate that the user is writing ink and one to indicate that the user is selecting ink.</span></span>  
  
 [!code-csharp[HowToSelectInk#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#2)]
 [!code-vb[HowToSelectInk#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#2)]  
  
 <span data-ttu-id="fcbe0-117">次に、2 つの <xref:System.Windows.Ink.DrawingAttributes> をクラスに追加します。1 つはユーザーがインクを書き込むときに使用するもの、もう 1 つはユーザーがインクを選択するときに使用するものです。</span><span class="sxs-lookup"><span data-stu-id="fcbe0-117">Next, add two <xref:System.Windows.Ink.DrawingAttributes> to the class: one to use when the user writes ink, one to use when the user selects ink.</span></span>  <span data-ttu-id="fcbe0-118">コンストラクターで <xref:System.Windows.Ink.DrawingAttributes> を初期化し、両方の <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> イベントを同じイベント ハンドラーにアタッチします。</span><span class="sxs-lookup"><span data-stu-id="fcbe0-118">In the constructor, initialize the <xref:System.Windows.Ink.DrawingAttributes> and attach both <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> events to the same event handler.</span></span> <span data-ttu-id="fcbe0-119">次に、<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> の <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> プロパティをインク <xref:System.Windows.Ink.DrawingAttributes> に設定します。</span><span class="sxs-lookup"><span data-stu-id="fcbe0-119">Then set the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> property of the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> to the ink <xref:System.Windows.Ink.DrawingAttributes>.</span></span>  
  
 [!code-csharp[HowToSelectInk#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#3)]
 [!code-vb[HowToSelectInk#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#3)]  
[!code-csharp[HowToSelectInk#4](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#4)]
[!code-vb[HowToSelectInk#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#4)]  
  
 <span data-ttu-id="fcbe0-120">選択モードを公開するプロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="fcbe0-120">Add a property that exposes the selection mode.</span></span> <span data-ttu-id="fcbe0-121">ユーザーが選択モードを変更したら、<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> の <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> プロパティを適切な <xref:System.Windows.Ink.DrawingAttributes> オブジェクトに設定してから、<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> プロパティを <xref:System.Windows.Controls.InkPresenter> に再アタッチします。</span><span class="sxs-lookup"><span data-stu-id="fcbe0-121">When the user changes the selection mode, set the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> property of the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> to the appropriate <xref:System.Windows.Ink.DrawingAttributes> object and then reattach the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> Property to the <xref:System.Windows.Controls.InkPresenter>.</span></span>  
  
 [!code-csharp[HowToSelectInk#5](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#5)]
 [!code-vb[HowToSelectInk#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#5)]  
  
 <span data-ttu-id="fcbe0-122">アプリケーションによってインク ストロークと選択ストロークの外観を決定できるように、<xref:System.Windows.Ink.DrawingAttributes> をプロパティとして公開します。</span><span class="sxs-lookup"><span data-stu-id="fcbe0-122">Expose the <xref:System.Windows.Ink.DrawingAttributes> as properties so applications can determine the appearance of the ink strokes and selection strokes.</span></span>  
  
 [!code-csharp[HowToSelectInk#6](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#6)]
 [!code-vb[HowToSelectInk#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#6)]  
  
 <span data-ttu-id="fcbe0-123"><xref:System.Windows.Ink.DrawingAttributes> オブジェクトのプロパティが変更された場合、<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> を <xref:System.Windows.Controls.InkPresenter> に再アタッチする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcbe0-123">When a property of a <xref:System.Windows.Ink.DrawingAttributes> object changes, the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> must be reattached to the <xref:System.Windows.Controls.InkPresenter>.</span></span>  <span data-ttu-id="fcbe0-124"><xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> イベントのイベント ハンドラーで、<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> を <xref:System.Windows.Controls.InkPresenter> に再アタッチします。</span><span class="sxs-lookup"><span data-stu-id="fcbe0-124">In the event handler for the <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> event, reattach the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> to the <xref:System.Windows.Controls.InkPresenter>.</span></span>  
  
 [!code-csharp[HowToSelectInk#7](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#7)]
 [!code-vb[HowToSelectInk#7](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#7)]  
  
## <a name="using-the-incrementallassohittester"></a><span data-ttu-id="fcbe0-125">IncrementalLassoHitTester の使用</span><span class="sxs-lookup"><span data-stu-id="fcbe0-125">Using the IncrementalLassoHitTester</span></span>  
 <span data-ttu-id="fcbe0-126">選択したストロークを含む <xref:System.Windows.Ink.StrokeCollection> を作成して初期化します。</span><span class="sxs-lookup"><span data-stu-id="fcbe0-126">Create and initialize a <xref:System.Windows.Ink.StrokeCollection> that contains the selected strokes.</span></span>  
  
 [!code-csharp[HowToSelectInk#8](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#8)]
 [!code-vb[HowToSelectInk#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#8)]  
  
 <span data-ttu-id="fcbe0-127">ユーザーがインクまたはなげなわでストロークを描画し始めたら、選択したストロークの選択を解除します。</span><span class="sxs-lookup"><span data-stu-id="fcbe0-127">When the user starts to draw a stroke, either ink or the lasso, unselect any selected strokes.</span></span> <span data-ttu-id="fcbe0-128">次に、ユーザーがなげなわを描画している場合は、<xref:System.Windows.Ink.StrokeCollection.GetIncrementalLassoHitTester%2A> を呼び出して <xref:System.Windows.Ink.IncrementalLassoHitTester> を作成し、<xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> イベントを登録して、<xref:System.Windows.Ink.IncrementalHitTester.AddPoints%2A> を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="fcbe0-128">Then, if the user is drawing a lasso, create an <xref:System.Windows.Ink.IncrementalLassoHitTester> by calling <xref:System.Windows.Ink.StrokeCollection.GetIncrementalLassoHitTester%2A>, subscribe to the <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> event, and call <xref:System.Windows.Ink.IncrementalHitTester.AddPoints%2A>.</span></span> <span data-ttu-id="fcbe0-129">このコードを個別のメソッドにして、<xref:System.Windows.UIElement.OnStylusDown%2A> および <xref:System.Windows.UIElement.OnMouseDown%2A> メソッドから呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="fcbe0-129">This code can be a separate method and called from the <xref:System.Windows.UIElement.OnStylusDown%2A> and <xref:System.Windows.UIElement.OnMouseDown%2A> methods.</span></span>  
  
 [!code-csharp[HowToSelectInk#9](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#9)]
 [!code-vb[HowToSelectInk#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#9)]  
  
 <span data-ttu-id="fcbe0-130">ユーザーがなげなわを描画している間に、スタイラス ポイントを <xref:System.Windows.Ink.IncrementalLassoHitTester> に追加します。</span><span class="sxs-lookup"><span data-stu-id="fcbe0-130">Add the stylus points to the <xref:System.Windows.Ink.IncrementalLassoHitTester> while the user draws the lasso.</span></span>  <span data-ttu-id="fcbe0-131"><xref:System.Windows.UIElement.OnStylusMove%2A>、<xref:System.Windows.UIElement.OnStylusUp%2A>、<xref:System.Windows.UIElement.OnMouseMove%2A>、<xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> メソッドから次のメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="fcbe0-131">Call the following method from the <xref:System.Windows.UIElement.OnStylusMove%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, <xref:System.Windows.UIElement.OnMouseMove%2A>, and <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> methods.</span></span>  
  
 [!code-csharp[HowToSelectInk#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#10)]
 [!code-vb[HowToSelectInk#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#10)]  
  
 <span data-ttu-id="fcbe0-132">ユーザーがストロークを選択または選択解除したときに応答するように <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged?displayProperty=nameWithType> イベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="fcbe0-132">Handle the <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged?displayProperty=nameWithType> event to respond when the user selects and unselects strokes.</span></span>  <span data-ttu-id="fcbe0-133"><xref:System.Windows.Ink.LassoSelectionChangedEventArgs> クラスには、選択されたストロークと選択解除されたストロークをそれぞれ取得する <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.SelectedStrokes%2A> プロパティと <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.DeselectedStrokes%2A> プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="fcbe0-133">The <xref:System.Windows.Ink.LassoSelectionChangedEventArgs> class has the <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.SelectedStrokes%2A> and <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.DeselectedStrokes%2A> properties that get the strokes that were selected and unselected, respectively.</span></span>  
  
 [!code-csharp[HowToSelectInk#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#11)]
 [!code-vb[HowToSelectInk#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#11)]  
  
 <span data-ttu-id="fcbe0-134">ユーザーがなげなわの描画を完了したら、<xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> イベントの登録を解除して <xref:System.Windows.Ink.IncrementalHitTester.EndHitTesting%2A> を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="fcbe0-134">When the user finishes drawing the lasso, unsubscribe from the <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> event and call <xref:System.Windows.Ink.IncrementalHitTester.EndHitTesting%2A>.</span></span>  
  
 [!code-csharp[HowToSelectInk#12](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#12)]
 [!code-vb[HowToSelectInk#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#12)]  
  
## <a name="putting-it-all-together"></a><span data-ttu-id="fcbe0-135">すべてを組み合わせると次のようになります。</span><span class="sxs-lookup"><span data-stu-id="fcbe0-135">Putting it All Together.</span></span>  
 <span data-ttu-id="fcbe0-136">次の例は、ユーザーがなげなわでインクを選択できるようにするカスタム コントロールです。</span><span class="sxs-lookup"><span data-stu-id="fcbe0-136">The following example is a custom control that enables a user to select ink with a lasso.</span></span>  
  
 [!code-csharp[HowToSelectInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#1)]
 [!code-vb[HowToSelectInk#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="fcbe0-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="fcbe0-137">See also</span></span>

- <xref:System.Windows.Ink.IncrementalLassoHitTester>
- <xref:System.Windows.Ink.StrokeCollection>
- <xref:System.Windows.Input.StylusPointCollection>
- [<span data-ttu-id="fcbe0-138">インク入力コントロールの作成</span><span class="sxs-lookup"><span data-stu-id="fcbe0-138">Creating an Ink Input Control</span></span>](creating-an-ink-input-control.md)
