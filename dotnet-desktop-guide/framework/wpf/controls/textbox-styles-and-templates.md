---
title: TextBox のスタイルとテンプレート
description: Windows Presentation Foundation の TextBox コントロールのスタイルとテンプレートについて説明します。 ControlTemplate を変更して、コントロールに固有の外観を指定します。
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], TextBox
- parts [WPF], TextBox
- states [WPF], TextBox
- styles [WPF], TextBox
- templates [WPF], TextBox
- TextBox [WPF], styles and templates
ms.assetid: aa99130c-43a1-450f-9b46-c40ae0db0cca
ms.openlocfilehash: e8c1bcbdeaf8b9b6d8bba2ccaf802e48dca02047
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974542"
---
# <a name="textbox-styles-and-templates"></a><span data-ttu-id="5551e-104">TextBox のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="5551e-104">TextBox Styles and Templates</span></span>
<span data-ttu-id="5551e-105">このトピックでは、<xref:System.Windows.Controls.TextBox> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5551e-105">This topic describes the styles and templates for the <xref:System.Windows.Controls.TextBox> control.</span></span> <span data-ttu-id="5551e-106"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="5551e-106">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="5551e-107">詳細については、「[コントロールのためにテンプレートを作成する](/dotnet/desktop-wpf/themes/how-to-create-apply-template)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5551e-107">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>  
  
## <a name="textbox-parts"></a><span data-ttu-id="5551e-108">TextBox のパーツ</span><span class="sxs-lookup"><span data-stu-id="5551e-108">TextBox Parts</span></span>  
 <span data-ttu-id="5551e-109">次の表は、<xref:System.Windows.Controls.TextBox> コントロールの名前付きパーツの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="5551e-109">The following table lists the named parts for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="5551e-110">パーツ</span><span class="sxs-lookup"><span data-stu-id="5551e-110">Part</span></span>|<span data-ttu-id="5551e-111">種類</span><span class="sxs-lookup"><span data-stu-id="5551e-111">Type</span></span>|<span data-ttu-id="5551e-112">説明</span><span class="sxs-lookup"><span data-stu-id="5551e-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="5551e-113">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="5551e-113">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="5551e-114"><xref:System.Windows.FrameworkElement> を含めることができるビジュアル要素。</span><span class="sxs-lookup"><span data-stu-id="5551e-114">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="5551e-115"><xref:System.Windows.Controls.TextBox> のテキストがこの要素に表示されます。</span><span class="sxs-lookup"><span data-stu-id="5551e-115">The text of the <xref:System.Windows.Controls.TextBox> is displayed in this element.</span></span>|  
  
## <a name="textbox-states"></a><span data-ttu-id="5551e-116">TextBox の状態</span><span class="sxs-lookup"><span data-stu-id="5551e-116">TextBox States</span></span>  
 <span data-ttu-id="5551e-117">次の表は、<xref:System.Windows.Controls.TextBox> コントロールの表示状態の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="5551e-117">The following table lists the visual states for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="5551e-118">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="5551e-118">VisualState Name</span></span>|<span data-ttu-id="5551e-119">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="5551e-119">VisualStateGroup Name</span></span>|<span data-ttu-id="5551e-120">説明</span><span class="sxs-lookup"><span data-stu-id="5551e-120">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="5551e-121">標準</span><span class="sxs-lookup"><span data-stu-id="5551e-121">Normal</span></span>|<span data-ttu-id="5551e-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="5551e-122">CommonStates</span></span>|<span data-ttu-id="5551e-123">既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="5551e-123">The default state.</span></span>|  
|<span data-ttu-id="5551e-124">MouseOver</span><span class="sxs-lookup"><span data-stu-id="5551e-124">MouseOver</span></span>|<span data-ttu-id="5551e-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="5551e-125">CommonStates</span></span>|<span data-ttu-id="5551e-126">マウス ポインターがコントロール上に配置されます。</span><span class="sxs-lookup"><span data-stu-id="5551e-126">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="5551e-127">無効</span><span class="sxs-lookup"><span data-stu-id="5551e-127">Disabled</span></span>|<span data-ttu-id="5551e-128">CommonStates</span><span class="sxs-lookup"><span data-stu-id="5551e-128">CommonStates</span></span>|<span data-ttu-id="5551e-129">コントロールが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="5551e-129">The control is disabled.</span></span>|  
|<span data-ttu-id="5551e-130">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="5551e-130">ReadOnly</span></span>|<span data-ttu-id="5551e-131">CommonStates</span><span class="sxs-lookup"><span data-stu-id="5551e-131">CommonStates</span></span>|<span data-ttu-id="5551e-132">ユーザーは、<xref:System.Windows.Controls.TextBox> のテキストを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="5551e-132">The user cannot change the text in the <xref:System.Windows.Controls.TextBox>.</span></span>|  
|<span data-ttu-id="5551e-133">フォーカスされている</span><span class="sxs-lookup"><span data-stu-id="5551e-133">Focused</span></span>|<span data-ttu-id="5551e-134">FocusStates</span><span class="sxs-lookup"><span data-stu-id="5551e-134">FocusStates</span></span>|<span data-ttu-id="5551e-135">コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="5551e-135">The control has focus.</span></span>|  
|<span data-ttu-id="5551e-136">フォーカスされていない</span><span class="sxs-lookup"><span data-stu-id="5551e-136">Unfocused</span></span>|<span data-ttu-id="5551e-137">FocusStates</span><span class="sxs-lookup"><span data-stu-id="5551e-137">FocusStates</span></span>|<span data-ttu-id="5551e-138">コントロールにフォーカスがありません。</span><span class="sxs-lookup"><span data-stu-id="5551e-138">The control does not have focus.</span></span>|  
|<span data-ttu-id="5551e-139">有効</span><span class="sxs-lookup"><span data-stu-id="5551e-139">Valid</span></span>|<span data-ttu-id="5551e-140">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5551e-140">ValidationStates</span></span>|<span data-ttu-id="5551e-141">このコントロールで <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false` です。</span><span class="sxs-lookup"><span data-stu-id="5551e-141">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="5551e-142">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="5551e-142">InvalidFocused</span></span>|<span data-ttu-id="5551e-143">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5551e-143">ValidationStates</span></span>|<span data-ttu-id="5551e-144"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがある `true` です。</span><span class="sxs-lookup"><span data-stu-id="5551e-144">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="5551e-145">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="5551e-145">InvalidUnfocused</span></span>|<span data-ttu-id="5551e-146">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5551e-146">ValidationStates</span></span>|<span data-ttu-id="5551e-147"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがない `true` です。</span><span class="sxs-lookup"><span data-stu-id="5551e-147">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="textbox-controltemplate-example"></a><span data-ttu-id="5551e-148">TextBox の ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="5551e-148">TextBox ControlTemplate Example</span></span>  
 <span data-ttu-id="5551e-149">次の例は、<xref:System.Windows.Controls.TextBox> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="5551e-149">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#TextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#textbox)]  
  
 <span data-ttu-id="5551e-150">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="5551e-150">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="5551e-151">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5551e-151">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5551e-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="5551e-152">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="5551e-153">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="5551e-153">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="5551e-154">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="5551e-154">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="5551e-155">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="5551e-155">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="5551e-156">コントロールのためのテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="5551e-156">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
