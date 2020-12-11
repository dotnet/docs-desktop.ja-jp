---
title: ContextMenu のスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- templates [WPF], ContextMenu
- parts [WPF], ContextMenu
- ContextMenu [WPF], styles and templates
- styles [WPF], ContextMenu
- ControlTemplate [WPF], ContextMenu
- states [WPF], ContextMenu
ms.assetid: 342d1f17-c406-4f94-8f55-867c5f3ea511
ms.openlocfilehash: 0f168c440c804c543ee9923d0021677ac529d5e1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984195"
---
# <a name="contextmenu-styles-and-templates"></a><span data-ttu-id="f046f-102">ContextMenu のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="f046f-102">ContextMenu Styles and Templates</span></span>
<span data-ttu-id="f046f-103">このトピックでは、<xref:System.Windows.Controls.ContextMenu> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f046f-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ContextMenu> control.</span></span> <span data-ttu-id="f046f-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="f046f-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="f046f-105">詳細については、「[コントロールのためにテンプレートを作成する](/dotnet/desktop-wpf/themes/how-to-create-apply-template)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f046f-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>  
  
## <a name="contextmenu-parts"></a><span data-ttu-id="f046f-106">ContextMenu のパーツ</span><span class="sxs-lookup"><span data-stu-id="f046f-106">ContextMenu Parts</span></span>  
 <span data-ttu-id="f046f-107"><xref:System.Windows.Controls.ContextMenu> コントロールに名前付きパーツはありません。</span><span class="sxs-lookup"><span data-stu-id="f046f-107">The <xref:System.Windows.Controls.ContextMenu> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="f046f-108"><xref:System.Windows.Controls.ContextMenu> の <xref:System.Windows.Controls.ControlTemplate> を作成する場合、テンプレートで、<xref:System.Windows.Controls.ScrollViewer> 内に <xref:System.Windows.Controls.ItemsPresenter> を含めることができます</span><span class="sxs-lookup"><span data-stu-id="f046f-108">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ContextMenu>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="f046f-109">(<xref:System.Windows.Controls.ItemsPresenter> により、<xref:System.Windows.Controls.ContextMenu> の各項目が表示されます。<xref:System.Windows.Controls.ScrollViewer> で、コントロール内のスクロールを有効にします)。</span><span class="sxs-lookup"><span data-stu-id="f046f-109">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ContextMenu>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="f046f-110"><xref:System.Windows.Controls.ItemsPresenter> が <xref:System.Windows.Controls.ScrollViewer> の直接の子でない場合は、<xref:System.Windows.Controls.ItemsPresenter> に `ItemsPresenter` という名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="f046f-110">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="contextmenu-states"></a><span data-ttu-id="f046f-111">ContextMenu の状態</span><span class="sxs-lookup"><span data-stu-id="f046f-111">ContextMenu States</span></span>  
 <span data-ttu-id="f046f-112">次の表は、<xref:System.Windows.Controls.ContextMenu> コントロールの表示状態の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="f046f-112">The following table lists the visual states for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
|<span data-ttu-id="f046f-113">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="f046f-113">VisualState Name</span></span>|<span data-ttu-id="f046f-114">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="f046f-114">VisualStateGroup Name</span></span>|<span data-ttu-id="f046f-115">説明</span><span class="sxs-lookup"><span data-stu-id="f046f-115">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="f046f-116">有効</span><span class="sxs-lookup"><span data-stu-id="f046f-116">Valid</span></span>|<span data-ttu-id="f046f-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f046f-117">ValidationStates</span></span>|<span data-ttu-id="f046f-118">このコントロールで <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false` です。</span><span class="sxs-lookup"><span data-stu-id="f046f-118">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="f046f-119">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="f046f-119">InvalidFocused</span></span>|<span data-ttu-id="f046f-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f046f-120">ValidationStates</span></span>|<span data-ttu-id="f046f-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがある `true` です。</span><span class="sxs-lookup"><span data-stu-id="f046f-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="f046f-122">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="f046f-122">InvalidUnfocused</span></span>|<span data-ttu-id="f046f-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f046f-123">ValidationStates</span></span>|<span data-ttu-id="f046f-124"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがない `true` です。</span><span class="sxs-lookup"><span data-stu-id="f046f-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="contextmenu-controltemplate-example"></a><span data-ttu-id="f046f-125">ContextMenu の ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="f046f-125">ContextMenu ControlTemplate Example</span></span>  
 <span data-ttu-id="f046f-126">次の例は、<xref:System.Windows.Controls.ContextMenu> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="f046f-126">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ContextMenu](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#contextmenu)]  
  
 <span data-ttu-id="f046f-127"><xref:System.Windows.Controls.ControlTemplate> では、次のリソースを使用します。</span><span class="sxs-lookup"><span data-stu-id="f046f-127">The <xref:System.Windows.Controls.ControlTemplate> uses the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="f046f-128">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f046f-128">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f046f-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="f046f-129">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="f046f-130">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="f046f-130">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="f046f-131">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="f046f-131">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="f046f-132">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="f046f-132">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="f046f-133">コントロールのためのテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="f046f-133">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
