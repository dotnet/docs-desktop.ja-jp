---
title: GDI+ でのイメージの描画、配置、およびクローン作成
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- raster images [Windows Forms]
- images [Windows Forms], positioning
- drawing [Windows Forms], images
- drawing [Windows Forms], raster images
- images [Windows Forms], cloning
- images [Windows Forms], drawing
- GDI+, drawing images
- GDI+, cloning images
- GDI+, positioning images
ms.assetid: 09f0c07a-19c0-43b4-90a2-862a10545ce8
ms.openlocfilehash: b5f98e7bdef9ff8ed0a4cd0e040cb92a31f30503
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96979843"
---
# <a name="drawing-positioning-and-cloning-images-in-gdi"></a><span data-ttu-id="9c247-102">GDI+ でのイメージの描画、配置、およびクローン作成</span><span class="sxs-lookup"><span data-stu-id="9c247-102">Drawing, Positioning, and Cloning Images in GDI+</span></span>
<span data-ttu-id="9c247-103">クラスを使用して、ラスターイメージを読み込んで表示することができ <xref:System.Drawing.Bitmap> ます。また、クラスを使用して、 <xref:System.Drawing.Imaging.Metafile> ベクターイメージを読み込んで表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="9c247-103">You can use the <xref:System.Drawing.Bitmap> class to load and display raster images, and you can use the <xref:System.Drawing.Imaging.Metafile> class to load and display vector images.</span></span> <span data-ttu-id="9c247-104"><xref:System.Drawing.Bitmap>クラスと <xref:System.Drawing.Imaging.Metafile> クラスは、クラスから継承され <xref:System.Drawing.Image> ます。</span><span class="sxs-lookup"><span data-stu-id="9c247-104">The <xref:System.Drawing.Bitmap> and <xref:System.Drawing.Imaging.Metafile> classes inherit from the <xref:System.Drawing.Image> class.</span></span> <span data-ttu-id="9c247-105">ベクターイメージを表示するには、クラスのインスタンスとが必要 <xref:System.Drawing.Graphics> <xref:System.Drawing.Imaging.Metafile> です。</span><span class="sxs-lookup"><span data-stu-id="9c247-105">To display a vector image, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Imaging.Metafile>.</span></span> <span data-ttu-id="9c247-106">ラスターイメージを表示するには、クラスのインスタンスとが必要 <xref:System.Drawing.Graphics> <xref:System.Drawing.Bitmap> です。</span><span class="sxs-lookup"><span data-stu-id="9c247-106">To display a raster image, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Bitmap>.</span></span> <span data-ttu-id="9c247-107">クラスのインスタンスに <xref:System.Drawing.Graphics> <xref:System.Drawing.Graphics.DrawImage%2A> <xref:System.Drawing.Imaging.Metafile> は、引数としてまたはを受け取るメソッドが用意されて <xref:System.Drawing.Bitmap> います。</span><span class="sxs-lookup"><span data-stu-id="9c247-107">The instance of the <xref:System.Drawing.Graphics> class provides the <xref:System.Drawing.Graphics.DrawImage%2A> method, which receives the <xref:System.Drawing.Imaging.Metafile> or <xref:System.Drawing.Bitmap> as an argument.</span></span>  
  
