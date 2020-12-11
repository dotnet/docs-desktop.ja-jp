---
title: '方法: Windows フォームに塗りつぶした四角形を描画する'
description: Windows フォームで塗りつぶされた四角形をプログラムで描画する方法について説明します。 また、コードをコンパイルする方法についても説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Graphics.FillRectangle
helpviewer_keywords:
- drawing [Windows Forms], rectangles
- rectangles [Windows Forms], drawing
- drawing rectangles
ms.assetid: d656a93c-987d-4809-aafd-493fe17450f0
ms.openlocfilehash: 0ad8ec97000e29b2194a9eda713aa43d5557b44c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974401"
---
# <a name="how-to-draw-a-filled-rectangle-on-a-windows-form"></a><span data-ttu-id="3a934-104">方法: Windows フォームに塗りつぶした四角形を描画する</span><span class="sxs-lookup"><span data-stu-id="3a934-104">How to: Draw a Filled Rectangle on a Windows Form</span></span>
<span data-ttu-id="3a934-105">この例では、フォーム上に塗りつぶされた四角形を描画します。</span><span class="sxs-lookup"><span data-stu-id="3a934-105">This example draws a filled rectangle on a form.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a934-106">例</span><span class="sxs-lookup"><span data-stu-id="3a934-106">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#2](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#2)]
 [!code-csharp[System.Drawing.ConceptualHowTos#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#2)]
 [!code-vb[System.Drawing.ConceptualHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#2)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3a934-107">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="3a934-107">Compiling the Code</span></span>  
 <span data-ttu-id="3a934-108">イベントハンドラーでは、このメソッドを呼び出すことはできません <xref:System.Windows.Forms.Form.Load> 。</span><span class="sxs-lookup"><span data-stu-id="3a934-108">You cannot call this method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="3a934-109">フォームのサイズが変更されたり、別の形式で隠されたりした場合、描画コンテンツは再描画されません。</span><span class="sxs-lookup"><span data-stu-id="3a934-109">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="3a934-110">コンテンツが自動的に再描画されるようにするには、メソッドをオーバーライドする必要があり <xref:System.Windows.Forms.Control.OnPaint%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="3a934-110">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="3a934-111">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="3a934-111">Robust Programming</span></span>  
 <span data-ttu-id="3a934-112">やオブジェクトなどの <xref:System.IDisposable.Dispose%2A> システムリソースを消費するオブジェクトに対しては、常にを呼び出す必要があり <xref:System.Drawing.Brush> <xref:System.Drawing.Graphics> ます。</span><span class="sxs-lookup"><span data-stu-id="3a934-112">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Brush> and <xref:System.Drawing.Graphics> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a934-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="3a934-113">See also</span></span>

- <xref:System.Drawing.Graphics.FillRectangle%2A>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [<span data-ttu-id="3a934-114">グラフィックス プログラミングについて</span><span class="sxs-lookup"><span data-stu-id="3a934-114">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="3a934-115">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="3a934-115">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="3a934-116">ペンを使用した直線と図形の描画</span><span class="sxs-lookup"><span data-stu-id="3a934-116">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="3a934-117">GDI+ でのブラシと塗りつぶされた図形</span><span class="sxs-lookup"><span data-stu-id="3a934-117">Brushes and Filled Shapes in GDI+</span></span>](brushes-and-filled-shapes-in-gdi.md)
