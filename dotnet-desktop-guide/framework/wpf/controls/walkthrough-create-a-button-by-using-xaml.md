---
title: 'チュートリアル: XAML を使用したボタンの作成'
description: このチュートリアルを使用し、XAML を使って Windows Presentation Foundation アプリケーションで利用するアニメーション化されたボタンを作成する方法について学習します。
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [WPF]
ms.assetid: 138c41c4-1759-4bbf-8d77-77031a06a8a0
ms.openlocfilehash: f5744004605ac1d301b70748986e68fc72627825
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985563"
---
# <a name="walkthrough-create-a-button-by-using-xaml"></a><span data-ttu-id="b7b4f-103">チュートリアル: XAML を使用したボタンの作成</span><span class="sxs-lookup"><span data-stu-id="b7b4f-103">Walkthrough: Create a Button by Using XAML</span></span>

<span data-ttu-id="b7b4f-104">このチュートリアルの目的は、Windows Presentation Foundation (WPF) アプリケーションで使用するためのアニメーション化されたボタンを作成する方法を学習することです。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-104">The objective of this walkthrough is to learn how to create an animated button for use in a Windows Presentation Foundation (WPF) application.</span></span> <span data-ttu-id="b7b4f-105">このチュートリアルでは、スタイルとテンプレートを使用して、コードの再利用と、ボタン宣言からのボタン ロジックの分離を可能にする、カスタマイズされたボタン リソースを作成します。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-105">This walkthrough uses styles and a template to create a customized button resource that allows reuse of code and separation of button logic from the button declaration.</span></span> <span data-ttu-id="b7b4f-106">このチュートリアルは、すべて [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] で記述されています。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-106">This walkthrough is written entirely in [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)].</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b7b4f-107">このチュートリアルでは、Visual Studio に [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] を入力するか、コピーして貼り付けることによって、アプリケーションを作成する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-107">This walkthrough guides you through the steps for creating the application by typing or copying and pasting [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] into Visual Studio.</span></span> <span data-ttu-id="b7b4f-108">デザイナーを使用して同じアプリケーションを作成する方法については、[Microsoft Expression Blend を使用してボタンを作成する方法](walkthrough-create-a-button-by-using-microsoft-expression-blend.md)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-108">If you would prefer to learn how to use a designer to create the same application, see [Create a Button by Using Microsoft Expression Blend](walkthrough-create-a-button-by-using-microsoft-expression-blend.md).</span></span>

<span data-ttu-id="b7b4f-109">完成したボタンを次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-109">The following figure shows the finished buttons.</span></span>

