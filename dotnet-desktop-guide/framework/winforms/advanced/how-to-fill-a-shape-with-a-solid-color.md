---
title: '方法: 純色で図形を塗りつぶす'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], adding to shapes
- shapes [Windows Forms], filling
ms.assetid: 06088b31-bac9-4ef3-9ebe-06c2c764d6df
ms.openlocfilehash: d6fe7a252029ff80f21d99f7342fabb1d29fbe24
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981336"
---
# <a name="how-to-fill-a-shape-with-a-solid-color"></a><span data-ttu-id="9cb59-102">方法: 純色で図形を塗りつぶす</span><span class="sxs-lookup"><span data-stu-id="9cb59-102">How to: Fill a Shape with a Solid Color</span></span>
<span data-ttu-id="9cb59-103">純色で図形を塗りつぶすには、オブジェクトを作成 <xref:System.Drawing.SolidBrush> し、その <xref:System.Drawing.SolidBrush> オブジェクトを引数としてクラスの fill メソッドの1つに渡し <xref:System.Drawing.Graphics> ます。</span><span class="sxs-lookup"><span data-stu-id="9cb59-103">To fill a shape with a solid color, create a <xref:System.Drawing.SolidBrush> object, and then pass that <xref:System.Drawing.SolidBrush> object as an argument to one of the fill methods of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="9cb59-104">次の例では、楕円に赤の色を入力する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9cb59-104">The following example shows how to fill an ellipse with the color red.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9cb59-105">例</span><span class="sxs-lookup"><span data-stu-id="9cb59-105">Example</span></span>  
 <span data-ttu-id="9cb59-106">次のコードでは、 <xref:System.Drawing.SolidBrush.%23ctor%2A> コンストラクターは <xref:System.Drawing.Color> オブジェクトを唯一の引数として受け取ります。</span><span class="sxs-lookup"><span data-stu-id="9cb59-106">In the following code, the <xref:System.Drawing.SolidBrush.%23ctor%2A> constructor takes a <xref:System.Drawing.Color> object as its only argument.</span></span> <span data-ttu-id="9cb59-107">メソッドによって使用される値は、 <xref:System.Drawing.Color.FromArgb%2A> 色のアルファ、赤、緑、および青のコンポーネントを表します。</span><span class="sxs-lookup"><span data-stu-id="9cb59-107">The values used by the <xref:System.Drawing.Color.FromArgb%2A> method represent the alpha, red, green, and blue components of the color.</span></span> <span data-ttu-id="9cb59-108">これらの値はそれぞれ 0 ~ 255 の範囲で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9cb59-108">Each of these values must be in the range 0 through 255.</span></span> <span data-ttu-id="9cb59-109">最初の255は、色が完全に不透明であることを示します。2番目の255は、赤のコンポーネントの輝度が完全であることを示します。</span><span class="sxs-lookup"><span data-stu-id="9cb59-109">The first 255 indicates that the color is fully opaque, and the second 255 indicates that the red component is at full intensity.</span></span> <span data-ttu-id="9cb59-110">2つの0は、緑と青のコンポーネントの両方の輝度が0であることを示します。</span><span class="sxs-lookup"><span data-stu-id="9cb59-110">The two zeros indicate that the green and blue components both have an intensity of 0.</span></span>  
  
 <span data-ttu-id="9cb59-111">メソッドに渡される4つの数値 (0、0、100、60) は、 <xref:System.Drawing.Graphics.FillEllipse%2A> 楕円の外接する四角形の位置とサイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="9cb59-111">The four numbers (0, 0, 100, 60) passed to the <xref:System.Drawing.Graphics.FillEllipse%2A> method specify the location and size of the bounding rectangle for the ellipse.</span></span> <span data-ttu-id="9cb59-112">四角形には、(0, 0) の左上隅、幅100、および高さ60があります。</span><span class="sxs-lookup"><span data-stu-id="9cb59-112">The rectangle has an upper-left corner of (0, 0), a width of 100, and a height of 60.</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingABrush#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9cb59-113">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="9cb59-113">Compiling the Code</span></span>  
 <span data-ttu-id="9cb59-114">前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。</span><span class="sxs-lookup"><span data-stu-id="9cb59-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cb59-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="9cb59-115">See also</span></span>

- [<span data-ttu-id="9cb59-116">ブラシを使用した図形の塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="9cb59-116">Using a Brush to Fill Shapes</span></span>](using-a-brush-to-fill-shapes.md)
