---
title: GDI+ でのブラシと塗りつぶされた図形
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [Windows Forms], GDI+
- filled shapes [Windows Forms], GDI+
- shapes [Windows Forms], GDI+
- GDI+, brushes
- GDI+, filled shapes
- gradient brushes
- brushes [Windows Forms], gradient
ms.assetid: e863e2a7-0294-4130-99b6-f1ea3201e7cd
ms.openlocfilehash: 45ef0b5920e43300e047d363149ea10a7833477b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974455"
---
# <a name="brushes-and-filled-shapes-in-gdi"></a><span data-ttu-id="b2bfc-102">GDI+ でのブラシと塗りつぶされた図形</span><span class="sxs-lookup"><span data-stu-id="b2bfc-102">Brushes and Filled Shapes in GDI+</span></span>
<span data-ttu-id="b2bfc-103">四角形や楕円などの閉じた図形は、アウトラインと内部で構成されます。</span><span class="sxs-lookup"><span data-stu-id="b2bfc-103">A closed shape, such as a rectangle or an ellipse, consists of an outline and an interior.</span></span> <span data-ttu-id="b2bfc-104">輪郭がペンで描画され、内部にブラシが挿入されます。</span><span class="sxs-lookup"><span data-stu-id="b2bfc-104">The outline is drawn with a pen and the interior is filled with a brush.</span></span> <span data-ttu-id="b2bfc-105">Gdi + には、閉じられた図形の内部を埋めるために、、、、、およびのブラシクラスがいくつか用意されて <xref:System.Drawing.SolidBrush> <xref:System.Drawing.Drawing2D.HatchBrush> います <xref:System.Drawing.TextureBrush> <xref:System.Drawing.Drawing2D.LinearGradientBrush> <xref:System.Drawing.Drawing2D.PathGradientBrush> 。</span><span class="sxs-lookup"><span data-stu-id="b2bfc-105">GDI+ provides several brush classes for filling the interiors of closed shapes: <xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, and <xref:System.Drawing.Drawing2D.PathGradientBrush>.</span></span> <span data-ttu-id="b2bfc-106">これらのクラスはすべて、クラスから継承さ <xref:System.Drawing.Brush> れます。</span><span class="sxs-lookup"><span data-stu-id="b2bfc-106">All of these classes inherit from the <xref:System.Drawing.Brush> class.</span></span> <span data-ttu-id="b2bfc-107">次の図は、単色ブラシで塗りつぶされた四角形と、ハッチブラシで塗りつぶされた楕円を示しています。</span><span class="sxs-lookup"><span data-stu-id="b2bfc-107">The following illustration shows a rectangle filled with a solid brush and an ellipse filled with a hatch brush.</span></span>  
  
 <span data-ttu-id="b2bfc-108">![塗りつぶされた図形](./media/aboutgdip02-art17.gif "Aboutgdip02_art17")</span><span class="sxs-lookup"><span data-stu-id="b2bfc-108">![Filled Shapes](./media/aboutgdip02-art17.gif "Aboutgdip02_art17")</span></span>  
  
