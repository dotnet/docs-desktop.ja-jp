---
title: '方法: ToolStrip オーバーフローを管理する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], managing overflow
- toolbars [Windows Forms], managing overflow
- examples [Windows Forms], toolbars
- CanOverflow property
ms.assetid: fa10e0ad-4cbf-4c0d-9082-359c2f855d4e
ms.openlocfilehash: 52cc02e626bee2d2457355028ecddc17e462d8fa
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974802"
---
# <a name="how-to-manage-toolstrip-overflow-in-windows-forms"></a><span data-ttu-id="e6b1f-102">方法 : Windows フォームの ToolStrip オーバーフローを管理する</span><span class="sxs-lookup"><span data-stu-id="e6b1f-102">How to: Manage ToolStrip Overflow in Windows Forms</span></span>

<span data-ttu-id="e6b1f-103">割り当てられた領域にコントロールのすべての項目が <xref:System.Windows.Forms.ToolStrip> 収まらない場合は、のオーバーフロー機能を有効に <xref:System.Windows.Forms.ToolStrip> し、特定ののオーバーフロー動作を決定することができ <xref:System.Windows.Forms.ToolStripItem> ます。</span><span class="sxs-lookup"><span data-stu-id="e6b1f-103">When all the items on a <xref:System.Windows.Forms.ToolStrip> control do not fit in the allotted space, you can enable overflow functionality on the <xref:System.Windows.Forms.ToolStrip> and determine the overflow behavior of specific <xref:System.Windows.Forms.ToolStripItem>s.</span></span>

<span data-ttu-id="e6b1f-104">指定された <xref:System.Windows.Forms.ToolStripItem> フォームの現在のサイズよりも多くの領域を必要とするを追加すると、が <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.ToolStripOverflowButton> 自動的にに表示され <xref:System.Windows.Forms.ToolStrip> ます。</span><span class="sxs-lookup"><span data-stu-id="e6b1f-104">When you add <xref:System.Windows.Forms.ToolStripItem>s that require more space than is allotted to the <xref:System.Windows.Forms.ToolStrip> given the form's current size, a <xref:System.Windows.Forms.ToolStripOverflowButton> automatically appears on the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="e6b1f-105"><xref:System.Windows.Forms.ToolStripOverflowButton>が表示され、オーバーフローに対応する項目がドロップダウンオーバーフローメニューに移動します。</span><span class="sxs-lookup"><span data-stu-id="e6b1f-105">The <xref:System.Windows.Forms.ToolStripOverflowButton> appears, and overflow-enabled items are moved into the drop-down overflow menu.</span></span> <span data-ttu-id="e6b1f-106">これにより、 <xref:System.Windows.Forms.ToolStrip> さまざまなフォームサイズに合わせて項目を適切に調整する方法をカスタマイズし、優先順位を付けることができます。</span><span class="sxs-lookup"><span data-stu-id="e6b1f-106">This allows you to customize and prioritize how your <xref:System.Windows.Forms.ToolStrip> items properly adjust to different form sizes.</span></span> <span data-ttu-id="e6b1f-107">また、 <xref:System.Windows.Forms.ToolStripItem.Placement%2A> プロパティとプロパティ、およびイベントを使用して、項目がオーバーフローになったときの外観を変更することもでき <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType> <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> ます。</span><span class="sxs-lookup"><span data-stu-id="e6b1f-107">You can also change the appearance of your items when they fall into the overflow by using the <xref:System.Windows.Forms.ToolStripItem.Placement%2A> and <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType> properties and the <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> event.</span></span> <span data-ttu-id="e6b1f-108">デザイン時または実行時にフォームを拡大すると、 <xref:System.Windows.Forms.ToolStripItem> メインにより多くのが表示され、 <xref:System.Windows.Forms.ToolStrip> フォームのサイズを小さくするまではが表示されなくなる場合が <xref:System.Windows.Forms.ToolStripOverflowButton> あります。</span><span class="sxs-lookup"><span data-stu-id="e6b1f-108">If you enlarge the form at either design time or run time, more <xref:System.Windows.Forms.ToolStripItem>s can be displayed on the main <xref:System.Windows.Forms.ToolStrip> and the <xref:System.Windows.Forms.ToolStripOverflowButton> might even disappear until you decrease the size of the form.</span></span>

