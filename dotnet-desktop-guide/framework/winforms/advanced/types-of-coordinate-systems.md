---
title: 座標系の種類
ms.date: 03/30/2017
ms.topic: overview
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], page
- unit of measure
- world coordinate system
- page coordinate system
- page transformation
- device coordinate system
- world transformation
- coordinate systems
- transformations [Windows Forms], world
ms.assetid: c61ff50a-eb1d-4e6c-83cd-f7e9764cfa9f
ms.openlocfilehash: ca5cd1839661123f0df4a86df60771b6313fb01a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981627"
---
# <a name="types-of-coordinate-systems"></a><span data-ttu-id="9f67d-102">座標系の種類</span><span class="sxs-lookup"><span data-stu-id="9f67d-102">Types of Coordinate Systems</span></span>
<span data-ttu-id="9f67d-103">GDI + では、ワールド、ページ、デバイスという3つの座標空間が使用されます。</span><span class="sxs-lookup"><span data-stu-id="9f67d-103">GDI+ uses three coordinate spaces: world, page, and device.</span></span> <span data-ttu-id="9f67d-104">ワールド座標は、特定のグラフィックワールドをモデル化するために使用される座標であり、.NET Framework のメソッドに渡す座標です。</span><span class="sxs-lookup"><span data-stu-id="9f67d-104">World coordinates are the coordinates used to model a particular graphic world and are the coordinates you pass to methods in the .NET Framework.</span></span> <span data-ttu-id="9f67d-105">ページ座標は、フォームやコントロールなど、描画サーフェイスによって使用される座標系を表します。</span><span class="sxs-lookup"><span data-stu-id="9f67d-105">Page coordinates refer to the coordinate system used by a drawing surface, such as a form or control.</span></span> <span data-ttu-id="9f67d-106">デバイス座標は、画面や用紙など、描画される物理デバイスで使用される座標です。</span><span class="sxs-lookup"><span data-stu-id="9f67d-106">Device coordinates are the coordinates used by the physical device being drawn on, such as a screen or sheet of paper.</span></span> <span data-ttu-id="9f67d-107">この呼び出しを行うと `myGraphics.DrawLine(myPen, 0, 0, 160, 80)` 、メソッドに渡す点 <xref:System.Drawing.Graphics.DrawLine%2A> ( `(0, 0)` と `(160, 80)` ) がワールド座標空間にあります。</span><span class="sxs-lookup"><span data-stu-id="9f67d-107">When you make the call `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, the points that you pass to the <xref:System.Drawing.Graphics.DrawLine%2A> method—`(0, 0)` and `(160, 80)`—are in the world coordinate space.</span></span> <span data-ttu-id="9f67d-108">GDI + が画面上に線を描画する前に、座標は一連の変換を通過します。</span><span class="sxs-lookup"><span data-stu-id="9f67d-108">Before GDI+ can draw the line on the screen, the coordinates pass through a sequence of transformations.</span></span> <span data-ttu-id="9f67d-109">ワールド変換と呼ばれる1つの変換は、ワールド座標をページ座標に変換し、ページ変換と呼ばれる別の変換はページ座標をデバイス座標に変換します。</span><span class="sxs-lookup"><span data-stu-id="9f67d-109">One transformation, called the world transformation, converts world coordinates to page coordinates, and another transformation, called the page transformation, converts page coordinates to device coordinates.</span></span>  
  
## <a name="transforms-and-coordinate-systems"></a><span data-ttu-id="9f67d-110">変換と座標系</span><span class="sxs-lookup"><span data-stu-id="9f67d-110">Transforms and Coordinate Systems</span></span>  
 <span data-ttu-id="9f67d-111">左上隅ではなく、クライアント領域の本体に原点がある座標系を操作するとします。</span><span class="sxs-lookup"><span data-stu-id="9f67d-111">Suppose you want to work with a coordinate system that has its origin in the body of the client area rather than the upper-left corner.</span></span> <span data-ttu-id="9f67d-112">たとえば、原点をクライアント領域の左端から100ピクセル、クライアント領域の上端から50ピクセルにする必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="9f67d-112">Say, for example, that you want the origin to be 100 pixels from the left edge of the client area and 50 pixels from the top of the client area.</span></span> <span data-ttu-id="9f67d-113">次の図は、このような座標系を示しています。</span><span class="sxs-lookup"><span data-stu-id="9f67d-113">The following illustration shows such a coordinate system.</span></span>  
  
 <span data-ttu-id="9f67d-114">![座標系](./media/aboutgdip05-art01.gif "AboutGdip05_art01")</span><span class="sxs-lookup"><span data-stu-id="9f67d-114">![Coordinate System](./media/aboutgdip05-art01.gif "AboutGdip05_art01")</span></span>  
  
 <span data-ttu-id="9f67d-115">呼び出しを行うと `myGraphics.DrawLine(myPen, 0, 0, 160, 80)` 、次の図に示すような行が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9f67d-115">When you make the call `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, you get the line shown in the following illustration.</span></span>  
  
 <span data-ttu-id="9f67d-116">![座標系](./media/aboutgdip05-art02.gif "AboutGdip05_art02")</span><span class="sxs-lookup"><span data-stu-id="9f67d-116">![Coordinate System](./media/aboutgdip05-art02.gif "AboutGdip05_art02")</span></span>  
  
 <span data-ttu-id="9f67d-117">3つの座標空間における直線の終点の座標は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="9f67d-117">The coordinates of the endpoints of your line in the three coordinate spaces are as follows:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9f67d-118">World</span><span class="sxs-lookup"><span data-stu-id="9f67d-118">World</span></span>|<span data-ttu-id="9f67d-119">(0, 0) ~ (160, 80)</span><span class="sxs-lookup"><span data-stu-id="9f67d-119">(0, 0) to (160, 80)</span></span>|  
