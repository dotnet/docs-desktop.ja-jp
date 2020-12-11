---
title: コントロールをレンダリングする
ms.date: 03/30/2017
ms.topic: overview
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], rendering
- OnPaintBackground method [Windows Forms], invoking in Windows Forms custom controls
- custom controls [Windows Forms], graphics resources
- custom controls [Windows Forms], invalidation and painting
ms.assetid: aae8e1e6-4786-432b-a15e-f4c44760d302
ms.openlocfilehash: 86e219723dde8c10a8cc0d4ee7bdf149cde399bf
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982472"
---
# <a name="rendering-a-windows-forms-control"></a><span data-ttu-id="3c82a-102">Windows フォーム コントロールのレンダリング</span><span class="sxs-lookup"><span data-stu-id="3c82a-102">Rendering a Windows Forms Control</span></span>

<span data-ttu-id="3c82a-103">レンダリングとは、ユーザーの画面で視覚的表現を作成するプロセスを指します。</span><span class="sxs-lookup"><span data-stu-id="3c82a-103">Rendering refers to the process of creating a visual representation on a user's screen.</span></span> <span data-ttu-id="3c82a-104">Windows フォームは、GDI (新しい Windows グラフィックスライブラリ) を使用してレンダリングを行います。</span><span class="sxs-lookup"><span data-stu-id="3c82a-104">Windows Forms uses GDI (the new Windows graphics library) for rendering.</span></span> <span data-ttu-id="3c82a-105">GDI へのアクセスを提供するマネージクラスは、 <xref:System.Drawing?displayProperty=nameWithType> 名前空間とその副名前空間にあります。</span><span class="sxs-lookup"><span data-stu-id="3c82a-105">The managed classes that provide access to GDI are in the <xref:System.Drawing?displayProperty=nameWithType> namespace and its subnamespaces.</span></span>  
  
 <span data-ttu-id="3c82a-106">コントロールのレンダリングには、次の要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3c82a-106">The following elements are involved in control rendering:</span></span>  
  
- <span data-ttu-id="3c82a-107">基本クラスによって提供される描画機能 <xref:System.Windows.Forms.Control?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="3c82a-107">The drawing functionality provided by the base class <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="3c82a-108">GDI グラフィックスライブラリの重要な要素。</span><span class="sxs-lookup"><span data-stu-id="3c82a-108">The essential elements of the GDI graphics library.</span></span>  
  
- <span data-ttu-id="3c82a-109">描画領域のジオメトリ。</span><span class="sxs-lookup"><span data-stu-id="3c82a-109">The geometry of the drawing region.</span></span>  
  
- <span data-ttu-id="3c82a-110">グラフィックスリソースを解放する手順。</span><span class="sxs-lookup"><span data-stu-id="3c82a-110">The procedure for freeing graphics resources.</span></span>  
  
## <a name="drawing-functionality-provided-by-control"></a><span data-ttu-id="3c82a-111">コントロールによって提供される描画機能</span><span class="sxs-lookup"><span data-stu-id="3c82a-111">Drawing Functionality Provided by Control</span></span>  

 <span data-ttu-id="3c82a-112">基底クラスは、 <xref:System.Windows.Forms.Control> イベントを通じて描画機能を提供し <xref:System.Windows.Forms.Control.Paint> ます。</span><span class="sxs-lookup"><span data-stu-id="3c82a-112">The base class <xref:System.Windows.Forms.Control> provides drawing functionality through its <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="3c82a-113">コントロールは、 <xref:System.Windows.Forms.Control.Paint> 表示を更新する必要があるときに常にイベントを発生させます。</span><span class="sxs-lookup"><span data-stu-id="3c82a-113">A control raises the <xref:System.Windows.Forms.Control.Paint> event whenever it needs to update its display.</span></span> <span data-ttu-id="3c82a-114">.NET Framework のイベントの詳細については、「 [イベントの処理と発生](/dotnet/standard/events/index)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c82a-114">For more information about events in the .NET Framework, see [Handling and Raising Events](/dotnet/standard/events/index).</span></span>  
  
 <span data-ttu-id="3c82a-115">イベントのイベントデータクラスは、 <xref:System.Windows.Forms.Control.Paint> <xref:System.Windows.Forms.PaintEventArgs> コントロールを描画するために必要なデータ (グラフィックスオブジェクトへのハンドル、および描画する領域を表す四角形オブジェクトを保持します) を保持します。</span><span class="sxs-lookup"><span data-stu-id="3c82a-115">The event data class for the <xref:System.Windows.Forms.Control.Paint> event, <xref:System.Windows.Forms.PaintEventArgs>, holds the data needed for drawing a control — a handle to a graphics object and a rectangle object that represents the region to draw in.</span></span> <span data-ttu-id="3c82a-116">これらのオブジェクトは、次のコードフラグメントに太字で示されています。</span><span class="sxs-lookup"><span data-stu-id="3c82a-116">These objects are shown in bold in the following code fragment.</span></span>  
  