## <a name="to-enable-overflow-on-a-toolstrip-control"></a><span data-ttu-id="e6b1f-109">ToolStrip コントロールでオーバーフローを有効にするには</span><span class="sxs-lookup"><span data-stu-id="e6b1f-109">To enable overflow on a ToolStrip control</span></span>

- <span data-ttu-id="e6b1f-110">のプロパティがに設定されていないことを確認し <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> `false` <xref:System.Windows.Forms.ToolStrip> ます。</span><span class="sxs-lookup"><span data-stu-id="e6b1f-110">Ensure that the <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> property is not set to `false` for the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="e6b1f-111">既定値は、`True` です。</span><span class="sxs-lookup"><span data-stu-id="e6b1f-111">The default is `True`.</span></span>

     <span data-ttu-id="e6b1f-112"><xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>が `True` (既定値) の場合、 <xref:System.Windows.Forms.ToolStripItem> のコンテンツが <xref:System.Windows.Forms.ToolStripItem> 水平方向または垂直方向の高さを超えたときに、ドロップダウンオーバーフローメニューにが送信され <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.ToolStrip> ます。</span><span class="sxs-lookup"><span data-stu-id="e6b1f-112">When <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> is `True` (the default), a <xref:System.Windows.Forms.ToolStripItem> is sent to the drop-down overflow menu when the content of the <xref:System.Windows.Forms.ToolStripItem> exceeds the width of a horizontal <xref:System.Windows.Forms.ToolStrip> or the height of a vertical <xref:System.Windows.Forms.ToolStrip>.</span></span>

## <a name="to-specify-overflow-behavior-of-a-specific-toolstripitem"></a><span data-ttu-id="e6b1f-113">特定の ToolStripItem のオーバーフロー動作を指定するには</span><span class="sxs-lookup"><span data-stu-id="e6b1f-113">To specify overflow behavior of a specific ToolStripItem</span></span>

- <span data-ttu-id="e6b1f-114"><xref:System.Windows.Forms.ToolStripItem.Overflow%2A>のプロパティ <xref:System.Windows.Forms.ToolStripItem> を目的の値に設定します。</span><span class="sxs-lookup"><span data-stu-id="e6b1f-114">Set the <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> property of the <xref:System.Windows.Forms.ToolStripItem> to the desired value.</span></span> <span data-ttu-id="e6b1f-115">その可能性は `Always` 、、、 `Never` および `AsNeeded` です。</span><span class="sxs-lookup"><span data-stu-id="e6b1f-115">The possibilities are `Always`, `Never`, and `AsNeeded`.</span></span> <span data-ttu-id="e6b1f-116">既定値は、`AsNeeded` です。</span><span class="sxs-lookup"><span data-stu-id="e6b1f-116">The default is `AsNeeded`.</span></span>

    ```vb
    toolStripTextBox1.Overflow = _
    System.Windows.Forms.ToolStripItemOverflow.Never
    ```

    ```csharp
    toolStripTextBox1.Overflow = _
    System.Windows.Forms.ToolStripItemOverflow.Never;
    ```

## <a name="see-also"></a><span data-ttu-id="e6b1f-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="e6b1f-117">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripOverflowButton>
- <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [<span data-ttu-id="e6b1f-118">ToolStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="e6b1f-118">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="e6b1f-119">ToolStrip コントロールのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="e6b1f-119">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="e6b1f-120">ToolStrip テクノロジの概要</span><span class="sxs-lookup"><span data-stu-id="e6b1f-120">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
