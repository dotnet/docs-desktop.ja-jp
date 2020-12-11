---
title: Graphics オブジェクトの状態の管理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], managing state
- graphics [Windows Forms], clipping
ms.assetid: 6207cad1-7a34-4bd6-bfc1-db823ca7a73e
ms.openlocfilehash: d1e7e6eac775ca779fb68605adcc9bc2b9915e49
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981200"
---
# <a name="managing-the-state-of-a-graphics-object"></a><span data-ttu-id="b47ec-102">Graphics オブジェクトの状態の管理</span><span class="sxs-lookup"><span data-stu-id="b47ec-102">Managing the State of a Graphics Object</span></span>
<span data-ttu-id="b47ec-103"><xref:System.Drawing.Graphics>クラスは GDI + の中心にあります。</span><span class="sxs-lookup"><span data-stu-id="b47ec-103">The <xref:System.Drawing.Graphics> class is at the heart of GDI+.</span></span> <span data-ttu-id="b47ec-104">任意のオブジェクトを描画するには、オブジェクトを取得し、 <xref:System.Drawing.Graphics> そのプロパティを設定して、メソッド <xref:System.Drawing.Graphics.DrawLine%2A> 、、 <xref:System.Drawing.Graphics.DrawImage%2A> <xref:System.Drawing.Graphics.DrawString%2A> 、およびのように呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b47ec-104">To draw anything, you obtain a <xref:System.Drawing.Graphics> object, set its properties, and call its methods <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, <xref:System.Drawing.Graphics.DrawString%2A>, and the like).</span></span>  
  
 <span data-ttu-id="b47ec-105">次の例では、 <xref:System.Drawing.Graphics.DrawRectangle%2A> オブジェクトのメソッドを呼び出し <xref:System.Drawing.Graphics> ます。</span><span class="sxs-lookup"><span data-stu-id="b47ec-105">The following example calls the <xref:System.Drawing.Graphics.DrawRectangle%2A> method of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="b47ec-106">メソッドに渡される最初の引数 <xref:System.Drawing.Graphics.DrawRectangle%2A> は <xref:System.Drawing.Pen> オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="b47ec-106">The first argument passed to the <xref:System.Drawing.Graphics.DrawRectangle%2A> method is a <xref:System.Drawing.Pen> object.</span></span>  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Blue) ' Opaque blue  
