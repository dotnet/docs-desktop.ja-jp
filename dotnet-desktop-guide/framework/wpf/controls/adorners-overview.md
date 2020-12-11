---
title: 装飾の概要
description: Windows Presentation Foundation Adorners について学習します。これは、要素の機能ハンドルなど、ユーザーに手掛かりを提供する特別な種類の FrameworkElement です。
ms.date: 03/30/2017
ms.topic: overview
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], about adorners
ms.assetid: 33d4c5c2-2daf-4e45-ba9a-5b673e2b8280
ms.openlocfilehash: 092be2948b1fb609c583877d4e9138a111eaec53
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984276"
---
# <a name="adorners-overview"></a><span data-ttu-id="b90fc-103">装飾の概要</span><span class="sxs-lookup"><span data-stu-id="b90fc-103">Adorners Overview</span></span>

<span data-ttu-id="b90fc-104">装飾は特別な種類の <xref:System.Windows.FrameworkElement> で、ユーザーに視覚的手掛かりを提供するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="b90fc-104">Adorners are a special type of <xref:System.Windows.FrameworkElement>, used to provide visual cues to a user.</span></span> <span data-ttu-id="b90fc-105">装飾は、要素への機能ハンドル追加やコントロールに関する状態情報の提供など、さまざまな用途に使用できます。</span><span class="sxs-lookup"><span data-stu-id="b90fc-105">Among other uses, Adorners can be used to add functional handles to elements or provide state information about a control.</span></span>

## <a name="about-adorners"></a><span data-ttu-id="b90fc-106">装飾について</span><span class="sxs-lookup"><span data-stu-id="b90fc-106">About Adorners</span></span>

<span data-ttu-id="b90fc-107"><xref:System.Windows.Documents.Adorner> は、<xref:System.Windows.UIElement> にバインドされるカスタム <xref:System.Windows.FrameworkElement> です。</span><span class="sxs-lookup"><span data-stu-id="b90fc-107">An <xref:System.Windows.Documents.Adorner> is a custom <xref:System.Windows.FrameworkElement> that is bound to a <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="b90fc-108">装飾は、<xref:System.Windows.Documents.AdornerLayer> に描画されます。これは、常に装飾対象の要素またはそのコレクションの最上層に位置するレンダリング面です。</span><span class="sxs-lookup"><span data-stu-id="b90fc-108">Adorners are rendered in an <xref:System.Windows.Documents.AdornerLayer>, which is a rendering surface that is always on top of the adorned element or a collection of adorned elements.</span></span> <span data-ttu-id="b90fc-109">装飾のレンダリングは、装飾がバインドされる <xref:System.Windows.UIElement> のレンダリングとは独立しています。</span><span class="sxs-lookup"><span data-stu-id="b90fc-109">Rendering of an adorner is independent from rendering of the <xref:System.Windows.UIElement> that the adorner is bound to.</span></span> <span data-ttu-id="b90fc-110">通常、装飾は、装飾対象の要素の左上に位置する標準の 2 次元座標の原点を使用して、バインド先の要素に対して相対的な位置に配置されます。</span><span class="sxs-lookup"><span data-stu-id="b90fc-110">An adorner is typically positioned relative to the element to which it is bound, using the standard 2D coordinate origin located at the upper-left of the adorned element.</span></span>

<span data-ttu-id="b90fc-111">装飾の一般的な用途は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b90fc-111">Common applications for adorners include:</span></span>

- <span data-ttu-id="b90fc-112">ユーザーが要素を操作 (サイズ変更、回転、位置の変更など) するための機能ハンドルを <xref:System.Windows.UIElement> に追加する。</span><span class="sxs-lookup"><span data-stu-id="b90fc-112">Adding functional handles to a <xref:System.Windows.UIElement> that enable a user to manipulate the element in some way (resize, rotate, reposition, etc.).</span></span>
- <span data-ttu-id="b90fc-113">視覚的なフィードバックによって、さまざまな状態を表示し、各種のイベントに応答する。</span><span class="sxs-lookup"><span data-stu-id="b90fc-113">Provide visual feedback to indicate various states, or in response to various events.</span></span>
- <span data-ttu-id="b90fc-114"><xref:System.Windows.UIElement> に視覚的装飾をオーバーレイする。</span><span class="sxs-lookup"><span data-stu-id="b90fc-114">Overlay visual decorations on a <xref:System.Windows.UIElement>.</span></span>
- <span data-ttu-id="b90fc-115"><xref:System.Windows.UIElement> の一部または全部を視覚的にマスクするか、オーバーライドする。</span><span class="sxs-lookup"><span data-stu-id="b90fc-115">Visually mask or override part or all of a <xref:System.Windows.UIElement>.</span></span>

