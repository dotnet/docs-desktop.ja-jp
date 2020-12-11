---
title: '方法: ライン キャップを使用した直線を描画する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drawing [Windows Forms], lines
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
- drawing lines [Windows Forms], line caps
ms.assetid: eb68c3e1-c400-4886-8a04-76978a429cb6
ms.openlocfilehash: 34abfc86e980a24ebb835cfd88d2522f8372c68d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981411"
---
# <a name="how-to-draw-a-line-with-line-caps"></a><span data-ttu-id="2bb89-102">方法: ライン キャップを使用した直線を描画する</span><span class="sxs-lookup"><span data-stu-id="2bb89-102">How to: Draw a Line with Line Caps</span></span>
<span data-ttu-id="2bb89-103">直線キャップと呼ばれる複数の図形のいずれかで、行の先頭または末尾を描画できます。</span><span class="sxs-lookup"><span data-stu-id="2bb89-103">You can draw the start or end of a line in one of several shapes called line caps.</span></span> <span data-ttu-id="2bb89-104">GDI + では、丸い、正方形、ひし形、矢じりいった複数のラインキャップがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2bb89-104">GDI+ supports several line caps, such as round, square, diamond, and arrowhead.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2bb89-105">例</span><span class="sxs-lookup"><span data-stu-id="2bb89-105">Example</span></span>  
 <span data-ttu-id="2bb89-106">線の始点 (始点のキャップ)、直線の端 (端のキャップ)、または破線の破線 (ダッシュキャップ) を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="2bb89-106">You can specify line caps for the start of a line (start cap), the end of a line (end cap), or the dashes of a dashed line (dash cap).</span></span>  
  
 <span data-ttu-id="2bb89-107">次の例では、一方の端の矢印ともう一方の端に丸いキャップを持つ線を描画します。</span><span class="sxs-lookup"><span data-stu-id="2bb89-107">The following example draws a line with an arrowhead at one end and a round cap at the other end.</span></span> <span data-ttu-id="2bb89-108">この図は、結果として得られる行を示しています。</span><span class="sxs-lookup"><span data-stu-id="2bb89-108">The illustration shows the resulting line:</span></span>  
  
 ![丸いキャップの線を示す図。](./media/how-to-draw-a-line-with-line-caps/line-cap-arrowhead-example.gif)  
  
 [!code-csharp[System.Drawing.UsingAPen#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.UsingAPen#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2bb89-110">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="2bb89-110">Compiling the Code</span></span>  
  
- <span data-ttu-id="2bb89-111">Windows フォームを作成し、フォームのイベントを処理し <xref:System.Windows.Forms.Control.Paint> ます。</span><span class="sxs-lookup"><span data-stu-id="2bb89-111">Create a Windows Form and handle the form's <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="2bb89-112">コード例を <xref:System.Windows.Forms.Control.Paint> として渡すイベントハンドラーに貼り付け `e` <xref:System.Windows.Forms.PaintEventArgs> ます。</span><span class="sxs-lookup"><span data-stu-id="2bb89-112">Paste the example code into the <xref:System.Windows.Forms.Control.Paint> event handler passing `e` as <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bb89-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="2bb89-113">See also</span></span>

- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- <xref:System.Drawing.Drawing2D.LineCap?displayProperty=nameWithType>
- [<span data-ttu-id="2bb89-114">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="2bb89-114">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="2bb89-115">ペンを使用した直線と図形の描画</span><span class="sxs-lookup"><span data-stu-id="2bb89-115">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
