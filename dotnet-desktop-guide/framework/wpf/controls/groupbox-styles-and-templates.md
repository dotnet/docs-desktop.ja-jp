---
title: GroupBox のスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], GroupBox
- parts [WPF], GroupBox
- GroupBox [WPF], styles and templates
- states [WPF], GroupBox
- styles [WPF], GroupBox
- templates [WPF], GroupBox
ms.assetid: 33df7037-0a1b-476f-b9d0-41566a777699
ms.openlocfilehash: 8648c284a1da3e7d629bec91210c8dd5ecdb8484
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983616"
---
# <a name="groupbox-styles-and-templates"></a><span data-ttu-id="1bba7-102">GroupBox のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="1bba7-102">GroupBox Styles and Templates</span></span>
<a name="introduction"></a> <span data-ttu-id="1bba7-103">このトピックでは、<xref:System.Windows.Controls.GroupBox> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1bba7-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.GroupBox> control.</span></span> <span data-ttu-id="1bba7-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="1bba7-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="1bba7-105">詳細については、「[コントロールのためにテンプレートを作成する](/dotnet/desktop-wpf/themes/how-to-create-apply-template)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1bba7-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>  
  
<a name="groupbox_parts"></a>
## <a name="groupbox-parts"></a><span data-ttu-id="1bba7-106">GroupBox のパーツ</span><span class="sxs-lookup"><span data-stu-id="1bba7-106">GroupBox Parts</span></span>  
 <span data-ttu-id="1bba7-107"><xref:System.Windows.Controls.GroupBox> コントロールに名前付きパーツはありません。</span><span class="sxs-lookup"><span data-stu-id="1bba7-107">The <xref:System.Windows.Controls.GroupBox> control does not have any named parts.</span></span>  
  
<a name="groupbox_states"></a>
## <a name="groupbox-states"></a><span data-ttu-id="1bba7-108">GroupBox の状態</span><span class="sxs-lookup"><span data-stu-id="1bba7-108">GroupBox States</span></span>  
 <span data-ttu-id="1bba7-109">次の表は、<xref:System.Windows.Controls.GroupBox> コントロールの表示状態の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="1bba7-109">The following table lists the visual states for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
|<span data-ttu-id="1bba7-110">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="1bba7-110">VisualState Name</span></span>|<span data-ttu-id="1bba7-111">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="1bba7-111">VisualStateGroup Name</span></span>|<span data-ttu-id="1bba7-112">説明</span><span class="sxs-lookup"><span data-stu-id="1bba7-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="1bba7-113">有効</span><span class="sxs-lookup"><span data-stu-id="1bba7-113">Valid</span></span>|<span data-ttu-id="1bba7-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="1bba7-114">ValidationStates</span></span>|<span data-ttu-id="1bba7-115">コントロールでは <xref:System.Windows.Controls.Validation> クラスが使用されていて、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false` です。</span><span class="sxs-lookup"><span data-stu-id="1bba7-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="1bba7-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="1bba7-116">InvalidFocused</span></span>|<span data-ttu-id="1bba7-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="1bba7-117">ValidationStates</span></span>|<span data-ttu-id="1bba7-118"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `true` で、コントロールにフォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="1bba7-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="1bba7-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="1bba7-119">InvalidUnfocused</span></span>|<span data-ttu-id="1bba7-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="1bba7-120">ValidationStates</span></span>|<span data-ttu-id="1bba7-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `true` で、コントロールにフォーカスはありません。</span><span class="sxs-lookup"><span data-stu-id="1bba7-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
<a name="groupbox_controltemplate_example"></a>
## <a name="groupbox-controltemplate-example"></a><span data-ttu-id="1bba7-122">GroupBox の ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="1bba7-122">GroupBox ControlTemplate Example</span></span>  
 <span data-ttu-id="1bba7-123">次の例は、<xref:System.Windows.Controls.GroupBox> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="1bba7-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#GroupBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/groupbox.xaml#groupbox)]  
  
 <span data-ttu-id="1bba7-124"><xref:System.Windows.Controls.ControlTemplate> では、次のリソースを 1 つ以上使用します。</span><span class="sxs-lookup"><span data-stu-id="1bba7-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="1bba7-125">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bba7-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bba7-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="1bba7-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="1bba7-127">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="1bba7-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="1bba7-128">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="1bba7-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="1bba7-129">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="1bba7-129">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="1bba7-130">コントロールのためのテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="1bba7-130">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
