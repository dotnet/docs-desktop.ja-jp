---
title: ToolBar コントロール
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolBar control [Windows Forms]
ms.assetid: 6b40e9ce-6a7a-4784-bfc9-7f1d36b7462e
ms.openlocfilehash: 027c96bb49e9446244e4b08ba93c551ef043b3c0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974373"
---
# <a name="toolbar-control-windows-forms"></a><span data-ttu-id="68efc-102">ToolBar コントロール (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="68efc-102">ToolBar Control (Windows Forms)</span></span>
> [!NOTE]
> <span data-ttu-id="68efc-103"><xref:System.Windows.Forms.ToolStrip> コントロールは、`ToolBar` コントロールに代わると共に追加の機能を提供します。ただし、`ToolBar` コントロールは、下位互換性を保つ目的および将来使用する目的で保持されます。</span><span class="sxs-lookup"><span data-stu-id="68efc-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the `ToolBar` control; however, the `ToolBar` control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="68efc-104">Windows フォーム `ToolBar` コントロールは、コマンドをアクティブ化するドロップダウン メニューとビットマップのボタンの行を表示するコントロール バーとしてフォームを使用します。</span><span class="sxs-lookup"><span data-stu-id="68efc-104">The Windows Forms `ToolBar` control is used on forms as a control bar that displays a row of drop-down menus and bitmapped buttons that activate commands.</span></span> <span data-ttu-id="68efc-105">そのため、ツールバー ボタンのクリックは、メニュー コマンドと同じです。</span><span class="sxs-lookup"><span data-stu-id="68efc-105">Thus, clicking a toolbar button is equivalent to choosing a menu command.</span></span> <span data-ttu-id="68efc-106">ボタンは、プッシュ ボタン、ドロップダウン メニュー、または区切り記号として表示して機能するように構成できます。</span><span class="sxs-lookup"><span data-stu-id="68efc-106">The buttons can be configured to appear and behave as push buttons, drop-down menus, or separators.</span></span> <span data-ttu-id="68efc-107">通常、ツールバーには、アプリケーションのメニュー構造の項目に対応するボタンとメニューが含まれ、アプリケーションで最も頻繁に使用される関数やコマンドにすばやくアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="68efc-107">Typically, a toolbar contains buttons and menus that correspond to items in an application's menu structure, providing quick access to an application's most frequently used functions and commands.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="68efc-108">`ToolBar` コントロールの <xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A> プロパティは、<xref:System.Windows.Forms.ContextMenu> クラスのインスタンスを参照として取得します。</span><span class="sxs-lookup"><span data-stu-id="68efc-108">The `ToolBar` control's <xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A> property takes an instance of the <xref:System.Windows.Forms.ContextMenu> class as a reference.</span></span> <span data-ttu-id="68efc-109">このプロパティは <xref:System.Windows.Forms.Menu> クラスから継承する任意のオブジェクトを受け入れるため、アプリケーションのツールバーにこの種類のボタンを実装する場合は、渡す参照を慎重に検討してください。</span><span class="sxs-lookup"><span data-stu-id="68efc-109">Carefully consider the reference you pass when implementing this sort of button on toolbars in your application, as the property will accept any object that inherits from the <xref:System.Windows.Forms.Menu> class.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="68efc-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="68efc-110">In This Section</span></span>  
 [<span data-ttu-id="68efc-111">ToolBar コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="68efc-111">ToolBar Control Overview</span></span>](toolbar-control-overview-windows-forms.md)  
 <span data-ttu-id="68efc-112">ユーザーが操作できるカスタム ツールバーを設計できる、`ToolBar` コントロールの一般的な概念について説明します。</span><span class="sxs-lookup"><span data-stu-id="68efc-112">Introduces the general concepts of the `ToolBar` control, which allows you to design custom toolbars that your users can work with.</span></span>  
  
 [<span data-ttu-id="68efc-113">方法: ツール バー コントロールにボタンを追加する</span><span class="sxs-lookup"><span data-stu-id="68efc-113">How to: Add Buttons to a ToolBar Control</span></span>](how-to-add-buttons-to-a-toolbar-control.md)  
 <span data-ttu-id="68efc-114">ボタンを `ToolBar` コントロールに追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="68efc-114">Describes how to add buttons to a `ToolBar` control.</span></span>  
  
 [<span data-ttu-id="68efc-115">方法: ツール バー ボタンのアイコンを定義する</span><span class="sxs-lookup"><span data-stu-id="68efc-115">How to: Define an Icon for a ToolBar Button</span></span>](how-to-define-an-icon-for-a-toolbar-button.md)  
 <span data-ttu-id="68efc-116">アイコンを `ToolBar` コントロールのボタン内に表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="68efc-116">Describes how to display icons within a `ToolBar` control's buttons.</span></span>  
  
 [<span data-ttu-id="68efc-117">方法: ツール バー ボタンのメニュー イベントをトリガーする</span><span class="sxs-lookup"><span data-stu-id="68efc-117">How to: Trigger Menu Events for Toolbar Buttons</span></span>](how-to-trigger-menu-events-for-toolbar-buttons.md)  
 <span data-ttu-id="68efc-118">`ToolBar` コントロールでユーザーがクリックするボタンを解釈するコードの記述方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="68efc-118">Gives directions on writing code to interpret which button the user clicks in a `ToolBar` control.</span></span>  
  
 <span data-ttu-id="68efc-119">「 [方法: デザイナーを使用してツールバーのボタンのアイコンを定義](how-to-define-an-icon-for-a-toolbar-button-using-the-designer.md)する」、「 [方法: デザイナーを使用してツールバーコントロールにボタンを追加](how-to-add-buttons-to-a-toolbar-control-using-the-designer.md)する」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="68efc-119">Also see [How to: Define an Icon for a ToolBar Button Using the Designer](how-to-define-an-icon-for-a-toolbar-button-using-the-designer.md), [How to: Add Buttons to a ToolBar Control Using the Designer](how-to-add-buttons-to-a-toolbar-control-using-the-designer.md).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="68efc-120">リファレンス</span><span class="sxs-lookup"><span data-stu-id="68efc-120">Reference</span></span>  
 <span data-ttu-id="68efc-121"><xref:System.Windows.Forms.ToolBar> クラス</span><span class="sxs-lookup"><span data-stu-id="68efc-121"><xref:System.Windows.Forms.ToolBar> class</span></span>  
 <span data-ttu-id="68efc-122">クラスとそのメンバーに関するリファレンス情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="68efc-122">Provides reference information on the class and its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="68efc-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="68efc-123">Related Sections</span></span>  
 [<span data-ttu-id="68efc-124">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="68efc-124">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="68efc-125">Windows フォーム コントロールの完全な一覧を、使用に関する情報リンクと共に提供します。</span><span class="sxs-lookup"><span data-stu-id="68efc-125">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>  
  
 [<span data-ttu-id="68efc-126">ToolStrip コントロール</span><span class="sxs-lookup"><span data-stu-id="68efc-126">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)  
 <span data-ttu-id="68efc-127">Windows フォーム アプリケーションでメニュー、コントロール、およびユーザー コントロールをホストするツールバーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="68efc-127">Describes toolbars that can host menus, controls, and user controls in Windows Forms applications.</span></span>
