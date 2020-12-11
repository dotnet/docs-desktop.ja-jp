---
title: '方法: Tab キーで ToolStrip コントロールから移動できるようにする'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], moving between
- TAB key [Windows Forms], enabling
- ToolStrip control [Windows Forms], moving from
ms.assetid: 40f9e88b-09a3-428e-8da8-c00bb65079c6
ms.openlocfilehash: 7fee9f685b9a9b402cbfe9c265669f7905434986
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980800"
---
# <a name="how-to-enable-the-tab-key-to-move-out-of-a-toolstrip-control"></a><span data-ttu-id="6e72e-102">方法: Tab キーで ToolStrip コントロールから移動できるようにする</span><span class="sxs-lookup"><span data-stu-id="6e72e-102">How to: Enable the TAB Key to Move Out of a ToolStrip Control</span></span>
<span data-ttu-id="6e72e-103">次の手順を使用して、ユーザーが tab キーを押してからタブオーダーの次のコントロールに移動できるようにし <xref:System.Windows.Forms.ToolStrip> ます。</span><span class="sxs-lookup"><span data-stu-id="6e72e-103">Use the following procedure to enable the user to press the TAB key to move out of a <xref:System.Windows.Forms.ToolStrip> to the next control in the tab order.</span></span>  
  
 <span data-ttu-id="6e72e-104">は <xref:System.Windows.Forms.ToolStrip> tab キーの最初のキーを受け入れ、方向キーは内の項目を選択し <xref:System.Windows.Forms.ToolStrip> ます。</span><span class="sxs-lookup"><span data-stu-id="6e72e-104">The <xref:System.Windows.Forms.ToolStrip> accepts the first press of the TAB key, and the arrow keys select items within the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="6e72e-105">TAB キーをもう一度押すと、ユーザーがタブオーダーの次のコントロールに移動します。</span><span class="sxs-lookup"><span data-stu-id="6e72e-105">When the user presses the TAB key a second time, it takes the user to the next control in the tab order.</span></span>  
  
### <a name="to-enable-the-user-to-press-the-tab-key-to-move-out-of-a-toolstrip-to-the-next-control"></a><span data-ttu-id="6e72e-106">ユーザーが TAB キーを押して ToolStrip から次のコントロールに移動できるようにするには</span><span class="sxs-lookup"><span data-stu-id="6e72e-106">To enable the user to press the TAB key to move out of a ToolStrip to the next control</span></span>  
  
- <span data-ttu-id="6e72e-107"><xref:System.Windows.Forms.ToolStrip> の  の <xref:System.Windows.Forms.ToolStrip.TabStop%2A> プロパティを `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="6e72e-107">Set the <xref:System.Windows.Forms.ToolStrip.TabStop%2A> property of the <xref:System.Windows.Forms.ToolStrip> to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e72e-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e72e-108">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.TabStop%2A>
- [<span data-ttu-id="6e72e-109">ToolStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="6e72e-109">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
