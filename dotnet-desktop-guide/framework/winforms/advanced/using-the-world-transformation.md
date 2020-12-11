---
title: ワールド変換の使用
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], world transformation
- world transformation [Windows Forms], examples
ms.assetid: 1e717711-1361-448e-aa49-0f3ec43110c9
ms.openlocfilehash: f40d7e8cb814344365e8b88c2659751903b79d77
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981184"
---
# <a name="using-the-world-transformation"></a><span data-ttu-id="a796d-102">ワールド変換の使用</span><span class="sxs-lookup"><span data-stu-id="a796d-102">Using the World Transformation</span></span>
<span data-ttu-id="a796d-103">ワールド変換は、クラスのプロパティです <xref:System.Drawing.Graphics> 。</span><span class="sxs-lookup"><span data-stu-id="a796d-103">The world transformation is a property of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="a796d-104">ワールド変換を指定する数値は、 <xref:System.Drawing.Drawing2D.Matrix> 3 ×3行列を表すオブジェクトに格納されます。</span><span class="sxs-lookup"><span data-stu-id="a796d-104">The numbers that specify the world transformation are stored in a <xref:System.Drawing.Drawing2D.Matrix> object, which represents a 3×3 matrix.</span></span> <span data-ttu-id="a796d-105"><xref:System.Drawing.Drawing2D.Matrix>クラスとクラスには、 <xref:System.Drawing.Graphics> ワールド変換行列の数値を設定するためのいくつかのメソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="a796d-105">The <xref:System.Drawing.Drawing2D.Matrix> and <xref:System.Drawing.Graphics> classes have several methods for setting the numbers in the world transformation matrix.</span></span>  
  
## <a name="different-types-of-transformations"></a><span data-ttu-id="a796d-106">さまざまな種類の変換</span><span class="sxs-lookup"><span data-stu-id="a796d-106">Different Types of Transformations</span></span>  
 <span data-ttu-id="a796d-107">次の例では、最初に50×50の四角形を作成し、原点 (0, 0) で検索します。</span><span class="sxs-lookup"><span data-stu-id="a796d-107">In the following example, the code first creates a 50×50 rectangle and locates it at the origin (0, 0).</span></span> <span data-ttu-id="a796d-108">原点は、クライアント領域の左上隅にあります。</span><span class="sxs-lookup"><span data-stu-id="a796d-108">The origin is at the upper-left corner of the client area.</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.MiscLegacyTopics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#11)]  
  
 <span data-ttu-id="a796d-109">次のコードは、x 方向の1.75 係数で四角形を拡大し、y 方向の0.5 の係数で四角形を縮小するスケーリング変換を適用します。</span><span class="sxs-lookup"><span data-stu-id="a796d-109">The following code applies a scaling transformation that expands the rectangle by a factor of 1.75 in the x direction and shrinks the rectangle by a factor of 0.5 in the y direction:</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.MiscLegacyTopics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#12)]  
  
 <span data-ttu-id="a796d-110">結果として、x 方向ではなく、元の方向よりも短い四角形が生成されます。</span><span class="sxs-lookup"><span data-stu-id="a796d-110">The result is a rectangle that is longer in the x direction and shorter in the y direction than the original.</span></span>  
  
 <span data-ttu-id="a796d-111">スケーリングではなく四角形を回転させるには、次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="a796d-111">To rotate the rectangle instead of scaling it, use the following code:</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.MiscLegacyTopics#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#13)]  
  
 <span data-ttu-id="a796d-112">四角形を変換するには、次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="a796d-112">To translate the rectangle, use the following code:</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#14](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.MiscLegacyTopics#14](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="a796d-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="a796d-113">See also</span></span>

- <xref:System.Drawing.Drawing2D.Matrix>
- [<span data-ttu-id="a796d-114">座標系と変換</span><span class="sxs-lookup"><span data-stu-id="a796d-114">Coordinate Systems and Transformations</span></span>](coordinate-systems-and-transformations.md)
- [<span data-ttu-id="a796d-115">マネージド GDI+ での変換の使用</span><span class="sxs-lookup"><span data-stu-id="a796d-115">Using Transformations in Managed GDI+</span></span>](using-transformations-in-managed-gdi.md)
