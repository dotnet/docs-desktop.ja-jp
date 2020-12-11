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
# <a name="how-to-use-a-drawing-as-an-image-source"></a>方法: 描画をイメージ ソースとして使用する
この例では、<xref:System.Windows.Controls.Image> コントロールの <xref:System.Windows.Controls.Image.Source%2A> として <xref:System.Windows.Media.Drawing> を使用する方法を示します。 <xref:System.Windows.Controls.Image> コントロールで <xref:System.Windows.Media.Drawing> を表示するには、<xref:System.Windows.Controls.Image> コントロールの <xref:System.Windows.Controls.Image.Source%2A> として <xref:System.Windows.Media.DrawingImage> を使用し、表示する描画に <xref:System.Windows.Media.DrawingImage> オブジェクトの <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> プロパティを設定します。  
  
## <a name="example"></a>例  
 次の例では、<xref:System.Windows.Media.DrawingImage> と <xref:System.Windows.Controls.Image> コントロールを使用して <xref:System.Windows.Media.GeometryDrawing> を表示します。 この例を実行すると、次の出力が生成されます。  
  
 ![2 つの楕円の GeometryDrawing](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
DrawingImage  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Freezable.Freeze%2A>
- [ImageDrawing を使用してイメージを描画する](how-to-draw-an-image-using-imagedrawing.md)
- [Drawing オブジェクトの概要](drawing-objects-overview.md)
- [Freezable オブジェクトの概要](../advanced/freezable-objects-overview.md)
- [PresentationOptions:Freeze 属性](../advanced/presentationoptions-freeze-attribute.md)
