---
title: グローバル変換とローカル変換
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- matrices [Windows Forms], using transformations
- transformations [Windows Forms], global
- transformations [Windows Forms], local
ms.assetid: b601d66d-d572-4f11-9d2e-92f0dc8893f3
ms.openlocfilehash: f62efb31e95b0797272997fadbc28459579a0de0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96979795"
---
# <a name="global-and-local-transformations"></a><span data-ttu-id="cced0-102">グローバル変換とローカル変換</span><span class="sxs-lookup"><span data-stu-id="cced0-102">Global and Local Transformations</span></span>
<span data-ttu-id="cced0-103">グローバル変換は、特定のオブジェクトによって描画されるすべてのアイテムに適用される変換です <xref:System.Drawing.Graphics> 。</span><span class="sxs-lookup"><span data-stu-id="cced0-103">A global transformation is a transformation that applies to every item drawn by a given <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="cced0-104">一方、ローカル変換は、描画される特定の項目に適用される変換です。</span><span class="sxs-lookup"><span data-stu-id="cced0-104">In contrast, a local transformation is a transformation that applies to a specific item to be drawn.</span></span>  
  
## <a name="global-transformations"></a><span data-ttu-id="cced0-105">グローバル変換</span><span class="sxs-lookup"><span data-stu-id="cced0-105">Global Transformations</span></span>  
 <span data-ttu-id="cced0-106">グローバル変換を作成するには、 <xref:System.Drawing.Graphics> オブジェクトを構築し、そのプロパティを操作し <xref:System.Drawing.Graphics.Transform%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="cced0-106">To create a global transformation, construct a <xref:System.Drawing.Graphics> object, and then manipulate its <xref:System.Drawing.Graphics.Transform%2A> property.</span></span> <span data-ttu-id="cced0-107"><xref:System.Drawing.Graphics.Transform%2A>プロパティは <xref:System.Drawing.Drawing2D.Matrix> オブジェクトであるため、アフィン変換の任意のシーケンスを保持できます。</span><span class="sxs-lookup"><span data-stu-id="cced0-107">The <xref:System.Drawing.Graphics.Transform%2A> property is a <xref:System.Drawing.Drawing2D.Matrix> object, so it can hold any sequence of affine transformations.</span></span> <span data-ttu-id="cced0-108">プロパティに格納されている変換 <xref:System.Drawing.Graphics.Transform%2A> は、ワールド変換と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="cced0-108">The transformation stored in the <xref:System.Drawing.Graphics.Transform%2A> property is called the world transformation.</span></span> <span data-ttu-id="cced0-109">クラスには <xref:System.Drawing.Graphics> <xref:System.Drawing.Graphics.MultiplyTransform%2A> 、、、 <xref:System.Drawing.Graphics.RotateTransform%2A> <xref:System.Drawing.Graphics.ScaleTransform%2A> 、およびという複合ワールド変換を構築するためのメソッドがいくつか用意されて <xref:System.Drawing.Graphics.TranslateTransform%2A> います。</span><span class="sxs-lookup"><span data-stu-id="cced0-109">The <xref:System.Drawing.Graphics> class provides several methods for building up a composite world transformation: <xref:System.Drawing.Graphics.MultiplyTransform%2A>, <xref:System.Drawing.Graphics.RotateTransform%2A>, <xref:System.Drawing.Graphics.ScaleTransform%2A>, and <xref:System.Drawing.Graphics.TranslateTransform%2A>.</span></span> <span data-ttu-id="cced0-110">次の例では、楕円を2回描画します。ワールド変換を作成する前に1回、その後に1回です。</span><span class="sxs-lookup"><span data-stu-id="cced0-110">The following example draws an ellipse twice: once before creating a world transformation and once after.</span></span> <span data-ttu-id="cced0-111">変換は、最初に y 方向の0.5 係数で拡大縮小し、次に x 方向に50単位を変換してから30°回転します。</span><span class="sxs-lookup"><span data-stu-id="cced0-111">The transformation first scales by a factor of 0.5 in the y direction, then translates 50 units in the x direction, and then rotates 30 degrees.</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.CoordinateSystems#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#21)]  
  
 <span data-ttu-id="cced0-112">次の図は、変換に関係するマトリックスを示しています。</span><span class="sxs-lookup"><span data-stu-id="cced0-112">The following illustration shows the matrices involved in the transformation.</span></span>  
  
 <span data-ttu-id="cced0-113">![変換](./media/aboutgdip05-art14.gif "AboutGdip05_art14")</span><span class="sxs-lookup"><span data-stu-id="cced0-113">![Transformations](./media/aboutgdip05-art14.gif "AboutGdip05_art14")</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cced0-114">前の例では、楕円は、クライアント領域の左上隅にある座標系の原点を中心に回転しています。</span><span class="sxs-lookup"><span data-stu-id="cced0-114">In the preceding example, the ellipse is rotated about the origin of the coordinate system, which is at the upper-left corner of the client area.</span></span> <span data-ttu-id="cced0-115">これにより、独自の中心点について楕円を回転する場合とは異なる結果が生成されます。</span><span class="sxs-lookup"><span data-stu-id="cced0-115">This produces a different result than rotating the ellipse about its own center.</span></span>  
  
