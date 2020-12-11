---
title: StatusStrip コントロールの概要
ms.date: 03/30/2017
f1_keywords:
- StatusStrip
helpviewer_keywords:
- StatusStrip control [Windows Forms], about StatusStrip control
- status bars [Windows Forms], about status bars
ms.assetid: c0d9bcbb-f8b8-46ef-bae2-4146b8c8ce99
ms.openlocfilehash: 9f2426220e8fe0f13d2098de8975be2ad2e43845
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982431"
---
# <a name="statusstrip-control-overview"></a><span data-ttu-id="69fe9-102">StatusStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="69fe9-102">StatusStrip Control Overview</span></span>

<span data-ttu-id="69fe9-103"><xref:System.Windows.Forms.StatusStrip> コントロールには、<xref:System.Windows.Forms.Form> に表示されているオブジェクト、そのオブジェクトのコンポーネント、またはそのオブジェクトのアプリケーション内での操作に関連するコンテキストについての情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="69fe9-103">A <xref:System.Windows.Forms.StatusStrip> control displays information about an object being viewed on a <xref:System.Windows.Forms.Form>, the object's components, or contextual information that relates to that object's operation within your application.</span></span> <span data-ttu-id="69fe9-104">通常、<xref:System.Windows.Forms.StatusStrip> コントロールは <xref:System.Windows.Forms.ToolStripStatusLabel> オブジェクトで構成され、それら各オブジェクトに、テキスト、アイコン、またはその両方が表示されます。</span><span class="sxs-lookup"><span data-stu-id="69fe9-104">Typically, a <xref:System.Windows.Forms.StatusStrip> control consists of <xref:System.Windows.Forms.ToolStripStatusLabel> objects, each of which displays text, an icon, or both.</span></span> <span data-ttu-id="69fe9-105"><xref:System.Windows.Forms.StatusStrip> には、<xref:System.Windows.Forms.ToolStripDropDownButton>、<xref:System.Windows.Forms.ToolStripSplitButton>、および <xref:System.Windows.Forms.ToolStripProgressBar> の各コントロールを組み込むこともできます。</span><span class="sxs-lookup"><span data-stu-id="69fe9-105">The <xref:System.Windows.Forms.StatusStrip> can also contain <xref:System.Windows.Forms.ToolStripDropDownButton>, <xref:System.Windows.Forms.ToolStripSplitButton>, and <xref:System.Windows.Forms.ToolStripProgressBar> controls.</span></span>  
  
 <span data-ttu-id="69fe9-106">既定の <xref:System.Windows.Forms.StatusStrip> にはパネルがありません。</span><span class="sxs-lookup"><span data-stu-id="69fe9-106">The default <xref:System.Windows.Forms.StatusStrip> has no panels.</span></span> <span data-ttu-id="69fe9-107"><xref:System.Windows.Forms.StatusStrip> にパネルを追加するには、<xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A?displayProperty=nameWithType> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="69fe9-107">To add panels to a <xref:System.Windows.Forms.StatusStrip>, use the <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="69fe9-108"><xref:System.Windows.Forms.StatusStrip> 項目と一般的なコマンドの処理に対しては、Visual Studio に広範なサポートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="69fe9-108">There is extensive support for handling <xref:System.Windows.Forms.StatusStrip> items and common commands in Visual Studio.</span></span>  
  
 <span data-ttu-id="69fe9-109">「 [StatusStrip Items Collection Editor](/previous-versions/visualstudio/visual-studio-2010/ms233631(v=vs.100)) And [StatusStrip Tasks」](/previous-versions/visualstudio/visual-studio-2010/ms233642(v=vs.100))も参照してください。</span><span class="sxs-lookup"><span data-stu-id="69fe9-109">Also see [StatusStrip Items Collection Editor](/previous-versions/visualstudio/visual-studio-2010/ms233631(v=vs.100)) and [StatusStrip Tasks Dialog Box](/previous-versions/visualstudio/visual-studio-2010/ms233642(v=vs.100)).</span></span>  
  
 <span data-ttu-id="69fe9-110"><xref:System.Windows.Forms.StatusStrip> コントロールは、以前のバージョンの <xref:System.Windows.Forms.StatusBar> コントロールに代わると共に追加の機能を提供します。ただし、<xref:System.Windows.Forms.StatusBar> コントロールも、下位互換性を保つ目的および必要に応じて将来使用する目的で保持されます。</span><span class="sxs-lookup"><span data-stu-id="69fe9-110">Although <xref:System.Windows.Forms.StatusStrip> replaces and extends the <xref:System.Windows.Forms.StatusBar> control of previous versions, <xref:System.Windows.Forms.StatusBar> is retained for both backward compatibility and future use if you choose.</span></span>  
  
