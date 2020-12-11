---
title: '方法: スライダーの目盛りをカスタマイズする'
ms.date: 03/30/2017
helpviewer_keywords:
- TickBar [WPF]
- Slider control [WPF], creating with TickBar
ms.assetid: 4fa694f2-a620-4b15-be78-5f4286f89361
ms.openlocfilehash: 150a546a2c94c1bd552f1f7486652d2b4ad900e3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985159"
---
# <a name="how-to-customize-the-ticks-on-a-slider"></a><span data-ttu-id="cde4a-102">方法: スライダーの目盛りをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="cde4a-102">How to: Customize the Ticks on a Slider</span></span>

<span data-ttu-id="cde4a-103">この例では、ティックのある <xref:System.Windows.Controls.Slider> コントロールを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="cde4a-103">This example shows how to create a <xref:System.Windows.Controls.Slider> control that has tick marks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cde4a-104">例</span><span class="sxs-lookup"><span data-stu-id="cde4a-104">Example</span></span>  

 <span data-ttu-id="cde4a-105"><xref:System.Windows.Controls.Primitives.TickBar> は、既定値である <xref:System.Windows.Controls.Primitives.TickPlacement.None> 以外の値に <xref:System.Windows.Controls.Slider.TickPlacement%2A> プロパティを設定したときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="cde4a-105">The <xref:System.Windows.Controls.Primitives.TickBar> displays when you set the <xref:System.Windows.Controls.Slider.TickPlacement%2A> property to a value other than <xref:System.Windows.Controls.Primitives.TickPlacement.None>, which is the default value.</span></span>  
  
 <span data-ttu-id="cde4a-106">次の例では、ティックを表示する <xref:System.Windows.Controls.Primitives.TickBar> で <xref:System.Windows.Controls.Slider> を定義する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="cde4a-106">The following example shows how to create a <xref:System.Windows.Controls.Slider> with a <xref:System.Windows.Controls.Primitives.TickBar> that displays tick marks.</span></span> <span data-ttu-id="cde4a-107"><xref:System.Windows.Controls.Slider.TickPlacement%2A> プロパティと <xref:System.Windows.Controls.Slider.TickFrequency%2A> プロパティによって、ティックの場所とティックの間隔が定義されます。</span><span class="sxs-lookup"><span data-stu-id="cde4a-107">The <xref:System.Windows.Controls.Slider.TickPlacement%2A> and <xref:System.Windows.Controls.Slider.TickFrequency%2A> properties define the location of the tick marks and the interval between them.</span></span> <span data-ttu-id="cde4a-108"><xref:System.Windows.Controls.Primitives.Thumb> を動かすと、ツールヒントに <xref:System.Windows.Controls.Slider> の値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cde4a-108">When you move the <xref:System.Windows.Controls.Primitives.Thumb>, tooltips display the value of the <xref:System.Windows.Controls.Slider>.</span></span> <span data-ttu-id="cde4a-109"><xref:System.Windows.Controls.Slider.AutoToolTipPlacement%2A> プロパティによってツールヒントの場所が定義されます。</span><span class="sxs-lookup"><span data-stu-id="cde4a-109">The <xref:System.Windows.Controls.Slider.AutoToolTipPlacement%2A> property defines where the tooltips occur.</span></span> <span data-ttu-id="cde4a-110"><xref:System.Windows.Controls.Slider.IsSnapToTickEnabled%2A> が `true` に設定されているため、<xref:System.Windows.Controls.Primitives.Thumb> の移動はティックの位置に対応します。</span><span class="sxs-lookup"><span data-stu-id="cde4a-110">The <xref:System.Windows.Controls.Primitives.Thumb> movements correspond to the location of the tick marks because <xref:System.Windows.Controls.Slider.IsSnapToTickEnabled%2A> is set to `true`.</span></span>  
  
 <span data-ttu-id="cde4a-111">次の例では、<xref:System.Windows.Controls.Slider.Ticks%2A> プロパティを使用して <xref:System.Windows.Controls.Slider> に沿ってティックを作成するとき、間隔を不規則にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="cde4a-111">The following example shows how to use the <xref:System.Windows.Controls.Slider.Ticks%2A> property to create tick marks along the <xref:System.Windows.Controls.Slider> at irregular intervals.</span></span>  
  
 [!code-xaml[Slider#4](~/samples/snippets/xaml/VS_Snippets_Wpf/Slider/xaml/window1.xaml#4)]  
  
## <a name="see-also"></a><span data-ttu-id="cde4a-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="cde4a-112">See also</span></span>

- <xref:System.Windows.Controls.Slider>
- <xref:System.Windows.Controls.Primitives.TickBar>
- <xref:System.Windows.Controls.Slider.TickPlacement%2A>
- <span data-ttu-id="cde4a-113">[方法: スライダーをプロパティ値にバインドする](/previous-versions/dotnet/netframework-3.5/ms788716(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="cde4a-113">[How to: Bind a Slider to a Property Value](/previous-versions/dotnet/netframework-3.5/ms788716(v=vs.90))</span></span>
