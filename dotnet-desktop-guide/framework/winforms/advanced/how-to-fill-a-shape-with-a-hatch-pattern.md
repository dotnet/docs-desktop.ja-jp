---
title: '方法: ハッチ パターンで図形を塗りつぶす'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- patterns [Windows Forms], adding to shapes
- shapes [Windows Forms], filling with patterns
- brushes [Windows Forms], using hatch brushes
ms.assetid: 9c8300ff-187b-404f-af1f-ebd499f5b16f
ms.openlocfilehash: b80708f0ce722b1809fe49190639231e7e4c8329
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981848"
---
# <a name="how-to-fill-a-shape-with-a-hatch-pattern"></a><span data-ttu-id="15365-102">方法: ハッチ パターンで図形を塗りつぶす</span><span class="sxs-lookup"><span data-stu-id="15365-102">How to: Fill a Shape with a Hatch Pattern</span></span>
<span data-ttu-id="15365-103">ハッチパターンは2色から作成されます。1つは背景用で、もう1つは背景のパターンを形成する線です。</span><span class="sxs-lookup"><span data-stu-id="15365-103">A hatch pattern is made from two colors: one for the background and one for the lines that form the pattern over the background.</span></span> <span data-ttu-id="15365-104">閉じた図形をハッチパターンで塗りつぶすには、オブジェクトを使用し <xref:System.Drawing.Drawing2D.HatchBrush> ます。</span><span class="sxs-lookup"><span data-stu-id="15365-104">To fill a closed shape with a hatch pattern, use a <xref:System.Drawing.Drawing2D.HatchBrush> object.</span></span> <span data-ttu-id="15365-105">次の例は、楕円にハッチパターンで塗りつぶす方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="15365-105">The following example demonstrates how to fill an ellipse with a hatch pattern:</span></span>  
  
## <a name="example"></a><span data-ttu-id="15365-106">例</span><span class="sxs-lookup"><span data-stu-id="15365-106">Example</span></span>  
 <span data-ttu-id="15365-107">コンストラクターは、 <xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A> ハッチスタイル、ハッチ線の色、背景色の3つの引数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="15365-107">The <xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A> constructor takes three arguments: the hatch style, the color of the hatch line, and the color of the background.</span></span> <span data-ttu-id="15365-108">ハッチスタイル引数には、列挙体の任意の値を指定でき <xref:System.Drawing.Drawing2D.HatchStyle> ます。</span><span class="sxs-lookup"><span data-stu-id="15365-108">The hatch style argument can be any value from the <xref:System.Drawing.Drawing2D.HatchStyle> enumeration.</span></span> <span data-ttu-id="15365-109">列挙体には50を超える要素があり <xref:System.Drawing.Drawing2D.HatchStyle> ます。これらの要素のいくつかを次の一覧に示します。</span><span class="sxs-lookup"><span data-stu-id="15365-109">There are more than fifty elements in the <xref:System.Drawing.Drawing2D.HatchStyle> enumeration; a few of those elements are shown in the following list:</span></span>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.Vertical>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.BackwardDiagonal>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.Cross>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.DiagonalCross>  
  
 <span data-ttu-id="15365-110">次の図は、塗りつぶされた楕円を示しています。</span><span class="sxs-lookup"><span data-stu-id="15365-110">The following illustration shows the filled ellipse.</span></span>  
  
  <span data-ttu-id="15365-111">![ハッチパターンで塗りつぶされた楕円のスクリーンショットは次のようになります。](./media/how-to-fill-a-shape-with-a-hatch-pattern/ellipse-filled-hatch.png "hatch1")</span><span class="sxs-lookup"><span data-stu-id="15365-111">![Screenshot of what an ellipse filled with a hatch pattern looks like.](./media/how-to-fill-a-shape-with-a-hatch-pattern/ellipse-filled-hatch.png "hatch1")</span></span>
  
 [!code-csharp[System.Drawing.UsingABrush#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.UsingABrush#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="15365-112">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="15365-112">Compiling the Code</span></span>  
 <span data-ttu-id="15365-113">前の例は、Windows フォームで使用するために設計されていて、<xref:System.Windows.Forms.PaintEventArgs> イベント ハンドラーのパラメーターである `e`<xref:System.Windows.Forms.Control.Paint> を必要とします。</span><span class="sxs-lookup"><span data-stu-id="15365-113">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15365-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="15365-114">See also</span></span>

- [<span data-ttu-id="15365-115">ブラシを使用した図形の塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="15365-115">Using a Brush to Fill Shapes</span></span>](using-a-brush-to-fill-shapes.md)
