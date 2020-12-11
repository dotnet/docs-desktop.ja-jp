---
title: StatusBar のスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], StatusBar
- styles [WPF], StatusBar
- templates [WPF], StatusBar
- states [WPF], StatusBar
- parts [WPF], StatusBar
- StatusBar [WPF], styles and templates
ms.assetid: 9f5e1c25-81eb-4756-a0ac-d9e1fbe33ee2
ms.openlocfilehash: 6b56ff468a195aaac470eaa944af481086e87520
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981440"
---
# <a name="statusbar-styles-and-templates"></a><span data-ttu-id="2425f-102">StatusBar のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="2425f-102">StatusBar Styles and Templates</span></span>
<span data-ttu-id="2425f-103">このトピックでは、<xref:System.Windows.Controls.Primitives.StatusBar> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2425f-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span> <span data-ttu-id="2425f-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="2425f-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="2425f-105">詳細については、「[コントロールのためにテンプレートを作成する](/dotnet/desktop-wpf/themes/how-to-create-apply-template)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2425f-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>  
  
## <a name="statusbar-parts"></a><span data-ttu-id="2425f-106">StatusBar のパーツ</span><span class="sxs-lookup"><span data-stu-id="2425f-106">StatusBar Parts</span></span>  
 <span data-ttu-id="2425f-107"><xref:System.Windows.Controls.Primitives.StatusBar> コントロールに名前付きパーツはありません。</span><span class="sxs-lookup"><span data-stu-id="2425f-107">The <xref:System.Windows.Controls.Primitives.StatusBar> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="2425f-108">StatusBar の状態</span><span class="sxs-lookup"><span data-stu-id="2425f-108">StatusBar States</span></span>  
 <span data-ttu-id="2425f-109">次の表は、<xref:System.Windows.Controls.Primitives.StatusBar> コントロールの表示状態の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="2425f-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
|<span data-ttu-id="2425f-110">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="2425f-110">VisualState Name</span></span>|<span data-ttu-id="2425f-111">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="2425f-111">VisualStateGroup Name</span></span>|<span data-ttu-id="2425f-112">説明</span><span class="sxs-lookup"><span data-stu-id="2425f-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="2425f-113">有効</span><span class="sxs-lookup"><span data-stu-id="2425f-113">Valid</span></span>|<span data-ttu-id="2425f-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="2425f-114">ValidationStates</span></span>|<span data-ttu-id="2425f-115">このコントロールで <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false` です。</span><span class="sxs-lookup"><span data-stu-id="2425f-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="2425f-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="2425f-116">InvalidFocused</span></span>|<span data-ttu-id="2425f-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="2425f-117">ValidationStates</span></span>|<span data-ttu-id="2425f-118"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがある `true` です。</span><span class="sxs-lookup"><span data-stu-id="2425f-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="2425f-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="2425f-119">InvalidUnfocused</span></span>|<span data-ttu-id="2425f-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="2425f-120">ValidationStates</span></span>|<span data-ttu-id="2425f-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがない `true` です。</span><span class="sxs-lookup"><span data-stu-id="2425f-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbaritem-parts"></a><span data-ttu-id="2425f-122">StatusBarItem のパーツ</span><span class="sxs-lookup"><span data-stu-id="2425f-122">StatusBarItem Parts</span></span>  
 <span data-ttu-id="2425f-123"><xref:System.Windows.Controls.Primitives.StatusBarItem> コントロールに名前付きパーツはありません。</span><span class="sxs-lookup"><span data-stu-id="2425f-123">The <xref:System.Windows.Controls.Primitives.StatusBarItem> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="2425f-124">StatusBar の状態</span><span class="sxs-lookup"><span data-stu-id="2425f-124">StatusBar States</span></span>  
 <span data-ttu-id="2425f-125">次の表は、<xref:System.Windows.Controls.Primitives.StatusBarItem> コントロールの表示状態の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="2425f-125">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBarItem> control.</span></span>  
  
|<span data-ttu-id="2425f-126">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="2425f-126">VisualState Name</span></span>|<span data-ttu-id="2425f-127">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="2425f-127">VisualStateGroup Name</span></span>|<span data-ttu-id="2425f-128">説明</span><span class="sxs-lookup"><span data-stu-id="2425f-128">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="2425f-129">有効</span><span class="sxs-lookup"><span data-stu-id="2425f-129">Valid</span></span>|<span data-ttu-id="2425f-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="2425f-130">ValidationStates</span></span>|<span data-ttu-id="2425f-131">このコントロールで <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false` です。</span><span class="sxs-lookup"><span data-stu-id="2425f-131">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="2425f-132">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="2425f-132">InvalidFocused</span></span>|<span data-ttu-id="2425f-133">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="2425f-133">ValidationStates</span></span>|<span data-ttu-id="2425f-134"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがある `true` です。</span><span class="sxs-lookup"><span data-stu-id="2425f-134">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="2425f-135">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="2425f-135">InvalidUnfocused</span></span>|<span data-ttu-id="2425f-136">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="2425f-136">ValidationStates</span></span>|<span data-ttu-id="2425f-137"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがない `true` です。</span><span class="sxs-lookup"><span data-stu-id="2425f-137">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbar-controltemplate-example"></a><span data-ttu-id="2425f-138">StatusBar の ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="2425f-138">StatusBar ControlTemplate Example</span></span>  
 <span data-ttu-id="2425f-139">次の例は、<xref:System.Windows.Controls.Primitives.StatusBar> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="2425f-139">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#StatusBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/statusbar.xaml#statusbar)]  
  
 <span data-ttu-id="2425f-140"><xref:System.Windows.Controls.ControlTemplate> では、次のリソースを 1 つ以上使用します。</span><span class="sxs-lookup"><span data-stu-id="2425f-140">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="2425f-141">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2425f-141">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2425f-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="2425f-142">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="2425f-143">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="2425f-143">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="2425f-144">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="2425f-144">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="2425f-145">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="2425f-145">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="2425f-146">コントロールのためのテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="2425f-146">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
