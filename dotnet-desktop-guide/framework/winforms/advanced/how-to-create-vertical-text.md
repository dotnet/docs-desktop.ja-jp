---
title: '方法: 垂直方向のテキストを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing vertical
- Windows Forms, drawing vertical text
- strings [Windows Forms], drawing vertical
- vertical text [Windows Forms], drawing
ms.assetid: 50c69046-4188-47d9-b949-cc2610ffd337
ms.openlocfilehash: 86401342625f593945b801f7619ef9ca9681317c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974410"
---
# <a name="how-to-create-vertical-text"></a><span data-ttu-id="5235c-102">方法: 垂直方向のテキストを作成する</span><span class="sxs-lookup"><span data-stu-id="5235c-102">How to: Create Vertical Text</span></span>
<span data-ttu-id="5235c-103">オブジェクトを使用すると、 <xref:System.Drawing.StringFormat> テキストを水平方向ではなく垂直方向に描画するように指定できます。</span><span class="sxs-lookup"><span data-stu-id="5235c-103">You can use a <xref:System.Drawing.StringFormat> object to specify that text be drawn vertically rather than horizontally.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5235c-104">例</span><span class="sxs-lookup"><span data-stu-id="5235c-104">Example</span></span>  
 <span data-ttu-id="5235c-105">次の例では、 <xref:System.Drawing.StringFormatFlags.DirectionVertical> オブジェクトのプロパティに値を代入し <xref:System.Drawing.StringFormat.FormatFlags%2A> <xref:System.Drawing.StringFormat> ます。</span><span class="sxs-lookup"><span data-stu-id="5235c-105">The following example assigns the value <xref:System.Drawing.StringFormatFlags.DirectionVertical> to the <xref:System.Drawing.StringFormat.FormatFlags%2A> property of a <xref:System.Drawing.StringFormat> object.</span></span> <span data-ttu-id="5235c-106">その <xref:System.Drawing.StringFormat> オブジェクトは <xref:System.Drawing.Graphics.DrawString%2A> 、クラスのメソッドに渡され <xref:System.Drawing.Graphics> ます。</span><span class="sxs-lookup"><span data-stu-id="5235c-106">That <xref:System.Drawing.StringFormat> object is passed to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="5235c-107">値は <xref:System.Drawing.StringFormatFlags.DirectionVertical> 列挙体のメンバーです <xref:System.Drawing.StringFormatFlags> 。</span><span class="sxs-lookup"><span data-stu-id="5235c-107">The value <xref:System.Drawing.StringFormatFlags.DirectionVertical> is a member of the <xref:System.Drawing.StringFormatFlags> enumeration.</span></span>  
  
 <span data-ttu-id="5235c-108">次の図は、縦のテキストを示しています。</span><span class="sxs-lookup"><span data-stu-id="5235c-108">The following illustration shows the vertical text:</span></span>
  
 ![縦書きのフォントテキストを示すグラフィック。](./media/how-to-create-vertical-text/vertical-font-text-graphic.png)  
  
 [!code-csharp[System.Drawing.FontsAndText#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.FontsAndText#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5235c-110">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="5235c-110">Compiling the Code</span></span>  
  
- <span data-ttu-id="5235c-111">前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、のパラメーターであるを必要とし <xref:System.Windows.Forms.PaintEventHandler> ます。</span><span class="sxs-lookup"><span data-stu-id="5235c-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e` , which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5235c-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="5235c-112">See also</span></span>

- [<span data-ttu-id="5235c-113">方法: GDI を使用してテキストを描画する</span><span class="sxs-lookup"><span data-stu-id="5235c-113">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
