---
title: '方法: ToolStrip コントロールにツールヒントを使用する'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], adding tooltips
- toolbars [Windows Forms], adding tooltips
- tooltips [Windows Forms], adding
ms.assetid: c5d86024-a7c5-44ee-8b3f-2daf53d80d3e
ms.openlocfilehash: 3f383b6cccba7825637ea65a0e13280b91b406c9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983003"
---
# <a name="how-to-use-tooltips-in-toolstrip-controls"></a>方法: ToolStrip コントロールにツールヒントを使用する
<xref:System.Windows.Forms.ToolTip> <xref:System.Windows.Forms.ToolStrip> コントロールのプロパティをに設定することによって、必要なコントロールのを表示でき <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> `true` ます。  
  
### <a name="to-display-a-tooltip"></a>ツールヒントを表示するには  
  
- <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>コントロールのプロパティをに設定 `true` します。  
  
     の既定値 <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType> は `true` で、との既定値 <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType> <xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType> は `false` です。  
  
### <a name="to-use-the-tooltiptext-property-for-the-tooltip-text-of-a-toolstripbutton"></a>ToolStripButton のツールヒントテキストに ToolTipText プロパティを使用するには  
  
1. <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>ボタンのプロパティをに設定 `true` します。  
  
2. <xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType>ボタンのプロパティをに設定 `false` します。  
  
     `AutoToolTip`既定では、、、 `true` およびに対してプロパティが使用され <xref:System.Windows.Forms.ToolStripButton> <xref:System.Windows.Forms.ToolStripDropDownButton> <xref:System.Windows.Forms.ToolStripSplitButton> ます。  
  
     は、 <xref:System.Windows.Forms.ToolStripButton> `Text` 既定ではそのプロパティをテキストに使用 <xref:System.Windows.Forms.ToolTip> します。 でカスタムテキストを表示するには、次の手順に従い <xref:System.Windows.Forms.ToolStripButton> <xref:System.Windows.Forms.ToolTip> ます。  
  
> [!NOTE]
> をまたはに設定しても、 <xref:System.Windows.Forms.ToolStripItemDisplayStyle> <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image> ボタンにテキストは表示されませんが、ツールヒントは表示されます。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>
- <xref:System.Windows.Forms.ToolStripButton>
- <xref:System.Windows.Forms.ToolStripDropDownButton>
- <xref:System.Windows.Forms.ToolStripSplitButton>
- [ToolStrip コントロールの概要](toolstrip-control-overview-windows-forms.md)
