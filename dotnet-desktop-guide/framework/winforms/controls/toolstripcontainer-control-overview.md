---
title: ToolStripContainer コントロールの概要
ms.date: 03/30/2017
f1_keywords:
- ToolStripContainer
helpviewer_keywords:
- toolbars [Windows Forms], built-in rafting
- ToolStripContainer control [Windows Forms], about ToolStripContainer control
ms.assetid: c7d63bff-64e2-4a63-bd89-d31bc96dacb8
ms.openlocfilehash: c279316c2a372a1498707b27ec8658813306304b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983847"
---
# <a name="toolstripcontainer-control-overview"></a><span data-ttu-id="a6eeb-102">ToolStripContainer コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="a6eeb-102">ToolStripContainer Control Overview</span></span>
<span data-ttu-id="a6eeb-103">には、 <xref:System.Windows.Forms.ToolStripContainer> 配置とラフティング <xref:System.Windows.Forms.ToolStrip> 、、およびコントロールの左、右、上、下側にパネルがあり <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.StatusStrip> ます。</span><span class="sxs-lookup"><span data-stu-id="a6eeb-103">A <xref:System.Windows.Forms.ToolStripContainer> has panels on its left, right, top, and bottom sides for positioning and rafting <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, and <xref:System.Windows.Forms.StatusStrip> controls.</span></span> <span data-ttu-id="a6eeb-104">複数の <xref:System.Windows.Forms.ToolStrip> コントロールを左右の <xref:System.Windows.Forms.ToolStripContainer> に配置すると、コントロールは垂直方向に積み重ねられます。</span><span class="sxs-lookup"><span data-stu-id="a6eeb-104">Multiple <xref:System.Windows.Forms.ToolStrip> controls stack vertically if you put them in the left or right <xref:System.Windows.Forms.ToolStripContainer>.</span></span> <span data-ttu-id="a6eeb-105">上または下の <xref:System.Windows.Forms.ToolStripContainer> に配置すると、コントロールは水平方向に積み重ねられます。</span><span class="sxs-lookup"><span data-stu-id="a6eeb-105">They stack horizontally if you put them in the top or bottom <xref:System.Windows.Forms.ToolStripContainer>.</span></span> <span data-ttu-id="a6eeb-106"><xref:System.Windows.Forms.ToolStripContainer> の中央の <xref:System.Windows.Forms.ToolStripContentPanel> を使用すると、従来のコントロールをフォーム上に配置できます。</span><span class="sxs-lookup"><span data-stu-id="a6eeb-106">You can use the central <xref:System.Windows.Forms.ToolStripContentPanel> of the <xref:System.Windows.Forms.ToolStripContainer> to position traditional controls on the form.</span></span>  
  
 <span data-ttu-id="a6eeb-107">一部または全部の <xref:System.Windows.Forms.ToolStripContainer> コントロールを、デザイン時に直接選択して削除できます。</span><span class="sxs-lookup"><span data-stu-id="a6eeb-107">Any or all <xref:System.Windows.Forms.ToolStripContainer> controls are directly selectable at design time and can be deleted.</span></span> <span data-ttu-id="a6eeb-108">の各パネル <xref:System.Windows.Forms.ToolStripContainer> は、展開および折りたたみが可能で、含まれるコントロールに合わせてサイズが変更されます。</span><span class="sxs-lookup"><span data-stu-id="a6eeb-108">Each panel of a <xref:System.Windows.Forms.ToolStripContainer> is expandable and collapsible, and resizes with the controls that it contains.</span></span>  
  
### <a name="important-toolstripcontainer-members"></a><span data-ttu-id="a6eeb-109">重要な ToolStripContainer メンバー</span><span class="sxs-lookup"><span data-stu-id="a6eeb-109">Important ToolStripContainer Members</span></span>  
  
|<span data-ttu-id="a6eeb-110">名前</span><span class="sxs-lookup"><span data-stu-id="a6eeb-110">Name</span></span>|<span data-ttu-id="a6eeb-111">説明</span><span class="sxs-lookup"><span data-stu-id="a6eeb-111">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripContainer.BottomToolStripPanel%2A>|<span data-ttu-id="a6eeb-112"><xref:System.Windows.Forms.ToolStripContainer> の下側パネルを取得します。</span><span class="sxs-lookup"><span data-stu-id="a6eeb-112">Gets the bottom panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.BottomToolStripPanelVisible%2A>|<span data-ttu-id="a6eeb-113"><xref:System.Windows.Forms.ToolStripContainer> の下パネルが表示されるかどうかを示す値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="a6eeb-113">Gets or sets a value indicating whether the bottom panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.LeftToolStripPanel%2A>|<span data-ttu-id="a6eeb-114"><xref:System.Windows.Forms.ToolStripContainer> の左パネルを取得します。</span><span class="sxs-lookup"><span data-stu-id="a6eeb-114">Gets the left panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.LeftToolStripPanelVisible%2A>|<span data-ttu-id="a6eeb-115"><xref:System.Windows.Forms.ToolStripContainer> の左パネルが表示されるかどうかを示す値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="a6eeb-115">Gets or sets a value indicating whether the left panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.RightToolStripPanel%2A>|<span data-ttu-id="a6eeb-116"><xref:System.Windows.Forms.ToolStripContainer> の右パネルを取得します。</span><span class="sxs-lookup"><span data-stu-id="a6eeb-116">Gets the right panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.RightToolStripPanelVisible%2A>|<span data-ttu-id="a6eeb-117"><xref:System.Windows.Forms.ToolStripContainer> の右パネルが表示されるかどうかを示す値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="a6eeb-117">Gets or sets a value indicating whether the right panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A>|<span data-ttu-id="a6eeb-118"><xref:System.Windows.Forms.ToolStripContainer> の上パネルを取得します。</span><span class="sxs-lookup"><span data-stu-id="a6eeb-118">Gets the top panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanelVisible%2A>|<span data-ttu-id="a6eeb-119"><xref:System.Windows.Forms.ToolStripContainer> の上パネルが表示されるかどうかを示す値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="a6eeb-119">Gets or sets a value indicating whether the top panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a6eeb-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="a6eeb-120">See also</span></span>

- <xref:System.Windows.Forms.ToolStripContainer>
- <xref:System.Windows.Forms.ToolStripContentPanel>
