---
title: '方法: 開いている図形を塗りつぶす'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- open figures [Windows Forms], filling
- figures [Windows Forms], filling
ms.assetid: 5a36b0e4-f1f4-46c0-a85a-22ae98491950
ms.openlocfilehash: 6ecea7d3edb0c3e25fb4e69ff12b88019e530021
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981339"
---
# <a name="how-to-fill-open-figures"></a><span data-ttu-id="6309f-102">方法: 開いている図形を塗りつぶす</span><span class="sxs-lookup"><span data-stu-id="6309f-102">How to: Fill Open Figures</span></span>
<span data-ttu-id="6309f-103">メソッドにオブジェクトを渡すことによって、パスを埋めることができ <xref:System.Drawing.Drawing2D.GraphicsPath> <xref:System.Drawing.Graphics.FillPath%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="6309f-103">You can fill a path by passing a <xref:System.Drawing.Drawing2D.GraphicsPath> object to the <xref:System.Drawing.Graphics.FillPath%2A> method.</span></span> <span data-ttu-id="6309f-104">メソッドは、 <xref:System.Drawing.Graphics.FillPath%2A> パスに現在設定されている塗りつぶしモード (代替またはワインディング) に従ってパスを塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="6309f-104">The <xref:System.Drawing.Graphics.FillPath%2A> method fills the path according to the fill mode (alternate or winding) currently set for the path.</span></span> <span data-ttu-id="6309f-105">パスに開いている図形がある場合は、その図形が閉じられているかのようにパスが塗りつぶされます。</span><span class="sxs-lookup"><span data-stu-id="6309f-105">If the path has any open figures, the path is filled as if those figures were closed.</span></span> <span data-ttu-id="6309f-106">GDI + は、終了点から開始点までの直線を描画することで、図形を閉じます。</span><span class="sxs-lookup"><span data-stu-id="6309f-106">GDI+ closes a figure by drawing a straight line from its ending point to its starting point.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6309f-107">例</span><span class="sxs-lookup"><span data-stu-id="6309f-107">Example</span></span>  
 <span data-ttu-id="6309f-108">次の例では、1つの開いている図形 (弧) と1つの閉じた図形 (楕円) を含むパスを作成します。</span><span class="sxs-lookup"><span data-stu-id="6309f-108">The following example creates a path that has one open figure (an arc) and one closed figure (an ellipse).</span></span> <span data-ttu-id="6309f-109">メソッドは、 <xref:System.Drawing.Graphics.FillPath%2A> 既定の塗りつぶしモード () に従ってパスを設定し <xref:System.Drawing.Drawing2D.FillMode.Alternate> ます。</span><span class="sxs-lookup"><span data-stu-id="6309f-109">The <xref:System.Drawing.Graphics.FillPath%2A> method fills the path according to the default fill mode, which is <xref:System.Drawing.Drawing2D.FillMode.Alternate>.</span></span>  
  
 <span data-ttu-id="6309f-110">次の図は、コード例の出力を示しています。</span><span class="sxs-lookup"><span data-stu-id="6309f-110">The following illustration shows the output of the example code.</span></span> <span data-ttu-id="6309f-111">開いている <xref:System.Drawing.Drawing2D.FillMode.Alternate> 図形が終了点から開始点までの直線で閉じられているかのように、パスが (に従って) 塗りつぶされていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6309f-111">Note that the path is filled (according to <xref:System.Drawing.Drawing2D.FillMode.Alternate>) as if the open figure were closed by a straight line from its ending point to its starting point.</span></span>  
  
 ![FillPath メソッドの出力を示す図](./media/how-to-fill-open-figures/fill-path-alternate-mode.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6309f-113">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="6309f-113">Compiling the Code</span></span>  
 <span data-ttu-id="6309f-114">前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。</span><span class="sxs-lookup"><span data-stu-id="6309f-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6309f-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="6309f-115">See also</span></span>

- <xref:System.Drawing.Drawing2D.GraphicsPath>
- [<span data-ttu-id="6309f-116">GDI+ でのグラフィックス パス</span><span class="sxs-lookup"><span data-stu-id="6309f-116">Graphics Paths in GDI+</span></span>](graphics-paths-in-gdi.md)
