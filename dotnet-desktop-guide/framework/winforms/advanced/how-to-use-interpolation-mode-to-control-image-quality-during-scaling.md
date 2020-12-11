---
title: '方法: 補間モードを使用してスケーリング時の画質を制御する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interpolation mode [Windows Forms], controlling image quality
- images [Windows Forms], scaling
- images [Windows Forms], controlling quality
ms.assetid: fde9bccf-8aa5-4b0d-ba4b-788740627b02
ms.openlocfilehash: ab0ff93b3ee26467c0de448efd31b698167f95c2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981720"
---
# <a name="how-to-use-interpolation-mode-to-control-image-quality-during-scaling"></a><span data-ttu-id="ff3cf-102">方法: 補間モードを使用してスケーリング時の画質を制御する</span><span class="sxs-lookup"><span data-stu-id="ff3cf-102">How to: Use Interpolation Mode to Control Image Quality During Scaling</span></span>
<span data-ttu-id="ff3cf-103">オブジェクトの補間モードは、 <xref:System.Drawing.Graphics> GDI + によるイメージのスケーリング (拡大と縮小) に影響します。</span><span class="sxs-lookup"><span data-stu-id="ff3cf-103">The interpolation mode of a <xref:System.Drawing.Graphics> object influences the way GDI+ scales (stretches and shrinks) images.</span></span> <span data-ttu-id="ff3cf-104"><xref:System.Drawing.Drawing2D.InterpolationMode>列挙体は、次の一覧に示すように、複数の補間モードを定義します。</span><span class="sxs-lookup"><span data-stu-id="ff3cf-104">The <xref:System.Drawing.Drawing2D.InterpolationMode> enumeration defines several interpolation modes, some of which are shown in the following list:</span></span>  
  
- <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor>  
  
- <xref:System.Drawing.Drawing2D.InterpolationMode.Bilinear>  
  
- <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBilinear>  
  
- <xref:System.Drawing.Drawing2D.InterpolationMode.Bicubic>  
  
- <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic>  
  
 <span data-ttu-id="ff3cf-105">画像を拡大するには、元のイメージ内の各ピクセルが、大きな画像のピクセルのグループにマップされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff3cf-105">To stretch an image, each pixel in the original image must be mapped to a group of pixels in the larger image.</span></span> <span data-ttu-id="ff3cf-106">イメージを圧縮するには、元のイメージのピクセルグループを小さいイメージの1ピクセルにマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff3cf-106">To shrink an image, groups of pixels in the original image must be mapped to single pixels in the smaller image.</span></span> <span data-ttu-id="ff3cf-107">これらのマッピングを実行するアルゴリズムの効果によって、スケーリングされたイメージの品質が決まります。</span><span class="sxs-lookup"><span data-stu-id="ff3cf-107">The effectiveness of the algorithms that perform these mappings determines the quality of a scaled image.</span></span> <span data-ttu-id="ff3cf-108">高品質のスケーリングされたイメージを生成するアルゴリズムでは、より多くの処理時間が必要になる傾向があります。</span><span class="sxs-lookup"><span data-stu-id="ff3cf-108">Algorithms that produce higher-quality scaled images tend to require more processing time.</span></span> <span data-ttu-id="ff3cf-109">上記の一覧で <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor> は、は最も品質の低いモードで、 <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic> は最高品質モードです。</span><span class="sxs-lookup"><span data-stu-id="ff3cf-109">In the preceding list, <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor> is the lowest-quality mode and <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic> is the highest-quality mode.</span></span>  
  
 <span data-ttu-id="ff3cf-110">補間モードを設定するには、列挙体のいずれかのメンバーを <xref:System.Drawing.Drawing2D.InterpolationMode> <xref:System.Drawing.Graphics.InterpolationMode%2A> オブジェクトのプロパティに割り当て <xref:System.Drawing.Graphics> ます。</span><span class="sxs-lookup"><span data-stu-id="ff3cf-110">To set the interpolation mode, assign one of the members of the <xref:System.Drawing.Drawing2D.InterpolationMode> enumeration to the <xref:System.Drawing.Graphics.InterpolationMode%2A> property of a <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff3cf-111">例</span><span class="sxs-lookup"><span data-stu-id="ff3cf-111">Example</span></span>  
 <span data-ttu-id="ff3cf-112">次の例では、イメージを描画し、3つの異なる補間モードでイメージを縮小します。</span><span class="sxs-lookup"><span data-stu-id="ff3cf-112">The following example draws an image and then shrinks the image with three different interpolation modes.</span></span>  
  
 <span data-ttu-id="ff3cf-113">次の図は、元のイメージと、3つの小さいイメージを示しています。</span><span class="sxs-lookup"><span data-stu-id="ff3cf-113">The following illustration shows the original image and the three smaller images.</span></span>  
  
 ![さまざまな補間設定のイメージを示すスクリーンショット。](./media/how-to-use-interpolation-mode-to-control-image-quality-during-scaling/varied-interpolation-settings.png)  
  
 [!code-csharp[System.Drawing.WorkingWithImages#81](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#81)]
 [!code-vb[System.Drawing.WorkingWithImages#81](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#81)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ff3cf-115">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="ff3cf-115">Compiling the Code</span></span>  
 <span data-ttu-id="ff3cf-116">前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。</span><span class="sxs-lookup"><span data-stu-id="ff3cf-116">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff3cf-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="ff3cf-117">See also</span></span>

- [<span data-ttu-id="ff3cf-118">イメージ、ビットマップ、およびメタファイル</span><span class="sxs-lookup"><span data-stu-id="ff3cf-118">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="ff3cf-119">イメージ、ビットマップ、アイコン、およびメタファイルの操作</span><span class="sxs-lookup"><span data-stu-id="ff3cf-119">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
