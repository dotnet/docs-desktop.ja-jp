---
title: '方法: GDI+ を使用してイメージをレンダリングする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- images [Windows Forms], creating
- GDI+, rendering existing images
ms.assetid: c128b79a-3e31-47d8-9e66-3470f570a056
ms.openlocfilehash: fffe1f1052d7323d234985b7e752866f2e89657d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981795"
---
# <a name="how-to-render-images-with-gdi"></a><span data-ttu-id="2a9cd-102">方法: GDI+ を使用してイメージをレンダリングする</span><span class="sxs-lookup"><span data-stu-id="2a9cd-102">How to: Render Images with GDI+</span></span>
<span data-ttu-id="2a9cd-103">GDI + を使用して、アプリケーションにファイルとして存在するイメージを表示できます。</span><span class="sxs-lookup"><span data-stu-id="2a9cd-103">You can use GDI+ to render images that exist as files in your applications.</span></span> <span data-ttu-id="2a9cd-104">これを行うには、クラスの新しいオブジェクト <xref:System.Drawing.Image> (など <xref:System.Drawing.Bitmap> ) を作成し、 <xref:System.Drawing.Graphics> 使用する描画サーフェイスを参照するオブジェクトを作成し、 <xref:System.Drawing.Graphics.DrawImage%2A> オブジェクトのメソッドを呼び出し <xref:System.Drawing.Graphics> ます。</span><span class="sxs-lookup"><span data-stu-id="2a9cd-104">You do this by creating a new object of an <xref:System.Drawing.Image> class (such as <xref:System.Drawing.Bitmap>), creating a <xref:System.Drawing.Graphics> object that refers to the drawing surface you want to use, and calling the <xref:System.Drawing.Graphics.DrawImage%2A> method of the <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="2a9cd-105">イメージは、グラフィックス クラスで表される描画サーフェイス上に描画されます。</span><span class="sxs-lookup"><span data-stu-id="2a9cd-105">The image will be painted onto the drawing surface represented by the graphics class.</span></span> <span data-ttu-id="2a9cd-106">イメージエディターを使用して、デザイン時にイメージファイルを作成および編集したり、実行時に GDI + を使用してイメージファイルをレンダリングしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="2a9cd-106">You can use the Image Editor to create and edit image files at design time, and render them with GDI+ at run time.</span></span> <span data-ttu-id="2a9cd-107">詳細については、「[アイコン用イメージ エディター](/cpp/windows/image-editor-for-icons)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a9cd-107">For more information, see [Image Editor for Icons](/cpp/windows/image-editor-for-icons).</span></span>  
  
### <a name="to-render-an-image-with-gdi"></a><span data-ttu-id="2a9cd-108">GDI + を使用してイメージをレンダリングするには</span><span class="sxs-lookup"><span data-stu-id="2a9cd-108">To render an image with GDI+</span></span>  
  
1. <span data-ttu-id="2a9cd-109">表示するイメージを表すオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="2a9cd-109">Create an object representing the image you want to display.</span></span> <span data-ttu-id="2a9cd-110">このオブジェクトは、やなど、から継承されるクラスのメンバーである必要があり <xref:System.Drawing.Image> <xref:System.Drawing.Bitmap> <xref:System.Drawing.Imaging.Metafile> ます。</span><span class="sxs-lookup"><span data-stu-id="2a9cd-110">This object must be a member of a class that inherits from <xref:System.Drawing.Image>, such as <xref:System.Drawing.Bitmap> or <xref:System.Drawing.Imaging.Metafile>.</span></span> <span data-ttu-id="2a9cd-111">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2a9cd-111">An example is shown:</span></span>  
  
    ```vb  
    ' Uses the System.Environment.GetFolderPath to get the path to the
    ' current user's MyPictures folder.  
    Dim myBitmap as New Bitmap _  
       (System.Environment.GetFolderPath _  
          (System.Environment.SpecialFolder.MyPictures))  
    ```  
  
    ```csharp  
    // Uses the System.Environment.GetFolderPath to get the path to the
    // current user's MyPictures folder.  
    Bitmap myBitmap = new Bitmap  
       (System.Environment.GetFolderPath  
          (System.Environment.SpecialFolder.MyPictures));  
    ```  
  
    ```cpp  
    // Uses the System.Environment.GetFolderPath to get the path to the
    // current user's MyPictures folder.  
    Bitmap^ myBitmap = gcnew Bitmap  
       (System::Environment::GetFolderPath  
          (System::Environment::SpecialFolder::MyPictures));  
    ```  
  
