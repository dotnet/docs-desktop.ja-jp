---
title: RadioButton のスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], RadioButton
- RadioButton [WPF], styles and templates
- ControlTemplate [WPF], RadioButton
- states [WPF], RadioButton
- templates [WPF], RadioButton
- parts [WPF], RadioButton
ms.assetid: 9acf93f7-dd2f-4010-8ce0-1edd81c52ae2
ms.openlocfilehash: f631ca3269c5660513090d6731d835376c407356
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983575"
---
# <a name="radiobutton-styles-and-templates"></a><span data-ttu-id="37ee2-102">RadioButton のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="37ee2-102">RadioButton Styles and Templates</span></span>
<span data-ttu-id="37ee2-103">このトピックでは、<xref:System.Windows.Controls.RadioButton> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="37ee2-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.RadioButton> control.</span></span> <span data-ttu-id="37ee2-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="37ee2-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="37ee2-105">詳細については、「[コントロールのためにテンプレートを作成する](/dotnet/desktop-wpf/themes/how-to-create-apply-template)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="37ee2-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>  
  
## <a name="radiobutton-parts"></a><span data-ttu-id="37ee2-106">RadioButton のパーツ</span><span class="sxs-lookup"><span data-stu-id="37ee2-106">RadioButton Parts</span></span>  
 <span data-ttu-id="37ee2-107"><xref:System.Windows.Controls.RadioButton> コントロールに名前付きパーツはありません。</span><span class="sxs-lookup"><span data-stu-id="37ee2-107">The <xref:System.Windows.Controls.RadioButton> control does not have any named parts.</span></span>  
  
## <a name="radiobutton-states"></a><span data-ttu-id="37ee2-108">RadioButton の状態</span><span class="sxs-lookup"><span data-stu-id="37ee2-108">RadioButton States</span></span>  
 <span data-ttu-id="37ee2-109">次の表は、<xref:System.Windows.Controls.RadioButton> コントロールの表示状態の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="37ee2-109">The following table lists the visual states for the <xref:System.Windows.Controls.RadioButton> control.</span></span>  
  
