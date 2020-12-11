---
title: ToggleButton のスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], ToggleButton
- ToggleButton [WPF], styles and templates
- ControlTemplate [WPF], ToggleButton
- styles [WPF], ToggleButton
- templates [WPF], ToggleButton
- parts [WPF], ToggleButton
ms.assetid: 54f23f30-4bcb-4f09-8ce4-376a13a255a1
ms.openlocfilehash: 2c5aee58878ea6199c07ee201882fd3ded97bdee
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983479"
---
# <a name="togglebutton-styles-and-templates"></a><span data-ttu-id="c4fe1-102">ToggleButton のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="c4fe1-102">ToggleButton Styles and Templates</span></span>

<span data-ttu-id="c4fe1-103">このトピックでは、<xref:System.Windows.Controls.Primitives.ToggleButton> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c4fe1-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span> <span data-ttu-id="c4fe1-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="c4fe1-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="c4fe1-105">詳細については、「[コントロールのためにテンプレートを作成する](/dotnet/desktop-wpf/themes/how-to-create-apply-template)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c4fe1-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>

## <a name="togglebutton-parts"></a><span data-ttu-id="c4fe1-106">ToggleButton のパーツ</span><span class="sxs-lookup"><span data-stu-id="c4fe1-106">ToggleButton Parts</span></span>

<span data-ttu-id="c4fe1-107"><xref:System.Windows.Controls.Primitives.ToggleButton> コントロールに名前付きパーツはありません。</span><span class="sxs-lookup"><span data-stu-id="c4fe1-107">The <xref:System.Windows.Controls.Primitives.ToggleButton> control does not have any named parts.</span></span>

## <a name="togglebutton-states"></a><span data-ttu-id="c4fe1-108">ToggleButton の状態</span><span class="sxs-lookup"><span data-stu-id="c4fe1-108">ToggleButton States</span></span>

<span data-ttu-id="c4fe1-109">次の表は、<xref:System.Windows.Controls.Primitives.ToggleButton> コントロールの表示状態の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="c4fe1-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>

