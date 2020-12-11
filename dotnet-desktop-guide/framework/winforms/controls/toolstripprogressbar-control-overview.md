---
title: ToolStripProgressBar コントロールの概要
ms.date: 03/30/2017
f1_keywords:
- ToolStripProgressBar
helpviewer_keywords:
- toolbars [Windows Forms], progress bars
- progress controls [Windows Forms]
- ToolStripProgressBar control [Windows Forms], about ToolStripProgressBar control
ms.assetid: ec3ab522-5fe4-4b4d-a551-bc19e84f4774
ms.openlocfilehash: 380dabe2468ae3c7d9d7303498823d847a8d119e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983835"
---
# <a name="toolstripprogressbar-control-overview"></a><span data-ttu-id="23f79-102">ToolStripProgressBar コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="23f79-102">ToolStripProgressBar Control Overview</span></span>
<span data-ttu-id="23f79-103">は、 <xref:System.Windows.Forms.ToolStripProgressBar> すべてのコントロールのラフティングおよびレンダリング機能と、 <xref:System.Windows.Forms.ToolStrip> 一般的なプロセス追跡機能を組み合わせたものです。</span><span class="sxs-lookup"><span data-stu-id="23f79-103">The <xref:System.Windows.Forms.ToolStripProgressBar> combines the rafting and rendering functionality of all <xref:System.Windows.Forms.ToolStrip> controls with its typical process-tracking functionality.</span></span> <span data-ttu-id="23f79-104">は、通常、に <xref:System.Windows.Forms.ToolStripProgressBar> よってホストされ、ではあまり頻繁にホストされ <xref:System.Windows.Forms.StatusStrip> <xref:System.Windows.Forms.ToolStrip> ません。</span><span class="sxs-lookup"><span data-stu-id="23f79-104">A <xref:System.Windows.Forms.ToolStripProgressBar> is most usually hosted by <xref:System.Windows.Forms.StatusStrip>, and less frequently by a <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
 <span data-ttu-id="23f79-105"><xref:System.Windows.Forms.ToolStripProgressBar>は、以前のバージョンのコントロールに代わる機能を追加して <xref:System.Windows.Forms.ToolStripProgressBar> いますが、必要に応じて、下位互換性と将来の使用の両方のために保持されています。</span><span class="sxs-lookup"><span data-stu-id="23f79-105">Although <xref:System.Windows.Forms.ToolStripProgressBar> replaces and adds functionality to the control in previous versions, <xref:System.Windows.Forms.ToolStripProgressBar> is retained for both backward compatibility and future use if desired.</span></span>  
  
### <a name="important-toolstripprogressbar-members"></a><span data-ttu-id="23f79-106">重要な ToolStripProgressBar メンバー</span><span class="sxs-lookup"><span data-stu-id="23f79-106">Important ToolStripProgressBar Members</span></span>  
  
|<span data-ttu-id="23f79-107">名前</span><span class="sxs-lookup"><span data-stu-id="23f79-107">Name</span></span>|<span data-ttu-id="23f79-108">説明</span><span class="sxs-lookup"><span data-stu-id="23f79-108">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripProgressBar.MarqueeAnimationSpeed%2A>|<span data-ttu-id="23f79-109"><xref:System.Windows.Forms.ProgressBarStyle.Marquee> の表示のそれぞれの更新の間隔をミリ秒単位で表す値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="23f79-109">Gets or sets a value representing the delay between each <xref:System.Windows.Forms.ProgressBarStyle.Marquee> display update, in milliseconds.</span></span>|  
|<xref:System.Windows.Forms.ProgressBar.Maximum%2A>|<span data-ttu-id="23f79-110">この <xref:System.Windows.Forms.ToolStripProgressBar> に対して定義される範囲の上限を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="23f79-110">Gets or sets the upper bound of the range that is defined for this <xref:System.Windows.Forms.ToolStripProgressBar>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripProgressBar.Minimum%2A>|<span data-ttu-id="23f79-111">この <xref:System.Windows.Forms.ToolStripProgressBar> に対して定義される範囲の下限を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="23f79-111">Gets or sets the lower bound of the range that is defined for this <xref:System.Windows.Forms.ToolStripProgressBar>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripProgressBar.Style%2A>|<span data-ttu-id="23f79-112">が <xref:System.Windows.Forms.ToolStripProgressBar> 操作の進行状況を表示するために使用するスタイルを取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="23f79-112">Gets or sets the style that the <xref:System.Windows.Forms.ToolStripProgressBar> uses to display the progress of an operation.</span></span>|  
|<xref:System.Windows.Forms.ToolStripProgressBar.Value%2A>|<span data-ttu-id="23f79-113"><xref:System.Windows.Forms.ToolStripProgressBar> コントロールの現在の値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="23f79-113">Gets or sets the current value of the <xref:System.Windows.Forms.ToolStripProgressBar>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripProgressBar.PerformStep%2A>|<span data-ttu-id="23f79-114">プログレス バーの現在位置を <xref:System.Windows.Forms.ToolStripProgressBar.Step%2A> プロパティの値の分だけ進めます。</span><span class="sxs-lookup"><span data-stu-id="23f79-114">Advances the current position of the progress bar by the amount of the <xref:System.Windows.Forms.ToolStripProgressBar.Step%2A> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="23f79-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="23f79-115">See also</span></span>

- <xref:System.Windows.Forms.ToolStripProgressBar>
