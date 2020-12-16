---
title: WPF でテンプレートを作成する - .NET デスクトップ
description: Windows Presentation Foundation と .NET Core でコントロール テンプレートを作成して参照する方法について説明します。
author: adegeo
ms.author: adegeo
ms.date: 11/15/2019
no-loc:
- <Window>
- <ControlTemplate>
- <Ellipse>
- <ContentPresenter>
- <Trigger>
- <Setter>
- <PropertyTrigger>
- <Grid>
- <VisualStateManager.VisualStateGroups>
- <VisualStateGroup>
- <VisualState>
- <Storyboard>
- SizeToContent
- MinWidth
- TargetType
- Title
ms.topic: how-to
helpviewer_keywords:
- control contract [WPF]
- controls [WPF], visual structure changes
- ControlTemplate [WPF], customizing for existing controls
- skinning controls [WPF]
- controls [WPF], appearance specified by state
- templates [WPF], custom for existing controls
ms.openlocfilehash: f90b39d4aaff891d22a86f8289cb7f6280f0b64a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96942303"
---
# <a name="create-a-template-for-a-control"></a><span data-ttu-id="bcdd8-103">コントロールのためのテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="bcdd8-103">Create a template for a control</span></span>

<span data-ttu-id="bcdd8-104">Windows Presentation Foundation (WPF) を使用すると、独自の再利用可能なテンプレートを使用して、既存のコントロールの視覚的な構造と動作をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-104">With Windows Presentation Foundation (WPF), you can customize an existing control's visual structure and behavior with your own reusable template.</span></span> <span data-ttu-id="bcdd8-105">テンプレートは、アプリケーション、ウィンドウ、ページにグローバルに適用することも、コントロールに直接適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-105">Templates can be applied globally to your application, windows and pages, or directly to controls.</span></span> <span data-ttu-id="bcdd8-106">新しいコントロールを作成する必要があるほとんどのシナリオは、代わりに既存のコントロール用の新しいテンプレートを作成することによってカバーできます。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-106">Most scenarios that require you to create a new control can be covered by instead creating a new template for an existing control.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

<span data-ttu-id="bcdd8-107">この記事では、<xref:System.Windows.Controls.Button> コントロールの新しい <xref:System.Windows.Controls.ControlTemplate> を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-107">In this article, you'll explore creating a new <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Button> control.</span></span>

## <a name="when-to-create-a-controltemplate"></a><span data-ttu-id="bcdd8-108">ControlTemplate を作成するタイミング</span><span class="sxs-lookup"><span data-stu-id="bcdd8-108">When to create a ControlTemplate</span></span>

<span data-ttu-id="bcdd8-109">コントロールには、<xref:System.Windows.Controls.Border.Background%2A>、<xref:System.Windows.Controls.Control.Foreground%2A>、<xref:System.Windows.Controls.Control.FontFamily%2A> などの多くのプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-109">Controls have many properties, such as <xref:System.Windows.Controls.Border.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>, and <xref:System.Windows.Controls.Control.FontFamily%2A>.</span></span> <span data-ttu-id="bcdd8-110">これらのプロパティは、コントロールの外観のさまざまな側面を制御しますが、これらのプロパティを設定することによって行うことができる変更は制限されます。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-110">These properties control different aspects of the control's appearance, but the changes that you can make by setting these properties are limited.</span></span> <span data-ttu-id="bcdd8-111">たとえば、<xref:System.Windows.Controls.CheckBox> では、<xref:System.Windows.Controls.Control.Foreground%2A> プロパティを青に、<xref:System.Windows.Controls.Control.FontStyle%2A> を斜体に設定できます。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-111">For example, you can set the <xref:System.Windows.Controls.Control.Foreground%2A> property to blue and <xref:System.Windows.Controls.Control.FontStyle%2A> to italic on a <xref:System.Windows.Controls.CheckBox>.</span></span> <span data-ttu-id="bcdd8-112">コントロールの他のプロパティを設定するだけでは、必要な外見のカスタマイズが十分にできない場合は、<xref:System.Windows.Controls.ControlTemplate> を作成します。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-112">When you want to customize the control's appearance beyond what setting the other properties on the control can do, you create a <xref:System.Windows.Controls.ControlTemplate>.</span></span>