graphics.DrawRectangle(pen, 10, 10, 200, 100)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Blue);  // Opaque blue  
graphics.DrawRectangle(pen, 10, 10, 200, 100);  
```  
  
## <a name="graphics-state"></a><span data-ttu-id="b47ec-107">グラフィックスの状態</span><span class="sxs-lookup"><span data-stu-id="b47ec-107">Graphics State</span></span>  
 <span data-ttu-id="b47ec-108">オブジェクトは、やなどの <xref:System.Drawing.Graphics> 描画メソッドを提供するだけではありません <xref:System.Drawing.Graphics.DrawLine%2A> <xref:System.Drawing.Graphics.DrawRectangle%2A> 。</span><span class="sxs-lookup"><span data-stu-id="b47ec-108">A <xref:System.Drawing.Graphics> object does more than provide drawing methods, such as <xref:System.Drawing.Graphics.DrawLine%2A> and <xref:System.Drawing.Graphics.DrawRectangle%2A>.</span></span> <span data-ttu-id="b47ec-109"><xref:System.Drawing.Graphics>また、オブジェクトはグラフィックスの状態も保持します。これは次のカテゴリに分類できます。</span><span class="sxs-lookup"><span data-stu-id="b47ec-109">A <xref:System.Drawing.Graphics> object also maintains graphics state, which can be divided into the following categories:</span></span>  
  
- <span data-ttu-id="b47ec-110">品質設定</span><span class="sxs-lookup"><span data-stu-id="b47ec-110">Quality settings</span></span>  
  
- <span data-ttu-id="b47ec-111">変換</span><span class="sxs-lookup"><span data-stu-id="b47ec-111">Transformations</span></span>  
  
- <span data-ttu-id="b47ec-112">領域のクリッピング</span><span class="sxs-lookup"><span data-stu-id="b47ec-112">Clipping region</span></span>  
  
### <a name="quality-settings"></a><span data-ttu-id="b47ec-113">品質設定</span><span class="sxs-lookup"><span data-stu-id="b47ec-113">Quality Settings</span></span>  
 <span data-ttu-id="b47ec-114"><xref:System.Drawing.Graphics>オブジェクトには、描画される項目の品質に影響を与えるいくつかのプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="b47ec-114">A <xref:System.Drawing.Graphics> object has several properties that influence the quality of the items that are drawn.</span></span> <span data-ttu-id="b47ec-115">たとえば、プロパティを設定して、 <xref:System.Drawing.Graphics.TextRenderingHint%2A> テキストに適用されるアンチエイリアシングの種類 (存在する場合) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b47ec-115">For example, you can set the <xref:System.Drawing.Graphics.TextRenderingHint%2A> property to specify the type of antialiasing (if any) applied to text.</span></span> <span data-ttu-id="b47ec-116">品質に影響を与える他のプロパティは、、、 <xref:System.Drawing.Graphics.SmoothingMode%2A> <xref:System.Drawing.Graphics.CompositingMode%2A> <xref:System.Drawing.Graphics.CompositingQuality%2A> 、および <xref:System.Drawing.Graphics.InterpolationMode%2A> です。</span><span class="sxs-lookup"><span data-stu-id="b47ec-116">Other properties that influence quality are <xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.CompositingMode%2A>, <xref:System.Drawing.Graphics.CompositingQuality%2A>, and <xref:System.Drawing.Graphics.InterpolationMode%2A>.</span></span>  
  
 <span data-ttu-id="b47ec-117">次の例では、スムージングモードがに設定された楕円と、スムージングモードがに設定されている2つの楕円を描画し <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed> ます。</span><span class="sxs-lookup"><span data-stu-id="b47ec-117">The following example draws two ellipses, one with the smoothing mode set to <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> and one with the smoothing mode set to <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed>:</span></span>  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Blue)  
  
graphics.SmoothingMode = SmoothingMode.AntiAlias  
graphics.DrawEllipse(pen, 0, 0, 200, 100)  
graphics.SmoothingMode = SmoothingMode.HighSpeed  
graphics.DrawEllipse(pen, 0, 150, 200, 100)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Blue);  
  
graphics.SmoothingMode = SmoothingMode.AntiAlias;  
graphics.DrawEllipse(pen, 0, 0, 200, 100);  
graphics.SmoothingMode = SmoothingMode.HighSpeed;  
graphics.DrawEllipse(pen, 0, 150, 200, 100);  
```  
  
