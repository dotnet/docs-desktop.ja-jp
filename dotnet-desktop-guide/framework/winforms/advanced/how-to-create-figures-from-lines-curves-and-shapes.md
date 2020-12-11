---
title: '方法: 直線、曲線、および形状から図形を作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- figures [Windows Forms], creating from shapes
- figures [Windows Forms], creating from lines
ms.assetid: 82fd56c7-b443-4765-9b7c-62ce030656ec
ms.openlocfilehash: c8cf7a7e08bed56fb704bba4e30ff369bc3fcf89
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974829"
---
# <a name="how-to-create-figures-from-lines-curves-and-shapes"></a><span data-ttu-id="36cbc-102">方法: 直線、曲線、および形状から図形を作成する</span><span class="sxs-lookup"><span data-stu-id="36cbc-102">How to: Create Figures from Lines, Curves, and Shapes</span></span>
<span data-ttu-id="36cbc-103">図形を作成するには、を構築してから、やなどのメソッドを呼び出して、 <xref:System.Drawing.Drawing2D.GraphicsPath> <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> パスにプリミティブを追加します。</span><span class="sxs-lookup"><span data-stu-id="36cbc-103">To create a figure, construct a <xref:System.Drawing.Drawing2D.GraphicsPath>, and then call methods, such as <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> and <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A>, to add primitives to the path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36cbc-104">例</span><span class="sxs-lookup"><span data-stu-id="36cbc-104">Example</span></span>  
 <span data-ttu-id="36cbc-105">次のコード例では、図を含むパスを作成します。</span><span class="sxs-lookup"><span data-stu-id="36cbc-105">The following code examples create paths that have figures:</span></span>  
  
- <span data-ttu-id="36cbc-106">最初の例では、1つの図形を含むパスを作成します。</span><span class="sxs-lookup"><span data-stu-id="36cbc-106">The first example creates a path that has a single figure.</span></span> <span data-ttu-id="36cbc-107">この図は、1つの円弧で構成されています。円弧は、既定の座標系で反時計回りに、-180 度のスイープ角度を持ちます。</span><span class="sxs-lookup"><span data-stu-id="36cbc-107">The figure consists of a single arc. The arc has a sweep angle of –180 degrees, which is counterclockwise in the default coordinate system.</span></span>  
  
- <span data-ttu-id="36cbc-108">2番目の例では、2つの図形を持つパスを作成します。</span><span class="sxs-lookup"><span data-stu-id="36cbc-108">The second example creates a path that has two figures.</span></span> <span data-ttu-id="36cbc-109">最初の図は、円弧の後に線を付けたものです。</span><span class="sxs-lookup"><span data-stu-id="36cbc-109">The first figure is an arc followed by a line.</span></span> <span data-ttu-id="36cbc-110">2番目の図は、曲線の後に直線が続く線です。</span><span class="sxs-lookup"><span data-stu-id="36cbc-110">The second figure is a line followed by a curve followed by a line.</span></span> <span data-ttu-id="36cbc-111">最初の図形は開いたままになり、2番目の図形は閉じています。</span><span class="sxs-lookup"><span data-stu-id="36cbc-111">The first figure is left open, and the second figure is closed.</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#21)]  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#22)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="36cbc-112">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="36cbc-112">Compiling the Code</span></span>  
 <span data-ttu-id="36cbc-113">前の例は、Windows フォームで使用するように設計されており <xref:System.Windows.Forms.PaintEventArgs> `e` 、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。</span><span class="sxs-lookup"><span data-stu-id="36cbc-113">The previous examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36cbc-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="36cbc-114">See also</span></span>

- <xref:System.Drawing.Drawing2D.GraphicsPath>
- [<span data-ttu-id="36cbc-115">パスの作成および描画</span><span class="sxs-lookup"><span data-stu-id="36cbc-115">Constructing and Drawing Paths</span></span>](constructing-and-drawing-paths.md)
- [<span data-ttu-id="36cbc-116">ペンを使用した直線と図形の描画</span><span class="sxs-lookup"><span data-stu-id="36cbc-116">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
