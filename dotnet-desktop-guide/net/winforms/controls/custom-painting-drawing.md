---
title: コントロールのカスタム ペインティング
description: Windows フォーム用の .NET の OnPaint メソッドと Paint イベントを使用して、コントロールの外観をカスタマイズする方法について説明します。
ms.date: 10/26/2020
ms.topic: overview
dev_langs:
- csharp
- vb
f1_keywords:
- OnPaint
helpviewer_keywords:
- controls [Windows Forms], user controls
- controls [Windows Forms], types of
- composite controls [Windows Forms]
- extended controls [Windows Forms]
- controls [Windows Forms], extended
- user controls [Windows Forms]
- custom controls [Windows Forms]
- controls [Windows Forms], composite
ms.openlocfilehash: 8d9775c02addb68cc962cdc2e4bf2d1baa6ab2a1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96942278"
---
# <a name="painting-and-drawing-on-controls-windows-forms-net"></a><span data-ttu-id="45a7f-103">コントロールのペインティングと描画 (.NET 用の Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="45a7f-103">Painting and drawing on controls (Windows Forms .NET)</span></span>

<span data-ttu-id="45a7f-104">コントロールのカスタム ペインティングは、Windows フォームによって簡単に実行できる多数の複雑なタスクの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="45a7f-104">Custom painting of controls is one of the many complicated tasks made easy by Windows Forms.</span></span> <span data-ttu-id="45a7f-105">カスタム コントロールを作成する場合、コントロールのグラフィカルな外観を処理するために使用できる多くのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="45a7f-105">When authoring a custom control, you have many options available to handle your control's graphical appearance.</span></span> <span data-ttu-id="45a7f-106">[カスタム コントロール](custom.md#custom-controls)、つまり <xref:System.Windows.Forms.Control> から継承するコントロールを作成する場合は、そのグラフィカル表現をレンダリングするコードを用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45a7f-106">If you're authoring a [custom control](custom.md#custom-controls), that is, a control that inherits from <xref:System.Windows.Forms.Control>, you must provide code to render its graphical representation.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

<span data-ttu-id="45a7f-107">[複合コントロール](custom.md#composite-controls)、つまり <xref:System.Windows.Forms.UserControl> または既存の Windows フォーム コントロールのいずれかを継承するコントロールを作成する場合は、標準のグラフィカル表現をオーバーライドし、独自のグラフィックス コードを提供することができます。</span><span class="sxs-lookup"><span data-stu-id="45a7f-107">If you're creating a [composite control](custom.md#composite-controls), that is a control that inherits from <xref:System.Windows.Forms.UserControl> or one of the existing Windows Forms controls, you may override the standard graphical representation and provide your own graphics code.</span></span>

<span data-ttu-id="45a7f-108">新しいコントロールを作成せずに既存のコントロールのカスタム レンダリングを提供する場合は、オプションがいっそう限られたものになります。</span><span class="sxs-lookup"><span data-stu-id="45a7f-108">If you want to provide custom rendering for an existing control without creating a new control, your options become more limited.</span></span> <span data-ttu-id="45a7f-109">ただし、それでもコントロールとアプリケーションに対して、広い範囲のグラフィカルの可能性があります。</span><span class="sxs-lookup"><span data-stu-id="45a7f-109">However, there are still a wide range of graphical possibilities for your controls and applications.</span></span>

<span data-ttu-id="45a7f-110">コントロールのレンダリングには、次の要素が関係します。</span><span class="sxs-lookup"><span data-stu-id="45a7f-110">The following elements are involved in control rendering:</span></span>

- <span data-ttu-id="45a7f-111">基底クラス <xref:System.Windows.Forms.Control?displayProperty=nameWithType> によって提供される描画機能。</span><span class="sxs-lookup"><span data-stu-id="45a7f-111">The drawing functionality provided by the base class <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span>
- <span data-ttu-id="45a7f-112">GDI グラフィックス ライブラリの必須要素。</span><span class="sxs-lookup"><span data-stu-id="45a7f-112">The essential elements of the GDI graphics library.</span></span>
- <span data-ttu-id="45a7f-113">描画領域のジオメトリ。</span><span class="sxs-lookup"><span data-stu-id="45a7f-113">The geometry of the drawing region.</span></span>
- <span data-ttu-id="45a7f-114">グラフィックス リソースを解放する手順。</span><span class="sxs-lookup"><span data-stu-id="45a7f-114">The procedure for freeing graphics resources.</span></span>

## <a name="drawing-provided-by-control"></a><span data-ttu-id="45a7f-115">コントロールによって提供される描画</span><span class="sxs-lookup"><span data-stu-id="45a7f-115">Drawing provided by control</span></span>

<span data-ttu-id="45a7f-116">基底クラス <xref:System.Windows.Forms.Control> の <xref:System.Windows.Forms.Control.Paint> イベントを通じて描画機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="45a7f-116">The base class <xref:System.Windows.Forms.Control> provides drawing functionality through its <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="45a7f-117">表示を更新する必要があるたびに、コントロールによって <xref:System.Windows.Forms.Control.Paint> イベントが生成されます。</span><span class="sxs-lookup"><span data-stu-id="45a7f-117">A control raises the <xref:System.Windows.Forms.Control.Paint> event whenever it needs to update its display.</span></span> <span data-ttu-id="45a7f-118">.NET でのイベントの詳細については、「[イベントの処理と発生](/dotnet/standard/events/index)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45a7f-118">For more information about events in the .NET, see [Handling and raising events](/dotnet/standard/events/index).</span></span>

<span data-ttu-id="45a7f-119"><xref:System.Windows.Forms.Control.Paint> イベントのイベント データ クラスである <xref:System.Windows.Forms.PaintEventArgs> により、コントロールの描画に必要なデータである、グラフィックス オブジェクトへのハンドルと、描画する領域を表す四角形が保持されます。</span><span class="sxs-lookup"><span data-stu-id="45a7f-119">The event data class for the <xref:System.Windows.Forms.Control.Paint> event, <xref:System.Windows.Forms.PaintEventArgs>, holds the data needed for drawing a control - a handle to a graphics object and a rectangle that represents the region to draw in.</span></span>

```csharp
public class PaintEventArgs : EventArgs, IDisposable
{

    public System.Drawing.Rectangle ClipRectangle {get;}
    public System.Drawing.Graphics Graphics {get;}

    // Other properties and methods.
}
```

```vb
Public Class PaintEventArgs
    Inherits EventArgs
    Implements IDisposable

    Public ReadOnly Property ClipRectangle As System.Drawing.Rectangle
    Public ReadOnly Property Graphics As System.Drawing.Graphics

    ' Other properties and methods.
End Class
```

<span data-ttu-id="45a7f-120"><xref:System.Drawing.Graphics> は、描画機能をカプセル化するマネージド クラスです (この記事の GDI に関する説明で後述します)。</span><span class="sxs-lookup"><span data-stu-id="45a7f-120"><xref:System.Drawing.Graphics> is a managed class that encapsulates drawing functionality, as described in the discussion of GDI later in this article.</span></span> <span data-ttu-id="45a7f-121"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> は <xref:System.Drawing.Rectangle> 構造体のインスタンスであり、コントロールで描画できる領域を定義します。</span><span class="sxs-lookup"><span data-stu-id="45a7f-121">The <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> is an instance of the <xref:System.Drawing.Rectangle> structure and defines the available area in which a control can draw.</span></span> <span data-ttu-id="45a7f-122">コントロール開発者は、コントロールの <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> プロパティを使用して、<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> を計算できます (この記事のジオメトリに関する説明で後述します)。</span><span class="sxs-lookup"><span data-stu-id="45a7f-122">A control developer can compute the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> using the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> property of a control, as described in the discussion of geometry later in this article.</span></span>

### <a name="onpaint"></a><span data-ttu-id="45a7f-123">OnPaint</span><span class="sxs-lookup"><span data-stu-id="45a7f-123">OnPaint</span></span>

<span data-ttu-id="45a7f-124">コントロールは <xref:System.Windows.Forms.Control> から継承する <xref:System.Windows.Forms.Control.OnPaint%2A> メソッドをオーバーライドすることにより、レンダリング ロジックを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45a7f-124">A control must provide rendering logic by overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method that it inherits from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="45a7f-125"><xref:System.Windows.Forms.Control.OnPaint%2A> は、渡された <xref:System.Windows.Forms.PaintEventArgs> インスタンスの <xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A> および <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> プロパティを通じて、グラフィックス オブジェクトと描画対象の四角形にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="45a7f-125"><xref:System.Windows.Forms.Control.OnPaint%2A> gets access to a graphics object and a rectangle to draw in through the <xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A> and the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> properties of the <xref:System.Windows.Forms.PaintEventArgs> instance passed to it.</span></span>

<span data-ttu-id="45a7f-126">次のコードでは、`System.Drawing` 名前空間を使用しています。</span><span class="sxs-lookup"><span data-stu-id="45a7f-126">The following code uses the `System.Drawing` namespace:</span></span>

:::code language="csharp" source="./snippets/custom-painting-drawing/cs/UserControl1.cs" id="OnPaintMethod":::

:::code language="vb" source="./snippets/custom-painting-drawing/vb/UserControl1.vb" id="OnPaintMethod":::

<span data-ttu-id="45a7f-127">基底クラス <xref:System.Windows.Forms.Control> の <xref:System.Windows.Forms.Control.OnPaint%2A> メソッドによって描画機能は実装されず、<xref:System.Windows.Forms.Control.Paint> イベントに登録されているイベント デリゲートを単に呼び出すだけです。</span><span class="sxs-lookup"><span data-stu-id="45a7f-127">The <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base <xref:System.Windows.Forms.Control> class doesn't implement any drawing functionality but merely invokes the event delegates that are registered with the <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="45a7f-128"><xref:System.Windows.Forms.Control.OnPaint%2A> をオーバーライドするときは、登録されているデリゲートで <xref:System.Windows.Forms.Control.Paint> イベントを受け取ることができるように、通常、基底クラスの <xref:System.Windows.Forms.Control.OnPaint%2A> メソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="45a7f-128">When you override <xref:System.Windows.Forms.Control.OnPaint%2A>, you should typically invoke the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class so that registered delegates receive the <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="45a7f-129">ただし、画面全体を描画するコントロールの場合は、基底クラスの <xref:System.Windows.Forms.Control.OnPaint%2A> を呼び出すことはできません。これによって、ちらつきが生じるためです。</span><span class="sxs-lookup"><span data-stu-id="45a7f-129">However, controls that paint their entire surface shouldn't invoke the base class's <xref:System.Windows.Forms.Control.OnPaint%2A>, as this introduces flicker.</span></span>

> [!NOTE]
> <span data-ttu-id="45a7f-130">コントロールから直接 <xref:System.Windows.Forms.Control.OnPaint%2A> を呼び出さないでください。代わりに、<xref:System.Windows.Forms.Control.Invalidate%2A> メソッド (<xref:System.Windows.Forms.Control> から継承)、または <xref:System.Windows.Forms.Control.Invalidate%2A> を呼び出す他のメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="45a7f-130">Don't invoke <xref:System.Windows.Forms.Control.OnPaint%2A> directly from your control; instead, invoke the <xref:System.Windows.Forms.Control.Invalidate%2A> method (inherited from <xref:System.Windows.Forms.Control>) or some other method that invokes <xref:System.Windows.Forms.Control.Invalidate%2A>.</span></span> <span data-ttu-id="45a7f-131"><xref:System.Windows.Forms.Control.Invalidate%2A> メソッドによって、<xref:System.Windows.Forms.Control.OnPaint%2A> が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="45a7f-131">The <xref:System.Windows.Forms.Control.Invalidate%2A> method in turn invokes <xref:System.Windows.Forms.Control.OnPaint%2A>.</span></span> <span data-ttu-id="45a7f-132"><xref:System.Windows.Forms.Control.Invalidate%2A> メソッドはオーバーロードされ、<xref:System.Windows.Forms.Control.Invalidate%2A> `e` に指定された引数に応じて、その画面領域の一部または全体が再描画されます。</span><span class="sxs-lookup"><span data-stu-id="45a7f-132">The <xref:System.Windows.Forms.Control.Invalidate%2A> method is overloaded, and, depending on the arguments supplied to <xref:System.Windows.Forms.Control.Invalidate%2A> `e`, redraws either some or all of its screen area.</span></span>

<span data-ttu-id="45a7f-133">コントロールが最初に描画されるときと、更新されるたびに、コントロールの <xref:System.Windows.Forms.Control.OnPaint%2A> メソッドのコードが実行されます。</span><span class="sxs-lookup"><span data-stu-id="45a7f-133">The code in the <xref:System.Windows.Forms.Control.OnPaint%2A> method of your control will execute when the control is first drawn, and whenever it is refreshed.</span></span> <span data-ttu-id="45a7f-134">サイズが変更されるたびにコントロールが確実に再描画されるようにするには、コントロールのコンストラクターに次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="45a7f-134">To ensure that your control is redrawn every time it is resized, add the following line to the constructor of your control:</span></span>

```csharp
SetStyle(ControlStyles.ResizeRedraw, true);
```

```vb
SetStyle(ControlStyles.ResizeRedraw, True)
```

### <a name="onpaintbackground"></a><span data-ttu-id="45a7f-135">OnPaintBackground</span><span class="sxs-lookup"><span data-stu-id="45a7f-135">OnPaintBackground</span></span>

<span data-ttu-id="45a7f-136">基底クラス <xref:System.Windows.Forms.Control> により、描画に便利なもう 1 つのメソッド <xref:System.Windows.Forms.Control.OnPaintBackground%2A> が定義されています。</span><span class="sxs-lookup"><span data-stu-id="45a7f-136">The base <xref:System.Windows.Forms.Control> class defines another method that is useful for drawing, the <xref:System.Windows.Forms.Control.OnPaintBackground%2A> method.</span></span>

```csharp
protected virtual void OnPaintBackground(PaintEventArgs e);
```

```vb
Protected Overridable Sub OnPaintBackground(e As PaintEventArgs)
```

<span data-ttu-id="45a7f-137"><xref:System.Windows.Forms.Control.OnPaintBackground%2A> を使用すると、ウィンドウの背景 (およびそのシェイプ) が描画され、高速な処理が保証されます。一方、<xref:System.Windows.Forms.Control.OnPaint%2A> を使用すると、細部が描画され、個々の描画要求が、再描画の必要なすべての領域をカバーする 1 つの <xref:System.Windows.Forms.Control.Paint> イベントに結合されるため、処理が遅くなる場合があります。</span><span class="sxs-lookup"><span data-stu-id="45a7f-137"><xref:System.Windows.Forms.Control.OnPaintBackground%2A> paints the background (and in that way, the shape) of the window and is guaranteed to be fast, while <xref:System.Windows.Forms.Control.OnPaint%2A> paints the details and might be slower because individual paint requests are combined into one <xref:System.Windows.Forms.Control.Paint> event that covers all areas that have to be redrawn.</span></span> <span data-ttu-id="45a7f-138">たとえば、コントロールのグラデーション カラーの背景を描画する必要がある場合は、<xref:System.Windows.Forms.Control.OnPaintBackground%2A> を呼び出す必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="45a7f-138">You might want to invoke the <xref:System.Windows.Forms.Control.OnPaintBackground%2A> if, for instance, you want to draw a gradient-colored background for your control.</span></span>

<span data-ttu-id="45a7f-139"><xref:System.Windows.Forms.Control.OnPaintBackground%2A> にはイベントのような命名法があり、`OnPaint` メソッドと同じ引数を受け取りますが、`OnPaintBackground` は本当のイベント メソッドではありません。</span><span class="sxs-lookup"><span data-stu-id="45a7f-139">While <xref:System.Windows.Forms.Control.OnPaintBackground%2A> has an event-like nomenclature and takes the same argument as the `OnPaint` method, `OnPaintBackground` is not a true event method.</span></span> <span data-ttu-id="45a7f-140">`PaintBackground` イベントは存在せず、`OnPaintBackground` でイベント デリゲートは呼び出されません。</span><span class="sxs-lookup"><span data-stu-id="45a7f-140">There is no `PaintBackground` event and `OnPaintBackground` doesn't invoke event delegates.</span></span> <span data-ttu-id="45a7f-141">`OnPaintBackground` メソッドをオーバーライドするとき、派生クラスで基底クラスの `OnPaintBackground` メソッドを呼び出す必要はありません。</span><span class="sxs-lookup"><span data-stu-id="45a7f-141">When overriding the `OnPaintBackground` method, a derived class is not required to invoke the `OnPaintBackground` method of its base class.</span></span>

## <a name="gdi-basics"></a><span data-ttu-id="45a7f-142">GDI+ の基礎</span><span class="sxs-lookup"><span data-stu-id="45a7f-142">GDI+ Basics</span></span>

<span data-ttu-id="45a7f-143"><xref:System.Drawing.Graphics> クラスには、円、三角形、円弧、楕円などのさまざまなシェイプを描画するためのメソッドと、テキストを表示するためのメソッドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="45a7f-143">The <xref:System.Drawing.Graphics> class provides methods for drawing various shapes such as circles, triangles, arcs, and ellipses, and methods for displaying text.</span></span> <span data-ttu-id="45a7f-144"><xref:System.Drawing?displayProperty=nameWithType> 名前空間には、シェイプ (円、四角形、円弧など)、色、フォント、ブラシなどのグラフィックス要素をカプセル化する名前空間とクラスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="45a7f-144">The <xref:System.Drawing?displayProperty=nameWithType> namespace contains namespaces and classes that encapsulate graphics elements such as shapes (circles, rectangles, arcs, and others), colors, fonts, brushes, and so on.</span></span><!-- TODO  For more information about GDI, see [Using Managed Graphics Classes](../advanced/using-managed-graphics-classes.md).-->

## <a name="geometry-of-the-drawing-region"></a><span data-ttu-id="45a7f-145">描画領域のジオメトリ</span><span class="sxs-lookup"><span data-stu-id="45a7f-145">Geometry of the Drawing Region</span></span>

<span data-ttu-id="45a7f-146">コントロールの <xref:System.Windows.Forms.Control.ClientRectangle%2A> プロパティにより、ユーザーの画面上でコントロールが使用できる四角形の領域が指定されています。一方、<xref:System.Windows.Forms.PaintEventArgs> の <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> プロパティにより、描画される領域が指定されます。</span><span class="sxs-lookup"><span data-stu-id="45a7f-146">The <xref:System.Windows.Forms.Control.ClientRectangle%2A> property of a control specifies the rectangular region available to the control on the user's screen, while the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> property of <xref:System.Windows.Forms.PaintEventArgs> specifies the area that is painted.</span></span> <span data-ttu-id="45a7f-147">コントロールの表示の小さいセクションが変更された場合のように、コントロールで使用可能な領域の一部だけを描画することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="45a7f-147">A control might need to paint only a portion of its available area, as is the case when a small section of the control's display changes.</span></span> <span data-ttu-id="45a7f-148">そのような状況では、コントロール開発者は、実際に描画する四角形を計算し、それを <xref:System.Windows.Forms.Control.Invalidate%2A> に渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="45a7f-148">In those situations, a control developer must compute the actual rectangle to draw in and pass that to <xref:System.Windows.Forms.Control.Invalidate%2A>.</span></span> <span data-ttu-id="45a7f-149">引数として <xref:System.Drawing.Rectangle> または <xref:System.Drawing.Region> を受け取る <xref:System.Windows.Forms.Control.Invalidate%2A> のオーバーロードされたバージョンにより、その引数を使用して、<xref:System.Windows.Forms.PaintEventArgs> の <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> プロパティが生成されます。</span><span class="sxs-lookup"><span data-stu-id="45a7f-149">The overloaded versions of <xref:System.Windows.Forms.Control.Invalidate%2A> that take a <xref:System.Drawing.Rectangle> or <xref:System.Drawing.Region> as an argument use that argument to generate the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> property of <xref:System.Windows.Forms.PaintEventArgs>.</span></span>

## <a name="freeing-graphics-resources"></a><span data-ttu-id="45a7f-150">グラフィックス リソースの解放</span><span class="sxs-lookup"><span data-stu-id="45a7f-150">Freeing Graphics Resources</span></span>

<span data-ttu-id="45a7f-151">グラフィックス オブジェクトは、システム リソースを使用するため、コストが高くなります。</span><span class="sxs-lookup"><span data-stu-id="45a7f-151">Graphics objects are expensive because they use system resources.</span></span> <span data-ttu-id="45a7f-152">そのようなオブジェクトには、<xref:System.Drawing.Graphics?displayProperty=nameWithType> クラスのインスタンスと、<xref:System.Drawing.Brush?displayProperty=nameWithType>、<xref:System.Drawing.Pen?displayProperty=nameWithType>、およびその他のグラフィックス クラスのインスタンスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="45a7f-152">Such objects include instances of the <xref:System.Drawing.Graphics?displayProperty=nameWithType> class and instances of <xref:System.Drawing.Brush?displayProperty=nameWithType>, <xref:System.Drawing.Pen?displayProperty=nameWithType>, and other graphics classes.</span></span> <span data-ttu-id="45a7f-153">必要なときにだけグラフィックス リソースを作成し、使い終わったらすぐに解放することが重要です。</span><span class="sxs-lookup"><span data-stu-id="45a7f-153">It's important that you create a graphics resource only when you need it and release it soon as you're finished using it.</span></span> <span data-ttu-id="45a7f-154"><xref:System.IDisposable> インターフェイスが実装されている型のインスタンスを作成する場合は、終了したらその <xref:System.IDisposable.Dispose%2A> メソッドを呼び出してリソースを解放します。</span><span class="sxs-lookup"><span data-stu-id="45a7f-154">If you create an instance of a type that implements the <xref:System.IDisposable> interface, call its <xref:System.IDisposable.Dispose%2A> method when you're finished with it to free resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="45a7f-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="45a7f-155">See also</span></span>

- [<span data-ttu-id="45a7f-156">カスタム コントロールの種類</span><span class="sxs-lookup"><span data-stu-id="45a7f-156">Types of custom controls</span></span>](custom.md)
