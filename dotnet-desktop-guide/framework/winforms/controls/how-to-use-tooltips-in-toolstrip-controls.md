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
# <a name="how-to-use-tooltips-in-toolstrip-controls"></a><span data-ttu-id="2091d-102">方法: ToolStrip コントロールにツールヒントを使用する</span><span class="sxs-lookup"><span data-stu-id="2091d-102">How to: Use ToolTips in ToolStrip Controls</span></span>
<span data-ttu-id="2091d-103"><xref:System.Windows.Forms.ToolTip> <xref:System.Windows.Forms.ToolStrip> コントロールのプロパティをに設定することによって、必要なコントロールのを表示でき <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> `true` ます。</span><span class="sxs-lookup"><span data-stu-id="2091d-103">You can display a <xref:System.Windows.Forms.ToolTip> for the <xref:System.Windows.Forms.ToolStrip> control you want by setting the control's <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property to `true`.</span></span>  
  
### <a name="to-display-a-tooltip"></a><span data-ttu-id="2091d-104">ツールヒントを表示するには</span><span class="sxs-lookup"><span data-stu-id="2091d-104">To display a ToolTip</span></span>  
  
- <span data-ttu-id="2091d-105"><xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>コントロールのプロパティをに設定 `true` します。</span><span class="sxs-lookup"><span data-stu-id="2091d-105">Set the <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property of the control to `true`.</span></span>  
  
     <span data-ttu-id="2091d-106">の既定値 <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType> は `true` で、との既定値 <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType> <xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType> は `false` です。</span><span class="sxs-lookup"><span data-stu-id="2091d-106">The default value of <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType> is `true`, and the default value of <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType> and <xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType> is `false`.</span></span>  
  
### <a name="to-use-the-tooltiptext-property-for-the-tooltip-text-of-a-toolstripbutton"></a><span data-ttu-id="2091d-107">ToolStripButton のツールヒントテキストに ToolTipText プロパティを使用するには</span><span class="sxs-lookup"><span data-stu-id="2091d-107">To use the ToolTipText property for the ToolTip text of a ToolStripButton</span></span>  
  
1. <span data-ttu-id="2091d-108"><xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>ボタンのプロパティをに設定 `true` します。</span><span class="sxs-lookup"><span data-stu-id="2091d-108">Set the <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property of the button to `true`.</span></span>  
  
2. <span data-ttu-id="2091d-109"><xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType>ボタンのプロパティをに設定 `false` します。</span><span class="sxs-lookup"><span data-stu-id="2091d-109">Set the <xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType> property of the button to `false`.</span></span>  
  
     <span data-ttu-id="2091d-110">`AutoToolTip`既定では、、、 `true` およびに対してプロパティが使用され <xref:System.Windows.Forms.ToolStripButton> <xref:System.Windows.Forms.ToolStripDropDownButton> <xref:System.Windows.Forms.ToolStripSplitButton> ます。</span><span class="sxs-lookup"><span data-stu-id="2091d-110">The `AutoToolTip` property is `true` by default for <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripDropDownButton>, and <xref:System.Windows.Forms.ToolStripSplitButton>.</span></span>  
  
     <span data-ttu-id="2091d-111">は、 <xref:System.Windows.Forms.ToolStripButton> `Text` 既定ではそのプロパティをテキストに使用 <xref:System.Windows.Forms.ToolTip> します。</span><span class="sxs-lookup"><span data-stu-id="2091d-111">A <xref:System.Windows.Forms.ToolStripButton> uses its `Text` property for the <xref:System.Windows.Forms.ToolTip> text by default.</span></span> <span data-ttu-id="2091d-112">でカスタムテキストを表示するには、次の手順に従い <xref:System.Windows.Forms.ToolStripButton> <xref:System.Windows.Forms.ToolTip> ます。</span><span class="sxs-lookup"><span data-stu-id="2091d-112">Use this procedure to display custom text in a <xref:System.Windows.Forms.ToolStripButton><xref:System.Windows.Forms.ToolTip>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2091d-113">をまたはに設定しても、 <xref:System.Windows.Forms.ToolStripItemDisplayStyle> <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image> ボタンにテキストは表示されませんが、ツールヒントは表示されます。</span><span class="sxs-lookup"><span data-stu-id="2091d-113">If you set <xref:System.Windows.Forms.ToolStripItemDisplayStyle> to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> or <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image>, no text will appear on the button, but the tool tip still appears.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2091d-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="2091d-114">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>
- <xref:System.Windows.Forms.ToolStripButton>
- <xref:System.Windows.Forms.ToolStripDropDownButton>
- <xref:System.Windows.Forms.ToolStripSplitButton>
- [<span data-ttu-id="2091d-115">ToolStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="2091d-115">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
