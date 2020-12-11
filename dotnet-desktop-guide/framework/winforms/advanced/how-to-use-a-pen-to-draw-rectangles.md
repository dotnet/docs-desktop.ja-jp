---
title: '方法: ペンを使用して四角形を描画する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- rectangles [Windows Forms], drawing
- pens [Windows Forms], drawing rectangles
ms.assetid: 54a7fa14-3ad8-4d64-b424-2a12005b250c
ms.openlocfilehash: cd5d965f8b92d15cdeb3049330d9b3cc0de893b2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981228"
---
# <a name="how-to-use-a-pen-to-draw-rectangles"></a><span data-ttu-id="b3a50-102">方法: ペンを使用して四角形を描画する</span><span class="sxs-lookup"><span data-stu-id="b3a50-102">How to: Use a Pen to Draw Rectangles</span></span>
<span data-ttu-id="b3a50-103">四角形を描画するには、 <xref:System.Drawing.Graphics> オブジェクトとオブジェクトが必要 <xref:System.Drawing.Pen> です。</span><span class="sxs-lookup"><span data-stu-id="b3a50-103">To draw rectangles, you need a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="b3a50-104"><xref:System.Drawing.Graphics>オブジェクトはメソッドを提供し、 <xref:System.Drawing.Graphics.DrawRectangle%2A> <xref:System.Drawing.Pen> オブジェクトは色や幅などの線の機能を格納します。</span><span class="sxs-lookup"><span data-stu-id="b3a50-104">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawRectangle%2A> method, and the <xref:System.Drawing.Pen> object stores features of the line, such as color and width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3a50-105">例</span><span class="sxs-lookup"><span data-stu-id="b3a50-105">Example</span></span>  
 <span data-ttu-id="b3a50-106">次の例では、左上隅に (10, 10) の四角形を描画します。</span><span class="sxs-lookup"><span data-stu-id="b3a50-106">The following example draws a rectangle with its upper-left corner at (10, 10).</span></span> <span data-ttu-id="b3a50-107">四角形の幅は100、高さは50です。</span><span class="sxs-lookup"><span data-stu-id="b3a50-107">The rectangle has a width of 100 and a height of 50.</span></span> <span data-ttu-id="b3a50-108">コンストラクターに渡される2番目の引数は、 <xref:System.Drawing.Pen.%23ctor%2A> ペンの幅が5ピクセルであることを示します。</span><span class="sxs-lookup"><span data-stu-id="b3a50-108">The second argument passed to the <xref:System.Drawing.Pen.%23ctor%2A> constructor indicates that the pen width is 5 pixels.</span></span>  
  
 <span data-ttu-id="b3a50-109">四角形が描画されると、ペンは四角形の境界の中央に配置されます。</span><span class="sxs-lookup"><span data-stu-id="b3a50-109">When the rectangle is drawn, the pen is centered on the rectangle's boundary.</span></span> <span data-ttu-id="b3a50-110">ペンの幅は5であるため、四角形の辺は5ピクセル幅で描画されます。これにより、境界自体に1ピクセルが描画され、2ピクセルが内側に描画され、2ピクセルが外側に描画されます。</span><span class="sxs-lookup"><span data-stu-id="b3a50-110">Because the pen width is 5, the sides of the rectangle are drawn 5 pixels wide, such that 1 pixel is drawn on the boundary itself, 2 pixels are drawn on the inside, and 2 pixels are drawn on the outside.</span></span> <span data-ttu-id="b3a50-111">ペンの配置の詳細については、「 [方法: ペンの幅と配置を設定する](how-to-set-pen-width-and-alignment.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3a50-111">For more details on pen alignment, see [How to: Set Pen Width and Alignment](how-to-set-pen-width-and-alignment.md).</span></span>  
  
 <span data-ttu-id="b3a50-112">次の図は、結果として得られる四角形を示しています。</span><span class="sxs-lookup"><span data-stu-id="b3a50-112">The following illustration shows the resulting rectangle.</span></span> <span data-ttu-id="b3a50-113">点線は、ペンの幅が1ピクセルの場合に四角形が描画された場所を示しています。</span><span class="sxs-lookup"><span data-stu-id="b3a50-113">The dotted lines show where the rectangle would have been drawn if the pen width had been one pixel.</span></span> <span data-ttu-id="b3a50-114">四角形の左上隅の拡大表示は、太い黒い線がそれらの点線の中央に配置されていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="b3a50-114">The enlarged view of the upper-left corner of the rectangle shows that the thick black lines are centered on those dotted lines.</span></span>  
  
 ![黒と点線で描画された四角形を示すスクリーンショット。](./media/how-to-use-a-pen-to-draw-rectangles/drawn-rectangle-black-lines-dotted-lines.gif)  
  
 [!code-csharp[System.Drawing.UsingAPen#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingAPen#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b3a50-116">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="b3a50-116">Compiling the Code</span></span>  
 <span data-ttu-id="b3a50-117">前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。</span><span class="sxs-lookup"><span data-stu-id="b3a50-117">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3a50-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3a50-118">See also</span></span>

- [<span data-ttu-id="b3a50-119">ペンを使用した直線と図形の描画</span><span class="sxs-lookup"><span data-stu-id="b3a50-119">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