<span data-ttu-id="bcdd8-113">ほとんどのユーザー インターフェイスのボタンの外観はテキストが記載されている四角形で、基本的には同じです。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-113">In most user interfaces, a button has the same general appearance: a rectangle with some text.</span></span> <span data-ttu-id="bcdd8-114">丸いボタンを作成する場合は、ボタンを継承する新しいコントロールを作成するか、ボタンの機能を再作成します。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-114">If you wanted to create a rounded button, you could create a new control that inherits from the button or recreates the functionality of the button.</span></span> <span data-ttu-id="bcdd8-115">さらに、新しいユーザー コントロールによって、円形のビジュアルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-115">In addition, the new user control would provide the circular visual.</span></span>

<span data-ttu-id="bcdd8-116">新しいコントロールを作成しないようにするには、既存のコントロールの視覚的なレイアウトをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-116">You can avoid creating new controls by customizing the visual layout of an existing control.</span></span> <span data-ttu-id="bcdd8-117">丸いボタンを使用して、目的の視覚的なレイアウトで <xref:System.Windows.Controls.ControlTemplate> を作成します。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-117">With a rounded button, you create a <xref:System.Windows.Controls.ControlTemplate> with the desired visual layout.</span></span>

<span data-ttu-id="bcdd8-118">一方、新しい機能、異なるプロパティ、および新しい設定を持つコントロールが必要な場合は、新しい <xref:System.Windows.Controls.UserControl> を作成します。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-118">On the other hand, if you need a control with new functionality, different properties, and new settings, you would create a new <xref:System.Windows.Controls.UserControl>.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bcdd8-119">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="bcdd8-119">Prerequisites</span></span>

<span data-ttu-id="bcdd8-120">新しい WPF アプリケーションを作成し、*MainWindow.xaml* (または任意の別のウィンドウ) の **\<Window>** 要素で次のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-120">Create a new WPF application and in *MainWindow.xaml* (or another window of your choice) set the following properties on the **\<Window>** element:</span></span>

|     |     |
| --- | --- |
| **Title**         | `Template Intro Sample` |
| **SizeToContent** | `WidthAndHeight` |
| **MinWidth**      | `250` |

<span data-ttu-id="bcdd8-121">**\<Window>** 要素のコンテンツを次の XAML に設定します。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-121">Set the content of the **\<Window>** element to the following XAML:</span></span>