|<span data-ttu-id="9f67d-120">ページ</span><span class="sxs-lookup"><span data-stu-id="9f67d-120">Page</span></span>|<span data-ttu-id="9f67d-121">(100, 50) から (260、130)</span><span class="sxs-lookup"><span data-stu-id="9f67d-121">(100, 50) to (260, 130)</span></span>|  
|<span data-ttu-id="9f67d-122">Device</span><span class="sxs-lookup"><span data-stu-id="9f67d-122">Device</span></span>|<span data-ttu-id="9f67d-123">(100, 50) から (260、130)</span><span class="sxs-lookup"><span data-stu-id="9f67d-123">(100, 50) to (260, 130)</span></span>|  
  
 <span data-ttu-id="9f67d-124">ページ座標空間の原点がクライアント領域の左上隅にあることに注意してください。常にこれが当てはまります。</span><span class="sxs-lookup"><span data-stu-id="9f67d-124">Note that the page coordinate space has its origin at the upper-left corner of the client area; this will always be the case.</span></span> <span data-ttu-id="9f67d-125">また、測定単位はピクセルであるため、デバイス座標はページ座標と同じであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9f67d-125">Also note that because the unit of measure is the pixel, the device coordinates are the same as the page coordinates.</span></span> <span data-ttu-id="9f67d-126">測定単位をピクセル以外の値 (インチなど) に設定した場合、デバイス座標はページ座標とは異なります。</span><span class="sxs-lookup"><span data-stu-id="9f67d-126">If you set the unit of measure to something other than pixels (for example, inches), then the device coordinates will be different from the page coordinates.</span></span>  
  
 <span data-ttu-id="9f67d-127">ワールド座標をページ座標にマップするワールド変換は、 <xref:System.Drawing.Graphics.Transform%2A> クラスのプロパティに保持され <xref:System.Drawing.Graphics> ます。</span><span class="sxs-lookup"><span data-stu-id="9f67d-127">The world transformation, which maps world coordinates to page coordinates, is held in the <xref:System.Drawing.Graphics.Transform%2A> property of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="9f67d-128">前の例では、ワールド変換は、x 方向の平行移動100単位と y 方向の50単位です。</span><span class="sxs-lookup"><span data-stu-id="9f67d-128">In the preceding example, the world transformation is a translation 100 units in the x direction and 50 units in the y direction.</span></span> <span data-ttu-id="9f67d-129">次の例では、オブジェクトのワールド変換を設定 <xref:System.Drawing.Graphics> し、そのオブジェクトを使用して、 <xref:System.Drawing.Graphics> 前の図に示した線を描画します。</span><span class="sxs-lookup"><span data-stu-id="9f67d-129">The following example sets the world transformation of a <xref:System.Drawing.Graphics> object and then uses that <xref:System.Drawing.Graphics> object to draw the line shown in the preceding figure:</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.CoordinateSystems#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#31)]  
  
 <span data-ttu-id="9f67d-130">ページ変換は、ページ座標をデバイス座標にマップします。</span><span class="sxs-lookup"><span data-stu-id="9f67d-130">The page transformation maps page coordinates to device coordinates.</span></span> <span data-ttu-id="9f67d-131">クラスには、 <xref:System.Drawing.Graphics> <xref:System.Drawing.Graphics.PageUnit%2A> <xref:System.Drawing.Graphics.PageScale%2A> ページ変換を操作するためのプロパティとプロパティが用意されています。</span><span class="sxs-lookup"><span data-stu-id="9f67d-131">The <xref:System.Drawing.Graphics> class provides the <xref:System.Drawing.Graphics.PageUnit%2A> and <xref:System.Drawing.Graphics.PageScale%2A> properties for manipulating the page transformation.</span></span> <span data-ttu-id="9f67d-132">また、クラスには、 <xref:System.Drawing.Graphics> 2 つの読み取り専用プロパティ <xref:System.Drawing.Graphics.DpiX%2A> と <xref:System.Drawing.Graphics.DpiY%2A> 、ディスプレイデバイスの1インチあたりの水平および垂直のドットを調べるためのプロパティも用意されています。</span><span class="sxs-lookup"><span data-stu-id="9f67d-132">The <xref:System.Drawing.Graphics> class also provides two read-only properties, <xref:System.Drawing.Graphics.DpiX%2A> and <xref:System.Drawing.Graphics.DpiY%2A>, for examining the horizontal and vertical dots per inch of the display device.</span></span>  
  
 <span data-ttu-id="9f67d-133">クラスのプロパティを使用して、 <xref:System.Drawing.Graphics.PageUnit%2A> <xref:System.Drawing.Graphics> ピクセル以外の測定単位を指定できます。</span><span class="sxs-lookup"><span data-stu-id="9f67d-133">You can use the <xref:System.Drawing.Graphics.PageUnit%2A> property of the <xref:System.Drawing.Graphics> class to specify a unit of measure other than the pixel.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9f67d-134">このプロパティをに設定することはできません <xref:System.Drawing.Graphics.PageUnit%2A> <xref:System.Drawing.GraphicsUnit.World> 。これは物理単位ではないため、例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="9f67d-134">You cannot set the <xref:System.Drawing.Graphics.PageUnit%2A> property to <xref:System.Drawing.GraphicsUnit.World>, as this is not a physical unit and will cause an exception.</span></span>  
  
 <span data-ttu-id="9f67d-135">次の例では、(0, 0) から (2, 1) までの線を描画します。ここで、点 (2, 1) は右に2インチ、ポイント (0, 0) から1インチ下になります。</span><span class="sxs-lookup"><span data-stu-id="9f67d-135">The following example draws a line from (0, 0) to (2, 1), where the point (2, 1) is 2 inches to the right and 1 inch down from the point (0, 0):</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.CoordinateSystems#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#32)]  
  
