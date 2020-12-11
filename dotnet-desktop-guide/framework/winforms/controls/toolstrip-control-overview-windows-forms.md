---
title: ToolStrip コントロールの概要
ms.date: 03/30/2017
f1_keywords:
- Toolstrip
helpviewer_keywords:
- ToolStrip control [Windows Forms], about ToolStrip control
- toolbars [Windows Forms], what's new in Windows Forms
- toolbars [Windows Forms]
- what's new [Windows Forms], toolbars
ms.assetid: 81d067ed-297c-4dad-90de-1bcac15336ec
ms.openlocfilehash: 931a6a0ea09f9b684b793c05cb1c3db8ee8fb7c7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983860"
---
# <a name="toolstrip-control-overview-windows-forms"></a><span data-ttu-id="49c09-102">ToolStrip コントロールの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="49c09-102">ToolStrip Control Overview (Windows Forms)</span></span>
<span data-ttu-id="49c09-103">Windows フォーム <xref:System.Windows.Forms.ToolStrip> コントロールとそれに関連付けられたクラスは、ユーザーインターフェイス要素をツールバー、ステータスバー、およびメニューに結合するための共通のフレームワークを提供します。</span><span class="sxs-lookup"><span data-stu-id="49c09-103">The Windows Forms <xref:System.Windows.Forms.ToolStrip> control and its associated classes provide a common framework for combining user interface elements into toolbars, status bars, and menus.</span></span> <span data-ttu-id="49c09-104"><xref:System.Windows.Forms.ToolStrip> コントロールは、埋め込み先のアクティベーションと編集、カスタムレイアウト、およびラフティングを含む豊富なデザイン時のエクスペリエンスを提供します。これは、水平方向または垂直方向のスペースを共有するためのツールバーの機能です。</span><span class="sxs-lookup"><span data-stu-id="49c09-104"><xref:System.Windows.Forms.ToolStrip> controls offer a rich design-time experience that includes in-place activation and editing, custom layout, and rafting, which is the ability of toolbars to share horizontal or vertical space.</span></span>  
  
 <span data-ttu-id="49c09-105"><xref:System.Windows.Forms.ToolStrip>は、以前のバージョンのコントロールに代わる機能を追加して <xref:System.Windows.Forms.ToolBar> いますが、必要に応じて、下位互換性と将来の使用の両方のために保持されています。</span><span class="sxs-lookup"><span data-stu-id="49c09-105">Although <xref:System.Windows.Forms.ToolStrip> replaces and adds functionality to the control in previous versions, <xref:System.Windows.Forms.ToolBar> is retained for both backward compatibility and future use if desired.</span></span>  
  
## <a name="features-of-the-toolstrip-controls"></a><span data-ttu-id="49c09-106">ToolStrip コントロールの機能</span><span class="sxs-lookup"><span data-stu-id="49c09-106">Features of the ToolStrip Controls</span></span>  
 <span data-ttu-id="49c09-107">コントロールを使用して <xref:System.Windows.Forms.ToolStrip> 次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="49c09-107">Use the <xref:System.Windows.Forms.ToolStrip> control to:</span></span>  
  
- <span data-ttu-id="49c09-108">コンテナー間で共通のユーザーインターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="49c09-108">Present a common user interface across containers.</span></span>  
  
- <span data-ttu-id="49c09-109">ドッキング、ラフティング、テキストとイメージを含むボタン、ドロップダウンボタンとコントロール、オーバーフローボタン、実行時の項目の並べ替えなど、高度なユーザーインターフェイスとレイアウト機能をサポートする、簡単にカスタマイズされたツールバーを作成し <xref:System.Windows.Forms.ToolStrip> ます。</span><span class="sxs-lookup"><span data-stu-id="49c09-109">Create easily customized, commonly employed toolbars that support advanced user interface and layout features, such as docking, rafting, buttons with text and images, drop-down buttons and controls, overflow buttons, and run-time reordering of <xref:System.Windows.Forms.ToolStrip> items.</span></span>  
  
