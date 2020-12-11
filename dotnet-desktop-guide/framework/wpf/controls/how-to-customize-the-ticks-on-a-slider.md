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
# <a name="how-to-customize-the-ticks-on-a-slider"></a>方法: スライダーの目盛りをカスタマイズする

この例では、ティックのある <xref:System.Windows.Controls.Slider> コントロールを作成する方法を示します。  
  
## <a name="example"></a>例  

 <xref:System.Windows.Controls.Primitives.TickBar> は、既定値である <xref:System.Windows.Controls.Primitives.TickPlacement.None> 以外の値に <xref:System.Windows.Controls.Slider.TickPlacement%2A> プロパティを設定したときに表示されます。  
  
 次の例では、ティックを表示する <xref:System.Windows.Controls.Primitives.TickBar> で <xref:System.Windows.Controls.Slider> を定義する方法を示します。 <xref:System.Windows.Controls.Slider.TickPlacement%2A> プロパティと <xref:System.Windows.Controls.Slider.TickFrequency%2A> プロパティによって、ティックの場所とティックの間隔が定義されます。 <xref:System.Windows.Controls.Primitives.Thumb> を動かすと、ツールヒントに <xref:System.Windows.Controls.Slider> の値が表示されます。 <xref:System.Windows.Controls.Slider.AutoToolTipPlacement%2A> プロパティによってツールヒントの場所が定義されます。 <xref:System.Windows.Controls.Slider.IsSnapToTickEnabled%2A> が `true` に設定されているため、<xref:System.Windows.Controls.Primitives.Thumb> の移動はティックの位置に対応します。  
  
 次の例では、<xref:System.Windows.Controls.Slider.Ticks%2A> プロパティを使用して <xref:System.Windows.Controls.Slider> に沿ってティックを作成するとき、間隔を不規則にする方法を示します。  
  
 [!code-xaml[Slider#4](~/samples/snippets/xaml/VS_Snippets_Wpf/Slider/xaml/window1.xaml#4)]  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Controls.Slider>
- <xref:System.Windows.Controls.Primitives.TickBar>
- <xref:System.Windows.Controls.Slider.TickPlacement%2A>
- [方法: スライダーをプロパティ値にバインドする](/previous-versions/dotnet/netframework-3.5/ms788716(v=vs.90))