## <a name="file-types-and-cloning"></a><span data-ttu-id="9c247-108">ファイルの種類と複製</span><span class="sxs-lookup"><span data-stu-id="9c247-108">File Types and Cloning</span></span>  
 <span data-ttu-id="9c247-109">次のコード例では、Climber.jpg ファイルからを構築し、ビットマップを表示する方法を示し <xref:System.Drawing.Bitmap> ます。</span><span class="sxs-lookup"><span data-stu-id="9c247-109">The following code example shows how to construct a <xref:System.Drawing.Bitmap> from the file Climber.jpg and displays the bitmap.</span></span> <span data-ttu-id="9c247-110">イメージの左上隅の宛先ポイント (10, 10) は、2番目と3番目のパラメーターで指定します。</span><span class="sxs-lookup"><span data-stu-id="9c247-110">The destination point for the upper-left corner of the image, (10, 10), is specified in the second and third parameters.</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#11)]  
  
 <span data-ttu-id="9c247-111">次の図は、イメージを示しています。</span><span class="sxs-lookup"><span data-stu-id="9c247-111">The following illustration shows the image.</span></span>  
  
 <span data-ttu-id="9c247-112">![イメージ サンプル](./media/aboutgdip03-art04.gif "AboutGdip03_Art04")</span><span class="sxs-lookup"><span data-stu-id="9c247-112">![Image Sample](./media/aboutgdip03-art04.gif "AboutGdip03_Art04")</span></span>  
  
 <span data-ttu-id="9c247-113">オブジェクトは、 <xref:System.Drawing.Bitmap> さまざまなグラフィックスファイル形式 (BMP、GIF、JPEG、EXIF、PNG、TIFF、ICON) から構築できます。</span><span class="sxs-lookup"><span data-stu-id="9c247-113">You can construct <xref:System.Drawing.Bitmap> objects from a variety of graphics file formats: BMP, GIF, JPEG, EXIF, PNG, TIFF, and ICON.</span></span>  
  
 <span data-ttu-id="9c247-114">次のコード例は、さまざまな <xref:System.Drawing.Bitmap> 種類のファイルからオブジェクトを作成し、ビットマップを表示する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="9c247-114">The following code example shows how to construct <xref:System.Drawing.Bitmap> objects from a variety of file types and then displays the bitmaps.</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#12)]  
  
 <span data-ttu-id="9c247-115">クラスには、 <xref:System.Drawing.Bitmap> <xref:System.Drawing.Bitmap.Clone%2A> 既存ののコピーを作成するために使用できるメソッドが用意されて <xref:System.Drawing.Bitmap> います。</span><span class="sxs-lookup"><span data-stu-id="9c247-115">The <xref:System.Drawing.Bitmap> class provides a <xref:System.Drawing.Bitmap.Clone%2A> method that you can use to make a copy of an existing <xref:System.Drawing.Bitmap>.</span></span> <span data-ttu-id="9c247-116"><xref:System.Drawing.Bitmap.Clone%2A>メソッドには、コピーする元のビットマップの部分を指定するために使用できるソース四角形パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="9c247-116">The <xref:System.Drawing.Bitmap.Clone%2A> method has a source rectangle parameter that you can use to specify the portion of the original bitmap that you want to copy.</span></span> <span data-ttu-id="9c247-117">次のコード例では、 <xref:System.Drawing.Bitmap> 既存のの上半分を複製してを作成する方法を示し <xref:System.Drawing.Bitmap> ます。</span><span class="sxs-lookup"><span data-stu-id="9c247-117">The following code example shows how to create a <xref:System.Drawing.Bitmap> by cloning the top half of an existing <xref:System.Drawing.Bitmap>.</span></span> <span data-ttu-id="9c247-118">次に、両方のイメージが描画されます。</span><span class="sxs-lookup"><span data-stu-id="9c247-118">Then both images are drawn.</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#13)]  
  
 <span data-ttu-id="9c247-119">次の図は、2つのイメージを示しています。</span><span class="sxs-lookup"><span data-stu-id="9c247-119">The following illustration shows the two images.</span></span>  
  
 <span data-ttu-id="9c247-120">![トリミング](./media/aboutgdip03-art05.gif "AboutGdip03_Art05")</span><span class="sxs-lookup"><span data-stu-id="9c247-120">![Cropping](./media/aboutgdip03-art05.gif "AboutGdip03_Art05")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c247-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="9c247-121">See also</span></span>

- [<span data-ttu-id="9c247-122">イメージ、ビットマップ、およびメタファイル</span><span class="sxs-lookup"><span data-stu-id="9c247-122">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="9c247-123">方法: 描画する Graphics オブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="9c247-123">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="9c247-124">イメージ、ビットマップ、アイコン、およびメタファイルの操作</span><span class="sxs-lookup"><span data-stu-id="9c247-124">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
