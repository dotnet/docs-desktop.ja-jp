---
title: ScrollViewer のスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], ScrollViewer
- states [WPF], ScrollViewer
- styles [WPF], ScrollViewer
- templates [WPF], ScrollViewer
- ControlTemplate [WPF], ScrollViewer
- ScrollViewer [WPF], styles and templates
ms.assetid: dffdd822-ae69-4946-abaf-710860cd65b2
ms.openlocfilehash: a33e99ed31b9154bcfacde988bc38c3852331722
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982043"
---
# <a name="scrollviewer-styles-and-templates"></a><span data-ttu-id="cafe6-102">ScrollViewer のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="cafe6-102">ScrollViewer Styles and Templates</span></span>
<span data-ttu-id="cafe6-103">このトピックでは、<xref:System.Windows.Controls.ScrollViewer> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="cafe6-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span> <span data-ttu-id="cafe6-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="cafe6-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="cafe6-105">詳細については、「[コントロールのためにテンプレートを作成する](/dotnet/desktop-wpf/themes/how-to-create-apply-template)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cafe6-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>  
  
## <a name="scrollviewer-parts"></a><span data-ttu-id="cafe6-106">ScrollViewer のパーツ</span><span class="sxs-lookup"><span data-stu-id="cafe6-106">ScrollViewer Parts</span></span>  
 <span data-ttu-id="cafe6-107">次の表は、<xref:System.Windows.Controls.ScrollViewer> コントロールの名前付きパーツの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="cafe6-107">The following table lists the named parts for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="cafe6-108">パーツ</span><span class="sxs-lookup"><span data-stu-id="cafe6-108">Part</span></span>|<span data-ttu-id="cafe6-109">種類</span><span class="sxs-lookup"><span data-stu-id="cafe6-109">Type</span></span>|<span data-ttu-id="cafe6-110">説明</span><span class="sxs-lookup"><span data-stu-id="cafe6-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="cafe6-111">PART_ScrollContentPresenter</span><span class="sxs-lookup"><span data-stu-id="cafe6-111">PART_ScrollContentPresenter</span></span>|<xref:System.Windows.Controls.ScrollContentPresenter>|<span data-ttu-id="cafe6-112"><xref:System.Windows.Controls.ScrollViewer> のコンテンツのプレースホルダー。</span><span class="sxs-lookup"><span data-stu-id="cafe6-112">The placeholder for content in the <xref:System.Windows.Controls.ScrollViewer>.</span></span>|  
|<span data-ttu-id="cafe6-113">PART_HorizontalScrollBar</span><span class="sxs-lookup"><span data-stu-id="cafe6-113">PART_HorizontalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="cafe6-114">コンテンツを水平方向にスクロールするために使用する <xref:System.Windows.Controls.Primitives.ScrollBar>。</span><span class="sxs-lookup"><span data-stu-id="cafe6-114">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content horizontally.</span></span>|  
|<span data-ttu-id="cafe6-115">PART_VerticalScrollBar</span><span class="sxs-lookup"><span data-stu-id="cafe6-115">PART_VerticalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="cafe6-116">コンテンツを垂直方向にスクロールするために使用する <xref:System.Windows.Controls.Primitives.ScrollBar>。</span><span class="sxs-lookup"><span data-stu-id="cafe6-116">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content vertically.</span></span>|  
  
## <a name="scrollviewer-states"></a><span data-ttu-id="cafe6-117">ScrollViewer の状態</span><span class="sxs-lookup"><span data-stu-id="cafe6-117">ScrollViewer States</span></span>  
 <span data-ttu-id="cafe6-118">次の表は、<xref:System.Windows.Controls.ScrollViewer> コントロールの表示状態の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="cafe6-118">The following table lists the visual states for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="cafe6-119">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="cafe6-119">VisualState Name</span></span>|<span data-ttu-id="cafe6-120">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="cafe6-120">VisualStateGroup Name</span></span>|<span data-ttu-id="cafe6-121">説明</span><span class="sxs-lookup"><span data-stu-id="cafe6-121">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="cafe6-122">有効</span><span class="sxs-lookup"><span data-stu-id="cafe6-122">Valid</span></span>|<span data-ttu-id="cafe6-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="cafe6-123">ValidationStates</span></span>|<span data-ttu-id="cafe6-124">このコントロールで <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false` です。</span><span class="sxs-lookup"><span data-stu-id="cafe6-124">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="cafe6-125">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="cafe6-125">InvalidFocused</span></span>|<span data-ttu-id="cafe6-126">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="cafe6-126">ValidationStates</span></span>|<span data-ttu-id="cafe6-127"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがある `true` です。</span><span class="sxs-lookup"><span data-stu-id="cafe6-127">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="cafe6-128">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="cafe6-128">InvalidUnfocused</span></span>|<span data-ttu-id="cafe6-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="cafe6-129">ValidationStates</span></span>|<span data-ttu-id="cafe6-130"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがない `true` です。</span><span class="sxs-lookup"><span data-stu-id="cafe6-130">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="scrollviewer-controltemplate-example"></a><span data-ttu-id="cafe6-131">ScrollViewer の ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="cafe6-131">ScrollViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="cafe6-132">次の例は、<xref:System.Windows.Controls.ScrollViewer> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="cafe6-132">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollviewer.xaml#scrollviewer)]  
  
 <span data-ttu-id="cafe6-133">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="cafe6-133">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="cafe6-134">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cafe6-134">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cafe6-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="cafe6-135">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="cafe6-136">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="cafe6-136">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="cafe6-137">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="cafe6-137">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="cafe6-138">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="cafe6-138">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="cafe6-139">コントロールのためのテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="cafe6-139">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