- <span data-ttu-id="49c09-110">オーバーフローおよび実行時の項目の並べ替えをサポートします。</span><span class="sxs-lookup"><span data-stu-id="49c09-110">Support overflow and run-time item reordering.</span></span> <span data-ttu-id="49c09-111">オーバーフロー機能は、に表示する領域が不足しているときに、項目をドロップダウンメニューに移動し <xref:System.Windows.Forms.ToolStrip> ます。</span><span class="sxs-lookup"><span data-stu-id="49c09-111">The overflow feature moves items to a drop-down menu when there is not enough room to display them in a <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
- <span data-ttu-id="49c09-112">共通のレンダリングモデルを使用して、オペレーティングシステムの一般的な外観と動作をサポートします。</span><span class="sxs-lookup"><span data-stu-id="49c09-112">Support the typical appearance and behavior of the operating system through a common rendering model.</span></span>  
  
- <span data-ttu-id="49c09-113">他のコントロールのイベントを処理するのと同じ方法で、すべてのコンテナーと含まれる項目に対して一貫したイベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="49c09-113">Handle events consistently for all containers and contained items, in the same way you handle events for other controls.</span></span>  
  
- <span data-ttu-id="49c09-114">ある項目から別の項目 <xref:System.Windows.Forms.ToolStrip> または内の項目をドラッグし <xref:System.Windows.Forms.ToolStrip> ます。</span><span class="sxs-lookup"><span data-stu-id="49c09-114">Drag items from one <xref:System.Windows.Forms.ToolStrip> to another or within a <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
- <span data-ttu-id="49c09-115">で高度なレイアウトを使用して、ドロップダウンコントロールとユーザーインターフェイスの種類のエディターを作成 <xref:System.Windows.Forms.ToolStripDropDown> します。</span><span class="sxs-lookup"><span data-stu-id="49c09-115">Create drop-down controls and user interface type editors with advanced layouts in a <xref:System.Windows.Forms.ToolStripDropDown>.</span></span>  
  
 <span data-ttu-id="49c09-116">クラスを使用して <xref:System.Windows.Forms.ToolStripControlHost> 、の他のコントロールを使用し、そのコントロール <xref:System.Windows.Forms.ToolStrip> の機能を取得し <xref:System.Windows.Forms.ToolStrip> ます。</span><span class="sxs-lookup"><span data-stu-id="49c09-116">Use the <xref:System.Windows.Forms.ToolStripControlHost> class to use other controls on a <xref:System.Windows.Forms.ToolStrip> and gain <xref:System.Windows.Forms.ToolStrip> functionality for them.</span></span>  
  
 <span data-ttu-id="49c09-117">、、を使用して、およびの列挙体と共に機能を拡張し、外観と動作を変更することができ <xref:System.Windows.Forms.ToolStripRenderer> <xref:System.Windows.Forms.ToolStripProfessionalRenderer> <xref:System.Windows.Forms.ToolStripManager> <xref:System.Windows.Forms.ToolStripRenderMode> <xref:System.Windows.Forms.ToolStripManagerRenderMode> ます。</span><span class="sxs-lookup"><span data-stu-id="49c09-117">You can extend the functionality and modify the appearance and behavior by using the <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripProfessionalRenderer>, and <xref:System.Windows.Forms.ToolStripManager> along with the <xref:System.Windows.Forms.ToolStripRenderMode> and <xref:System.Windows.Forms.ToolStripManagerRenderMode> enumerations.</span></span>  
  
 <span data-ttu-id="49c09-118"><xref:System.Windows.Forms.ToolStrip>コントロールは、高度な構成と拡張が可能で、外観と動作をカスタマイズするための多数のプロパティ、メソッド、およびイベントが用意されています。</span><span class="sxs-lookup"><span data-stu-id="49c09-118">The <xref:System.Windows.Forms.ToolStrip> control is highly configurable and extensible, and it provides many properties, methods, and events to customize appearance and behavior.</span></span> <span data-ttu-id="49c09-119">注目すべきメンバーを次に示します。</span><span class="sxs-lookup"><span data-stu-id="49c09-119">Below are some noteworthy members:</span></span>  
  
