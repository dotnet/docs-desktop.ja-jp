---
title: '方法: 描画に GuidelineSet を適用する'
ms.date: 03/30/2017
helpviewer_keywords:
- GuidelineSet property [WPF], applying to drawings
- graphics [WPF], GuidelineSet property
ms.assetid: 45f3e0b4-8820-45a7-b865-b8ea5b17b0c8
ms.openlocfilehash: 134236c5beca806b747d45f20764cc82ddd8a4e8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985048"
---
# <a name="how-to-apply-a-guidelineset-to-a-drawing"></a>方法: 描画に GuidelineSet を適用する
この例では、<xref:System.Windows.Media.GuidelineSet> を <xref:System.Windows.Media.DrawingGroup> に適用する方法を示します。  
  
 <xref:System.Windows.Media.DrawingGroup> クラスは、<xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> プロパティを持つ唯一の <xref:System.Windows.Media.Drawing> 型です。 別の <xref:System.Windows.Media.Drawing> 型に <xref:System.Windows.Media.GuidelineSet> を適用するには、それを <xref:System.Windows.Media.DrawingGroup> に追加し、<xref:System.Windows.Media.GuidelineSet> を <xref:System.Windows.Media.DrawingGroup> に適用します。  
  
## <a name="example"></a>例  
 次の例では、ほとんど同じである 2 つの <xref:System.Windows.Media.DrawingGroup> オブジェクトが作成されます。唯一の違いは、2 つ目の <xref:System.Windows.Media.DrawingGroup> に <xref:System.Windows.Media.GuidelineSet> があり、1 つ目にはそれがないことです。  
  
 この例からの出力を次の図に示します。 2 つの <xref:System.Windows.Media.DrawingGroup> オブジェクトではレンダリングの違いが微妙であるため、図の一部を拡大してあります。  
  
 ![GuidelineSet がある (またはない) DrawingGroup](./media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupGuidelineSetExample.cs#graphicsmmdrawinggroupguidelinesetexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupGuidelineSetExample.xaml#graphicsmmdrawinggroupguidelinesetexamplewholepage)]  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Media.DrawingGroup>
- <xref:System.Windows.Media.GuidelineSet>
- [Drawing オブジェクトの概要](drawing-objects-overview.md)
