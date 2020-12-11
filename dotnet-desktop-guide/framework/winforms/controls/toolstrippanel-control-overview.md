---
title: ToolStripPanel コントロールの概要
ms.date: 03/30/2017
f1_keywords:
- ToolStripPanel
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripPanel control [Windows Forms], about ToolStripPanel control
ms.assetid: ce54a60c-5eba-4b4c-bd77-cf0748a666cc
ms.openlocfilehash: 154a1b77a9312b19fe8dd51a4f603f29a219ec50
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983840"
---
# <a name="toolstrippanel-control-overview"></a><span data-ttu-id="b9091-102">ToolStripPanel コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="b9091-102">ToolStripPanel Control Overview</span></span>

<span data-ttu-id="b9091-103">は、、 <xref:System.Windows.Forms.ToolStripPanel> 、およびの各コントロールを配置するための単一の領域を提供し <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.StatusStrip> ます。</span><span class="sxs-lookup"><span data-stu-id="b9091-103">A <xref:System.Windows.Forms.ToolStripPanel> provides a single area for positioning and rafting <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, and <xref:System.Windows.Forms.StatusStrip> controls.</span></span> <span data-ttu-id="b9091-104"><xref:System.Windows.Forms.ToolStrip>のに応じて、複数のコントロールが垂直方向または水平方向に積み重ね <xref:System.Windows.Forms.ToolStripPanelRow.Orientation%2A> <xref:System.Windows.Forms.ToolStripPanel> ます。</span><span class="sxs-lookup"><span data-stu-id="b9091-104">Multiple <xref:System.Windows.Forms.ToolStrip> controls stack vertically or horizontally depending on the <xref:System.Windows.Forms.ToolStripPanelRow.Orientation%2A> of the <xref:System.Windows.Forms.ToolStripPanel>.</span></span>  
  
### <a name="important-toolstrippanel-members"></a><span data-ttu-id="b9091-105">重要な ToolStripPanel メンバー</span><span class="sxs-lookup"><span data-stu-id="b9091-105">Important ToolStripPanel Members</span></span>  
  
|<span data-ttu-id="b9091-106">名前</span><span class="sxs-lookup"><span data-stu-id="b9091-106">Name</span></span>|<span data-ttu-id="b9091-107">説明</span><span class="sxs-lookup"><span data-stu-id="b9091-107">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripPanel.Orientation%2A>|<span data-ttu-id="b9091-108"><xref:System.Windows.Forms.ToolStripPanel> の向きが水平方向であるか垂直方向であるかを示す値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="b9091-108">Gets or sets a value indicating the horizontal or vertical orientation of the <xref:System.Windows.Forms.ToolStripPanel>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripPanel.Renderer%2A>|<span data-ttu-id="b9091-109"><xref:System.Windows.Forms.ToolStripRenderer> の外観のカスタマイズに使用する <xref:System.Windows.Forms.ToolStripPanel> を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="b9091-109">Gets or sets a <xref:System.Windows.Forms.ToolStripRenderer> used to customize the appearance of a <xref:System.Windows.Forms.ToolStripPanel>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripPanel.RenderMode%2A>|<span data-ttu-id="b9091-110"><xref:System.Windows.Forms.ToolStripPanel> に適用される描画スタイルを取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="b9091-110">Gets or sets the painting styles to be applied to the <xref:System.Windows.Forms.ToolStripPanel>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripPanel.RowMargin%2A>|<span data-ttu-id="b9091-111">との間隔をピクセル単位で取得または設定し <xref:System.Windows.Forms.ToolStripPanelRow> <xref:System.Windows.Forms.ToolStripPanel> ます。</span><span class="sxs-lookup"><span data-stu-id="b9091-111">Gets or sets the spacing, in pixels, between the <xref:System.Windows.Forms.ToolStripPanelRow> and the <xref:System.Windows.Forms.ToolStripPanel>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripPanel.Rows%2A>|<span data-ttu-id="b9091-112">こののを取得し <xref:System.Windows.Forms.ToolStripPanelRow> <xref:System.Windows.Forms.ToolStripPanel> ます。</span><span class="sxs-lookup"><span data-stu-id="b9091-112">Gets the <xref:System.Windows.Forms.ToolStripPanelRow> in this <xref:System.Windows.Forms.ToolStripPanel>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripPanel.Join%2A>|<span data-ttu-id="b9091-113"><xref:System.Windows.Forms.ToolStrip> を <xref:System.Windows.Forms.ToolStripPanel> に追加します。</span><span class="sxs-lookup"><span data-stu-id="b9091-113">Adds a <xref:System.Windows.Forms.ToolStrip> to a <xref:System.Windows.Forms.ToolStripPanel>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b9091-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="b9091-114">See also</span></span>

- <xref:System.Windows.Forms.ToolStripContainer>
- <xref:System.Windows.Forms.ToolStripContentPanel>
- <span data-ttu-id="b9091-115">[ToolStrip サンプル](/previous-versions/visualstudio/visual-studio-2008/ms181005(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="b9091-115">[ToolStrip Sample](/previous-versions/visualstudio/visual-studio-2008/ms181005(v=vs.90))</span></span>