### <a name="transformations"></a><span data-ttu-id="b47ec-118">変換</span><span class="sxs-lookup"><span data-stu-id="b47ec-118">Transformations</span></span>  
 <span data-ttu-id="b47ec-119">オブジェクトは、 <xref:System.Drawing.Graphics> そのオブジェクトによって描画されるすべてのアイテムに適用される2つの変換 (ワールドおよび page) を保持し <xref:System.Drawing.Graphics> ます。</span><span class="sxs-lookup"><span data-stu-id="b47ec-119">A <xref:System.Drawing.Graphics> object maintains two transformations (world and page) that are applied to all items drawn by that <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="b47ec-120">すべてのアフィン変換は、ワールド変換に格納できます。</span><span class="sxs-lookup"><span data-stu-id="b47ec-120">Any affine transformation can be stored in the world transformation.</span></span> <span data-ttu-id="b47ec-121">アフィン変換には、拡大縮小、回転、反射、傾斜、および平行移動などがあります。</span><span class="sxs-lookup"><span data-stu-id="b47ec-121">Affine transformations include scaling, rotating, reflecting, skewing, and translating.</span></span> <span data-ttu-id="b47ec-122">ページ変換を使用して、単位を変更することができます (ピクセルからインチなど)。</span><span class="sxs-lookup"><span data-stu-id="b47ec-122">The page transformation can be used for scaling and for changing units (for example, pixels to inches).</span></span> <span data-ttu-id="b47ec-123">詳細については、「 [座標系と変換](coordinate-systems-and-transformations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b47ec-123">For more information, see [Coordinate Systems and Transformations](coordinate-systems-and-transformations.md).</span></span>  
  
 <span data-ttu-id="b47ec-124">次の例では、オブジェクトのワールド変換とページ変換を設定し <xref:System.Drawing.Graphics> ます。</span><span class="sxs-lookup"><span data-stu-id="b47ec-124">The following example sets the world and page transformations of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="b47ec-125">ワールド変換は30度回転に設定されています。</span><span class="sxs-lookup"><span data-stu-id="b47ec-125">The world transformation is set to a 30-degree rotation.</span></span> <span data-ttu-id="b47ec-126">ページ変換は、2番目に渡される座標がピクセルでは <xref:System.Drawing.Graphics.DrawEllipse%2A> なくミリメートルとして処理されるように設定されます。</span><span class="sxs-lookup"><span data-stu-id="b47ec-126">The page transformation is set so that the coordinates passed to the second <xref:System.Drawing.Graphics.DrawEllipse%2A> will be treated as millimeters instead of pixels.</span></span> <span data-ttu-id="b47ec-127">このコードでは、2つの同じ呼び出しをメソッドに対して行い <xref:System.Drawing.Graphics.DrawEllipse%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="b47ec-127">The code makes two identical calls to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method.</span></span> <span data-ttu-id="b47ec-128">ワールド変換は最初の呼び出しに適用され、 <xref:System.Drawing.Graphics.DrawEllipse%2A> 2 回目の呼び出しには両方の変換 (ワールドとページ) が適用され <xref:System.Drawing.Graphics.DrawEllipse%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="b47ec-128">The world transformation is applied to the first <xref:System.Drawing.Graphics.DrawEllipse%2A> call, and both transformations (world and page) are applied to the second <xref:System.Drawing.Graphics.DrawEllipse%2A> call.</span></span>  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Red)  
  
graphics.ResetTransform()  
graphics.RotateTransform(30) ' world transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50)  
graphics.PageUnit = GraphicsUnit.Millimeter ' page transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Red);
  
