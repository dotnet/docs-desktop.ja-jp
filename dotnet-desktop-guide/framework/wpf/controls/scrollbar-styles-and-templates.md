---
title: ScrollBar のスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], ScrollBar
- ControlTemplate [WPF], ScrollBar
- states [WPF], ScrollBar
- ScrollBar [WPF], styles and templates
- templates [WPF], ScrollBar
- parts [WPF], ScrollBar
ms.assetid: 066ea45a-e27d-43b0-adfe-cce6934c22f5
ms.openlocfilehash: 4c4a0e4eeb6d9d58470973dc8ae1877b8fef9bde
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983676"
---
# <a name="scrollbar-styles-and-templates"></a><span data-ttu-id="e377d-102">ScrollBar のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="e377d-102">ScrollBar Styles and Templates</span></span>
<span data-ttu-id="e377d-103">このトピックでは、<xref:System.Windows.Controls.Primitives.ScrollBar> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e377d-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span> <span data-ttu-id="e377d-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="e377d-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="e377d-105">詳細については、「[コントロールのためにテンプレートを作成する](/dotnet/desktop-wpf/themes/how-to-create-apply-template)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e377d-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>  
  
## <a name="scrollbar-parts"></a><span data-ttu-id="e377d-106">ScrollBar のパーツ</span><span class="sxs-lookup"><span data-stu-id="e377d-106">ScrollBar Parts</span></span>  
 <span data-ttu-id="e377d-107">次の表は、<xref:System.Windows.Controls.Primitives.ScrollBar> コントロールの名前付きパーツの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="e377d-107">The following table lists the named parts for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="e377d-108">パーツ</span><span class="sxs-lookup"><span data-stu-id="e377d-108">Part</span></span>|<span data-ttu-id="e377d-109">種類</span><span class="sxs-lookup"><span data-stu-id="e377d-109">Type</span></span>|<span data-ttu-id="e377d-110">説明</span><span class="sxs-lookup"><span data-stu-id="e377d-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="e377d-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="e377d-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="e377d-112"><xref:System.Windows.Controls.Primitives.ScrollBar> の位置を示す要素のコンテナー。</span><span class="sxs-lookup"><span data-stu-id="e377d-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Primitives.ScrollBar>.</span></span>|  
  
## <a name="scrollbar-states"></a><span data-ttu-id="e377d-113">ScrollBar の状態</span><span class="sxs-lookup"><span data-stu-id="e377d-113">ScrollBar States</span></span>  
 <span data-ttu-id="e377d-114">次の表は、<xref:System.Windows.Controls.Primitives.ScrollBar> コントロールの表示状態の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="e377d-114">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="e377d-115">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="e377d-115">VisualState Name</span></span>|<span data-ttu-id="e377d-116">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="e377d-116">VisualStateGroup Name</span></span>|<span data-ttu-id="e377d-117">説明</span><span class="sxs-lookup"><span data-stu-id="e377d-117">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="e377d-118">標準</span><span class="sxs-lookup"><span data-stu-id="e377d-118">Normal</span></span>|<span data-ttu-id="e377d-119">CommonStates</span><span class="sxs-lookup"><span data-stu-id="e377d-119">CommonStates</span></span>|<span data-ttu-id="e377d-120">既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="e377d-120">The default state.</span></span>|  
|<span data-ttu-id="e377d-121">MouseOver</span><span class="sxs-lookup"><span data-stu-id="e377d-121">MouseOver</span></span>|<span data-ttu-id="e377d-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="e377d-122">CommonStates</span></span>|<span data-ttu-id="e377d-123">マウス ポインターがコントロール上に配置されます。</span><span class="sxs-lookup"><span data-stu-id="e377d-123">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="e377d-124">無効</span><span class="sxs-lookup"><span data-stu-id="e377d-124">Disabled</span></span>|<span data-ttu-id="e377d-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="e377d-125">CommonStates</span></span>|<span data-ttu-id="e377d-126">コントロールが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="e377d-126">The control is disabled.</span></span>|  
|<span data-ttu-id="e377d-127">有効</span><span class="sxs-lookup"><span data-stu-id="e377d-127">Valid</span></span>|<span data-ttu-id="e377d-128">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e377d-128">ValidationStates</span></span>|<span data-ttu-id="e377d-129">このコントロールで <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false` です。</span><span class="sxs-lookup"><span data-stu-id="e377d-129">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="e377d-130">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="e377d-130">InvalidFocused</span></span>|<span data-ttu-id="e377d-131">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e377d-131">ValidationStates</span></span>|<span data-ttu-id="e377d-132"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `true` で、コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="e377d-132">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="e377d-133">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="e377d-133">InvalidUnfocused</span></span>|<span data-ttu-id="e377d-134">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e377d-134">ValidationStates</span></span>|<span data-ttu-id="e377d-135"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `true` で、コントロールにフォーカスがありません。</span><span class="sxs-lookup"><span data-stu-id="e377d-135">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="scrollbar-controltemplate-example"></a><span data-ttu-id="e377d-136">ScrollBar の ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="e377d-136">ScrollBar ControlTemplate Example</span></span>  
 <span data-ttu-id="e377d-137">次の例は、<xref:System.Windows.Controls.Primitives.ScrollBar> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e377d-137">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#scrollbar)]  
  
 <span data-ttu-id="e377d-138">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="e377d-138">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="e377d-139">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e377d-139">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e377d-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="e377d-140">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="e377d-141">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="e377d-141">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="e377d-142">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="e377d-142">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="e377d-143">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="e377d-143">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="e377d-144">コントロールのためのテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="e377d-144">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
