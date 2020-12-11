---
title: GDI+ での描画サーフェイスの制限
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, clipping
- clipping [Windows Forms], using GDI+
- GDI+, restricting drawing surface
ms.assetid: 8b5f71d9-d2f0-4540-9c41-740f90fd4c26
ms.openlocfilehash: d0508166f905b45789ce638b03d0747dd6fa904e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981648"
---
# <a name="restricting-the-drawing-surface-in-gdi"></a><span data-ttu-id="3a781-102">GDI+ での描画サーフェイスの制限</span><span class="sxs-lookup"><span data-stu-id="3a781-102">Restricting the Drawing Surface in GDI+</span></span>
<span data-ttu-id="3a781-103">クリッピングには、特定の四角形または領域への描画の制限が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3a781-103">Clipping involves restricting drawing to a certain rectangle or region.</span></span> <span data-ttu-id="3a781-104">次の図は、ハート形の領域にクリップされた文字列 "Hello" を示しています。</span><span class="sxs-lookup"><span data-stu-id="3a781-104">The following illustration shows the string "Hello" clipped to a heart-shaped region.</span></span>  
  
 <span data-ttu-id="3a781-105">![制限付き描画面](./media/aboutgdip02-art30.gif "AboutGdip02_Art30")</span><span class="sxs-lookup"><span data-stu-id="3a781-105">![Restricted Drawing Surface](./media/aboutgdip02-art30.gif "AboutGdip02_Art30")</span></span>  
  
## <a name="clipping-with-regions"></a><span data-ttu-id="3a781-106">領域でのクリッピング</span><span class="sxs-lookup"><span data-stu-id="3a781-106">Clipping with Regions</span></span>  
 <span data-ttu-id="3a781-107">領域はパスから構築でき、パスには文字列のアウトラインを含めることができるため、表示されているテキストを使用してクリッピングを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="3a781-107">Regions can be constructed from paths, and paths can contain the outlines of strings, so you can use outlined text for clipping.</span></span> <span data-ttu-id="3a781-108">次の図は、テキスト文字列の内部にクリップされた同心円の楕円のセットを示しています。</span><span class="sxs-lookup"><span data-stu-id="3a781-108">The following illustration shows a set of concentric ellipses clipped to the interior of a string of text.</span></span>  
  
 <span data-ttu-id="3a781-109">![制限付き描画面](./media/aboutgdip02-art31.gif "AboutGdip02_Art31")</span><span class="sxs-lookup"><span data-stu-id="3a781-109">![Restricted Drawing Surface](./media/aboutgdip02-art31.gif "AboutGdip02_Art31")</span></span>  
  
 <span data-ttu-id="3a781-110">クリッピングを使用して描画するには、オブジェクトを作成し、 <xref:System.Drawing.Graphics> その <xref:System.Drawing.Graphics.Clip%2A> プロパティを設定して、同じオブジェクトの描画メソッドを呼び出し <xref:System.Drawing.Graphics> ます。</span><span class="sxs-lookup"><span data-stu-id="3a781-110">To draw with clipping, create a <xref:System.Drawing.Graphics> object, set its <xref:System.Drawing.Graphics.Clip%2A> property, and then call the drawing methods of that same <xref:System.Drawing.Graphics> object:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#91](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#91)]
 [!code-vb[LinesCurvesAndShapes#91](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#91)]  
  
## <a name="see-also"></a><span data-ttu-id="3a781-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="3a781-111">See also</span></span>

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Region?displayProperty=nameWithType>
- [<span data-ttu-id="3a781-112">直線、曲線、および図形</span><span class="sxs-lookup"><span data-stu-id="3a781-112">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="3a781-113">領域の使用</span><span class="sxs-lookup"><span data-stu-id="3a781-113">Using Regions</span></span>](using-regions.md)
