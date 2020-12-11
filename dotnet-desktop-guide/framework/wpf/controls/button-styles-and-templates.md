---
title: ボタンのスタイルとテンプレート
description: Windows Presentation Foundation の Button コントロールのスタイルとテンプレートについて学習します。 ControlTemplate を変更して、コントロールに固有の外観を指定します。
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], Button
- parts [WPF], Button
- styles [WPF], Button
- Button [WPF], styles and templates
- templates [WPF], Button
- ControlTemplate [WPF], Button
ms.assetid: e223c759-f8c4-4717-acfb-b1e40bdf5f3b
ms.openlocfilehash: 957c0663a8c444de71d2710bcff04cb73aaf3e27
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984256"
---
# <a name="button-styles-and-templates"></a><span data-ttu-id="8aea2-104">ボタンのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="8aea2-104">Button Styles and Templates</span></span>
<span data-ttu-id="8aea2-105">このトピックでは、<xref:System.Windows.Controls.Button> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8aea2-105">This topic describes the styles and templates for the <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="8aea2-106"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="8aea2-106">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="8aea2-107">詳細については、「[コントロールのためにテンプレートを作成する](/dotnet/desktop-wpf/themes/how-to-create-apply-template)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8aea2-107">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>  
  
## <a name="button-parts"></a><span data-ttu-id="8aea2-108">Button のパーツ</span><span class="sxs-lookup"><span data-stu-id="8aea2-108">Button Parts</span></span>  
 <span data-ttu-id="8aea2-109"><xref:System.Windows.Controls.Button> コントロールに名前付きパーツはありません。</span><span class="sxs-lookup"><span data-stu-id="8aea2-109">The <xref:System.Windows.Controls.Button> control does not have any named parts.</span></span>  
  
## <a name="button-states"></a><span data-ttu-id="8aea2-110">Button の状態</span><span class="sxs-lookup"><span data-stu-id="8aea2-110">Button States</span></span>  
 <span data-ttu-id="8aea2-111">次の表は、<xref:System.Windows.Controls.Button> コントロールの表示状態の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="8aea2-111">The following table lists the visual states for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
|<span data-ttu-id="8aea2-112">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="8aea2-112">VisualState Name</span></span>|<span data-ttu-id="8aea2-113">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="8aea2-113">VisualStateGroup Name</span></span>|<span data-ttu-id="8aea2-114">説明</span><span class="sxs-lookup"><span data-stu-id="8aea2-114">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="8aea2-115">標準</span><span class="sxs-lookup"><span data-stu-id="8aea2-115">Normal</span></span>|<span data-ttu-id="8aea2-116">CommonStates</span><span class="sxs-lookup"><span data-stu-id="8aea2-116">CommonStates</span></span>|<span data-ttu-id="8aea2-117">既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="8aea2-117">The default state.</span></span>|  
|<span data-ttu-id="8aea2-118">MouseOver</span><span class="sxs-lookup"><span data-stu-id="8aea2-118">MouseOver</span></span>|<span data-ttu-id="8aea2-119">CommonStates</span><span class="sxs-lookup"><span data-stu-id="8aea2-119">CommonStates</span></span>|<span data-ttu-id="8aea2-120">マウス ポインターがコントロール上に配置されています。</span><span class="sxs-lookup"><span data-stu-id="8aea2-120">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="8aea2-121">押されている</span><span class="sxs-lookup"><span data-stu-id="8aea2-121">Pressed</span></span>|<span data-ttu-id="8aea2-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="8aea2-122">CommonStates</span></span>|<span data-ttu-id="8aea2-123">コントロールが押されています。</span><span class="sxs-lookup"><span data-stu-id="8aea2-123">The control is pressed.</span></span>|  
|<span data-ttu-id="8aea2-124">無効</span><span class="sxs-lookup"><span data-stu-id="8aea2-124">Disabled</span></span>|<span data-ttu-id="8aea2-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="8aea2-125">CommonStates</span></span>|<span data-ttu-id="8aea2-126">コントロールが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="8aea2-126">The control is disabled.</span></span>|  
|<span data-ttu-id="8aea2-127">フォーカスされている</span><span class="sxs-lookup"><span data-stu-id="8aea2-127">Focused</span></span>|<span data-ttu-id="8aea2-128">FocusStates</span><span class="sxs-lookup"><span data-stu-id="8aea2-128">FocusStates</span></span>|<span data-ttu-id="8aea2-129">コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="8aea2-129">The control has focus.</span></span>|  
|<span data-ttu-id="8aea2-130">フォーカスされていない</span><span class="sxs-lookup"><span data-stu-id="8aea2-130">Unfocused</span></span>|<span data-ttu-id="8aea2-131">FocusStates</span><span class="sxs-lookup"><span data-stu-id="8aea2-131">FocusStates</span></span>|<span data-ttu-id="8aea2-132">コントロールにフォーカスがありません。</span><span class="sxs-lookup"><span data-stu-id="8aea2-132">The control does not have focus.</span></span>|  
|<span data-ttu-id="8aea2-133">有効</span><span class="sxs-lookup"><span data-stu-id="8aea2-133">Valid</span></span>|<span data-ttu-id="8aea2-134">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8aea2-134">ValidationStates</span></span>|<span data-ttu-id="8aea2-135">このコントロールで <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false` です。</span><span class="sxs-lookup"><span data-stu-id="8aea2-135">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="8aea2-136">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="8aea2-136">InvalidFocused</span></span>|<span data-ttu-id="8aea2-137">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8aea2-137">ValidationStates</span></span>|<span data-ttu-id="8aea2-138"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `true` で、コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="8aea2-138">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="8aea2-139">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="8aea2-139">InvalidUnfocused</span></span>|<span data-ttu-id="8aea2-140">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8aea2-140">ValidationStates</span></span>|<span data-ttu-id="8aea2-141"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `true` で、コントロールにフォーカスがありません。</span><span class="sxs-lookup"><span data-stu-id="8aea2-141">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="button-controltemplate-example"></a><span data-ttu-id="8aea2-142">Button の ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="8aea2-142">Button ControlTemplate Example</span></span>  
 <span data-ttu-id="8aea2-143">次の例は、<xref:System.Windows.Controls.Button> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="8aea2-143">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Button](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/button.xaml#button)]  
  
 <span data-ttu-id="8aea2-144">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="8aea2-144">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="8aea2-145">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8aea2-145">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8aea2-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="8aea2-146">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="8aea2-147">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="8aea2-147">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="8aea2-148">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="8aea2-148">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="8aea2-149">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="8aea2-149">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="8aea2-150">コントロールのためのテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="8aea2-150">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
