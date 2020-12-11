---
title: '方法: イメージを回転、反転、および傾斜させる'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], reflecting
- images [Windows Forms], rotating
- images [Windows Forms], skewing
ms.assetid: a3bf97eb-63ed-425a-ba07-dcc65efb567c
ms.openlocfilehash: 80ac92d545d9be7a4a611038eaaadbbdbe2e8ecf
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981287"
---
# <a name="how-to-rotate-reflect-and-skew-images"></a><span data-ttu-id="b1085-102">方法: イメージを回転、反転、および傾斜させる</span><span class="sxs-lookup"><span data-stu-id="b1085-102">How to: Rotate, Reflect, and Skew Images</span></span>
<span data-ttu-id="b1085-103">イメージの回転、反転、および傾斜を行うには、元のイメージの左上、右上、左下の各コーナーのコピー先のポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="b1085-103">You can rotate, reflect, and skew an image by specifying destination points for the upper-left, upper-right, and lower-left corners of the original image.</span></span> <span data-ttu-id="b1085-104">3つのコピー先のポイントは、元の四角形のイメージを平行四辺形にマップするアフィン変換を決定します。</span><span class="sxs-lookup"><span data-stu-id="b1085-104">The three destination points determine an affine transformation that maps the original rectangular image to a parallelogram.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1085-105">例</span><span class="sxs-lookup"><span data-stu-id="b1085-105">Example</span></span>  
 <span data-ttu-id="b1085-106">たとえば、元の画像が左上隅が (0, 0)、右上隅が (100, 0)、左下隅 (0, 50) の四角形であるとします。</span><span class="sxs-lookup"><span data-stu-id="b1085-106">For example, suppose the original image is a rectangle with upper-left corner at (0, 0), upper-right corner at (100, 0), and lower-left corner at (0, 50).</span></span> <span data-ttu-id="b1085-107">ここで、次のように3つの点をターゲットポイントにマップするとします。</span><span class="sxs-lookup"><span data-stu-id="b1085-107">Now suppose you map those three points to destination points as follows.</span></span>  
  
|<span data-ttu-id="b1085-108">元のポイント</span><span class="sxs-lookup"><span data-stu-id="b1085-108">Original point</span></span>|<span data-ttu-id="b1085-109">コピー先のポイント</span><span class="sxs-lookup"><span data-stu-id="b1085-109">Destination point</span></span>|  
|--------------------|-----------------------|  
|<span data-ttu-id="b1085-110">左上 (0, 0)</span><span class="sxs-lookup"><span data-stu-id="b1085-110">Upper-left (0, 0)</span></span>|<span data-ttu-id="b1085-111">(200, 20)</span><span class="sxs-lookup"><span data-stu-id="b1085-111">(200, 20)</span></span>|  
|<span data-ttu-id="b1085-112">右上 (100、0)</span><span class="sxs-lookup"><span data-stu-id="b1085-112">Upper-right (100, 0)</span></span>|<span data-ttu-id="b1085-113">(110, 100)</span><span class="sxs-lookup"><span data-stu-id="b1085-113">(110, 100)</span></span>|  
|<span data-ttu-id="b1085-114">左下 (0, 50)</span><span class="sxs-lookup"><span data-stu-id="b1085-114">Lower-left (0, 50)</span></span>|<span data-ttu-id="b1085-115">(250, 30)</span><span class="sxs-lookup"><span data-stu-id="b1085-115">(250, 30)</span></span>|  
  
 <span data-ttu-id="b1085-116">次の図は、元のイメージと平行四辺形にマップされているイメージを示しています。</span><span class="sxs-lookup"><span data-stu-id="b1085-116">The following illustration shows the original image and the image mapped to the parallelogram.</span></span> <span data-ttu-id="b1085-117">元のイメージは、傾斜、反射、回転、および翻訳されています。</span><span class="sxs-lookup"><span data-stu-id="b1085-117">The original image has been skewed, reflected, rotated, and translated.</span></span> <span data-ttu-id="b1085-118">元のイメージの上端に沿った x 軸は、(200, 20) と (110, 100) を介して実行される行にマップされます。</span><span class="sxs-lookup"><span data-stu-id="b1085-118">The x-axis along the top edge of the original image is mapped to the line that runs through (200, 20) and (110, 100).</span></span> <span data-ttu-id="b1085-119">元のイメージの左端に沿った y 軸は、(200, 20) と (250, 30) を介して実行される行にマップされます。</span><span class="sxs-lookup"><span data-stu-id="b1085-119">The y-axis along the left edge of the original image is mapped to the line that runs through (200, 20) and (250, 30).</span></span>  
  
 ![平行四辺形にマップされた元のイメージとイメージ。](./media/how-to-rotate-reflect-and-skew-images/reflected-skewed-rotated-illustration.gif)  
  
 <span data-ttu-id="b1085-121">次の図は、写真イメージに適用される同様の変換を示しています。</span><span class="sxs-lookup"><span data-stu-id="b1085-121">The following illustration shows a similar transformation applied to a photographic image:</span></span>  
  
 ![平行四辺形にマップされているクライマと画像の画像。](./media/how-to-rotate-reflect-and-skew-images/reflected-skewed-rotated-photo.png)  
  
 <span data-ttu-id="b1085-123">次の図は、メタファイルに適用される同様の変換を示しています。</span><span class="sxs-lookup"><span data-stu-id="b1085-123">The following illustration shows a similar transformation applied to a metafile:</span></span>  
  
 ![平行四辺形にマップされた図形とテキストの図。](./media/how-to-rotate-reflect-and-skew-images/reflected-skewed-rotated-metafile.png)  
  
 <span data-ttu-id="b1085-125">次の例では、最初の図に示されているイメージを生成します。</span><span class="sxs-lookup"><span data-stu-id="b1085-125">The following example produces the images shown in the first illustration.</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.WorkingWithImages#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b1085-126">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="b1085-126">Compiling the Code</span></span>  
 <span data-ttu-id="b1085-127">前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。</span><span class="sxs-lookup"><span data-stu-id="b1085-127">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="b1085-128">`Stripes.bmp`は、システムで有効なイメージへのパスに置き換えてください。</span><span class="sxs-lookup"><span data-stu-id="b1085-128">Make sure to replace `Stripes.bmp` with the path to an image that is valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1085-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="b1085-129">See also</span></span>

- [<span data-ttu-id="b1085-130">イメージ、ビットマップ、アイコン、およびメタファイルの操作</span><span class="sxs-lookup"><span data-stu-id="b1085-130">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