2. <span data-ttu-id="2a9cd-112">使用する <xref:System.Drawing.Graphics> 描画サーフェイスを表すオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="2a9cd-112">Create a <xref:System.Drawing.Graphics> object that represents the drawing surface you want to use.</span></span> <span data-ttu-id="2a9cd-113">詳細については、「[方法 : 描画する Graphics オブジェクトを作成する](how-to-create-graphics-objects-for-drawing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a9cd-113">For more information, see [How to: Create Graphics Objects for Drawing](how-to-create-graphics-objects-for-drawing.md).</span></span>  
  
    ```vb  
    ' Creates a Graphics object that represents the drawing surface of
    ' Button1.  
    Dim g as Graphics = Button1.CreateGraphics  
    ```  
  
    ```csharp  
    // Creates a Graphics object that represents the drawing surface of
    // Button1.  
    Graphics g = Button1.CreateGraphics();  
    ```  
  
    ```cpp  
    // Creates a Graphics object that represents the drawing surface of
    // Button1.  
    Graphics^ g = button1->CreateGraphics();  
    ```  
  
3. <span data-ttu-id="2a9cd-114"><xref:System.Drawing.Graphics.DrawImage%2A>グラフィックスオブジェクトのを呼び出してイメージをレンダリングします。</span><span class="sxs-lookup"><span data-stu-id="2a9cd-114">Call the <xref:System.Drawing.Graphics.DrawImage%2A> of your graphics object to render the image.</span></span> <span data-ttu-id="2a9cd-115">描画対象のイメージとイメージを描画する場所の座標を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a9cd-115">You must specify both the image to be drawn, and the coordinates where it is to be drawn.</span></span>  
  
    ```vb  
    g.DrawImage(myBitmap, 1, 1)  
    ```  
  
    ```csharp  
    g.DrawImage(myBitmap, 1, 1);  
    ```  
  
    ```cpp  
    g->DrawImage(myBitmap, 1, 1);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="2a9cd-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a9cd-116">See also</span></span>

- [<span data-ttu-id="2a9cd-117">グラフィックス プログラミングについて</span><span class="sxs-lookup"><span data-stu-id="2a9cd-117">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="2a9cd-118">方法: 描画する Graphics オブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="2a9cd-118">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="2a9cd-119">GDI+ でのペン、直線、および四角形</span><span class="sxs-lookup"><span data-stu-id="2a9cd-119">Pens, Lines, and Rectangles in GDI+</span></span>](pens-lines-and-rectangles-in-gdi.md)
- [<span data-ttu-id="2a9cd-120">方法: Windows フォームにテキストを描画する</span><span class="sxs-lookup"><span data-stu-id="2a9cd-120">How to: Draw Text on a Windows Form</span></span>](how-to-draw-text-on-a-windows-form.md)
- [<span data-ttu-id="2a9cd-121">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="2a9cd-121">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="2a9cd-122">線または閉じた図形の描画</span><span class="sxs-lookup"><span data-stu-id="2a9cd-122">Drawing Lines or Closed Figures</span></span>](/cpp/windows/drawing-lines-or-closed-figures-image-editor-for-icons)
- [<span data-ttu-id="2a9cd-123">アイコン用イメージエディター</span><span class="sxs-lookup"><span data-stu-id="2a9cd-123">Image Editor for Icons</span></span>](/cpp/windows/image-editor-for-icons)
