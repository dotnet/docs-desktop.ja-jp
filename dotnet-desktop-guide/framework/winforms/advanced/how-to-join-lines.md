---
title: '方法: 直線を接合する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- miter line join style
- bevel line join style
- line join
- drawing [Windows Forms], joining lines
- GraphicsPath object
- round line join style
- lines [Windows Forms], joining
- graphics [Windows Forms], joining lines
ms.assetid: 9fc480c2-3c75-4fd1-8ab5-296a99e820e2
ms.openlocfilehash: 362ce0c701d6e5f640fecd143a60cf471045629c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981831"
---
# <a name="how-to-join-lines"></a><span data-ttu-id="6e5cd-102">方法: 直線を接合する</span><span class="sxs-lookup"><span data-stu-id="6e5cd-102">How to: Join Lines</span></span>
<span data-ttu-id="6e5cd-103">線結合は、2つの行で構成される共通領域で、両端が一致しているか、重複しています。</span><span class="sxs-lookup"><span data-stu-id="6e5cd-103">A line join is the common area that is formed by two lines whose ends meet or overlap.</span></span> <span data-ttu-id="6e5cd-104">GDI + には、3つの線の結合スタイル (マイタ、ベベル、round) が用意されています。</span><span class="sxs-lookup"><span data-stu-id="6e5cd-104">GDI+ provides three line join styles: miter, bevel, and round.</span></span> <span data-ttu-id="6e5cd-105">線の結合スタイルは、クラスのプロパティ <xref:System.Drawing.Pen> です。</span><span class="sxs-lookup"><span data-stu-id="6e5cd-105">Line join style is a property of the <xref:System.Drawing.Pen> class.</span></span> <span data-ttu-id="6e5cd-106">オブジェクトの線の結合スタイルを指定すると <xref:System.Drawing.Pen> 、その結合スタイルは、 <xref:System.Drawing.Drawing2D.GraphicsPath> そのペンを使用して描画されたオブジェクト内のすべての接続線に適用されます。</span><span class="sxs-lookup"><span data-stu-id="6e5cd-106">When you specify a line join style for a <xref:System.Drawing.Pen> object, that join style will be applied to all the connected lines in any <xref:System.Drawing.Drawing2D.GraphicsPath> object drawn using that pen.</span></span>  
  
 <span data-ttu-id="6e5cd-107">次の図は、傾斜線結合の例の結果を示しています。</span><span class="sxs-lookup"><span data-stu-id="6e5cd-107">The following illustration shows the results of the beveled line join example.</span></span>  
  
 ![結合された直線を示す図。](./media/how-to-join-lines/joined-beveled-lines.gif)  
  
## <a name="example"></a><span data-ttu-id="6e5cd-109">例</span><span class="sxs-lookup"><span data-stu-id="6e5cd-109">Example</span></span>  
 <span data-ttu-id="6e5cd-110">線の結合スタイルは、クラスのプロパティを使用して指定でき <xref:System.Drawing.Pen.LineJoin%2A> <xref:System.Drawing.Pen> ます。</span><span class="sxs-lookup"><span data-stu-id="6e5cd-110">You can specify the line join style by using the <xref:System.Drawing.Pen.LineJoin%2A> property of the <xref:System.Drawing.Pen> class.</span></span> <span data-ttu-id="6e5cd-111">この例は、水平線と垂直線の間のベベル線結合を示しています。</span><span class="sxs-lookup"><span data-stu-id="6e5cd-111">The example demonstrates a beveled line join between a horizontal line and a vertical line.</span></span> <span data-ttu-id="6e5cd-112">次のコードで <xref:System.Drawing.Drawing2D.LineJoin.Bevel> は、プロパティに割り当てられた値 <xref:System.Drawing.Pen.LineJoin%2A> は列挙体のメンバーです <xref:System.Drawing.Drawing2D.LineJoin> 。</span><span class="sxs-lookup"><span data-stu-id="6e5cd-112">In the following code, the value <xref:System.Drawing.Drawing2D.LineJoin.Bevel> assigned to the <xref:System.Drawing.Pen.LineJoin%2A> property is a member of the <xref:System.Drawing.Drawing2D.LineJoin> enumeration.</span></span> <span data-ttu-id="6e5cd-113">列挙体の他のメンバー <xref:System.Drawing.Drawing2D.LineJoin> は、 <xref:System.Drawing.Drawing2D.LineJoin.Miter> と <xref:System.Drawing.Drawing2D.LineJoin.Round> です。</span><span class="sxs-lookup"><span data-stu-id="6e5cd-113">The other members of the <xref:System.Drawing.Drawing2D.LineJoin> enumeration are <xref:System.Drawing.Drawing2D.LineJoin.Miter> and <xref:System.Drawing.Drawing2D.LineJoin.Round>.</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingAPen#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6e5cd-114">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="6e5cd-114">Compiling the Code</span></span>  
 <span data-ttu-id="6e5cd-115">前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。</span><span class="sxs-lookup"><span data-stu-id="6e5cd-115">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e5cd-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e5cd-116">See also</span></span>

- [<span data-ttu-id="6e5cd-117">ペンを使用した直線と図形の描画</span><span class="sxs-lookup"><span data-stu-id="6e5cd-117">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
