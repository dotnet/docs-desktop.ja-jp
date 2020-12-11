---
title: '方法: ContextMenuStrip のオープン イベントを処理する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ContextMenuStrip control [Windows Forms]
- context menus [Windows Forms], event handling
- ToolStrip control [Windows Forms]
- event handling [Windows Forms], context menus
- shortcut menus [Windows Forms], event handling
ms.assetid: b661b3dd-7815-4cc2-a1aa-a9a391ab3427
ms.openlocfilehash: 3001480959ef90cb31048cbcf70aeff1632979fb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982112"
---
# <a name="how-to-handle-the-contextmenustrip-opening-event"></a><span data-ttu-id="04b52-102">方法: ContextMenuStrip のオープン イベントを処理する</span><span class="sxs-lookup"><span data-stu-id="04b52-102">How to: Handle the ContextMenuStrip Opening Event</span></span>
<span data-ttu-id="04b52-103">イベントを処理することによって、コントロールの動作をカスタマイズでき <xref:System.Windows.Forms.ContextMenuStrip> <xref:System.Windows.Forms.ToolStripDropDown.Opening> ます。</span><span class="sxs-lookup"><span data-stu-id="04b52-103">You can customize the behavior of your <xref:System.Windows.Forms.ContextMenuStrip> control by handling the <xref:System.Windows.Forms.ToolStripDropDown.Opening> event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04b52-104">例</span><span class="sxs-lookup"><span data-stu-id="04b52-104">Example</span></span>  
 <span data-ttu-id="04b52-105">イベントを処理する方法を次のコード例に示し <xref:System.Windows.Forms.ToolStripDropDown.Opening> ます。</span><span class="sxs-lookup"><span data-stu-id="04b52-105">The following code example demonstrates how to handle the <xref:System.Windows.Forms.ToolStripDropDown.Opening> event.</span></span> <span data-ttu-id="04b52-106">イベントハンドラーは、コントロールに項目を動的に追加し <xref:System.Windows.Forms.ContextMenuStrip> ます。</span><span class="sxs-lookup"><span data-stu-id="04b52-106">The event handler adds items dynamically to a <xref:System.Windows.Forms.ContextMenuStrip> control.</span></span> <span data-ttu-id="04b52-107">完全なコード例については、「 [方法: ToolStrip 項目を動的に追加する](how-to-add-toolstrip-items-dynamically.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04b52-107">For the complete code example, see [How to: Add ToolStrip Items Dynamically](how-to-add-toolstrip-items-dynamically.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#42)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#42)]  
  
 <span data-ttu-id="04b52-108"><xref:System.ComponentModel.CancelEventArgs.Cancel%2A?displayProperty=nameWithType> `true` メニューが開かないようにするには、プロパティをに設定します。</span><span class="sxs-lookup"><span data-stu-id="04b52-108">Set the <xref:System.ComponentModel.CancelEventArgs.Cancel%2A?displayProperty=nameWithType> property to `true` to prevent the menu from opening.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04b52-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="04b52-109">See also</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.ComponentModel.CancelEventArgs.Cancel%2A>
- <xref:System.Windows.Forms.ToolStripDropDown>
- [<span data-ttu-id="04b52-110">ToolStrip コントロール</span><span class="sxs-lookup"><span data-stu-id="04b52-110">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