|<span data-ttu-id="37ee2-110">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="37ee2-110">VisualState Name</span></span>|<span data-ttu-id="37ee2-111">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="37ee2-111">VisualStateGroup Name</span></span>|<span data-ttu-id="37ee2-112">説明</span><span class="sxs-lookup"><span data-stu-id="37ee2-112">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="37ee2-113">標準</span><span class="sxs-lookup"><span data-stu-id="37ee2-113">Normal</span></span>|<span data-ttu-id="37ee2-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="37ee2-114">CommonStates</span></span>|<span data-ttu-id="37ee2-115">既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="37ee2-115">The default state.</span></span>|  
|<span data-ttu-id="37ee2-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="37ee2-116">MouseOver</span></span>|<span data-ttu-id="37ee2-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="37ee2-117">CommonStates</span></span>|<span data-ttu-id="37ee2-118">マウス ポインターがコントロール上に配置されています。</span><span class="sxs-lookup"><span data-stu-id="37ee2-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="37ee2-119">押されている</span><span class="sxs-lookup"><span data-stu-id="37ee2-119">Pressed</span></span>|<span data-ttu-id="37ee2-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="37ee2-120">CommonStates</span></span>|<span data-ttu-id="37ee2-121">コントロールが押されています。</span><span class="sxs-lookup"><span data-stu-id="37ee2-121">The control is pressed.</span></span>|  
|<span data-ttu-id="37ee2-122">無効</span><span class="sxs-lookup"><span data-stu-id="37ee2-122">Disabled</span></span>|<span data-ttu-id="37ee2-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="37ee2-123">CommonStates</span></span>|<span data-ttu-id="37ee2-124">コントロールが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="37ee2-124">The control is disabled.</span></span>|  
|<span data-ttu-id="37ee2-125">フォーカスされている</span><span class="sxs-lookup"><span data-stu-id="37ee2-125">Focused</span></span>|<span data-ttu-id="37ee2-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="37ee2-126">FocusStates</span></span>|<span data-ttu-id="37ee2-127">コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="37ee2-127">The control has focus.</span></span>|  
|<span data-ttu-id="37ee2-128">フォーカスされていない</span><span class="sxs-lookup"><span data-stu-id="37ee2-128">Unfocused</span></span>|<span data-ttu-id="37ee2-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="37ee2-129">FocusStates</span></span>|<span data-ttu-id="37ee2-130">コントロールにフォーカスがありません。</span><span class="sxs-lookup"><span data-stu-id="37ee2-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="37ee2-131">チェック済み</span><span class="sxs-lookup"><span data-stu-id="37ee2-131">Checked</span></span>|<span data-ttu-id="37ee2-132">CheckStates</span><span class="sxs-lookup"><span data-stu-id="37ee2-132">CheckStates</span></span>|<span data-ttu-id="37ee2-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> が `true`です。</span><span class="sxs-lookup"><span data-stu-id="37ee2-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `true`.</span></span>|  
|<span data-ttu-id="37ee2-134">オフ</span><span class="sxs-lookup"><span data-stu-id="37ee2-134">Unchecked</span></span>|<span data-ttu-id="37ee2-135">CheckStates</span><span class="sxs-lookup"><span data-stu-id="37ee2-135">CheckStates</span></span>|<span data-ttu-id="37ee2-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> が `false`です。</span><span class="sxs-lookup"><span data-stu-id="37ee2-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `false`.</span></span>|  
|<span data-ttu-id="37ee2-137">Indeterminate</span><span class="sxs-lookup"><span data-stu-id="37ee2-137">Indeterminate</span></span>|<span data-ttu-id="37ee2-138">CheckStates</span><span class="sxs-lookup"><span data-stu-id="37ee2-138">CheckStates</span></span>|<span data-ttu-id="37ee2-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> が `true` で、<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> が `null` です。</span><span class="sxs-lookup"><span data-stu-id="37ee2-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span></span>|  
|<span data-ttu-id="37ee2-140">有効</span><span class="sxs-lookup"><span data-stu-id="37ee2-140">Valid</span></span>|<span data-ttu-id="37ee2-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="37ee2-141">ValidationStates</span></span>|<span data-ttu-id="37ee2-142">このコントロールで <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false` です。</span><span class="sxs-lookup"><span data-stu-id="37ee2-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="37ee2-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="37ee2-143">InvalidFocused</span></span>|<span data-ttu-id="37ee2-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="37ee2-144">ValidationStates</span></span>|<span data-ttu-id="37ee2-145"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがある `true` です。</span><span class="sxs-lookup"><span data-stu-id="37ee2-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="37ee2-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="37ee2-146">InvalidUnfocused</span></span>|<span data-ttu-id="37ee2-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="37ee2-147">ValidationStates</span></span>|<span data-ttu-id="37ee2-148"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがない `true` です。</span><span class="sxs-lookup"><span data-stu-id="37ee2-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="radiobutton-controltemplate-example"></a><span data-ttu-id="37ee2-149">RadioButton の ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="37ee2-149">RadioButton ControlTemplate Example</span></span>  
 <span data-ttu-id="37ee2-150">次の例は、<xref:System.Windows.Controls.RadioButton> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="37ee2-150">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.RadioButton> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#RadioButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/radiobutton.xaml#radiobutton)]  
  
 <span data-ttu-id="37ee2-151">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="37ee2-151">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="37ee2-152">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37ee2-152">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37ee2-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="37ee2-153">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="37ee2-154">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="37ee2-154">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="37ee2-155">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="37ee2-155">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="37ee2-156">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="37ee2-156">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="37ee2-157">コントロールのためのテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="37ee2-157">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
