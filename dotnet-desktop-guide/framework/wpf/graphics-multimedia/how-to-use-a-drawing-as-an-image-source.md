---
title: '方法: 描画をイメージ ソースとして使用する'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], drawings [WPF], as image sources
- image sources [WPF], drawings
- drawings [WPF], as image sources
ms.assetid: dcf71c7b-9e86-4b8e-8e39-0d0ce0389ef4
ms.openlocfilehash: d4b91a6495e1c54400d5fbfe43b6311d908565a7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980365"
---
# <a name="how-to-use-a-drawing-as-an-image-source"></a><span data-ttu-id="d91f7-102">方法: 描画をイメージ ソースとして使用する</span><span class="sxs-lookup"><span data-stu-id="d91f7-102">How to: Use a Drawing as an Image Source</span></span>
<span data-ttu-id="d91f7-103">この例では、<xref:System.Windows.Controls.Image> コントロールの <xref:System.Windows.Controls.Image.Source%2A> として <xref:System.Windows.Media.Drawing> を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d91f7-103">This example shows how to use a <xref:System.Windows.Media.Drawing> as the <xref:System.Windows.Controls.Image.Source%2A> for an <xref:System.Windows.Controls.Image> control.</span></span> <span data-ttu-id="d91f7-104"><xref:System.Windows.Controls.Image> コントロールで <xref:System.Windows.Media.Drawing> を表示するには、<xref:System.Windows.Controls.Image> コントロールの <xref:System.Windows.Controls.Image.Source%2A> として <xref:System.Windows.Media.DrawingImage> を使用し、表示する描画に <xref:System.Windows.Media.DrawingImage> オブジェクトの <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="d91f7-104">To display a <xref:System.Windows.Media.Drawing> with an <xref:System.Windows.Controls.Image> control, use a <xref:System.Windows.Media.DrawingImage> as the <xref:System.Windows.Controls.Image> control's <xref:System.Windows.Controls.Image.Source%2A> and set the <xref:System.Windows.Media.DrawingImage> object's <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> property to the drawing you want to display.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d91f7-105">例</span><span class="sxs-lookup"><span data-stu-id="d91f7-105">Example</span></span>  
 <span data-ttu-id="d91f7-106">次の例では、<xref:System.Windows.Media.DrawingImage> と <xref:System.Windows.Controls.Image> コントロールを使用して <xref:System.Windows.Media.GeometryDrawing> を表示します。</span><span class="sxs-lookup"><span data-stu-id="d91f7-106">The following example uses a <xref:System.Windows.Media.DrawingImage> and an <xref:System.Windows.Controls.Image> control to display a <xref:System.Windows.Media.GeometryDrawing>.</span></span> <span data-ttu-id="d91f7-107">この例を実行すると、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="d91f7-107">This example produces the following output:</span></span>  
  
 <span data-ttu-id="d91f7-108">![2 つの楕円の GeometryDrawing](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span><span class="sxs-lookup"><span data-stu-id="d91f7-108">![A GeometryDrawing of two ellipses](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span></span>  
<span data-ttu-id="d91f7-109">DrawingImage</span><span class="sxs-lookup"><span data-stu-id="d91f7-109">A DrawingImage</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="d91f7-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="d91f7-110">See also</span></span>

- <xref:System.Windows.Freezable.Freeze%2A>
- [<span data-ttu-id="d91f7-111">ImageDrawing を使用してイメージを描画する</span><span class="sxs-lookup"><span data-stu-id="d91f7-111">Draw an Image Using ImageDrawing</span></span>](how-to-draw-an-image-using-imagedrawing.md)
- [<span data-ttu-id="d91f7-112">Drawing オブジェクトの概要</span><span class="sxs-lookup"><span data-stu-id="d91f7-112">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="d91f7-113">Freezable オブジェクトの概要</span><span class="sxs-lookup"><span data-stu-id="d91f7-113">Freezable Objects Overview</span></span>](../advanced/freezable-objects-overview.md)
- [<span data-ttu-id="d91f7-114">PresentationOptions:Freeze 属性</span><span class="sxs-lookup"><span data-stu-id="d91f7-114">PresentationOptions:Freeze Attribute</span></span>](../advanced/presentationoptions-freeze-attribute.md)
