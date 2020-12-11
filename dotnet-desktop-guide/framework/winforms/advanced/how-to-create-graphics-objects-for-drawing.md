---
title: '方法: 描画する Graphics オブジェクトを作成する'
description: GDI + を使用して、線や図形を描画したり、テキストをレンダリングしたり、イメージを表示および操作したりするために必要なグラフィックオブジェクトを作成する方法について説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], creating
- images [Windows Forms], creating
- GDI+, creating images
ms.assetid: 162861f9-f050-445e-8abb-b2c43a918b8b
ms.openlocfilehash: 1a0884c1e9956dc6f4608e32372deeea24ef4670
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974825"
---
# <a name="how-to-create-graphics-objects-for-drawing"></a><span data-ttu-id="fe7f5-103">方法: 描画する Graphics オブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="fe7f5-103">How to: Create Graphics Objects for Drawing</span></span>
<span data-ttu-id="fe7f5-104">GDI + を使用して、線や形状の描画、テキストのレンダリング、イメージの表示と操作を行うには、オブジェクトを作成する必要があり <xref:System.Drawing.Graphics> ます。</span><span class="sxs-lookup"><span data-stu-id="fe7f5-104">Before you can draw lines and shapes, render text, or display and manipulate images with GDI+, you need to create a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="fe7f5-105"><xref:System.Drawing.Graphics>オブジェクトは GDI + の描画サーフェイスを表し、はグラフィックイメージを作成するために使用されるオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="fe7f5-105">The <xref:System.Drawing.Graphics> object represents a GDI+ drawing surface, and is the object that is used to create graphical images.</span></span>  
  
 <span data-ttu-id="fe7f5-106">グラフィックスを操作するには、次の2つの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="fe7f5-106">There are two steps in working with graphics:</span></span>  
  
1. <span data-ttu-id="fe7f5-107">オブジェクトを作成 <xref:System.Drawing.Graphics> しています。</span><span class="sxs-lookup"><span data-stu-id="fe7f5-107">Creating a <xref:System.Drawing.Graphics> object.</span></span>  
  
2. <span data-ttu-id="fe7f5-108">オブジェクトを使用して、 <xref:System.Drawing.Graphics> 線と形状を描画したり、テキストを表示したり、イメージを表示および操作したりします。</span><span class="sxs-lookup"><span data-stu-id="fe7f5-108">Using the <xref:System.Drawing.Graphics> object to draw lines and shapes, render text, or display and manipulate images.</span></span>  
  
## <a name="creating-a-graphics-object"></a><span data-ttu-id="fe7f5-109">グラフィックスオブジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="fe7f5-109">Creating a Graphics Object</span></span>  
 <span data-ttu-id="fe7f5-110">グラフィックスオブジェクトは、さまざまな方法で作成できます。</span><span class="sxs-lookup"><span data-stu-id="fe7f5-110">A graphics object can be created in a variety of ways.</span></span>  
  
#### <a name="to-create-a-graphics-object"></a><span data-ttu-id="fe7f5-111">グラフィックスオブジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="fe7f5-111">To create a graphics object</span></span>  
  
- <span data-ttu-id="fe7f5-112"><xref:System.Windows.Forms.PaintEventArgs> <xref:System.Windows.Forms.Control.Paint> フォームまたはコントロールのイベントで、の一部としてグラフィックスオブジェクトへの参照を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="fe7f5-112">Receive a reference to a graphics object as part of the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event of a form or control.</span></span> <span data-ttu-id="fe7f5-113">これは、通常、コントロールの描画コードを作成するときに、グラフィックスオブジェクトへの参照を取得する方法です。</span><span class="sxs-lookup"><span data-stu-id="fe7f5-113">This is usually how you obtain a reference to a graphics object when creating painting code for a control.</span></span> <span data-ttu-id="fe7f5-114">同様に、のイベントを処理するときに、グラフィックスオブジェクトをのプロパティとして取得することもでき <xref:System.Drawing.Printing.PrintPageEventArgs> <xref:System.Drawing.Printing.PrintDocument.PrintPage> <xref:System.Drawing.Printing.PrintDocument> ます。</span><span class="sxs-lookup"><span data-stu-id="fe7f5-114">Similarly, you can also obtain a graphics object as a property of the <xref:System.Drawing.Printing.PrintPageEventArgs> when handling the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event for a <xref:System.Drawing.Printing.PrintDocument>.</span></span>  
  
     <span data-ttu-id="fe7f5-115">または</span><span class="sxs-lookup"><span data-stu-id="fe7f5-115">-or-</span></span>  
  
