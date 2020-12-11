---
title: '方法: 色を回転させる'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], rotating
- examples [Windows Forms], rotating colors
ms.assetid: e2e4c300-159c-4f4a-9b56-103b0f7cbc05
ms.openlocfilehash: 8d2717dd7b819e963126072279b361fda02188bc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981792"
---
# <a name="how-to-rotate-colors"></a><span data-ttu-id="e47eb-102">方法: 色を回転させる</span><span class="sxs-lookup"><span data-stu-id="e47eb-102">How to: Rotate Colors</span></span>
<span data-ttu-id="e47eb-103">4次元の色空間での回転は、視覚化するのが困難です。</span><span class="sxs-lookup"><span data-stu-id="e47eb-103">Rotation in a four-dimensional color space is difficult to visualize.</span></span> <span data-ttu-id="e47eb-104">色のコンポーネントの1つを固定したままにして、回転を簡単に視覚化できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="e47eb-104">We can make it easier to visualize rotation by agreeing to keep one of the color components fixed.</span></span> <span data-ttu-id="e47eb-105">アルファコンポーネントを 1 (完全に不透明) に固定したままにすることに同意したとします。</span><span class="sxs-lookup"><span data-stu-id="e47eb-105">Suppose we agree to keep the alpha component fixed at 1 (fully opaque).</span></span> <span data-ttu-id="e47eb-106">次の図に示すように、赤、緑、および青の軸を持つ3次元の色空間を視覚化できます。</span><span class="sxs-lookup"><span data-stu-id="e47eb-106">Then we can visualize a three-dimensional color space with red, green, and blue axes as shown in the following illustration.</span></span>  
  
 ![赤、緑、および青の軸を使用した回転を示す図。](./media/how-to-rotate-colors/rotation-red-green-blue-axes.gif)  
  
 <span data-ttu-id="e47eb-108">色は、3D 空間のポイントと考えることができます。</span><span class="sxs-lookup"><span data-stu-id="e47eb-108">A color can be thought of as a point in 3D space.</span></span> <span data-ttu-id="e47eb-109">たとえば、空間のポイント (1, 0, 0) は赤を表し、空間のポイント (0, 1, 0) は緑を表します。</span><span class="sxs-lookup"><span data-stu-id="e47eb-109">For example, the point (1, 0, 0) in space represents the color red, and the point (0, 1, 0) in space represents the color green.</span></span>  
  
 <span data-ttu-id="e47eb-110">次の図は、Red-Green 平面で60度の角度を使用して、色 (1, 0, 0) を回転させる意味を示しています。</span><span class="sxs-lookup"><span data-stu-id="e47eb-110">The following illustration shows what it means to rotate the color (1, 0, 0) through an angle of 60 degrees in the Red-Green plane.</span></span> <span data-ttu-id="e47eb-111">平面内の回転は、Red-Green 平面と平行していて、青の軸についての回転と考えることができます。</span><span class="sxs-lookup"><span data-stu-id="e47eb-111">Rotation in a plane parallel to the Red-Green plane can be thought of as rotation about the blue axis.</span></span>  
  
 ![青色の軸についての回転を示す図。](./media/how-to-rotate-colors/rotation-about-blue-axis.gif)  
  
 <span data-ttu-id="e47eb-113">次の図は、カラー行列を初期化して、3つの座標軸 (赤、緑、青) のそれぞれに対して回転を実行する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e47eb-113">The following illustration shows how to initialize a color matrix to perform rotations about each of the three coordinate axes (red, green, blue):</span></span>  
  
 ![カラー行列を初期化して、3つの軸についての回転を実行します。](./media/how-to-rotate-colors/rotation-about-three-axes.gif)  
  
## <a name="example"></a><span data-ttu-id="e47eb-115">例</span><span class="sxs-lookup"><span data-stu-id="e47eb-115">Example</span></span>  
 <span data-ttu-id="e47eb-116">次の例では、1つの色 (1、0、0.6) のイメージを取得し、青の軸について60度回転を適用します。</span><span class="sxs-lookup"><span data-stu-id="e47eb-116">The following example takes an image that is all one color (1, 0, 0.6) and applies a 60-degree rotation about the blue axis.</span></span> <span data-ttu-id="e47eb-117">回転の角度は、赤と緑の平面に平行した平面でスイープされます。</span><span class="sxs-lookup"><span data-stu-id="e47eb-117">The angle of the rotation is swept out in a plane that is parallel to the red-green plane.</span></span>  
  
 <span data-ttu-id="e47eb-118">次の図は、左側の元の画像と右側のカラー回転画像を示しています。</span><span class="sxs-lookup"><span data-stu-id="e47eb-118">The following illustration shows the original image on the left and the color-rotated image on the right:</span></span>  
  
 ![元の画像とカラー回転した画像を示す図。](./media/how-to-rotate-colors/original-color-rotated-images.png)  
  
 <span data-ttu-id="e47eb-120">次の図は、次のコードで実行されるカラー回転の視覚化を示しています。</span><span class="sxs-lookup"><span data-stu-id="e47eb-120">The following illustration shows a visualization of the color rotation performed in the following code:</span></span>
  
 ![色の回転の視覚化を示す図。](./media/how-to-rotate-colors/visualization-color-rotation.gif)  
  
 [!code-csharp[System.Drawing.RotateColors#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e47eb-122">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="e47eb-122">Compiling the Code</span></span>  
 <span data-ttu-id="e47eb-123">前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。</span><span class="sxs-lookup"><span data-stu-id="e47eb-123">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="e47eb-124">`RotationInput.bmp`システムで有効なイメージファイル名とパスで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e47eb-124">Replace `RotationInput.bmp` with an image file name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e47eb-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="e47eb-125">See also</span></span>

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="e47eb-126">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="e47eb-126">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="e47eb-127">イメージの色の変更</span><span class="sxs-lookup"><span data-stu-id="e47eb-127">Recoloring Images</span></span>](recoloring-images.md)
