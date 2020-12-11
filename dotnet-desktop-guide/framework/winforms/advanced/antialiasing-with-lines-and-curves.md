---
title: 直線と曲線のアンチエイリアシング
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- antialiasing
- antialiasing [Windows Forms], smoothing modes
- GDI+, antialiasing
ms.assetid: 810da1a4-c136-4abf-88df-68e49efdd8d4
ms.openlocfilehash: 871c5cb3cd9356f677633acb04fe82021a9787c5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974898"
---
# <a name="antialiasing-with-lines-and-curves"></a><span data-ttu-id="22616-102">直線と曲線のアンチエイリアシング</span><span class="sxs-lookup"><span data-stu-id="22616-102">Antialiasing with Lines and Curves</span></span>
<span data-ttu-id="22616-103">GDI + を使用して線を描画する場合は、線の開始点と終了点を指定しますが、行の個々のピクセルに関する情報を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="22616-103">When you use GDI+ to draw a line, you provide the starting point and ending point of the line, but you do not have to provide any information about the individual pixels on the line.</span></span> <span data-ttu-id="22616-104">GDI + は、ディスプレイドライバーソフトウェアと連携して、特定のディスプレイデバイスの線を表示するためにオンにするピクセルを決定します。</span><span class="sxs-lookup"><span data-stu-id="22616-104">GDI+ works in conjunction with the display driver software to determine which pixels will be turned on to show the line on a particular display device.</span></span>  
  
## <a name="aliasing"></a><span data-ttu-id="22616-105">エイリアス化</span><span class="sxs-lookup"><span data-stu-id="22616-105">Aliasing</span></span>  
 <span data-ttu-id="22616-106">ポイント (4, 2) からポイント (16, 10) までの直線の赤い線を考えてみます。</span><span class="sxs-lookup"><span data-stu-id="22616-106">Consider the straight red line that goes from the point (4, 2) to the point (16, 10).</span></span> <span data-ttu-id="22616-107">座標系の原点が左上隅にあり、測定単位がピクセルであるとします。</span><span class="sxs-lookup"><span data-stu-id="22616-107">Assume the coordinate system has its origin in the upper-left corner and that the unit of measure is the pixel.</span></span> <span data-ttu-id="22616-108">また、x 軸が右を指し、y 軸が下向きであることを想定しています。</span><span class="sxs-lookup"><span data-stu-id="22616-108">Also assume that the x-axis points to the right and the y-axis points down.</span></span> <span data-ttu-id="22616-109">次の図は、色付きの背景で描画された赤い線の拡大ビューを示しています。</span><span class="sxs-lookup"><span data-stu-id="22616-109">The following illustration shows an enlarged view of the red line drawn on a multicolored background.</span></span>  
  
 <span data-ttu-id="22616-110">![線 (アンチエイリアシングなし)](./media/aboutgdip02-art33.gif "AboutGdip02_Art33")</span><span class="sxs-lookup"><span data-stu-id="22616-110">![Line, no antialiasing](./media/aboutgdip02-art33.gif "AboutGdip02_Art33")</span></span>  
  
 <span data-ttu-id="22616-111">線を描画するために使用される赤いピクセルは不透明です。</span><span class="sxs-lookup"><span data-stu-id="22616-111">The red pixels used to render the line are opaque.</span></span> <span data-ttu-id="22616-112">行には、部分的に透明なピクセルはありません。</span><span class="sxs-lookup"><span data-stu-id="22616-112">There are no partially transparent pixels in the line.</span></span> <span data-ttu-id="22616-113">この種類の線レンダリングでは、線がギザギザの形になり、線は階段状のように見えます。</span><span class="sxs-lookup"><span data-stu-id="22616-113">This type of line rendering gives the line a jagged appearance, and the line looks somewhat like a staircase.</span></span> <span data-ttu-id="22616-114">階段のある線を表すこの方法は、エイリアスと呼ばれます。階段は、理論上の線のエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="22616-114">This technique of representing a line with a staircase is called aliasing; the staircase is an alias for the theoretical line.</span></span>  
  
