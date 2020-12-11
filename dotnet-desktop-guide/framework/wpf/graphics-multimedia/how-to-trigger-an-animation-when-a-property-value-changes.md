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
# <a name="how-to-trigger-an-animation-when-a-property-value-changes"></a>方法: プロパティ値が変化したときにアニメーションをトリガーする
この例からは、<xref:System.Windows.Trigger> を使用し、プロパティ値が変わったときに <xref:System.Windows.Media.Animation.Storyboard> を開始する方法がわかります。 <xref:System.Windows.Style>、<xref:System.Windows.Controls.ControlTemplate>、<xref:System.Windows.DataTemplate> 内で <xref:System.Windows.Trigger> を使用できます。  
  
## <a name="example"></a>例  
 次の例では、<xref:System.Windows.Trigger> を使用し、その <xref:System.Windows.UIElement.IsMouseOver%2A> プロパティが `true` になったとき、<xref:System.Windows.Controls.Button> の <xref:System.Windows.UIElement.Opacity%2A> をアニメーション化します。  
  
 [!code-xaml[AnimatePropertyStoryboards#PropertyTriggerExample](~/samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/PropertyTriggerExample.xaml#propertytriggerexample)]  
  
 プロパティ <xref:System.Windows.Trigger> オブジェクトによって適用されたアニメーションは、<xref:System.Windows.EventTrigger> アニメーションや、<xref:System.Windows.Media.Animation.Storyboard> メソッドで始動するアニメーションより複雑に動作をします。  他の <xref:System.Windows.Trigger> オブジェクトによって定義されたアニメーションで "手渡し" しますが、<xref:System.Windows.EventTrigger> と、メソッドで始動するアニメーションで構成を行います。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Trigger>
- [プロパティ アニメーションの手法の概要](property-animation-techniques-overview.md)
- [ストーリーボードの概要](storyboards-overview.md)
