---
title: '方法: ペンの幅と配置を設定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pens [Windows Forms], setting width
- pens [Windows Forms], setting alignment
ms.assetid: a202af36-4d31-4401-a126-b232f51db581
ms.openlocfilehash: 1f1ea6e8ef0b94aa46a4bf8177d59e59297d6e3f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981775"
---
# <a name="how-to-set-pen-width-and-alignment"></a><span data-ttu-id="537dd-102">方法: ペンの幅と配置を設定する</span><span class="sxs-lookup"><span data-stu-id="537dd-102">How to: Set Pen Width and Alignment</span></span>
<span data-ttu-id="537dd-103">を作成するときに、 <xref:System.Drawing.Pen> コンストラクターの引数の1つとしてペンの幅を指定できます。</span><span class="sxs-lookup"><span data-stu-id="537dd-103">When you create a <xref:System.Drawing.Pen>, you can supply the pen width as one of the arguments to the constructor.</span></span> <span data-ttu-id="537dd-104">また、クラスのプロパティを使用して、ペンの幅を変更することもでき <xref:System.Drawing.Pen.Width%2A> <xref:System.Drawing.Pen> ます。</span><span class="sxs-lookup"><span data-stu-id="537dd-104">You can also change the pen width with the <xref:System.Drawing.Pen.Width%2A> property of the <xref:System.Drawing.Pen> class.</span></span>  
  
 <span data-ttu-id="537dd-105">理論上の線の幅は0です。</span><span class="sxs-lookup"><span data-stu-id="537dd-105">A theoretical line has a width of 0.</span></span> <span data-ttu-id="537dd-106">幅が1ピクセルの線を描画すると、そのピクセルは理論上の線の中央に配置されます。</span><span class="sxs-lookup"><span data-stu-id="537dd-106">When you draw a line that is 1 pixel wide, the pixels are centered on the theoretical line.</span></span> <span data-ttu-id="537dd-107">幅が1ピクセルを超える線を描画する場合、ピクセルは理論上の線の中央に配置されるか、理論的な線の片側に表示されます。</span><span class="sxs-lookup"><span data-stu-id="537dd-107">If you draw a line that is more than one pixel wide, the pixels are either centered on the theoretical line or appear to one side of the theoretical line.</span></span> <span data-ttu-id="537dd-108">のペンの配置プロパティを設定して、 <xref:System.Drawing.Pen> そのペンで描画されたピクセルを理論上の線に対して相対的に配置する方法を決定できます。</span><span class="sxs-lookup"><span data-stu-id="537dd-108">You can set the pen alignment property of a <xref:System.Drawing.Pen> to determine how the pixels drawn with that pen will be positioned relative to theoretical lines.</span></span>  
  
 <span data-ttu-id="537dd-109">次の <xref:System.Drawing.Drawing2D.PenAlignment.Center> <xref:System.Drawing.Drawing2D.PenAlignment.Outset> コード例に示されている、、の値は、 <xref:System.Drawing.Drawing2D.PenAlignment.Inset> 列挙体のメンバーです <xref:System.Drawing.Drawing2D.PenAlignment> 。</span><span class="sxs-lookup"><span data-stu-id="537dd-109">The values <xref:System.Drawing.Drawing2D.PenAlignment.Center>, <xref:System.Drawing.Drawing2D.PenAlignment.Outset>, and <xref:System.Drawing.Drawing2D.PenAlignment.Inset> that appear in the following code examples are members of the <xref:System.Drawing.Drawing2D.PenAlignment> enumeration.</span></span>  
  
 <span data-ttu-id="537dd-110">次のコード例では、1行を2回描画します。1回は幅1の黒のペン、もう1回は幅10の緑色のペンを使用します。</span><span class="sxs-lookup"><span data-stu-id="537dd-110">The following code example draws a line twice: once with a black pen of width 1 and once with a green pen of width 10.</span></span>  
  
### <a name="to-vary-the-width-of-a-pen"></a><span data-ttu-id="537dd-111">ペンの幅を変更するには</span><span class="sxs-lookup"><span data-stu-id="537dd-111">To vary the width of a pen</span></span>  
  