## <a name="solid-brushes"></a><span data-ttu-id="b2bfc-109">ソリッドブラシ</span><span class="sxs-lookup"><span data-stu-id="b2bfc-109">Solid Brushes</span></span>  
 <span data-ttu-id="b2bfc-110">閉じた図形を塗りつぶすには、クラスのインスタンス <xref:System.Drawing.Graphics> とが必要 <xref:System.Drawing.Brush> です。</span><span class="sxs-lookup"><span data-stu-id="b2bfc-110">To fill a closed shape, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Brush>.</span></span> <span data-ttu-id="b2bfc-111">クラスのインスタンスは、やなどの <xref:System.Drawing.Graphics> メソッドを提供 <xref:System.Drawing.Graphics.FillRectangle%2A> し、 <xref:System.Drawing.Graphics.FillEllipse%2A> <xref:System.Drawing.Brush> 色やパターンなどの塗りつぶしの属性を格納します。</span><span class="sxs-lookup"><span data-stu-id="b2bfc-111">The instance of the <xref:System.Drawing.Graphics> class provides methods, such as <xref:System.Drawing.Graphics.FillRectangle%2A> and <xref:System.Drawing.Graphics.FillEllipse%2A>, and the <xref:System.Drawing.Brush> stores attributes of the fill, such as color and pattern.</span></span> <span data-ttu-id="b2bfc-112">は、 <xref:System.Drawing.Brush> 引数の1つとして fill メソッドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="b2bfc-112">The <xref:System.Drawing.Brush> is passed as one of the arguments to the fill method.</span></span> <span data-ttu-id="b2bfc-113">次のコード例では、楕円に純色を赤で塗りつぶす方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b2bfc-113">The following code example shows how to fill an ellipse with a solid red color.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#121](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#121)]
 [!code-vb[LinesCurvesAndShapes#121](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#121)]  
  
> [!NOTE]
> <span data-ttu-id="b2bfc-114">前の例では、ブラシは型 <xref:System.Drawing.SolidBrush> であり、から継承され <xref:System.Drawing.Brush> ます。</span><span class="sxs-lookup"><span data-stu-id="b2bfc-114">In the preceding example, the brush is of type <xref:System.Drawing.SolidBrush>, which inherits from <xref:System.Drawing.Brush>.</span></span>  
  
## <a name="hatch-brushes"></a><span data-ttu-id="b2bfc-115">ハッチブラシ</span><span class="sxs-lookup"><span data-stu-id="b2bfc-115">Hatch Brushes</span></span>  
 <span data-ttu-id="b2bfc-116">ハッチブラシを使用して図形を塗りつぶす場合は、前景色、背景色、およびハッチスタイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="b2bfc-116">When you fill a shape with a hatch brush, you specify a foreground color, a background color, and a hatch style.</span></span> <span data-ttu-id="b2bfc-117">前景色は陰影の色です。</span><span class="sxs-lookup"><span data-stu-id="b2bfc-117">The foreground color is the color of the hatching.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#122](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#122)]
 [!code-vb[LinesCurvesAndShapes#122](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#122)]  
  
 <span data-ttu-id="b2bfc-118">GDI + は、50を超えるハッチスタイルを提供します。次の図に示す3つのスタイルは、、、 <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal> <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal> および <xref:System.Drawing.Drawing2D.HatchStyle.Cross> です。</span><span class="sxs-lookup"><span data-stu-id="b2bfc-118">GDI+ provides more than 50 hatch styles; the three styles shown in the following illustration are <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>, <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>, and <xref:System.Drawing.Drawing2D.HatchStyle.Cross>.</span></span>  
  
 <span data-ttu-id="b2bfc-119">![塗りつぶされた図形](./media/aboutgdip02-art18.gif "Aboutgdip02_art18")</span><span class="sxs-lookup"><span data-stu-id="b2bfc-119">![Filled Shapes](./media/aboutgdip02-art18.gif "Aboutgdip02_art18")</span></span>  
  
## <a name="texture-brushes"></a><span data-ttu-id="b2bfc-120">テクスチャブラシ</span><span class="sxs-lookup"><span data-stu-id="b2bfc-120">Texture Brushes</span></span>  
 <span data-ttu-id="b2bfc-121">テクスチャブラシを使用すると、ビットマップに格納されているパターンで図形を塗りつぶすことができます。</span><span class="sxs-lookup"><span data-stu-id="b2bfc-121">With a texture brush, you can fill a shape with a pattern stored in a bitmap.</span></span> <span data-ttu-id="b2bfc-122">たとえば、次の画像がという名前のディスクファイルに格納されているとし `MyTexture.bmp` ます。</span><span class="sxs-lookup"><span data-stu-id="b2bfc-122">For example, suppose the following picture is stored in a disk file named `MyTexture.bmp`.</span></span>  
  
 <span data-ttu-id="b2bfc-123">![塗りつぶされた図形](./media/aboutgdip02-art19.gif "Aboutgdip02_Art19")</span><span class="sxs-lookup"><span data-stu-id="b2bfc-123">![Filled Shape](./media/aboutgdip02-art19.gif "Aboutgdip02_Art19")</span></span>  
  
 <span data-ttu-id="b2bfc-124">次のコード例では、に格納されている画像を繰り返して楕円に入力する方法を示し `MyTexture.bmp` ます。</span><span class="sxs-lookup"><span data-stu-id="b2bfc-124">The following code example shows how to fill an ellipse by repeating the picture stored in `MyTexture.bmp`.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#123](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#123)]
 [!code-vb[LinesCurvesAndShapes#123](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#123)]  
  
 <span data-ttu-id="b2bfc-125">次の図は、塗りつぶされた楕円を示しています。</span><span class="sxs-lookup"><span data-stu-id="b2bfc-125">The following illustration shows the filled ellipse.</span></span>  
  
 <span data-ttu-id="b2bfc-126">![塗りつぶされた図形](./media/aboutgdip02-art20.gif "AboutGdip02_Art20")</span><span class="sxs-lookup"><span data-stu-id="b2bfc-126">![Filled Shape](./media/aboutgdip02-art20.gif "AboutGdip02_Art20")</span></span>  
  
## <a name="gradient-brushes"></a><span data-ttu-id="b2bfc-127">グラデーションブラシ</span><span class="sxs-lookup"><span data-stu-id="b2bfc-127">Gradient Brushes</span></span>  
 <span data-ttu-id="b2bfc-128">GDI + には、線形とパスという2種類のグラデーションブラシが用意されています。</span><span class="sxs-lookup"><span data-stu-id="b2bfc-128">GDI+ provides two kinds of gradient brushes: linear and path.</span></span> <span data-ttu-id="b2bfc-129">線状グラデーションブラシを使用すると、図形を水平方向、垂直方向、または対角線方向に移動するときに徐々に変化する色で図形を塗りつぶすことができます。</span><span class="sxs-lookup"><span data-stu-id="b2bfc-129">You can use a linear gradient brush to fill a shape with color that changes gradually as you move across the shape horizontally, vertically, or diagonally.</span></span> <span data-ttu-id="b2bfc-130">次のコード例は、楕円の左端から右端に移動したときに青から緑に変化する水平グラデーションブラシを使用して楕円に塗りつぶす方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b2bfc-130">The following code example shows how to fill an ellipse with a horizontal gradient brush that changes from blue to green as you move from the left edge of the ellipse to the right edge.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#124](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#124)]
 [!code-vb[LinesCurvesAndShapes#124](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#124)]  
  
 <span data-ttu-id="b2bfc-131">次の図は、塗りつぶされた楕円を示しています。</span><span class="sxs-lookup"><span data-stu-id="b2bfc-131">The following illustration shows the filled ellipse.</span></span>  
  
 <span data-ttu-id="b2bfc-132">![塗りつぶされた図形](./media/aboutgdip02-art21.gif "AboutGdip02_Art21")</span><span class="sxs-lookup"><span data-stu-id="b2bfc-132">![Filled Shape](./media/aboutgdip02-art21.gif "AboutGdip02_Art21")</span></span>  
  
 <span data-ttu-id="b2bfc-133">パスグラデーションブラシは、図形の中心から端に向かって移動するときに色を変更するように構成できます。</span><span class="sxs-lookup"><span data-stu-id="b2bfc-133">A path gradient brush can be configured to change color as you move from the center of a shape toward the edge.</span></span>  
  
 <span data-ttu-id="b2bfc-134">![塗りつぶされた図形](./media/aboutgdip02-art22.gif "AboutGdip02_Art22")</span><span class="sxs-lookup"><span data-stu-id="b2bfc-134">![Filled Shape](./media/aboutgdip02-art22.gif "AboutGdip02_Art22")</span></span>  
  
 <span data-ttu-id="b2bfc-135">パスグラデーションブラシは非常に柔軟です。</span><span class="sxs-lookup"><span data-stu-id="b2bfc-135">Path gradient brushes are quite flexible.</span></span> <span data-ttu-id="b2bfc-136">次の図の三角形の塗りつぶしに使用されるグラデーションブラシは、中央の赤から頂点の3つの異なる色のそれぞれに徐々に変化します。</span><span class="sxs-lookup"><span data-stu-id="b2bfc-136">The gradient brush used to fill the triangle in the following illustration changes gradually from red at the center to each of three different colors at the vertices.</span></span>  
  
 <span data-ttu-id="b2bfc-137">![塗りつぶされた図形](./media/aboutgdip02-art23.gif "AboutGdip02_Art23")</span><span class="sxs-lookup"><span data-stu-id="b2bfc-137">![Filled Shape](./media/aboutgdip02-art23.gif "AboutGdip02_Art23")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2bfc-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="b2bfc-138">See also</span></span>

- <xref:System.Drawing.SolidBrush?displayProperty=nameWithType>
- <xref:System.Drawing.Drawing2D.HatchBrush?displayProperty=nameWithType>
- <xref:System.Drawing.TextureBrush?displayProperty=nameWithType>
- <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>
- [<span data-ttu-id="b2bfc-139">直線、曲線、および図形</span><span class="sxs-lookup"><span data-stu-id="b2bfc-139">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="b2bfc-140">方法: Windows フォームに塗りつぶした四角形を描画する</span><span class="sxs-lookup"><span data-stu-id="b2bfc-140">How to: Draw a Filled Rectangle on a Windows Form</span></span>](how-to-draw-a-filled-rectangle-on-a-windows-form.md)
- [<span data-ttu-id="b2bfc-141">方法: Windows フォームに塗りつぶした楕円を描画する</span><span class="sxs-lookup"><span data-stu-id="b2bfc-141">How to: Draw a Filled Ellipse on a Windows Form</span></span>](how-to-draw-a-filled-ellipse-on-a-windows-form.md)
