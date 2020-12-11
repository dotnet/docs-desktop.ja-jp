---
title: '方法: ペンの色を設定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- pens [Windows Forms], setting color
- colored pens
ms.assetid: a9df06f9-a6d5-4d9b-a2d1-583943540775
ms.openlocfilehash: ee2d3f8cdf6dd10ca2a9ff0dd3e66b164c84f21b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981755"
---
# <a name="how-to-set-the-color-of-a-pen"></a><span data-ttu-id="e7643-102">方法: ペンの色を設定する</span><span class="sxs-lookup"><span data-stu-id="e7643-102">How to: Set the Color of a Pen</span></span>
<span data-ttu-id="e7643-103">この例では、既存のオブジェクトの色を変更します。 <xref:System.Drawing.Pen></span><span class="sxs-lookup"><span data-stu-id="e7643-103">This example changes the color of a pre-existing <xref:System.Drawing.Pen> object</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7643-104">例</span><span class="sxs-lookup"><span data-stu-id="e7643-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#9](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#9)]
 [!code-csharp[System.Drawing.ConceptualHowTos#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#9)]
 [!code-vb[System.Drawing.ConceptualHowTos#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#9)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e7643-105">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="e7643-105">Compiling the Code</span></span>  
 <span data-ttu-id="e7643-106">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e7643-106">This example requires:</span></span>  
  
- <span data-ttu-id="e7643-107"><xref:System.Drawing.Pen>という名前のオブジェクト `myPen` 。</span><span class="sxs-lookup"><span data-stu-id="e7643-107">A <xref:System.Drawing.Pen> object named `myPen`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="e7643-108">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="e7643-108">Robust Programming</span></span>  
 <span data-ttu-id="e7643-109"><xref:System.Drawing.Pen.Dispose%2A>の使用が完了した後、システムリソース (オブジェクトなど) を使用するオブジェクトに対してを呼び出す必要があり <xref:System.Drawing.Pen> ます。</span><span class="sxs-lookup"><span data-stu-id="e7643-109">You should call <xref:System.Drawing.Pen.Dispose%2A> on objects that consume system resources (such as <xref:System.Drawing.Pen> objects) after you are finished using them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7643-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="e7643-110">See also</span></span>

- <xref:System.Drawing.Pen>
- [<span data-ttu-id="e7643-111">グラフィックス プログラミングについて</span><span class="sxs-lookup"><span data-stu-id="e7643-111">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="e7643-112">方法: ペンを作成する</span><span class="sxs-lookup"><span data-stu-id="e7643-112">How to: Create a Pen</span></span>](how-to-create-a-pen.md)
- [<span data-ttu-id="e7643-113">ペンを使用した直線と図形の描画</span><span class="sxs-lookup"><span data-stu-id="e7643-113">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="e7643-114">GDI+ でのペン、直線、および四角形</span><span class="sxs-lookup"><span data-stu-id="e7643-114">Pens, Lines, and Rectangles in GDI+</span></span>](pens-lines-and-rectangles-in-gdi.md)
