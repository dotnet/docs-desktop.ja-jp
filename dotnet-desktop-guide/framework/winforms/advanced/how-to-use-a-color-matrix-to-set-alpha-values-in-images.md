---
title: '方法: カラー行列を使用してイメージのアルファ値を設定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], using color matrices for semi-transparent
- transparency [Windows Forms], color matrices
- matrices [Windows Forms], alpha values
- bitmaps [Windows Forms], using color matrices for semi-transparent
ms.assetid: a27121e6-f7e9-4c09-84e2-f05aa9d2a1bb
ms.openlocfilehash: 73e820845d040856a0ae367da8b9371ad6afa142
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981240"
---
# <a name="how-to-use-a-color-matrix-to-set-alpha-values-in-images"></a><span data-ttu-id="45f92-102">方法: カラー行列を使用してイメージのアルファ値を設定する</span><span class="sxs-lookup"><span data-stu-id="45f92-102">How to: Use a Color Matrix to Set Alpha Values in Images</span></span>
<span data-ttu-id="45f92-103">クラス <xref:System.Drawing.Bitmap> (クラスから継承 <xref:System.Drawing.Image> ) とクラスは、 <xref:System.Drawing.Imaging.ImageAttributes> ピクセル値を取得および設定するための機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="45f92-103">The <xref:System.Drawing.Bitmap> class (which inherits from the <xref:System.Drawing.Image> class) and the <xref:System.Drawing.Imaging.ImageAttributes> class provide functionality for getting and setting pixel values.</span></span> <span data-ttu-id="45f92-104">クラスを使用して <xref:System.Drawing.Imaging.ImageAttributes> イメージ全体のアルファ値を変更することも、クラスのメソッドを呼び出して個々のピクセル値を変更することもでき <xref:System.Drawing.Bitmap.SetPixel%2A> <xref:System.Drawing.Bitmap> ます。</span><span class="sxs-lookup"><span data-stu-id="45f92-104">You can use the <xref:System.Drawing.Imaging.ImageAttributes> class to modify the alpha values for an entire image, or you can call the <xref:System.Drawing.Bitmap.SetPixel%2A> method of the <xref:System.Drawing.Bitmap> class to modify individual pixel values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="45f92-105">例</span><span class="sxs-lookup"><span data-stu-id="45f92-105">Example</span></span>  
 <span data-ttu-id="45f92-106"><xref:System.Drawing.Imaging.ImageAttributes>クラスには、レンダリング時にイメージを変更するために使用できる多くのプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="45f92-106">The <xref:System.Drawing.Imaging.ImageAttributes> class has many properties that you can use to modify images during rendering.</span></span> <span data-ttu-id="45f92-107">次の例では、 <xref:System.Drawing.Imaging.ImageAttributes> オブジェクトを使用して、すべてのアルファ値を80% に設定しています。</span><span class="sxs-lookup"><span data-stu-id="45f92-107">In the following example, an <xref:System.Drawing.Imaging.ImageAttributes> object is used to set all the alpha values to 80 percent of what they were.</span></span> <span data-ttu-id="45f92-108">これは、カラーマトリックスを初期化し、マトリックスのアルファスケーリング値を0.8 に設定することによって行われます。</span><span class="sxs-lookup"><span data-stu-id="45f92-108">This is done by initializing a color matrix and setting the alpha scaling value in the matrix to 0.8.</span></span> <span data-ttu-id="45f92-109">カラーマトリックスのアドレスがオブジェクトのメソッドに渡され、オブジェクト <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> <xref:System.Drawing.Imaging.ImageAttributes> がオブジェクト <xref:System.Drawing.Imaging.ImageAttributes> のメソッドに渡され <xref:System.Drawing.Graphics.DrawString%2A> <xref:System.Drawing.Graphics> ます。</span><span class="sxs-lookup"><span data-stu-id="45f92-109">The address of the color matrix is passed to the <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> method of the <xref:System.Drawing.Imaging.ImageAttributes> object, and the <xref:System.Drawing.Imaging.ImageAttributes> object is passed to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> object.</span></span>  
  
 <span data-ttu-id="45f92-110">レンダリング中、ビットマップのアルファ値は、その値の80% に変換されます。</span><span class="sxs-lookup"><span data-stu-id="45f92-110">During rendering, the alpha values in the bitmap are converted to 80 percent of what they were.</span></span> <span data-ttu-id="45f92-111">これにより、背景とブレンドされるイメージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="45f92-111">This results in an image that is blended with the background.</span></span> <span data-ttu-id="45f92-112">次の図に示すように、ビットマップイメージは透明に見えます。黒い線が表示されます。</span><span class="sxs-lookup"><span data-stu-id="45f92-112">As the following illustration shows, the bitmap image looks transparent; you can see the solid black line through it.</span></span>  
  
 <span data-ttu-id="45f92-113">![マトリックスを使用したアルファブレンドのスクリーンショット。](./media/how-to-use-a-color-matrix-to-set-alpha-values-in-images/alpha-blending-matrix.png "Image2")</span><span class="sxs-lookup"><span data-stu-id="45f92-113">![Screenshot of alpha blending using a matrix.](./media/how-to-use-a-color-matrix-to-set-alpha-values-in-images/alpha-blending-matrix.png "image2")</span></span>  
  
 <span data-ttu-id="45f92-114">画像が背景の白い部分の上にある場合、画像は白の色にブレンドされています。</span><span class="sxs-lookup"><span data-stu-id="45f92-114">Where the image is over the white portion of the background, the image has been blended with the color white.</span></span> <span data-ttu-id="45f92-115">画像が黒い線と交差する場合、イメージは黒の色とブレンドされます。</span><span class="sxs-lookup"><span data-stu-id="45f92-115">Where the image crosses the black line, the image is blended with the color black.</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.AlphaBlending#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="45f92-116">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="45f92-116">Compiling the Code</span></span>  
 <span data-ttu-id="45f92-117">前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、のパラメーターであるを必要とし <xref:System.Windows.Forms.PaintEventHandler> ます。</span><span class="sxs-lookup"><span data-stu-id="45f92-117">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45f92-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="45f92-118">See also</span></span>

- [<span data-ttu-id="45f92-119">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="45f92-119">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="45f92-120">アルファ ブレンドの直線と塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="45f92-120">Alpha Blending Lines and Fills</span></span>](alpha-blending-lines-and-fills.md)
