---
title: '方法: イメージの色を変換する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [Windows Forms], changing colors
- images [Windows Forms], changing colors
- image colors [Windows Forms]
ms.assetid: 2106fb9a-4d60-4dcf-9220-9f189a6c4d19
ms.openlocfilehash: fb9ec30c06740214b8dc6b65d32eba4e2920c89b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981740"
---
# <a name="how-to-translate-image-colors"></a><span data-ttu-id="15d09-102">方法: イメージの色を変換する</span><span class="sxs-lookup"><span data-stu-id="15d09-102">How to: Translate Image Colors</span></span>
<span data-ttu-id="15d09-103">変換では、4つのカラーコンポーネントの1つ以上に値が追加されます。</span><span class="sxs-lookup"><span data-stu-id="15d09-103">A translation adds a value to one or more of the four color components.</span></span> <span data-ttu-id="15d09-104">次の表は、翻訳を表すカラーマトリックスエントリを示しています。</span><span class="sxs-lookup"><span data-stu-id="15d09-104">The color matrix entries that represent translations are given in the following table.</span></span>  
  
|<span data-ttu-id="15d09-105">変換するコンポーネント</span><span class="sxs-lookup"><span data-stu-id="15d09-105">Component to be translated</span></span>|<span data-ttu-id="15d09-106">マトリックスエントリ</span><span class="sxs-lookup"><span data-stu-id="15d09-106">Matrix entry</span></span>|  
|--------------------------------|------------------|  
|<span data-ttu-id="15d09-107">[赤]</span><span class="sxs-lookup"><span data-stu-id="15d09-107">Red</span></span>|<span data-ttu-id="15d09-108">[4][0]</span><span class="sxs-lookup"><span data-stu-id="15d09-108">[4][0]</span></span>|  
|<span data-ttu-id="15d09-109">[緑]</span><span class="sxs-lookup"><span data-stu-id="15d09-109">Green</span></span>|<span data-ttu-id="15d09-110">[4][1]</span><span class="sxs-lookup"><span data-stu-id="15d09-110">[4][1]</span></span>|  
|<span data-ttu-id="15d09-111">青</span><span class="sxs-lookup"><span data-stu-id="15d09-111">Blue</span></span>|<span data-ttu-id="15d09-112">[4][2]</span><span class="sxs-lookup"><span data-stu-id="15d09-112">[4][2]</span></span>|  
|<span data-ttu-id="15d09-113">[アルファ]</span><span class="sxs-lookup"><span data-stu-id="15d09-113">Alpha</span></span>|<span data-ttu-id="15d09-114">[4][3]</span><span class="sxs-lookup"><span data-stu-id="15d09-114">[4][3]</span></span>|  
  
## <a name="example"></a><span data-ttu-id="15d09-115">例</span><span class="sxs-lookup"><span data-stu-id="15d09-115">Example</span></span>  
 <span data-ttu-id="15d09-116">次の例では、 <xref:System.Drawing.Image> ファイル ColorBars.bmp からオブジェクトを構築します。</span><span class="sxs-lookup"><span data-stu-id="15d09-116">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars.bmp.</span></span> <span data-ttu-id="15d09-117">次に、コードは、イメージ内の各ピクセルの赤の部分に0.75 を追加します。</span><span class="sxs-lookup"><span data-stu-id="15d09-117">Then the code adds 0.75 to the red component of each pixel in the image.</span></span> <span data-ttu-id="15d09-118">元のイメージは、変換されたイメージと共に描画されます。</span><span class="sxs-lookup"><span data-stu-id="15d09-118">The original image is drawn alongside the transformed image.</span></span>  
  
 <span data-ttu-id="15d09-119">次の図は、左側にある元のイメージと、右側の変換されたイメージを示しています。</span><span class="sxs-lookup"><span data-stu-id="15d09-119">The following illustration shows the original image on the left and the transformed image on the right:</span></span>  
  
 ![元のイメージと変換されたイメージのスクリーンショット。](./media/how-to-translate-image-colors/original-image-translate-colors.png)  
  
 <span data-ttu-id="15d09-121">次の表は、赤の平行移動の前後の4つのバーの色ベクトルを示しています。</span><span class="sxs-lookup"><span data-stu-id="15d09-121">The following table lists the color vectors for the four bars before and after the red translation.</span></span> <span data-ttu-id="15d09-122">色成分の最大値は1であるため、2番目の行の赤の成分は変化しないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="15d09-122">Note that because the maximum value for a color component is 1, the red component in the second row does not change.</span></span> <span data-ttu-id="15d09-123">(同様に、カラーコンポーネントの最小値は0です)。</span><span class="sxs-lookup"><span data-stu-id="15d09-123">(Similarly, the minimum value for a color component is 0.)</span></span>  
  
|<span data-ttu-id="15d09-124">変更元</span><span class="sxs-lookup"><span data-stu-id="15d09-124">Original</span></span>|<span data-ttu-id="15d09-125">変換後</span><span class="sxs-lookup"><span data-stu-id="15d09-125">Translated</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="15d09-126">黒 (0、0、0、1)</span><span class="sxs-lookup"><span data-stu-id="15d09-126">Black (0, 0, 0, 1)</span></span>|<span data-ttu-id="15d09-127">(0.75, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="15d09-127">(0.75, 0, 0, 1)</span></span>|  
|<span data-ttu-id="15d09-128">赤 (1、0、0、1)</span><span class="sxs-lookup"><span data-stu-id="15d09-128">Red (1, 0, 0, 1)</span></span>|<span data-ttu-id="15d09-129">(1, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="15d09-129">(1, 0, 0, 1)</span></span>|  
|<span data-ttu-id="15d09-130">緑 (0、1、0、1)</span><span class="sxs-lookup"><span data-stu-id="15d09-130">Green (0, 1, 0, 1)</span></span>|<span data-ttu-id="15d09-131">(0.75, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="15d09-131">(0.75, 1, 0, 1)</span></span>|  
|<span data-ttu-id="15d09-132">Blue (0, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="15d09-132">Blue (0, 0, 1, 1)</span></span>|<span data-ttu-id="15d09-133">(0.75, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="15d09-133">(0.75, 0, 1, 1)</span></span>|  
  
 [!code-csharp[System.Drawing.RecoloringImages#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.RecoloringImages#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="15d09-134">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="15d09-134">Compiling the Code</span></span>  
 <span data-ttu-id="15d09-135">前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。</span><span class="sxs-lookup"><span data-stu-id="15d09-135">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="15d09-136">を、 `ColorBars.bmp` システムで有効なイメージファイル名とパスに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="15d09-136">Replace `ColorBars.bmp` with an image file name and path that are valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15d09-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="15d09-137">See also</span></span>

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="15d09-138">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="15d09-138">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="15d09-139">イメージの色の変更</span><span class="sxs-lookup"><span data-stu-id="15d09-139">Recoloring Images</span></span>](recoloring-images.md)
