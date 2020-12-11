---
title: '方法: カラー リマップ テーブルを使用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- color tables [Windows Forms], remapping colors with
- custom colors [Windows Forms], creating with color remap table
- color remap tables [Windows Forms], using
ms.assetid: 977df1ce-8665-42d4-9fb1-ef7f0ff63419
ms.openlocfilehash: 360ec30563ee5001d784dc7c4ccdb50563867c29
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981236"
---
# <a name="how-to-use-a-color-remap-table"></a><span data-ttu-id="dd57c-102">方法: カラー リマップ テーブルを使用する</span><span class="sxs-lookup"><span data-stu-id="dd57c-102">How to: Use a Color Remap Table</span></span>
<span data-ttu-id="dd57c-103">再マップとは、カラーリマップテーブルに従ってイメージの色を変換するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="dd57c-103">Remapping is the process of converting the colors in an image according to a color remap table.</span></span> <span data-ttu-id="dd57c-104">カラーリマップテーブルは、オブジェクトの配列です <xref:System.Drawing.Imaging.ColorMap> 。</span><span class="sxs-lookup"><span data-stu-id="dd57c-104">The color remap table is an array of <xref:System.Drawing.Imaging.ColorMap> objects.</span></span> <span data-ttu-id="dd57c-105"><xref:System.Drawing.Imaging.ColorMap>配列内の各オブジェクトには、 <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> プロパティとプロパティがあり <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="dd57c-105">Each <xref:System.Drawing.Imaging.ColorMap> object in the array has an <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> property and a <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> property.</span></span>  
  
 <span data-ttu-id="dd57c-106">GDI + でイメージを描画すると、イメージの各ピクセルが古い色の配列と比較されます。</span><span class="sxs-lookup"><span data-stu-id="dd57c-106">When GDI+ draws an image, each pixel of the image is compared to the array of old colors.</span></span> <span data-ttu-id="dd57c-107">ピクセルの色が古い色と一致する場合、色は対応する新しい色に変更されます。</span><span class="sxs-lookup"><span data-stu-id="dd57c-107">If a pixel's color matches an old color, its color is changed to the corresponding new color.</span></span> <span data-ttu-id="dd57c-108">色はレンダリングの場合にのみ変更されます。イメージ自体の色の値 ( <xref:System.Drawing.Image> またはオブジェクトに格納され <xref:System.Drawing.Bitmap> ます) は変更されません。</span><span class="sxs-lookup"><span data-stu-id="dd57c-108">The colors are changed only for rendering — the color values of the image itself (stored in an <xref:System.Drawing.Image> or <xref:System.Drawing.Bitmap> object) are not changed.</span></span>  
  
 <span data-ttu-id="dd57c-109">リマップされたイメージを描画するには、オブジェクトの配列を初期化し <xref:System.Drawing.Imaging.ColorMap> ます。</span><span class="sxs-lookup"><span data-stu-id="dd57c-109">To draw a remapped image, initialize an array of <xref:System.Drawing.Imaging.ColorMap> objects.</span></span> <span data-ttu-id="dd57c-110">オブジェクトのメソッドにその配列を渡し <xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A> <xref:System.Drawing.Imaging.ImageAttributes> 、オブジェクト <xref:System.Drawing.Imaging.ImageAttributes> のメソッドにオブジェクトを渡し <xref:System.Drawing.Graphics.DrawImage%2A> <xref:System.Drawing.Graphics> ます。</span><span class="sxs-lookup"><span data-stu-id="dd57c-110">Pass that array to the <xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A> method of an <xref:System.Drawing.Imaging.ImageAttributes> object, and then pass the <xref:System.Drawing.Imaging.ImageAttributes> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd57c-111">例</span><span class="sxs-lookup"><span data-stu-id="dd57c-111">Example</span></span>  
 <span data-ttu-id="dd57c-112">次の例では、 <xref:System.Drawing.Image> ファイル RemapInput.bmp からオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="dd57c-112">The following example creates an <xref:System.Drawing.Image> object from the file RemapInput.bmp.</span></span> <span data-ttu-id="dd57c-113">このコードでは、1つのオブジェクトで構成されるカラーリマップテーブルを作成し <xref:System.Drawing.Imaging.ColorMap> ます。</span><span class="sxs-lookup"><span data-stu-id="dd57c-113">The code creates a color remap table that consists of a single <xref:System.Drawing.Imaging.ColorMap> object.</span></span> <span data-ttu-id="dd57c-114"><xref:System.Drawing.Imaging.ColorMap.OldColor%2A>オブジェクトのプロパティは `ColorRemap` 赤、 <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> プロパティは青色です。</span><span class="sxs-lookup"><span data-stu-id="dd57c-114">The <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> property of the `ColorRemap` object is red, and the <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> property is blue.</span></span> <span data-ttu-id="dd57c-115">イメージは再マップせずに1回だけ描画され、再マップされます。</span><span class="sxs-lookup"><span data-stu-id="dd57c-115">The image is drawn once without remapping and once with remapping.</span></span> <span data-ttu-id="dd57c-116">再マッププロセスでは、赤のすべてのピクセルが青に変わります。</span><span class="sxs-lookup"><span data-stu-id="dd57c-116">The remapping process changes all the red pixels to blue.</span></span>  
  
 <span data-ttu-id="dd57c-117">次の図は、左側にある元のイメージと右側に再マップされたイメージを示しています。</span><span class="sxs-lookup"><span data-stu-id="dd57c-117">The following illustration shows the original image on the left and the remapped image on the right.</span></span>  
  
 ![元のイメージと再マップされたイメージを示すスクリーンショット。](./media/how-to-use-a-color-remap-table/original-image-remap-colors.png)  
  
 [!code-csharp[System.Drawing.RecoloringImages#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.RecoloringImages#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="dd57c-119">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="dd57c-119">Compiling the Code</span></span>  
 <span data-ttu-id="dd57c-120">前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。</span><span class="sxs-lookup"><span data-stu-id="dd57c-120">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd57c-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="dd57c-121">See also</span></span>

- [<span data-ttu-id="dd57c-122">イメージの色の変更</span><span class="sxs-lookup"><span data-stu-id="dd57c-122">Recoloring Images</span></span>](recoloring-images.md)
- [<span data-ttu-id="dd57c-123">イメージ、ビットマップ、およびメタファイル</span><span class="sxs-lookup"><span data-stu-id="dd57c-123">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
