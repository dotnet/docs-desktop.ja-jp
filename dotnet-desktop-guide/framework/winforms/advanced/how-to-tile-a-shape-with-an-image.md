---
title: '方法: イメージを並べたパターンによって図形を塗りつぶす'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- texture brushes [Windows Forms], tiling images with
- images [Windows Forms], filling shapes with
- shapes [Windows Forms], tiling with images
- bitmaps [Windows Forms], filling shapes with
ms.assetid: 6d407891-6e5c-4495-a546-3da5604e9fb8
ms.openlocfilehash: a906db44a548361df2822efa24d1dd1849cb5a24
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981248"
---
# <a name="how-to-tile-a-shape-with-an-image"></a><span data-ttu-id="9a1f4-102">方法: イメージを並べたパターンによって図形を塗りつぶす</span><span class="sxs-lookup"><span data-stu-id="9a1f4-102">How to: Tile a Shape with an Image</span></span>
<span data-ttu-id="9a1f4-103">タイルを横に配置してフロアをカバーできるのと同様に、四角形のイメージを相互に配置して、図形を塗りつぶす (並べて表示) ことができます。</span><span class="sxs-lookup"><span data-stu-id="9a1f4-103">Just as tiles can be placed next to each other to cover a floor, rectangular images can be placed next to each other to fill (tile) a shape.</span></span> <span data-ttu-id="9a1f4-104">図形の内部を並べて表示するには、テクスチャブラシを使用します。</span><span class="sxs-lookup"><span data-stu-id="9a1f4-104">To tile the interior of a shape, use a texture brush.</span></span> <span data-ttu-id="9a1f4-105">オブジェクトを構築する場合 <xref:System.Drawing.TextureBrush> 、コンストラクターに渡す引数の1つは <xref:System.Drawing.Image> オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="9a1f4-105">When you construct a <xref:System.Drawing.TextureBrush> object, one of the arguments you pass to the constructor is an <xref:System.Drawing.Image> object.</span></span> <span data-ttu-id="9a1f4-106">テクスチャブラシを使用して図形の内部を描画する場合、図形にはこのイメージの繰り返しコピーが格納されます。</span><span class="sxs-lookup"><span data-stu-id="9a1f4-106">When you use the texture brush to paint the interior of a shape, the shape is filled with repeated copies of this image.</span></span>  
  
 <span data-ttu-id="9a1f4-107">オブジェクトの "ラップモード" プロパティによっ <xref:System.Drawing.TextureBrush> て、四角形のグリッド内でイメージがどのように配置されるかが決まります。</span><span class="sxs-lookup"><span data-stu-id="9a1f4-107">The wrap mode property of the <xref:System.Drawing.TextureBrush> object determines how the image is oriented as it is repeated in a rectangular grid.</span></span> <span data-ttu-id="9a1f4-108">グリッド内のすべてのタイルの向きを同じにすることも、イメージを1つのグリッド位置から次の位置に切り替えられるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="9a1f4-108">You can make all the tiles in the grid have the same orientation, or you can make the image flip from one grid position to the next.</span></span> <span data-ttu-id="9a1f4-109">反転は、水平方向、垂直方向、または両方にすることができます。</span><span class="sxs-lookup"><span data-stu-id="9a1f4-109">The flipping can be horizontal, vertical, or both.</span></span> <span data-ttu-id="9a1f4-110">次の例は、さまざまな種類の反転のタイルを示しています。</span><span class="sxs-lookup"><span data-stu-id="9a1f4-110">The following examples demonstrate tiling with different types of flipping.</span></span>  
  
### <a name="to-tile-an-image"></a><span data-ttu-id="9a1f4-111">イメージを並べて表示するには</span><span class="sxs-lookup"><span data-stu-id="9a1f4-111">To tile an image</span></span>  
  
- <span data-ttu-id="9a1f4-112">この例では、次の75×75の画像を使用して、200×200の四角形を並べて表示します。</span><span class="sxs-lookup"><span data-stu-id="9a1f4-112">This example uses the following 75×75 image to tile a 200×200 rectangle.</span></span>  
  
 ![赤い家と1つのツリーを表示するタイルイメージ。](./media/how-to-tile-a-shape-with-an-image/rectangle-tile-200x200.gif)  
  
