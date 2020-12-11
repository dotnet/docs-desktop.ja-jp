---
title: '方法: Canvas を作成および使用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Canvas
- Canvas control [WPF], creating
- Canvas control [WPF], using
ms.assetid: 420b9487-9a15-477c-9489-a22a4dec7779
ms.openlocfilehash: c9ee49327b6490df094e84b4227ea0fb2e757c4d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983512"
---
# <a name="how-to-create-and-use-a-canvas"></a><span data-ttu-id="e2c31-102">方法: Canvas を作成および使用する</span><span class="sxs-lookup"><span data-stu-id="e2c31-102">How to: Create and Use a Canvas</span></span>
<span data-ttu-id="e2c31-103">この例は、<xref:System.Windows.Controls.Canvas> のインスタンスを作成して使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e2c31-103">This example shows how to create and use an instance of <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2c31-104">例</span><span class="sxs-lookup"><span data-stu-id="e2c31-104">Example</span></span>  
 <span data-ttu-id="e2c31-105">次の例では、<xref:System.Windows.Controls.Canvas> の <xref:System.Windows.Controls.Canvas.SetTop%2A> メソッドと <xref:System.Windows.Controls.Canvas.SetLeft%2A> メソッドの使用により、2 つの <xref:System.Windows.Controls.TextBlock> 要素が明示的に配置されます。</span><span class="sxs-lookup"><span data-stu-id="e2c31-105">The following example explicitly positions two <xref:System.Windows.Controls.TextBlock> elements by using the <xref:System.Windows.Controls.Canvas.SetTop%2A> and <xref:System.Windows.Controls.Canvas.SetLeft%2A> methods of <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="e2c31-106">この例では、<xref:System.Windows.Controls.Canvas> に `LightSteelBlue` の <xref:System.Windows.Controls.Control.Background%2A> 色も割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="e2c31-106">The example also assigns a <xref:System.Windows.Controls.Control.Background%2A> color of `LightSteelBlue` to the <xref:System.Windows.Controls.Canvas>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e2c31-107">[!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] を使用して <xref:System.Windows.Controls.TextBlock> 要素を配置する場合は、<xref:System.Windows.Controls.Canvas.Top%2A> プロパティと <xref:System.Windows.Controls.Canvas.Left%2A> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="e2c31-107">When you use [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] to position <xref:System.Windows.Controls.TextBlock> elements, use the <xref:System.Windows.Controls.Canvas.Top%2A> and <xref:System.Windows.Controls.Canvas.Left%2A> properties.</span></span>  
  
 [!code-csharp[CanvasCode#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasCode/CSharp/Canvas_Code.cs#1)]
 [!code-vb[CanvasCode#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasCode/VisualBasic/canvas_vb.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e2c31-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="e2c31-108">See also</span></span>

- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.TextBlock>
- <xref:System.Windows.Controls.Canvas.SetTop%2A>
- <xref:System.Windows.Controls.Canvas.SetLeft%2A>
- <xref:System.Windows.Controls.Canvas.Top%2A>
- <xref:System.Windows.Controls.Canvas.Left%2A>
- [<span data-ttu-id="e2c31-109">パネルの概要</span><span class="sxs-lookup"><span data-stu-id="e2c31-109">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="e2c31-110">方法トピック</span><span class="sxs-lookup"><span data-stu-id="e2c31-110">How-to Topics</span></span>](canvas-how-to-topics.md)
