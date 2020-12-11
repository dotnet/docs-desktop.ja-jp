---
title: 変換を使用した色のスケーリング
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], for scaling colors
- colors [Windows Forms], scaling
ms.assetid: df23c887-7fd6-4b15-ad94-e30b5bd4b849
ms.openlocfilehash: 81c0ddf5b937d604559a9eb1a8b598885546c97f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981179"
---
# <a name="using-transformations-to-scale-colors"></a><span data-ttu-id="9251a-102">変換を使用した色のスケーリング</span><span class="sxs-lookup"><span data-stu-id="9251a-102">Using Transformations to Scale Colors</span></span>
<span data-ttu-id="9251a-103">スケーリング変換は、4つの色のコンポーネントの1つ以上を数値で乗算します。</span><span class="sxs-lookup"><span data-stu-id="9251a-103">A scaling transformation multiplies one or more of the four color components by a number.</span></span> <span data-ttu-id="9251a-104">スケーリングを表すカラーマトリックスのエントリを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="9251a-104">The color matrix entries that represent scaling are given in the following table.</span></span>  
  
|<span data-ttu-id="9251a-105">スケールするコンポーネント</span><span class="sxs-lookup"><span data-stu-id="9251a-105">Component to be scaled</span></span>|<span data-ttu-id="9251a-106">マトリックスエントリ</span><span class="sxs-lookup"><span data-stu-id="9251a-106">Matrix entry</span></span>|  
|----------------------------|------------------|  
|<span data-ttu-id="9251a-107">[赤]</span><span class="sxs-lookup"><span data-stu-id="9251a-107">Red</span></span>|<span data-ttu-id="9251a-108">[0][0]</span><span class="sxs-lookup"><span data-stu-id="9251a-108">[0][0]</span></span>|  
|<span data-ttu-id="9251a-109">[緑]</span><span class="sxs-lookup"><span data-stu-id="9251a-109">Green</span></span>|<span data-ttu-id="9251a-110">[1][1]</span><span class="sxs-lookup"><span data-stu-id="9251a-110">[1][1]</span></span>|  
|<span data-ttu-id="9251a-111">青</span><span class="sxs-lookup"><span data-stu-id="9251a-111">Blue</span></span>|<span data-ttu-id="9251a-112">[2][2]</span><span class="sxs-lookup"><span data-stu-id="9251a-112">[2][2]</span></span>|  
|<span data-ttu-id="9251a-113">[アルファ]</span><span class="sxs-lookup"><span data-stu-id="9251a-113">Alpha</span></span>|<span data-ttu-id="9251a-114">[3][3]</span><span class="sxs-lookup"><span data-stu-id="9251a-114">[3][3]</span></span>|  
  
## <a name="scaling-one-color"></a><span data-ttu-id="9251a-115">1色のスケーリング</span><span class="sxs-lookup"><span data-stu-id="9251a-115">Scaling One Color</span></span>  
 <span data-ttu-id="9251a-116">次の例では、 <xref:System.Drawing.Image> ファイル ColorBars2.bmp からオブジェクトを構築します。</span><span class="sxs-lookup"><span data-stu-id="9251a-116">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars2.bmp.</span></span> <span data-ttu-id="9251a-117">次に、このコードでは、イメージ内の各ピクセルの青の要素を2倍の量でスケーリングします。</span><span class="sxs-lookup"><span data-stu-id="9251a-117">Then the code scales the blue component of each pixel in the image by a factor of 2.</span></span> <span data-ttu-id="9251a-118">元のイメージは、変換されたイメージと共に描画されます。</span><span class="sxs-lookup"><span data-stu-id="9251a-118">The original image is drawn alongside the transformed image.</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.RecoloringImages#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#41)]  
  
 <span data-ttu-id="9251a-119">次の図は、左側にある元のイメージと右側の拡大縮小されたイメージを示しています。</span><span class="sxs-lookup"><span data-stu-id="9251a-119">The following illustration shows the original image on the left and the scaled image on the right:</span></span>  
  
 ![元の色とスケーリングされた色を比較するスクリーンショット。](./media/using-transformations-to-scale-colors/four-bar-scale-one-color.png)  
  
 <span data-ttu-id="9251a-121">次の表は、青のスケーリングの前後に4つのバーの色ベクトルを示しています。</span><span class="sxs-lookup"><span data-stu-id="9251a-121">The following table lists the color vectors for the four bars before and after the blue scaling.</span></span> <span data-ttu-id="9251a-122">4番目のカラーバーの青のコンポーネントが0.8 から0.6 になりました。</span><span class="sxs-lookup"><span data-stu-id="9251a-122">Note that the blue component in the fourth color bar went from 0.8 to 0.6.</span></span> <span data-ttu-id="9251a-123">これは、GDI + によって結果の小数部のみが保持されるためです。</span><span class="sxs-lookup"><span data-stu-id="9251a-123">That is because GDI+ retains only the fractional part of the result.</span></span> <span data-ttu-id="9251a-124">たとえば、(2) (0.8) = 1.6、1.6 の小数部は0.6 です。</span><span class="sxs-lookup"><span data-stu-id="9251a-124">For example, (2)(0.8) = 1.6, and the fractional part of 1.6 is 0.6.</span></span> <span data-ttu-id="9251a-125">小数部のみを保持すると、結果は常に [0, 1] の範囲内になります。</span><span class="sxs-lookup"><span data-stu-id="9251a-125">Retaining only the fractional part ensures that the result is always in the interval [0, 1].</span></span>  
  
