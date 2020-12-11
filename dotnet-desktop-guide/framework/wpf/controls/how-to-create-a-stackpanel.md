---
title: '方法: StackPanel を作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- StackPanel control [WPF], creating
ms.assetid: e7ce65cb-720a-4bb6-95b6-286b74488a58
ms.openlocfilehash: bcf6decff2fbc012b5f8b62794f0d7b2cd9f29fc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984835"
---
# <a name="how-to-create-a-stackpanel"></a><span data-ttu-id="e204b-102">方法: StackPanel を作成する</span><span class="sxs-lookup"><span data-stu-id="e204b-102">How to: Create a StackPanel</span></span>
<span data-ttu-id="e204b-103">この例では、<xref:System.Windows.Controls.StackPanel> を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e204b-103">This example shows how to create a <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e204b-104">例</span><span class="sxs-lookup"><span data-stu-id="e204b-104">Example</span></span>  
 <span data-ttu-id="e204b-105"><xref:System.Windows.Controls.StackPanel> では、指定した方向で要素を積み重ねることができます。</span><span class="sxs-lookup"><span data-stu-id="e204b-105">A <xref:System.Windows.Controls.StackPanel> allows you to stack elements in a specified direction.</span></span> <span data-ttu-id="e204b-106"><xref:System.Windows.Controls.StackPanel> で定義されているプロパティを使用することで、コンテンツを上下 (既定) または左右に浮動させることができます。</span><span class="sxs-lookup"><span data-stu-id="e204b-106">By using properties that are defined on <xref:System.Windows.Controls.StackPanel>, content can flow both vertically, which is the default setting, or horizontally.</span></span>  
  
 <span data-ttu-id="e204b-107">次の例では、<xref:System.Windows.Controls.StackPanel> を使用することで、5 つの <xref:System.Windows.Controls.TextBlock> コントロールが縦に積み重ねられます。それぞれ、<xref:System.Windows.Controls.Border> と <xref:System.Windows.Controls.Border.Background%2A> が異なります。</span><span class="sxs-lookup"><span data-stu-id="e204b-107">The following example vertically stacks five <xref:System.Windows.Controls.TextBlock> controls, each with a different <xref:System.Windows.Controls.Border> and <xref:System.Windows.Controls.Border.Background%2A>, by using <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="e204b-108"><xref:System.Windows.FrameworkElement.Width%2A> が指定されていない子要素は拡張され、親ウィンドウを満たします。ただし、<xref:System.Windows.FrameworkElement.Width%2A> が指定されている子要素はウィンドウ内の中心に配置されます。</span><span class="sxs-lookup"><span data-stu-id="e204b-108">The child elements that have no specified <xref:System.Windows.FrameworkElement.Width%2A> stretch to fill the parent window; however, the child elements that have a specified <xref:System.Windows.FrameworkElement.Width%2A>, are centered within the window.</span></span>  
  
 <span data-ttu-id="e204b-109"><xref:System.Windows.Controls.StackPanel> における積み重ねの既定の方向は縦です。</span><span class="sxs-lookup"><span data-stu-id="e204b-109">The default stack direction in a <xref:System.Windows.Controls.StackPanel> is vertical.</span></span> <span data-ttu-id="e204b-110"><xref:System.Windows.Controls.StackPanel> でコンテンツ フローを制御するには、<xref:System.Windows.Controls.StackPanel.Orientation%2A> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="e204b-110">To control content flow in a <xref:System.Windows.Controls.StackPanel>, use the <xref:System.Windows.Controls.StackPanel.Orientation%2A> property.</span></span> <span data-ttu-id="e204b-111"><xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> プロパティを使用することで横の配置を制御できます。</span><span class="sxs-lookup"><span data-stu-id="e204b-111">You can control horizontal alignment by using the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property.</span></span>  
  
```xaml  
<Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation" WindowTitle="StackPanel Sample">  
  <StackPanel>  
    <Border Background="SkyBlue" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="12">Stacked Item #1</TextBlock>  
    </Border>  
    <Border Width="400" Background="CadetBlue" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="14">Stacked Item #2</TextBlock>  
    </Border>  
    <Border Background="LightGoldenRodYellow" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="16">Stacked Item #3</TextBlock>  
    </Border>  
    <Border Width="200" Background="PaleGreen" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="18">Stacked Item #4</TextBlock>  
    </Border>  
    <Border Background="White" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="20">Stacked Item #5</TextBlock>  
    </Border>  
  </StackPanel>  
</Page>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e204b-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="e204b-112">See also</span></span>

- <xref:System.Windows.Controls.StackPanel>
- [<span data-ttu-id="e204b-113">パネルの概要</span><span class="sxs-lookup"><span data-stu-id="e204b-113">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="e204b-114">方法トピック</span><span class="sxs-lookup"><span data-stu-id="e204b-114">How-to Topics</span></span>](stackpanel-how-to-topics.md)
