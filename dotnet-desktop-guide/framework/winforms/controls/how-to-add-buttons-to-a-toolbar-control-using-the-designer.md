---
title: '方法: デザイナーを使って ToolBar コントロールにボタンを追加する'
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding separators
- examples [Windows Forms], toolbars
- ToolBar control [Windows Forms], adding drop-down menus
ms.assetid: d9ce3040-3e21-4e2d-80ae-b430982b2db8
ms.openlocfilehash: 4d7a49633599aabc96153e4793e50c1a4d6d092d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981007"
---
# <a name="how-to-add-buttons-to-a-toolbar-control-using-the-designer"></a><span data-ttu-id="551b4-102">方法: デザイナーを使って ToolBar コントロールにボタンを追加する</span><span class="sxs-lookup"><span data-stu-id="551b4-102">How to: Add Buttons to a ToolBar Control Using the Designer</span></span>

> [!NOTE]
> <span data-ttu-id="551b4-103"><xref:System.Windows.Forms.ToolStrip> コントロールは、<xref:System.Windows.Forms.ToolBar> コントロールに代わると共に追加の機能を提供します。ただし、<xref:System.Windows.Forms.ToolBar> コントロールは、下位互換性を保つ目的および将来使用する目的で保持されます。</span><span class="sxs-lookup"><span data-stu-id="551b4-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ToolBar> control; however, the <xref:System.Windows.Forms.ToolBar> control is retained for both backward compatibility and future use, if you choose.</span></span>

<span data-ttu-id="551b4-104">コントロールの不可欠な部分 <xref:System.Windows.Forms.ToolBar> は、コントロールに追加するボタンです。</span><span class="sxs-lookup"><span data-stu-id="551b4-104">An integral part of the <xref:System.Windows.Forms.ToolBar> control is the buttons you add to it.</span></span> <span data-ttu-id="551b4-105">これらは、メニューコマンドに簡単にアクセスできるようにするために使用できます。また、アプリケーションのユーザーインターフェイスの別の領域に配置して、メニュー構造では使用できないコマンドをユーザーに公開することもできます。</span><span class="sxs-lookup"><span data-stu-id="551b4-105">These can be used to provide easy access to menu commands or, alternately, they can be placed in another area of the user interface of your application to expose commands to your users that are not available in the menu structure.</span></span>

