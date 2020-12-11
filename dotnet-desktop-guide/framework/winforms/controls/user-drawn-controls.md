---
title: ユーザー描画コントロール
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], user-drawn
- OnPaint method [Windows Forms]
- user-drawn controls [Windows Forms]
ms.assetid: 034af4b5-457f-4160-a937-22891817faa8
ms.openlocfilehash: c68c8c88376cfe7295962264c466030115f2f3db
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984031"
---
# <a name="user-drawn-controls"></a><span data-ttu-id="206fb-102">ユーザー描画コントロール</span><span class="sxs-lookup"><span data-stu-id="206fb-102">User-Drawn Controls</span></span>
<span data-ttu-id="206fb-103">.NET Framework には、独自のコントロールを簡単に開発する機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="206fb-103">The .NET Framework provides you with the ability to easily develop your own controls.</span></span> <span data-ttu-id="206fb-104">コードによって連結された一連の標準コントロールであるユーザーコントロールを作成することも、独自のコントロールを最初からデザインすることもできます。</span><span class="sxs-lookup"><span data-stu-id="206fb-104">You can create a user control, which is a set of standard controls bound together by code, or you can design your own control from the ground up.</span></span> <span data-ttu-id="206fb-105">継承を使用して、既存のコントロールから継承し、固有の機能に追加するコントロールを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="206fb-105">You can even use inheritance to create a control that inherits from an existing control and add to its inherent functionality.</span></span> <span data-ttu-id="206fb-106">どのような方法を使用する場合でも、.NET Framework は、作成するコントロールのカスタムグラフィカルインターフェイスを描画する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="206fb-106">Whatever approach you use, the .NET Framework provides the functionality to draw a custom graphical interface for any control you create.</span></span>  
  
 <span data-ttu-id="206fb-107">コントロールを描画するには、コントロールのメソッドでコードを実行し <xref:System.Windows.Forms.Control.OnPaint%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="206fb-107">Painting of a control is accomplished by the execution of code in the control's <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="206fb-108">メソッドの1つの引数 <xref:System.Windows.Forms.Control.OnPaint%2A> は、 <xref:System.Windows.Forms.PaintEventArgs> コントロールを表示するために必要なすべての情報と機能を提供するオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="206fb-108">The single argument of the <xref:System.Windows.Forms.Control.OnPaint%2A> method is a <xref:System.Windows.Forms.PaintEventArgs> object that provides all of the information and functionality required to render your control.</span></span> <span data-ttu-id="206fb-109">は、 <xref:System.Windows.Forms.PaintEventArgs> コントロールのレンダリングで使用される2つのプリンシパルオブジェクトをプロパティとして提供します。</span><span class="sxs-lookup"><span data-stu-id="206fb-109">The <xref:System.Windows.Forms.PaintEventArgs> provides as properties two principal objects that will be used in the rendering of your control:</span></span>  
  
- <span data-ttu-id="206fb-110"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object-描画されるコントロールの部分を表す四角形。</span><span class="sxs-lookup"><span data-stu-id="206fb-110"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object - the rectangle that represents the part of the control that will be drawn.</span></span> <span data-ttu-id="206fb-111">コントロール全体、またはコントロールの描画方法に応じたコントロールの一部を指定できます。</span><span class="sxs-lookup"><span data-stu-id="206fb-111">This can be the entire control, or part of the control depending on how the control is drawn.</span></span>  
  