> [!NOTE]
> <span data-ttu-id="9f67d-136">ペンを作成するときにペンの幅を指定しなかった場合、前の例では1インチ幅の線が描画されます。</span><span class="sxs-lookup"><span data-stu-id="9f67d-136">If you don't specify a pen width when you construct your pen, the preceding example will draw a line that is one inch wide.</span></span> <span data-ttu-id="9f67d-137">コンストラクターの2番目の引数には、ペンの幅を指定でき <xref:System.Drawing.Pen> ます。</span><span class="sxs-lookup"><span data-stu-id="9f67d-137">You can specify the pen width in the second argument to the <xref:System.Drawing.Pen> constructor:</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#33](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#33)]
 [!code-vb[System.Drawing.CoordinateSystems#33](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#33)]  
  
 <span data-ttu-id="9f67d-138">ディスプレイデバイスの水平方向には96ドット/インチ、垂直方向には96ドットがあると想定している場合、前の例の線の端点には、3つの座標空間に次の座標があります。</span><span class="sxs-lookup"><span data-stu-id="9f67d-138">If we assume that the display device has 96 dots per inch in the horizontal direction and 96 dots per inch in the vertical direction, the endpoints of the line in the preceding example have the following coordinates in the three coordinate spaces:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9f67d-139">World</span><span class="sxs-lookup"><span data-stu-id="9f67d-139">World</span></span>|<span data-ttu-id="9f67d-140">(0, 0) ~ (2, 1)</span><span class="sxs-lookup"><span data-stu-id="9f67d-140">(0, 0) to (2, 1)</span></span>|  
|<span data-ttu-id="9f67d-141">ページ</span><span class="sxs-lookup"><span data-stu-id="9f67d-141">Page</span></span>|<span data-ttu-id="9f67d-142">(0, 0) ~ (2, 1)</span><span class="sxs-lookup"><span data-stu-id="9f67d-142">(0, 0) to (2, 1)</span></span>|  
|<span data-ttu-id="9f67d-143">Device</span><span class="sxs-lookup"><span data-stu-id="9f67d-143">Device</span></span>|<span data-ttu-id="9f67d-144">(0, 0) ~ (192, 96)</span><span class="sxs-lookup"><span data-stu-id="9f67d-144">(0, 0) to (192, 96)</span></span>|  
  
 <span data-ttu-id="9f67d-145">ワールド座標空間の原点がクライアント領域の左上隅にあるため、ページ座標はワールド座標と同じであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9f67d-145">Note that because the origin of the world coordinate space is at the upper-left corner of the client area, the page coordinates are the same as the world coordinates.</span></span>  
  
 <span data-ttu-id="9f67d-146">世界およびページの変換を組み合わせて、さまざまな効果を実現できます。</span><span class="sxs-lookup"><span data-stu-id="9f67d-146">You can combine the world and page transformations to achieve a variety of effects.</span></span> <span data-ttu-id="9f67d-147">たとえば、ミリメートルを測定単位として使用する場合に、座標系の原点をクライアント領域の左端から2インチ、クライアント領域の上端から1/2 インチにする必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="9f67d-147">For example, suppose you want to use inches as the unit of measure and you want the origin of your coordinate system to be 2 inches from the left edge of the client area and 1/2 inch from the top of the client area.</span></span> <span data-ttu-id="9f67d-148">次の例では、オブジェクトのワールド変換とページ変換を設定 <xref:System.Drawing.Graphics> し、(0, 0) から (2, 1) までの線を描画します。</span><span class="sxs-lookup"><span data-stu-id="9f67d-148">The following example sets the world and page transformations of a <xref:System.Drawing.Graphics> object and then draws a line from (0, 0) to (2, 1):</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#34](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.CoordinateSystems#34](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#34)]  
  
 <span data-ttu-id="9f67d-149">次の図は、線と座標系を示しています。</span><span class="sxs-lookup"><span data-stu-id="9f67d-149">The following illustration shows the line and coordinate system.</span></span>  
  
 <span data-ttu-id="9f67d-150">![座標系](./media/aboutgdip05-art03.gif "AboutGdip05_art03")</span><span class="sxs-lookup"><span data-stu-id="9f67d-150">![Coordinate System](./media/aboutgdip05-art03.gif "AboutGdip05_art03")</span></span>  
  
 <span data-ttu-id="9f67d-151">ディスプレイデバイスの水平方向には96ドット/インチ、垂直方向には96ドットがあると想定している場合、前の例の線の端点には、3つの座標空間に次の座標があります。</span><span class="sxs-lookup"><span data-stu-id="9f67d-151">If we assume that the display device has 96 dots per inch in the horizontal direction and 96 dots per inch in the vertical direction, the endpoints of the line in the preceding example have the following coordinates in the three coordinate spaces:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9f67d-152">World</span><span class="sxs-lookup"><span data-stu-id="9f67d-152">World</span></span>|<span data-ttu-id="9f67d-153">(0, 0) ~ (2, 1)</span><span class="sxs-lookup"><span data-stu-id="9f67d-153">(0, 0) to (2, 1)</span></span>|  
|<span data-ttu-id="9f67d-154">ページ</span><span class="sxs-lookup"><span data-stu-id="9f67d-154">Page</span></span>|<span data-ttu-id="9f67d-155">(2, 0.5) から (4, 1.5)</span><span class="sxs-lookup"><span data-stu-id="9f67d-155">(2, 0.5) to (4, 1.5)</span></span>|  
|<span data-ttu-id="9f67d-156">Device</span><span class="sxs-lookup"><span data-stu-id="9f67d-156">Device</span></span>|<span data-ttu-id="9f67d-157">(192, 48) から (384、144)</span><span class="sxs-lookup"><span data-stu-id="9f67d-157">(192, 48) to (384, 144)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9f67d-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="9f67d-158">See also</span></span>

- [<span data-ttu-id="9f67d-159">座標系と変換</span><span class="sxs-lookup"><span data-stu-id="9f67d-159">Coordinate Systems and Transformations</span></span>](coordinate-systems-and-transformations.md)
- [<span data-ttu-id="9f67d-160">変換の行列表現</span><span class="sxs-lookup"><span data-stu-id="9f67d-160">Matrix Representation of Transformations</span></span>](matrix-representation-of-transformations.md)
