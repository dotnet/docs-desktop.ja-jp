---
title: '方法: イメージをトリミングおよびスケーリングする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], cropping
- images [Windows Forms], scaling
ms.assetid: 053e3360-bca0-4b25-9afa-0e77a6f17b03
ms.openlocfilehash: 4257431881565f9160f45795111d374cc680dedd
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974409"
---
# <a name="how-to-crop-and-scale-images"></a><span data-ttu-id="b4522-102">方法: イメージをトリミングおよびスケーリングする</span><span class="sxs-lookup"><span data-stu-id="b4522-102">How to: Crop and Scale Images</span></span>
<span data-ttu-id="b4522-103"><xref:System.Drawing.Graphics>クラスにはいくつかのメソッドが用意されて <xref:System.Drawing.Graphics.DrawImage%2A> います。一部のメソッドには、イメージのトリミングとスケーリングに使用できる変換元と変換先の四角形のパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="b4522-103">The <xref:System.Drawing.Graphics> class provides several <xref:System.Drawing.Graphics.DrawImage%2A> methods, some of which have source and destination rectangle parameters that you can use to crop and scale images.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4522-104">例</span><span class="sxs-lookup"><span data-stu-id="b4522-104">Example</span></span>  
 <span data-ttu-id="b4522-105">次の例では、 <xref:System.Drawing.Image> Apple.gif ディスクファイルからオブジェクトを構築します。</span><span class="sxs-lookup"><span data-stu-id="b4522-105">The following example constructs an <xref:System.Drawing.Image> object from the disk file Apple.gif.</span></span> <span data-ttu-id="b4522-106">このコードは、apple イメージ全体を元のサイズで描画します。</span><span class="sxs-lookup"><span data-stu-id="b4522-106">The code draws the entire apple image in its original size.</span></span> <span data-ttu-id="b4522-107">次に、オブジェクトのメソッドを呼び出して、 <xref:System.Drawing.Graphics.DrawImage%2A> <xref:System.Drawing.Graphics> apple イメージの一部を、元の apple イメージよりも大きいコピー先の四角形に描画します。</span><span class="sxs-lookup"><span data-stu-id="b4522-107">The code then calls the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object to draw a portion of the apple image in a destination rectangle that is larger than the original apple image.</span></span>  
  
 <span data-ttu-id="b4522-108">メソッドは、 <xref:System.Drawing.Graphics.DrawImage%2A> ソースの四角形を調べることで、apple のどの部分を描画するかを決定します。これは、3番目、4番目、5番目、および6番目の引数で指定されます。</span><span class="sxs-lookup"><span data-stu-id="b4522-108">The <xref:System.Drawing.Graphics.DrawImage%2A> method determines which portion of the apple to draw by looking at the source rectangle, which is specified by the third, fourth, fifth, and sixth arguments.</span></span> <span data-ttu-id="b4522-109">この場合、apple は幅の75% と高さの75% にトリミングされます。</span><span class="sxs-lookup"><span data-stu-id="b4522-109">In this case, the apple is cropped to 75 percent of its width and 75 percent of its height.</span></span>  
  
 <span data-ttu-id="b4522-110">メソッドは、 <xref:System.Drawing.Graphics.DrawImage%2A> 2 番目の引数で指定されたコピー先の四角形を確認することにより、トリミングされた apple の描画場所とトリミングされた apple のサイズを決定します。</span><span class="sxs-lookup"><span data-stu-id="b4522-110">The <xref:System.Drawing.Graphics.DrawImage%2A> method determines where to draw the cropped apple and how big to make the cropped apple by looking at the destination rectangle, which is specified by the second argument.</span></span> <span data-ttu-id="b4522-111">この場合、コピー先の四角形は、元のイメージよりも30% 広く、30% の高さになります。</span><span class="sxs-lookup"><span data-stu-id="b4522-111">In this case, the destination rectangle is 30 percent wider and 30 percent taller than the original image.</span></span>  
  
 <span data-ttu-id="b4522-112">次の図は、オリジナルの apple と、スケーリングされた、トリミングされた apple を示しています。</span><span class="sxs-lookup"><span data-stu-id="b4522-112">The following illustration shows the original apple and the scaled, cropped apple.</span></span>  
  
 ![元のイメージとトリミングされた同じイメージのスクリーンショット。](./media/how-to-crop-and-scale-images/original-image-cropped-image.png)  
  
 [!code-csharp[System.Drawing.WorkingWithImages#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.WorkingWithImages#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b4522-114">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="b4522-114">Compiling the Code</span></span>  
 <span data-ttu-id="b4522-115">前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。</span><span class="sxs-lookup"><span data-stu-id="b4522-115">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="b4522-116">`Apple.gif`は、システムで有効なイメージファイル名とパスに置き換えてください。</span><span class="sxs-lookup"><span data-stu-id="b4522-116">Make sure to replace `Apple.gif` with an image file name and path that are valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4522-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="b4522-117">See also</span></span>

- [<span data-ttu-id="b4522-118">イメージ、ビットマップ、およびメタファイル</span><span class="sxs-lookup"><span data-stu-id="b4522-118">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="b4522-119">イメージ、ビットマップ、アイコン、およびメタファイルの操作</span><span class="sxs-lookup"><span data-stu-id="b4522-119">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
