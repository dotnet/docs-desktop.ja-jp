---
title: '方法: カスタム パネル要素を作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Panel control [WPF]
- custom Panel elements [WPF]
ms.assetid: e0df4f1e-8c07-4e86-89a3-e22acfffdc2a
ms.openlocfilehash: 31edc75114c5dad613e5b65e7d8b051e2c3713af
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985667"
---
# <a name="how-to-create-a-custom-panel-element"></a><span data-ttu-id="c6f7b-102">方法: カスタム パネル要素を作成する</span><span class="sxs-lookup"><span data-stu-id="c6f7b-102">How to: Create a Custom Panel Element</span></span>
## <a name="example"></a><span data-ttu-id="c6f7b-103">例</span><span class="sxs-lookup"><span data-stu-id="c6f7b-103">Example</span></span>  
 <span data-ttu-id="c6f7b-104">この例では、<xref:System.Windows.Controls.Panel> 要素の既定のレイアウト動作をオーバーライドし、<xref:System.Windows.Controls.Panel> から派生したカスタム レイアウト要素を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c6f7b-104">This example shows how to override the default layout behavior of the <xref:System.Windows.Controls.Panel> element and create custom layout elements that are derived from <xref:System.Windows.Controls.Panel>.</span></span>  
  
 <span data-ttu-id="c6f7b-105">この例では、`PlotPanel` と呼ばれる単純なカスタム <xref:System.Windows.Controls.Panel> 要素が定義されます。これは、2 つのハードコーディングされた x 座標と y 座標に従って子要素を配置するものです。</span><span class="sxs-lookup"><span data-stu-id="c6f7b-105">The example defines a simple custom <xref:System.Windows.Controls.Panel> element called `PlotPanel`, which positions child elements according to two hard-coded x- and y-coordinates.</span></span> <span data-ttu-id="c6f7b-106">この例では、`x` と `y` の両方が `50` に設定されています。したがって、すべての子要素が、x 軸と y 軸上のその位置に配置されます。</span><span class="sxs-lookup"><span data-stu-id="c6f7b-106">In this example, `x` and `y` are both set to `50`; therefore, all child elements are positioned at that location on the x and y axes.</span></span>  
  
 <span data-ttu-id="c6f7b-107">カスタム <xref:System.Windows.Controls.Panel> 動作を実装するために、この例では <xref:System.Windows.FrameworkElement.MeasureOverride%2A> メソッドと <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> メソッドが使用されます。</span><span class="sxs-lookup"><span data-stu-id="c6f7b-107">To implement custom <xref:System.Windows.Controls.Panel> behaviors, the example uses the <xref:System.Windows.FrameworkElement.MeasureOverride%2A> and <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> methods.</span></span> <span data-ttu-id="c6f7b-108">各メソッドからは、子要素を配置および表示するために必要な <xref:System.Windows.Size> データが返されます。</span><span class="sxs-lookup"><span data-stu-id="c6f7b-108">Each method returns the <xref:System.Windows.Size> data that is necessary to position and render child elements.</span></span>  
  
 [!code-cpp[PlotPanel#1](~/samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="c6f7b-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="c6f7b-109">See also</span></span>

- <xref:System.Windows.Controls.Panel>
- [<span data-ttu-id="c6f7b-110">パネルの概要</span><span class="sxs-lookup"><span data-stu-id="c6f7b-110">Panels Overview</span></span>](panels-overview.md)
