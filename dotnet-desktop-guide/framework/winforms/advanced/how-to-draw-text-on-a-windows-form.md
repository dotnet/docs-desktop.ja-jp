---
title: '方法: Windows フォームにテキストを描画する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- forms [Windows Forms], drawing text
- text [Windows Forms], drawing
ms.assetid: 5d2447a9-21a1-4adc-b954-5516f2bb9b2c
ms.openlocfilehash: dc99a863765cd617c2ab4a636286f42f5e8daf79
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981371"
---
# <a name="how-to-draw-text-on-a-windows-form"></a><span data-ttu-id="4e2fd-102">方法: Windows フォームにテキストを描画する</span><span class="sxs-lookup"><span data-stu-id="4e2fd-102">How to: Draw Text on a Windows Form</span></span>
<span data-ttu-id="4e2fd-103">次のコード例は、のメソッドを使用して、フォームにテキストを描画する方法を示して <xref:System.Drawing.Graphics.DrawString%2A> <xref:System.Drawing.Graphics> います。</span><span class="sxs-lookup"><span data-stu-id="4e2fd-103">The following code example shows how to use the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> to draw text on a form.</span></span> <span data-ttu-id="4e2fd-104">または、を使用し <xref:System.Windows.Forms.TextRenderer> てフォーム上のテキストを描画することもできます。</span><span class="sxs-lookup"><span data-stu-id="4e2fd-104">Alternatively, you can use <xref:System.Windows.Forms.TextRenderer> for drawing text on a form.</span></span> <span data-ttu-id="4e2fd-105">詳細については、「 [方法: GDI を使用してテキストを描画する](how-to-draw-text-with-gdi.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e2fd-105">For more information, see [How to: Draw Text with GDI](how-to-draw-text-with-gdi.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e2fd-106">例</span><span class="sxs-lookup"><span data-stu-id="4e2fd-106">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#7](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#7)]
 [!code-csharp[System.Drawing.ConceptualHowTos#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#7)]
 [!code-vb[System.Drawing.ConceptualHowTos#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#7)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4e2fd-107">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="4e2fd-107">Compiling the Code</span></span>  
 <span data-ttu-id="4e2fd-108"><xref:System.Drawing.Graphics.DrawString%2A>イベントハンドラーでメソッドを呼び出すことはできません <xref:System.Windows.Forms.Form.Load> 。</span><span class="sxs-lookup"><span data-stu-id="4e2fd-108">You cannot call the <xref:System.Drawing.Graphics.DrawString%2A> method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="4e2fd-109">フォームのサイズが変更されたり、別の形式で隠されたりした場合、描画コンテンツは再描画されません。</span><span class="sxs-lookup"><span data-stu-id="4e2fd-109">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="4e2fd-110">コンテンツが自動的に再描画されるようにするには、メソッドをオーバーライドする必要があり <xref:System.Windows.Forms.Control.OnPaint%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="4e2fd-110">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="4e2fd-111">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="4e2fd-111">Robust Programming</span></span>  
 <span data-ttu-id="4e2fd-112">次の条件を満たす場合は、例外が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4e2fd-112">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="4e2fd-113">Arial フォントがインストールされていません。</span><span class="sxs-lookup"><span data-stu-id="4e2fd-113">The Arial font is not installed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e2fd-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="4e2fd-114">See also</span></span>

- <xref:System.Drawing.Graphics.DrawString%2A>
- <xref:System.Windows.Forms.TextRenderer.DrawText%2A>
- <xref:System.Drawing.StringFormat.FormatFlags%2A>
- <xref:System.Drawing.StringFormatFlags>
- <xref:System.Windows.Forms.TextFormatFlags>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [<span data-ttu-id="4e2fd-115">グラフィックス プログラミングについて</span><span class="sxs-lookup"><span data-stu-id="4e2fd-115">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="4e2fd-116">方法: GDI を使用してテキストを描画する</span><span class="sxs-lookup"><span data-stu-id="4e2fd-116">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