```vb  
Public Class PaintEventArgs  
   Inherits EventArgs  
   Implements IDisposable  
  
   Public ReadOnly Property ClipRectangle() As System.Drawing.Rectangle  
      ...  
   End Property  
  
   Public ReadOnly Property Graphics() As System.Drawing.Graphics  
      ...  
   End Property  
   ' Other properties and methods.  
   ...  
End Class  
```  
  
```csharp  
public class PaintEventArgs : EventArgs, IDisposable {  
public System.Drawing.Rectangle ClipRectangle {get;}  
public System.Drawing.Graphics Graphics {get;}  
// Other properties and methods.  
...  
}  
```  
  
 <span data-ttu-id="3c82a-117"><xref:System.Drawing.Graphics> は、このトピックの後半の「GDI の説明」で説明されているように、描画機能をカプセル化するマネージクラスです。</span><span class="sxs-lookup"><span data-stu-id="3c82a-117"><xref:System.Drawing.Graphics> is a managed class that encapsulates drawing functionality, as described in the discussion of GDI later in this topic.</span></span> <span data-ttu-id="3c82a-118"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>は構造体のインスタンスであり、 <xref:System.Drawing.Rectangle> コントロールが描画できる領域を定義します。</span><span class="sxs-lookup"><span data-stu-id="3c82a-118">The <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> is an instance of the <xref:System.Drawing.Rectangle> structure and defines the available area in which a control can draw.</span></span> <span data-ttu-id="3c82a-119">コントロール開発者は、 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> このトピックで後述する「ジオメトリの説明」で説明されているように、コントロールのプロパティを使用してを計算できます。</span><span class="sxs-lookup"><span data-stu-id="3c82a-119">A control developer can compute the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> using the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> property of a control, as described in the discussion of geometry later in this topic.</span></span>  
  
 <span data-ttu-id="3c82a-120">コントロールは、継承元のメソッドをオーバーライドすることにより、レンダリングロジックを提供する必要があり <xref:System.Windows.Forms.Control.OnPaint%2A> <xref:System.Windows.Forms.Control> ます。</span><span class="sxs-lookup"><span data-stu-id="3c82a-120">A control must provide rendering logic by overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method that it inherits from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="3c82a-121"><xref:System.Windows.Forms.Control.OnPaint%2A> グラフィックスオブジェクトと、に <xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A> <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 渡されるインスタンスのプロパティを通じて描画する四角形へのアクセスを取得し <xref:System.Windows.Forms.PaintEventArgs> ます。</span><span class="sxs-lookup"><span data-stu-id="3c82a-121"><xref:System.Windows.Forms.Control.OnPaint%2A> gets access to a graphics object and a rectangle to draw in through the <xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A> and the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> properties of the <xref:System.Windows.Forms.PaintEventArgs> instance passed to it.</span></span>  
  
