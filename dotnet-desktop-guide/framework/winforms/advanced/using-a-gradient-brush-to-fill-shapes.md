---
title: グラデーション ブラシを使用した図形の塗りつぶし
ms.date: 03/30/2017
helpviewer_keywords:
- brushes [Windows Forms], gradient brushes
- gradient brushes
- examples [Windows Forms], gradient brushes
ms.assetid: 2c6037b9-05bd-44c0-a22a-19584b722524
ms.openlocfilehash: 7ff555ba4fd81e9123e5f9e9feed38a0ec9d0a08
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981607"
---
# <a name="using-a-gradient-brush-to-fill-shapes"></a><span data-ttu-id="8d16b-102">グラデーション ブラシを使用した図形の塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="8d16b-102">Using a Gradient Brush to Fill Shapes</span></span>
<span data-ttu-id="8d16b-103">グラデーションブラシを使用して、徐々に変化する色で図形を塗りつぶすことができます。</span><span class="sxs-lookup"><span data-stu-id="8d16b-103">You can use a gradient brush to fill a shape with a gradually changing color.</span></span> <span data-ttu-id="8d16b-104">たとえば、横方向のグラデーションを使用すると、図形の左端から右端に移動したときに徐々に変化する色で図形を塗りつぶすことができます。</span><span class="sxs-lookup"><span data-stu-id="8d16b-104">For example, you can use a horizontal gradient to fill a shape with color that changes gradually as you move from the left edge of the shape to the right edge.</span></span> <span data-ttu-id="8d16b-105">左端が黒 (赤、緑、青のコンポーネント0、0、0で表されます) と、赤 (255, 0, 0 で表されます) である四角形を想像してみてください。</span><span class="sxs-lookup"><span data-stu-id="8d16b-105">Imagine a rectangle with a left edge that is black (represented by red, green, and blue components 0, 0, 0) and a right edge that is red (represented by 255, 0, 0).</span></span> <span data-ttu-id="8d16b-106">四角形の幅が256ピクセルの場合、指定されたピクセルの赤の要素は、その左のピクセルの赤の要素より1大きい値になります。</span><span class="sxs-lookup"><span data-stu-id="8d16b-106">If the rectangle is 256 pixels wide, the red component of a given pixel will be one greater than the red component of the pixel to its left.</span></span> <span data-ttu-id="8d16b-107">行の左端のピクセルにはカラーコンポーネント (0, 0, 0) があり、2番目のピクセルは (1, 0, 0)、3番目のピクセルは (2, 0, 0) のようになります。これは、カラーコンポーネント (255, 0, 0) を持つ右端のピクセルに到達するまで続きます。</span><span class="sxs-lookup"><span data-stu-id="8d16b-107">The leftmost pixel in a row has color components (0, 0, 0), the second pixel has (1, 0, 0), the third pixel has (2, 0, 0), and so on, until you get to the rightmost pixel, which has color components (255, 0, 0).</span></span> <span data-ttu-id="8d16b-108">これらの補間カラー値は、色グラデーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="8d16b-108">These interpolated color values make up the color gradient.</span></span>  
  
 <span data-ttu-id="8d16b-109">線状グラデーションは、水平方向、垂直方向、または平行移動したときに、指定した斜線に色が変化します。</span><span class="sxs-lookup"><span data-stu-id="8d16b-109">A linear gradient changes color as you move horizontally, vertically, or parallel to a specified slanted line.</span></span> <span data-ttu-id="8d16b-110">パスの内側と境界について移動すると、パスのグラデーションの色が変わります。</span><span class="sxs-lookup"><span data-stu-id="8d16b-110">A path gradient changes color as you move about the interior and boundary of a path.</span></span> <span data-ttu-id="8d16b-111">パスのグラデーションをカスタマイズして、さまざまな効果を実現できます。</span><span class="sxs-lookup"><span data-stu-id="8d16b-111">You can customize path gradients to achieve a wide variety of effects.</span></span>  
  
 <span data-ttu-id="8d16b-112">次の図は、線状グラデーションブラシで塗りつぶされた四角形と、パスグラデーションブラシで塗りつぶされた楕円を示しています。</span><span class="sxs-lookup"><span data-stu-id="8d16b-112">The following illustration shows a rectangle filled with a linear gradient brush and an ellipse filled with a path gradient brush:</span></span>  
  
 ![楕円のグラデーションブラシで塗りつぶされた四角形。](./media/using-a-gradient-brush-to-fill-shapes/rectangle-ellipse-gradient-brush.png)  
  
## <a name="in-this-section"></a><span data-ttu-id="8d16b-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8d16b-114">In This Section</span></span>  
 [<span data-ttu-id="8d16b-115">方法: 線形グラデーションを作成する</span><span class="sxs-lookup"><span data-stu-id="8d16b-115">How to: Create a Linear Gradient</span></span>](how-to-create-a-linear-gradient.md)  
 <span data-ttu-id="8d16b-116">クラスを使用して線形グラデーションを作成する方法について説明し <xref:System.Drawing.Drawing2D.LinearGradientBrush> ます。</span><span class="sxs-lookup"><span data-stu-id="8d16b-116">Shows how to create a linear gradient using the <xref:System.Drawing.Drawing2D.LinearGradientBrush> class.</span></span>  
  
 [<span data-ttu-id="8d16b-117">方法: パス グラデーションを作成する</span><span class="sxs-lookup"><span data-stu-id="8d16b-117">How to: Create a Path Gradient</span></span>](how-to-create-a-path-gradient.md)  
 <span data-ttu-id="8d16b-118">クラスを使用してパスグラデーションを作成する方法について説明し <xref:System.Drawing.Drawing2D.PathGradientBrush> ます。</span><span class="sxs-lookup"><span data-stu-id="8d16b-118">Describes how to create a path gradient using the <xref:System.Drawing.Drawing2D.PathGradientBrush> class.</span></span>  
  
 [<span data-ttu-id="8d16b-119">方法: グラデーションに対してガンマ補正を適用する</span><span class="sxs-lookup"><span data-stu-id="8d16b-119">How to: Apply Gamma Correction to a Gradient</span></span>](how-to-apply-gamma-correction-to-a-gradient.md)  
 <span data-ttu-id="8d16b-120">グラデーションブラシでガンマ補正を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8d16b-120">Explains how to use gamma correction with a gradient brush.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="8d16b-121">リファレンス</span><span class="sxs-lookup"><span data-stu-id="8d16b-121">Reference</span></span>  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>  
 <span data-ttu-id="8d16b-122">このクラスの説明が含まれ、そのすべてのメンバーへのリンクがあります。</span><span class="sxs-lookup"><span data-stu-id="8d16b-122">Contains a description of this class and has links to all of its members.</span></span>  
  
 <xref:System.Drawing.Drawing2D.PathGradientBrush?displayProperty=nameWithType>  
 <span data-ttu-id="8d16b-123">このクラスの説明が含まれ、そのすべてのメンバーへのリンクがあります。</span><span class="sxs-lookup"><span data-stu-id="8d16b-123">Contains a description of this class and has links to all of its members.</span></span>
