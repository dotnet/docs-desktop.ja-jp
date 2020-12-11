---
title: '方法: メタファイルを読み込んで表示する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], metafiles
- metafiles [Windows Forms], displaying
ms.assetid: 60af1714-f148-4d85-a739-0557965ffa73
ms.openlocfilehash: 6c17e0b2d023ccf80b0d32301b7ee6765edcae9f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981323"
---
# <a name="how-to-load-and-display-metafiles"></a><span data-ttu-id="b3385-102">方法: メタファイルを読み込んで表示する</span><span class="sxs-lookup"><span data-stu-id="b3385-102">How to: Load and Display Metafiles</span></span>
<span data-ttu-id="b3385-103">クラスを <xref:System.Drawing.Imaging.Metafile> 継承するクラスには、 <xref:System.Drawing.Image> ベクターイメージの記録、表示、および検査を行うためのメソッドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="b3385-103">The <xref:System.Drawing.Imaging.Metafile> class, which inherits from the <xref:System.Drawing.Image> class, provides methods for recording, displaying, and examining vector images.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3385-104">例</span><span class="sxs-lookup"><span data-stu-id="b3385-104">Example</span></span>  
 <span data-ttu-id="b3385-105">ベクターイメージ (メタファイル) を画面に表示するには、 <xref:System.Drawing.Imaging.Metafile> オブジェクトとオブジェクトが必要 <xref:System.Drawing.Graphics> です。</span><span class="sxs-lookup"><span data-stu-id="b3385-105">To display a vector image (metafile) on the screen, you need a <xref:System.Drawing.Imaging.Metafile> object and a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="b3385-106">ファイル (またはストリーム) の名前をコンストラクターに渡し <xref:System.Drawing.Imaging.Metafile> ます。</span><span class="sxs-lookup"><span data-stu-id="b3385-106">Pass the name of a file (or a stream) to a <xref:System.Drawing.Imaging.Metafile> constructor.</span></span> <span data-ttu-id="b3385-107">オブジェクトを作成したら <xref:System.Drawing.Imaging.Metafile> 、そのオブジェクトを <xref:System.Drawing.Imaging.Metafile> <xref:System.Drawing.Graphics.DrawImage%2A> オブジェクトのメソッドに渡し <xref:System.Drawing.Graphics> ます。</span><span class="sxs-lookup"><span data-stu-id="b3385-107">After you have created a <xref:System.Drawing.Imaging.Metafile> object, pass that <xref:System.Drawing.Imaging.Metafile> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 <span data-ttu-id="b3385-108">この例では、 <xref:System.Drawing.Imaging.Metafile> EMF (拡張メタファイル) ファイルからオブジェクトを作成し、(60, 10) の左上隅でイメージを描画します。</span><span class="sxs-lookup"><span data-stu-id="b3385-108">The example creates a <xref:System.Drawing.Imaging.Metafile> object from an EMF (enhanced metafile) file and then draws the image with its upper-left corner at (60, 10).</span></span>  
  
 <span data-ttu-id="b3385-109">次の図は、指定した位置に描画されたメタファイルを示しています。</span><span class="sxs-lookup"><span data-stu-id="b3385-109">The following illustration shows the metafile drawn at the specified location.</span></span>  
  
 <span data-ttu-id="b3385-110">![画像の位置を示すスクリーンショット。](./media/how-to-load-and-display-metafiles/metafile-drawn-specified-location.png "imageposition2")</span><span class="sxs-lookup"><span data-stu-id="b3385-110">![Screenshot showing image position.](./media/how-to-load-and-display-metafiles/metafile-drawn-specified-location.png "imageposition2")</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.WorkingWithImages#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b3385-111">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="b3385-111">Compiling the Code</span></span>  
 <span data-ttu-id="b3385-112">前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。</span><span class="sxs-lookup"><span data-stu-id="b3385-112">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3385-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3385-113">See also</span></span>

- [<span data-ttu-id="b3385-114">イメージ、ビットマップ、アイコン、およびメタファイルの操作</span><span class="sxs-lookup"><span data-stu-id="b3385-114">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