graphics.ResetTransform();  
graphics.RotateTransform(30);                    // world transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50);  
graphics.PageUnit = GraphicsUnit.Millimeter;     // page transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50);  
```  
  
 <span data-ttu-id="b47ec-129">次の図は、2つの楕円を示しています。</span><span class="sxs-lookup"><span data-stu-id="b47ec-129">The following illustration shows the two ellipses.</span></span> <span data-ttu-id="b47ec-130">30度回転は、楕円の中心についてではなく、座標系の原点 (クライアント領域の左上隅) に関することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b47ec-130">Note that the 30-degree rotation is about the origin of the coordinate system (upper-left corner of the client area), not about the centers of the ellipses.</span></span> <span data-ttu-id="b47ec-131">また、ペンの幅1は、最初の楕円に1ピクセル、2番目の楕円に1ミリメートルを意味します。</span><span class="sxs-lookup"><span data-stu-id="b47ec-131">Also note that the pen width of 1 means 1 pixel for the first ellipse and 1 millimeter for the second ellipse.</span></span>  
  
 ![2つの楕円 (回転とペンの幅) を示す図。](./media/managing-the-state-of-a-graphics-object/set-rotation-pen-width-drawellipse-method.png)  
  
### <a name="clipping-region"></a><span data-ttu-id="b47ec-133">領域のクリッピング</span><span class="sxs-lookup"><span data-stu-id="b47ec-133">Clipping Region</span></span>  
 <span data-ttu-id="b47ec-134">オブジェクトは、 <xref:System.Drawing.Graphics> そのオブジェクトによって描画されるすべての項目に適用されるクリッピング領域を保持し <xref:System.Drawing.Graphics> ます。</span><span class="sxs-lookup"><span data-stu-id="b47ec-134">A <xref:System.Drawing.Graphics> object maintains a clipping region that applies to all items drawn by that <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="b47ec-135">クリッピング領域は、メソッドを呼び出すことによって設定でき <xref:System.Drawing.Graphics.SetClip%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="b47ec-135">You can set the clipping region by calling the <xref:System.Drawing.Graphics.SetClip%2A> method.</span></span>  
  
 <span data-ttu-id="b47ec-136">次の例では、2つの四角形の和集合を形成することによって、正形の領域を作成します。</span><span class="sxs-lookup"><span data-stu-id="b47ec-136">The following example creates a plus-shaped region by forming the union of two rectangles.</span></span> <span data-ttu-id="b47ec-137">この領域は、オブジェクトのクリッピング領域として指定され <xref:System.Drawing.Graphics> ます。</span><span class="sxs-lookup"><span data-stu-id="b47ec-137">That region is designated as the clipping region of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="b47ec-138">次に、クリッピング領域の内部に制限されている2つの線を描画します。</span><span class="sxs-lookup"><span data-stu-id="b47ec-138">Then the code draws two lines that are restricted to the interior of the clipping region.</span></span>  
  
```vb  
Dim graphics As Graphics = e.Graphics  
  
' Opaque red, width 5  
Dim pen As New Pen(Color.Red, 5)  
  
' Opaque aqua  
Dim brush As New SolidBrush(Color.FromArgb(255, 180, 255, 255))  
  
' Create a plus-shaped region by forming the union of two rectangles.  
Dim [region] As New [Region](New Rectangle(50, 0, 50, 150))  
[region].Union(New Rectangle(0, 50, 150, 50))  
graphics.FillRegion(brush, [region])  
  
' Set the clipping region.  
graphics.SetClip([region], CombineMode.Replace)  
  
' Draw two clipped lines.  
graphics.DrawLine(pen, 0, 30, 150, 160)  
graphics.DrawLine(pen, 40, 20, 190, 150)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
  
// Opaque red, width 5  
Pen pen = new Pen(Color.Red, 5);
  
// Opaque aqua  
SolidBrush brush = new SolidBrush(Color.FromArgb(255, 180, 255, 255));
  
// Create a plus-shaped region by forming the union of two rectangles.  
Region region = new Region(new Rectangle(50, 0, 50, 150));  
region.Union(new Rectangle(0, 50, 150, 50));  
graphics.FillRegion(brush, region);  
  
// Set the clipping region.  
graphics.SetClip(region, CombineMode.Replace);  
  
// Draw two clipped lines.  
graphics.DrawLine(pen, 0, 30, 150, 160);  
graphics.DrawLine(pen, 40, 20, 190, 150);  
```  
  
 <span data-ttu-id="b47ec-139">次の図は、クリップされた行を示しています。</span><span class="sxs-lookup"><span data-stu-id="b47ec-139">The following illustration shows the clipped lines:</span></span>  
  
 ![制限されたクリップ領域を示す図。](./media/managing-the-state-of-a-graphics-object/set-clipping-region-setclip-method.png)  
  
## <a name="see-also"></a><span data-ttu-id="b47ec-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="b47ec-141">See also</span></span>

- [<span data-ttu-id="b47ec-142">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="b47ec-142">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="b47ec-143">入れ子になっているグラフィックス コンテナーの使用</span><span class="sxs-lookup"><span data-stu-id="b47ec-143">Using Nested Graphics Containers</span></span>](using-nested-graphics-containers.md)
