---
title: メニューの概要
ms.date: 03/30/2017
helpviewer_keywords:
- Menu control [WPF]
- controls [WPF], Menu
ms.assetid: 67df6de5-db96-4c71-b752-af90729a6537
ms.openlocfilehash: 53bc8f10e61b6e4e9e1f3b9a484340d9e2ec2a85
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985723"
---
# <a name="menu-overview"></a><span data-ttu-id="f60c5-102">メニューの概要</span><span class="sxs-lookup"><span data-stu-id="f60c5-102">Menu Overview</span></span>
<span data-ttu-id="f60c5-103"><xref:System.Windows.Controls.Menu> クラスを使うと、コマンドおよびイベント ハンドラーに関連付けられている要素を階層順に整理できます。</span><span class="sxs-lookup"><span data-stu-id="f60c5-103">The <xref:System.Windows.Controls.Menu> class enables you to organize elements associated with commands and event handlers in a hierarchical order.</span></span> <span data-ttu-id="f60c5-104">各 <xref:System.Windows.Controls.Menu> 要素には、<xref:System.Windows.Controls.MenuItem> 要素のコレクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f60c5-104">Each <xref:System.Windows.Controls.Menu> element contains a collection of <xref:System.Windows.Controls.MenuItem> elements.</span></span>  

<a name="menu_control"></a>
## <a name="menu-control"></a><span data-ttu-id="f60c5-105">メニュー コントロール</span><span class="sxs-lookup"><span data-stu-id="f60c5-105">Menu Control</span></span>  
 <span data-ttu-id="f60c5-106"><xref:System.Windows.Controls.Menu> コントロールには、アプリケーションのコマンドまたはオプションを指定する項目の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f60c5-106">The <xref:System.Windows.Controls.Menu> control presents a list of items that specify commands or options for an application.</span></span> <span data-ttu-id="f60c5-107">通常、<xref:System.Windows.Controls.MenuItem> をクリックすると、サブメニューが開かれるか、またはアプリケーションによってコマンドが実行されます。</span><span class="sxs-lookup"><span data-stu-id="f60c5-107">Typically, clicking a <xref:System.Windows.Controls.MenuItem> opens a submenu or causes an application to carry out a command.</span></span>  
  
