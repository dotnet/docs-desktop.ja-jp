---
title: '方法: TextBox でカスタム コンテキスト メニューを使用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- context menus [WPF], custom
- menus [WPF], custom
- custom context menus [WPF]
- TextBox control [WPF], custom content menus
ms.assetid: 842d3cd5-6fa0-4be4-8d90-6c7466213b1c
ms.openlocfilehash: 93ee6d44e9e5703d70d0583b759330a9e52f60b9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982768"
---
# <a name="how-to-use-a-custom-context-menu-with-a-textbox"></a><span data-ttu-id="085c2-102">方法: TextBox でカスタム コンテキスト メニューを使用する</span><span class="sxs-lookup"><span data-stu-id="085c2-102">How to: Use a Custom Context Menu with a TextBox</span></span>
<span data-ttu-id="085c2-103">この例からは、<xref:System.Windows.Controls.TextBox> 用の単純なカスタム コンテキスト メニューを定義し、実装する方法がわかります。</span><span class="sxs-lookup"><span data-stu-id="085c2-103">This example shows how to define and implement a simple custom context menu for a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="085c2-104">例</span><span class="sxs-lookup"><span data-stu-id="085c2-104">Example</span></span>  
 <span data-ttu-id="085c2-105">次の [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] の例では、カスタム コンテキスト メニューを含む <xref:System.Windows.Controls.TextBox> コントロールが定義されます。</span><span class="sxs-lookup"><span data-stu-id="085c2-105">The following [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] example defines a <xref:System.Windows.Controls.TextBox> control that includes a custom context menu.</span></span>  
  
 <span data-ttu-id="085c2-106">このコンテキスト メニューは <xref:System.Windows.Controls.ContextMenu> 要素を利用して定義されています。</span><span class="sxs-lookup"><span data-stu-id="085c2-106">The context menu is defined using a <xref:System.Windows.Controls.ContextMenu> element.</span></span>  <span data-ttu-id="085c2-107">コンテキスト メニュー自体は一連の <xref:System.Windows.Controls.MenuItem> 要素と <xref:System.Windows.Controls.Separator> 要素で構成されています。</span><span class="sxs-lookup"><span data-stu-id="085c2-107">The context menu itself consists of a series of <xref:System.Windows.Controls.MenuItem> elements and <xref:System.Windows.Controls.Separator> elements.</span></span>  <span data-ttu-id="085c2-108">各 <xref:System.Windows.Controls.MenuItem> 要素によってコンテキスト メニューのコマンドが定義されます。<xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> 属性によって、メニュー コマンドの表示テキストが定義されます。<xref:System.Windows.Controls.MenuItem.Click> 属性によって、各メニュー項目のハンドラー メソッドが指定されます。</span><span class="sxs-lookup"><span data-stu-id="085c2-108">Each <xref:System.Windows.Controls.MenuItem> element defines a command in the context menu; the <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> attribute defines the display text for the menu command, and the <xref:System.Windows.Controls.MenuItem.Click> attribute specifies a handler method for each menu item.</span></span>  <span data-ttu-id="085c2-109"><xref:System.Windows.Controls.Separator> 要素は、前のメニュー項目とそれに続くメニュー項目の間に分割線を表示するだけのものです。</span><span class="sxs-lookup"><span data-stu-id="085c2-109">The <xref:System.Windows.Controls.Separator> element simply causes a separating line to be rendered between the previous and subsequent menu items.</span></span>  
  
 [!code-xaml[TextBox_ContextMenu#_TextBox_ContextMenuXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_ContextMenu/CSharp/Window1.xaml#_textbox_contextmenuxaml)]  
  
## <a name="example"></a><span data-ttu-id="085c2-110">例</span><span class="sxs-lookup"><span data-stu-id="085c2-110">Example</span></span>  
 <span data-ttu-id="085c2-111">次の例では、前のコンテキスト メニュー定義の実装コードと、コンテキスト メニューを有効にし、無効にするコードを示します。</span><span class="sxs-lookup"><span data-stu-id="085c2-111">The following example shows the implementation code for the preceding context menu definition, as well as the code that enables and disables the context menu.</span></span>  <span data-ttu-id="085c2-112"><xref:System.Windows.Controls.ContextMenu.Opened> イベントは、<xref:System.Windows.Controls.TextBox> の現在の状態に基づき、特定のコマンドの有効と無効を動的に切り替えるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="085c2-112">The <xref:System.Windows.Controls.ContextMenu.Opened> event is used to dynamically enable or disable certain commands depending on the current state of the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
 <span data-ttu-id="085c2-113">既定のコンテキスト メニューを復元するには、<xref:System.Windows.DependencyObject.ClearValue%2A> メソッドを使用し、<xref:System.Windows.FrameworkElement.ContextMenu%2A> プロパティの値を消去します。</span><span class="sxs-lookup"><span data-stu-id="085c2-113">To restore the default context menu, use the <xref:System.Windows.DependencyObject.ClearValue%2A> method to clear the value of the <xref:System.Windows.FrameworkElement.ContextMenu%2A> property.</span></span>  <span data-ttu-id="085c2-114">コンテキスト メニューを完全に無効にするには、<xref:System.Windows.FrameworkElement.ContextMenu%2A> プロパティを null 参照に設定します (Visual Basic の `Nothing`)。</span><span class="sxs-lookup"><span data-stu-id="085c2-114">To disable the context menu altogether, set the <xref:System.Windows.FrameworkElement.ContextMenu%2A> property to a null reference (`Nothing` in Visual Basic).</span></span>  
  
 [!code-csharp[TextBox_ContextMenu#_TextBox_ContextMenu](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_ContextMenu/CSharp/Window1.xaml.cs#_textbox_contextmenu)]
 [!code-vb[TextBox_ContextMenu#_TextBox_ContextMenu](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_ContextMenu/VisualBasic/Window1.xaml.vb#_textbox_contextmenu)]  
  
## <a name="see-also"></a><span data-ttu-id="085c2-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="085c2-115">See also</span></span>

- [<span data-ttu-id="085c2-116">コンテキスト メニューでスペル チェックを使用する</span><span class="sxs-lookup"><span data-stu-id="085c2-116">Use Spell Checking with a Context Menu</span></span>](how-to-use-spell-checking-with-a-context-menu.md)
- [<span data-ttu-id="085c2-117">TextBox の概要</span><span class="sxs-lookup"><span data-stu-id="085c2-117">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="085c2-118">RichTextBox の概要</span><span class="sxs-lookup"><span data-stu-id="085c2-118">RichTextBox Overview</span></span>](richtextbox-overview.md)