### <a name="important-toolstrip-members"></a><span data-ttu-id="49c09-120">重要な ToolStrip メンバー</span><span class="sxs-lookup"><span data-stu-id="49c09-120">Important ToolStrip Members</span></span>  
  
|<span data-ttu-id="49c09-121">名前</span><span class="sxs-lookup"><span data-stu-id="49c09-121">Name</span></span>|<span data-ttu-id="49c09-122">説明</span><span class="sxs-lookup"><span data-stu-id="49c09-122">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStrip.Dock%2A>|<span data-ttu-id="49c09-123">がドッキングされている親コンテナーの端を取得または設定し <xref:System.Windows.Forms.ToolStrip> ます。</span><span class="sxs-lookup"><span data-stu-id="49c09-123">Gets or sets which edge of the parent container a <xref:System.Windows.Forms.ToolStrip> is docked to.</span></span>|  
|<xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>|<span data-ttu-id="49c09-124"><xref:System.Windows.Forms.ToolStrip> クラスがドラッグ アンド ドロップおよび項目の並べ替えをプライベートで処理するかどうかを示す値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="49c09-124">Gets or sets a value indicating whether drag-and-drop and item reordering are handled privately by the <xref:System.Windows.Forms.ToolStrip> class.</span></span>|  
|<xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A>|<span data-ttu-id="49c09-125">が項目をレイアウトする方法を示す値を取得または設定し <xref:System.Windows.Forms.ToolStrip> ます。</span><span class="sxs-lookup"><span data-stu-id="49c09-125">Gets or sets a value indicating how the <xref:System.Windows.Forms.ToolStrip> lays out its items.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItem.Overflow%2A>|<span data-ttu-id="49c09-126">がにアタッチされているかどうか、また <xref:System.Windows.Forms.ToolStripItem> <xref:System.Windows.Forms.ToolStrip> はこの <xref:System.Windows.Forms.ToolStripOverflowButton> 2 つの間で浮動小数点演算が可能かどうかを取得または設定します</span><span class="sxs-lookup"><span data-stu-id="49c09-126">Gets or sets whether a <xref:System.Windows.Forms.ToolStripItem> is attached to the <xref:System.Windows.Forms.ToolStrip> or <xref:System.Windows.Forms.ToolStripOverflowButton> or can float between the two.</span></span>|  
|<xref:System.Windows.Forms.ToolStrip.IsDropDown%2A>|<span data-ttu-id="49c09-127"><xref:System.Windows.Forms.ToolStripItem>がクリックされたときに、ドロップダウンリストに他の項目を表示するかどうかを示す値を取得し <xref:System.Windows.Forms.ToolStripItem> ます。</span><span class="sxs-lookup"><span data-stu-id="49c09-127">Gets a value indicating whether a <xref:System.Windows.Forms.ToolStripItem> displays other items in a drop-down list when the <xref:System.Windows.Forms.ToolStripItem> is clicked.</span></span>|  
|<xref:System.Windows.Forms.ToolStrip.OverflowButton%2A>|<span data-ttu-id="49c09-128">オーバーフローが有効な <xref:System.Windows.Forms.ToolStripItem> のオーバーフロー ボタンである <xref:System.Windows.Forms.ToolStrip> を取得します。</span><span class="sxs-lookup"><span data-stu-id="49c09-128">Gets the <xref:System.Windows.Forms.ToolStripItem> that is the overflow button for a <xref:System.Windows.Forms.ToolStrip> with overflow enabled.</span></span>|  
|<xref:System.Windows.Forms.ToolStrip.Renderer%2A>|<span data-ttu-id="49c09-129"><xref:System.Windows.Forms.ToolStripRenderer>の外観と動作 (ルックアンドフィール) をカスタマイズするために使用するを取得または設定し <xref:System.Windows.Forms.ToolStrip> ます。</span><span class="sxs-lookup"><span data-stu-id="49c09-129">Gets or sets a <xref:System.Windows.Forms.ToolStripRenderer> used to customize the appearance and behavior (look and feel) of a <xref:System.Windows.Forms.ToolStrip>.</span></span>|  
|<xref:System.Windows.Forms.ToolStrip.RenderMode%2A>|<span data-ttu-id="49c09-130"><xref:System.Windows.Forms.ToolStrip> に適用される描画スタイルを取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="49c09-130">Gets or sets the painting styles to be applied to the <xref:System.Windows.Forms.ToolStrip>.</span></span>|  
|<xref:System.Windows.Forms.ToolStrip.RendererChanged>|<span data-ttu-id="49c09-131"><xref:System.Windows.Forms.ToolStrip.Renderer%2A> プロパティが変更されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="49c09-131">Raised when the <xref:System.Windows.Forms.ToolStrip.Renderer%2A> property changes.</span></span>|  
  
 <span data-ttu-id="49c09-132"><xref:System.Windows.Forms.ToolStrip>コントロールの柔軟性は、多数のコンパニオンクラスを使用することによって実現されます。</span><span class="sxs-lookup"><span data-stu-id="49c09-132">The <xref:System.Windows.Forms.ToolStrip> control's flexibility is achieved through the use of a number of companion classes.</span></span> <span data-ttu-id="49c09-133">次に、最も注目すべき点をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="49c09-133">Below are some of the most noteworthy:</span></span>  
  