- <span data-ttu-id="fe7f5-116">コントロールまたはフォームのメソッドを呼び出して、 <xref:System.Windows.Forms.Control.CreateGraphics%2A> <xref:System.Drawing.Graphics> そのコントロールまたはフォームの描画サーフェイスを表すオブジェクトへの参照を取得します。</span><span class="sxs-lookup"><span data-stu-id="fe7f5-116">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span> <span data-ttu-id="fe7f5-117">既に存在するフォームまたはコントロールに描画する場合は、このメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="fe7f5-117">Use this method if you want to draw on a form or control that already exists.</span></span>  
  
     <span data-ttu-id="fe7f5-118">または</span><span class="sxs-lookup"><span data-stu-id="fe7f5-118">-or-</span></span>  
  
- <span data-ttu-id="fe7f5-119"><xref:System.Drawing.Graphics>を継承する任意のオブジェクトからオブジェクトを作成 <xref:System.Drawing.Image> します。</span><span class="sxs-lookup"><span data-stu-id="fe7f5-119">Create a <xref:System.Drawing.Graphics> object from any object that inherits from <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="fe7f5-120">この方法は、既存のイメージを変更する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="fe7f5-120">This approach is useful when you want to alter an already existing image.</span></span>  
  
     <span data-ttu-id="fe7f5-121">次のセクションでは、これらの各プロセスについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="fe7f5-121">The following sections give details about each of these processes.</span></span>  
  
## <a name="painteventargs-in-the-paint-event-handler"></a><span data-ttu-id="fe7f5-122">描画イベントハンドラーの PaintEventArgs</span><span class="sxs-lookup"><span data-stu-id="fe7f5-122">PaintEventArgs in the Paint Event Handler</span></span>  
 <span data-ttu-id="fe7f5-123">コントロールまたはのをプログラミングする場合、 <xref:System.Windows.Forms.PaintEventHandler> <xref:System.Drawing.Printing.PrintDocument.PrintPage> <xref:System.Drawing.Printing.PrintDocument> グラフィックスオブジェクトはまたはのプロパティの1つとして提供され <xref:System.Windows.Forms.PaintEventArgs> <xref:System.Drawing.Printing.PrintPageEventArgs> ます。</span><span class="sxs-lookup"><span data-stu-id="fe7f5-123">When programming the <xref:System.Windows.Forms.PaintEventHandler> for controls or the <xref:System.Drawing.Printing.PrintDocument.PrintPage> for a <xref:System.Drawing.Printing.PrintDocument>, a graphics object is provided as one of the properties of <xref:System.Windows.Forms.PaintEventArgs> or <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
#### <a name="to-obtain-a-reference-to-a-graphics-object-from-the-painteventargs-in-the-paint-event"></a><span data-ttu-id="fe7f5-124">描画イベントの PaintEventArgs からグラフィックスオブジェクトへの参照を取得するには</span><span class="sxs-lookup"><span data-stu-id="fe7f5-124">To obtain a reference to a Graphics object from the PaintEventArgs in the Paint event</span></span>  
  
1. <span data-ttu-id="fe7f5-125">オブジェクトを宣言 <xref:System.Drawing.Graphics> します。</span><span class="sxs-lookup"><span data-stu-id="fe7f5-125">Declare the <xref:System.Drawing.Graphics> object.</span></span>  
  
