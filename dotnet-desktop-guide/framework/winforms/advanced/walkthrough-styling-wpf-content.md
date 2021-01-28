---
title: 'チュートリアル: WPF コンテンツのスタイルを適用する'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Designer [Windows Forms], styling WPF content
- interoperability [WDF]
- styles [Windows Forms], WPF content
ms.assetid: e574aac7-7ea4-4cdb-8034-bab541f000df
ms.openlocfilehash: f7acec4edb31dba0aa014943dde7f758fe8e4575
ms.sourcegitcommit: 7f48b9ecf8a30db42c8ecea0dd4df577736631a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957397"
---
# <a name="walkthrough-style-wpf-content"></a><span data-ttu-id="dc83e-102">チュートリアル: WPF コンテンツのスタイルを適用する</span><span class="sxs-lookup"><span data-stu-id="dc83e-102">Walkthrough: Style WPF content</span></span>

<span data-ttu-id="dc83e-103">この記事では、Windows フォームでホストされている Windows Presentation Foundation (WPF) コントロールにスタイルを適用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dc83e-103">This article show you how to apply styling to a Windows Presentation Foundation (WPF) control hosted on a Windows Form.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="dc83e-104">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="dc83e-104">Prerequisites</span></span>

<span data-ttu-id="dc83e-105">このチュートリアルを完了するには Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="dc83e-105">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="dc83e-106">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="dc83e-106">Create the project</span></span>

<span data-ttu-id="dc83e-107">Visual Studio を開き、Visual Basic またはという名前の Visual C# で新しい Windows フォームアプリケーションプロジェクトを作成し `StylingWpfContent` ます。</span><span class="sxs-lookup"><span data-stu-id="dc83e-107">Open Visual Studio and create a new Windows Forms Application project in Visual Basic or Visual C# named `StylingWpfContent`.</span></span>

> [!NOTE]
> <span data-ttu-id="dc83e-108">WPF コンテンツをホストする場合は、C# プロジェクトと Visual Basic プロジェクトのみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="dc83e-108">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-the-wpf-control-types"></a><span data-ttu-id="dc83e-109">WPF コントロール型を作成する</span><span class="sxs-lookup"><span data-stu-id="dc83e-109">Create the WPF control types</span></span>

<span data-ttu-id="dc83e-110">プロジェクトに追加した WPF コントロール型は、<xref:System.Windows.Forms.Integration.ElementHost> コントロールでホストできます。</span><span class="sxs-lookup"><span data-stu-id="dc83e-110">After you add a WPF control type to the project, you can host it in an <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>

