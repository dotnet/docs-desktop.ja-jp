---
title: '方法: 色を傾斜する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], transforming with color matrices
- colors [Windows Forms], shearing
ms.assetid: 0a424171-5b8b-45c4-afef-e9720a6c3e22
ms.openlocfilehash: 825e5a90ebb0d9df3b894ce7bd353e917b676939
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981271"
---
# <a name="how-to-shear-colors"></a><span data-ttu-id="fbbaf-102">方法: 色を傾斜する</span><span class="sxs-lookup"><span data-stu-id="fbbaf-102">How to: Shear Colors</span></span>
<span data-ttu-id="fbbaf-103">傾斜を設定すると、別のカラーコンポーネントに比例してカラーコンポーネントが拡大または縮小されます。</span><span class="sxs-lookup"><span data-stu-id="fbbaf-103">Shearing increases or decreases a color component by an amount proportional to another color component.</span></span> <span data-ttu-id="fbbaf-104">たとえば、赤の成分が青のコンポーネントの半分の値になるような変換を考えてみます。</span><span class="sxs-lookup"><span data-stu-id="fbbaf-104">For example, consider the transformation where the red component is increased by one half the value of the blue component.</span></span> <span data-ttu-id="fbbaf-105">このような変換では、色 (0.2、0.5、1) が (0.7、0.5、1) になります。</span><span class="sxs-lookup"><span data-stu-id="fbbaf-105">Under such a transformation, the color (0.2, 0.5, 1) would become (0.7, 0.5, 1).</span></span> <span data-ttu-id="fbbaf-106">新しい赤の成分は 0.2 + (1/2) (1) = 0.7 です。</span><span class="sxs-lookup"><span data-stu-id="fbbaf-106">The new red component is 0.2 + (1/2)(1) = 0.7.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fbbaf-107">例</span><span class="sxs-lookup"><span data-stu-id="fbbaf-107">Example</span></span>  
 <span data-ttu-id="fbbaf-108">次の例では、 <xref:System.Drawing.Image> ファイル ColorBars4.bmp からオブジェクトを構築します。</span><span class="sxs-lookup"><span data-stu-id="fbbaf-108">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars4.bmp.</span></span> <span data-ttu-id="fbbaf-109">次に、前の段落で説明されている傾斜変換をイメージ内の各ピクセルに適用します。</span><span class="sxs-lookup"><span data-stu-id="fbbaf-109">Then the code applies the shearing transformation described in the preceding paragraph to each pixel in the image.</span></span>  
  
 <span data-ttu-id="fbbaf-110">次の図は、左側にある元のイメージと右側の傾斜されたイメージを示しています。</span><span class="sxs-lookup"><span data-stu-id="fbbaf-110">The following illustration shows the original image on the left and the sheared image on the right:</span></span>
  
 ![元のイメージと傾斜したイメージを並べて並べた、色付きのストライプを含む2つの四角形。](./media/how-to-shear-colors/original-image-sheared-image.png)  
  
 <span data-ttu-id="fbbaf-112">次の表は、傾斜変換の前後に4つのバーの色ベクトルを示しています。</span><span class="sxs-lookup"><span data-stu-id="fbbaf-112">The following table lists the color vectors for the four bars before and after the shearing transformation.</span></span>  
  
|<span data-ttu-id="fbbaf-113">変更元</span><span class="sxs-lookup"><span data-stu-id="fbbaf-113">Original</span></span>|<span data-ttu-id="fbbaf-114">変形</span><span class="sxs-lookup"><span data-stu-id="fbbaf-114">Sheared</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="fbbaf-115">(0, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="fbbaf-115">(0, 0, 1, 1)</span></span>|<span data-ttu-id="fbbaf-116">(0.5, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="fbbaf-116">(0.5, 0, 1, 1)</span></span>|  
|<span data-ttu-id="fbbaf-117">(0.5, 1, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="fbbaf-117">(0.5, 1, 0.5, 1)</span></span>|<span data-ttu-id="fbbaf-118">(0.75, 1, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="fbbaf-118">(0.75, 1, 0.5, 1)</span></span>|  
|<span data-ttu-id="fbbaf-119">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="fbbaf-119">(1, 1, 0, 1)</span></span>|<span data-ttu-id="fbbaf-120">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="fbbaf-120">(1, 1, 0, 1)</span></span>|  
|<span data-ttu-id="fbbaf-121">(0.4, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="fbbaf-121">(0.4, 0.4, 0.4, 1)</span></span>|<span data-ttu-id="fbbaf-122">(0.6, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="fbbaf-122">(0.6, 0.4, 0.4, 1)</span></span>|  
  
 [!code-csharp[System.Drawing.Misc3#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Misc3/CS/Form1.cs#9)]
 [!code-vb[System.Drawing.Misc3#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Misc3/VB/Form1.vb#9)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fbbaf-123">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="fbbaf-123">Compiling the Code</span></span>  
 <span data-ttu-id="fbbaf-124">前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。</span><span class="sxs-lookup"><span data-stu-id="fbbaf-124">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="fbbaf-125">`ColorBars.bmp`システムで有効なイメージ名とパスで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="fbbaf-125">Replace `ColorBars.bmp` with an image name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbbaf-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="fbbaf-126">See also</span></span>

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="fbbaf-127">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="fbbaf-127">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="fbbaf-128">イメージの色の変更</span><span class="sxs-lookup"><span data-stu-id="fbbaf-128">Recoloring Images</span></span>](recoloring-images.md)