### <a name="important-statusstrip-members"></a><span data-ttu-id="69fe9-111">StatusStrip の重要なメンバー</span><span class="sxs-lookup"><span data-stu-id="69fe9-111">Important StatusStrip Members</span></span>  
  
|<span data-ttu-id="69fe9-112">名前</span><span class="sxs-lookup"><span data-stu-id="69fe9-112">Name</span></span>|<span data-ttu-id="69fe9-113">説明</span><span class="sxs-lookup"><span data-stu-id="69fe9-113">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.StatusStrip.CanOverflow%2A>|<span data-ttu-id="69fe9-114"><xref:System.Windows.Forms.StatusStrip> がオーバーフロー機能をサポートするかどうかを示す値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="69fe9-114">Gets or sets a value indicating whether the <xref:System.Windows.Forms.StatusStrip> supports overflow functionality.</span></span>|  
|<xref:System.Windows.Forms.StatusStrip.Stretch%2A>|<span data-ttu-id="69fe9-115"><xref:System.Windows.Forms.StatusStrip> を <xref:System.Windows.Forms.ToolStripContainer> 内で端から端まで拡大するかどうかを示す値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="69fe9-115">Gets or sets a value indicating whether the <xref:System.Windows.Forms.StatusStrip> stretches from end to end in its <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
  
### <a name="important-statusstrip-companion-classes"></a><span data-ttu-id="69fe9-116">StatusStrip の重要なコンパニオン クラス</span><span class="sxs-lookup"><span data-stu-id="69fe9-116">Important StatusStrip Companion Classes</span></span>  
  
|<span data-ttu-id="69fe9-117">名前</span><span class="sxs-lookup"><span data-stu-id="69fe9-117">Name</span></span>|<span data-ttu-id="69fe9-118">説明</span><span class="sxs-lookup"><span data-stu-id="69fe9-118">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripStatusLabel>|<span data-ttu-id="69fe9-119"><xref:System.Windows.Forms.StatusStrip> コントロールのパネルを表します。</span><span class="sxs-lookup"><span data-stu-id="69fe9-119">Represents a panel in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDownButton>|<span data-ttu-id="69fe9-120">関連付けられた <xref:System.Windows.Forms.ToolStripDropDown> を表示します。そこからユーザーは、単一の項目を選択できます。</span><span class="sxs-lookup"><span data-stu-id="69fe9-120">Displays an associated <xref:System.Windows.Forms.ToolStripDropDown> from which the user can select a single item.</span></span>|  
|<xref:System.Windows.Forms.ToolStripSplitButton>|<span data-ttu-id="69fe9-121">標準のボタンとドロップダウン メニューという 2 つの部分から成るコントロールを表します。</span><span class="sxs-lookup"><span data-stu-id="69fe9-121">Represents a two-part control that is a standard button and a drop-down menu.</span></span>|  
|<xref:System.Windows.Forms.ToolStripProgressBar>|<span data-ttu-id="69fe9-122">処理の完了状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="69fe9-122">Displays the completion state of a process.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="69fe9-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="69fe9-123">See also</span></span>

- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A>