[!code-xaml[Initial](./snippets/how-to-create-apply-template/csharp/Window1.xaml#Initial)]

<span data-ttu-id="bcdd8-122">最終的に、*MainWindow.xaml* ファイルは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-122">In the end, the *MainWindow.xaml* file should look similar to the following:</span></span>

[!code-xaml[InitialWhole](./snippets/how-to-create-apply-template/csharp/Window1.xaml#InitialWhole)]

<span data-ttu-id="bcdd8-123">アプリケーションを実行すると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-123">If you run the application, it looks like the following:</span></span>

![スタイルが設定されていない 2 つのボタンがある WPF ウィンドウ](media/create-apply-template/unstyled-button.png)

## <a name="create-a-controltemplate"></a><span data-ttu-id="bcdd8-125">ControlTemplate の作成</span><span class="sxs-lookup"><span data-stu-id="bcdd8-125">Create a ControlTemplate</span></span>

<span data-ttu-id="bcdd8-126"><xref:System.Windows.Controls.ControlTemplate> を宣言する最も一般的な方法は、XAML ファイルの `Resources` セクションのリソースとして宣言する方法です。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-126">The most common way to declare a <xref:System.Windows.Controls.ControlTemplate> is as a resource in the `Resources` section in a XAML file.</span></span> <span data-ttu-id="bcdd8-127">テンプレートはリソースなので、すべてのリソースに適用されるものと同じスコープ規則に従います。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-127">Because templates are resources, they obey the same scoping rules that apply to all resources.</span></span> <span data-ttu-id="bcdd8-128">つまり、テンプレートの宣言場所は、テンプレートの適用場所に影響するということです。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-128">Put simply, where you declare a template affects where the template can be applied.</span></span> <span data-ttu-id="bcdd8-129">たとえば、アプリケーション定義 XAML ファイルのルート要素でテンプレートを宣言すると、そのテンプレートはアプリケーションのどこでも使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-129">For example, if you declare the template in the root element of your application definition XAML file, the template can be used anywhere in your application.</span></span> <span data-ttu-id="bcdd8-130">ウィンドウでテンプレートを定義すると、そのテンプレートはウィンドウ内のコントロールでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-130">If you define the template in a window, only the controls in that window can use the template.</span></span>

<span data-ttu-id="bcdd8-131">まず、*MainWindow.xaml* ファイルに `Window.Resources` 要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-131">To start with, add a `Window.Resources` element to your *MainWindow.xaml* file:</span></span>

[!code-xaml[WindowResStart](./snippets/how-to-create-apply-template/csharp/Window2.xaml#WindowResStart)]

<span data-ttu-id="bcdd8-132">次のプロパティ セットで新しい **\<ControlTemplate>** を作成します。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-132">Create a new **\<ControlTemplate>** with the following properties set:</span></span>

|     |     |
| --- | --- |
| <span data-ttu-id="bcdd8-133">**x:Key**</span><span class="sxs-lookup"><span data-stu-id="bcdd8-133">**x:Key**</span></span>         | `roundbutton` |
| **TargetType**    | `Button` |

<span data-ttu-id="bcdd8-134">このコントロール テンプレートは単純です。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-134">This control template will be simple:</span></span>

- <span data-ttu-id="bcdd8-135">コントロールのルート要素である <xref:System.Windows.Controls.Grid></span><span class="sxs-lookup"><span data-stu-id="bcdd8-135">a root element for the control, a <xref:System.Windows.Controls.Grid></span></span>
- <span data-ttu-id="bcdd8-136">ボタンの丸みのある外観を描画するための <xref:System.Windows.Shapes.Ellipse></span><span class="sxs-lookup"><span data-stu-id="bcdd8-136">an <xref:System.Windows.Shapes.Ellipse> to draw the rounded appearance of the button</span></span>
- <span data-ttu-id="bcdd8-137">ユーザー指定のボタンの内容を表示する <xref:System.Windows.Controls.ContentPresenter></span><span class="sxs-lookup"><span data-stu-id="bcdd8-137">a <xref:System.Windows.Controls.ContentPresenter> to display the user-specified button content</span></span>

[!code-xaml[ControlTemplate](./snippets/how-to-create-apply-template/csharp/Window3.xaml#ControlTemplate)]

### <a name="templatebinding"></a><span data-ttu-id="bcdd8-138">TemplateBinding</span><span class="sxs-lookup"><span data-stu-id="bcdd8-138">TemplateBinding</span></span>

<span data-ttu-id="bcdd8-139">新しい <xref:System.Windows.Controls.ControlTemplate> を作成した場合も、パブリック プロパティを使用して、コントロールの外観を変更する必要が生じる場合があります。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-139">When you create a new <xref:System.Windows.Controls.ControlTemplate>, you still might want to use the public properties to change the control's appearance.</span></span> <span data-ttu-id="bcdd8-140">[TemplateBinding](../../../framework/wpf/advanced/templatebinding-markup-extension.md) のマークアップ拡張機能は、<xref:System.Windows.Controls.ControlTemplate> 内の要素のプロパティを、コントロールで定義されたパブリック プロパティにバインドする機能です。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-140">The [TemplateBinding](../../../framework/wpf/advanced/templatebinding-markup-extension.md) markup extension binds a property of an element that is in the <xref:System.Windows.Controls.ControlTemplate> to a public property that is defined by the control.</span></span> <span data-ttu-id="bcdd8-141">[TemplateBinding](../../../framework/wpf/advanced/templatebinding-markup-extension.md) を使用すると、コントロールのプロパティをテンプレートのパラメーターとして機能させることができます。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-141">When you use a [TemplateBinding](../../../framework/wpf/advanced/templatebinding-markup-extension.md), you enable properties on the control to act as parameters to the template.</span></span> <span data-ttu-id="bcdd8-142">つまり、コントロールのプロパティを設定すると、その値は [TemplateBinding](../../../framework/wpf/advanced/templatebinding-markup-extension.md) が機能している要素に渡されます。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-142">That is, when a property on a control is set, that value is passed on to the element that has the [TemplateBinding](../../../framework/wpf/advanced/templatebinding-markup-extension.md) on it.</span></span>

### <a name="ellipse"></a><span data-ttu-id="bcdd8-143">Ellipse</span><span class="sxs-lookup"><span data-stu-id="bcdd8-143">Ellipse</span></span>

<span data-ttu-id="bcdd8-144">**\<Ellipse>** 要素の **:::no-loc text="Fill":::** および **:::no-loc text="Stroke":::** プロパティが、コントロールの <xref:System.Windows.Controls.Control.Foreground> と <xref:System.Windows.Controls.Control.Background> プロパティにバインドされていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-144">Notice that the **:::no-loc text="Fill":::** and **:::no-loc text="Stroke":::** properties of the **\<Ellipse>** element are bound to the control's <xref:System.Windows.Controls.Control.Foreground> and <xref:System.Windows.Controls.Control.Background> properties.</span></span>

### <a name="contentpresenter"></a><span data-ttu-id="bcdd8-145">ContentPresenter</span><span class="sxs-lookup"><span data-stu-id="bcdd8-145">ContentPresenter</span></span>

<span data-ttu-id="bcdd8-146">[\<ContentPresenter>](xref:System.Windows.Controls.ContentPresenter) 要素もテンプレートに追加されます。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-146">A [\<ContentPresenter>](xref:System.Windows.Controls.ContentPresenter) element is also added to the template.</span></span> <span data-ttu-id="bcdd8-147">このテンプレートはボタン用に設計されているため、ボタンは <xref:System.Windows.Controls.ContentControl> から継承されることを考慮します。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-147">Because this template is designed for a button, take into consideration that the button inherits from <xref:System.Windows.Controls.ContentControl>.</span></span> <span data-ttu-id="bcdd8-148">このボタンに、要素のコンテンツが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-148">The button presents the content of the element.</span></span> <span data-ttu-id="bcdd8-149">ボタン内には、プレーンテキストや別のコントロールなど、任意のものを設定できます。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-149">You can set anything inside of the button, such as plain text or even another control.</span></span> <span data-ttu-id="bcdd8-150">次のボタンは、いずれも有効です。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-150">Both of the following are valid buttons:</span></span>

```xaml
<Button>My Text</Button>

<!-- and -->

<Button>
    <CheckBox>Checkbox in a button</CheckBox>
</Button>
```

<span data-ttu-id="bcdd8-151">前のどちらの例においても、テキストとチェック ボックスは [Button.Content](xref:System.Windows.Controls.ContentControl.Content) プロパティとして設定されています。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-151">In both of the previous examples, the text and the checkbox are set as the [Button.Content](xref:System.Windows.Controls.ContentControl.Content) property.</span></span> <span data-ttu-id="bcdd8-152">コンテンツとして設定されている内容は、テンプレートで実行される **\<ContentPresenter>** によって表示できます。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-152">Whatever is set as the content can be presented through a **\<ContentPresenter>**, which is what the template does.</span></span>

<span data-ttu-id="bcdd8-153"><xref:System.Windows.Controls.ControlTemplate> が <xref:System.Windows.Controls.ContentControl> 型 (`Button` など) に適用されている場合は、要素ツリー内で <xref:System.Windows.Controls.ContentPresenter> が検索されます。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-153">If the <xref:System.Windows.Controls.ControlTemplate> is applied to a <xref:System.Windows.Controls.ContentControl> type, such as a `Button`, a <xref:System.Windows.Controls.ContentPresenter> is searched for in the element tree.</span></span> <span data-ttu-id="bcdd8-154">`ContentPresenter` が見つかった場合、テンプレートはコントロールの <xref:System.Windows.Controls.ContentControl.Content> プロパティを `ContentPresenter` に自動的にバインドします。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-154">If the `ContentPresenter` is found, the template automatically binds the control's <xref:System.Windows.Controls.ContentControl.Content> property to the `ContentPresenter`.</span></span>

## <a name="use-the-template"></a><span data-ttu-id="bcdd8-155">テンプレートを使用する</span><span class="sxs-lookup"><span data-stu-id="bcdd8-155">Use the template</span></span>

<span data-ttu-id="bcdd8-156">この記事の冒頭で宣言したボタンを見つけます。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-156">Find the buttons that were declared at the start of this article.</span></span>

[!code-xaml[Initial](./snippets/how-to-create-apply-template/csharp/Window1.xaml#Initial)]

<span data-ttu-id="bcdd8-157">2 番目のボタンの <xref:System.Windows.Controls.Control.Template> プロパティを次のように `roundbutton` リソースに設定します。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-157">Set the second button's <xref:System.Windows.Controls.Control.Template> property to the `roundbutton` resource:</span></span>

[!code-xaml[StyledButton](./snippets/how-to-create-apply-template/csharp/Window3.xaml#StyledButton)]

<span data-ttu-id="bcdd8-158">プロジェクトを実行して結果を確認すると、ボタンの背景が丸められていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-158">If you run the project and look at the result, you'll see that the button has a rounded background.</span></span>

![テンプレートの楕円のボタンが 1 つ表示されている WPF ウィンドウ](media/create-apply-template/styled-button.png)

<span data-ttu-id="bcdd8-160">ボタンが円ではなく、歪曲されていることに気付いたかもしれません。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-160">You may have noticed that the button isn't a circle but is skewed.</span></span> <span data-ttu-id="bcdd8-161">**\<Ellipse>** 要素の動作方法により、これらは常に空いているスペースを埋めるように拡張されます。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-161">Because of the way the **\<Ellipse>** element works, it always expands to fill the available space.</span></span> <span data-ttu-id="bcdd8-162">ボタンの **:::no-loc text="width":::** プロパティと **:::no-loc text="height":::** プロパティを同じ値に変更し、円を一定にします。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-162">Make the circle uniform by changing the button's  **:::no-loc text="width":::** and **:::no-loc text="height":::** properties to the same value:</span></span>

[!code-xaml[StyledButtonSize](./snippets/how-to-create-apply-template/csharp/Window3.xaml#StyledButtonSize)]

![テンプレートの円形のボタンが 1 つ表示されている WPF ウィンドウ](media/create-apply-template/styled-uniform-button.png)

## <a name="add-a-trigger"></a><span data-ttu-id="bcdd8-164">トリガーの追加</span><span class="sxs-lookup"><span data-stu-id="bcdd8-164">Add a Trigger</span></span>

<span data-ttu-id="bcdd8-165">テンプレートが適用されているボタンの見た目が異なる場合でも、他のボタンと同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-165">Even though a button with a template applied looks different, it behaves the same as any other button.</span></span> <span data-ttu-id="bcdd8-166">このボタンを押すと、<xref:System.Windows.Controls.Primitives.ButtonBase.Click> イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-166">If you press the button, the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event fires.</span></span> <span data-ttu-id="bcdd8-167">ただし、ボタンの上にマウスを移動しても、ボタンの見た目は変わりません。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-167">However, you may have noticed that when you move your mouse over the button, the button's visuals don't change.</span></span> <span data-ttu-id="bcdd8-168">これらの視覚的な相互作用は、すべてテンプレートによって定義されています。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-168">These visual interactions are all defined by the template.</span></span>

<span data-ttu-id="bcdd8-169">WPF で提供されている動的イベントおよびプロパティ システムを使用して、特定のプロパティの値を監視し、必要に応じてテンプレートのスタイルを再作成することができます。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-169">With the dynamic event and property systems that WPF provides, you can watch a specific property for a value and then restyle the template when appropriate.</span></span> <span data-ttu-id="bcdd8-170">この例では、ボタンの <xref:System.Windows.UIElement.IsMouseOver> プロパティを見ていきます。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-170">In this example, you'll watch the button's <xref:System.Windows.UIElement.IsMouseOver> property.</span></span> <span data-ttu-id="bcdd8-171">マウスがコントロールの上にあるときに、新しい色で **\<Ellipse>** のスタイルを設定します。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-171">When the mouse is over the control, style the **\<Ellipse>** with a new color.</span></span> <span data-ttu-id="bcdd8-172">この種類のトリガーは、*PropertyTrigger* として知られています。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-172">This type of trigger is known as a *PropertyTrigger*.</span></span>

<span data-ttu-id="bcdd8-173">これを機能させるには、参照できる **\<Ellipse>** に名前を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-173">For this to work, you'll need to add a name to the **\<Ellipse>** that you can reference.</span></span> <span data-ttu-id="bcdd8-174">**backgroundElement** という名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-174">Give it the name of **backgroundElement**.</span></span>

[!code-xaml[EllipseName](./snippets/how-to-create-apply-template/csharp/Window4.xaml#EllipseName)]

<span data-ttu-id="bcdd8-175">次に、[ControlTemplate.Triggers](xref:System.Windows.Controls.ControlTemplate.Triggers) コレクションに新しい <xref:System.Windows.Trigger> を追加します。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-175">Next, add a new <xref:System.Windows.Trigger> to the [ControlTemplate.Triggers](xref:System.Windows.Controls.ControlTemplate.Triggers) collection.</span></span> <span data-ttu-id="bcdd8-176">トリガーは、`true` 値の `IsMouseOver` イベントを監視します。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-176">The trigger will watch the `IsMouseOver` event for the value `true`.</span></span>

[!code-xaml[ControlTemplate](./snippets/how-to-create-apply-template/csharp/Window4.xaml?name=ControlTemplate&highlight=6-10)]

<span data-ttu-id="bcdd8-177">次に、 **\<Ellipse>** の **Fill** プロパティを新しい色に変更する **\<Trigger>** に **\<Setter>** を追加します。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-177">Next, add a **\<Setter>** to the **\<Trigger>** that changes the **Fill** property of the **\<Ellipse>** to a new color.</span></span>

[!code-xaml[MouseOver](./snippets/how-to-create-apply-template/csharp/Window5.xaml#MouseOver)]

<span data-ttu-id="bcdd8-178">プロジェクトを実行します。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-178">Run the project.</span></span> <span data-ttu-id="bcdd8-179">ボタンの上にマウスを移動すると、 **\<Ellipse>** の色が変化する点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-179">Notice that when you move the mouse over the button, the color of the **\<Ellipse>** changes.</span></span>

![WPF ボタンの上にマウスを移動したことで塗りつぶしの色が変化](media/create-apply-template/mouse-move-over-button.gif)

## <a name="use-a-visualstate"></a><span data-ttu-id="bcdd8-181">VisualState を使用する</span><span class="sxs-lookup"><span data-stu-id="bcdd8-181">Use a VisualState</span></span>

<span data-ttu-id="bcdd8-182">表示状態は、コントロールによって定義され、トリガーされます。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-182">Visual states are defined and triggered by a control.</span></span> <span data-ttu-id="bcdd8-183">たとえば、マウスをコントロールの上に移動すると、`CommonStates.MouseOver` 状態がトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-183">For example, when the mouse is moved on top of the control, the `CommonStates.MouseOver` state is triggered.</span></span> <span data-ttu-id="bcdd8-184">コントロールの現在の状態に基づいて、プロパティの変更にアニメーションを付けることができます。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-184">You can animate property changes based on the current state of the control.</span></span> <span data-ttu-id="bcdd8-185">前のセクションでは、 **\<PropertyTrigger>** を使用して、`IsMouseOver` プロパティが `true` である場合にボタンの前景が `AliceBlue` に変更されるようにしました。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-185">In the previous section, a **\<PropertyTrigger>** was used to change the foreground of the button to `AliceBlue` when the `IsMouseOver` property was `true`.</span></span> <span data-ttu-id="bcdd8-186">代わりに、この色が変化するアニメーションを付けて、滑らかな遷移を実現する表示状態を作成します。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-186">Instead, create a visual state that animates the change of this color, providing a smooth transition.</span></span> <span data-ttu-id="bcdd8-187">*VisualStates* の詳細については、[「WPF のスタイルとテンプレート」](../fundamentals/styles-templates-overview.md#visual-states)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-187">For more information about *VisualStates*, see [Styles and templates in WPF](../fundamentals/styles-templates-overview.md#visual-states).</span></span>

<span data-ttu-id="bcdd8-188">**\<PropertyTrigger>** をアニメーションが付いた表示状態に変換するには、まず、テンプレートから **\<ControlTemplate.Triggers>** 要素を削除します。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-188">To convert the **\<PropertyTrigger>** to an animated visual state, First, remove the **\<ControlTemplate.Triggers>** element from your template.</span></span>

[!code-xaml[CleanTemplate](./snippets/how-to-create-apply-template/csharp/Window5.xaml#CleanTemplate)]

<span data-ttu-id="bcdd8-189">次に、コントロール テンプレートの **\<Grid>** ルートに、`CommonStates` の **\<VisualStateGroup>** が指定された **\<VisualStateManager.VisualStateGroups>** 要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-189">Next, in the **\<Grid>** root of the control template, add the **\<VisualStateManager.VisualStateGroups>** element with a **\<VisualStateGroup>** for `CommonStates`.</span></span> <span data-ttu-id="bcdd8-190">`Normal` と `MouseOver` の 2 つの状態を定義します。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-190">Define two states, `Normal` and `MouseOver`.</span></span>

[!code-xaml[VisualState](./snippets/how-to-create-apply-template/csharp/Window6.xaml#VisualState)]

<span data-ttu-id="bcdd8-191">**\<VisualState>** で定義されているアニメーションは、その状態がトリガーされたときに適用されます。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-191">Any animations defined in a **\<VisualState>** are applied when that state is triggered.</span></span> <span data-ttu-id="bcdd8-192">各状態のアニメーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-192">Create animations for each state.</span></span> <span data-ttu-id="bcdd8-193">アニメーションは、 **\<Storyboard>** 要素に格納されます。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-193">Animations are put inside of a **\<Storyboard>** element.</span></span> <span data-ttu-id="bcdd8-194">ストーリーボードの詳細については、「[ストーリーボードの概要](../../../framework/wpf/graphics-multimedia/storyboards-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-194">For more information about storyboards, see [Storyboards Overview](../../../framework/wpf/graphics-multimedia/storyboards-overview.md).</span></span>

- <span data-ttu-id="bcdd8-195">標準</span><span class="sxs-lookup"><span data-stu-id="bcdd8-195">Normal</span></span>

  <span data-ttu-id="bcdd8-196">この状態では、楕円の塗りつぶしにアニメーションが付けられ、コントロールの `Background` の色に復元されます。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-196">This state animates the ellipse fill, restoring it to the control's `Background` color.</span></span>

  [!code-xaml[NormalState](./snippets/how-to-create-apply-template/csharp/Window6.xaml#NormalState)]

- <span data-ttu-id="bcdd8-197">MouseOver</span><span class="sxs-lookup"><span data-stu-id="bcdd8-197">MouseOver</span></span>

  <span data-ttu-id="bcdd8-198">この状態では、楕円の `Background` の色から新しい色である `Yellow` に切り替わるようアニメーションが付けられます。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-198">This state animates the ellipse `Background` color to a new color: `Yellow`.</span></span>

  [!code-xaml[MouseOverState](./snippets/how-to-create-apply-template/csharp/Window6.xaml#MouseOverState)]

<span data-ttu-id="bcdd8-199">**\<ControlTemplate>** は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-199">The **\<ControlTemplate>** should now look like the following.</span></span>

[!code-xaml[FinalTemplate](./snippets/how-to-create-apply-template/csharp/Window7.xaml#FinalTemplate)]

<span data-ttu-id="bcdd8-200">プロジェクトを実行します。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-200">Run the project.</span></span> <span data-ttu-id="bcdd8-201">ボタンの上にマウスを移動すると、 **\<Ellipse>** の色がアニメーションになる点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="bcdd8-201">Notice that when you move the mouse over the button, the color of the **\<Ellipse>** animates.</span></span>

![WPF ボタンの上にマウスを移動したことで塗りつぶしの色が変化](media/create-apply-template/mouse-move-over-button-visualstate.gif)

## <a name="next-steps"></a><span data-ttu-id="bcdd8-203">次の手順</span><span class="sxs-lookup"><span data-stu-id="bcdd8-203">Next steps</span></span>

- [<span data-ttu-id="bcdd8-204">WPF でコントロールのスタイルを作成する</span><span class="sxs-lookup"><span data-stu-id="bcdd8-204">Create a style for a control in WPF</span></span>](../fundamentals/styles-templates-create-apply-style.md)
- [<span data-ttu-id="bcdd8-205">WPF のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="bcdd8-205">Styles and templates in WPF</span></span>](../fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="bcdd8-206">XAML リソースの概要</span><span class="sxs-lookup"><span data-stu-id="bcdd8-206">Overview of XAML Resources</span></span>](../fundamentals/xaml-resources-define.md)
