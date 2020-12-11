---
title: フレームのスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], Frame
- templates [WPF], Frame
- ControlTemplate [WPF], Frame
- Frame [WPF], styles and templates
- states [WPF], Frame
- styles [WPF], Frame
ms.assetid: a01c32e2-c951-46a0-a82f-2614ca241f0b
ms.openlocfilehash: 106a7a2a0138250261ce31b0cbd98173b14e749a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974942"
---
# <a name="frame-styles-and-templates"></a><span data-ttu-id="8de7a-102">フレームのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="8de7a-102">Frame Styles and Templates</span></span>
<span data-ttu-id="8de7a-103">このトピックでは、<xref:System.Windows.Controls.Frame> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8de7a-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Frame> control.</span></span> <span data-ttu-id="8de7a-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="8de7a-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="8de7a-105">詳細については、「[コントロールのためにテンプレートを作成する](/dotnet/desktop-wpf/themes/how-to-create-apply-template)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8de7a-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>  
  
## <a name="frame-parts"></a><span data-ttu-id="8de7a-106">Frame のパーツ</span><span class="sxs-lookup"><span data-stu-id="8de7a-106">Frame Parts</span></span>  
 <span data-ttu-id="8de7a-107">次の表は、<xref:System.Windows.Controls.Frame> コントロールの名前付きパーツの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="8de7a-107">The following table lists the named parts for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="8de7a-108">パーツ</span><span class="sxs-lookup"><span data-stu-id="8de7a-108">Part</span></span>|<span data-ttu-id="8de7a-109">種類</span><span class="sxs-lookup"><span data-stu-id="8de7a-109">Type</span></span>|<span data-ttu-id="8de7a-110">説明</span><span class="sxs-lookup"><span data-stu-id="8de7a-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="8de7a-111">PART_FrameCP</span><span class="sxs-lookup"><span data-stu-id="8de7a-111">PART_FrameCP</span></span>|<xref:System.Windows.Controls.ContentPresenter>|<span data-ttu-id="8de7a-112">コンテンツ領域。</span><span class="sxs-lookup"><span data-stu-id="8de7a-112">The content area.</span></span>|  
  
## <a name="frame-states"></a><span data-ttu-id="8de7a-113">Frame の状態</span><span class="sxs-lookup"><span data-stu-id="8de7a-113">Frame States</span></span>  
 <span data-ttu-id="8de7a-114">次の表は、<xref:System.Windows.Controls.Frame> コントロールの表示状態の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="8de7a-114">The following table lists the visual states for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="8de7a-115">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="8de7a-115">VisualState Name</span></span>|<span data-ttu-id="8de7a-116">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="8de7a-116">VisualStateGroup Name</span></span>|<span data-ttu-id="8de7a-117">説明</span><span class="sxs-lookup"><span data-stu-id="8de7a-117">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="8de7a-118">有効</span><span class="sxs-lookup"><span data-stu-id="8de7a-118">Valid</span></span>|<span data-ttu-id="8de7a-119">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8de7a-119">ValidationStates</span></span>|<span data-ttu-id="8de7a-120">このコントロールで <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false` です。</span><span class="sxs-lookup"><span data-stu-id="8de7a-120">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="8de7a-121">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="8de7a-121">InvalidFocused</span></span>|<span data-ttu-id="8de7a-122">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8de7a-122">ValidationStates</span></span>|<span data-ttu-id="8de7a-123"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがある `true` です。</span><span class="sxs-lookup"><span data-stu-id="8de7a-123">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="8de7a-124">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="8de7a-124">InvalidUnfocused</span></span>|<span data-ttu-id="8de7a-125">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="8de7a-125">ValidationStates</span></span>|<span data-ttu-id="8de7a-126"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがない `true` です。</span><span class="sxs-lookup"><span data-stu-id="8de7a-126">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="frame-controltemplate-example"></a><span data-ttu-id="8de7a-127">Frame の ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="8de7a-127">Frame ControlTemplate Example</span></span>  
 <span data-ttu-id="8de7a-128">次の例は、<xref:System.Windows.Controls.Frame> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="8de7a-128">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Frame](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/frame.xaml#frame)]  
  
 <span data-ttu-id="8de7a-129">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="8de7a-129">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="8de7a-130">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8de7a-130">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8de7a-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="8de7a-131">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="8de7a-132">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="8de7a-132">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="8de7a-133">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="8de7a-133">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="8de7a-134">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="8de7a-134">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="8de7a-135">コントロールのためのテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="8de7a-135">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
