---
title: '方法: ArcSegment のサイズをアニメーション化する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], animation
- animation [WPF], ArcSegment size
- ArcSegment [WPF], animating size
ms.assetid: f93a1065-b00a-4d7e-9d4b-37023f98186a
ms.openlocfilehash: d1b9db72c9d1ea47f3c1bc6476a3b579bc03eae2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96979954"
---
# <a name="how-to-animate-the-size-of-an-arcsegment"></a>方法: ArcSegment のサイズをアニメーション化する
この例では、<xref:System.Windows.Media.ArcSegment> の <xref:System.Windows.Media.ArcSegment.Size%2A> プロパティをアニメーション化する方法を示します。  
  
## <a name="example"></a>例  
 次の例では、<xref:System.Windows.Media.ArcSegment> を作成します。これは、画面に読み込まれたときに、その <xref:System.Windows.Media.ArcSegment.Size%2A> をアニメーション化します。  
  
 [!code-csharp[BasicAnimations_snip#SizeAnimationWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/SizeAnimationExample.cs#sizeanimationwholepage)]
 [!code-vb[BasicAnimations_snip#SizeAnimationWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/SizeAnimationExample.vb#sizeanimationwholepage)]  
  
 ジオメトリとアニメーションのその他のサンプルについては、「[ジオメトリのサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)」を参照してください。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Media.ArcSegment.Size%2A>
- <xref:System.Windows.Media.ArcSegment>
- [アニメーションの概要](animation-overview.md)
- [ジオメトリの概要](geometry-overview.md)
- [ジオメトリに関する「方法」トピック](geometries-how-to-topics.md)
- [アニメーションおよびタイミングに関する「方法」トピック](animation-and-timing-how-to-topics.md)