```vb  
Protected Overridable Sub OnPaint(pe As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaint(PaintEventArgs pe);  
```  
  
 <span data-ttu-id="3c82a-122"><xref:System.Windows.Forms.Control.OnPaint%2A>基底クラスのメソッドは <xref:System.Windows.Forms.Control> 描画機能を実装しませんが、イベントに登録されているイベントデリゲートを呼び出すだけです <xref:System.Windows.Forms.Control.Paint> 。</span><span class="sxs-lookup"><span data-stu-id="3c82a-122">The <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base <xref:System.Windows.Forms.Control> class does not implement any drawing functionality but merely invokes the event delegates that are registered with the <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="3c82a-123">をオーバーライドする場合は <xref:System.Windows.Forms.Control.OnPaint%2A> 、通常、 <xref:System.Windows.Forms.Control.OnPaint%2A> 基本クラスのメソッドを呼び出して、登録されているデリゲートがイベントを受け取るようにする必要があり <xref:System.Windows.Forms.Control.Paint> ます。</span><span class="sxs-lookup"><span data-stu-id="3c82a-123">When you override <xref:System.Windows.Forms.Control.OnPaint%2A>, you should typically invoke the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class so that registered delegates receive the <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="3c82a-124">ただし、画面全体を描画するコントロールでは、基本クラスのを呼び出さないでください。これにより、ちらつきが発生 <xref:System.Windows.Forms.Control.OnPaint%2A> します。</span><span class="sxs-lookup"><span data-stu-id="3c82a-124">However, controls that paint their entire surface should not invoke the base class's <xref:System.Windows.Forms.Control.OnPaint%2A>, as this introduces flicker.</span></span> <span data-ttu-id="3c82a-125">イベントをオーバーライドする例については、 <xref:System.Windows.Forms.Control.OnPaint%2A> 「 [方法: 進行状況を示す Windows フォームコントロールを作成](how-to-create-a-windows-forms-control-that-shows-progress.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c82a-125">For an example of overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> event, see the [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3c82a-126">コントロールから直接呼び出すのでは <xref:System.Windows.Forms.Control.OnPaint%2A> なく、 <xref:System.Windows.Forms.Control.Invalidate%2A> (から継承され <xref:System.Windows.Forms.Control> た) メソッドまたはを呼び出す他のメソッドを呼び出し <xref:System.Windows.Forms.Control.Invalidate%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="3c82a-126">Do not invoke <xref:System.Windows.Forms.Control.OnPaint%2A> directly from your control; instead, invoke the <xref:System.Windows.Forms.Control.Invalidate%2A> method (inherited from <xref:System.Windows.Forms.Control>) or some other method that invokes <xref:System.Windows.Forms.Control.Invalidate%2A>.</span></span> <span data-ttu-id="3c82a-127"><xref:System.Windows.Forms.Control.Invalidate%2A>メソッドが呼び出さ <xref:System.Windows.Forms.Control.OnPaint%2A> れます。</span><span class="sxs-lookup"><span data-stu-id="3c82a-127">The <xref:System.Windows.Forms.Control.Invalidate%2A> method in turn invokes <xref:System.Windows.Forms.Control.OnPaint%2A>.</span></span> <span data-ttu-id="3c82a-128"><xref:System.Windows.Forms.Control.Invalidate%2A>メソッドはオーバーロードされており、に指定された引数によっては、 <xref:System.Windows.Forms.Control.Invalidate%2A> `e` コントロールが画面領域の一部またはすべてを再描画します。</span><span class="sxs-lookup"><span data-stu-id="3c82a-128">The <xref:System.Windows.Forms.Control.Invalidate%2A> method is overloaded, and, depending on the arguments supplied to <xref:System.Windows.Forms.Control.Invalidate%2A> `e`, a control redraws either some or all of its screen area.</span></span>  
  
 <span data-ttu-id="3c82a-129">基底クラスは、 <xref:System.Windows.Forms.Control> 描画に便利な別のメソッド (メソッド) を定義し <xref:System.Windows.Forms.Control.OnPaintBackground%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="3c82a-129">The base <xref:System.Windows.Forms.Control> class defines another method that is useful for drawing — the <xref:System.Windows.Forms.Control.OnPaintBackground%2A> method.</span></span>  
  
```vb  
Protected Overridable Sub OnPaintBackground(pevent As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaintBackground(PaintEventArgs pevent);  
```  
  
 <span data-ttu-id="3c82a-130"><xref:System.Windows.Forms.Control.OnPaintBackground%2A> ウィンドウの背景 (およびその図形) を描画し、高速であることを保証し <xref:System.Windows.Forms.Control.OnPaint%2A> ます。個々の描画要求は、再 <xref:System.Windows.Forms.Control.Paint> 描画する必要があるすべての領域を対象とした1つのイベントに結合されるため、詳細が描画され、速度が低下することがあります。</span><span class="sxs-lookup"><span data-stu-id="3c82a-130"><xref:System.Windows.Forms.Control.OnPaintBackground%2A> paints the background (and thereby the shape) of the window and is guaranteed to be fast, while <xref:System.Windows.Forms.Control.OnPaint%2A> paints the details and might be slower because individual paint requests are combined into one <xref:System.Windows.Forms.Control.Paint> event that covers all areas that have to be redrawn.</span></span> <span data-ttu-id="3c82a-131">たとえば、 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> コントロールのグラデーションカラーの背景を描画する必要がある場合は、を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="3c82a-131">You might want to invoke the <xref:System.Windows.Forms.Control.OnPaintBackground%2A> if, for instance, you want to draw a gradient-colored background for your control.</span></span>  
  
 <span data-ttu-id="3c82a-132">に <xref:System.Windows.Forms.Control.OnPaintBackground%2A> はイベントのような用語があり、メソッドと同じ引数を取り `OnPaint` <xref:System.Windows.Forms.Control.OnPaintBackground%2A> ますが、は true のイベントメソッドではありません。</span><span class="sxs-lookup"><span data-stu-id="3c82a-132">While <xref:System.Windows.Forms.Control.OnPaintBackground%2A> has an event-like nomenclature and takes the same argument as the `OnPaint` method, <xref:System.Windows.Forms.Control.OnPaintBackground%2A> is not a true event method.</span></span> <span data-ttu-id="3c82a-133">イベントは存在せず `PaintBackground` 、 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> イベントデリゲートを呼び出しません。</span><span class="sxs-lookup"><span data-stu-id="3c82a-133">There is no `PaintBackground` event and <xref:System.Windows.Forms.Control.OnPaintBackground%2A> does not invoke event delegates.</span></span> <span data-ttu-id="3c82a-134">メソッドをオーバーライドする場合 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 、派生クラスは <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 基底クラスのメソッドを呼び出す必要がありません。</span><span class="sxs-lookup"><span data-stu-id="3c82a-134">When overriding the <xref:System.Windows.Forms.Control.OnPaintBackground%2A> method, a derived class is not required to invoke the <xref:System.Windows.Forms.Control.OnPaintBackground%2A> method of its base class.</span></span>  
  