## <a name="local-transformations"></a><span data-ttu-id="cced0-116">ローカル変換</span><span class="sxs-lookup"><span data-stu-id="cced0-116">Local Transformations</span></span>  
 <span data-ttu-id="cced0-117">ローカル変換は、描画される特定の項目に適用されます。</span><span class="sxs-lookup"><span data-stu-id="cced0-117">A local transformation applies to a specific item to be drawn.</span></span> <span data-ttu-id="cced0-118">たとえば、オブジェクトには、 <xref:System.Drawing.Drawing2D.GraphicsPath> <xref:System.Drawing.Drawing2D.GraphicsPath.Transform%2A> そのパスのデータポイントを変換できるメソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="cced0-118">For example, a <xref:System.Drawing.Drawing2D.GraphicsPath> object has a <xref:System.Drawing.Drawing2D.GraphicsPath.Transform%2A> method that allows you to transform the data points of that path.</span></span> <span data-ttu-id="cced0-119">次の例では、変換なしの四角形と回転変換を含むパスを描画します。</span><span class="sxs-lookup"><span data-stu-id="cced0-119">The following example draws a rectangle with no transformation and a path with a rotation transformation.</span></span> <span data-ttu-id="cced0-120">(ワールド変換がないと仮定します)。</span><span class="sxs-lookup"><span data-stu-id="cced0-120">(Assume that there is no world transformation.)</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.CoordinateSystems#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#22)]  
  
 <span data-ttu-id="cced0-121">ワールド変換とローカル変換を組み合わせて、さまざまな結果を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="cced0-121">You can combine the world transformation with local transformations to achieve a variety of results.</span></span> <span data-ttu-id="cced0-122">たとえば、ワールド変換を使用して座標系を変更し、ローカル変換を使用して、新しい座標系で描画されたオブジェクトの回転と拡大縮小を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="cced0-122">For example, you can use the world transformation to revise the coordinate system and use local transformations to rotate and scale objects drawn on the new coordinate system.</span></span>  
  
 <span data-ttu-id="cced0-123">クライアント領域の左端から200ピクセルの原点を持つ座標系と、クライアント領域の上端から150ピクセルを使用するとします。</span><span class="sxs-lookup"><span data-stu-id="cced0-123">Suppose you want a coordinate system that has its origin 200 pixels from the left edge of the client area and 150 pixels from the top of the client area.</span></span> <span data-ttu-id="cced0-124">さらに、測定単位をピクセルにする必要があるとします。 x 軸は右を指し、y 軸は上向きになります。</span><span class="sxs-lookup"><span data-stu-id="cced0-124">Furthermore, assume that you want the unit of measure to be the pixel, with the x-axis pointing to the right and the y-axis pointing up.</span></span> <span data-ttu-id="cced0-125">既定の座標系では y 軸が下向きになっているため、横軸全体で反射を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="cced0-125">The default coordinate system has the y-axis pointing down, so you need to perform a reflection across the horizontal axis.</span></span> <span data-ttu-id="cced0-126">次の図は、このようなリフレクションのマトリックスを示しています。</span><span class="sxs-lookup"><span data-stu-id="cced0-126">The following illustration shows the matrix of such a reflection.</span></span>  
  
 <span data-ttu-id="cced0-127">![変換](./media/aboutgdip05-art15.gif "AboutGdip05_art15")</span><span class="sxs-lookup"><span data-stu-id="cced0-127">![Transformations](./media/aboutgdip05-art15.gif "AboutGdip05_art15")</span></span>  
  
 <span data-ttu-id="cced0-128">次に、200ユニットを右および150単位に変換する必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="cced0-128">Next, assume you need to perform a translation 200 units to the right and 150 units down.</span></span>  
  
 <span data-ttu-id="cced0-129">次の例では、オブジェクトのワールド変換を設定することによって、記述した座標系を確立し <xref:System.Drawing.Graphics> ます。</span><span class="sxs-lookup"><span data-stu-id="cced0-129">The following example establishes the coordinate system just described by setting the world transformation of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.CoordinateSystems#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#23)]  
  
 <span data-ttu-id="cced0-130">次のコード (前の例の最後にあります) では、新しい座標系の原点の左下隅にある単一の四角形で構成されるパスを作成します。</span><span class="sxs-lookup"><span data-stu-id="cced0-130">The following code (placed at the end of the preceding example) creates a path that consists of a single rectangle with its lower-left corner at the origin of the new coordinate system.</span></span> <span data-ttu-id="cced0-131">四角形は、ローカル変換なしで1回、ローカル変換で1回入力します。</span><span class="sxs-lookup"><span data-stu-id="cced0-131">The rectangle is filled once with no local transformation and once with a local transformation.</span></span> <span data-ttu-id="cced0-132">ローカル変換は、係数2の後に30度回転する水平方向のスケーリングで構成されます。</span><span class="sxs-lookup"><span data-stu-id="cced0-132">The local transformation consists of a horizontal scaling by a factor of 2 followed by a 30-degree rotation.</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#24](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#24)]
 [!code-vb[System.Drawing.CoordinateSystems#24](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#24)]  
  
 <span data-ttu-id="cced0-133">次の図は、新しい座標系と2つの四角形を示しています。</span><span class="sxs-lookup"><span data-stu-id="cced0-133">The following illustration shows the new coordinate system and the two rectangles.</span></span>  
  
 <span data-ttu-id="cced0-134">![変換](./media/aboutgdip05-art16.gif "AboutGdip05_art16")</span><span class="sxs-lookup"><span data-stu-id="cced0-134">![Transformations](./media/aboutgdip05-art16.gif "AboutGdip05_art16")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cced0-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="cced0-135">See also</span></span>

- [<span data-ttu-id="cced0-136">座標系と変換</span><span class="sxs-lookup"><span data-stu-id="cced0-136">Coordinate Systems and Transformations</span></span>](coordinate-systems-and-transformations.md)
- [<span data-ttu-id="cced0-137">マネージド GDI+ での変換の使用</span><span class="sxs-lookup"><span data-stu-id="cced0-137">Using Transformations in Managed GDI+</span></span>](using-transformations-in-managed-gdi.md)
