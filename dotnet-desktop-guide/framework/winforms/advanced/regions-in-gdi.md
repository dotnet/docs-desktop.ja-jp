---
title: GDI+ での領域
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, regions
- drawing [Windows Forms], regions
- regions
ms.assetid: 52184f9b-16dd-4bbd-85be-029112644ceb
ms.openlocfilehash: 33d4f4ecca7b9d777fa4eab5b6d031de10f03ccc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96979717"
---
# <a name="regions-in-gdi"></a><span data-ttu-id="bb200-102">GDI+ での領域</span><span class="sxs-lookup"><span data-stu-id="bb200-102">Regions in GDI+</span></span>
<span data-ttu-id="bb200-103">領域は、出力デバイスの表示領域の一部です。</span><span class="sxs-lookup"><span data-stu-id="bb200-103">A region is a portion of the display area of an output device.</span></span> <span data-ttu-id="bb200-104">領域は、単純な (単一の四角形) か、複雑な (多角形と閉じた曲線の組み合わせ) ことができます。</span><span class="sxs-lookup"><span data-stu-id="bb200-104">Regions can be simple (a single rectangle) or complex (a combination of polygons and closed curves).</span></span> <span data-ttu-id="bb200-105">次の図は、2つの領域を示しています。1つは四角形から構築され、もう1つはパスから構築されます。</span><span class="sxs-lookup"><span data-stu-id="bb200-105">The following illustration shows two regions: one constructed from a rectangle, and the other constructed from a path.</span></span>  
  
 <span data-ttu-id="bb200-106">![リージョン](./media/aboutgdip02-art27.gif "AboutGdip02_Art27")</span><span class="sxs-lookup"><span data-stu-id="bb200-106">![Regions](./media/aboutgdip02-art27.gif "AboutGdip02_Art27")</span></span>  
  