|<span data-ttu-id="9251a-126">変更元</span><span class="sxs-lookup"><span data-stu-id="9251a-126">Original</span></span>|<span data-ttu-id="9251a-127">位取り</span><span class="sxs-lookup"><span data-stu-id="9251a-127">Scaled</span></span>|  
|--------------|------------|  
|<span data-ttu-id="9251a-128">(0.4, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="9251a-128">(0.4, 0.4, 0.4, 1)</span></span>|<span data-ttu-id="9251a-129">(0.4, 0.4, 0.8, 1)</span><span class="sxs-lookup"><span data-stu-id="9251a-129">(0.4, 0.4, 0.8, 1)</span></span>|  
|<span data-ttu-id="9251a-130">(0.4, 0.2, 0.2, 1)</span><span class="sxs-lookup"><span data-stu-id="9251a-130">(0.4, 0.2, 0.2, 1)</span></span>|<span data-ttu-id="9251a-131">(0.4, 0.2, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="9251a-131">(0.4, 0.2, 0.4, 1)</span></span>|  
|<span data-ttu-id="9251a-132">(0.2, 0.4, 0.2, 1)</span><span class="sxs-lookup"><span data-stu-id="9251a-132">(0.2, 0.4, 0.2, 1)</span></span>|<span data-ttu-id="9251a-133">(0.2, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="9251a-133">(0.2, 0.4, 0.4, 1)</span></span>|  
|<span data-ttu-id="9251a-134">(0.4, 0.4, 0.8, 1)</span><span class="sxs-lookup"><span data-stu-id="9251a-134">(0.4, 0.4, 0.8, 1)</span></span>|<span data-ttu-id="9251a-135">(0.4, 0.4, 0.6, 1)</span><span class="sxs-lookup"><span data-stu-id="9251a-135">(0.4, 0.4, 0.6, 1)</span></span>|  
  
## <a name="scaling-multiple-colors"></a><span data-ttu-id="9251a-136">複数の色のスケーリング</span><span class="sxs-lookup"><span data-stu-id="9251a-136">Scaling Multiple Colors</span></span>  
 <span data-ttu-id="9251a-137">次の例では、 <xref:System.Drawing.Image> ファイル ColorBars2.bmp からオブジェクトを構築します。</span><span class="sxs-lookup"><span data-stu-id="9251a-137">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars2.bmp.</span></span> <span data-ttu-id="9251a-138">次に、イメージ内の各ピクセルの赤、緑、および青のコンポーネントをスケーリングします。</span><span class="sxs-lookup"><span data-stu-id="9251a-138">Then the code scales the red, green, and blue components of each pixel in the image.</span></span> <span data-ttu-id="9251a-139">赤のコンポーネントは25% スケールダウンされ、緑のコンポーネントは35% にスケールダウンされ、青のコンポーネントは50% にスケールダウンされます。</span><span class="sxs-lookup"><span data-stu-id="9251a-139">The red components are scaled down 25 percent, the green components are scaled down 35 percent, and the blue components are scaled down 50 percent.</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.RecoloringImages#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#42)]  
  
 <span data-ttu-id="9251a-140">次の図は、左側にある元のイメージと右側の拡大縮小されたイメージを示しています。</span><span class="sxs-lookup"><span data-stu-id="9251a-140">The following illustration shows the original image on the left and the scaled image on the right:</span></span>  
  
 ![元の色とスケーリングされた色を比較するスクリーンショット。](./media/using-transformations-to-scale-colors/four-bar-scale-multiple-colors.png)  
  
 <span data-ttu-id="9251a-142">次の表は、赤、緑、および青のスケーリングの前後に4つのバーの色ベクトルを示しています。</span><span class="sxs-lookup"><span data-stu-id="9251a-142">The following table lists the color vectors for the four bars before and after the red, green and blue scaling.</span></span>  
  
|<span data-ttu-id="9251a-143">変更元</span><span class="sxs-lookup"><span data-stu-id="9251a-143">Original</span></span>|<span data-ttu-id="9251a-144">位取り</span><span class="sxs-lookup"><span data-stu-id="9251a-144">Scaled</span></span>|  
|--------------|------------|  
|<span data-ttu-id="9251a-145">(0.6, 0.6, 0.6, 1)</span><span class="sxs-lookup"><span data-stu-id="9251a-145">(0.6, 0.6, 0.6, 1)</span></span>|<span data-ttu-id="9251a-146">(0.45, 0.39, 0.3, 1)</span><span class="sxs-lookup"><span data-stu-id="9251a-146">(0.45, 0.39, 0.3, 1)</span></span>|  
|<span data-ttu-id="9251a-147">(0, 1, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="9251a-147">(0, 1, 1, 1)</span></span>|<span data-ttu-id="9251a-148">(0, 0.65, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="9251a-148">(0, 0.65, 0.5, 1)</span></span>|  
|<span data-ttu-id="9251a-149">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="9251a-149">(1, 1, 0, 1)</span></span>|<span data-ttu-id="9251a-150">(0.75, 0.65, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="9251a-150">(0.75, 0.65, 0, 1)</span></span>|  
|<span data-ttu-id="9251a-151">(1, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="9251a-151">(1, 0, 1, 1)</span></span>|<span data-ttu-id="9251a-152">(0.75, 0, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="9251a-152">(0.75, 0, 0.5, 1)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9251a-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="9251a-153">See also</span></span>

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="9251a-154">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="9251a-154">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="9251a-155">イメージの色の変更</span><span class="sxs-lookup"><span data-stu-id="9251a-155">Recoloring Images</span></span>](recoloring-images.md)
