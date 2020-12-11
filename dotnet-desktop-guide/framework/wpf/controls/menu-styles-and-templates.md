---
title: メニューのスタイルとテンプレート
description: Windows Presentation Foundation の Menu コントロールのスタイルとテンプレートについて説明します。 ControlTemplate を変更して、コントロールに固有の外観を指定します。
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], Menu
- ControlTemplate [WPF], Menu
- Menu [WPF], styles and templates
- states [WPF], Menu
- templates [WPF], Menu
- parts [WPF], Menu
ms.assetid: b89da183-9b87-42c6-ac53-731a42c7b09e
ms.openlocfilehash: 94797afe923f15cda57ef103f3563ff486aadfc0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974614"
---
# <a name="menu-styles-and-templates"></a><span data-ttu-id="85ace-104">メニューのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="85ace-104">Menu Styles and Templates</span></span>
<span data-ttu-id="85ace-105">このトピックでは、<xref:System.Windows.Controls.Menu> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="85ace-105">This topic describes the styles and templates for the <xref:System.Windows.Controls.Menu> control.</span></span> <span data-ttu-id="85ace-106"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="85ace-106">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="85ace-107">詳細については、「[コントロールのためにテンプレートを作成する](/dotnet/desktop-wpf/themes/how-to-create-apply-template)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="85ace-107">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>  
  
## <a name="menu-parts"></a><span data-ttu-id="85ace-108">Menu のパーツ</span><span class="sxs-lookup"><span data-stu-id="85ace-108">Menu Parts</span></span>  
 <span data-ttu-id="85ace-109"><xref:System.Windows.Controls.Menu> コントロールに名前付きパーツはありません。</span><span class="sxs-lookup"><span data-stu-id="85ace-109">The <xref:System.Windows.Controls.Menu> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="85ace-110"><xref:System.Windows.Controls.Menu> の <xref:System.Windows.Controls.ControlTemplate> を作成する場合、テンプレートで、<xref:System.Windows.Controls.ScrollViewer> 内に <xref:System.Windows.Controls.ItemsPresenter> を含めることができます</span><span class="sxs-lookup"><span data-stu-id="85ace-110">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.Menu>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="85ace-111">(<xref:System.Windows.Controls.ItemsPresenter> により、<xref:System.Windows.Controls.Menu> の各項目が表示されます。<xref:System.Windows.Controls.ScrollViewer> で、コントロール内のスクロールを有効にします)。</span><span class="sxs-lookup"><span data-stu-id="85ace-111">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.Menu>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="85ace-112"><xref:System.Windows.Controls.ItemsPresenter> が <xref:System.Windows.Controls.ScrollViewer> の直接の子でない場合は、<xref:System.Windows.Controls.ItemsPresenter> に `ItemsPresenter` という名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="85ace-112">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="menu-states"></a><span data-ttu-id="85ace-113">Menu の状態</span><span class="sxs-lookup"><span data-stu-id="85ace-113">Menu States</span></span>  
 <span data-ttu-id="85ace-114">次の表は、<xref:System.Windows.Controls.Menu> コントロールの表示状態の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="85ace-114">The following table lists the visual states for the <xref:System.Windows.Controls.Menu> control.</span></span>  
  
