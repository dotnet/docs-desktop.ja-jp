---
title: '方法: 曲線のパスを直線に平坦化する'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], flattening curves into lines
- curves [Windows Forms], flattening
- GraphicsPath object
- paths [Windows Forms], flattening
- drawing [Windows Forms], flattening curves
ms.assetid: e654b8de-25f4-4735-9208-42e4514a589c
ms.openlocfilehash: d59a802618ddd5080c651e822ed4c09641f7f170
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981843"
---
# <a name="how-to-flatten-a-curved-path-into-a-line"></a><span data-ttu-id="cb5ac-102">方法: 曲線のパスを直線に平坦化する</span><span class="sxs-lookup"><span data-stu-id="cb5ac-102">How to: Flatten a Curved Path into a Line</span></span>
<span data-ttu-id="cb5ac-103">オブジェクトは、一連 <xref:System.Drawing.Drawing2D.GraphicsPath> の行とベジエスプラインを格納します。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-103">A <xref:System.Drawing.Drawing2D.GraphicsPath> object stores a sequence of lines and Bézier splines.</span></span> <span data-ttu-id="cb5ac-104">パスにはいくつかの種類の曲線 (楕円、円弧、カーディナルスプライン) を追加できますが、パスに格納される前に各曲線がベジエスプラインに変換されます。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-104">You can add several types of curves (ellipses, arcs, cardinal splines) to a path, but each curve is converted to a Bézier spline before it is stored in the path.</span></span> <span data-ttu-id="cb5ac-105">パスのフラット化では、パス内の各ベジエスプラインを直線のシーケンスに変換します。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-105">Flattening a path consists of converting each Bézier spline in the path to a sequence of straight lines.</span></span> <span data-ttu-id="cb5ac-106">次の図は、フラット化の前後のパスを示しています。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-106">The following illustration shows a path before and after flattening.</span></span>  
  
 <span data-ttu-id="cb5ac-107">![直線と曲線](./media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")</span><span class="sxs-lookup"><span data-stu-id="cb5ac-107">![Straight Lines and Curves](./media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")</span></span>  
  
### <a name="to-flatten-a-path"></a><span data-ttu-id="cb5ac-108">パスを平坦化するには</span><span class="sxs-lookup"><span data-stu-id="cb5ac-108">To Flatten a Path</span></span>  
  
- <span data-ttu-id="cb5ac-109"><xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A>オブジェクトのメソッドを呼び出し <xref:System.Drawing.Drawing2D.GraphicsPath> ます。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-109">call the <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> method of a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="cb5ac-110">メソッドは、フラット化された <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> パスと元のパスの間の最大距離を指定する平坦化引数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="cb5ac-110">The <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> method receives a flatness argument that specifies the maximum distance between the flattened path and the original path.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb5ac-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="cb5ac-111">See also</span></span>

- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- [<span data-ttu-id="cb5ac-112">直線、曲線、および図形</span><span class="sxs-lookup"><span data-stu-id="cb5ac-112">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="cb5ac-113">パスの作成および描画</span><span class="sxs-lookup"><span data-stu-id="cb5ac-113">Constructing and Drawing Paths</span></span>](constructing-and-drawing-paths.md)
