---
title: '方法: 四角形内にテキストを折り返して描画する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drawing text in a rectangle
- text [Windows Forms], drawing in a rectangle
- strings [Windows Forms], drawing in a rectangle
ms.assetid: e1fb432a-dc90-48b5-9b6b-acc14507133d
ms.openlocfilehash: ace79e45737a3ce26d8bdcd603e923c1e6040d4d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981348"
---
# <a name="how-to-draw-wrapped-text-in-a-rectangle"></a><span data-ttu-id="736e5-102">方法: 四角形内にテキストを折り返して描画する</span><span class="sxs-lookup"><span data-stu-id="736e5-102">How to: Draw Wrapped Text in a Rectangle</span></span>
<span data-ttu-id="736e5-103"><xref:System.Drawing.Graphics.DrawString%2A> <xref:System.Drawing.Graphics> またはパラメーターを受け取るクラスのオーバーロードされたメソッドを使用することにより、ラップされたテキストを四角形で描画でき <xref:System.Drawing.Rectangle> <xref:System.Drawing.RectangleF> ます。</span><span class="sxs-lookup"><span data-stu-id="736e5-103">You can draw wrapped text in a rectangle by using the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method of the <xref:System.Drawing.Graphics> class that takes a <xref:System.Drawing.Rectangle> or <xref:System.Drawing.RectangleF> parameter.</span></span> <span data-ttu-id="736e5-104">また、とを使用し <xref:System.Drawing.Brush> <xref:System.Drawing.Font> ます。</span><span class="sxs-lookup"><span data-stu-id="736e5-104">You will also use a <xref:System.Drawing.Brush> and a <xref:System.Drawing.Font>.</span></span>  
  
 <span data-ttu-id="736e5-105">およびパラメーターを受け取るのオーバーロードされたメソッドを使用して、四角形内にラップされたテキストを描画することもでき <xref:System.Windows.Forms.TextRenderer.DrawText%2A> <xref:System.Windows.Forms.TextRenderer> <xref:System.Drawing.Rectangle> <xref:System.Windows.Forms.TextFormatFlags> ます。</span><span class="sxs-lookup"><span data-stu-id="736e5-105">You can also draw wrapped text in a rectangle by using the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> overloaded method of the <xref:System.Windows.Forms.TextRenderer> that takes a <xref:System.Drawing.Rectangle> and a <xref:System.Windows.Forms.TextFormatFlags> parameter.</span></span> <span data-ttu-id="736e5-106">また、とを使用し <xref:System.Drawing.Color> <xref:System.Drawing.Font> ます。</span><span class="sxs-lookup"><span data-stu-id="736e5-106">You will also use a <xref:System.Drawing.Color> and a <xref:System.Drawing.Font>.</span></span>  
  
 <span data-ttu-id="736e5-107">次の図は、メソッドを使用するときに四角形に描画されるテキストの出力を示してい <xref:System.Drawing.Graphics.DrawString%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="736e5-107">The following illustration shows the output of text drawn in the rectangle when you use the <xref:System.Drawing.Graphics.DrawString%2A> method:</span></span>
  
 ![DrawString メソッドを使用した場合の出力を示すスクリーンショット。](./media/how-to-draw-wrapped-text-in-a-rectangle/drawstring-method-font-text.png)  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a><span data-ttu-id="736e5-109">GDI + を使用して四角形内にラップされたテキストを描画するには</span><span class="sxs-lookup"><span data-stu-id="736e5-109">To draw wrapped text in a rectangle with GDI+</span></span>  
  
1. <span data-ttu-id="736e5-110">オーバーロードされたメソッドを使用して、 <xref:System.Drawing.Graphics.DrawString%2A> 必要なテキスト、 <xref:System.Drawing.Rectangle> または <xref:System.Drawing.RectangleF> を渡し <xref:System.Drawing.Font> <xref:System.Drawing.Brush> ます。</span><span class="sxs-lookup"><span data-stu-id="736e5-110">Use the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method, passing the text you want, <xref:System.Drawing.Rectangle> or <xref:System.Drawing.RectangleF>, <xref:System.Drawing.Font> and <xref:System.Drawing.Brush>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#50](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#50)]
     [!code-vb[System.Drawing.AlignDrawnText#50](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#50)]  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a><span data-ttu-id="736e5-111">GDI を使用して四角形内にラップされたテキストを描画するには</span><span class="sxs-lookup"><span data-stu-id="736e5-111">To draw wrapped text in a rectangle with GDI</span></span>  
  
1. <span data-ttu-id="736e5-112">列挙値を使用して、 <xref:System.Windows.Forms.TextFormatFlags> オーバーロードされたメソッドでテキストをラップすることを指定し <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 、必要なテキスト、 <xref:System.Drawing.Rectangle> 、およびを渡し <xref:System.Drawing.Font> <xref:System.Drawing.Color> ます。</span><span class="sxs-lookup"><span data-stu-id="736e5-112">Use the <xref:System.Windows.Forms.TextFormatFlags> enumeration value to specify the text should be wrapped with the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> overloaded method, passing the text you want, <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Font> and <xref:System.Drawing.Color>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#60)]
     [!code-vb[System.Drawing.AlignDrawnText#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#60)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="736e5-113">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="736e5-113">Compiling the Code</span></span>  
 <span data-ttu-id="736e5-114">前の例では、次のものが必要です。</span><span class="sxs-lookup"><span data-stu-id="736e5-114">The previous examples require:</span></span>  
  
- <span data-ttu-id="736e5-115"><xref:System.Windows.Forms.PaintEventArgs>`e`。これはのパラメーターです <xref:System.Windows.Forms.PaintEventHandler> 。</span><span class="sxs-lookup"><span data-stu-id="736e5-115"><xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="736e5-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="736e5-116">See also</span></span>

- [<span data-ttu-id="736e5-117">方法: GDI を使用してテキストを描画する</span><span class="sxs-lookup"><span data-stu-id="736e5-117">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
- [<span data-ttu-id="736e5-118">フォントとテキストの使用</span><span class="sxs-lookup"><span data-stu-id="736e5-118">Using Fonts and Text</span></span>](using-fonts-and-text.md)
- [<span data-ttu-id="736e5-119">方法: フォント ファミリとフォントを作成する</span><span class="sxs-lookup"><span data-stu-id="736e5-119">How to: Construct Font Families and Fonts</span></span>](how-to-construct-font-families-and-fonts.md)
- [<span data-ttu-id="736e5-120">方法: テキストを指定の位置に描画する</span><span class="sxs-lookup"><span data-stu-id="736e5-120">How to: Draw Text at a Specified Location</span></span>](how-to-draw-text-at-a-specified-location.md)