- <span data-ttu-id="537dd-112">プロパティの値 <xref:System.Drawing.Pen.Alignment%2A> を (既定値) に設定して、 <xref:System.Drawing.Drawing2D.PenAlignment.Center> 緑色のペンで描画されたピクセルを理論上の線の中央に配置するように指定します。</span><span class="sxs-lookup"><span data-stu-id="537dd-112">Set the value of the <xref:System.Drawing.Pen.Alignment%2A> property to <xref:System.Drawing.Drawing2D.PenAlignment.Center> (the default) to specify that pixels drawn with the green pen will be centered on the theoretical line.</span></span> <span data-ttu-id="537dd-113">次の図は、結果として得られる行を示しています。</span><span class="sxs-lookup"><span data-stu-id="537dd-113">The following illustration shows the resulting line.</span></span>  
  
     ![緑の強調表示の黒い細い線。](./media/how-to-set-pen-width-and-alignment/green-pixels-centered-line.gif)  
  
     <span data-ttu-id="537dd-115">次のコード例では、四角形を2回描画します。1回は幅1の黒のペン、もう1回は幅10の緑色のペンを使用します。</span><span class="sxs-lookup"><span data-stu-id="537dd-115">The following code example draws a rectangle twice: once with a black pen of width 1 and once with a green pen of width 10.</span></span>  
  
     [!code-csharp[System.Drawing.UsingAPen#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#41)]
     [!code-vb[System.Drawing.UsingAPen#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#41)]  
  
### <a name="to-change-the-alignment-of-a-pen"></a><span data-ttu-id="537dd-116">ペンの配置を変更するには</span><span class="sxs-lookup"><span data-stu-id="537dd-116">To change the alignment of a pen</span></span>  
  
- <span data-ttu-id="537dd-117">プロパティの値をに設定して、 <xref:System.Drawing.Pen.Alignment%2A> <xref:System.Drawing.Drawing2D.PenAlignment.Center> 緑色のペンで描画されたピクセルを四角形の境界の中央に配置するように指定します。</span><span class="sxs-lookup"><span data-stu-id="537dd-117">Set the value of the <xref:System.Drawing.Pen.Alignment%2A> property to <xref:System.Drawing.Drawing2D.PenAlignment.Center> to specify that the pixels drawn with the green pen will be centered on the boundary of the rectangle.</span></span>  
  
     <span data-ttu-id="537dd-118">次の図は、結果として得られる四角形を示しています。</span><span class="sxs-lookup"><span data-stu-id="537dd-118">The following illustration shows the resulting rectangle:</span></span>
  
     ![黒い細い線が緑色の強調表示された四角形。](./media/how-to-set-pen-width-and-alignment/green-pixels-centered-rectangle.gif)  
  
     [!code-csharp[System.Drawing.UsingAPen#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#42)]
     [!code-vb[System.Drawing.UsingAPen#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#42)]  
  
### <a name="to-create-an-inset-pen"></a><span data-ttu-id="537dd-120">インセットペンを作成するには</span><span class="sxs-lookup"><span data-stu-id="537dd-120">To create an inset pen</span></span>  
  
- <span data-ttu-id="537dd-121">前のコード例の3番目のステートメントを次のように変更して、緑色のペンの配置を変更します。</span><span class="sxs-lookup"><span data-stu-id="537dd-121">Change the green pen's alignment by modifying the third statement in the preceding code example as follows:</span></span>  
  
     [!code-csharp[System.Drawing.UsingAPen#43](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#43)]
     [!code-vb[System.Drawing.UsingAPen#43](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#43)]  
  
     <span data-ttu-id="537dd-122">これで、次の図に示すように、緑色のワイド線のピクセルが四角形の内側に表示されます。</span><span class="sxs-lookup"><span data-stu-id="537dd-122">Now the pixels in the wide green line appear on the inside of the rectangle as shown in the following illustration:</span></span>
  
     ![黒色の線で囲まれた四角形。内部には、幅の広い緑色の線が付きます。](./media/how-to-set-pen-width-and-alignment/green-pixels-inside-rectangle.gif)  
  
## <a name="see-also"></a><span data-ttu-id="537dd-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="537dd-124">See also</span></span>

- [<span data-ttu-id="537dd-125">ペンを使用した直線と図形の描画</span><span class="sxs-lookup"><span data-stu-id="537dd-125">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="537dd-126">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="537dd-126">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