## <a name="using-regions"></a><span data-ttu-id="bb200-107">領域の使用</span><span class="sxs-lookup"><span data-stu-id="bb200-107">Using Regions</span></span>  
 <span data-ttu-id="bb200-108">領域は、多くの場合、クリッピングとヒットテストに使用されます。</span><span class="sxs-lookup"><span data-stu-id="bb200-108">Regions are often used for clipping and hit testing.</span></span> <span data-ttu-id="bb200-109">クリッピングでは、表示領域の特定の領域 (通常は更新が必要な部分) に描画を制限します。</span><span class="sxs-lookup"><span data-stu-id="bb200-109">Clipping involves restricting drawing to a certain region of the display area, usually the portion that needs to be updated.</span></span> <span data-ttu-id="bb200-110">ヒットテストでは、マウスボタンが押されたときにカーソルが画面の特定の領域内にあるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="bb200-110">Hit testing involves checking to determine whether the cursor is in a certain region of the screen when a mouse button is pressed.</span></span>  
  
 <span data-ttu-id="bb200-111">領域は、四角形またはパスから構築できます。</span><span class="sxs-lookup"><span data-stu-id="bb200-111">You can construct a region from a rectangle or a path.</span></span> <span data-ttu-id="bb200-112">また、既存の領域を組み合わせることによって、複雑な領域を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="bb200-112">You can also create complex regions by combining existing regions.</span></span> <span data-ttu-id="bb200-113">クラスには <xref:System.Drawing.Region> 、領域を結合するための次のメソッドが用意されています。、、 <xref:System.Drawing.Region.Intersect%2A> 、、 <xref:System.Drawing.Region.Union%2A> <xref:System.Drawing.Region.Xor%2A> <xref:System.Drawing.Region.Exclude%2A> および <xref:System.Drawing.Region.Complement%2A> 。</span><span class="sxs-lookup"><span data-stu-id="bb200-113">The <xref:System.Drawing.Region> class provides the following methods for combining regions: <xref:System.Drawing.Region.Intersect%2A>, <xref:System.Drawing.Region.Union%2A>, <xref:System.Drawing.Region.Xor%2A>, <xref:System.Drawing.Region.Exclude%2A>, and <xref:System.Drawing.Region.Complement%2A>.</span></span>  
  
 <span data-ttu-id="bb200-114">2つのリージョンの交差部分は、両方のリージョンに属するすべてのポイントの集合です。</span><span class="sxs-lookup"><span data-stu-id="bb200-114">The intersection of two regions is the set of all points belonging to both regions.</span></span> <span data-ttu-id="bb200-115">共用体は、一方または両方または両方の領域に属するすべての点のセットです。</span><span class="sxs-lookup"><span data-stu-id="bb200-115">The union is the set of all points belonging to one or the other or both regions.</span></span> <span data-ttu-id="bb200-116">領域の補数は、領域内に存在しないすべてのポイントのセットです。</span><span class="sxs-lookup"><span data-stu-id="bb200-116">The complement of a region is the set of all points that are not in the region.</span></span> <span data-ttu-id="bb200-117">次の図は、前の図に示した2つの領域の交差と和集合を示しています。</span><span class="sxs-lookup"><span data-stu-id="bb200-117">The following illustration shows the intersection and union of the two regions shown in the preceding illustration.</span></span>  
  
 <span data-ttu-id="bb200-118">![リージョン](./media/aboutgdip02-art28.gif "AboutGdip02_Art28")</span><span class="sxs-lookup"><span data-stu-id="bb200-118">![Regions](./media/aboutgdip02-art28.gif "AboutGdip02_Art28")</span></span>  
  
 <span data-ttu-id="bb200-119">領域 <xref:System.Drawing.Region.Xor%2A> のペアに適用されたメソッドは、ある領域に属するすべての点を含む領域を生成しますが、両方は含まれません。</span><span class="sxs-lookup"><span data-stu-id="bb200-119">The <xref:System.Drawing.Region.Xor%2A> method, applied to a pair of regions, produces a region that contains all points that belong to one region or the other, but not both.</span></span> <span data-ttu-id="bb200-120">メソッドは、 <xref:System.Drawing.Region.Exclude%2A> 領域のペアに適用され、2番目の領域にはない最初の領域のすべての点を含む領域を生成します。</span><span class="sxs-lookup"><span data-stu-id="bb200-120">The <xref:System.Drawing.Region.Exclude%2A> method, applied to a pair of regions, produces a region that contains all points in the first region that are not in the second region.</span></span> <span data-ttu-id="bb200-121">次の図は、 <xref:System.Drawing.Region.Xor%2A> <xref:System.Drawing.Region.Exclude%2A> このトピックの冒頭に示した2つの領域にメソッドとメソッドを適用した結果として得られる領域を示しています。</span><span class="sxs-lookup"><span data-stu-id="bb200-121">The following illustration shows the regions that result from applying the <xref:System.Drawing.Region.Xor%2A> and <xref:System.Drawing.Region.Exclude%2A> methods to the two regions shown at the beginning of this topic.</span></span>  
  
 <span data-ttu-id="bb200-122">![リージョン](./media/aboutgdip02-art29.gif "AboutGdip02_Art29")</span><span class="sxs-lookup"><span data-stu-id="bb200-122">![Regions](./media/aboutgdip02-art29.gif "AboutGdip02_Art29")</span></span>  
  
 <span data-ttu-id="bb200-123">領域にデータを格納するには、オブジェクト、オブジェクト、 <xref:System.Drawing.Graphics> <xref:System.Drawing.Brush> およびオブジェクトが必要 <xref:System.Drawing.Region> です。</span><span class="sxs-lookup"><span data-stu-id="bb200-123">To fill a region, you need a <xref:System.Drawing.Graphics> object, a <xref:System.Drawing.Brush> object, and a <xref:System.Drawing.Region> object.</span></span> <span data-ttu-id="bb200-124"><xref:System.Drawing.Graphics>オブジェクトはメソッドを提供し、 <xref:System.Drawing.Graphics.FillRegion%2A> <xref:System.Drawing.Brush> オブジェクトは color や pattern などの塗りつぶしの属性を格納します。</span><span class="sxs-lookup"><span data-stu-id="bb200-124">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.FillRegion%2A> method, and the <xref:System.Drawing.Brush> object stores attributes of the fill, such as color or pattern.</span></span> <span data-ttu-id="bb200-125">次の例では、純色で領域を塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="bb200-125">The following example fills a region with a solid color.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#61](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#61)]
 [!code-vb[LinesCurvesAndShapes#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#61)]  
  
## <a name="see-also"></a><span data-ttu-id="bb200-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="bb200-126">See also</span></span>

- <xref:System.Drawing.Region?displayProperty=nameWithType>
- [<span data-ttu-id="bb200-127">直線、曲線、および図形</span><span class="sxs-lookup"><span data-stu-id="bb200-127">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="bb200-128">領域の使用</span><span class="sxs-lookup"><span data-stu-id="bb200-128">Using Regions</span></span>](using-regions.md)