## <a name="antialiasing"></a><span data-ttu-id="22616-115">アンチエイリアシング</span><span class="sxs-lookup"><span data-stu-id="22616-115">Antialiasing</span></span>  
 <span data-ttu-id="22616-116">線を描画するためのより高度な手法として、部分的に透明なピクセルを不透明ピクセルと共に使用することがあります。</span><span class="sxs-lookup"><span data-stu-id="22616-116">A more sophisticated technique for rendering a line involves using partially transparent pixels along with opaque pixels.</span></span> <span data-ttu-id="22616-117">ピクセルは、直線に近いかどうかに応じて、純粋な赤または赤と背景色のブレンドに設定されます。</span><span class="sxs-lookup"><span data-stu-id="22616-117">Pixels are set to pure red, or to some blend of red and the background color, depending on how close they are to the line.</span></span> <span data-ttu-id="22616-118">この種類のレンダリングはアンチエイリアシングと呼ばれ、人間の目がより滑らかになる線になります。</span><span class="sxs-lookup"><span data-stu-id="22616-118">This type of rendering is called antialiasing and results in a line that the human eye perceives as more smooth.</span></span> <span data-ttu-id="22616-119">次の図は、アンチエイリアシングされた線を生成するために、特定のピクセルと背景をブレンドする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="22616-119">The following illustration shows how certain pixels are blended with the background to produce an antialiased line.</span></span>  
  
 <span data-ttu-id="22616-120">![アンチエイリアシング線](./media/aboutgdip02-art34.gif "AboutGdip02_Art34")</span><span class="sxs-lookup"><span data-stu-id="22616-120">![Antialiasing a Line](./media/aboutgdip02-art34.gif "AboutGdip02_Art34")</span></span>  
  
 <span data-ttu-id="22616-121">アンチエイリアシング (スムージングとも呼ばれます) を曲線に適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="22616-121">Antialiasing, also called smoothing, can also be applied to curves.</span></span> <span data-ttu-id="22616-122">次の図は、スムージングされた楕円の拡大表示を示しています。</span><span class="sxs-lookup"><span data-stu-id="22616-122">The following illustration shows an enlarged view of a smoothed ellipse.</span></span>  
  
 <span data-ttu-id="22616-123">![アンチエイリアシング曲線](./media/aboutgdip02-art35.gif "AboutGdip02_Art35")</span><span class="sxs-lookup"><span data-stu-id="22616-123">![Antialiasing Curves](./media/aboutgdip02-art35.gif "AboutGdip02_Art35")</span></span>  
  
 <span data-ttu-id="22616-124">次の図は、実際のサイズにおける同じ楕円を示しています。この楕円は、アンチエイリアシングを使用せず、アンチエイリアシングを使用して1回です。</span><span class="sxs-lookup"><span data-stu-id="22616-124">The following illustration shows the same ellipse in its actual size, once without antialiasing and once with antialiasing.</span></span>  
  
 <span data-ttu-id="22616-125">![アンチエイリアシング例](./media/aboutgdip02-art36.gif "AboutGdip02_Art36")</span><span class="sxs-lookup"><span data-stu-id="22616-125">![Antialiasing example](./media/aboutgdip02-art36.gif "AboutGdip02_Art36")</span></span>  
  
 <span data-ttu-id="22616-126">アンチエイリアシングを使用する直線と曲線を描画するには、クラスのインスタンスを作成 <xref:System.Drawing.Graphics> し、その <xref:System.Drawing.Graphics.SmoothingMode%2A> プロパティをまたはに設定し <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> <xref:System.Drawing.Drawing2D.SmoothingMode.HighQuality> ます。</span><span class="sxs-lookup"><span data-stu-id="22616-126">To draw lines and curves that use antialiasing, create an instance of the <xref:System.Drawing.Graphics> class and set its <xref:System.Drawing.Graphics.SmoothingMode%2A> property to <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> or <xref:System.Drawing.Drawing2D.SmoothingMode.HighQuality>.</span></span> <span data-ttu-id="22616-127">次に、同じクラスの描画メソッドの1つを呼び出し <xref:System.Drawing.Graphics> ます。</span><span class="sxs-lookup"><span data-stu-id="22616-127">Then call one of the drawing methods of that same <xref:System.Drawing.Graphics> class.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#81](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#81)]
 [!code-vb[LinesCurvesAndShapes#81](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#81)]  
  
## <a name="see-also"></a><span data-ttu-id="22616-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="22616-128">See also</span></span>

- <xref:System.Drawing.Drawing2D.SmoothingMode?displayProperty=nameWithType>
- [<span data-ttu-id="22616-129">直線、曲線、および図形</span><span class="sxs-lookup"><span data-stu-id="22616-129">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="22616-130">方法: テキストでのアンチエイリアシングの使用</span><span class="sxs-lookup"><span data-stu-id="22616-130">How to: Use Antialiasing with Text</span></span>](how-to-use-antialiasing-with-text.md)