- <span data-ttu-id="9a1f4-114">次の図は、イメージで四角形を並べて表示する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="9a1f4-114">The following illustration shows how the rectangle is tiled with the image.</span></span> <span data-ttu-id="9a1f4-115">すべてのタイルの向きが同じであることに注意してください。反転はありません。</span><span class="sxs-lookup"><span data-stu-id="9a1f4-115">Note that all tiles have the same orientation; there is no flipping.</span></span>  
  
 ![すべてのタイルで同じ向きを使用して、イメージで並べて表示される四角形。](./media/how-to-tile-a-shape-with-an-image/rectangle-tiled-image-no-flip.gif)  
  
 [!code-csharp[System.Drawing.UsingABrush#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingABrush#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#31)]  
  
### <a name="to-flip-an-image-horizontally-while-tiling"></a><span data-ttu-id="9a1f4-117">タイリング中に画像を水平に反転するには</span><span class="sxs-lookup"><span data-stu-id="9a1f4-117">To flip an image horizontally while tiling</span></span>  
  
- <span data-ttu-id="9a1f4-118">この例では、同じ75×75の画像を使用して、200×200の四角形を塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="9a1f4-118">This example uses the same 75×75 image to fill a 200×200 rectangle.</span></span> <span data-ttu-id="9a1f4-119">折り返しモードは、画像を水平方向に反転するように設定されています。</span><span class="sxs-lookup"><span data-stu-id="9a1f4-119">The wrap mode is set to flip the image horizontally.</span></span> <span data-ttu-id="9a1f4-120">次の図は、イメージで四角形を並べて表示する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="9a1f4-120">The following illustration shows how the rectangle is tiled with the image.</span></span> <span data-ttu-id="9a1f4-121">あるタイルから、特定の行の次のタイルに移動すると、画像が水平方向に反転されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9a1f4-121">Note that as you move from one tile to the next in a given row, the image is flipped horizontally.</span></span>  
  
 ![水平方向に反転されたイメージで並べて表示される四角形。](./media/how-to-tile-a-shape-with-an-image/rectangle-tiled-image-horizontal-flip.gif)  
  
 [!code-csharp[System.Drawing.UsingABrush#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.UsingABrush#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#32)]  
  
### <a name="to-flip-an-image-vertically-while-tiling"></a><span data-ttu-id="9a1f4-123">タイル処理中に画像を垂直方向に反転するには</span><span class="sxs-lookup"><span data-stu-id="9a1f4-123">To flip an image vertically while tiling</span></span>  
  
- <span data-ttu-id="9a1f4-124">この例では、同じ75×75の画像を使用して、200×200の四角形を塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="9a1f4-124">This example uses the same 75×75 image to fill a 200×200 rectangle.</span></span> <span data-ttu-id="9a1f4-125">折り返しモードは、画像を垂直方向に反転するように設定されています。</span><span class="sxs-lookup"><span data-stu-id="9a1f4-125">The wrap mode is set to flip the image vertically.</span></span>  
  
     [!code-csharp[System.Drawing.UsingABrush#33](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#33)]
     [!code-vb[System.Drawing.UsingABrush#33](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#33)]  
  
### <a name="to-flip-an-image-horizontally-and-vertically-while-tiling"></a><span data-ttu-id="9a1f4-126">タイル処理中に画像を水平方向および垂直方向に反転するには</span><span class="sxs-lookup"><span data-stu-id="9a1f4-126">To flip an image horizontally and vertically while tiling</span></span>  
  
- <span data-ttu-id="9a1f4-127">この例では、同じ75×75の画像を使用して、200×200の四角形を並べて表示します。</span><span class="sxs-lookup"><span data-stu-id="9a1f4-127">This example uses the same 75×75 image to tile a 200×200 rectangle.</span></span> <span data-ttu-id="9a1f4-128">折り返しモードは、画像を水平方向および垂直方向に反転するように設定されています。</span><span class="sxs-lookup"><span data-stu-id="9a1f4-128">The wrap mode is set to flip the image both horizontally and vertically.</span></span> <span data-ttu-id="9a1f4-129">次の図は、イメージで四角形を並べて表示する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="9a1f4-129">The following illustration shows how the rectangle is tiled by the image.</span></span> <span data-ttu-id="9a1f4-130">特定の行で1つのタイルから次のタイルに移動すると、画像が水平方向に反転されます。また、あるタイルから特定の列の次のタイルに移動すると、画像が垂直方向に反転されます。</span><span class="sxs-lookup"><span data-stu-id="9a1f4-130">Note that as you move from one tile to the next in a given row, the image is flipped horizontally, and as you move from one tile to the next in a given column, the image is flipped vertically.</span></span>  
  
 ![水平方向および垂直方向に反転されたイメージで並べて表示される四角形。](./media/how-to-tile-a-shape-with-an-image/rectangle-tiled-image-horizontal-vertical-flip.gif)  
  
 [!code-csharp[System.Drawing.UsingABrush#34](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.UsingABrush#34](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#34)]  
  
## <a name="see-also"></a><span data-ttu-id="9a1f4-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="9a1f4-132">See also</span></span>

- [<span data-ttu-id="9a1f4-133">ブラシを使用した図形の塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="9a1f4-133">Using a Brush to Fill Shapes</span></span>](using-a-brush-to-fill-shapes.md)