<a name="creating_menus"></a>
## <a name="creating-menus"></a><span data-ttu-id="f60c5-108">メニューの作成</span><span class="sxs-lookup"><span data-stu-id="f60c5-108">Creating Menus</span></span>  
 <span data-ttu-id="f60c5-109">次の例では、<xref:System.Windows.Controls.TextBox> のテキストを操作するための <xref:System.Windows.Controls.Menu> を作成します。</span><span class="sxs-lookup"><span data-stu-id="f60c5-109">The following example creates a <xref:System.Windows.Controls.Menu> to manipulate text in a <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="f60c5-110"><xref:System.Windows.Controls.Menu> に含まれる <xref:System.Windows.Controls.MenuItem> オブジェクトでは、<xref:System.Windows.Controls.MenuItem.Command%2A>、<xref:System.Windows.Controls.MenuItem.IsCheckable%2A>、<xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> の各プロパティと、<xref:System.Windows.Controls.MenuItem.Checked>、<xref:System.Windows.Controls.MenuItem.Unchecked>、<xref:System.Windows.Controls.MenuItem.Click> の各イベントが使用されます。</span><span class="sxs-lookup"><span data-stu-id="f60c5-110">The <xref:System.Windows.Controls.Menu> contains <xref:System.Windows.Controls.MenuItem> objects that use the <xref:System.Windows.Controls.MenuItem.Command%2A>, <xref:System.Windows.Controls.MenuItem.IsCheckable%2A>, and <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> properties and the <xref:System.Windows.Controls.MenuItem.Checked>, <xref:System.Windows.Controls.MenuItem.Unchecked>, and <xref:System.Windows.Controls.MenuItem.Click> events.</span></span>  
  
 [!code-xaml[MenuItemCommandsAndEvents#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml#1)]  
  
 [!code-csharp[MenuItemCommandsAndEvents#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml.cs#2)]
 [!code-vb[MenuItemCommandsAndEvents#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MenuItemCommandsAndEvents/VisualBasic/Window1.xaml.vb#2)]  
  
<a name="menus_with_shortcutkeys"></a>
## <a name="menuitems-with-keyboard-shortcuts"></a><span data-ttu-id="f60c5-111">キーボード ショートカット付きのメニュー項目</span><span class="sxs-lookup"><span data-stu-id="f60c5-111">MenuItems with Keyboard Shortcuts</span></span>  
 <span data-ttu-id="f60c5-112">キーボード ショートカットは、<xref:System.Windows.Controls.Menu> コマンドを呼び出すために、キーボードを使用して入力できる文字の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="f60c5-112">Keyboard shortcuts are character combinations that can be entered with the keyboard to invoke <xref:System.Windows.Controls.Menu> commands.</span></span> <span data-ttu-id="f60c5-113">たとえば、**コピー** のショートカットは CTRL+C です。</span><span class="sxs-lookup"><span data-stu-id="f60c5-113">For example, the shortcut for **Copy** is CTRL+C.</span></span> <span data-ttu-id="f60c5-114">キーボード ショートカットとメニュー項目で使用するプロパティは、<xref:System.Windows.Controls.MenuItem.InputGestureText%2A> または <xref:System.Windows.Controls.MenuItem.Command%2A> の 2 つです。</span><span class="sxs-lookup"><span data-stu-id="f60c5-114">There are two properties to use with keyboard shortcuts and menu items —<xref:System.Windows.Controls.MenuItem.InputGestureText%2A> or <xref:System.Windows.Controls.MenuItem.Command%2A>.</span></span>  
  
<a name="menus_inputgesturetext"></a>
### <a name="inputgesturetext"></a><span data-ttu-id="f60c5-115">InputGestureText</span><span class="sxs-lookup"><span data-stu-id="f60c5-115">InputGestureText</span></span>  
 <span data-ttu-id="f60c5-116">次の例では、<xref:System.Windows.Controls.MenuItem.InputGestureText%2A> プロパティを使用し、キーボード ショートカットのテキストを <xref:System.Windows.Controls.MenuItem> コントロールに割り当てる方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f60c5-116">The following example shows how to use the <xref:System.Windows.Controls.MenuItem.InputGestureText%2A> property to assign keyboard shortcut text to <xref:System.Windows.Controls.MenuItem> controls.</span></span> <span data-ttu-id="f60c5-117">これは、キーボード ショートカットをメニュー項目に配置するだけです。</span><span class="sxs-lookup"><span data-stu-id="f60c5-117">This only places the keyboard shortcut in the menu item.</span></span>  <span data-ttu-id="f60c5-118">コマンドと <xref:System.Windows.Controls.MenuItem> が関連付けられることはありません。</span><span class="sxs-lookup"><span data-stu-id="f60c5-118">It does not associate the command with the <xref:System.Windows.Controls.MenuItem>.</span></span> <span data-ttu-id="f60c5-119">アプリケーションでは、アクションを実行するために、ユーザーの入力を処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f60c5-119">The application must handle the user's input to carry out the action.</span></span>  
  
 [!code-xaml[MenuEvent#6](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#6)]  
  
<a name="menus_commands"></a>
### <a name="command"></a><span data-ttu-id="f60c5-120">コマンド</span><span class="sxs-lookup"><span data-stu-id="f60c5-120">Command</span></span>  
 <span data-ttu-id="f60c5-121">次の例では、<xref:System.Windows.Controls.MenuItem.Command%2A> プロパティを使用して、**開く** コマンドと **保存** コマンドを <xref:System.Windows.Controls.MenuItem> コントロールに関連付ける方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f60c5-121">The following example shows how to use the <xref:System.Windows.Controls.MenuItem.Command%2A> property to associate the **Open** and **Save** commands with <xref:System.Windows.Controls.MenuItem> controls.</span></span> <span data-ttu-id="f60c5-122">コマンドのプロパティでは、コマンドと <xref:System.Windows.Controls.MenuItem> が関連付けられるだけでなく、ショートカットとして使用する入力ジェスチャのテキストも提供されます。</span><span class="sxs-lookup"><span data-stu-id="f60c5-122">Not only does the command property associate a command with a <xref:System.Windows.Controls.MenuItem>, but it also supplies the input gesture text to use as a shortcut.</span></span>  
  
 [!code-xaml[MenuEvent#8](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#8)]  
  
 <span data-ttu-id="f60c5-123"><xref:System.Windows.Controls.MenuItem> クラスには <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> プロパティもあり、このプロパティではコマンドが発生する要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="f60c5-123">The <xref:System.Windows.Controls.MenuItem> class also has a <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> property, which specifies the element where the command occurs.</span></span> <span data-ttu-id="f60c5-124"><xref:System.Windows.Controls.MenuItem.CommandTarget%2A> が設定されていない場合は、キーボード フォーカスを持つ要素がコマンドを受信します。</span><span class="sxs-lookup"><span data-stu-id="f60c5-124">If <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> is not set, the element that has keyboard focus receives the command.</span></span> <span data-ttu-id="f60c5-125">コマンドの詳細については、[Commanding Overview](../advanced/commanding-overview.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f60c5-125">For more information about commands, see [Commanding Overview](../advanced/commanding-overview.md).</span></span>  
  
<a name="menu_styling"></a>
## <a name="menu-styling"></a><span data-ttu-id="f60c5-126">メニューのスタイル指定</span><span class="sxs-lookup"><span data-stu-id="f60c5-126">Menu Styling</span></span>  
 <span data-ttu-id="f60c5-127">コントロールのスタイル設定では、<xref:System.Windows.Controls.Menu> コントロールの動作と外観を大幅に変更できます。カスタム コントロールを作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f60c5-127">With control styling, you can dramatically change the appearance and behavior of <xref:System.Windows.Controls.Menu> controls without having to write a custom control.</span></span> <span data-ttu-id="f60c5-128">ビジュアル プロパティの設定の他、<xref:System.Windows.Style> をコントロールの各パーツに適用し、プロパティを使用してコントロールのパーツの動作を変更、パーツを追加またはコントロールのレイアウトを変更できます。</span><span class="sxs-lookup"><span data-stu-id="f60c5-128">In addition to setting visual properties, you can also apply a <xref:System.Windows.Style> to individual parts of a control, change the behavior of parts of the control through properties, or add additional parts or change the layout of a control.</span></span> <span data-ttu-id="f60c5-129">次の例では、<xref:System.Windows.Style> を <xref:System.Windows.Controls.Menu> コントロールに追加するいくつかの方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f60c5-129">The following examples demonstrate several ways to add a <xref:System.Windows.Style> to a <xref:System.Windows.Controls.Menu> control.</span></span>  
  
 <span data-ttu-id="f60c5-130">最初のコード例は、スタイルの現在のシステム設定を使用する方法を示す `Simple` という名前の <xref:System.Windows.Style> を定義します。</span><span class="sxs-lookup"><span data-stu-id="f60c5-130">The first code example defines a <xref:System.Windows.Style> called `Simple` that shows how to use the current system settings in your style.</span></span> <span data-ttu-id="f60c5-131">このコードは、`MenuHighlightBrush`の色をメニューの背景色として、 `MenuTextBrush`の色をメニューの前景色として割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f60c5-131">The code assigns the color of the `MenuHighlightBrush` as the menu's background color and the `MenuTextBrush` as the menu's foreground color.</span></span> <span data-ttu-id="f60c5-132">ブラシを割り当てるには、リソース キーを使用することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f60c5-132">Notice that you use resource keys to assign the brushes.</span></span>  
  
 [!code-xaml[MenuStylesSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#1)]  
  
 <span data-ttu-id="f60c5-133">次のサンプルでは、<xref:System.Windows.Controls.Menu> で発生したイベントに応じて <xref:System.Windows.Controls.MenuItem> の外観を変更できる <xref:System.Windows.Trigger> 要素が使用されています。</span><span class="sxs-lookup"><span data-stu-id="f60c5-133">The following sample uses <xref:System.Windows.Trigger> elements that enable you to change the appearance of a <xref:System.Windows.Controls.MenuItem> in response to events that occur on the <xref:System.Windows.Controls.Menu>.</span></span> <span data-ttu-id="f60c5-134"><xref:System.Windows.Controls.Menu> をポイントすると、メニュー項目の前景色およびフォント文字が変更されます。</span><span class="sxs-lookup"><span data-stu-id="f60c5-134">When you move the mouse over the <xref:System.Windows.Controls.Menu>, the foreground color and the font characteristics of the menu items change.</span></span>  
  
 [!code-xaml[MenuStylesSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#2)]  
  
## <a name="see-also"></a><span data-ttu-id="f60c5-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="f60c5-135">See also</span></span>

- [<span data-ttu-id="f60c5-136">WPF Controls Gallery Sample</span><span class="sxs-lookup"><span data-stu-id="f60c5-136">WPF Controls Gallery Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)
