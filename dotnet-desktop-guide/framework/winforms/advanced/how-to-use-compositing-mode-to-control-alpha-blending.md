---
title: '方法: 複合モードを使用してアルファ ブレンドを制御する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- alpha blending [Windows Forms], compositing
- colors [Windows Forms], blending
- colors [Windows Forms], controlling transparency
ms.assetid: f331df2d-b395-4b0a-95be-24fec8c9bbb5
ms.openlocfilehash: 6863e59efa25323f80933bf8ab595316b430ef53
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981723"
---
# <a name="how-to-use-compositing-mode-to-control-alpha-blending"></a><span data-ttu-id="90d1a-102">方法: 複合モードを使用してアルファ ブレンドを制御する</span><span class="sxs-lookup"><span data-stu-id="90d1a-102">How to: Use Compositing Mode to Control Alpha Blending</span></span>
<span data-ttu-id="90d1a-103">次の特性を持つオフスクリーンビットマップを作成することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="90d1a-103">There may be times when you want to create an off-screen bitmap that has the following characteristics:</span></span>  
  
- <span data-ttu-id="90d1a-104">色には、255未満のアルファ値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="90d1a-104">Colors have alpha values that are less than 255.</span></span>  
  
- <span data-ttu-id="90d1a-105">ビットマップを作成すると、色はアルファブレンドされません。</span><span class="sxs-lookup"><span data-stu-id="90d1a-105">Colors are not alpha blended with each other as you create the bitmap.</span></span>  
  
- <span data-ttu-id="90d1a-106">完成したビットマップを表示すると、ビットマップ内の色は、ディスプレイデバイスの背景色とアルファブレンドされます。</span><span class="sxs-lookup"><span data-stu-id="90d1a-106">When you display the finished bitmap, colors in the bitmap are alpha blended with the background colors on the display device.</span></span>  
  
 <span data-ttu-id="90d1a-107">このようなビットマップを作成するには、空のオブジェクトを構築 <xref:System.Drawing.Bitmap> し、 <xref:System.Drawing.Graphics> そのビットマップに基づいてオブジェクトを構築します。</span><span class="sxs-lookup"><span data-stu-id="90d1a-107">To create such a bitmap, construct a blank <xref:System.Drawing.Bitmap> object, and then construct a <xref:System.Drawing.Graphics> object based on that bitmap.</span></span> <span data-ttu-id="90d1a-108">オブジェクトの合成モード <xref:System.Drawing.Graphics> をに設定し <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy?displayProperty=nameWithType> ます。</span><span class="sxs-lookup"><span data-stu-id="90d1a-108">Set the compositing mode of the <xref:System.Drawing.Graphics> object to <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="90d1a-109">例</span><span class="sxs-lookup"><span data-stu-id="90d1a-109">Example</span></span>  
 <span data-ttu-id="90d1a-110">次の例では、 <xref:System.Drawing.Graphics> オブジェクトに基づいてオブジェクトを作成し <xref:System.Drawing.Bitmap> ます。</span><span class="sxs-lookup"><span data-stu-id="90d1a-110">The following example creates a <xref:System.Drawing.Graphics> object based on a <xref:System.Drawing.Bitmap> object.</span></span> <span data-ttu-id="90d1a-111">このコードでは、 <xref:System.Drawing.Graphics> オブジェクトを2つの半透明ブラシ (アルファ = 160) と共に使用して、ビットマップに描画します。</span><span class="sxs-lookup"><span data-stu-id="90d1a-111">The code uses the <xref:System.Drawing.Graphics> object along with two semitransparent brushes (alpha = 160) to paint on the bitmap.</span></span> <span data-ttu-id="90d1a-112">このコードは、半透明のブラシを使用して赤の楕円と緑の楕円を塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="90d1a-112">The code fills a red ellipse and a green ellipse using the semitransparent brushes.</span></span> <span data-ttu-id="90d1a-113">緑の楕円は赤い楕円と重なっていますが、オブジェクトの合成モード <xref:System.Drawing.Graphics> がに設定されているため、緑は赤とブレンドされません <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy> 。</span><span class="sxs-lookup"><span data-stu-id="90d1a-113">The green ellipse overlaps the red ellipse, but the green is not blended with the red because the compositing mode of the <xref:System.Drawing.Graphics> object is set to <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy>.</span></span>  
  
 <span data-ttu-id="90d1a-114">このコードでは、画面にビットマップを2回描画します。1回は白の背景に、もう1回はマルチカラーの背景にします。</span><span class="sxs-lookup"><span data-stu-id="90d1a-114">The code draws the bitmap on the screen twice: once on a white background and once on a multicolored background.</span></span> <span data-ttu-id="90d1a-115">2つの楕円の一部であるビットマップのピクセルは、160のアルファ成分を持つため、楕円は画面の背景色とブレンドされます。</span><span class="sxs-lookup"><span data-stu-id="90d1a-115">The pixels in the bitmap that are part of the two ellipses have an alpha component of 160, so the ellipses are blended with the background colors on the screen.</span></span>  
  
 <span data-ttu-id="90d1a-116">次の図は、コード例の出力を示しています。</span><span class="sxs-lookup"><span data-stu-id="90d1a-116">The following illustration shows the output of the code example.</span></span> <span data-ttu-id="90d1a-117">省略記号は背景とブレンドされますが、互いにブレンドされることはありません。</span><span class="sxs-lookup"><span data-stu-id="90d1a-117">Note that the ellipses are blended with the background, but they are not blended with each other.</span></span>  
  
 ![楕円が背景とブレンドされていて、互いにブレンドされていないことを示す図。](./media/how-to-use-compositing-mode-to-control-alpha-blending/ellipses-blended-background.png)  
  
 <span data-ttu-id="90d1a-119">このコード例には、次のステートメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="90d1a-119">The code example contains this statement:</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.AlphaBlending#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#41)]  
  
 <span data-ttu-id="90d1a-120">楕円を背景と共に相互にブレンドする場合は、そのステートメントを次のように変更します。</span><span class="sxs-lookup"><span data-stu-id="90d1a-120">If you want the ellipses to be blended with each other as well as with the background, change that statement to the following:</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.AlphaBlending#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#42)]  
  
 <span data-ttu-id="90d1a-121">次の図は、変更されたコードの出力を示しています。</span><span class="sxs-lookup"><span data-stu-id="90d1a-121">The following illustration shows the output of the revised code.</span></span>  
  
 ![省略記号を背景に合わせて表示する図。](./media/how-to-use-compositing-mode-to-control-alpha-blending/blend-ellipses-background.png)  
  
 [!code-csharp[System.Drawing.AlphaBlending#43](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#43)]
 [!code-vb[System.Drawing.AlphaBlending#43](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#43)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="90d1a-123">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="90d1a-123">Compiling the Code</span></span>  
 <span data-ttu-id="90d1a-124">前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、のパラメーターであるを必要とし <xref:System.Windows.Forms.PaintEventHandler> ます。</span><span class="sxs-lookup"><span data-stu-id="90d1a-124">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90d1a-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="90d1a-125">See also</span></span>

- <xref:System.Drawing.Color.FromArgb%2A>
- [<span data-ttu-id="90d1a-126">アルファ ブレンドの直線と塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="90d1a-126">Alpha Blending Lines and Fills</span></span>](alpha-blending-lines-and-fills.md)