|<span data-ttu-id="85ace-115">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="85ace-115">VisualState Name</span></span>|<span data-ttu-id="85ace-116">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="85ace-116">VisualStateGroup Name</span></span>|<span data-ttu-id="85ace-117">説明</span><span class="sxs-lookup"><span data-stu-id="85ace-117">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="85ace-118">有効</span><span class="sxs-lookup"><span data-stu-id="85ace-118">Valid</span></span>|<span data-ttu-id="85ace-119">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="85ace-119">ValidationStates</span></span>|<span data-ttu-id="85ace-120">このコントロールで <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false` です。</span><span class="sxs-lookup"><span data-stu-id="85ace-120">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="85ace-121">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="85ace-121">InvalidFocused</span></span>|<span data-ttu-id="85ace-122">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="85ace-122">ValidationStates</span></span>|<span data-ttu-id="85ace-123"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがある `true` です。</span><span class="sxs-lookup"><span data-stu-id="85ace-123">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="85ace-124">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="85ace-124">InvalidUnfocused</span></span>|<span data-ttu-id="85ace-125">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="85ace-125">ValidationStates</span></span>|<span data-ttu-id="85ace-126"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがない `true` です。</span><span class="sxs-lookup"><span data-stu-id="85ace-126">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="menuitem-parts"></a><span data-ttu-id="85ace-127">MenuItem のパーツ</span><span class="sxs-lookup"><span data-stu-id="85ace-127">MenuItem Parts</span></span>  
 <span data-ttu-id="85ace-128">次の表は、<xref:System.Windows.Controls.Menu> コントロールの名前付きパーツの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="85ace-128">The following table lists the named parts for the <xref:System.Windows.Controls.Menu> control.</span></span>  
  
|<span data-ttu-id="85ace-129">パーツ</span><span class="sxs-lookup"><span data-stu-id="85ace-129">Part</span></span>|<span data-ttu-id="85ace-130">種類</span><span class="sxs-lookup"><span data-stu-id="85ace-130">Type</span></span>|<span data-ttu-id="85ace-131">説明</span><span class="sxs-lookup"><span data-stu-id="85ace-131">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="85ace-132">PART_Popup</span><span class="sxs-lookup"><span data-stu-id="85ace-132">PART_Popup</span></span>|<xref:System.Windows.Controls.Primitives.Popup>|<span data-ttu-id="85ace-133">サブメニューの領域。</span><span class="sxs-lookup"><span data-stu-id="85ace-133">The area for the submenu.</span></span>|  
  
 <span data-ttu-id="85ace-134"><xref:System.Windows.Controls.MenuItem> の <xref:System.Windows.Controls.ControlTemplate> を作成する場合、テンプレートで、<xref:System.Windows.Controls.ScrollViewer> 内に <xref:System.Windows.Controls.ItemsPresenter> を含めることができます</span><span class="sxs-lookup"><span data-stu-id="85ace-134">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.MenuItem>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="85ace-135">(<xref:System.Windows.Controls.ItemsPresenter> により、<xref:System.Windows.Controls.MenuItem> の各項目が表示されます。<xref:System.Windows.Controls.ScrollViewer> で、コントロール内のスクロールを有効にします)。</span><span class="sxs-lookup"><span data-stu-id="85ace-135">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.MenuItem>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="85ace-136"><xref:System.Windows.Controls.ItemsPresenter> が <xref:System.Windows.Controls.ScrollViewer> の直接の子でない場合は、<xref:System.Windows.Controls.ItemsPresenter> に `ItemsPresenter` という名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="85ace-136">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="menuitem-states"></a><span data-ttu-id="85ace-137">MenuItem の状態</span><span class="sxs-lookup"><span data-stu-id="85ace-137">MenuItem States</span></span>  
 <span data-ttu-id="85ace-138">次の表は、<xref:System.Windows.Controls.MenuItem> コントロールの表示状態の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="85ace-138">The following table lists the visual states for the <xref:System.Windows.Controls.MenuItem> control.</span></span>  
  
|<span data-ttu-id="85ace-139">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="85ace-139">VisualState Name</span></span>|<span data-ttu-id="85ace-140">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="85ace-140">VisualStateGroup Name</span></span>|<span data-ttu-id="85ace-141">説明</span><span class="sxs-lookup"><span data-stu-id="85ace-141">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="85ace-142">有効</span><span class="sxs-lookup"><span data-stu-id="85ace-142">Valid</span></span>|<span data-ttu-id="85ace-143">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="85ace-143">ValidationStates</span></span>|<span data-ttu-id="85ace-144">このコントロールで <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false` です。</span><span class="sxs-lookup"><span data-stu-id="85ace-144">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="85ace-145">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="85ace-145">InvalidFocused</span></span>|<span data-ttu-id="85ace-146">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="85ace-146">ValidationStates</span></span>|<span data-ttu-id="85ace-147"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがある `true` です。</span><span class="sxs-lookup"><span data-stu-id="85ace-147">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="85ace-148">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="85ace-148">InvalidUnfocused</span></span>|<span data-ttu-id="85ace-149">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="85ace-149">ValidationStates</span></span>|<span data-ttu-id="85ace-150"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがない `true` です。</span><span class="sxs-lookup"><span data-stu-id="85ace-150">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="menu-and-menuitem-controltemplate-example"></a><span data-ttu-id="85ace-151">Menu および MenuItem の ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="85ace-151">Menu and MenuItem ControlTemplate Example</span></span>  
 <span data-ttu-id="85ace-152">次の例は、<xref:System.Windows.Controls.Menu> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="85ace-152">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Menu> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Menu](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menu)]  
  
 <span data-ttu-id="85ace-153">次の例は、<xref:System.Windows.Controls.MenuItem> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="85ace-153">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.MenuItem> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#MenuItem](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menuitem)]  
  
 <span data-ttu-id="85ace-154">次の例は、前の例で使用した `MenuScrollViewer` を定義しています。</span><span class="sxs-lookup"><span data-stu-id="85ace-154">The following example defines the `MenuScrollViewer`, which is used in the previous example.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#MenuScrollViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menuscrollviewer)]  
  
 <span data-ttu-id="85ace-155"><xref:System.Windows.Controls.ControlTemplate> の例では、次のリソースを 1 つ以上使用します。</span><span class="sxs-lookup"><span data-stu-id="85ace-155">The <xref:System.Windows.Controls.ControlTemplate> examples use one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="85ace-156">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85ace-156">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85ace-157">関連項目</span><span class="sxs-lookup"><span data-stu-id="85ace-157">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="85ace-158">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="85ace-158">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="85ace-159">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="85ace-159">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="85ace-160">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="85ace-160">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="85ace-161">コントロールのためのテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="85ace-161">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
