---
title: DocumentViewer のスタイルとテンプレート
ms.date: 03/30/2017
helpviewer_keywords:
- templates [WPF], DocumentViewer
- DocumentViewer [WPF], styles and templates
- states [WPF], DocumentViewer
- ControlTemplate [WPF], DocumentViewer
- parts [WPF], DocumentViewer
- styles [WPF], DocumentViewer
ms.assetid: 6bd4ff8f-ea6a-4084-ac58-e7a67446ce1c
ms.openlocfilehash: 8a5d000dd67c1f5699c411db6ad1d7244ef0ad03
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985084"
---
# <a name="documentviewer-styles-and-templates"></a><span data-ttu-id="aa983-102">DocumentViewer のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="aa983-102">DocumentViewer Styles and Templates</span></span>
<span data-ttu-id="aa983-103">このトピックでは、<xref:System.Windows.Controls.DocumentViewer> コントロールのスタイルとテンプレートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="aa983-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span> <span data-ttu-id="aa983-104"><xref:System.Windows.Controls.ControlTemplate>の既定値を変更して外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="aa983-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="aa983-105">詳細については、「[コントロールのためにテンプレートを作成する](/dotnet/desktop-wpf/themes/how-to-create-apply-template)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="aa983-105">For more information, see [Create a template for a control](/dotnet/desktop-wpf/themes/how-to-create-apply-template).</span></span>  
  
## <a name="documentviewer-parts"></a><span data-ttu-id="aa983-106">DocumentViewer のパーツ</span><span class="sxs-lookup"><span data-stu-id="aa983-106">DocumentViewer Parts</span></span>  
 <span data-ttu-id="aa983-107">次の表は、<xref:System.Windows.Controls.DocumentViewer> コントロールの名前付きパーツの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="aa983-107">The following table lists the named parts for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
|<span data-ttu-id="aa983-108">パーツ</span><span class="sxs-lookup"><span data-stu-id="aa983-108">Part</span></span>|<span data-ttu-id="aa983-109">種類</span><span class="sxs-lookup"><span data-stu-id="aa983-109">Type</span></span>|<span data-ttu-id="aa983-110">説明</span><span class="sxs-lookup"><span data-stu-id="aa983-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="aa983-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="aa983-111">PART_ContentHost</span></span>|<xref:System.Windows.Controls.ScrollViewer>|<span data-ttu-id="aa983-112">コンテンツとスクロール領域。</span><span class="sxs-lookup"><span data-stu-id="aa983-112">The content and scrolling area.</span></span>|  
|<span data-ttu-id="aa983-113">PART_FindToolBarHost</span><span class="sxs-lookup"><span data-stu-id="aa983-113">PART_FindToolBarHost</span></span>|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="aa983-114">既定で一番下に配置される検索ボックス。</span><span class="sxs-lookup"><span data-stu-id="aa983-114">The search box, at the bottom by default.</span></span>|  
  
## <a name="documentviewer-states"></a><span data-ttu-id="aa983-115">DocumentViewer の状態</span><span class="sxs-lookup"><span data-stu-id="aa983-115">DocumentViewer States</span></span>  
 <span data-ttu-id="aa983-116">次の表は、<xref:System.Windows.Controls.DocumentViewer> コントロールの表示状態の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="aa983-116">The following table lists the visual states for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
|<span data-ttu-id="aa983-117">VisualState 名</span><span class="sxs-lookup"><span data-stu-id="aa983-117">VisualState Name</span></span>|<span data-ttu-id="aa983-118">VisualStateGroup 名</span><span class="sxs-lookup"><span data-stu-id="aa983-118">VisualStateGroup Name</span></span>|<span data-ttu-id="aa983-119">説明</span><span class="sxs-lookup"><span data-stu-id="aa983-119">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="aa983-120">有効</span><span class="sxs-lookup"><span data-stu-id="aa983-120">Valid</span></span>|<span data-ttu-id="aa983-121">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="aa983-121">ValidationStates</span></span>|<span data-ttu-id="aa983-122">このコントロールで <xref:System.Windows.Controls.Validation> クラスを使用し、<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは `false` です。</span><span class="sxs-lookup"><span data-stu-id="aa983-122">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="aa983-123">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="aa983-123">InvalidFocused</span></span>|<span data-ttu-id="aa983-124">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="aa983-124">ValidationStates</span></span>|<span data-ttu-id="aa983-125"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがある `true` です。</span><span class="sxs-lookup"><span data-stu-id="aa983-125">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="aa983-126">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="aa983-126">InvalidUnfocused</span></span>|<span data-ttu-id="aa983-127">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="aa983-127">ValidationStates</span></span>|<span data-ttu-id="aa983-128"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 添付プロパティは、コントロールにフォーカスがない `true` です。</span><span class="sxs-lookup"><span data-stu-id="aa983-128">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="documentviewer-controltemplate-example"></a><span data-ttu-id="aa983-129">DocumentViewer の ControlTemplate の例</span><span class="sxs-lookup"><span data-stu-id="aa983-129">DocumentViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="aa983-130">次の例は、<xref:System.Windows.Controls.DocumentViewer> コントロールの <xref:System.Windows.Controls.ControlTemplate> を定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="aa983-130">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#DocumentViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/documentviewer.xaml#documentviewer)]  
  
 <span data-ttu-id="aa983-131">前の例では、次のリソースの 1 つ以上を使用します。</span><span class="sxs-lookup"><span data-stu-id="aa983-131">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="aa983-132">完全なサンプルについては、[Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa983-132">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa983-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="aa983-133">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="aa983-134">コントロールのスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="aa983-134">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="aa983-135">コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="aa983-135">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="aa983-136">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="aa983-136">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="aa983-137">コントロールのためのテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="aa983-137">Create a template for a control</span></span>](/dotnet/desktop-wpf/themes/how-to-create-apply-template)
