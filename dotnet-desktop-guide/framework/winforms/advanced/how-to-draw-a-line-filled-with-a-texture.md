---
title: '方法: テクスチャを使用して塗りつぶした直線を描画する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drawing [Windows Forms], lines
- lines [Windows Forms], texture
- drawing lines [Windows Forms], texture
ms.assetid: dc9118cc-f3c2-42e5-8173-f46d41d18fd5
ms.openlocfilehash: c0f90c298f48aeb96893bb09241faddc08d8a49d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981427"
---
# <a name="how-to-draw-a-line-filled-with-a-texture"></a><span data-ttu-id="cecaa-102">方法: テクスチャを使用して塗りつぶした直線を描画する</span><span class="sxs-lookup"><span data-stu-id="cecaa-102">How to: Draw a Line Filled with a Texture</span></span>
<span data-ttu-id="cecaa-103">純色で線を描画する代わりに、テクスチャを使用して線を描画することもできます。</span><span class="sxs-lookup"><span data-stu-id="cecaa-103">Instead of drawing a line with a solid color, you can draw a line with a texture.</span></span> <span data-ttu-id="cecaa-104">テクスチャで線と曲線を描画するには、 <xref:System.Drawing.TextureBrush> オブジェクトを作成し、その <xref:System.Drawing.TextureBrush> オブジェクトをコンストラクターに渡し <xref:System.Drawing.Pen.%23ctor%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="cecaa-104">To draw lines and curves with a texture, create a <xref:System.Drawing.TextureBrush> object, and pass that <xref:System.Drawing.TextureBrush> object to a <xref:System.Drawing.Pen.%23ctor%2A> constructor.</span></span> <span data-ttu-id="cecaa-105">テクスチャブラシに関連付けられているビットマップを使用して平面を並べて表示します (非表示)。また、ペンが直線または曲線を描画すると、ペンのストロークによって、タイル化されたテクスチャの特定のピクセルが明らかになります。</span><span class="sxs-lookup"><span data-stu-id="cecaa-105">The bitmap associated with the texture brush is used to tile the plane (invisibly), and when the pen draws a line or curve, the stroke of the pen uncovers certain pixels of the tiled texture.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cecaa-106">例</span><span class="sxs-lookup"><span data-stu-id="cecaa-106">Example</span></span>  
 <span data-ttu-id="cecaa-107">次の例では、 <xref:System.Drawing.Bitmap> ファイルからオブジェクトを作成し `Texture1.jpg` ます。</span><span class="sxs-lookup"><span data-stu-id="cecaa-107">The following example creates a <xref:System.Drawing.Bitmap> object from the file `Texture1.jpg`.</span></span> <span data-ttu-id="cecaa-108">そのビットマップを使用してオブジェクトを作成し、オブジェクトを使用してオブジェクトを <xref:System.Drawing.TextureBrush> <xref:System.Drawing.TextureBrush> 構築し <xref:System.Drawing.Pen> ます。</span><span class="sxs-lookup"><span data-stu-id="cecaa-108">That bitmap is used to construct a <xref:System.Drawing.TextureBrush> object, and the <xref:System.Drawing.TextureBrush> object is used to construct a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="cecaa-109">を呼び出すと、 <xref:System.Drawing.Graphics.DrawImage%2A> ビットマップが左上隅 ((0, 0)) で描画されます。</span><span class="sxs-lookup"><span data-stu-id="cecaa-109">The call to <xref:System.Drawing.Graphics.DrawImage%2A> draws the bitmap with its upper-left corner at (0, 0).</span></span> <span data-ttu-id="cecaa-110">への呼び出しは、オブジェクトを使用して、 <xref:System.Drawing.Graphics.DrawEllipse%2A> <xref:System.Drawing.Pen> テクスチャ楕円を描画します。</span><span class="sxs-lookup"><span data-stu-id="cecaa-110">The call to <xref:System.Drawing.Graphics.DrawEllipse%2A> uses the <xref:System.Drawing.Pen> object to draw a textured ellipse.</span></span>  
  
 <span data-ttu-id="cecaa-111">次の図は、ビットマップとテクスチャ楕円を示しています。</span><span class="sxs-lookup"><span data-stu-id="cecaa-111">The following illustration shows the bitmap and the textured ellipse:</span></span>  
  
 ![ビットマップとテクスチャ楕円を示すスクリーンショット。](./media/how-to-draw-a-line-filled-with-a-texture/bitmap-textured-ellipse.png)  
  
 [!code-csharp[System.Drawing.UsingAPen#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.UsingAPen#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cecaa-113">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="cecaa-113">Compiling the Code</span></span>  
 <span data-ttu-id="cecaa-114">Windows フォームを作成し、フォームのイベントを処理し <xref:System.Windows.Forms.Control.Paint> ます。</span><span class="sxs-lookup"><span data-stu-id="cecaa-114">Create a Windows Form and handle the form's <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="cecaa-115">前のコードをイベントハンドラーに貼り付け <xref:System.Windows.Forms.Control.Paint> ます。</span><span class="sxs-lookup"><span data-stu-id="cecaa-115">Paste the preceding code into the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="cecaa-116">`Texture.jpg`システムで有効なイメージで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="cecaa-116">Replace `Texture.jpg` with an image valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cecaa-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="cecaa-117">See also</span></span>

- [<span data-ttu-id="cecaa-118">ペンを使用した直線と図形の描画</span><span class="sxs-lookup"><span data-stu-id="cecaa-118">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="cecaa-119">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="cecaa-119">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