2. <span data-ttu-id="fe7f5-126">変数を割り当て <xref:System.Drawing.Graphics> て、の一部として渡されたオブジェクトを参照し <xref:System.Windows.Forms.PaintEventArgs> ます。</span><span class="sxs-lookup"><span data-stu-id="fe7f5-126">Assign the variable to refer to the <xref:System.Drawing.Graphics> object passed as part of the <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
3. <span data-ttu-id="fe7f5-127">フォームまたはコントロールを描画するためのコードを挿入します。</span><span class="sxs-lookup"><span data-stu-id="fe7f5-127">Insert code to paint the form or control.</span></span>  
  
     <span data-ttu-id="fe7f5-128">次の例は、イベントでからオブジェクトを参照する方法を示してい <xref:System.Drawing.Graphics> <xref:System.Windows.Forms.PaintEventArgs> <xref:System.Windows.Forms.Control.Paint> ます。</span><span class="sxs-lookup"><span data-stu-id="fe7f5-128">The following example shows how to reference a <xref:System.Drawing.Graphics> object from the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event:</span></span>  
  
    ```vb  
    Private Sub Form1_Paint(sender As Object, pe As PaintEventArgs) Handles _  
       MyBase.Paint  
       ' Declares the Graphics object and sets it to the Graphics object  
       ' supplied in the PaintEventArgs.  
       Dim g As Graphics = pe.Graphics  
       ' Insert code to paint the form here.  
    End Sub  
    ```  
  
    ```csharp  
    private void Form1_Paint(object sender,
       System.Windows.Forms.PaintEventArgs pe)
    {  
       // Declares the Graphics object and sets it to the Graphics object  
       // supplied in the PaintEventArgs.  
       Graphics g = pe.Graphics;  
       // Insert code to paint the form here.  
    }  
    ```  
  
    ```cpp  
    private:  
       void Form1_Paint(System::Object ^ sender,  
          System::Windows::Forms::PaintEventArgs ^ pe)  
       {  
          // Declares the Graphics object and sets it to the Graphics object  
          // supplied in the PaintEventArgs.  
          Graphics ^ g = pe->Graphics;  
          // Insert code to paint the form here.  
       }  
    ```  
  
## <a name="creategraphics-method"></a><span data-ttu-id="fe7f5-129">CreateGraphics メソッド</span><span class="sxs-lookup"><span data-stu-id="fe7f5-129">CreateGraphics Method</span></span>  
 <span data-ttu-id="fe7f5-130">また、コントロールまたはフォームのメソッドを使用して、 <xref:System.Windows.Forms.Control.CreateGraphics%2A> <xref:System.Drawing.Graphics> そのコントロールまたはフォームの描画サーフェイスを表すオブジェクトへの参照を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="fe7f5-130">You can also use the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span>  
  
#### <a name="to-create-a-graphics-object-with-the-creategraphics-method"></a><span data-ttu-id="fe7f5-131">CreateGraphics メソッドを使用してグラフィックスオブジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="fe7f5-131">To create a Graphics object with the CreateGraphics method</span></span>  
  
- <span data-ttu-id="fe7f5-132"><xref:System.Windows.Forms.Control.CreateGraphics%2A>グラフィックスをレンダリングするフォームまたはコントロールのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="fe7f5-132">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of the form or control upon which you want to render graphics.</span></span>  
  
    ```vb  
    Dim g as Graphics  
    ' Sets g to a Graphics object representing the drawing surface of the  
    ' control or form g is a member of.  
    g = Me.CreateGraphics  
    ```  
  
    ```csharp  
    Graphics g;  
    // Sets g to a graphics object representing the drawing surface of the  
    // control or form g is a member of.  
    g = this.CreateGraphics();  
    ```  
  
    ```cpp  
    Graphics ^ g;  
    // Sets g to a graphics object representing the drawing surface of the  
    // control or form g is a member of.  
    g = this->CreateGraphics();  
    ```  
  
## <a name="create-from-an-image-object"></a><span data-ttu-id="fe7f5-133">イメージオブジェクトから作成する</span><span class="sxs-lookup"><span data-stu-id="fe7f5-133">Create from an Image Object</span></span>  
 <span data-ttu-id="fe7f5-134">さらに、クラスから派生した任意のオブジェクトからグラフィックスオブジェクトを作成することもでき <xref:System.Drawing.Image> ます。</span><span class="sxs-lookup"><span data-stu-id="fe7f5-134">Additionally, you can create a graphics object from any object that derives from the <xref:System.Drawing.Image> class.</span></span>  
  
