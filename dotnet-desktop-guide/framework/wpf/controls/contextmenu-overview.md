---
title: ContextMenu の概要
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], ContextMenu
- ContextMenu controls [WPF], about ContextMenu controls
ms.assetid: 16909c42-799a-4561-91e0-7d69dcfeea91
ms.openlocfilehash: c9e63efb37c8847f27ca4b3616f6f1b5323ac3e5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984200"
---
# <a name="contextmenu-overview"></a><span data-ttu-id="5f9bd-102">ContextMenu の概要</span><span class="sxs-lookup"><span data-stu-id="5f9bd-102">ContextMenu Overview</span></span>
<span data-ttu-id="5f9bd-103"><xref:System.Windows.Controls.ContextMenu> クラスは、コンテキスト固有の <xref:System.Windows.Controls.Menu> を使用して機能を公開する要素を表します。</span><span class="sxs-lookup"><span data-stu-id="5f9bd-103">The <xref:System.Windows.Controls.ContextMenu> class represents the element that exposes functionality by using a context-specific <xref:System.Windows.Controls.Menu>.</span></span> <span data-ttu-id="5f9bd-104">通常、ユーザーはマウス ボタンを右クリックすることによって、[!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] に <xref:System.Windows.Controls.ContextMenu> を表示します。</span><span class="sxs-lookup"><span data-stu-id="5f9bd-104">Typically, a user exposes the <xref:System.Windows.Controls.ContextMenu> in the [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] by right-clicking the mouse button.</span></span> <span data-ttu-id="5f9bd-105">このトピックでは、<xref:System.Windows.Controls.ContextMenu> 要素について説明し、この要素を [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] とコードで使用する例を示します。</span><span class="sxs-lookup"><span data-stu-id="5f9bd-105">This topic introduces the <xref:System.Windows.Controls.ContextMenu> element and provides examples of how to use it in [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] and code.</span></span>  

<a name="contextmenu_control"></a>
## <a name="contextmenu-control"></a><span data-ttu-id="5f9bd-106">ContextMenu コントロール</span><span class="sxs-lookup"><span data-stu-id="5f9bd-106">ContextMenu Control</span></span>  
 <span data-ttu-id="5f9bd-107"><xref:System.Windows.Controls.ContextMenu> は特定のコントロールに結び付けられています。</span><span class="sxs-lookup"><span data-stu-id="5f9bd-107">A <xref:System.Windows.Controls.ContextMenu> is attached to a specific control.</span></span> <span data-ttu-id="5f9bd-108"><xref:System.Windows.Controls.ContextMenu> 要素を使用すると、<xref:System.Windows.Controls.Button> などの特定のコントロールに関連付けられているコマンドやオプションを指定する項目の一覧をユーザーに提供できます。</span><span class="sxs-lookup"><span data-stu-id="5f9bd-108">The <xref:System.Windows.Controls.ContextMenu> element enables you to present users with a list of items that specify commands or options that are associated with a particular control, for example, a <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="5f9bd-109">ユーザーがコントロールを右クリックすると、メニューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5f9bd-109">Users right-click the control to make the menu appear.</span></span> <span data-ttu-id="5f9bd-110">通常、<xref:System.Windows.Controls.MenuItem> をクリックすると、サブメニューが開かれるか、またはアプリケーションによってコマンドが実行されます。</span><span class="sxs-lookup"><span data-stu-id="5f9bd-110">Typically, clicking a <xref:System.Windows.Controls.MenuItem> opens a submenu or causes an application to carry out a command.</span></span>  
  
