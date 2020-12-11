---
title: ToolBar のスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], ToolBar
- styles [WPF], ToolBar
- ControlTemplate [WPF], ToolBar
- parts [WPF], ToolBar
- ToolBar [WPF], styles and templates
- templates [WPF], ToolBar
ms.assetid: bd875f46-4690-46f5-81e0-f11a9822484f
ms.openlocfilehash: 1ece74e1c4aa1be9845bd812b29f2ad7f580d4e2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983567"
---
# <a name="toolbar-styles-and-templates"></a><span data-ttu-id="ad934-102">ToolBar のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="ad934-102">ToolBar Styles and Templates</span></span>
<span data-ttu-id="ad934-103">このトピックでは、<xref:System.Windows.Controls.ToolBar> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ad934-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ToolBar> control.</span></span> <span data-ttu-id="ad934-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="ad934-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="ad934-105">詳細については、「[コントロールのためにテンプレートを作成する](/dotnet/desktop-wpf/themes/how-to-create-apply-template)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ad934-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>  
  
## <a name="toolbar-parts"></a><span data-ttu-id="ad934-106">ToolBar のパーツ</span><span class="sxs-lookup"><span data-stu-id="ad934-106">ToolBar Parts</span></span>  
 <span data-ttu-id="ad934-107">次の表は、<xref:System.Windows.Controls.ToolBar> コントロールの名前付きパーツの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="ad934-107">The following table lists the named parts for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
|<span data-ttu-id="ad934-108">パーツ</span><span class="sxs-lookup"><span data-stu-id="ad934-108">Part</span></span>|<span data-ttu-id="ad934-109">種類</span><span class="sxs-lookup"><span data-stu-id="ad934-109">Type</span></span>|<span data-ttu-id="ad934-110">説明</span><span class="sxs-lookup"><span data-stu-id="ad934-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="ad934-111">PART_ToolBarPanel</span><span class="sxs-lookup"><span data-stu-id="ad934-111">PART_ToolBarPanel</span></span>|<xref:System.Windows.Controls.Primitives.ToolBarPanel>|<span data-ttu-id="ad934-112"><xref:System.Windows.Controls.ToolBar> 上のコントロールを格納するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ad934-112">The object that contains the controls on the <xref:System.Windows.Controls.ToolBar>.</span></span>|  
|<span data-ttu-id="ad934-113">PART_ToolBarOverflowPanel</span><span class="sxs-lookup"><span data-stu-id="ad934-113">PART_ToolBarOverflowPanel</span></span>|<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|<span data-ttu-id="ad934-114"><xref:System.Windows.Controls.ToolBar> のオーバーフロー領域にあるコントロールを格納するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ad934-114">The object that contains the controls that are in the overflow area of the <xref:System.Windows.Controls.ToolBar>.</span></span>|  
  
 <span data-ttu-id="ad934-115"><xref:System.Windows.Controls.ToolBar> の <xref:System.Windows.Controls.ControlTemplate> を作成する場合、テンプレートで、<xref:System.Windows.Controls.ScrollViewer> 内に <xref:System.Windows.Controls.ItemsPresenter> を含めることができます</span><span class="sxs-lookup"><span data-stu-id="ad934-115">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ToolBar>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="ad934-116">(<xref:System.Windows.Controls.ItemsPresenter> により、<xref:System.Windows.Controls.ToolBar> の各項目が表示されます。<xref:System.Windows.Controls.ScrollViewer> で、コントロール内のスクロールを有効にします)。</span><span class="sxs-lookup"><span data-stu-id="ad934-116">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ToolBar>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="ad934-117"><xref:System.Windows.Controls.ItemsPresenter> が <xref:System.Windows.Controls.ScrollViewer> の直接の子でない場合は、<xref:System.Windows.Controls.ItemsPresenter> に `ItemsPresenter` という名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad934-117">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="toolbar-states"></a><span data-ttu-id="ad934-118">ToolBar の状態</span><span class="sxs-lookup"><span data-stu-id="ad934-118">ToolBar States</span></span>  
 <span data-ttu-id="ad934-119">次の表は、<xref:System.Windows.Controls.ToolBar> コントロールの表示状態の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="ad934-119">The following table lists the visual states for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
|<span data-ttu-id="ad934-120">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="ad934-120">VisualState Name</span></span>|<span data-ttu-id="ad934-121">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="ad934-121">VisualStateGroup Name</span></span>|<span data-ttu-id="ad934-122">説明</span><span class="sxs-lookup"><span data-stu-id="ad934-122">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="ad934-123">有効</span><span class="sxs-lookup"><span data-stu-id="ad934-123">Valid</span></span>|<span data-ttu-id="ad934-124">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ad934-124">ValidationStates</span></span>|<span data-ttu-id="ad934-125">このコントロールで <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false` です。</span><span class="sxs-lookup"><span data-stu-id="ad934-125">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="ad934-126">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="ad934-126">InvalidFocused</span></span>|<span data-ttu-id="ad934-127">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ad934-127">ValidationStates</span></span>|<span data-ttu-id="ad934-128"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがある `true` です。</span><span class="sxs-lookup"><span data-stu-id="ad934-128">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="ad934-129">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="ad934-129">InvalidUnfocused</span></span>|<span data-ttu-id="ad934-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ad934-130">ValidationStates</span></span>|<span data-ttu-id="ad934-131"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがない `true` です。</span><span class="sxs-lookup"><span data-stu-id="ad934-131">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="toolbar-controltemplate-example"></a><span data-ttu-id="ad934-132">ToolBar の ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="ad934-132">ToolBar ControlTemplate Example</span></span>  
 <span data-ttu-id="ad934-133">次の例は、<xref:System.Windows.Controls.ToolBar> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="ad934-133">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ToolBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/toolbar.xaml#toolbar)]  
  
 <span data-ttu-id="ad934-134">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="ad934-134">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="ad934-135">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad934-135">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad934-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="ad934-136">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="ad934-137">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="ad934-137">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="ad934-138">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="ad934-138">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="ad934-139">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="ad934-139">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="ad934-140">コントロールのためのテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="ad934-140">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