1. <span data-ttu-id="dc83e-111">新しい WPF <xref:System.Windows.Controls.UserControl> プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="dc83e-111">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="dc83e-112">コントロール型の既定の名前である `UserControl1.xaml` を使用します。</span><span class="sxs-lookup"><span data-stu-id="dc83e-112">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="dc83e-113">詳細については、「 [チュートリアル: デザイン時の Windows フォームでの新しい WPF コンテンツの作成](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc83e-113">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="dc83e-114">デザイン ビューで `UserControl1` が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dc83e-114">In Design view, make sure that `UserControl1` is selected.</span></span>

3. <span data-ttu-id="dc83e-115">[ **プロパティ** ] ウィンドウで、 <xref:System.Windows.FrameworkElement.Width%2A> プロパティとプロパティの値を <xref:System.Windows.FrameworkElement.Height%2A> **200** に設定します。</span><span class="sxs-lookup"><span data-stu-id="dc83e-115">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

4. <span data-ttu-id="dc83e-116"><xref:System.Windows.Controls.Button?displayProperty=nameWithType>にコントロールを追加 <xref:System.Windows.Controls.UserControl> し、プロパティの値を <xref:System.Windows.Controls.ContentControl.Content%2A> **Cancel** に設定します。</span><span class="sxs-lookup"><span data-stu-id="dc83e-116">Add a <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.ContentControl.Content%2A> property to **Cancel**.</span></span>

5. <span data-ttu-id="dc83e-117">に2つ目のコントロールを追加 <xref:System.Windows.Controls.Button?displayProperty=nameWithType> <xref:System.Windows.Controls.UserControl> し、プロパティの値 <xref:System.Windows.Controls.ContentControl.Content%2A> を **OK** に設定します。</span><span class="sxs-lookup"><span data-stu-id="dc83e-117">Add a second <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.ContentControl.Content%2A> property to **OK**.</span></span>

6. <span data-ttu-id="dc83e-118">プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="dc83e-118">Build the project.</span></span>

## <a name="apply-a-style-to-a-wpf-control"></a><span data-ttu-id="dc83e-119">WPF コントロールへのスタイルの適用</span><span class="sxs-lookup"><span data-stu-id="dc83e-119">Apply a Style to a WPF Control</span></span>

<span data-ttu-id="dc83e-120">さまざまなスタイルを WPF コントロールに適用することで、外観や動作を変えることができます。</span><span class="sxs-lookup"><span data-stu-id="dc83e-120">You can apply different styling to a WPF control to change its appearance and behavior.</span></span>

1. <span data-ttu-id="dc83e-121">Windows フォーム デザイナーで `Form1` を開きます。</span><span class="sxs-lookup"><span data-stu-id="dc83e-121">Open `Form1` in the Windows Forms Designer.</span></span>

1. <span data-ttu-id="dc83e-122">**ツールボックス** で、をダブルクリックして、 `UserControl1` フォーム上にのインスタンスを作成し `UserControl1` ます。</span><span class="sxs-lookup"><span data-stu-id="dc83e-122">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>

   <span data-ttu-id="dc83e-123">`UserControl1` のインスタンスは、`elementHost1` という名前の新しい <xref:System.Windows.Forms.Integration.ElementHost> コントロールでホストされます。</span><span class="sxs-lookup"><span data-stu-id="dc83e-123">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

1. <span data-ttu-id="dc83e-124">のスマートタグパネルで `elementHost1` 、ドロップダウンリストから [ホストされている **コンテンツの編集** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc83e-124">In the smart tag panel for `elementHost1`, click **Edit Hosted Content** from the drop-down list.</span></span>

   <span data-ttu-id="dc83e-125">`UserControl1` WPF デザイナーでを開きます。</span><span class="sxs-lookup"><span data-stu-id="dc83e-125">`UserControl1` opens in the WPF Designer.</span></span>

1. <span data-ttu-id="dc83e-126">XAML ビューで、次の XAML を `<UserControl>` の開始タグの後に挿入します。</span><span class="sxs-lookup"><span data-stu-id="dc83e-126">In XAML view, insert the following XAML after the `<UserControl>` opening tag.</span></span> <span data-ttu-id="dc83e-127">この XAML は、明暗のあるグラデーション境界を持つグラデーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="dc83e-127">This XAML creates a gradient with a contrasting gradient border.</span></span> <span data-ttu-id="dc83e-128">このコントロールをクリックすると、グラデーションが変わり、ボタンを押したような外観が生成されます。</span><span class="sxs-lookup"><span data-stu-id="dc83e-128">When the control is clicked, the gradients are changed to generate a pressed button look.</span></span> <span data-ttu-id="dc83e-129">詳しくは、「 [スタイルとテンプレート](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dc83e-129">For more information, see [Styling and Templating](/dotnet/desktop-wpf/fundamentals/styles-templates-overview).</span></span>

   ```xaml
   <UserControl.Resources>
    <LinearGradientBrush x:Key="NormalBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#FFF" Offset="0.0"/>
        <GradientStop Color="#CCC" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="PressedBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#BBB" Offset="0.0"/>
        <GradientStop Color="#EEE" Offset="0.1"/>
        <GradientStop Color="#EEE" Offset="0.9"/>
        <GradientStop Color="#FFF" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="NormalBorderBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#CCC" Offset="0.0"/>
        <GradientStop Color="#444" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="BorderBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#CCC" Offset="0.0"/>
        <GradientStop Color="#444" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="PressedBorderBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#444" Offset="0.0"/>
        <GradientStop Color="#888" Offset="1.0"/>
    </LinearGradientBrush>

    <Style x:Key="SimpleButton" TargetType="{x:Type Button}" BasedOn="{x:Null}">
        <Setter Property="Background" Value="{StaticResource NormalBrush}"/>
        <Setter Property="BorderBrush" Value="{StaticResource NormalBorderBrush}"/>
        <Setter Property="Template">
            <Setter.Value>
                <ControlTemplate TargetType="{x:Type Button}">
                    <Grid x:Name="Grid">
                        <Border x:Name="Border" Background="{TemplateBinding Background}" BorderBrush="{TemplateBinding BorderBrush}" BorderThickness="{TemplateBinding BorderThickness}" Padding="{TemplateBinding Padding}"/>
                        <ContentPresenter HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" Margin="{TemplateBinding Padding}" VerticalAlignment="{TemplateBinding VerticalContentAlignment}" RecognizesAccessKey="True"/>
                    </Grid>
                    <ControlTemplate.Triggers>
                        <Trigger Property="IsPressed" Value="true">
                            <Setter Property="Background" Value="{StaticResource PressedBrush}" TargetName="Border"/>
                            <Setter Property="BorderBrush" Value="{StaticResource PressedBorderBrush}" TargetName="Border"/>
                        </Trigger>
                    </ControlTemplate.Triggers>
                </ControlTemplate>
            </Setter.Value>
        </Setter>
    </Style>
   </UserControl.Resources>
   ```

1. <span data-ttu-id="dc83e-130">`SimpleButton` `<Button>` **[キャンセル**] ボタンのタグに次の XAML を挿入して、前の手順で定義したスタイルを [キャンセル] ボタンに適用します。</span><span class="sxs-lookup"><span data-stu-id="dc83e-130">Apply the `SimpleButton` style defined in the previous step to the Cancel button by inserting the following XAML in the `<Button>` tag of the **Cancel** button.</span></span>

   ```xaml
   Style="{StaticResource SimpleButton}
   ```

   <span data-ttu-id="dc83e-131">ボタン宣言は、次の XAML のようになります。</span><span class="sxs-lookup"><span data-stu-id="dc83e-131">Your button declaration will resemble the following XAML:</span></span>

   ```xaml
   <Button Height="23" Margin="41,52,98,0" Name="button1" VerticalAlignment="Top"
                Style="{StaticResource SimpleButton}">Cancel</Button>
   ```

1. <span data-ttu-id="dc83e-132">プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="dc83e-132">Build the project.</span></span>

1. <span data-ttu-id="dc83e-133">Windows フォーム デザイナーで `Form1` を開きます。</span><span class="sxs-lookup"><span data-stu-id="dc83e-133">Open `Form1` in the Windows Forms Designer.</span></span>

1. <span data-ttu-id="dc83e-134">新しいスタイルが Button コントロールに適用されます。</span><span class="sxs-lookup"><span data-stu-id="dc83e-134">The new style is applied to the button control.</span></span>

1. <span data-ttu-id="dc83e-135">[ **デバッグ** ] メニューの [ **デバッグ開始** ] をクリックして、アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="dc83e-135">From the **Debug** menu, select **Start Debugging** to run the application.</span></span>

1. <span data-ttu-id="dc83e-136">[ **OK]** ボタンと **[キャンセル** ] ボタンをクリックして、相違点を確認します。</span><span class="sxs-lookup"><span data-stu-id="dc83e-136">Click the **OK** and **Cancel** buttons and view the differences.</span></span>

## <a name="see-also"></a><span data-ttu-id="dc83e-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="dc83e-137">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="dc83e-138">移行と相互運用性</span><span class="sxs-lookup"><span data-stu-id="dc83e-138">Migration and Interoperability</span></span>](/dotnet/framework/wpf/advanced/migration-and-interoperability)
- [<span data-ttu-id="dc83e-139">WPF コントロールの使用</span><span class="sxs-lookup"><span data-stu-id="dc83e-139">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="dc83e-140">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="dc83e-140">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="dc83e-141">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="dc83e-141">XAML Overview (WPF)</span></span>](/dotnet/desktop-wpf/fundamentals/xaml)
- [<span data-ttu-id="dc83e-142">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="dc83e-142">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