- <span data-ttu-id="206fb-112"><xref:System.Drawing.Graphics> object-コントロールを描画するために必要な機能を提供する複数のグラフィックス指向オブジェクトおよびメソッドをカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="206fb-112"><xref:System.Drawing.Graphics> object - encapsulates several graphics-oriented objects and methods that provide the functionality necessary to draw your control.</span></span>  
  
 <span data-ttu-id="206fb-113"><xref:System.Drawing.Graphics>オブジェクトとその使用方法の詳細については、「[方法: 描画するためのグラフィックスオブジェクトを作成する](../advanced/how-to-create-graphics-objects-for-drawing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="206fb-113">For more information on the <xref:System.Drawing.Graphics> object and how to use it, see [How to: Create Graphics Objects for Drawing](../advanced/how-to-create-graphics-objects-for-drawing.md).</span></span>  
  
 <span data-ttu-id="206fb-114">イベントは、 <xref:System.Windows.Forms.Control.OnPaint%2A> 画面上でコントロールが描画またはリフレッシュされるたびに発生し、 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> オブジェクトは描画が行われる四角形を表します。</span><span class="sxs-lookup"><span data-stu-id="206fb-114">The <xref:System.Windows.Forms.Control.OnPaint%2A> event is fired whenever the control is drawn or refreshed on the screen, and the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object represents the rectangle in which painting will take place.</span></span> <span data-ttu-id="206fb-115">コントロール全体を更新する必要がある場合、は <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> コントロール全体のサイズを表します。</span><span class="sxs-lookup"><span data-stu-id="206fb-115">If the entire control needs to be refreshed, the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> will represent the size of the entire control.</span></span> <span data-ttu-id="206fb-116">ただし、コントロールの一部だけを更新する必要がある場合、 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> オブジェクトは再描画する必要がある領域のみを表します。</span><span class="sxs-lookup"><span data-stu-id="206fb-116">If only part of the control needs to be refreshed, however, the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object will represent only the region that needs to be redrawn.</span></span> <span data-ttu-id="206fb-117">このような場合の例として、コントロールがユーザーインターフェイスの別のコントロールまたはフォームによって部分的に隠されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="206fb-117">An example of such a case would be when a control was partially obscured by another control or form in the user interface.</span></span>  
  
 <span data-ttu-id="206fb-118">クラスから継承する場合は、 <xref:System.Windows.Forms.Control> メソッドをオーバーライド <xref:System.Windows.Forms.Control.OnPaint%2A> し、内にグラフィックスレンダリングコードを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="206fb-118">When inheriting from the <xref:System.Windows.Forms.Control> class, you must override the <xref:System.Windows.Forms.Control.OnPaint%2A> method and provide graphics-rendering code within.</span></span> <span data-ttu-id="206fb-119">ユーザーコントロールまたは継承されたコントロールにカスタムグラフィカルインターフェイスを提供する場合は、メソッドをオーバーライドすることによってもでき <xref:System.Windows.Forms.Control.OnPaint%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="206fb-119">If you want to provide a custom graphical interface to a user control or an inherited control, you can also do so by overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="206fb-120">例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="206fb-120">An example is shown below:</span></span>  
  
```vb  
Protected Overrides Sub OnPaint(ByVal e As PaintEventArgs)  
   ' Call the OnPaint method of the base class.  
   MyBase.OnPaint(e)  
  
   ' Declare and instantiate a drawing pen.  
   Using myPen As System.Drawing.Pen = New System.Drawing.Pen(Color.Aqua)  
      ' Draw an aqua rectangle in the rectangle represented by the control.  
      e.Graphics.DrawRectangle(myPen, New Rectangle(Me.Location, Me.Size))  
   End Using
End Sub  
```  
  
```csharp  
protected override void OnPaint(PaintEventArgs e)  
{  
   // Call the OnPaint method of the base class.  
   base.OnPaint(e);  
  
   // Declare and instantiate a new pen.  
   using (System.Drawing.Pen myPen = new System.Drawing.Pen(Color.Aqua))  
   {
      // Draw an aqua rectangle in the rectangle represented by the control.  
      e.Graphics.DrawRectangle(myPen, new Rectangle(this.Location,
         this.Size));  
   }
}  
```  
  
 <span data-ttu-id="206fb-121">前の例では、非常に単純なグラフィカル表示を使用してコントロールを表示する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="206fb-121">The preceding example demonstrates how to render a control with a very simple graphical representation.</span></span> <span data-ttu-id="206fb-122"><xref:System.Windows.Forms.Control.OnPaint%2A>基底クラスのメソッドを呼び出し、 <xref:System.Drawing.Pen> 描画に使用するオブジェクトを作成します。最後に、コントロールのとによって決定される四角形に楕円を描画し <xref:System.Windows.Forms.Control.Location%2A> <xref:System.Windows.Forms.Control.Size%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="206fb-122">It calls the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class, it creates a <xref:System.Drawing.Pen> object with which to draw, and finally draws an ellipse in the rectangle determined by the <xref:System.Windows.Forms.Control.Location%2A> and <xref:System.Windows.Forms.Control.Size%2A> of the control.</span></span> <span data-ttu-id="206fb-123">ほとんどのレンダリングコードは、これよりもかなり複雑になりますが、この例では、オブジェクト内に含まれるオブジェクトの使用方法を示して <xref:System.Drawing.Graphics> <xref:System.Windows.Forms.PaintEventArgs> います。</span><span class="sxs-lookup"><span data-stu-id="206fb-123">Although most rendering code will be significantly more complicated than this, this example demonstrates the use of the <xref:System.Drawing.Graphics> object contained within the <xref:System.Windows.Forms.PaintEventArgs> object.</span></span> <span data-ttu-id="206fb-124">またはのように、既にグラフィック表示を使用しているクラスから継承 <xref:System.Windows.Forms.UserControl> していて、 <xref:System.Windows.Forms.Button> その表現をレンダリングに組み込む必要がない場合は、基底クラスのメソッドを呼び出さないように注意してください <xref:System.Windows.Forms.Control.OnPaint%2A> 。</span><span class="sxs-lookup"><span data-stu-id="206fb-124">Note that if you are inheriting from a class that already has a graphical representation, such as <xref:System.Windows.Forms.UserControl> or <xref:System.Windows.Forms.Button>, and you do not wish to incorporate that representation into your rendering, you should not call your base class's <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
 <span data-ttu-id="206fb-125">コントロールのメソッドのコードは、 <xref:System.Windows.Forms.Control.OnPaint%2A> コントロールが最初に描画されたときと、コントロールが更新されるたびに実行されます。</span><span class="sxs-lookup"><span data-stu-id="206fb-125">The code in the <xref:System.Windows.Forms.Control.OnPaint%2A> method of your control will execute when the control is first drawn, and whenever it is refreshed.</span></span> <span data-ttu-id="206fb-126">コントロールがサイズ変更されるたびに再描画されるようにするには、コントロールのコンストラクターに次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="206fb-126">To ensure that your control is redrawn every time it is resized, add the following line to the constructor of your control:</span></span>  
  
```vb  
SetStyle(ControlStyles.ResizeRedraw, True)  
```  
  
```csharp  
SetStyle(ControlStyles.ResizeRedraw, true);  
```  
  
> [!NOTE]
> <span data-ttu-id="206fb-127"><xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType>四角形以外のコントロールを実装するには、プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="206fb-127">Use the <xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType> property to implement a non-rectangular control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="206fb-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="206fb-128">See also</span></span>

- <xref:System.Windows.Forms.Control.Region%2A>
- <xref:System.Windows.Forms.ControlStyles>
- <xref:System.Drawing.Graphics>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- <xref:System.Windows.Forms.PaintEventArgs>
- [<span data-ttu-id="206fb-129">方法: 描画する Graphics オブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="206fb-129">How to: Create Graphics Objects for Drawing</span></span>](../advanced/how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="206fb-130">内在コントロール</span><span class="sxs-lookup"><span data-stu-id="206fb-130">Constituent Controls</span></span>](constituent-controls.md)
- [<span data-ttu-id="206fb-131">さまざまなカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="206fb-131">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
