---
title: '方法: アニメーションを加速または減速させる'
ms.date: 03/30/2017
helpviewer_keywords:
- decelerating animation [WPF]
- accelerating animation [WPF]
- animation [WPF], accelerating
- animation [WPF], decelerating
ms.assetid: 4f383b2c-f94d-4a4e-9a06-f56f5dae95f9
ms.openlocfilehash: 7ab55ba44b866a992b9021284f170858f0108d15
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983960"
---
# <a name="how-to-accelerate-or-decelerate-an-animation"></a><span data-ttu-id="a4322-102">方法: アニメーションを加速または減速させる</span><span class="sxs-lookup"><span data-stu-id="a4322-102">How to: Accelerate or decelerate an animation</span></span>

<span data-ttu-id="a4322-103">この例では、時間の経過と共にアニメーションを加速および減速させる方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a4322-103">This example demonstrates how to make an animation accelerate and decelerate over time.</span></span> <span data-ttu-id="a4322-104">次の例では、<xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A> と <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A> の異なる設定を使用したアニメーションによって複数の四角形がアニメーション化されます。</span><span class="sxs-lookup"><span data-stu-id="a4322-104">In the following example, several rectangles are animated by animations with different <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A> and <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A> settings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4322-105">例</span><span class="sxs-lookup"><span data-stu-id="a4322-105">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AccelDecelExample.xaml#1)]  
  
 <span data-ttu-id="a4322-106">この例では、コードは省略されています。</span><span class="sxs-lookup"><span data-stu-id="a4322-106">Code has been omitted from this example.</span></span> <span data-ttu-id="a4322-107">詳しいコードについては、[アニメーションのタイミング動作 (C#)](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp) または[アニメーションのタイミング動作 (Visual Basic)](https://github.com/dotnet/docs/tree/master/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic) に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4322-107">For the complete code, see the [Animation Timing Behavior (C#)](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp) or [Animation Timing Behavior (Visual Basic)](https://github.com/dotnet/docs/tree/master/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic).</span></span>
