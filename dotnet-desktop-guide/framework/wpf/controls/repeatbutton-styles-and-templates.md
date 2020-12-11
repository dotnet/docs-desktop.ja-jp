---
title: RepeatButton のスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- RepeatButton [WPF], styles and templates
- styles [WPF], RepeatButton
- templates [WPF], RepeatButton
- parts [WPF], RepeatButton
- ControlTemplate [WPF], RepeatButton
- states [WPF], RepeatButton
ms.assetid: fd340743-f44f-4990-9077-085301469670
ms.openlocfilehash: cff73c4c7ff06ad6d7b602ff1c6b9b38a4396509
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985319"
---
# <a name="repeatbutton-styles-and-templates"></a><span data-ttu-id="69f80-102">RepeatButton のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="69f80-102">RepeatButton Styles and Templates</span></span>

<span data-ttu-id="69f80-103">このトピックでは、<xref:System.Windows.Controls.Primitives.RepeatButton> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="69f80-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span> <span data-ttu-id="69f80-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="69f80-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="69f80-105">詳細については、「[コントロールのためにテンプレートを作成する](/dotnet/desktop-wpf/themes/how-to-create-apply-template)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="69f80-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>

## <a name="repeatbutton-parts"></a><span data-ttu-id="69f80-106">RepeatButton のパーツ</span><span class="sxs-lookup"><span data-stu-id="69f80-106">RepeatButton Parts</span></span>

<span data-ttu-id="69f80-107"><xref:System.Windows.Controls.Primitives.RepeatButton> コントロールに名前付きパーツはありません。</span><span class="sxs-lookup"><span data-stu-id="69f80-107">The <xref:System.Windows.Controls.Primitives.RepeatButton> control does not have any named parts.</span></span>

## <a name="repeatbutton-states"></a><span data-ttu-id="69f80-108">RepeatButton の状態</span><span class="sxs-lookup"><span data-stu-id="69f80-108">RepeatButton States</span></span>

<span data-ttu-id="69f80-109">次の表は、<xref:System.Windows.Controls.Primitives.RepeatButton> コントロールの表示状態の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="69f80-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span>

|<span data-ttu-id="69f80-110">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="69f80-110">VisualState Name</span></span>|<span data-ttu-id="69f80-111">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="69f80-111">VisualStateGroup Name</span></span>|<span data-ttu-id="69f80-112">説明</span><span class="sxs-lookup"><span data-stu-id="69f80-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="69f80-113">標準</span><span class="sxs-lookup"><span data-stu-id="69f80-113">Normal</span></span>|<span data-ttu-id="69f80-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="69f80-114">CommonStates</span></span>|<span data-ttu-id="69f80-115">既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="69f80-115">The default state.</span></span>|
|<span data-ttu-id="69f80-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="69f80-116">MouseOver</span></span>|<span data-ttu-id="69f80-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="69f80-117">CommonStates</span></span>|<span data-ttu-id="69f80-118">マウス ポインターがコントロール上に配置されています。</span><span class="sxs-lookup"><span data-stu-id="69f80-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="69f80-119">押されている</span><span class="sxs-lookup"><span data-stu-id="69f80-119">Pressed</span></span>|<span data-ttu-id="69f80-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="69f80-120">CommonStates</span></span>|<span data-ttu-id="69f80-121">コントロールが押されています。</span><span class="sxs-lookup"><span data-stu-id="69f80-121">The control is pressed.</span></span>|
|<span data-ttu-id="69f80-122">無効</span><span class="sxs-lookup"><span data-stu-id="69f80-122">Disabled</span></span>|<span data-ttu-id="69f80-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="69f80-123">CommonStates</span></span>|<span data-ttu-id="69f80-124">コントロールが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="69f80-124">The control is disabled.</span></span>|
|<span data-ttu-id="69f80-125">フォーカスされている</span><span class="sxs-lookup"><span data-stu-id="69f80-125">Focused</span></span>|<span data-ttu-id="69f80-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="69f80-126">FocusStates</span></span>|<span data-ttu-id="69f80-127">コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="69f80-127">The control has focus.</span></span>|
|<span data-ttu-id="69f80-128">フォーカスされていない</span><span class="sxs-lookup"><span data-stu-id="69f80-128">Unfocused</span></span>|<span data-ttu-id="69f80-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="69f80-129">FocusStates</span></span>|<span data-ttu-id="69f80-130">コントロールにフォーカスがありません。</span><span class="sxs-lookup"><span data-stu-id="69f80-130">The control does not have focus.</span></span>|
|<span data-ttu-id="69f80-131">有効</span><span class="sxs-lookup"><span data-stu-id="69f80-131">Valid</span></span>|<span data-ttu-id="69f80-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="69f80-132">ValidationStates</span></span>|<span data-ttu-id="69f80-133">このコントロールで <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false` です。</span><span class="sxs-lookup"><span data-stu-id="69f80-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="69f80-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="69f80-134">InvalidFocused</span></span>|<span data-ttu-id="69f80-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="69f80-135">ValidationStates</span></span>|<span data-ttu-id="69f80-136"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがある `true` です。</span><span class="sxs-lookup"><span data-stu-id="69f80-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="69f80-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="69f80-137">InvalidUnfocused</span></span>|<span data-ttu-id="69f80-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="69f80-138">ValidationStates</span></span>|<span data-ttu-id="69f80-139"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがない `true` です。</span><span class="sxs-lookup"><span data-stu-id="69f80-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

## <a name="repeatbutton-controltemplate-example"></a><span data-ttu-id="69f80-140">RepeatButton の ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="69f80-140">RepeatButton ControlTemplate Example</span></span>

<span data-ttu-id="69f80-141">次の例は、<xref:System.Windows.Controls.Primitives.RepeatButton> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="69f80-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span>

[!code-xaml[ControlTemplateExamples#RepeatButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#repeatbutton)]

<span data-ttu-id="69f80-142">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="69f80-142">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="69f80-143">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69f80-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="69f80-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="69f80-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="69f80-145">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="69f80-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="69f80-146">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="69f80-146">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="69f80-147">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="69f80-147">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="69f80-148">コントロールのためのテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="69f80-148">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