#### <a name="to-create-a-graphics-object-from-an-image"></a><span data-ttu-id="fe7f5-135">イメージからグラフィックスオブジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="fe7f5-135">To create a Graphics object from an Image</span></span>  
  
- <span data-ttu-id="fe7f5-136">オブジェクトを <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> 作成するイメージ変数の名前を指定して、メソッドを呼び出し <xref:System.Drawing.Graphics> ます。</span><span class="sxs-lookup"><span data-stu-id="fe7f5-136">Call the <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> method, supplying the name of the Image variable from which you want to create a <xref:System.Drawing.Graphics> object.</span></span>  
  
     <span data-ttu-id="fe7f5-137">次の例は、オブジェクトの使用方法を示してい <xref:System.Drawing.Bitmap> ます。</span><span class="sxs-lookup"><span data-stu-id="fe7f5-137">The following example shows how to use a <xref:System.Drawing.Bitmap> object:</span></span>  
  
    ```vb  
    Dim myBitmap as New Bitmap("C:\Documents and Settings\Joe\Pics\myPic.bmp")  
    Dim g as Graphics = Graphics.FromImage(myBitmap)  
    ```  
  
    ```csharp  
    Bitmap myBitmap = new Bitmap(@"C:\Documents and
       Settings\Joe\Pics\myPic.bmp");  
    Graphics g = Graphics.FromImage(myBitmap);  
    ```  
  
    ```cpp  
    Bitmap ^ myBitmap = gcnew  
       Bitmap("D:\\Documents and Settings\\Joe\\Pics\\myPic.bmp");  
    Graphics ^ g = Graphics::FromImage(myBitmap);  
    ```  
  
> [!NOTE]
> <span data-ttu-id="fe7f5-138">オブジェクトを作成できるのは、 <xref:System.Drawing.Graphics> 16 ビット、24ビット、32ビットの .bmp ファイルなど、インデックスのない .bmp ファイルのオブジェクトだけです。</span><span class="sxs-lookup"><span data-stu-id="fe7f5-138">You can only create <xref:System.Drawing.Graphics> objects from nonindexed .bmp files, such as 16-bit, 24-bit, and 32-bit .bmp files.</span></span> <span data-ttu-id="fe7f5-139">インデックス付けされていない .bmp ファイルの各ピクセルには、カラーテーブルのインデックスを保持するインデックス付き .bmp ファイルのピクセルとは対照的に、色が保持されます。</span><span class="sxs-lookup"><span data-stu-id="fe7f5-139">Each pixel of nonindexed .bmp files holds a color, in contrast to pixels of indexed .bmp files, which hold an index to a color table.</span></span>  
  
## <a name="drawing-and-manipulating-shapes-and-images"></a><span data-ttu-id="fe7f5-140">図形とイメージの描画と操作</span><span class="sxs-lookup"><span data-stu-id="fe7f5-140">Drawing and Manipulating Shapes and Images</span></span>  
 <span data-ttu-id="fe7f5-141">オブジェクトを作成した後、オブジェクトを使用して、 <xref:System.Drawing.Graphics> 線や図形の描画、テキストの表示、画像の表示と操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="fe7f5-141">After it is created, a <xref:System.Drawing.Graphics> object may be used to draw lines and shapes, render text, or display and manipulate images.</span></span> <span data-ttu-id="fe7f5-142">オブジェクトで使用されるプリンシパルオブジェクト <xref:System.Drawing.Graphics> は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fe7f5-142">The principal objects that are used with the <xref:System.Drawing.Graphics> object are:</span></span>  
  
- <span data-ttu-id="fe7f5-143"><xref:System.Drawing.Pen>クラス。線の描画、図形のアウトライン表示、またはその他の幾何学的表現のレンダリングに使用されます。</span><span class="sxs-lookup"><span data-stu-id="fe7f5-143">The <xref:System.Drawing.Pen> class—Used for drawing lines, outlining shapes, or rendering other geometric representations.</span></span>  
  
