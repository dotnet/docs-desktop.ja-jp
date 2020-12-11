---
title: '方法: テキストを指定の位置に描画する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing at specified locations [Windows Forms]
- drawing text
- drawing text [Windows Forms], specified locations [Windows Forms]
- Windows Forms, drawing text at a specified location
ms.assetid: 60816423-1c38-465e-980d-2c2b64d74086
ms.openlocfilehash: 0c36b00e4f6f71f0ecf8042853bb8e99e57854da
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981372"
---
# <a name="how-to-draw-text-at-a-specified-location"></a><span data-ttu-id="412ed-102">方法: テキストを指定の位置に描画する</span><span class="sxs-lookup"><span data-stu-id="412ed-102">How to: Draw Text at a Specified Location</span></span>
<span data-ttu-id="412ed-103">カスタム描画を実行すると、指定したポイントから始まる1本の水平線にテキストを描画できます。</span><span class="sxs-lookup"><span data-stu-id="412ed-103">When you perform custom drawing, you can draw text in a single horizontal line starting at a specified point.</span></span> <span data-ttu-id="412ed-104"><xref:System.Drawing.Graphics.DrawString%2A> <xref:System.Drawing.Graphics> またはパラメーターを受け取るクラスのオーバーロードされたメソッドを使用して、この方法でテキストを描画でき <xref:System.Drawing.Point> <xref:System.Drawing.PointF> ます。</span><span class="sxs-lookup"><span data-stu-id="412ed-104">You can draw text in this manner by using the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method of the <xref:System.Drawing.Graphics> class that takes a <xref:System.Drawing.Point> or <xref:System.Drawing.PointF> parameter.</span></span> <span data-ttu-id="412ed-105">また、この <xref:System.Drawing.Graphics.DrawString%2A> メソッドにはとが必要です。 <xref:System.Drawing.Brush><xref:System.Drawing.Font></span><span class="sxs-lookup"><span data-stu-id="412ed-105">The <xref:System.Drawing.Graphics.DrawString%2A> method also requires a <xref:System.Drawing.Brush> and <xref:System.Drawing.Font></span></span>  
  
 <span data-ttu-id="412ed-106">を受け取るのオーバーロードされたメソッドを使用することもでき <xref:System.Windows.Forms.TextRenderer.DrawText%2A> <xref:System.Windows.Forms.TextRenderer> <xref:System.Drawing.Point> ます。</span><span class="sxs-lookup"><span data-stu-id="412ed-106">You can also use the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> overloaded method of the <xref:System.Windows.Forms.TextRenderer> that takes a <xref:System.Drawing.Point>.</span></span> <span data-ttu-id="412ed-107"><xref:System.Windows.Forms.TextRenderer.DrawText%2A> また、にはとが必要です <xref:System.Drawing.Color> <xref:System.Drawing.Font> 。</span><span class="sxs-lookup"><span data-stu-id="412ed-107"><xref:System.Windows.Forms.TextRenderer.DrawText%2A> also requires a <xref:System.Drawing.Color> and a <xref:System.Drawing.Font>.</span></span>  
  
 <span data-ttu-id="412ed-108">次の図は、オーバーロードされたメソッドを使用する場合に、指定したポイントで描画されるテキストの出力を示して <xref:System.Drawing.Graphics.DrawString%2A> います。</span><span class="sxs-lookup"><span data-stu-id="412ed-108">The following illustration shows the output of text drawn at a specified point when you use the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method.</span></span>  
  
 ![指定したポイントのテキストの出力を示すスクリーンショット。](./media/how-to-draw-text-at-a-specified-location/font-text-specified-point.png)  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a><span data-ttu-id="412ed-110">GDI + を使用してテキストの行を描画するには</span><span class="sxs-lookup"><span data-stu-id="412ed-110">To draw a line of text with GDI+</span></span>  
  
1. <span data-ttu-id="412ed-111">メソッドを使用して、 <xref:System.Drawing.Graphics.DrawString%2A> 必要なテキストを渡し <xref:System.Drawing.Point> ます。または、、、およびを渡し <xref:System.Drawing.PointF> <xref:System.Drawing.Font> <xref:System.Drawing.Brush> ます。</span><span class="sxs-lookup"><span data-stu-id="412ed-111">Use the <xref:System.Drawing.Graphics.DrawString%2A> method, passing the text you want, <xref:System.Drawing.Point> or <xref:System.Drawing.PointF>, <xref:System.Drawing.Font>, and <xref:System.Drawing.Brush>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#30)]
     [!code-vb[System.Drawing.AlignDrawnText#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#30)]  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a><span data-ttu-id="412ed-112">GDI を使用してテキスト行を描画するには</span><span class="sxs-lookup"><span data-stu-id="412ed-112">To draw a line of text with GDI</span></span>  
  
1. <span data-ttu-id="412ed-113">メソッドを使用して、必要なテキスト、、、を <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 渡し <xref:System.Drawing.Point> <xref:System.Drawing.Font> <xref:System.Drawing.Color> ます。</span><span class="sxs-lookup"><span data-stu-id="412ed-113">Use the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method, passing the text you want, <xref:System.Drawing.Point>, <xref:System.Drawing.Font>, and <xref:System.Drawing.Color>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#40)]
     [!code-vb[System.Drawing.AlignDrawnText#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#40)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="412ed-114">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="412ed-114">Compiling the Code</span></span>  
 <span data-ttu-id="412ed-115">前の例では、次のものが必要です。</span><span class="sxs-lookup"><span data-stu-id="412ed-115">The previous examples require:</span></span>  
  
- <span data-ttu-id="412ed-116"><xref:System.Windows.Forms.PaintEventArgs>  `e`。これはのパラメーターです <xref:System.Windows.Forms.PaintEventHandler> 。</span><span class="sxs-lookup"><span data-stu-id="412ed-116"><xref:System.Windows.Forms.PaintEventArgs>  `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="412ed-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="412ed-117">See also</span></span>

- [<span data-ttu-id="412ed-118">方法: GDI を使用してテキストを描画する</span><span class="sxs-lookup"><span data-stu-id="412ed-118">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
- [<span data-ttu-id="412ed-119">フォントとテキストの使用</span><span class="sxs-lookup"><span data-stu-id="412ed-119">Using Fonts and Text</span></span>](using-fonts-and-text.md)
- [<span data-ttu-id="412ed-120">方法: フォント ファミリとフォントを作成する</span><span class="sxs-lookup"><span data-stu-id="412ed-120">How to: Construct Font Families and Fonts</span></span>](how-to-construct-font-families-and-fonts.md)
- [<span data-ttu-id="412ed-121">方法: 四角形内にテキストを折り返して描画する</span><span class="sxs-lookup"><span data-stu-id="412ed-121">How to: Draw Wrapped Text in a Rectangle</span></span>](how-to-draw-wrapped-text-in-a-rectangle.md)
