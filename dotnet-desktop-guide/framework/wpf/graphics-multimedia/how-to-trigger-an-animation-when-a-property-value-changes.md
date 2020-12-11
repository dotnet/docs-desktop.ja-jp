---
title: '方法: プロパティ値が変化したときにアニメーションをトリガーする'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], starting when property values change
- triggering animation [WPF]
- Storyboards [WPF], starting when property values change
ms.assetid: 12399c21-0300-4f4f-9e3a-d92d9907e5f5
ms.openlocfilehash: 7e3eecedf7d464eeb8e4f60f2f05fa06d2e23e09
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984727"
---
# <a name="how-to-trigger-an-animation-when-a-property-value-changes"></a><span data-ttu-id="34995-102">方法: プロパティ値が変化したときにアニメーションをトリガーする</span><span class="sxs-lookup"><span data-stu-id="34995-102">How to: Trigger an Animation When a Property Value Changes</span></span>
<span data-ttu-id="34995-103">この例からは、<xref:System.Windows.Trigger> を使用し、プロパティ値が変わったときに <xref:System.Windows.Media.Animation.Storyboard> を開始する方法がわかります。</span><span class="sxs-lookup"><span data-stu-id="34995-103">This example shows how to use a <xref:System.Windows.Trigger> to start a <xref:System.Windows.Media.Animation.Storyboard> when a property value changes.</span></span> <span data-ttu-id="34995-104"><xref:System.Windows.Style>、<xref:System.Windows.Controls.ControlTemplate>、<xref:System.Windows.DataTemplate> 内で <xref:System.Windows.Trigger> を使用できます。</span><span class="sxs-lookup"><span data-stu-id="34995-104">You can use a <xref:System.Windows.Trigger> inside a <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>, or <xref:System.Windows.DataTemplate>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34995-105">例</span><span class="sxs-lookup"><span data-stu-id="34995-105">Example</span></span>  
 <span data-ttu-id="34995-106">次の例では、<xref:System.Windows.Trigger> を使用し、その <xref:System.Windows.UIElement.IsMouseOver%2A> プロパティが `true` になったとき、<xref:System.Windows.Controls.Button> の <xref:System.Windows.UIElement.Opacity%2A> をアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="34995-106">The following example uses a <xref:System.Windows.Trigger> to animate the <xref:System.Windows.UIElement.Opacity%2A> of a <xref:System.Windows.Controls.Button> when its <xref:System.Windows.UIElement.IsMouseOver%2A> property becomes `true`.</span></span>  
  
 [!code-xaml[AnimatePropertyStoryboards#PropertyTriggerExample](~/samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/PropertyTriggerExample.xaml#propertytriggerexample)]  
  
 <span data-ttu-id="34995-107">プロパティ <xref:System.Windows.Trigger> オブジェクトによって適用されたアニメーションは、<xref:System.Windows.EventTrigger> アニメーションや、<xref:System.Windows.Media.Animation.Storyboard> メソッドで始動するアニメーションより複雑に動作をします。</span><span class="sxs-lookup"><span data-stu-id="34995-107">Animations applied by property <xref:System.Windows.Trigger> objects behave in a more complex fashion than <xref:System.Windows.EventTrigger> animations or animations started using <xref:System.Windows.Media.Animation.Storyboard> methods.</span></span>  <span data-ttu-id="34995-108">他の <xref:System.Windows.Trigger> オブジェクトによって定義されたアニメーションで "手渡し" しますが、<xref:System.Windows.EventTrigger> と、メソッドで始動するアニメーションで構成を行います。</span><span class="sxs-lookup"><span data-stu-id="34995-108">They "handoff" with animations defined by other <xref:System.Windows.Trigger> objects, but compose with <xref:System.Windows.EventTrigger> and method-triggered animations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34995-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="34995-109">See also</span></span>

- <xref:System.Windows.Trigger>
- [<span data-ttu-id="34995-110">プロパティ アニメーションの手法の概要</span><span class="sxs-lookup"><span data-stu-id="34995-110">Property Animation Techniques Overview</span></span>](property-animation-techniques-overview.md)
- [<span data-ttu-id="34995-111">ストーリーボードの概要</span><span class="sxs-lookup"><span data-stu-id="34995-111">Storyboards Overview</span></span>](storyboards-overview.md)
