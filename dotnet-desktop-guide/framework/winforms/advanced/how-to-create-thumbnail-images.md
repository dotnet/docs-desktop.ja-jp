---
title: '方法: サムネイル イメージを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thumbnail images [Windows Forms], creating
- images [Windows Forms], creating thumbnails
ms.assetid: e956242a-1e5b-4217-a3cf-5f3fb45d00ba
ms.openlocfilehash: 786a92d99f5e7a0c27f502efa9a5fe617ac4d4d6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974415"
---
# <a name="how-to-create-thumbnail-images"></a><span data-ttu-id="816d3-102">方法: サムネイル イメージを作成する</span><span class="sxs-lookup"><span data-stu-id="816d3-102">How to: Create Thumbnail Images</span></span>
<span data-ttu-id="816d3-103">サムネイル画像は、イメージの小さなバージョンです。</span><span class="sxs-lookup"><span data-stu-id="816d3-103">A thumbnail image is a small version of an image.</span></span> <span data-ttu-id="816d3-104">オブジェクトのメソッドを呼び出すことにより、サムネイルイメージを作成でき <xref:System.Drawing.Image.GetThumbnailImage%2A> <xref:System.Drawing.Image> ます。</span><span class="sxs-lookup"><span data-stu-id="816d3-104">You can create a thumbnail image by calling the <xref:System.Drawing.Image.GetThumbnailImage%2A> method of an <xref:System.Drawing.Image> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="816d3-105">例</span><span class="sxs-lookup"><span data-stu-id="816d3-105">Example</span></span>  
 <span data-ttu-id="816d3-106">次の例では、 <xref:System.Drawing.Image> JPG ファイルからオブジェクトを構築します。</span><span class="sxs-lookup"><span data-stu-id="816d3-106">The following example constructs an <xref:System.Drawing.Image> object from a JPG file.</span></span> <span data-ttu-id="816d3-107">元のイメージの幅は640ピクセル、高さは479ピクセルです。</span><span class="sxs-lookup"><span data-stu-id="816d3-107">The original image has a width of 640 pixels and a height of 479 pixels.</span></span> <span data-ttu-id="816d3-108">このコードでは、幅100ピクセル、高さ100ピクセルのサムネイル画像を作成します。</span><span class="sxs-lookup"><span data-stu-id="816d3-108">The code creates a thumbnail image that has a width of 100 pixels and a height of 100 pixels.</span></span>  
  
 <span data-ttu-id="816d3-109">サムネイル画像を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="816d3-109">The following illustration shows the thumbnail image:</span></span>  
  
 ![出力サムネイルを示すスクリーンショット。](./media/how-to-create-thumbnail-images/construct-thumbnail-image.png)  
  
> [!NOTE]
> <span data-ttu-id="816d3-111">この例では、コールバックメソッドが宣言されていますが、使用されていません。</span><span class="sxs-lookup"><span data-stu-id="816d3-111">In this example, a callback method is declared, but never used.</span></span> <span data-ttu-id="816d3-112">これは、GDI + のすべてのバージョンをサポートします。</span><span class="sxs-lookup"><span data-stu-id="816d3-112">This supports all versions of GDI+.</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.WorkingWithImages#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="816d3-113">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="816d3-113">Compiling the Code</span></span>  
 <span data-ttu-id="816d3-114">前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。</span><span class="sxs-lookup"><span data-stu-id="816d3-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="816d3-115">この例を実行するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="816d3-115">To run the example, follow these steps:</span></span>  
  
1. <span data-ttu-id="816d3-116">新しい Windows フォーム アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="816d3-116">Create a new Windows Forms application.</span></span>  
  
2. <span data-ttu-id="816d3-117">サンプルコードをフォームに追加します。</span><span class="sxs-lookup"><span data-stu-id="816d3-117">Add the example code to the form.</span></span>  
  
3. <span data-ttu-id="816d3-118">フォームのイベントのハンドラーを作成します。 <xref:System.Windows.Forms.Control.Paint></span><span class="sxs-lookup"><span data-stu-id="816d3-118">Create a handler for the form's <xref:System.Windows.Forms.Control.Paint> event</span></span>  
  
4. <span data-ttu-id="816d3-119">ハンドラーで <xref:System.Windows.Forms.Control.Paint> 、メソッドを呼び出し、 `GetThumbnail` `e` にを渡し <xref:System.Windows.Forms.PaintEventArgs> ます。</span><span class="sxs-lookup"><span data-stu-id="816d3-119">In the <xref:System.Windows.Forms.Control.Paint> handler, call the `GetThumbnail` method and pass `e` for <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
5. <span data-ttu-id="816d3-120">サムネイルを作成するイメージファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="816d3-120">Find an image file that you want to make a thumbnail of.</span></span>  
  
6. <span data-ttu-id="816d3-121">メソッドで `GetThumbnail` 、イメージのパスとファイル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="816d3-121">In the `GetThumbnail` method, specify the path and file name to your image.</span></span>  
  
7. <span data-ttu-id="816d3-122">F5 キーを押して、例を実行します。</span><span class="sxs-lookup"><span data-stu-id="816d3-122">Press F5 to run the example.</span></span>  
  
     <span data-ttu-id="816d3-123">100の100サムネイル画像がフォームに表示されます。</span><span class="sxs-lookup"><span data-stu-id="816d3-123">A 100 by 100 thumbnail image appears on the form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="816d3-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="816d3-124">See also</span></span>

- [<span data-ttu-id="816d3-125">イメージ、ビットマップ、およびメタファイル</span><span class="sxs-lookup"><span data-stu-id="816d3-125">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="816d3-126">イメージ、ビットマップ、アイコン、およびメタファイルの操作</span><span class="sxs-lookup"><span data-stu-id="816d3-126">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
