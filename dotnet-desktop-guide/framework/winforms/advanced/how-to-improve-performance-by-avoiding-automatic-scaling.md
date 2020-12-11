---
title: '方法: 自動スケーリングを解除してパフォーマンスを向上させる'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- automatic scaling
- images [Windows Forms], improving performance
- images [Windows Forms], using without automatic scaling
- performance [Windows Forms], improving image
ms.assetid: 5fe2c95d-8653-4d55-bf0d-e5afa28f223b
ms.openlocfilehash: dd1a1545dce33de1ce11938db8495ebf311dadda
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981332"
---
# <a name="how-to-improve-performance-by-avoiding-automatic-scaling"></a><span data-ttu-id="51cb8-102">方法: 自動スケーリングを解除してパフォーマンスを向上させる</span><span class="sxs-lookup"><span data-stu-id="51cb8-102">How to: Improve Performance by Avoiding Automatic Scaling</span></span>
<span data-ttu-id="51cb8-103">GDI + では、イメージを描画するときに自動的にスケーリングするため、パフォーマンスが低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="51cb8-103">GDI+ may automatically scale an image as you draw it, which would decrease performance.</span></span> <span data-ttu-id="51cb8-104">または、変換先の四角形の大きさをメソッドに渡すことによって、イメージのスケーリングを制御でき <xref:System.Drawing.Graphics.DrawImage%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="51cb8-104">Alternatively, you can control the scaling of the image by passing the dimensions of the destination rectangle to the <xref:System.Drawing.Graphics.DrawImage%2A> method.</span></span>  
  
 <span data-ttu-id="51cb8-105">たとえば、メソッドの次の呼び出しでは、 <xref:System.Drawing.Graphics.DrawImage%2A> (50, 30) の左上隅を指定しますが、変換先の四角形は指定しません。</span><span class="sxs-lookup"><span data-stu-id="51cb8-105">For example, the following call to the <xref:System.Drawing.Graphics.DrawImage%2A> method specifies an upper-left corner of (50, 30) but does not specify a destination rectangle.</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.WorkingWithImages#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#31)]  
  
 <span data-ttu-id="51cb8-106">これは必須の引数の数に関して最も簡単な方法ですが、必ずしも効率的であるとは <xref:System.Drawing.Graphics.DrawImage%2A> 限りません。</span><span class="sxs-lookup"><span data-stu-id="51cb8-106">Although this is the easiest version of the <xref:System.Drawing.Graphics.DrawImage%2A> method in terms of the number of required arguments, it is not necessarily the most efficient.</span></span> <span data-ttu-id="51cb8-107">GDI + によって使用される解像度 (通常は、1インチあたり96ドット) がオブジェクトに格納されている解像度と異なる場合は、 <xref:System.Drawing.Image> メソッドによって <xref:System.Drawing.Graphics.DrawImage%2A> イメージが拡大縮小されます。</span><span class="sxs-lookup"><span data-stu-id="51cb8-107">If the resolution used by GDI+ (usually 96 dots per inch) is different from the resolution stored in the <xref:System.Drawing.Image> object, then the <xref:System.Drawing.Graphics.DrawImage%2A> method will scale the image.</span></span> <span data-ttu-id="51cb8-108">たとえば、 <xref:System.Drawing.Image> オブジェクトの幅が216ピクセルで、格納されている水平解像度の値が72ドット/インチであるとします。</span><span class="sxs-lookup"><span data-stu-id="51cb8-108">For example, suppose an <xref:System.Drawing.Image> object has a width of 216 pixels and a stored horizontal resolution value of 72 dots per inch.</span></span> <span data-ttu-id="51cb8-109">216/72 は3であるため、 <xref:System.Drawing.Graphics.DrawImage%2A> 解像度が96ドット/インチの解像度では、幅が3インチになるようにイメージをスケーリングします。</span><span class="sxs-lookup"><span data-stu-id="51cb8-109">Because 216/72 is 3, <xref:System.Drawing.Graphics.DrawImage%2A> will scale the image so that it has a width of 3 inches at a resolution of 96 dots per inch.</span></span> <span data-ttu-id="51cb8-110">つまり、に <xref:System.Drawing.Graphics.DrawImage%2A> よって、幅が 96x3 = 288 ピクセルのイメージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="51cb8-110">That is, <xref:System.Drawing.Graphics.DrawImage%2A> will display an image that has a width of 96x3 = 288 pixels.</span></span>  
  
 <span data-ttu-id="51cb8-111">画面の解像度が96ドット/インチと異なる場合でも、GDI + は、画面の解像度が96ドット/インチであるかのようにイメージを拡大縮小することがあります。</span><span class="sxs-lookup"><span data-stu-id="51cb8-111">Even if your screen resolution is different from 96 dots per inch, GDI+ will probably scale the image as if the screen resolution were 96 dots per inch.</span></span> <span data-ttu-id="51cb8-112">これは、GDI + <xref:System.Drawing.Graphics> オブジェクトがデバイスコンテキストに関連付けられており、GDI + によってデバイスコンテキストに対して画面の解像度が照会される場合、実際の画面解像度に関係なく、通常は96です。</span><span class="sxs-lookup"><span data-stu-id="51cb8-112">That is because a GDI+ <xref:System.Drawing.Graphics> object is associated with a device context, and when GDI+ queries the device context for the screen resolution, the result is usually 96, regardless of the actual screen resolution.</span></span> <span data-ttu-id="51cb8-113">メソッドでターゲットの四角形を指定することによって、自動スケーリングを回避でき <xref:System.Drawing.Graphics.DrawImage%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="51cb8-113">You can avoid automatic scaling by specifying the destination rectangle in the <xref:System.Drawing.Graphics.DrawImage%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="51cb8-114">例</span><span class="sxs-lookup"><span data-stu-id="51cb8-114">Example</span></span>  
 <span data-ttu-id="51cb8-115">次の例では、同じイメージを2回描画します。</span><span class="sxs-lookup"><span data-stu-id="51cb8-115">The following example draws the same image twice.</span></span> <span data-ttu-id="51cb8-116">最初のケースでは、コピー先の四角形の幅と高さが指定されていないため、イメージは自動的に拡大縮小されます。</span><span class="sxs-lookup"><span data-stu-id="51cb8-116">In the first case, the width and height of the destination rectangle are not specified, and the image is automatically scaled.</span></span> <span data-ttu-id="51cb8-117">2番目のケースでは、コピー先の四角形の幅と高さ (ピクセル単位) は、元のイメージの幅と高さと同じになるように指定されています。</span><span class="sxs-lookup"><span data-stu-id="51cb8-117">In the second case, the width and height (measured in pixels) of the destination rectangle are specified to be the same as the width and height of the original image.</span></span> <span data-ttu-id="51cb8-118">次の図は、2回レンダリングされるイメージを示しています。</span><span class="sxs-lookup"><span data-stu-id="51cb8-118">The following illustration shows the image rendered twice:</span></span>  
  
 ![テクスチャがスケーリングされたイメージを表示するスクリーンショット。](./media/how-to-improve-performance-by-avoiding-automatic-scaling/two-scaled-texture-images.png)  
  
 [!code-csharp[System.Drawing.WorkingWithImages#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.WorkingWithImages#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#32)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="51cb8-120">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="51cb8-120">Compiling the Code</span></span>  
 <span data-ttu-id="51cb8-121">前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。</span><span class="sxs-lookup"><span data-stu-id="51cb8-121">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="51cb8-122">Texture.jpg を、システムで有効なイメージ名とパスに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="51cb8-122">Replace Texture.jpg with an image name and path that are valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51cb8-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="51cb8-123">See also</span></span>

- [<span data-ttu-id="51cb8-124">イメージ、ビットマップ、およびメタファイル</span><span class="sxs-lookup"><span data-stu-id="51cb8-124">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="51cb8-125">イメージ、ビットマップ、アイコン、およびメタファイルの操作</span><span class="sxs-lookup"><span data-stu-id="51cb8-125">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
