---
title: '方法: ペンを使用して線を描画する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
ms.assetid: 0828c331-a438-4bdd-a4d6-3ef1e59e8795
ms.openlocfilehash: 263c0fbda377e64753cd2d607f633117b4b44253
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981735"
---
# <a name="how-to-use-a-pen-to-draw-lines"></a><span data-ttu-id="6fe24-102">方法: ペンを使用して線を描画する</span><span class="sxs-lookup"><span data-stu-id="6fe24-102">How to: Use a Pen to Draw Lines</span></span>
<span data-ttu-id="6fe24-103">線を描画するには、 <xref:System.Drawing.Graphics> オブジェクトとオブジェクトが必要 <xref:System.Drawing.Pen> です。</span><span class="sxs-lookup"><span data-stu-id="6fe24-103">To draw lines, you need a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="6fe24-104"><xref:System.Drawing.Graphics>オブジェクトはメソッドを提供し、 <xref:System.Drawing.Graphics.DrawLine%2A> <xref:System.Drawing.Pen> オブジェクトは色や幅などの線の機能を格納します。</span><span class="sxs-lookup"><span data-stu-id="6fe24-104">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawLine%2A> method, and the <xref:System.Drawing.Pen> object stores features of the line, such as color and width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6fe24-105">例</span><span class="sxs-lookup"><span data-stu-id="6fe24-105">Example</span></span>  
 <span data-ttu-id="6fe24-106">次の例では、(20, 10) から (300, 100) までの線を描画します。</span><span class="sxs-lookup"><span data-stu-id="6fe24-106">The following example draws a line from (20, 10) to (300, 100).</span></span> <span data-ttu-id="6fe24-107">最初のステートメントでは、クラスコンストラクターを使用して、 <xref:System.Drawing.Pen.%23ctor%2A> 黒色のペンを作成します。</span><span class="sxs-lookup"><span data-stu-id="6fe24-107">The first statement uses the <xref:System.Drawing.Pen.%23ctor%2A> class constructor to create a black pen.</span></span> <span data-ttu-id="6fe24-108">コンストラクターに渡される1つの引数 <xref:System.Drawing.Pen.%23ctor%2A> は、 <xref:System.Drawing.Color> メソッドを使用して作成されたオブジェクトです <xref:System.Drawing.Color.FromArgb%2A> 。</span><span class="sxs-lookup"><span data-stu-id="6fe24-108">The one argument passed to the <xref:System.Drawing.Pen.%23ctor%2A> constructor is a <xref:System.Drawing.Color> object created with the <xref:System.Drawing.Color.FromArgb%2A> method.</span></span> <span data-ttu-id="6fe24-109">オブジェクトの作成に使用される値 <xref:System.Drawing.Color> (255、0、0、0) は、色のアルファ、赤、緑、および青のコンポーネントに対応します。</span><span class="sxs-lookup"><span data-stu-id="6fe24-109">The values used to create the <xref:System.Drawing.Color> object — (255, 0, 0, 0) — correspond to the alpha, red, green, and blue components of the color.</span></span> <span data-ttu-id="6fe24-110">これらの値は、不透明な黒のペンを定義します。</span><span class="sxs-lookup"><span data-stu-id="6fe24-110">These values define an opaque black pen.</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6fe24-111">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="6fe24-111">Compiling the Code</span></span>  
 <span data-ttu-id="6fe24-112">前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。</span><span class="sxs-lookup"><span data-stu-id="6fe24-112">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fe24-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="6fe24-113">See also</span></span>

- <xref:System.Drawing.Pen>
- [<span data-ttu-id="6fe24-114">ペンを使用した直線と図形の描画</span><span class="sxs-lookup"><span data-stu-id="6fe24-114">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="6fe24-115">GDI+ でのペン、直線、および四角形</span><span class="sxs-lookup"><span data-stu-id="6fe24-115">Pens, Lines, and Rectangles in GDI+</span></span>](pens-lines-and-rectangles-in-gdi.md)
