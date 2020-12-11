---
title: '方法: ToolStrip を ToolStripContainer からフォームに移動する'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], parenting to forms
- Windows Forms, parenting ToolStrip controls
ms.assetid: a1c94a7f-6fc5-4e4c-84cf-ff11dc573d33
ms.openlocfilehash: c6519add6789485d41146633abb5e11f80913649
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980759"
---
# <a name="how-to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a><span data-ttu-id="534e5-102">方法: ToolStrip を ToolStripContainer からフォームに移動する</span><span class="sxs-lookup"><span data-stu-id="534e5-102">How to: Move a ToolStrip Out of a ToolStripContainer onto a Form</span></span>
<span data-ttu-id="534e5-103">をフォームに移動するには、次の手順に従い <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.ToolStripContainer> ます。</span><span class="sxs-lookup"><span data-stu-id="534e5-103">Use the following procedure to move a <xref:System.Windows.Forms.ToolStrip> out of a <xref:System.Windows.Forms.ToolStripContainer> onto a form.</span></span>

## <a name="to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a><span data-ttu-id="534e5-104">ToolStrip を ToolStripContainer からフォームに移動するには</span><span class="sxs-lookup"><span data-stu-id="534e5-104">To move a ToolStrip out of a ToolStripContainer onto a form</span></span>

1. <span data-ttu-id="534e5-105"><xref:System.Windows.Forms.ToolStrip>を選択します。</span><span class="sxs-lookup"><span data-stu-id="534e5-105">Select the <xref:System.Windows.Forms.ToolStrip>.</span></span>

2. <span data-ttu-id="534e5-106">CTRL キーを <xref:System.Windows.Forms.ToolStrip> 押しながら X キーを押してを切り取るか、を右クリック <xref:System.Windows.Forms.ToolStrip> してコンテキストメニューの [ **切り取り** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="534e5-106">Cut the <xref:System.Windows.Forms.ToolStrip> by pressing CTRL+X, or right-click the <xref:System.Windows.Forms.ToolStrip> and choose **Cut** from the context menu.</span></span>

3. <span data-ttu-id="534e5-107">フォームを選択します。</span><span class="sxs-lookup"><span data-stu-id="534e5-107">Select the form.</span></span>

4. <span data-ttu-id="534e5-108"><xref:System.Windows.Forms.ToolStrip>CTRL キーを押しながら V キーを押すか、[**編集**] メニューの [**貼り付け**] をクリックして、を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="534e5-108">Paste the <xref:System.Windows.Forms.ToolStrip> by pressing CTRL+V, or choose **Paste** from the **Edit** menu.</span></span>

5. <span data-ttu-id="534e5-109">の <xref:System.Windows.Forms.ToolStrip.Dock%2A> プロパティを <xref:System.Windows.Forms.ToolStrip> **Top** に設定します。</span><span class="sxs-lookup"><span data-stu-id="534e5-109">Set the <xref:System.Windows.Forms.ToolStrip.Dock%2A> property of the <xref:System.Windows.Forms.ToolStrip> to **Top**.</span></span>

## <a name="see-also"></a><span data-ttu-id="534e5-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="534e5-110">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripContainer>
- [<span data-ttu-id="534e5-111">ToolStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="534e5-111">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
