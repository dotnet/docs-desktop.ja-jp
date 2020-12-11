---
title: GDI+ でのイメージのトリミングおよびスケーリング
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, scaling images
- GDI+, cropping images
- images [Windows Forms], cropping
- compressing data [Windows Forms], images
- images [Windows Forms], expansion
- images [Windows Forms], scaling
- rectangles [Windows Forms], source
- rectangles [Windows Forms], destination
- images [Windows Forms], compression
ms.assetid: ad5daf26-005f-45bc-a2af-e0e97777a21a
ms.openlocfilehash: c3cdb06e99770808461f9266fb5f07df9074149b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96975038"
---
# <a name="cropping-and-scaling-images-in-gdi"></a><span data-ttu-id="5e496-102">GDI+ でのイメージのトリミングおよびスケーリング</span><span class="sxs-lookup"><span data-stu-id="5e496-102">Cropping and Scaling Images in GDI+</span></span>
<span data-ttu-id="5e496-103"><xref:System.Drawing.Graphics.DrawImage%2A>クラスのメソッドを使用し <xref:System.Drawing.Graphics> て、ベクターイメージとラスターイメージを描画し、配置することができます。</span><span class="sxs-lookup"><span data-stu-id="5e496-103">You can use the <xref:System.Drawing.Graphics.DrawImage%2A> method of the <xref:System.Drawing.Graphics> class to draw and position vector images and raster images.</span></span> <span data-ttu-id="5e496-104"><xref:System.Drawing.Graphics.DrawImage%2A> はオーバーロードされたメソッドであるため、いくつかの方法で引数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5e496-104"><xref:System.Drawing.Graphics.DrawImage%2A> is an overloaded method, so there are several ways you can supply it with arguments.</span></span>  
  
## <a name="drawimage-variations"></a><span data-ttu-id="5e496-105">DrawImage のバリエーション</span><span class="sxs-lookup"><span data-stu-id="5e496-105">DrawImage Variations</span></span>  
 <span data-ttu-id="5e496-106">メソッドの1つのバリエーション <xref:System.Drawing.Graphics.DrawImage%2A> は、とを受け取り <xref:System.Drawing.Bitmap> <xref:System.Drawing.Rectangle> ます。</span><span class="sxs-lookup"><span data-stu-id="5e496-106">One variation of the <xref:System.Drawing.Graphics.DrawImage%2A> method receives a <xref:System.Drawing.Bitmap> and a <xref:System.Drawing.Rectangle>.</span></span> <span data-ttu-id="5e496-107">四角形は、描画操作の対象を指定します。つまり、イメージを描画する四角形を指定します。</span><span class="sxs-lookup"><span data-stu-id="5e496-107">The rectangle specifies the destination for the drawing operation; that is, it specifies the rectangle in which to draw the image.</span></span> <span data-ttu-id="5e496-108">コピー先の四角形のサイズが元のイメージのサイズと異なる場合、イメージはコピー先の四角形に合わせて拡大縮小されます。</span><span class="sxs-lookup"><span data-stu-id="5e496-108">If the size of the destination rectangle is different from the size of the original image, the image is scaled to fit the destination rectangle.</span></span> <span data-ttu-id="5e496-109">次のコード例は、同じイメージを3回描画する方法を示しています。1回はスケーリングせず、1回は拡張を、もう1回は圧縮を使用します。</span><span class="sxs-lookup"><span data-stu-id="5e496-109">The following code example shows how to draw the same image three times: once with no scaling, once with an expansion, and once with a compression:</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#31)]  
  
 <span data-ttu-id="5e496-110">次の図は、3つの画像を示しています。</span><span class="sxs-lookup"><span data-stu-id="5e496-110">The following illustration shows the three pictures.</span></span>  
  
 <span data-ttu-id="5e496-111">![スケーリング](./media/aboutgdip03-art06.gif "AboutGdip03_Art06")</span><span class="sxs-lookup"><span data-stu-id="5e496-111">![Scaling](./media/aboutgdip03-art06.gif "AboutGdip03_Art06")</span></span>  
  
 <span data-ttu-id="5e496-112">メソッドの一部のバリエーションには、 <xref:System.Drawing.Graphics.DrawImage%2A> 変換元の四角形のパラメーターと、変換先の四角形のパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="5e496-112">Some variations of the <xref:System.Drawing.Graphics.DrawImage%2A> method have a source-rectangle parameter as well as a destination-rectangle parameter.</span></span> <span data-ttu-id="5e496-113">Source 四角形パラメーターは、描画する元のイメージの部分を指定します。</span><span class="sxs-lookup"><span data-stu-id="5e496-113">The source-rectangle parameter specifies the portion of the original image to draw.</span></span> <span data-ttu-id="5e496-114">コピー先の四角形は、イメージのその部分を描画する四角形を指定します。</span><span class="sxs-lookup"><span data-stu-id="5e496-114">The destination rectangle specifies the rectangle in which to draw that portion of the image.</span></span> <span data-ttu-id="5e496-115">コピー先の四角形のサイズがコピー元の四角形のサイズと異なる場合、画像はコピー先の四角形に合わせて拡大縮小されます。</span><span class="sxs-lookup"><span data-stu-id="5e496-115">If the size of the destination rectangle is different from the size of the source rectangle, the picture is scaled to fit the destination rectangle.</span></span>  
  
 <span data-ttu-id="5e496-116">ファイル Runner.jpg からを構築する方法を次のコード例に示し <xref:System.Drawing.Bitmap> ます。</span><span class="sxs-lookup"><span data-stu-id="5e496-116">The following code example shows how to construct a <xref:System.Drawing.Bitmap> from the file Runner.jpg.</span></span> <span data-ttu-id="5e496-117">イメージ全体が、(0, 0) にスケーリングなしで描画されます。</span><span class="sxs-lookup"><span data-stu-id="5e496-117">The entire image is drawn with no scaling at (0, 0).</span></span> <span data-ttu-id="5e496-118">次に、イメージの小さな部分が2回描画されます。1回は圧縮を、もう1回は拡張です。</span><span class="sxs-lookup"><span data-stu-id="5e496-118">Then a small portion of the image is drawn twice: once with a compression and once with an expansion.</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#32)]  
  
 <span data-ttu-id="5e496-119">次の図は、スケールされていないイメージと、圧縮されたイメージ部分と展開されたイメージ部分を示しています。</span><span class="sxs-lookup"><span data-stu-id="5e496-119">The following illustration shows the unscaled image, and the compressed and expanded image portions.</span></span>  
  
 <span data-ttu-id="5e496-120">![トリミングとスケーリング](./media/aboutgdip03-art07.gif "AboutGdip03_Art07")</span><span class="sxs-lookup"><span data-stu-id="5e496-120">![Cropping and Scaling](./media/aboutgdip03-art07.gif "AboutGdip03_Art07")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e496-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="5e496-121">See also</span></span>

- [<span data-ttu-id="5e496-122">イメージ、ビットマップ、およびメタファイル</span><span class="sxs-lookup"><span data-stu-id="5e496-122">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="5e496-123">イメージ、ビットマップ、アイコン、およびメタファイルの操作</span><span class="sxs-lookup"><span data-stu-id="5e496-123">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