### <a name="important-toolstrip-companion-classes"></a><span data-ttu-id="49c09-134">重要な ToolStrip コンパニオンクラス</span><span class="sxs-lookup"><span data-stu-id="49c09-134">Important ToolStrip Companion Classes</span></span>  
  
|<span data-ttu-id="49c09-135">名前</span><span class="sxs-lookup"><span data-stu-id="49c09-135">Name</span></span>|<span data-ttu-id="49c09-136">説明</span><span class="sxs-lookup"><span data-stu-id="49c09-136">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip>|<span data-ttu-id="49c09-137">を置き換えて、機能をクラスに追加し <xref:System.Windows.Forms.MainMenu> ます。</span><span class="sxs-lookup"><span data-stu-id="49c09-137">Replaces and adds functionality to the <xref:System.Windows.Forms.MainMenu> class.</span></span>|  
|<xref:System.Windows.Forms.StatusStrip>|<span data-ttu-id="49c09-138">を置き換えて、機能をクラスに追加し <xref:System.Windows.Forms.StatusBar> ます。</span><span class="sxs-lookup"><span data-stu-id="49c09-138">Replaces and adds functionality to the <xref:System.Windows.Forms.StatusBar> class.</span></span>|  
|<xref:System.Windows.Forms.ContextMenuStrip>|<span data-ttu-id="49c09-139">を置き換えて、機能をクラスに追加し <xref:System.Windows.Forms.ContextMenu> ます。</span><span class="sxs-lookup"><span data-stu-id="49c09-139">Replaces and adds functionality to the <xref:System.Windows.Forms.ContextMenu> class.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItem>|<span data-ttu-id="49c09-140"><xref:System.Windows.Forms.ToolStrip>、 <xref:System.Windows.Forms.ToolStripControlHost> 、またはに格納できるすべての要素のイベントとレイアウトを管理する抽象基本クラス <xref:System.Windows.Forms.ToolStripDropDown> 。</span><span class="sxs-lookup"><span data-stu-id="49c09-140">Abstract base class that manages events and layout for all the elements that a <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripControlHost>, or <xref:System.Windows.Forms.ToolStripDropDown> can contain.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer>|<span data-ttu-id="49c09-141">さまざまな方法でコントロールを配置できるように、フォームの各辺にパネルを備えたコンテナーを提供します。</span><span class="sxs-lookup"><span data-stu-id="49c09-141">Provides a container with a panel on each side of the form in which controls can be arranged in various ways.</span></span>|  
|<xref:System.Windows.Forms.ToolStripRenderer>|<span data-ttu-id="49c09-142"><xref:System.Windows.Forms.ToolStrip> オブジェクトの描画機能を処理します。</span><span class="sxs-lookup"><span data-stu-id="49c09-142">Handles the painting functionality for <xref:System.Windows.Forms.ToolStrip> objects.</span></span>|  
|<xref:System.Windows.Forms.ToolStripProfessionalRenderer>|<span data-ttu-id="49c09-143">Microsoft Office スタイルの外観を提供します。</span><span class="sxs-lookup"><span data-stu-id="49c09-143">Provides Microsoft Office-style appearance.</span></span>|  
|<xref:System.Windows.Forms.ToolStripManager>|<span data-ttu-id="49c09-144"><xref:System.Windows.Forms.ToolStrip> のレンダリングとラフティング、および <xref:System.Windows.Forms.MenuStrip>、<xref:System.Windows.Forms.ToolStripDropDownMenu>、<xref:System.Windows.Forms.ToolStripMenuItem> の各オブジェクトのマージを制御します。</span><span class="sxs-lookup"><span data-stu-id="49c09-144">Controls <xref:System.Windows.Forms.ToolStrip> rendering and rafting, and the merging of <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ToolStripDropDownMenu>, and <xref:System.Windows.Forms.ToolStripMenuItem> objects.</span></span>|  
|<xref:System.Windows.Forms.ToolStripManagerRenderMode>|<span data-ttu-id="49c09-145">フォームに含まれる複数のオブジェクトに適用される描画スタイル (カスタム、Windows XP、または Microsoft Office Professional) を指定し <xref:System.Windows.Forms.ToolStrip> ます。</span><span class="sxs-lookup"><span data-stu-id="49c09-145">Specifies the painting style (custom, Windows XP, or Microsoft Office Professional) applied to multiple <xref:System.Windows.Forms.ToolStrip> objects contained in a form.</span></span>|  
|<xref:System.Windows.Forms.ToolStripRenderMode>|<span data-ttu-id="49c09-146">フォームに含まれる1つのオブジェクトに適用される描画スタイル (カスタム、Windows XP、または Microsoft Office Professional) を指定し <xref:System.Windows.Forms.ToolStrip> ます。</span><span class="sxs-lookup"><span data-stu-id="49c09-146">Specifies the painting style (custom, Windows XP, or Microsoft Office Professional) applied to one <xref:System.Windows.Forms.ToolStrip> object contained in a form.</span></span>|  
|<xref:System.Windows.Forms.ToolStripControlHost>|<span data-ttu-id="49c09-147">特に制御していないが、機能を必要とする他のコントロールをホスト <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.ToolStrip> します。</span><span class="sxs-lookup"><span data-stu-id="49c09-147">Hosts other controls that are not specifically <xref:System.Windows.Forms.ToolStrip> controls but for which you want <xref:System.Windows.Forms.ToolStrip> functionality.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItemPlacement>|<span data-ttu-id="49c09-148">をメインに配置するか、オーバーフローするか <xref:System.Windows.Forms.ToolStripItem> 、またはそのどちらでレイアウトするかを指定し <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.ToolStrip> ます。</span><span class="sxs-lookup"><span data-stu-id="49c09-148">Specifies whether a <xref:System.Windows.Forms.ToolStripItem> is to be laid out on the main <xref:System.Windows.Forms.ToolStrip>, on the overflow <xref:System.Windows.Forms.ToolStrip>, or neither.</span></span>|  
  
 <span data-ttu-id="49c09-149">詳細については、「 [Toolstrip テクノロジの概要](toolstrip-technology-summary.md) 」と「 [toolstrip コントロールアーキテクチャ](toolstrip-control-architecture.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49c09-149">For more information, see [ToolStrip Technology Summary](toolstrip-technology-summary.md) and [ToolStrip Control Architecture](toolstrip-control-architecture.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49c09-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="49c09-150">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
