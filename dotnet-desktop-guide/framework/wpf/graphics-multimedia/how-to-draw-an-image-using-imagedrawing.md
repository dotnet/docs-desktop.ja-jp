---
title: '方法: ImageDrawing を使用してイメージを描画する'
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], images
- graphics [WPF], drawing images
- images [WPF], drawing
ms.assetid: df28ab41-25fb-4ab3-b51d-7f695b24f55e
ms.openlocfilehash: f9459185bf81160b45222e7d6821e0f945ada381
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974308"
---
# <a name="how-to-draw-an-image-using-imagedrawing"></a><span data-ttu-id="6f29c-102">方法: ImageDrawing を使用してイメージを描画する</span><span class="sxs-lookup"><span data-stu-id="6f29c-102">How to: Draw an Image Using ImageDrawing</span></span>
<span data-ttu-id="6f29c-103">この例では、<xref:System.Windows.Media.ImageDrawing> を使用してイメージを描画する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6f29c-103">This example shows how to use an <xref:System.Windows.Media.ImageDrawing> to draw an image.</span></span> <span data-ttu-id="6f29c-104"><xref:System.Windows.Media.ImageDrawing> を使用すると、<xref:System.Windows.Media.ImageSource> に、<xref:System.Windows.Media.DrawingBrush>、<xref:System.Windows.Media.DrawingImage>、または <xref:System.Windows.Media.Visual> を表示できます。</span><span class="sxs-lookup"><span data-stu-id="6f29c-104">An <xref:System.Windows.Media.ImageDrawing> enables you display an <xref:System.Windows.Media.ImageSource> with a <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.DrawingImage>, or <xref:System.Windows.Media.Visual>.</span></span> <span data-ttu-id="6f29c-105">イメージを描画するには、<xref:System.Windows.Media.ImageDrawing> を作成し、それの <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> プロパティと <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="6f29c-105">To draw an image, you create an <xref:System.Windows.Media.ImageDrawing> and set its <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> and <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> properties.</span></span> <span data-ttu-id="6f29c-106"><xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> プロパティでは描画するイメージを指定し、<xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> プロパティでは各イメージの位置とサイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="6f29c-106">The <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> property specifies the image to draw, and the <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> property specifies the position and size of each image.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f29c-107">例</span><span class="sxs-lookup"><span data-stu-id="6f29c-107">Example</span></span>  
 <span data-ttu-id="6f29c-108">次の例では、4 つの <xref:System.Windows.Media.ImageDrawing> オブジェクトが使用された合成画が作成されます。</span><span class="sxs-lookup"><span data-stu-id="6f29c-108">The following example creates a composite drawing using four <xref:System.Windows.Media.ImageDrawing> objects.</span></span> <span data-ttu-id="6f29c-109">この例では、次の画像が生成されます。</span><span class="sxs-lookup"><span data-stu-id="6f29c-109">This example produces the following image:</span></span>  
  
 <span data-ttu-id="6f29c-110">![複数の DrawingImage オブジェクト](./media/graphicsmm-imagedrawingexample.jpg "graphicsmm_ImageDrawingExample")</span><span class="sxs-lookup"><span data-stu-id="6f29c-110">![Several DrawingImage objects](./media/graphicsmm-imagedrawingexample.jpg "graphicsmm_ImageDrawingExample")</span></span>  
<span data-ttu-id="6f29c-111">4 つの ImageDrawing オブジェクト</span><span class="sxs-lookup"><span data-stu-id="6f29c-111">Four ImageDrawing objects</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawingExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawingexample)]
 [!code-xaml[DrawingMiscSnippets_snip#ImageDrawingExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawingexample)]  
  
 <span data-ttu-id="6f29c-112"><xref:System.Windows.Media.ImageDrawing> を使用せずにイメージを表示する簡単な方法の例については、「[イメージ要素使用する](../controls/how-to-use-the-image-element.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f29c-112">For an example showing a simple way to display an image without using <xref:System.Windows.Media.ImageDrawing>, see [Use the Image Element](../controls/how-to-use-the-image-element.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f29c-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="6f29c-113">See also</span></span>

- <xref:System.Windows.Freezable.Freeze%2A>
- <xref:System.Windows.Controls.Image>
- [<span data-ttu-id="6f29c-114">Drawing オブジェクトの概要</span><span class="sxs-lookup"><span data-stu-id="6f29c-114">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="6f29c-115">Freezable オブジェクトの概要</span><span class="sxs-lookup"><span data-stu-id="6f29c-115">Freezable Objects Overview</span></span>](../advanced/freezable-objects-overview.md)
- [<span data-ttu-id="6f29c-116">PresentationOptions:Freeze 属性</span><span class="sxs-lookup"><span data-stu-id="6f29c-116">PresentationOptions:Freeze Attribute</span></span>](../advanced/presentationoptions-freeze-attribute.md)