<a name="creating_contextmenus"></a>
## <a name="creating-contextmenus"></a><span data-ttu-id="5f9bd-111">ContextMenu の作成</span><span class="sxs-lookup"><span data-stu-id="5f9bd-111">Creating ContextMenus</span></span>  
 <span data-ttu-id="5f9bd-112">次の例では、サブメニューのある <xref:System.Windows.Controls.ContextMenu> を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5f9bd-112">The following examples show how to create a <xref:System.Windows.Controls.ContextMenu> with submenus.</span></span> <span data-ttu-id="5f9bd-113"><xref:System.Windows.Controls.ContextMenu> コントロールは、ボタン コントロールに結び付けられます。</span><span class="sxs-lookup"><span data-stu-id="5f9bd-113">The <xref:System.Windows.Controls.ContextMenu> controls are attached to button controls.</span></span>  
  
 [!code-xaml[ContextMenu#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml#1)]  
  
 [!code-csharp[ContextMenu#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ContextMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ContextMenu/VisualBasic/Pane1.xaml.vb#2)]  
  
<a name="applying_styles_to_contextmenu"></a>
## <a name="applying-styles-to-a-contextmenu"></a><span data-ttu-id="5f9bd-114">ContextMenu へのスタイルの適用</span><span class="sxs-lookup"><span data-stu-id="5f9bd-114">Applying Styles to a ContextMenu</span></span>  
 <span data-ttu-id="5f9bd-115"><xref:System.Windows.Style> コントロールを使用すると、カスタム コントロールを作成しなくても、<xref:System.Windows.Controls.ContextMenu> の外観と動作を大幅に変更できます。</span><span class="sxs-lookup"><span data-stu-id="5f9bd-115">By using a control <xref:System.Windows.Style>, you can dramatically change the appearance and behavior of a <xref:System.Windows.Controls.ContextMenu> without writing a custom control.</span></span> <span data-ttu-id="5f9bd-116">視覚プロパティの設定に加えて、コントロールの一部にスタイルを適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="5f9bd-116">In addition to setting visual properties, you can also apply styles to parts of a control.</span></span> <span data-ttu-id="5f9bd-117">たとえば、プロパティを使用してコントロールの一部の動作を変更したり、<xref:System.Windows.Controls.ContextMenu> に対するパーツの追加やレイアウトの変更を行ったりできます。</span><span class="sxs-lookup"><span data-stu-id="5f9bd-117">For example, you can change the behavior of parts of the control by using properties, or you can add parts to, or change the layout of, a <xref:System.Windows.Controls.ContextMenu>.</span></span> <span data-ttu-id="5f9bd-118">次の例では、<xref:System.Windows.Controls.ContextMenu> コントロールにスタイルを追加する方法をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="5f9bd-118">The following examples show several ways to add styles to <xref:System.Windows.Controls.ContextMenu> controls.</span></span>  
  
 <span data-ttu-id="5f9bd-119">最初の例では、`SimpleSysResources` という名前のスタイルを定義し、スタイルで現在のシステム設定を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5f9bd-119">The first example defines a style called `SimpleSysResources`, which shows how to use the current system settings in your style.</span></span> <span data-ttu-id="5f9bd-120">この例では、<xref:System.Windows.Controls.ContextMenu> の <xref:System.Windows.Controls.Control.Background%2A> の色として <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A> を割り当て、<xref:System.Windows.Controls.Control.Foreground%2A> の色として <xref:System.Windows.SystemColors.MenuTextBrushKey%2A> を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="5f9bd-120">The example assigns <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A> as the <xref:System.Windows.Controls.Control.Background%2A> color and <xref:System.Windows.SystemColors.MenuTextBrushKey%2A> as the <xref:System.Windows.Controls.Control.Foreground%2A> color of the <xref:System.Windows.Controls.ContextMenu>.</span></span>  
  
```xaml  
<Style x:Key="SimpleSysResources" TargetType="{x:Type MenuItem}">  
  <Setter Property = "Background" Value=
    "{DynamicResource {x:Static SystemColors.MenuHighlightBrushKey}}"/>  
  <Setter Property = "Foreground" Value=
    "{DynamicResource {x:Static SystemColors.MenuTextBrushKey}}"/>  
</Style>  
```  
  
 <span data-ttu-id="5f9bd-121">次の例では、<xref:System.Windows.Trigger> 要素を使用して、<xref:System.Windows.Controls.ContextMenu> で発生するイベントに応じて、<xref:System.Windows.Controls.Menu> の外観を変更します。</span><span class="sxs-lookup"><span data-stu-id="5f9bd-121">The following example uses the <xref:System.Windows.Trigger> element to change the appearance of a <xref:System.Windows.Controls.Menu> in response to events that are raised on the <xref:System.Windows.Controls.ContextMenu>.</span></span> <span data-ttu-id="5f9bd-122">ユーザーがメニューの上にマウスを移動すると、<xref:System.Windows.Controls.ContextMenu> 項目の外観が変わります。</span><span class="sxs-lookup"><span data-stu-id="5f9bd-122">When a user moves the mouse over the menu, the appearance of the <xref:System.Windows.Controls.ContextMenu> items changes.</span></span>  
  
```xaml  
<Style x:Key="Triggers" TargetType="{x:Type MenuItem}">  
  <Style.Triggers>  
    <Trigger Property="MenuItem.IsMouseOver" Value="true">  
      <Setter Property = "FontSize" Value="16"/>  
      <Setter Property = "FontStyle" Value="Italic"/>  
      <Setter Property = "Foreground" Value="Red"/>  
    </Trigger>  
  </Style.Triggers>  
</Style>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5f9bd-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="5f9bd-123">See also</span></span>

- <xref:System.Windows.Controls.ContextMenu>
- <xref:System.Windows.Style>
- <xref:System.Windows.Controls.Menu>
- <xref:System.Windows.Controls.MenuItem>
- [<span data-ttu-id="5f9bd-124">ContextMenu</span><span class="sxs-lookup"><span data-stu-id="5f9bd-124">ContextMenu</span></span>](contextmenu.md)
- [<span data-ttu-id="5f9bd-125">ContextMenu のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="5f9bd-125">ContextMenu Styles and Templates</span></span>](contextmenu-styles-and-templates.md)
- [<span data-ttu-id="5f9bd-126">WPF Controls Gallery Sample</span><span class="sxs-lookup"><span data-stu-id="5f9bd-126">WPF Controls Gallery Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)
