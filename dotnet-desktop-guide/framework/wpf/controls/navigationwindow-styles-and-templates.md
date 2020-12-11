---
title: NavigationWindow のスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], NavigationWindow
- NavigationWindow [WPF], styles and templates
- ControlTemplate [WPF], NavigationWindow
- parts [WPF], NavigationWindow
- styles [WPF], NavigationWindow
- templates [WPF], NavigationWindow
ms.assetid: 3656055e-3222-43c8-b868-fd0c90cc31a3
ms.openlocfilehash: 1189a6709a77af0a777b908f6aacab90288d01e7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985123"
---
# <a name="navigationwindow-styles-and-templates"></a><span data-ttu-id="490d9-102">NavigationWindow のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="490d9-102">NavigationWindow Styles and Templates</span></span>
<span data-ttu-id="490d9-103">このトピックでは、<xref:System.Windows.Navigation.NavigationWindow> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="490d9-103">This topic describes the styles and templates for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span> <span data-ttu-id="490d9-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="490d9-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="490d9-105">詳細については、「[コントロールのためにテンプレートを作成する](/dotnet/desktop-wpf/themes/how-to-create-apply-template)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="490d9-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>  
  
## <a name="navigationwindow-parts"></a><span data-ttu-id="490d9-106">NavigationWindow のパーツ</span><span class="sxs-lookup"><span data-stu-id="490d9-106">NavigationWindow Parts</span></span>  
 <span data-ttu-id="490d9-107">次の表は、<xref:System.Windows.Navigation.NavigationWindow> コントロールの名前付きパーツの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="490d9-107">The following table lists the named parts for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span>  
  
|<span data-ttu-id="490d9-108">パーツ</span><span class="sxs-lookup"><span data-stu-id="490d9-108">Part</span></span>|<span data-ttu-id="490d9-109">種類</span><span class="sxs-lookup"><span data-stu-id="490d9-109">Type</span></span>|<span data-ttu-id="490d9-110">説明</span><span class="sxs-lookup"><span data-stu-id="490d9-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="490d9-111">PART_NavWinCP</span><span class="sxs-lookup"><span data-stu-id="490d9-111">PART_NavWinCP</span></span>|<xref:System.Windows.Controls.ContentPresenter>|<span data-ttu-id="490d9-112">コンテンツの領域。</span><span class="sxs-lookup"><span data-stu-id="490d9-112">The area for the content.</span></span>|  
  
## <a name="navigationwindow-states"></a><span data-ttu-id="490d9-113">NavigationWindow の状態</span><span class="sxs-lookup"><span data-stu-id="490d9-113">NavigationWindow States</span></span>  
 <span data-ttu-id="490d9-114">次の表は、<xref:System.Windows.Navigation.NavigationWindow> コントロールの表示状態の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="490d9-114">The following table lists the visual states for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span>  
  
|<span data-ttu-id="490d9-115">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="490d9-115">VisualState Name</span></span>|<span data-ttu-id="490d9-116">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="490d9-116">VisualStateGroup Name</span></span>|<span data-ttu-id="490d9-117">説明</span><span class="sxs-lookup"><span data-stu-id="490d9-117">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="490d9-118">有効</span><span class="sxs-lookup"><span data-stu-id="490d9-118">Valid</span></span>|<span data-ttu-id="490d9-119">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="490d9-119">ValidationStates</span></span>|<span data-ttu-id="490d9-120">このコントロールで <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false` です。</span><span class="sxs-lookup"><span data-stu-id="490d9-120">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="490d9-121">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="490d9-121">InvalidFocused</span></span>|<span data-ttu-id="490d9-122">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="490d9-122">ValidationStates</span></span>|<span data-ttu-id="490d9-123"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがある `true` です。</span><span class="sxs-lookup"><span data-stu-id="490d9-123">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="490d9-124">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="490d9-124">InvalidUnfocused</span></span>|<span data-ttu-id="490d9-125">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="490d9-125">ValidationStates</span></span>|<span data-ttu-id="490d9-126"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがない `true` です。</span><span class="sxs-lookup"><span data-stu-id="490d9-126">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="navigationwindow-controltemplate-example"></a><span data-ttu-id="490d9-127">NavigationWindow の ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="490d9-127">NavigationWindow ControlTemplate Example</span></span>  
 <span data-ttu-id="490d9-128">この例には、<xref:System.Windows.Navigation.NavigationWindow> の <xref:System.Windows.Controls.ControlTemplate> に既定で定義されているすべての要素が含まれていますが、例として特定の値を考える必要があります。</span><span class="sxs-lookup"><span data-stu-id="490d9-128">Although this example contains all of the elements that are defined in the <xref:System.Windows.Controls.ControlTemplate> of a <xref:System.Windows.Navigation.NavigationWindow> by default, the specific values should be thought of as examples.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#NavigationWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/navigationwindow.xaml#navigationwindow)]  
  
 <span data-ttu-id="490d9-129">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="490d9-129">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="490d9-130">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="490d9-130">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="490d9-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="490d9-131">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="490d9-132">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="490d9-132">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="490d9-133">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="490d9-133">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="490d9-134">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="490d9-134">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="490d9-135">コントロールのためのテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="490d9-135">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
