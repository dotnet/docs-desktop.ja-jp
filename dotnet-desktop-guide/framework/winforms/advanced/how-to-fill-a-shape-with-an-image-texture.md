---
title: '方法: イメージ テクスチャによって図形を塗りつぶす'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], using with brushes
- bitmaps [Windows Forms], using texture
- shapes [Windows Forms], filling with images
ms.assetid: 508da5a6-2433-4d2b-9680-eaeae4e96e3b
ms.openlocfilehash: 42c456137f84c6fa657ba5a09727eae052a45376
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981851"
---
# <a name="how-to-fill-a-shape-with-an-image-texture"></a><span data-ttu-id="69a72-102">方法: イメージ テクスチャによって図形を塗りつぶす</span><span class="sxs-lookup"><span data-stu-id="69a72-102">How to: Fill a Shape with an Image Texture</span></span>
<span data-ttu-id="69a72-103">クラスとクラスを使用して、閉じた図形にテクスチャを埋め込むことができ <xref:System.Drawing.Image> <xref:System.Drawing.TextureBrush> ます。</span><span class="sxs-lookup"><span data-stu-id="69a72-103">You can fill a closed shape with a texture by using the <xref:System.Drawing.Image> class and the <xref:System.Drawing.TextureBrush> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69a72-104">例</span><span class="sxs-lookup"><span data-stu-id="69a72-104">Example</span></span>  
 <span data-ttu-id="69a72-105">次の例では、楕円にイメージを塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="69a72-105">The following example fills an ellipse with an image.</span></span> <span data-ttu-id="69a72-106">このコードは、 <xref:System.Drawing.Image> オブジェクトを構築し、そのオブジェクトのアドレスを <xref:System.Drawing.Image> 引数としてコンストラクターに渡し <xref:System.Drawing.TextureBrush.%23ctor%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="69a72-106">The code constructs an <xref:System.Drawing.Image> object, and then passes the address of that <xref:System.Drawing.Image> object as an argument to a <xref:System.Drawing.TextureBrush.%23ctor%2A> constructor.</span></span> <span data-ttu-id="69a72-107">3番目のステートメントはイメージをスケーリングし、4番目のステートメントは、拡大縮小されたイメージの繰り返しコピーを楕円に入力します。</span><span class="sxs-lookup"><span data-stu-id="69a72-107">The third statement scales the image, and the fourth statement fills the ellipse with repeated copies of the scaled image.</span></span>  
  
 <span data-ttu-id="69a72-108">次のコードでは、プロパティには、 <xref:System.Drawing.TextureBrush.Transform%2A> イメージが描画される前に適用される変換が含まれています。</span><span class="sxs-lookup"><span data-stu-id="69a72-108">In the following code, the <xref:System.Drawing.TextureBrush.Transform%2A> property contains the transformation that is applied to the image before it is drawn.</span></span> <span data-ttu-id="69a72-109">元のイメージの幅が640ピクセル、高さが480ピクセルであると仮定します。</span><span class="sxs-lookup"><span data-stu-id="69a72-109">Assume that the original image has a width of 640 pixels and a height of 480 pixels.</span></span> <span data-ttu-id="69a72-110">変換は、水平方向と垂直方向のスケーリング値を設定することによって、イメージを75×75に縮小します。</span><span class="sxs-lookup"><span data-stu-id="69a72-110">The transform shrinks the image to 75×75 by setting the horizontal and vertical scaling values.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="69a72-111">次の例では、イメージのサイズは75×75、楕円のサイズは150×250です。</span><span class="sxs-lookup"><span data-stu-id="69a72-111">In the following example, the image size is 75×75, and the ellipse size is 150×250.</span></span> <span data-ttu-id="69a72-112">画像は塗りつぶされている楕円より小さいため、楕円は画像で並べられています。</span><span class="sxs-lookup"><span data-stu-id="69a72-112">Because the image is smaller than the ellipse it is filling, the ellipse is tiled with the image.</span></span> <span data-ttu-id="69a72-113">タイルは、図形の境界に到達するまで、画像が水平方向および垂直方向に繰り返されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="69a72-113">Tiling means that the image is repeated horizontally and vertically until the boundary of the shape is reached.</span></span> <span data-ttu-id="69a72-114">タイルの詳細については、「 [方法: イメージを使用して図形を並べ](how-to-tile-a-shape-with-an-image.md)て表示する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69a72-114">For more information about tiling, see [How to: Tile a Shape with an Image](how-to-tile-a-shape-with-an-image.md).</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingABrush#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="69a72-115">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="69a72-115">Compiling the Code</span></span>  
 <span data-ttu-id="69a72-116">前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。</span><span class="sxs-lookup"><span data-stu-id="69a72-116">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69a72-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="69a72-117">See also</span></span>

- [<span data-ttu-id="69a72-118">ブラシを使用した図形の塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="69a72-118">Using a Brush to Fill Shapes</span></span>](using-a-brush-to-fill-shapes.md)