|<span data-ttu-id="c4fe1-110">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="c4fe1-110">VisualState Name</span></span>|<span data-ttu-id="c4fe1-111">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="c4fe1-111">VisualStateGroup Name</span></span>|<span data-ttu-id="c4fe1-112">説明</span><span class="sxs-lookup"><span data-stu-id="c4fe1-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="c4fe1-113">標準</span><span class="sxs-lookup"><span data-stu-id="c4fe1-113">Normal</span></span>|<span data-ttu-id="c4fe1-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="c4fe1-114">CommonStates</span></span>|<span data-ttu-id="c4fe1-115">既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="c4fe1-115">The default state.</span></span>|
|<span data-ttu-id="c4fe1-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="c4fe1-116">MouseOver</span></span>|<span data-ttu-id="c4fe1-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="c4fe1-117">CommonStates</span></span>|<span data-ttu-id="c4fe1-118">マウス ポインターがコントロール上に配置されています。</span><span class="sxs-lookup"><span data-stu-id="c4fe1-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="c4fe1-119">押されている</span><span class="sxs-lookup"><span data-stu-id="c4fe1-119">Pressed</span></span>|<span data-ttu-id="c4fe1-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="c4fe1-120">CommonStates</span></span>|<span data-ttu-id="c4fe1-121">コントロールが押されています。</span><span class="sxs-lookup"><span data-stu-id="c4fe1-121">The control is pressed.</span></span>|
|<span data-ttu-id="c4fe1-122">無効</span><span class="sxs-lookup"><span data-stu-id="c4fe1-122">Disabled</span></span>|<span data-ttu-id="c4fe1-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="c4fe1-123">CommonStates</span></span>|<span data-ttu-id="c4fe1-124">コントロールが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="c4fe1-124">The control is disabled.</span></span>|
|<span data-ttu-id="c4fe1-125">フォーカスされている</span><span class="sxs-lookup"><span data-stu-id="c4fe1-125">Focused</span></span>|<span data-ttu-id="c4fe1-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="c4fe1-126">FocusStates</span></span>|<span data-ttu-id="c4fe1-127">コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="c4fe1-127">The control has focus.</span></span>|
|<span data-ttu-id="c4fe1-128">フォーカスされていない</span><span class="sxs-lookup"><span data-stu-id="c4fe1-128">Unfocused</span></span>|<span data-ttu-id="c4fe1-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="c4fe1-129">FocusStates</span></span>|<span data-ttu-id="c4fe1-130">コントロールにフォーカスがありません。</span><span class="sxs-lookup"><span data-stu-id="c4fe1-130">The control does not have focus.</span></span>|
|<span data-ttu-id="c4fe1-131">チェック済み</span><span class="sxs-lookup"><span data-stu-id="c4fe1-131">Checked</span></span>|<span data-ttu-id="c4fe1-132">CheckStates</span><span class="sxs-lookup"><span data-stu-id="c4fe1-132">CheckStates</span></span>|<span data-ttu-id="c4fe1-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> が `true`です。</span><span class="sxs-lookup"><span data-stu-id="c4fe1-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `true`.</span></span>|
|<span data-ttu-id="c4fe1-134">オフ</span><span class="sxs-lookup"><span data-stu-id="c4fe1-134">Unchecked</span></span>|<span data-ttu-id="c4fe1-135">CheckStates</span><span class="sxs-lookup"><span data-stu-id="c4fe1-135">CheckStates</span></span>|<span data-ttu-id="c4fe1-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> が `false`です。</span><span class="sxs-lookup"><span data-stu-id="c4fe1-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `false`.</span></span>|
|<span data-ttu-id="c4fe1-137">Indeterminate</span><span class="sxs-lookup"><span data-stu-id="c4fe1-137">Indeterminate</span></span>|<span data-ttu-id="c4fe1-138">CheckStates</span><span class="sxs-lookup"><span data-stu-id="c4fe1-138">CheckStates</span></span>|<span data-ttu-id="c4fe1-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> が `true` で、<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> が `null` です。</span><span class="sxs-lookup"><span data-stu-id="c4fe1-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span></span>|
|<span data-ttu-id="c4fe1-140">有効</span><span class="sxs-lookup"><span data-stu-id="c4fe1-140">Valid</span></span>|<span data-ttu-id="c4fe1-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="c4fe1-141">ValidationStates</span></span>|<span data-ttu-id="c4fe1-142">コントロールでは <xref:System.Windows.Controls.Validation> クラスが使用されており、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false` です。</span><span class="sxs-lookup"><span data-stu-id="c4fe1-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="c4fe1-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="c4fe1-143">InvalidFocused</span></span>|<span data-ttu-id="c4fe1-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="c4fe1-144">ValidationStates</span></span>|<span data-ttu-id="c4fe1-145"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `true` で、コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="c4fe1-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|
|<span data-ttu-id="c4fe1-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="c4fe1-146">InvalidUnfocused</span></span>|<span data-ttu-id="c4fe1-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="c4fe1-147">ValidationStates</span></span>|<span data-ttu-id="c4fe1-148"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `true` で、コントロールにフォーカスがありません。</span><span class="sxs-lookup"><span data-stu-id="c4fe1-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|

> [!NOTE]
> <span data-ttu-id="c4fe1-149">Indeterminate 表示状態がコントロール テンプレートに存在しない場合、Unchecked 表示状態が既定の表示状態として使用されます。</span><span class="sxs-lookup"><span data-stu-id="c4fe1-149">If the Indeterminate visual state does not exist in your control template, then the Unchecked visual state will be used as default visual state.</span></span>

## <a name="togglebutton-controltemplate-example"></a><span data-ttu-id="c4fe1-150">ToggleButton の ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="c4fe1-150">ToggleButton ControlTemplate Example</span></span>

<span data-ttu-id="c4fe1-151">次の例は、<xref:System.Windows.Controls.Primitives.ToggleButton> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="c4fe1-151">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>

[!code-xaml[ControlTemplateExamples#ToggleButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#togglebutton)]

<span data-ttu-id="c4fe1-152">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="c4fe1-152">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="c4fe1-153">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4fe1-153">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="c4fe1-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="c4fe1-154">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="c4fe1-155">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="c4fe1-155">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="c4fe1-156">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="c4fe1-156">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="c4fe1-157">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="c4fe1-157">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="c4fe1-158">コントロールのためのテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="c4fe1-158">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
