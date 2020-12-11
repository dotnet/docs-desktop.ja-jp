---
title: ToolTip のスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], ToolTip
- styles [WPF], ToolTip
- states [WPF], ToolTip
- ToolTip [WPF], styles and templates
- ControlTemplate [WPF], ToolTip
- templates [WPF], ToolTip
ms.assetid: 405fe385-4de9-49ee-a448-d8f4d1f740dd
ms.openlocfilehash: bc77555a7663bf1e4cd8cea82d43bf3bd2c33b53
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985972"
---
# <a name="tooltip-styles-and-templates"></a><span data-ttu-id="2cf4f-102">ToolTip のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="2cf4f-102">ToolTip Styles and Templates</span></span>
<span data-ttu-id="2cf4f-103">このトピックでは、<xref:System.Windows.Controls.ToolTip> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2cf4f-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ToolTip> control.</span></span> <span data-ttu-id="2cf4f-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="2cf4f-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="2cf4f-105">詳細については、「[コントロールのためにテンプレートを作成する](/dotnet/desktop-wpf/themes/how-to-create-apply-template)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2cf4f-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>  
  
## <a name="tooltip-parts"></a><span data-ttu-id="2cf4f-106">ToolTip のパーツ</span><span class="sxs-lookup"><span data-stu-id="2cf4f-106">ToolTip Parts</span></span>  
 <span data-ttu-id="2cf4f-107"><xref:System.Windows.Controls.ToolTip> コントロールに名前付きパーツはありません。</span><span class="sxs-lookup"><span data-stu-id="2cf4f-107">The <xref:System.Windows.Controls.ToolTip> control does not have any named parts.</span></span>  
  
## <a name="tooltip-states"></a><span data-ttu-id="2cf4f-108">ToolTip の状態</span><span class="sxs-lookup"><span data-stu-id="2cf4f-108">ToolTip States</span></span>  
 <span data-ttu-id="2cf4f-109">次の表は、<xref:System.Windows.Controls.ToolTip> コントロールの表示状態の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="2cf4f-109">The following table lists the visual states for the <xref:System.Windows.Controls.ToolTip> control.</span></span>  
  
|<span data-ttu-id="2cf4f-110">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="2cf4f-110">VisualState Name</span></span>|<span data-ttu-id="2cf4f-111">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="2cf4f-111">VisualStateGroup Name</span></span>|<span data-ttu-id="2cf4f-112">説明</span><span class="sxs-lookup"><span data-stu-id="2cf4f-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="2cf4f-113">Closed</span><span class="sxs-lookup"><span data-stu-id="2cf4f-113">Closed</span></span>|<span data-ttu-id="2cf4f-114">OpenStates</span><span class="sxs-lookup"><span data-stu-id="2cf4f-114">OpenStates</span></span>|<span data-ttu-id="2cf4f-115">既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="2cf4f-115">The default state.</span></span>|  
|<span data-ttu-id="2cf4f-116">開く</span><span class="sxs-lookup"><span data-stu-id="2cf4f-116">Open</span></span>|<span data-ttu-id="2cf4f-117">OpenStates</span><span class="sxs-lookup"><span data-stu-id="2cf4f-117">OpenStates</span></span>|<span data-ttu-id="2cf4f-118"><xref:System.Windows.Controls.ToolTip> が表示されています。</span><span class="sxs-lookup"><span data-stu-id="2cf4f-118">The <xref:System.Windows.Controls.ToolTip> is visible.</span></span>|  
|<span data-ttu-id="2cf4f-119">有効</span><span class="sxs-lookup"><span data-stu-id="2cf4f-119">Valid</span></span>|<span data-ttu-id="2cf4f-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="2cf4f-120">ValidationStates</span></span>|<span data-ttu-id="2cf4f-121">このコントロールで <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false` です。</span><span class="sxs-lookup"><span data-stu-id="2cf4f-121">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="2cf4f-122">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="2cf4f-122">InvalidFocused</span></span>|<span data-ttu-id="2cf4f-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="2cf4f-123">ValidationStates</span></span>|<span data-ttu-id="2cf4f-124"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがある `true` です。</span><span class="sxs-lookup"><span data-stu-id="2cf4f-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="2cf4f-125">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="2cf4f-125">InvalidUnfocused</span></span>|<span data-ttu-id="2cf4f-126">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="2cf4f-126">ValidationStates</span></span>|<span data-ttu-id="2cf4f-127"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがない `true` です。</span><span class="sxs-lookup"><span data-stu-id="2cf4f-127">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="tooltip-controltemplate-example"></a><span data-ttu-id="2cf4f-128">ToolTip の ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="2cf4f-128">ToolTip ControlTemplate Example</span></span>  
 <span data-ttu-id="2cf4f-129">次の例は、<xref:System.Windows.Controls.ToolTip> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="2cf4f-129">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ToolTip> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/tooltip.xaml#tooltip)]  
  
 <span data-ttu-id="2cf4f-130">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="2cf4f-130">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="2cf4f-131">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2cf4f-131">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cf4f-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="2cf4f-132">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="2cf4f-133">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="2cf4f-133">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="2cf4f-134">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="2cf4f-134">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="2cf4f-135">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="2cf4f-135">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="2cf4f-136">コントロールのためのテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="2cf4f-136">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
