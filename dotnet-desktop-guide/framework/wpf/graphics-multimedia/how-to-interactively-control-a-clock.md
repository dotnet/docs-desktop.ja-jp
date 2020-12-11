---
title: '方法: クロックを対話的に制御する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controlling clocks interactively [WPF]
- clocks [WPF], controlling interactively
ms.assetid: d0b520e0-2f18-4cef-977f-2909e709548a
ms.openlocfilehash: 2d18f395974750a6b85458f636a27f6101e7978f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984723"
---
# <a name="how-to-interactively-control-a-clock"></a><span data-ttu-id="98e6f-102">方法: クロックを対話的に制御する</span><span class="sxs-lookup"><span data-stu-id="98e6f-102">How to: Interactively Control a Clock</span></span>
<span data-ttu-id="98e6f-103"><xref:System.Windows.Media.Animation.Clock> オブジェクトの <xref:System.Windows.Media.Animation.ClockController> プロパティを使用すると、クロックを対話形式で開始、一時停止、再開、シークできることに加えて、その保留期間までクロックを進めたり、停止したりできます。</span><span class="sxs-lookup"><span data-stu-id="98e6f-103">A <xref:System.Windows.Media.Animation.Clock> object's <xref:System.Windows.Media.Animation.ClockController> property enables you to interactively start, pause, resume, seek, advance the clock to its fill period, and stop the clock.</span></span> <span data-ttu-id="98e6f-104">タイミング ツリーのルート クロックのみを対話式で制御できます。</span><span class="sxs-lookup"><span data-stu-id="98e6f-104">Only the root clock of a timing tree can be interactively controlled.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="98e6f-105">クロックを直接操作する必要のないアニメーションを対話的に制御する方法は他にもあります。それは、ストーリーボードを使用する方法です。</span><span class="sxs-lookup"><span data-stu-id="98e6f-105">There are other ways to interactively control animations that don't require you to work directly with clocks: you can also use Storyboards.</span></span> <span data-ttu-id="98e6f-106">ストーリーボードは、マークアップとコードの両方でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="98e6f-106">Storyboards are supported in both markup and code.</span></span> <span data-ttu-id="98e6f-107">例については、「[ストーリーボードを使ってプロパティをアニメーション化する](how-to-animate-a-property-by-using-a-storyboard.md)」または「[アニメーションの概要](animation-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98e6f-107">For an example, see [Animate a Property by Using a Storyboard](how-to-animate-a-property-by-using-a-storyboard.md) or the [Animation Overview](animation-overview.md).</span></span>  
  
 <span data-ttu-id="98e6f-108">次の例では、いくつかのボタンを使用して、アニメーション クロックを対話的に制御しています。</span><span class="sxs-lookup"><span data-stu-id="98e6f-108">In the following example, several buttons are used to interactively control an animation clock.</span></span>  
  
## <a name="example"></a><span data-ttu-id="98e6f-109">例</span><span class="sxs-lookup"><span data-stu-id="98e6f-109">Example</span></span>  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerExample.cs#graphicsmmclockcontrollerexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerexample.vb#graphicsmmclockcontrollerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="98e6f-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="98e6f-110">See also</span></span>

- [<span data-ttu-id="98e6f-111">ストーリーボードを使ってプロパティをアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="98e6f-111">Animate a Property by Using a Storyboard</span></span>](how-to-animate-a-property-by-using-a-storyboard.md)
- [<span data-ttu-id="98e6f-112">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="98e6f-112">Animation Overview</span></span>](animation-overview.md)