[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="b90fc-116">は、視覚的要素を装飾する基本的なフレームワークを提供します。</span><span class="sxs-lookup"><span data-stu-id="b90fc-116">provides a basic framework for adorning visual elements.</span></span> <span data-ttu-id="b90fc-117">次の表に示すのは、オブジェクトの装飾に使用する主な種類と、その用途の一覧です。</span><span class="sxs-lookup"><span data-stu-id="b90fc-117">The following table lists the primary types used when adorning objects, and their purpose.</span></span> <span data-ttu-id="b90fc-118">その後に、使用例をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="b90fc-118">Several usage examples follow:</span></span>

|||
|-|-|
|<xref:System.Windows.Documents.Adorner>|<span data-ttu-id="b90fc-119">具体的な装飾の実装すべての継承元になる抽象基本クラス。</span><span class="sxs-lookup"><span data-stu-id="b90fc-119">An abstract base class from which all concrete adorner implementations inherit.</span></span>|
|<xref:System.Windows.Documents.AdornerLayer>|<span data-ttu-id="b90fc-120">装飾される 1 つ以上の要素に対する、装飾のレンダリング層を表すクラス。</span><span class="sxs-lookup"><span data-stu-id="b90fc-120">A class representing a rendering layer for the adorner(s) of one or more adorned elements.</span></span>|
|<xref:System.Windows.Documents.AdornerDecorator>|<span data-ttu-id="b90fc-121">1 つの装飾層を要素のコレクションに関連付けることを可能にするクラス。</span><span class="sxs-lookup"><span data-stu-id="b90fc-121">A class that enables an adorner layer to be associated with a collection of elements.</span></span>|

## <a name="implementing-a-custom-adorner"></a><span data-ttu-id="b90fc-122">カスタム装飾の実装</span><span class="sxs-lookup"><span data-stu-id="b90fc-122">Implementing a Custom Adorner</span></span>

<span data-ttu-id="b90fc-123">[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] が提供する装飾フレームワークは、カスタム装飾の作成をサポートすることを主な目的としています。</span><span class="sxs-lookup"><span data-stu-id="b90fc-123">The adorners framework provided by [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] is intended primarily to support the creation of custom adorners.</span></span> <span data-ttu-id="b90fc-124">カスタム装飾は、抽象クラス <xref:System.Windows.Documents.Adorner> から継承されるクラスを実装することによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="b90fc-124">A custom adorner is created by implementing a class that inherits from the abstract <xref:System.Windows.Documents.Adorner> class.</span></span>

> [!NOTE]
> <span data-ttu-id="b90fc-125"><xref:System.Windows.Documents.Adorner> の親は、装飾される要素ではなく、<xref:System.Windows.Documents.Adorner> をレンダリングする <xref:System.Windows.Documents.AdornerLayer> です。</span><span class="sxs-lookup"><span data-stu-id="b90fc-125">The parent of an <xref:System.Windows.Documents.Adorner> is the <xref:System.Windows.Documents.AdornerLayer> that renders the <xref:System.Windows.Documents.Adorner>, not the element being adorned.</span></span>

<span data-ttu-id="b90fc-126">次の例では、簡単な装飾を実装するクラスを示します。</span><span class="sxs-lookup"><span data-stu-id="b90fc-126">The following example shows a class that implements a simple adorner.</span></span> <span data-ttu-id="b90fc-127">この例の装飾では、<xref:System.Windows.UIElement> の四隅が円で装飾されるだけです。</span><span class="sxs-lookup"><span data-stu-id="b90fc-127">The example adorner simply adorns the corners of a <xref:System.Windows.UIElement> with circles.</span></span>

[!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
[!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]
  
<span data-ttu-id="b90fc-128">次の図に示すのは、<xref:System.Windows.Controls.TextBox> に適用された SimpleCircleAdorner です。</span><span class="sxs-lookup"><span data-stu-id="b90fc-128">The following image shows the SimpleCircleAdorner applied to a <xref:System.Windows.Controls.TextBox>:</span></span>

![装飾されたテキスト ボックスを示すスクリーンショット。](./media/adorners-overview/simplecircleadorner-textbox.png)

## <a name="rendering-behavior-for-adorners"></a><span data-ttu-id="b90fc-130">装飾のレンダリング動作</span><span class="sxs-lookup"><span data-stu-id="b90fc-130">Rendering Behavior for Adorners</span></span>

<span data-ttu-id="b90fc-131">装飾自体にはレンダリング動作が備わっていないので、装飾のレンダリングは装飾の実装側の責任で行う必要がある点に、注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="b90fc-131">It is important to note that adorners do not include any inherent rendering behavior; ensuring that an adorner renders is the responsibility of the adorner implementer.</span></span> <span data-ttu-id="b90fc-132">レンダリング動作を実装する一般的な方法は、(この例で示すように) <xref:System.Windows.UIElement.OnRender%2A> メソッドをオーバーライドし、1 つまたは複数の <xref:System.Windows.Media.DrawingContext> オブジェクトを使用して、必要に応じて装飾のビジュアルをレンダリングすることです。</span><span class="sxs-lookup"><span data-stu-id="b90fc-132">A common way of implementing rendering behavior is to override the <xref:System.Windows.UIElement.OnRender%2A> method and use one or more <xref:System.Windows.Media.DrawingContext> objects to render the adorner's visuals as needed (as shown in the example above).</span></span>

> [!NOTE]
> <span data-ttu-id="b90fc-133">装飾層に配置されているすべてのものは、設定した他のすべてのスタイルの上に描画されます。</span><span class="sxs-lookup"><span data-stu-id="b90fc-133">Anything placed in the adorner layer is rendered on top of the rest of any styles you have set.</span></span> <span data-ttu-id="b90fc-134">つまり、装飾は常に視覚的に最上位にあり、z オーダーを使用してオーバーライドすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b90fc-134">In other words, adorners are always visually on top and cannot be overridden using z-order.</span></span>

## <a name="events-and-hit-testing"></a><span data-ttu-id="b90fc-135">イベントおよびヒット テスト</span><span class="sxs-lookup"><span data-stu-id="b90fc-135">Events and Hit Testing</span></span>

<span data-ttu-id="b90fc-136">他のすべての <xref:System.Windows.FrameworkElement> と同様に、装飾は入力イベントを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="b90fc-136">Adorners receive input events just like any other <xref:System.Windows.FrameworkElement>.</span></span>  <span data-ttu-id="b90fc-137">装飾は、それが装飾する要素よりも常に高い z オーダーを持つため、下位にある装飾対象の要素に向けられた入力イベント (<xref:System.Windows.UIElement.Drop> または <xref:System.Windows.UIElement.MouseMove> など) であっても受け取ります。</span><span class="sxs-lookup"><span data-stu-id="b90fc-137">Because an adorner always has a higher z-order than the element it adorns, the adorner receives input events (such as <xref:System.Windows.UIElement.Drop> or <xref:System.Windows.UIElement.MouseMove>) that may be intended for the underlying adorned element.</span></span>  <span data-ttu-id="b90fc-138">装飾は、特定の入力イベントをリッスンし、それらのイベントを再度発生させることによって、下位にある装飾対象の要素に渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="b90fc-138">An adorner can listen for certain input events and pass these on to the underlying adorned element by re-raising the event.</span></span>

<span data-ttu-id="b90fc-139">装飾の下にある要素に対するヒット テストをパススルーするには、その装飾でヒット テストの <xref:System.Windows.UIElement.IsHitTestVisible%2A> プロパティを **false** に設定します。</span><span class="sxs-lookup"><span data-stu-id="b90fc-139">To enable pass-through hit testing of elements under an adorner, set the hit test <xref:System.Windows.UIElement.IsHitTestVisible%2A> property to **false** on the adorner.</span></span>  <span data-ttu-id="b90fc-140">ヒット テストの詳細については、「[ビジュアル層でのヒット テスト](../graphics-multimedia/hit-testing-in-the-visual-layer.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b90fc-140">For more information about hit testing, see [Hit Testing in the Visual Layer](../graphics-multimedia/hit-testing-in-the-visual-layer.md).</span></span>

## <a name="adorning-a-single-uielement"></a><span data-ttu-id="b90fc-141">単一の UIElement の装飾</span><span class="sxs-lookup"><span data-stu-id="b90fc-141">Adorning a Single UIElement</span></span>

<span data-ttu-id="b90fc-142">特定の <xref:System.Windows.UIElement> に装飾をバインドするには、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="b90fc-142">To bind an adorner to a particular <xref:System.Windows.UIElement>, follow these steps:</span></span>

1. <span data-ttu-id="b90fc-143">静的メソッド <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> を呼び出して、装飾対象の <xref:System.Windows.UIElement> の <xref:System.Windows.Documents.AdornerLayer> オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="b90fc-143">Call the static method <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> to get an <xref:System.Windows.Documents.AdornerLayer> object for the <xref:System.Windows.UIElement> to be adorned.</span></span> <span data-ttu-id="b90fc-144"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> では、指定した <xref:System.Windows.UIElement> を起点としてビジュアル ツリーが上方に探索され、最初に見つかった装飾層が返されます。</span><span class="sxs-lookup"><span data-stu-id="b90fc-144"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> walks up the visual tree, starting at the specified <xref:System.Windows.UIElement>, and returns the first adorner layer it finds.</span></span> <span data-ttu-id="b90fc-145">(装飾層が見つからない場合、メソッドにより null が返されます)。</span><span class="sxs-lookup"><span data-stu-id="b90fc-145">(If no adorner layers are found, the method returns null.)</span></span>

2. <span data-ttu-id="b90fc-146"><xref:System.Windows.Documents.AdornerLayer.Add%2A> メソッドを呼び出し、装飾を対象の <xref:System.Windows.UIElement> にバインドします。</span><span class="sxs-lookup"><span data-stu-id="b90fc-146">Call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind the adorner to the target <xref:System.Windows.UIElement>.</span></span>

 <span data-ttu-id="b90fc-147">次の例では、SimpleCircleAdorner (上図参照) を *myTextBox* という名前の <xref:System.Windows.Controls.TextBox> にバインドします。</span><span class="sxs-lookup"><span data-stu-id="b90fc-147">The following example binds a SimpleCircleAdorner (shown above) to a <xref:System.Windows.Controls.TextBox> named *myTextBox*:</span></span>

 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]

> [!NOTE]
> <span data-ttu-id="b90fc-148">[!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] を使用して、装飾を別の要素にバインドする方法は、現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b90fc-148">Using [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] to bind an adorner to another element is currently not supported.</span></span>

## <a name="adorning-the-children-of-a-panel"></a><span data-ttu-id="b90fc-149">パネルの子の装飾</span><span class="sxs-lookup"><span data-stu-id="b90fc-149">Adorning the Children of a Panel</span></span>

<span data-ttu-id="b90fc-150"><xref:System.Windows.Controls.Panel> の子に装飾をバインドするには、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="b90fc-150">To bind an adorner to the children of a <xref:System.Windows.Controls.Panel>, follow these steps:</span></span>

1. <span data-ttu-id="b90fc-151">`static` メソッド <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> を呼び出し、子が装飾対象となる要素の装飾層を検出します。</span><span class="sxs-lookup"><span data-stu-id="b90fc-151">Call the `static` method <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> to find an adorner layer for the element whose children are to be adorned.</span></span>

2. <span data-ttu-id="b90fc-152">親要素の子を列挙し、<xref:System.Windows.Documents.AdornerLayer.Add%2A> メソッドを呼び出して、装飾を各子要素にバインドします。</span><span class="sxs-lookup"><span data-stu-id="b90fc-152">Enumerate through the children of the parent element and call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind an adorner to each child element.</span></span>

<span data-ttu-id="b90fc-153">次の例では、SimpleCircleAdorner (上図参照) を *myStackPanel* という名前の <xref:System.Windows.Controls.StackPanel> の子にバインドします。</span><span class="sxs-lookup"><span data-stu-id="b90fc-153">The following example binds a SimpleCircleAdorner (shown above) to the children of a <xref:System.Windows.Controls.StackPanel> named *myStackPanel*:</span></span>

[!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
[!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]

## <a name="see-also"></a><span data-ttu-id="b90fc-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="b90fc-154">See also</span></span>

- <xref:System.Windows.Media.AdornerHitTestResult>
- [<span data-ttu-id="b90fc-155">WPF での図形と基本描画の概要</span><span class="sxs-lookup"><span data-stu-id="b90fc-155">Shapes and Basic Drawing in WPF Overview</span></span>](../graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
- [<span data-ttu-id="b90fc-156">イメージ、描画、およびビジュアルによる塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="b90fc-156">Painting with Images, Drawings, and Visuals</span></span>](../graphics-multimedia/painting-with-images-drawings-and-visuals.md)
- [<span data-ttu-id="b90fc-157">Drawing オブジェクトの概要</span><span class="sxs-lookup"><span data-stu-id="b90fc-157">Drawing Objects Overview</span></span>](../graphics-multimedia/drawing-objects-overview.md)
- [<span data-ttu-id="b90fc-158">方法トピック</span><span class="sxs-lookup"><span data-stu-id="b90fc-158">How-to Topics</span></span>](adorners-how-to-topics.md)
