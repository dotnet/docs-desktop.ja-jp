---
title: スライダーのスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], Slider
- states [WPF], Slider
- Slider [WPF], styles and templates
- styles [WPF], Slider
- templates [WPF], Slider
- ControlTemplate [WPF], Slider
ms.assetid: d89aa97b-075a-4752-9c41-9679df65c491
ms.openlocfilehash: d97e9c1e2783d2c348955622fbe98ea3916726d6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983492"
---
# <a name="slider-styles-and-templates"></a><span data-ttu-id="b2642-102">スライダーのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="b2642-102">Slider Styles and Templates</span></span>
<span data-ttu-id="b2642-103">このトピックでは、<xref:System.Windows.Controls.Slider> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b2642-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Slider> control.</span></span> <span data-ttu-id="b2642-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="b2642-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="b2642-105">詳細については、「[コントロールのためにテンプレートを作成する](/dotnet/desktop-wpf/themes/how-to-create-apply-template)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b2642-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>  
  
## <a name="slider-parts"></a><span data-ttu-id="b2642-106">Slider のパーツ</span><span class="sxs-lookup"><span data-stu-id="b2642-106">Slider Parts</span></span>  
 <span data-ttu-id="b2642-107">次の表は、<xref:System.Windows.Controls.Slider> コントロールの名前付きパーツの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="b2642-107">The following table lists the named parts for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
|<span data-ttu-id="b2642-108">パーツ</span><span class="sxs-lookup"><span data-stu-id="b2642-108">Part</span></span>|<span data-ttu-id="b2642-109">種類</span><span class="sxs-lookup"><span data-stu-id="b2642-109">Type</span></span>|<span data-ttu-id="b2642-110">説明</span><span class="sxs-lookup"><span data-stu-id="b2642-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="b2642-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="b2642-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="b2642-112"><xref:System.Windows.Controls.Slider> の位置を示す要素のコンテナー。</span><span class="sxs-lookup"><span data-stu-id="b2642-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Slider>.</span></span>|  
|<span data-ttu-id="b2642-113">PART_SelectionRange</span><span class="sxs-lookup"><span data-stu-id="b2642-113">PART_SelectionRange</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="b2642-114"><xref:System.Windows.Controls.Slider> に沿って選択範囲を表示する要素。</span><span class="sxs-lookup"><span data-stu-id="b2642-114">The element that displays a selection range along the <xref:System.Windows.Controls.Slider>.</span></span>  <span data-ttu-id="b2642-115">選択範囲は、<xref:System.Windows.Controls.Slider.IsSelectionRangeEnabled%2A> プロパティが `true` の場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="b2642-115">The selection range is visible only if the <xref:System.Windows.Controls.Slider.IsSelectionRangeEnabled%2A> property is `true`.</span></span>|  
  
## <a name="slider-states"></a><span data-ttu-id="b2642-116">Slider の状態</span><span class="sxs-lookup"><span data-stu-id="b2642-116">Slider States</span></span>  
 <span data-ttu-id="b2642-117">次の表は、<xref:System.Windows.Controls.Slider> コントロールの表示状態の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="b2642-117">The following table lists the visual states for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
|<span data-ttu-id="b2642-118">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="b2642-118">VisualState Name</span></span>|<span data-ttu-id="b2642-119">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="b2642-119">VisualStateGroup Name</span></span>|<span data-ttu-id="b2642-120">説明</span><span class="sxs-lookup"><span data-stu-id="b2642-120">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="b2642-121">標準</span><span class="sxs-lookup"><span data-stu-id="b2642-121">Normal</span></span>|<span data-ttu-id="b2642-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="b2642-122">CommonStates</span></span>|<span data-ttu-id="b2642-123">既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="b2642-123">The default state.</span></span>|  
|<span data-ttu-id="b2642-124">MouseOver</span><span class="sxs-lookup"><span data-stu-id="b2642-124">MouseOver</span></span>|<span data-ttu-id="b2642-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="b2642-125">CommonStates</span></span>|<span data-ttu-id="b2642-126">マウス ポインターがコントロール上に配置されます。</span><span class="sxs-lookup"><span data-stu-id="b2642-126">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="b2642-127">無効</span><span class="sxs-lookup"><span data-stu-id="b2642-127">Disabled</span></span>|<span data-ttu-id="b2642-128">CommonStates</span><span class="sxs-lookup"><span data-stu-id="b2642-128">CommonStates</span></span>|<span data-ttu-id="b2642-129">コントロールが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="b2642-129">The control is disabled.</span></span>|  
|<span data-ttu-id="b2642-130">フォーカスされている</span><span class="sxs-lookup"><span data-stu-id="b2642-130">Focused</span></span>|<span data-ttu-id="b2642-131">FocusStates</span><span class="sxs-lookup"><span data-stu-id="b2642-131">FocusStates</span></span>|<span data-ttu-id="b2642-132">コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="b2642-132">The control has focus.</span></span>|  
|<span data-ttu-id="b2642-133">フォーカスされていない</span><span class="sxs-lookup"><span data-stu-id="b2642-133">Unfocused</span></span>|<span data-ttu-id="b2642-134">FocusStates</span><span class="sxs-lookup"><span data-stu-id="b2642-134">FocusStates</span></span>|<span data-ttu-id="b2642-135">コントロールにフォーカスがありません。</span><span class="sxs-lookup"><span data-stu-id="b2642-135">The control does not have focus.</span></span>|  
|<span data-ttu-id="b2642-136">有効</span><span class="sxs-lookup"><span data-stu-id="b2642-136">Valid</span></span>|<span data-ttu-id="b2642-137">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b2642-137">ValidationStates</span></span>|<span data-ttu-id="b2642-138">このコントロールで <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false` です。</span><span class="sxs-lookup"><span data-stu-id="b2642-138">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="b2642-139">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="b2642-139">InvalidFocused</span></span>|<span data-ttu-id="b2642-140">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b2642-140">ValidationStates</span></span>|<span data-ttu-id="b2642-141"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがある `true` です。</span><span class="sxs-lookup"><span data-stu-id="b2642-141">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="b2642-142">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="b2642-142">InvalidUnfocused</span></span>|<span data-ttu-id="b2642-143">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b2642-143">ValidationStates</span></span>|<span data-ttu-id="b2642-144"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがない `true` です。</span><span class="sxs-lookup"><span data-stu-id="b2642-144">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="slider-controltemplate-example"></a><span data-ttu-id="b2642-145">Slider の ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="b2642-145">Slider ControlTemplate Example</span></span>  
 <span data-ttu-id="b2642-146">次の例は、<xref:System.Windows.Controls.Slider> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b2642-146">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Slider](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/slider.xaml#slider)]  
  
 <span data-ttu-id="b2642-147">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="b2642-147">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="b2642-148">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2642-148">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2642-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="b2642-149">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="b2642-150">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="b2642-150">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="b2642-151">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="b2642-151">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="b2642-152">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="b2642-152">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="b2642-153">コントロールのためのテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="b2642-153">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