- <span data-ttu-id="fe7f5-144"><xref:System.Drawing.Brush>塗りつぶされた図形、画像、テキストなど、グラフィックスの領域を塗りつぶすために使用されるクラス。</span><span class="sxs-lookup"><span data-stu-id="fe7f5-144">The <xref:System.Drawing.Brush> class—Used for filling areas of graphics, such as filled shapes, images, or text.</span></span>  
  
- <span data-ttu-id="fe7f5-145"><xref:System.Drawing.Font>クラス: テキストを表示するときに使用する図形の説明を提供します。</span><span class="sxs-lookup"><span data-stu-id="fe7f5-145">The <xref:System.Drawing.Font> class—Provides a description of what shapes to use when rendering text.</span></span>  
  
- <span data-ttu-id="fe7f5-146"><xref:System.Drawing.Color>構造体は、表示するさまざまな色を表します。</span><span class="sxs-lookup"><span data-stu-id="fe7f5-146">The <xref:System.Drawing.Color> structure—Represents the different colors to display.</span></span>  
  
#### <a name="to-use-the-graphics-object-you-have-created"></a><span data-ttu-id="fe7f5-147">作成したグラフィックスオブジェクトを使用するには</span><span class="sxs-lookup"><span data-stu-id="fe7f5-147">To use the Graphics object you have created</span></span>  
  
- <span data-ttu-id="fe7f5-148">上記の適切なオブジェクトを使用して、必要なものを描画します。</span><span class="sxs-lookup"><span data-stu-id="fe7f5-148">Work with the appropriate object listed above to draw what you need.</span></span>  
  
     <span data-ttu-id="fe7f5-149">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe7f5-149">For more information, see the following topics:</span></span>  
  
    |<span data-ttu-id="fe7f5-150">レンダリングするには</span><span class="sxs-lookup"><span data-stu-id="fe7f5-150">To render</span></span>|<span data-ttu-id="fe7f5-151">解決方法については、</span><span class="sxs-lookup"><span data-stu-id="fe7f5-151">See</span></span>|  
    |---------------|---------|  
    |<span data-ttu-id="fe7f5-152">路線</span><span class="sxs-lookup"><span data-stu-id="fe7f5-152">Lines</span></span>|[<span data-ttu-id="fe7f5-153">方法: Windows フォームに直線を描画する</span><span class="sxs-lookup"><span data-stu-id="fe7f5-153">How to: Draw a Line on a Windows Form</span></span>](how-to-draw-a-line-on-a-windows-form.md)|  
    |<span data-ttu-id="fe7f5-154">図形</span><span class="sxs-lookup"><span data-stu-id="fe7f5-154">Shapes</span></span>|[<span data-ttu-id="fe7f5-155">方法: 形状のアウトラインを描画する</span><span class="sxs-lookup"><span data-stu-id="fe7f5-155">How to: Draw an Outlined Shape</span></span>](how-to-draw-an-outlined-shape.md)|  
    |<span data-ttu-id="fe7f5-156">Text</span><span class="sxs-lookup"><span data-stu-id="fe7f5-156">Text</span></span>|[<span data-ttu-id="fe7f5-157">方法: Windows フォームにテキストを描画する</span><span class="sxs-lookup"><span data-stu-id="fe7f5-157">How to: Draw Text on a Windows Form</span></span>](how-to-draw-text-on-a-windows-form.md)|  
    |<span data-ttu-id="fe7f5-158">イメージ</span><span class="sxs-lookup"><span data-stu-id="fe7f5-158">Images</span></span>|[<span data-ttu-id="fe7f5-159">方法: GDI+ を使用してイメージをレンダリングする</span><span class="sxs-lookup"><span data-stu-id="fe7f5-159">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)|  
  
## <a name="see-also"></a><span data-ttu-id="fe7f5-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="fe7f5-160">See also</span></span>

- [<span data-ttu-id="fe7f5-161">グラフィックス プログラミングについて</span><span class="sxs-lookup"><span data-stu-id="fe7f5-161">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="fe7f5-162">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="fe7f5-162">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="fe7f5-163">直線、曲線、および図形</span><span class="sxs-lookup"><span data-stu-id="fe7f5-163">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="fe7f5-164">方法: GDI+ を使用してイメージをレンダリングする</span><span class="sxs-lookup"><span data-stu-id="fe7f5-164">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)
