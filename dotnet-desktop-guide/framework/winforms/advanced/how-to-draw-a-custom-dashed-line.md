---
title: '方法: カスタム破線を描画する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines [Windows Forms], custom
- lines [Windows Forms], drawing
- lines [Windows Forms], dashed
ms.assetid: cd0ed96a-cce4-47b9-b58a-3bae2e3d1bee
ms.openlocfilehash: d2184a8d7d7f24b8f631818608ab4bcdb89857c7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974404"
---
# <a name="how-to-draw-a-custom-dashed-line"></a><span data-ttu-id="7a490-102">方法: カスタム破線を描画する</span><span class="sxs-lookup"><span data-stu-id="7a490-102">How to: Draw a Custom Dashed Line</span></span>
<span data-ttu-id="7a490-103">GDI + には、列挙体に示されている複数のダッシュスタイルが用意されてい <xref:System.Drawing.Drawing2D.DashStyle> ます。</span><span class="sxs-lookup"><span data-stu-id="7a490-103">GDI+ provides several dash styles that are listed in the <xref:System.Drawing.Drawing2D.DashStyle> enumeration.</span></span> <span data-ttu-id="7a490-104">これらの標準の破線スタイルがニーズに合わない場合は、カスタムダッシュパターンを作成できます。</span><span class="sxs-lookup"><span data-stu-id="7a490-104">If those standard dash styles do not suit your needs, you can create a custom dash pattern.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a490-105">例</span><span class="sxs-lookup"><span data-stu-id="7a490-105">Example</span></span>  
 <span data-ttu-id="7a490-106">カスタム破線を描画するには、配列にダッシュとスペースの長さを設定し、オブジェクトのプロパティの値として配列を割り当て <xref:System.Drawing.Pen.DashPattern%2A> <xref:System.Drawing.Pen> ます。</span><span class="sxs-lookup"><span data-stu-id="7a490-106">To draw a custom dashed line, put the lengths of the dashes and spaces in an array and assign the array as the value of the <xref:System.Drawing.Pen.DashPattern%2A> property of a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="7a490-107">次の例では、配列に基づいてカスタム破線を描画し `{5, 2, 15, 4}` ます。</span><span class="sxs-lookup"><span data-stu-id="7a490-107">The following example draws a custom dashed line based on the array `{5, 2, 15, 4}`.</span></span> <span data-ttu-id="7a490-108">配列の要素をペンの幅5で乗算すると、が表示さ `{25, 10, 75, 20}` れます。</span><span class="sxs-lookup"><span data-stu-id="7a490-108">If you multiply the elements of the array by the pen width of 5, you get `{25, 10, 75, 20}`.</span></span> <span data-ttu-id="7a490-109">表示されるダッシュの長さは 25 ~ 75 の間で、スペースは 10 ~ 20 の範囲で交互に表示されます。</span><span class="sxs-lookup"><span data-stu-id="7a490-109">The displayed dashes alternate in length between 25 and 75, and the spaces alternate in length between 10 and 20.</span></span>  
  
 <span data-ttu-id="7a490-110">結果として得られる破線を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="7a490-110">The following illustration shows the resulting dashed line.</span></span> <span data-ttu-id="7a490-111">最後のダッシュは25単位にする必要があることに注意してください。これにより、行を (405, 5) で終わらせることができます。</span><span class="sxs-lookup"><span data-stu-id="7a490-111">Note that the final dash has to be shorter than 25 units so that the line can end at (405, 5).</span></span>  
  
 <span data-ttu-id="7a490-112">![破線を示す図。](./media/how-to-draw-a-custom-dashed-line/dashed-line-illustration.gif "pens6")</span><span class="sxs-lookup"><span data-stu-id="7a490-112">![Illustration that shows a dashed line.](./media/how-to-draw-a-custom-dashed-line/dashed-line-illustration.gif "pens6")</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.UsingAPen#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7a490-113">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="7a490-113">Compiling the Code</span></span>  
 <span data-ttu-id="7a490-114">Windows フォームを作成し、フォームのイベントを処理し <xref:System.Windows.Forms.Control.Paint> ます。</span><span class="sxs-lookup"><span data-stu-id="7a490-114">Create a Windows Form and handle the form's <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="7a490-115">前のコードをイベントハンドラーに貼り付け <xref:System.Windows.Forms.Control.Paint> ます。</span><span class="sxs-lookup"><span data-stu-id="7a490-115">Paste the preceding code into the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a490-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="7a490-116">See also</span></span>

- [<span data-ttu-id="7a490-117">ペンを使用した直線と図形の描画</span><span class="sxs-lookup"><span data-stu-id="7a490-117">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