## <a name="gdi-basics"></a><span data-ttu-id="3c82a-135">GDI + の基礎</span><span class="sxs-lookup"><span data-stu-id="3c82a-135">GDI+ Basics</span></span>  

 <span data-ttu-id="3c82a-136"><xref:System.Drawing.Graphics>クラスには、円、三角形、円弧、楕円などのさまざまな図形を描画するためのメソッドと、テキストを表示するためのメソッドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="3c82a-136">The <xref:System.Drawing.Graphics> class provides methods for drawing various shapes such as circles, triangles, arcs, and ellipses, as well as methods for displaying text.</span></span> <span data-ttu-id="3c82a-137"><xref:System.Drawing?displayProperty=nameWithType>名前空間とその副名前空間には、図形 (円、四角形、円弧など)、色、フォント、ブラシなどのグラフィックス要素をカプセル化するクラスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3c82a-137">The <xref:System.Drawing?displayProperty=nameWithType> namespace and its subnamespaces contain classes that encapsulate graphics elements such as shapes (circles, rectangles, arcs, and others), colors, fonts, brushes, and so on.</span></span> <span data-ttu-id="3c82a-138">GDI の詳細については、「 [マネージグラフィックスクラスの使用](../advanced/using-managed-graphics-classes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c82a-138">For more information about GDI, see [Using Managed Graphics Classes](../advanced/using-managed-graphics-classes.md).</span></span> <span data-ttu-id="3c82a-139">GDI の基本事項については、「 [方法: 進行状況を示す Windows フォームコントロールを作成](how-to-create-a-windows-forms-control-that-shows-progress.md)する」でも説明しています。</span><span class="sxs-lookup"><span data-stu-id="3c82a-139">The essentials of GDI are also described in the [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
## <a name="geometry-of-the-drawing-region"></a><span data-ttu-id="3c82a-140">描画領域のジオメトリ</span><span class="sxs-lookup"><span data-stu-id="3c82a-140">Geometry of the Drawing Region</span></span>  

 <span data-ttu-id="3c82a-141"><xref:System.Windows.Forms.Control.ClientRectangle%2A>コントロールのプロパティは、ユーザーの画面上のコントロールで使用できる四角形の領域を指定し <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> ます。また、のプロパティは、実際に <xref:System.Windows.Forms.PaintEventArgs> 描画される領域を指定します。</span><span class="sxs-lookup"><span data-stu-id="3c82a-141">The <xref:System.Windows.Forms.Control.ClientRectangle%2A> property of a control specifies the rectangular region available to the control on the user's screen, while the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> property of <xref:System.Windows.Forms.PaintEventArgs> specifies the area that is actually painted.</span></span> <span data-ttu-id="3c82a-142">(描画は、 <xref:System.Windows.Forms.Control.Paint> <xref:System.Windows.Forms.PaintEventArgs> 引数としてインスタンスを受け取るイベントメソッドで行われることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="3c82a-142">(Remember that painting is done in the <xref:System.Windows.Forms.Control.Paint> event method that takes a <xref:System.Windows.Forms.PaintEventArgs> instance as its argument).</span></span> <span data-ttu-id="3c82a-143">コントロールは、コントロールの表示の小さいセクションが変更された場合のように、使用可能な領域の一部だけを描画する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="3c82a-143">A control might need to paint only a portion of its available area, as is the case when a small section of the control's display changes.</span></span> <span data-ttu-id="3c82a-144">このような状況では、コントロール開発者は、描画する実際の四角形を計算してに渡す必要があり <xref:System.Windows.Forms.Control.Invalidate%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="3c82a-144">In those situations, a control developer must compute the actual rectangle to draw in and pass that to <xref:System.Windows.Forms.Control.Invalidate%2A>.</span></span> <span data-ttu-id="3c82a-145"><xref:System.Windows.Forms.Control.Invalidate%2A>引数としてまたはを受け取るのオーバーロードされたバージョンは、 <xref:System.Drawing.Rectangle> <xref:System.Drawing.Region> その引数を使用してプロパティを生成し <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> <xref:System.Windows.Forms.PaintEventArgs> ます。</span><span class="sxs-lookup"><span data-stu-id="3c82a-145">The overloaded versions of <xref:System.Windows.Forms.Control.Invalidate%2A> that take a <xref:System.Drawing.Rectangle> or <xref:System.Drawing.Region> as an argument use that argument to generate the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> property of <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
 <span data-ttu-id="3c82a-146">次のコードフラグメントは、カスタムコントロールが四角形の領域を計算して描画する方法を示して `FlashTrackBar` います。</span><span class="sxs-lookup"><span data-stu-id="3c82a-146">The following code fragment shows how the `FlashTrackBar` custom control computes the rectangular area to draw in.</span></span> <span data-ttu-id="3c82a-147">変数は、 `client` プロパティを表し <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="3c82a-147">The `client` variable denotes the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> property.</span></span> <span data-ttu-id="3c82a-148">完全なサンプルについては、「 [方法: 進行状況を示す Windows フォームコントロールを作成](how-to-create-a-windows-forms-control-that-shows-progress.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c82a-148">For a complete sample, see [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#6)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#6)]  
  
## <a name="freeing-graphics-resources"></a><span data-ttu-id="3c82a-149">グラフィックスリソースの解放</span><span class="sxs-lookup"><span data-stu-id="3c82a-149">Freeing Graphics Resources</span></span>  

 <span data-ttu-id="3c82a-150">グラフィックスオブジェクトは、システムリソースを使用するため、コストが高くなります。</span><span class="sxs-lookup"><span data-stu-id="3c82a-150">Graphics objects are expensive because they use system resources.</span></span> <span data-ttu-id="3c82a-151">このようなオブジェクトには <xref:System.Drawing.Graphics?displayProperty=nameWithType> 、クラスのインスタンスだけ <xref:System.Drawing.Brush?displayProperty=nameWithType> でなく、、、 <xref:System.Drawing.Pen?displayProperty=nameWithType> およびその他のグラフィックスクラスのインスタンスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3c82a-151">Such objects include instances of the <xref:System.Drawing.Graphics?displayProperty=nameWithType> class as well as instances of <xref:System.Drawing.Brush?displayProperty=nameWithType>, <xref:System.Drawing.Pen?displayProperty=nameWithType>, and other graphics classes.</span></span> <span data-ttu-id="3c82a-152">グラフィックスリソースは、必要なときにのみ作成し、使用が終了したらすぐにリリースすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="3c82a-152">It is important that you create a graphics resource only when you need it and release it soon as you are finished using it.</span></span> <span data-ttu-id="3c82a-153">インターフェイスを実装する型を作成する場合は <xref:System.IDisposable> 、 <xref:System.IDisposable.Dispose%2A> リソースを解放するために、メソッドの使用が終了したときにメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="3c82a-153">If you create a type that implements the <xref:System.IDisposable> interface, call its <xref:System.IDisposable.Dispose%2A> method when you are finished with it in order to free resources.</span></span>  
  
 <span data-ttu-id="3c82a-154">次のコードフラグメントは、 `FlashTrackBar` カスタムコントロールがリソースを作成および解放する方法を示して <xref:System.Drawing.Brush> います。</span><span class="sxs-lookup"><span data-stu-id="3c82a-154">The following code fragment shows how the `FlashTrackBar` custom control creates and releases a <xref:System.Drawing.Brush> resource.</span></span> <span data-ttu-id="3c82a-155">完全なソースコードについては、「 [方法: 進行状況を示す Windows フォームコントロールを作成](how-to-create-a-windows-forms-control-that-shows-progress.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c82a-155">For the complete source code, see [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#5)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#5)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#4)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#4)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#3)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="3c82a-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="3c82a-156">See also</span></span>

- [<span data-ttu-id="3c82a-157">方法: 進行状況を示す Windows フォーム コントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="3c82a-157">How to: Create a Windows Forms Control That Shows Progress</span></span>](how-to-create-a-windows-forms-control-that-shows-progress.md)