<span data-ttu-id="551b4-106">次の手順では、コントロールを含むフォームを含む **Windows アプリケーション** プロジェクトが必要です <xref:System.Windows.Forms.ToolBar> 。</span><span class="sxs-lookup"><span data-stu-id="551b4-106">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ToolBar> control.</span></span> <span data-ttu-id="551b4-107">このようなプロジェクトの設定の詳細については、「 [方法: Windows フォームアプリケーションプロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project) する」および「 [方法: Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="551b4-107">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

### <a name="to-add-buttons-at-design-time"></a><span data-ttu-id="551b4-108">デザイン時にボタンを追加するには</span><span class="sxs-lookup"><span data-stu-id="551b4-108">To add buttons at design time</span></span>

1. <span data-ttu-id="551b4-109"><xref:System.Windows.Forms.ToolBar> コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="551b4-109">Select the <xref:System.Windows.Forms.ToolBar> control.</span></span>

2. <span data-ttu-id="551b4-110">[ **プロパティ** ] ウィンドウで、プロパティをクリックして選択し、 <xref:System.Windows.Forms.ToolBar.Buttons%2A> **省略記号** ([ ![ Visual Studio のプロパティウィンドウ] の省略記号ボタン ([...]) をクリックして ](./media/visual-studio-ellipsis-button.png) **ToolBarButton Collection エディター** を開きます。</span><span class="sxs-lookup"><span data-stu-id="551b4-110">In the **Properties** window, click the <xref:System.Windows.Forms.ToolBar.Buttons%2A> property to select it and click the **Ellipsis** (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button to open the **ToolBarButton Collection Editor**.</span></span>

3. <span data-ttu-id="551b4-111">コントロールのボタンを追加および削除するには、[ **追加** ] ボタンと [ **削除** ] ボタンを使用し <xref:System.Windows.Forms.ToolBar> ます。</span><span class="sxs-lookup"><span data-stu-id="551b4-111">Use the **Add** and **Remove** buttons to add and remove buttons from the <xref:System.Windows.Forms.ToolBar> control.</span></span>

4. <span data-ttu-id="551b4-112">エディターの右側のペインに表示される [ **プロパティ** ] ウィンドウで、個々のボタンのプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="551b4-112">Configure the properties of the individual buttons in the **Properties** window that appears in the pane on the right side of the editor.</span></span> <span data-ttu-id="551b4-113">次の表は、考慮する必要があるいくつかの重要なプロパティを示しています。</span><span class="sxs-lookup"><span data-stu-id="551b4-113">The following table shows some important properties to consider.</span></span>

    |<span data-ttu-id="551b4-114">プロパティ</span><span class="sxs-lookup"><span data-stu-id="551b4-114">Property</span></span>|<span data-ttu-id="551b4-115">説明</span><span class="sxs-lookup"><span data-stu-id="551b4-115">Description</span></span>|
    |--------------|-----------------|
    |<xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A>|<span data-ttu-id="551b4-116">ドロップダウンツールバーボタンに表示するメニューを設定します。</span><span class="sxs-lookup"><span data-stu-id="551b4-116">Sets the menu to be displayed in the drop-down toolbar button.</span></span> <span data-ttu-id="551b4-117">ツールバーボタンの <xref:System.Windows.Forms.ToolBarButton.Style%2A> プロパティをに設定する必要があり <xref:System.Windows.Forms.ToolBarButtonStyle.DropDownButton> ます。</span><span class="sxs-lookup"><span data-stu-id="551b4-117">The toolbar button's <xref:System.Windows.Forms.ToolBarButton.Style%2A> property must be set to <xref:System.Windows.Forms.ToolBarButtonStyle.DropDownButton>.</span></span> <span data-ttu-id="551b4-118">このプロパティは、クラスのインスタンスを <xref:System.Windows.Forms.ContextMenu> 参照として受け取ります。</span><span class="sxs-lookup"><span data-stu-id="551b4-118">This property takes an instance of the <xref:System.Windows.Forms.ContextMenu> class as a reference.</span></span>|
    |<xref:System.Windows.Forms.ToolBarButton.PartialPush%2A>|<span data-ttu-id="551b4-119">トグルスタイルのツールバーボタンを部分的にプッシュするかどうかを設定します。</span><span class="sxs-lookup"><span data-stu-id="551b4-119">Sets whether a toggle-style toolbar button is partially pushed.</span></span> <span data-ttu-id="551b4-120">ツールバーボタンの <xref:System.Windows.Forms.ToolBarButton.Style%2A> プロパティをに設定する必要があり <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton> ます。</span><span class="sxs-lookup"><span data-stu-id="551b4-120">The toolbar button's <xref:System.Windows.Forms.ToolBarButton.Style%2A> property must be set to <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton>.</span></span>|
    |<xref:System.Windows.Forms.ToolBarButton.Pushed%2A>|<span data-ttu-id="551b4-121">トグルスタイルのツールバーボタンが現在プッシュ状態になっているかどうかを設定します。</span><span class="sxs-lookup"><span data-stu-id="551b4-121">Sets whether a toggle-style toolbar button is currently in the pushed state.</span></span> <span data-ttu-id="551b4-122">ツールバーボタンの <xref:System.Windows.Forms.ToolBarButton.Style%2A> プロパティは、またはに設定する必要があり <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton> <xref:System.Windows.Forms.ToolBarButtonStyle.PushButton> ます。</span><span class="sxs-lookup"><span data-stu-id="551b4-122">The toolbar button's <xref:System.Windows.Forms.ToolBarButton.Style%2A> property must be set to <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton> or <xref:System.Windows.Forms.ToolBarButtonStyle.PushButton>.</span></span>|
    |<xref:System.Windows.Forms.ToolBarButton.Style%2A>|<span data-ttu-id="551b4-123">ツールバーボタンのスタイルを設定します。</span><span class="sxs-lookup"><span data-stu-id="551b4-123">Sets the style of the toolbar button.</span></span> <span data-ttu-id="551b4-124">列挙体の値のいずれかである必要があり <xref:System.Windows.Forms.ToolBarButtonStyle> ます。</span><span class="sxs-lookup"><span data-stu-id="551b4-124">Must be one of the values in the <xref:System.Windows.Forms.ToolBarButtonStyle> enumeration.</span></span>|
    |<xref:System.Windows.Forms.ToolBarButton.Text%2A>|<span data-ttu-id="551b4-125">ボタンによって表示されるテキスト文字列。</span><span class="sxs-lookup"><span data-stu-id="551b4-125">The text string displayed by the button.</span></span>|
    |<xref:System.Windows.Forms.ToolBarButton.ToolTipText%2A>|<span data-ttu-id="551b4-126">ボタンのツールヒントとして表示されるテキスト。</span><span class="sxs-lookup"><span data-stu-id="551b4-126">The text that appears as a ToolTip for the button.</span></span>|

5. <span data-ttu-id="551b4-127">[ **OK** ] をクリックしてダイアログボックスを閉じ、指定したパネルを作成します。</span><span class="sxs-lookup"><span data-stu-id="551b4-127">Click **OK** to close the dialog box and create the panels you specified.</span></span>

## <a name="see-also"></a><span data-ttu-id="551b4-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="551b4-128">See also</span></span>

- <xref:System.Windows.Forms.ToolBar>
- [<span data-ttu-id="551b4-129">方法: ツール バー ボタンのアイコンを定義する</span><span class="sxs-lookup"><span data-stu-id="551b4-129">How to: Define an Icon for a ToolBar Button</span></span>](how-to-define-an-icon-for-a-toolbar-button.md)
- [<span data-ttu-id="551b4-130">方法: ツール バー ボタンのメニュー イベントをトリガーする</span><span class="sxs-lookup"><span data-stu-id="551b4-130">How to: Trigger Menu Events for Toolbar Buttons</span></span>](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [<span data-ttu-id="551b4-131">ToolBar コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="551b4-131">ToolBar Control Overview</span></span>](toolbar-control-overview-windows-forms.md)
- [<span data-ttu-id="551b4-132">ToolBar コントロール</span><span class="sxs-lookup"><span data-stu-id="551b4-132">ToolBar Control</span></span>](toolbar-control-windows-forms.md)