<span data-ttu-id="b7b4f-110">![XAML を使用して作成されたカスタム ボタン](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span><span class="sxs-lookup"><span data-stu-id="b7b4f-110">![Custom buttons that were created by using XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span></span>

## <a name="create-basic-buttons"></a><span data-ttu-id="b7b4f-111">基本的なボタンを作成する</span><span class="sxs-lookup"><span data-stu-id="b7b4f-111">Create Basic Buttons</span></span>

<span data-ttu-id="b7b4f-112">まず、新しいプロジェクトを作成し、いくつかのボタンをウィンドウに追加します。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-112">Let's start by creating a new project and adding a few buttons to the window.</span></span>

### <a name="to-create-a-new-wpf-project-and-add-buttons-to-the-window"></a><span data-ttu-id="b7b4f-113">新しい WPF プロジェクトを作成し、ウィンドウにボタンを追加するには</span><span class="sxs-lookup"><span data-stu-id="b7b4f-113">To create a new WPF project and add buttons to the window</span></span>

1. <span data-ttu-id="b7b4f-114">Visual Studio を起動します。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-114">Start Visual Studio.</span></span>

2. <span data-ttu-id="b7b4f-115">**新しい WPF プロジェクトを作成する:** **[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-115">**Create a new WPF project:** On the **File** menu, point to **New**, and then click **Project**.</span></span> <span data-ttu-id="b7b4f-116">**Windows アプリケーション (WPF)** テンプレートを探し、プロジェクトの名前を "AnimatedButton" に設定します。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-116">Find the **Windows Application (WPF)** template and name the project "AnimatedButton".</span></span> <span data-ttu-id="b7b4f-117">これにより、アプリケーションのスケルトンが作成されます。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-117">This will create the skeleton for the application.</span></span>

3. <span data-ttu-id="b7b4f-118">**基本的な既定のボタンを追加する:** このチュートリアルで必要なすべてのファイルは、テンプレートによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-118">**Add basic default buttons:** All the files you need for this walkthrough are provided by the template.</span></span> <span data-ttu-id="b7b4f-119">ソリューション エクスプローラーで Window1.xaml ファイルをダブルクリックして開きます。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-119">Open the Window1.xaml file by double clicking it in Solution Explorer.</span></span> <span data-ttu-id="b7b4f-120">Window1.xaml には <xref:System.Windows.Controls.Grid> 要素が既定で存在します。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-120">By default, there is a <xref:System.Windows.Controls.Grid> element in Window1.xaml.</span></span> <span data-ttu-id="b7b4f-121"><xref:System.Windows.Controls.Grid> 要素を削除し、次の強調表示されているコードを Window1.xaml に入力するか、コピーして貼り付けて、[!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] ページにいくつかのボタンを追加します。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-121">Remove the <xref:System.Windows.Controls.Grid> element and add a few buttons to the [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] page by typing or copy and pasting the following highlighted code to Window1.xaml:</span></span>

    ```xaml
    <Window x:Class="AnimatedButton.Window1"
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
      Title="AnimatedButton" Height="300" Width="300"
      Background="Black">
      <!-- Buttons arranged vertically inside a StackPanel. -->
      <StackPanel HorizontalAlignment="Left">
          <Button>Button 1</Button>
          <Button>Button 2</Button>
          <Button>Button 3</Button>
      </StackPanel>
    </Window>
    ```

     <span data-ttu-id="b7b4f-122">F5 キーを押してアプリケーションを実行します。次の図のような一連のボタンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-122">Press F5 to run the application; you should see a set of buttons that looks like the following figure.</span></span>

     <span data-ttu-id="b7b4f-123">![3 つの基本的なボタン](./media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")</span><span class="sxs-lookup"><span data-stu-id="b7b4f-123">![Three basic buttons](./media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")</span></span>

     <span data-ttu-id="b7b4f-124">これで基本的なボタンが作成されたので、Window1.xaml ファイルでの作業は終了です。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-124">Now that you have created the basic buttons, you are finished working in the Window1.xaml file.</span></span> <span data-ttu-id="b7b4f-125">このチュートリアルの残りの部分では、ボタンのスタイルとテンプレートを定義する app.xaml ファイルに注目します。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-125">The rest of the walkthrough focuses on the app.xaml file, defining styles and a template for the buttons.</span></span>

## <a name="set-basic-properties"></a><span data-ttu-id="b7b4f-126">基本プロパティを設定する</span><span class="sxs-lookup"><span data-stu-id="b7b4f-126">Set Basic Properties</span></span>

<span data-ttu-id="b7b4f-127">次に、ボタンの外観とレイアウトを制御するため、これらのボタンにいくつかのプロパティを設定してみましょう。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-127">Next, let's set some properties on these buttons to control the button appearance and layout.</span></span> <span data-ttu-id="b7b4f-128">個々のボタンにプロパティを設定するのではなく、リソースを使用して、アプリケーション全体に対してボタンのプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-128">Rather than setting properties on the buttons individually, you will use resources to define button properties for the entire application.</span></span> <span data-ttu-id="b7b4f-129">アプリケーション リソースは、概念的には Web ページの外部カスケード スタイル シート (CSS) に似ています。ただし、このチュートリアルの最後にはわかるように、リソースの方がカスケード スタイル シート (CSS) よりはるかに強力です。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-129">Application resources are conceptually similar to external Cascading Style Sheets (CSS) for Web pages; however, resources are much more powerful than Cascading Style Sheets (CSS), as you will see by the end of this walkthrough.</span></span> <span data-ttu-id="b7b4f-130">リソースの詳細については、[XAML のリソース](/dotnet/desktop-wpf/fundamentals/xaml-resources-define)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-130">To learn more about resources, see [XAML Resources](/dotnet/desktop-wpf/fundamentals/xaml-resources-define).</span></span>

### <a name="to-use-styles-to-set-basic-properties-on-the-buttons"></a><span data-ttu-id="b7b4f-131">スタイルを使用してボタンの基本プロパティを設定するには</span><span class="sxs-lookup"><span data-stu-id="b7b4f-131">To use styles to set basic properties on the buttons</span></span>

1. <span data-ttu-id="b7b4f-132">**Application.Resources ブロックを定義する:** app.xaml を開き、次の強調表示されているマークアップを追加します (まだ存在していない場合)。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-132">**Define an Application.Resources block:** Open app.xaml and add the following highlighted markup if it is not already there:</span></span>

    ```xaml
    <Application x:Class="AnimatedButton.App"
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
      StartupUri="Window1.xaml"
      >
      <Application.Resources>
        <!-- Resources for the entire application can be defined here. -->
      </Application.Resources>
    </Application>
    ```

     <span data-ttu-id="b7b4f-133">リソースのスコープは、リソースを定義する場所によって決まります。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-133">Resource scope is determined by where you define the resource.</span></span> <span data-ttu-id="b7b4f-134">app.xaml ファイルの `Application.Resources` でリソースを定義すると、アプリケーションのどこでもリソースを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-134">Defining resources in `Application.Resources` in the app.xaml file enables the resource to be used from anywhere in the application.</span></span> <span data-ttu-id="b7b4f-135">リソースのスコープを定義する方法の詳細については、[XAML のリソース](/dotnet/desktop-wpf/fundamentals/xaml-resources-define)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-135">To learn more about defining the scope of your resources, see [XAML Resources](/dotnet/desktop-wpf/fundamentals/xaml-resources-define).</span></span>

2. <span data-ttu-id="b7b4f-136">**スタイルを作成し、それを使用して基本的なプロパティ値を定義する:** 次のマークアップを `Application.Resources` ブロックに追加します。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-136">**Create a style and define basic property values with it:** Add the following markup to the `Application.Resources` block.</span></span> <span data-ttu-id="b7b4f-137">このマークアップで作成される <xref:System.Windows.Style> はアプリケーションのすべてのボタンに適用され、ボタンの <xref:System.Windows.FrameworkElement.Width%2A> が 90 に、<xref:System.Windows.FrameworkElement.Margin%2A> が 10 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-137">This markup creates a <xref:System.Windows.Style> that applies to all buttons in the application, setting the <xref:System.Windows.FrameworkElement.Width%2A> of the buttons to 90 and the <xref:System.Windows.FrameworkElement.Margin%2A> to 10:</span></span>

    ```xaml
    <Application.Resources>
      <Style TargetType="Button">
        <Setter Property="Width" Value="90" />
        <Setter Property="Margin" Value="10" />
      </Style>
    </Application.Resources>
    ```

     <span data-ttu-id="b7b4f-138"><xref:System.Windows.Style.TargetType%2A> プロパティでは、スタイルが <xref:System.Windows.Controls.Button> 型のすべてのオブジェクトに適用されることが指定されます。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-138">The <xref:System.Windows.Style.TargetType%2A> property specifies that the style applies to all objects of type <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="b7b4f-139">各 <xref:System.Windows.Setter> では、<xref:System.Windows.Style> に対して異なるプロパティ値が設定されます。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-139">Each <xref:System.Windows.Setter> sets a different property value for the <xref:System.Windows.Style>.</span></span> <span data-ttu-id="b7b4f-140">そのため、この時点では、アプリケーションのすべてのボタンは幅が 90、余白が 10 になっています。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-140">Therefore, at this point every button in the application has a width of 90 and a margin of 10.</span></span>  <span data-ttu-id="b7b4f-141">F5 キーを押してアプリケーションを実行すると、次のようなウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-141">If you press F5 to run the application, you see the following window.</span></span>

     <span data-ttu-id="b7b4f-142">![幅 90、余白 10 のボタン](./media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")</span><span class="sxs-lookup"><span data-stu-id="b7b4f-142">![Buttons with a width of 90 and a margin of 10](./media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")</span></span>

     <span data-ttu-id="b7b4f-143">スタイルを使用すると、さまざまな方法による対象オブジェクトの微調整、複雑なプロパティ値の指定、他のスタイルに対する入力としてのスタイルの使用など、多くのことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-143">There is much more you can do with styles, including a variety of ways to fine-tune what objects are targeted, specifying complex property values, and even using styles as input for other styles.</span></span> <span data-ttu-id="b7b4f-144">詳しくは、「 [スタイルとテンプレート](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-144">For more information, see [Styling and Templating](/dotnet/desktop-wpf/fundamentals/styles-templates-overview).</span></span>

3. <span data-ttu-id="b7b4f-145">**リソースにスタイルのプロパティ値を設定する:** リソースを使用すると、一般的に定義されているオブジェクトと値を簡単に再利用できます。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-145">**Set a style property value to a resource:** Resources enable a simple way to reuse commonly defined objects and values.</span></span> <span data-ttu-id="b7b4f-146">特に、リソースを使用して複雑な値を定義し、コードのモジュール性を高めるのに便利です。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-146">It is especially useful to define complex values using resources to make your code more modular.</span></span> <span data-ttu-id="b7b4f-147">次の強調表示されているマークアップを app.xaml に追加します。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-147">Add the following highlighted markup to app.xaml.</span></span>

    ```xaml
    <Application.Resources>
      <LinearGradientBrush x:Key="GrayBlueGradientBrush" StartPoint="0,0" EndPoint="1,1">
        <GradientStop Color="DarkGray" Offset="0" />
        <GradientStop Color="#CCCCFF" Offset="0.5" />
        <GradientStop Color="DarkGray" Offset="1" />
      </LinearGradientBrush>
      <Style TargetType="{x:Type Button}">
        <Setter Property="Background" Value="{StaticResource GrayBlueGradientBrush}" />
        <Setter Property="Width" Value="80" />
        <Setter Property="Margin" Value="10" />
      </Style>
    </Application.Resources>
    ```

     <span data-ttu-id="b7b4f-148">`Application.Resources` ブロックのすぐ下には、"GrayBlueGradientBrush" という名前のリソースを作成してあります。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-148">Directly under the `Application.Resources` block, you created a resource called "GrayBlueGradientBrush".</span></span> <span data-ttu-id="b7b4f-149">このリソースでは、水平方向のグラデーションが定義されています。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-149">This resource defines a horizontal gradient.</span></span> <span data-ttu-id="b7b4f-150">このリソースは、<xref:System.Windows.Controls.Control.Background%2A> プロパティに対するボタン スタイル セッターの内部など、アプリケーションの任意の場所からプロパティ値として使用できます。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-150">This resource can be used as a property value from anywhere in the application, including inside the button style setter for the <xref:System.Windows.Controls.Control.Background%2A> property.</span></span> <span data-ttu-id="b7b4f-151">これで、すべてのボタンにこのグラデーションの <xref:System.Windows.Controls.Control.Background%2A> プロパティ値が設定されました。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-151">Now, all the buttons have a <xref:System.Windows.Controls.Control.Background%2A> property value of this gradient.</span></span>

     <span data-ttu-id="b7b4f-152">F5 キーを押してアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-152">Press F5 to run the application.</span></span> <span data-ttu-id="b7b4f-153">次のような表示になります。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-153">It should look like the following.</span></span>

     <span data-ttu-id="b7b4f-154">![グラデーション背景を持つボタン](./media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")</span><span class="sxs-lookup"><span data-stu-id="b7b4f-154">![Buttons with a gradient background](./media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")</span></span>

## <a name="create-a-template-that-defines-the-look-of-the-button"></a><span data-ttu-id="b7b4f-155">ボタンの外観を定義するテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="b7b4f-155">Create a Template That Defines the Look of the Button</span></span>

<span data-ttu-id="b7b4f-156">このセクションでは、ボタンの外観 (プレゼンテーション) をカスタマイズするテンプレートを作成します。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-156">In this section, you create a template that customizes the appearance (presentation) of the button.</span></span> <span data-ttu-id="b7b4f-157">ボタンのプレゼンテーションは、四角形などの複数のオブジェクトと、ボタンに固有の外観を提供するその他のコンポーネントで構成されています。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-157">The button presentation is made up of several objects including rectangles and other components to give the button a unique look.</span></span>

<span data-ttu-id="b7b4f-158">これまでのところ、アプリケーションでのボタンの外観の制御は、ボタンのプロパティの変更に限定されています。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-158">So far, the control of how buttons look in the application has been confined to changing properties of the button.</span></span> <span data-ttu-id="b7b4f-159">ボタンの外観をさらに大きく変更するには、どうすればよいでしょうか。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-159">What if you want to make more radical changes to the button's appearance?</span></span> <span data-ttu-id="b7b4f-160">テンプレートを使用すると、オブジェクトのプレゼンテーションを強力に制御できます。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-160">Templates enable powerful control over the presentation of an object.</span></span> <span data-ttu-id="b7b4f-161">テンプレートはスタイル内で使用できるため、スタイルが適用されるすべてのオブジェクト (このチュートリアルではボタン) に、テンプレートを適用できます。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-161">Because templates can be used within styles, you can apply a template to all objects that the style applies to (in this walkthrough, the button).</span></span>

### <a name="to-use-the-template-to-define-the-look-of-the-button"></a><span data-ttu-id="b7b4f-162">テンプレートを使用してボタンの外観を定義するには</span><span class="sxs-lookup"><span data-stu-id="b7b4f-162">To use the template to define the look of the button</span></span>

1. <span data-ttu-id="b7b4f-163">**テンプレートを設定する:** <xref:System.Windows.Controls.Button> のようなコントロールには <xref:System.Windows.Controls.Control.Template%2A> プロパティがあるため、<xref:System.Windows.Setter> を使用して <xref:System.Windows.Style> で設定した他のプロパティ値と同じように、テンプレート プロパティの値を定義できます。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-163">**Set up the template:** Because controls like <xref:System.Windows.Controls.Button> have a <xref:System.Windows.Controls.Control.Template%2A> property, you can define the template property value just like the other property values we have set in a <xref:System.Windows.Style> using a <xref:System.Windows.Setter>.</span></span> <span data-ttu-id="b7b4f-164">次の強調表示されたマークアップを、ボタンのスタイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-164">Add the following highlighted markup to your button style.</span></span>

    ```xaml
    <Application.Resources>
      <LinearGradientBrush x:Key="GrayBlueGradientBrush"
        StartPoint="0,0" EndPoint="1,1">
        <GradientStop Color="DarkGray" Offset="0" />
        <GradientStop Color="#CCCCFF" Offset="0.5" />
        <GradientStop Color="DarkGray" Offset="1" />
      </LinearGradientBrush>
      <Style TargetType="{x:Type Button}">
        <Setter Property="Background" Value="{StaticResource GrayBlueGradientBrush}" />
        <Setter Property="Width" Value="80" />
        <Setter Property="Margin" Value="10" />
        <Setter Property="Template">
          <Setter.Value>
            <!-- The button template is defined here. -->
          </Setter.Value>
        </Setter>
      </Style>
    </Application.Resources>
    ```

2. <span data-ttu-id="b7b4f-165">**ボタンのプレゼンテーションを変更する:** この時点で、テンプレートを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-165">**Alter button presentation:** At this point, you need to define the template.</span></span> <span data-ttu-id="b7b4f-166">次の強調表示されたマークアップを追加します。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-166">Add the following highlighted markup.</span></span> <span data-ttu-id="b7b4f-167">このマークアップでは、角が丸い 2 つの <xref:System.Windows.Shapes.Rectangle> 要素と、その後で <xref:System.Windows.Controls.DockPanel> が指定されています。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-167">This markup specifies two <xref:System.Windows.Shapes.Rectangle> elements with rounded edges, followed by a <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="b7b4f-168"><xref:System.Windows.Controls.DockPanel> は、ボタンの <xref:System.Windows.Controls.ContentPresenter> をホストするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-168">The <xref:System.Windows.Controls.DockPanel> is used to host the <xref:System.Windows.Controls.ContentPresenter> of the button.</span></span> <span data-ttu-id="b7b4f-169"><xref:System.Windows.Controls.ContentPresenter> では、ボタンの内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-169">A <xref:System.Windows.Controls.ContentPresenter> displays the content of the button.</span></span> <span data-ttu-id="b7b4f-170">このチュートリアルでは、内容はテキスト ("Button 1"、"Button 2"、"Button 3") です。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-170">In this walkthrough, the content is text ("Button 1", "Button 2", "Button 3").</span></span> <span data-ttu-id="b7b4f-171">すべてのテンプレート コンポーネント (四角形と <xref:System.Windows.Controls.DockPanel>) は、<xref:System.Windows.Controls.Grid> の内部にレイアウトされます。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-171">All of the template components (the rectangles and the <xref:System.Windows.Controls.DockPanel>) are laid out inside of a <xref:System.Windows.Controls.Grid>.</span></span>

    ```xaml
    <Setter.Value>
      <ControlTemplate TargetType="Button">
        <Grid Width="{TemplateBinding Width}" Height="{TemplateBinding Height}" ClipToBounds="True">
          <!-- Outer Rectangle with rounded corners. -->
          <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}" RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />
          <!-- Inner Rectangle with rounded corners. -->
          <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" Stroke="Transparent" StrokeThickness="20" Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20" />
          <!-- Present Content (text) of the button. -->
          <DockPanel Name="myContentPresenterDockPanel">
            <ContentPresenter x:Name="myContentPresenter" Margin="20" Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />
          </DockPanel>
        </Grid>
      </ControlTemplate>
    </Setter.Value>
    ```

     <span data-ttu-id="b7b4f-172">F5 キーを押してアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-172">Press F5 to run the application.</span></span> <span data-ttu-id="b7b4f-173">次のような表示になります。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-173">It should look like the following.</span></span>

     ![3 個のボタンがあるウィンドウ](./media/custom-button-animatedbutton-4.gif)

3. <span data-ttu-id="b7b4f-175">**テンプレートにガラス効果を追加する:** 次に、ガラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-175">**Add a glasseffect to the template:** Next you will add the glass.</span></span> <span data-ttu-id="b7b4f-176">まず、ガラスのグラデーション効果を作成するいくつかのリソースを作成します。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-176">First you create some resources that create a glass gradient effect.</span></span> <span data-ttu-id="b7b4f-177">これらのグラデーション リソースを、`Application.Resources` ブロック内の任意の場所に追加します。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-177">Add these gradient resources anywhere within the `Application.Resources` block:</span></span>

    ```xaml
    <Application.Resources>
      <GradientStopCollection x:Key="MyGlassGradientStopsResource">
        <GradientStop Color="WhiteSmoke" Offset="0.2" />
        <GradientStop Color="Transparent" Offset="0.4" />
        <GradientStop Color="WhiteSmoke" Offset="0.5" />
        <GradientStop Color="Transparent" Offset="0.75" />
        <GradientStop Color="WhiteSmoke" Offset="0.9" />
        <GradientStop Color="Transparent" Offset="1" />
      </GradientStopCollection>
      <LinearGradientBrush x:Key="MyGlassBrushResource"
        StartPoint="0,0" EndPoint="1,1" Opacity="0.75"
        GradientStops="{StaticResource MyGlassGradientStopsResource}" />
    <!-- Styles and other resources below here. -->
    ```

     <span data-ttu-id="b7b4f-178">これらのリソースは、ボタン テンプレートの <xref:System.Windows.Controls.Grid> に挿入する四角形の <xref:System.Windows.Shapes.Shape.Fill%2A> として使用されます。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-178">These resources are used as the <xref:System.Windows.Shapes.Shape.Fill%2A> for a rectangle that we insert into the <xref:System.Windows.Controls.Grid> of the button template.</span></span> <span data-ttu-id="b7b4f-179">次の強調表示されているマークアップをテンプレートに追加します。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-179">Add the following highlighted markup to the template.</span></span>

    ```xaml
    <Setter.Value>
      <ControlTemplate TargetType="{x:Type Button}">
        <Grid Width="{TemplateBinding Width}" Height="{TemplateBinding Height}"
          ClipToBounds="True">

        <!-- Outer Rectangle with rounded corners. -->
        <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}"
          RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />

        <!-- Inner Rectangle with rounded corners. -->
        <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch" Stroke="Transparent" StrokeThickness="20"
          Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20" />

        <!-- Glass Rectangle -->
        <Rectangle x:Name="glassCube" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch"
          StrokeThickness="2" RadiusX="10" RadiusY="10" Opacity="0"
          Fill="{StaticResource MyGlassBrushResource}"
          RenderTransformOrigin="0.5,0.5">
          <Rectangle.Stroke>
            <LinearGradientBrush StartPoint="0.5,0" EndPoint="0.5,1">
              <LinearGradientBrush.GradientStops>
                <GradientStop Offset="0.0" Color="LightBlue" />
                <GradientStop Offset="1.0" Color="Gray" />
              </LinearGradientBrush.GradientStops>
            </LinearGradientBrush>
          </Rectangle.Stroke>
          <!-- These transforms have no effect as they are declared here.
          The reason the transforms are included is to be targets
          for animation (see later). -->
          <Rectangle.RenderTransform>
            <TransformGroup>
              <ScaleTransform />
              <RotateTransform />
            </TransformGroup>
          </Rectangle.RenderTransform>
          <!-- A BevelBitmapEffect is applied to give the button a "Beveled" look. -->
          <Rectangle.BitmapEffect>
            <BevelBitmapEffect />
          </Rectangle.BitmapEffect>
        </Rectangle>

        <!-- Present Text of the button. -->
        <DockPanel Name="myContentPresenterDockPanel">
          <ContentPresenter x:Name="myContentPresenter" Margin="20"
            Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />
        </DockPanel>
      </Grid>
    </ControlTemplate>
    </Setter.Value>
    ```

     <span data-ttu-id="b7b4f-180">`x:Name` プロパティが "glassCube" である四角形の <xref:System.Windows.UIElement.Opacity%2A> が 0 であることに注意してください。そのため、サンプルを実行すると、ガラスの四角形が上に重なって表示されません。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-180">Notice that the <xref:System.Windows.UIElement.Opacity%2A> of the rectangle with the `x:Name` property of "glassCube" is 0, so when you run the sample, you do not see the glass rectangle overlaid on top.</span></span> <span data-ttu-id="b7b4f-181">これは、ユーザーがボタンを操作したときのためのトリガーを、後でテンプレートに追加するためです。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-181">This is because we will later add triggers to the template for when the user interacts with the button.</span></span> <span data-ttu-id="b7b4f-182">ただし、<xref:System.Windows.UIElement.Opacity%2A> の値を 1 に変更してアプリケーションを実行すると、ボタンがどのように表示されるかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-182">However, you can see what the button looks like now by changing the <xref:System.Windows.UIElement.Opacity%2A> value to 1 and running the application.</span></span> <span data-ttu-id="b7b4f-183">次の図を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-183">See the following figure.</span></span> <span data-ttu-id="b7b4f-184">次のステップに進む前に、<xref:System.Windows.UIElement.Opacity%2A> を 0 に戻しておきます。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-184">Before proceeding to the next step, change the <xref:System.Windows.UIElement.Opacity%2A> back to 0.</span></span>

     <span data-ttu-id="b7b4f-185">![XAML を使用して作成されたカスタム ボタン](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span><span class="sxs-lookup"><span data-stu-id="b7b4f-185">![Custom buttons that were created by using XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span></span>

## <a name="create-button-interactivity"></a><span data-ttu-id="b7b4f-186">ボタンの操作機能を作成する</span><span class="sxs-lookup"><span data-stu-id="b7b4f-186">Create Button Interactivity</span></span>

<span data-ttu-id="b7b4f-187">このセクションでは、ボタン上のマウス ポインターの移動やクリックなどのユーザーの操作に応じて、プロパティ値を変更してアニメーションを実行するための、プロパティ トリガーとイベント トリガーを作成します。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-187">In this section, you will create property triggers and event triggers to change property values and run animations in response to user actions such as moving the mouse pointer over the button and clicking.</span></span>

<span data-ttu-id="b7b4f-188">操作機能 (内部へのマウスの移動、外部へのマウスの移動、クリックなど) を追加する簡単な方法は、テンプレートまたはスタイル内でトリガーを定義することです。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-188">An easy way to add interactivity (mouse-over, mouse-leave, click, and so on) is to define triggers within your template or style.</span></span> <span data-ttu-id="b7b4f-189"><xref:System.Windows.Trigger> を作成するには、次のようなプロパティの "条件" を定義します: ボタンの <xref:System.Windows.UIElement.IsMouseOver%2A> プロパティの値が `true` と等しい。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-189">To create a <xref:System.Windows.Trigger>, you define a property "condition" such as: The button <xref:System.Windows.UIElement.IsMouseOver%2A> property value is equal to `true`.</span></span> <span data-ttu-id="b7b4f-190">次に、トリガー条件が true のときに実行されるセッター (アクション) を定義します。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-190">You then define setters (actions) that take place when the trigger condition is true.</span></span>

### <a name="to-create-button-interactivity"></a><span data-ttu-id="b7b4f-191">ボタンの操作機能を作成するには</span><span class="sxs-lookup"><span data-stu-id="b7b4f-191">To create button interactivity</span></span>

1. <span data-ttu-id="b7b4f-192">**テンプレート トリガーを追加する:** 強調表示されたマークアップをテンプレートに追加します。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-192">**Add template triggers:** Add the highlighted markup to your template.</span></span>

    ```xaml
    <Setter.Value>
      <ControlTemplate TargetType="{x:Type Button}">
        <Grid Width="{TemplateBinding Width}"
          Height="{TemplateBinding Height}" ClipToBounds="True">

          <!-- Outer Rectangle with rounded corners. -->
          <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}"
          RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />

          <!-- Inner Rectangle with rounded corners. -->
          <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch"
            VerticalAlignment="Stretch" Stroke="Transparent"
            StrokeThickness="20"
            Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20"
          />

          <!-- Glass Rectangle -->
          <Rectangle x:Name="glassCube" HorizontalAlignment="Stretch"
            VerticalAlignment="Stretch"
            StrokeThickness="2" RadiusX="10" RadiusY="10" Opacity="0"
            Fill="{StaticResource MyGlassBrushResource}"
            RenderTransformOrigin="0.5,0.5">
            <Rectangle.Stroke>
              <LinearGradientBrush StartPoint="0.5,0" EndPoint="0.5,1">
                <LinearGradientBrush.GradientStops>
                  <GradientStop Offset="0.0" Color="LightBlue" />
                  <GradientStop Offset="1.0" Color="Gray" />
                </LinearGradientBrush.GradientStops>
              </LinearGradientBrush>
            </Rectangle.Stroke>

            <!-- These transforms have no effect as they
                 are declared here.
                 The reason the transforms are included is to be targets
                 for animation (see later). -->
            <Rectangle.RenderTransform>
              <TransformGroup>
                <ScaleTransform />
                <RotateTransform />
              </TransformGroup>
            </Rectangle.RenderTransform>

              <!-- A BevelBitmapEffect is applied to give the button a
                   "Beveled" look. -->
            <Rectangle.BitmapEffect>
              <BevelBitmapEffect />
            </Rectangle.BitmapEffect>
          </Rectangle>

          <!-- Present Text of the button. -->
          <DockPanel Name="myContentPresenterDockPanel">
            <ContentPresenter x:Name="myContentPresenter" Margin="20"
              Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />
          </DockPanel>
        </Grid>

        <ControlTemplate.Triggers>       <!-- Set action triggers for the buttons and define            what the button does in response to those triggers. -->     </ControlTemplate.Triggers>
      </ControlTemplate>
    </Setter.Value>
    ```

2. <span data-ttu-id="b7b4f-193">**プロパティ トリガーを追加する:** 強調表示されたマークアップを `ControlTemplate.Triggers` ブロックに追加します。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-193">**Add property triggers:** Add the highlighted markup to the `ControlTemplate.Triggers` block:</span></span>

    ```xaml
    <ControlTemplate.Triggers>

      <!-- Set properties when mouse pointer is over the button. -->   <Trigger Property="IsMouseOver" Value="True">     <!-- Below are three property settings that occur when the           condition is met (user mouses over button).  -->     <!-- Change the color of the outer rectangle when user           mouses over it. -->     <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <!-- Sets the glass opacity to 1, therefore, the           glass "appears" when user mouses over it. -->     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />     <!-- Makes the text slightly blurry as though you           were looking at it through blurry glass. -->     <Setter Property="ContentPresenter.BitmapEffect"        TargetName="myContentPresenter">       <Setter.Value>         <BlurBitmapEffect Radius="1" />       </Setter.Value>     </Setter>   </Trigger>

    <ControlTemplate.Triggers/>
    ```

     <span data-ttu-id="b7b4f-194">F5 キーを押してアプリケーションを実行し、ボタンの上にマウス ポインターを置いたときの効果を確認します。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-194">Press F5 to run the application and see the effect as you run the mouse pointer over the buttons.</span></span>

3. <span data-ttu-id="b7b4f-195">**フォーカス トリガーを追加する:** 次に、ボタンにフォーカスが設定された場合 (ユーザーがクリックした後など) に対処する、同様のセッターを追加します。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-195">**Add a focus trigger:** Next, we'll add some similar setters to handle the case when the button has focus (for example, after the user clicks it).</span></span>

    ```xaml
    <ControlTemplate.Triggers>

      <!-- Set properties when mouse pointer is over the button. -->
      <Trigger Property="IsMouseOver" Value="True">

        <!-- Below are three property settings that occur when the
             condition is met (user mouses over button).  -->
        <!-- Change the color of the outer rectangle when user          mouses over it. -->
        <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"
          Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />

        <!-- Sets the glass opacity to 1, therefore, the          glass "appears" when user mouses over it. -->
        <Setter Property="Rectangle.Opacity" Value="1"       TargetName="glassCube" />

        <!-- Makes the text slightly blurry as though you were          looking at it through blurry glass. -->
        <Setter Property="ContentPresenter.BitmapEffect"       TargetName="myContentPresenter">
          <Setter.Value>
            <BlurBitmapEffect Radius="1" />
          </Setter.Value>
        </Setter>
      </Trigger>
      <!-- Set properties when button has focus. -->   <Trigger Property="IsFocused" Value="true">     <Setter Property="Rectangle.Opacity" Value="1"       TargetName="glassCube" />     <Setter Property="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />   </Trigger>

    </ControlTemplate.Triggers>
    ```

     <span data-ttu-id="b7b4f-196">F5 キーを押してアプリケーションを実行し、ボタンのいずれかをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-196">Press F5 to run the application and click on one of the buttons.</span></span> <span data-ttu-id="b7b4f-197">クリックした後もフォーカスがまだ設定されているため、ボタンが強調表示されたままになることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-197">Notice that the button stays highlighted after you click it because it still has focus.</span></span> <span data-ttu-id="b7b4f-198">別のボタンをクリックすると、新しいボタンがフォーカスを取得し、前のボタンは失います。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-198">If you click another button, the new button gains focus while the last one loses it.</span></span>

4. <span data-ttu-id="b7b4f-199"><xref:System.Windows.UIElement.MouseEnter>**と**<xref:System.Windows.UIElement.MouseLeave> **に対するアニメーション** **を追加する:** 次に、トリガーにいくつかのアニメーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-199">**Add animations for**  <xref:System.Windows.UIElement.MouseEnter> **and** <xref:System.Windows.UIElement.MouseLeave> **:** Next we add some animations to the triggers.</span></span> <span data-ttu-id="b7b4f-200">`ControlTemplate.Triggers` ブロック内の任意の場所に、次のマークアップを追加します。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-200">Add the following markup anywhere inside of the `ControlTemplate.Triggers` block.</span></span>

    ```xaml
    <!-- Animations that start when mouse enters and leaves button. -->
    <EventTrigger RoutedEvent="Mouse.MouseEnter">
      <EventTrigger.Actions>
        <BeginStoryboard Name="mouseEnterBeginStoryboard">
          <Storyboard>
          <!-- This animation makes the glass rectangle shrink in the X direction. -->
            <DoubleAnimation Storyboard.TargetName="glassCube"
              Storyboard.TargetProperty=
              "(Rectangle.RenderTransform).(TransformGroup.Children)[0].(ScaleTransform.ScaleX)"
              By="-0.1" Duration="0:0:0.5" />
            <!-- This animation makes the glass rectangle shrink in the Y direction. -->
            <DoubleAnimation
            Storyboard.TargetName="glassCube"
              Storyboard.TargetProperty=
              "(Rectangle.RenderTransform).(TransformGroup.Children)[0].(ScaleTransform.ScaleY)"
              By="-0.1" Duration="0:0:0.5" />
          </Storyboard>
        </BeginStoryboard>
      </EventTrigger.Actions>
    </EventTrigger>
    <EventTrigger RoutedEvent="Mouse.MouseLeave">
      <EventTrigger.Actions>
        <!-- Stopping the storyboard sets all animated properties back to default. -->
        <StopStoryboard BeginStoryboardName="mouseEnterBeginStoryboard" />
      </EventTrigger.Actions>
    </EventTrigger>
    ```

     <span data-ttu-id="b7b4f-201">マウス ポインターがボタンの上に移動するとガラスの四角形を小さくし、ポインターが離れると通常のサイズに戻します。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-201">The glass rectangle shrinks when the mouse pointer moves over the button and returns back to normal size when the pointer leaves.</span></span>

     <span data-ttu-id="b7b4f-202">ポインターがボタンの上に移動するとトリガーされるアニメーションが 2 つあります (<xref:System.Windows.UIElement.MouseEnter> イベントが発生します)。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-202">There are two animations that are triggered when the pointer goes over the button (<xref:System.Windows.UIElement.MouseEnter> event is raised).</span></span> <span data-ttu-id="b7b4f-203">これらのアニメーションでは、X 軸と Y 軸に沿ってガラスの四角形を縮小します。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-203">These animations shrink the glass rectangle along the X and Y axis.</span></span> <span data-ttu-id="b7b4f-204"><xref:System.Windows.Media.Animation.DoubleAnimation> 要素のプロパティ (<xref:System.Windows.Media.Animation.Timeline.Duration%2A> と <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>) に注意してください。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-204">Notice the properties on the <xref:System.Windows.Media.Animation.DoubleAnimation> elements — <xref:System.Windows.Media.Animation.Timeline.Duration%2A> and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.</span></span> <span data-ttu-id="b7b4f-205"><xref:System.Windows.Media.Animation.Timeline.Duration%2A> ではアニメーションを 0.5 秒間実行することが指定されていて、<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> ではガラスを 10% 縮小することが指定されています。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-205">The <xref:System.Windows.Media.Animation.Timeline.Duration%2A> specifies that the animation occurs over half a second, and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> specifies that the glass shrinks by 10%.</span></span>

     <span data-ttu-id="b7b4f-206">2 つ目のイベント トリガー (<xref:System.Windows.UIElement.MouseLeave>) では、最初のトリガーが単に停止されます。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-206">The second event trigger (<xref:System.Windows.UIElement.MouseLeave>) simply stops the first one.</span></span> <span data-ttu-id="b7b4f-207"><xref:System.Windows.Media.Animation.Storyboard> を停止すると、アニメーション化されたすべてのプロパティが既定値に戻ります。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-207">When you stop a <xref:System.Windows.Media.Animation.Storyboard>, all the animated properties return to their default values.</span></span> <span data-ttu-id="b7b4f-208">このため、ユーザーがポインターをボタンの外に移動すると、ボタンはマウス ポインターがボタンの上に移動する前の状態に戻ります。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-208">Therefore, when the user moves the pointer off the button, the button goes back to the way it was before the mouse pointer moved over the button.</span></span> <span data-ttu-id="b7b4f-209">アニメーションの詳細については、「[アニメーションの概要](../graphics-multimedia/animation-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-209">For more information about animations, see [Animation Overview](../graphics-multimedia/animation-overview.md).</span></span>

5. <span data-ttu-id="b7b4f-210">**ボタンがクリックされたときのアニメーションを追加する:** 最後のステップでは、ユーザーがボタンをクリックしたときのトリガーを追加します。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-210">**Add an animation for when the button is clicked:** The final step is to add a trigger for when the user clicks the button.</span></span> <span data-ttu-id="b7b4f-211">`ControlTemplate.Triggers` ブロック内の任意の場所に、次のマークアップを追加します。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-211">Add the following markup anywhere inside of the `ControlTemplate.Triggers` block:</span></span>

    ```xaml
    <!-- Animation fires when button is clicked, causing glass to spin.  -->
    <EventTrigger RoutedEvent="Button.Click">
      <EventTrigger.Actions>
        <BeginStoryboard>
          <Storyboard>
            <DoubleAnimation Storyboard.TargetName="glassCube"
              Storyboard.TargetProperty=
              "(Rectangle.RenderTransform).(TransformGroup.Children)[1].(RotateTransform.Angle)"
              By="360" Duration="0:0:0.5" />
          </Storyboard>
        </BeginStoryboard>
      </EventTrigger.Actions>
    </EventTrigger>
    ```

     <span data-ttu-id="b7b4f-212">F5 キーを押してアプリケーションを実行し、ボタンのいずれかをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-212">Press F5 to run the application, and click one of the buttons.</span></span> <span data-ttu-id="b7b4f-213">ボタンをクリックすると、ガラスの四角形が回転します。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-213">When you click a button, the glass rectangle spins around.</span></span>

## <a name="summary"></a><span data-ttu-id="b7b4f-214">まとめ</span><span class="sxs-lookup"><span data-stu-id="b7b4f-214">Summary</span></span>
 <span data-ttu-id="b7b4f-215">このチュートリアルでは、次の演習を行いました。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-215">In this walkthrough, you performed the following exercises:</span></span>

- <span data-ttu-id="b7b4f-216"><xref:System.Windows.Style> の対象をオブジェクトの種類 (<xref:System.Windows.Controls.Button>) に設定しました。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-216">Targeted a <xref:System.Windows.Style> to an object type (<xref:System.Windows.Controls.Button>).</span></span>

- <span data-ttu-id="b7b4f-217"><xref:System.Windows.Style> を使用して、アプリケーション全体でボタンの基本プロパティを制御しました。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-217">Controlled basic properties of the buttons in the entire application using the <xref:System.Windows.Style>.</span></span>

- <span data-ttu-id="b7b4f-218"><xref:System.Windows.Style> のセッターのプロパティ値に使用する、グラデーションなどのリソースを作成しました。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-218">Created resources like gradients to use for property values of the <xref:System.Windows.Style> setters.</span></span>

- <span data-ttu-id="b7b4f-219">ボタンにテンプレートを適用することにより、アプリケーション全体でボタンの外観をカスタマイズしました。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-219">Customized the look of buttons in the entire application by applying a template to the buttons.</span></span>

- <span data-ttu-id="b7b4f-220">アニメーション効果など、ユーザーの操作 (<xref:System.Windows.UIElement.MouseEnter>、<xref:System.Windows.UIElement.MouseLeave>、<xref:System.Windows.Controls.Primitives.ButtonBase.Click> など) に応じてボタンの動作をカスタマイズしました。</span><span class="sxs-lookup"><span data-stu-id="b7b4f-220">Customized behavior for the buttons in response to user actions (such as <xref:System.Windows.UIElement.MouseEnter>, <xref:System.Windows.UIElement.MouseLeave>, and <xref:System.Windows.Controls.Primitives.ButtonBase.Click>) that included animation effects.</span></span>

## <a name="see-also"></a><span data-ttu-id="b7b4f-221">関連項目</span><span class="sxs-lookup"><span data-stu-id="b7b4f-221">See also</span></span>

- [<span data-ttu-id="b7b4f-222">Microsoft Expression Blend を使用してボタンを作成する</span><span class="sxs-lookup"><span data-stu-id="b7b4f-222">Create a Button by Using Microsoft Expression Blend</span></span>](walkthrough-create-a-button-by-using-microsoft-expression-blend.md)
- [<span data-ttu-id="b7b4f-223">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="b7b4f-223">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="b7b4f-224">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="b7b4f-224">Animation Overview</span></span>](../graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="b7b4f-225">純色およびグラデーションによる塗りつぶしの概要</span><span class="sxs-lookup"><span data-stu-id="b7b4f-225">Painting with Solid Colors and Gradients Overview</span></span>](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="b7b4f-226">ビットマップ効果の概要</span><span class="sxs-lookup"><span data-stu-id="b7b4f-226">Bitmap Effects Overview</span></span>](../graphics-multimedia/bitmap-effects-overview.md)
