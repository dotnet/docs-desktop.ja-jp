---
title: '方法: 既存のビットマップを画面に描画する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [Windows Forms], displaying in Windows Forms
- bitmaps [Windows Forms], loading in Windows Forms applications
- images [Windows Forms], displaying on Windows Forms
ms.assetid: 5bc558d7-b326-4050-a834-b8600da0de95
ms.openlocfilehash: 90511adf9caffe7952e270d6fe32dd85162a29d7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981391"
---
# <a name="how-to-draw-an-existing-bitmap-to-the-screen"></a><span data-ttu-id="332ae-102">方法: 既存のビットマップを画面に描画する</span><span class="sxs-lookup"><span data-stu-id="332ae-102">How to: Draw an Existing Bitmap to the Screen</span></span>
<span data-ttu-id="332ae-103">画面には、既存のイメージを簡単に描画できます。</span><span class="sxs-lookup"><span data-stu-id="332ae-103">You can easily draw an existing image on the screen.</span></span> <span data-ttu-id="332ae-104">まず <xref:System.Drawing.Bitmap> 、ファイル名を受け取るビットマップコンストラクターを使用して、オブジェクトを作成する必要があり <xref:System.Drawing.Bitmap.%23ctor%28System.String%29> ます。</span><span class="sxs-lookup"><span data-stu-id="332ae-104">First you need to create a <xref:System.Drawing.Bitmap> object by using the bitmap constructor that takes a file name, <xref:System.Drawing.Bitmap.%23ctor%28System.String%29>.</span></span> <span data-ttu-id="332ae-105">このコンストラクターは、BMP、GIF、JPEG、PNG、TIFF など、いくつかの異なるファイル形式のイメージを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="332ae-105">This constructor accepts images with several different file formats, including BMP, GIF, JPEG, PNG, and TIFF.</span></span> <span data-ttu-id="332ae-106">オブジェクトを作成したら <xref:System.Drawing.Bitmap> 、そのオブジェクトを <xref:System.Drawing.Bitmap> <xref:System.Drawing.Graphics.DrawImage%2A> オブジェクトのメソッドに渡し <xref:System.Drawing.Graphics> ます。</span><span class="sxs-lookup"><span data-stu-id="332ae-106">After you have created the <xref:System.Drawing.Bitmap> object, pass that <xref:System.Drawing.Bitmap> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="332ae-107">例</span><span class="sxs-lookup"><span data-stu-id="332ae-107">Example</span></span>  
 <span data-ttu-id="332ae-108">この例では、 <xref:System.Drawing.Bitmap> JPEG ファイルからオブジェクトを作成し、(60, 10) の左上隅にビットマップを描画します。</span><span class="sxs-lookup"><span data-stu-id="332ae-108">This example creates a <xref:System.Drawing.Bitmap> object from a JPEG file and then draws the bitmap with its upper-left corner at (60, 10).</span></span>  
  
 <span data-ttu-id="332ae-109">次の図は、指定した位置に描画されたビットマップを示しています。</span><span class="sxs-lookup"><span data-stu-id="332ae-109">The following illustration shows the bitmap drawn at the specified location:</span></span>  
  
 ![指定された位置にあるイメージを示すスクリーンショット。](./media/how-to-draw-an-existing-bitmap-to-the-screen/bitmap-specified-position.png)  
  
 [!code-csharp[System.Drawing.WorkingWithImages#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.WorkingWithImages#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="332ae-111">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="332ae-111">Compiling the Code</span></span>  
 <span data-ttu-id="332ae-112">前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。</span><span class="sxs-lookup"><span data-stu-id="332ae-112">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="332ae-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="332ae-113">See also</span></span>

- [<span data-ttu-id="332ae-114">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="332ae-114">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="332ae-115">イメージ、ビットマップ、アイコン、およびメタファイルの操作</span><span class="sxs-lookup"><span data-stu-id="332ae-115">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
