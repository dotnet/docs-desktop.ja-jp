---
title: '方法: マウス ポインターが ToolStripItem 上にあることを検出する'
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], detecting mouse movement
- ToolStrip control [Windows Forms], detecting mouse movement
- ToolStripItem class [Windows Forms], detecting mouse movement
- mouse [Windows Forms], detecting movement on toolbars
ms.assetid: d38b5082-aba7-4f6c-841b-bd9714e307fd
ms.openlocfilehash: f01a9acb3a566be40d65fb075c8487d4e9cb6e73
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980848"
---
# <a name="how-to-detect-when-the-mouse-pointer-is-over-a-toolstripitem"></a><span data-ttu-id="a23ee-102">方法: マウス ポインターが ToolStripItem 上にあることを検出する</span><span class="sxs-lookup"><span data-stu-id="a23ee-102">How to: Detect When the Mouse Pointer Is Over a ToolStripItem</span></span>
<span data-ttu-id="a23ee-103">マウスポインターがの上にあることを検出するには、次の手順に従い <xref:System.Windows.Forms.ToolStripItem> ます。</span><span class="sxs-lookup"><span data-stu-id="a23ee-103">Use the following procedure to detect when the mouse pointer is over a <xref:System.Windows.Forms.ToolStripItem>.</span></span>  
  
### <a name="to-detect-when-the-pointer-is-over-a-toolstripitem"></a><span data-ttu-id="a23ee-104">ToolStripItem の上にポインターがあることを検出するには</span><span class="sxs-lookup"><span data-stu-id="a23ee-104">To detect when the pointer is over a ToolStripItem</span></span>  
  
- <span data-ttu-id="a23ee-105"><xref:System.Windows.Forms.ToolStripItem.Selected%2A>がである項目のプロパティを使用し <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> `true` ます。</span><span class="sxs-lookup"><span data-stu-id="a23ee-105">Use the <xref:System.Windows.Forms.ToolStripItem.Selected%2A> property for items in which <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> is `true`.</span></span>  
  
     <span data-ttu-id="a23ee-106">これにより、イベントとイベントを同期する必要がなくなり <xref:System.Windows.Forms.ToolStripItem.MouseEnter> <xref:System.Windows.Forms.ToolStripItem.MouseLeave> ます。</span><span class="sxs-lookup"><span data-stu-id="a23ee-106">This will prevent you from having to synchronize the <xref:System.Windows.Forms.ToolStripItem.MouseEnter> and <xref:System.Windows.Forms.ToolStripItem.MouseLeave> events.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a23ee-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="a23ee-107">See also</span></span>

- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripItem.Selected%2A>
- [<span data-ttu-id="a23ee-108">ToolStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="a23ee-108">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
