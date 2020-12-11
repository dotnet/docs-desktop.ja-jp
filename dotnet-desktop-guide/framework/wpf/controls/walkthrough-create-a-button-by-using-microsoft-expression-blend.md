---
title: 'チュートリアル: Microsoft Expression Blend を使用してボタンを作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [WPF]
- converting [WPF], shape to button
- Expression Blend [WPF Designer]
ms.assetid: ff5037c2-bba7-4cae-8abb-6475b686c48e
ms.openlocfilehash: bcf1c14980556caf7c08be03e12467c86ab3c6a1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985603"
---
# <a name="walkthrough-create-a-button-by-using-microsoft-expression-blend"></a><span data-ttu-id="2bc1d-102">チュートリアル: Microsoft Expression Blend を使用してボタンを作成する</span><span class="sxs-lookup"><span data-stu-id="2bc1d-102">Walkthrough: Create a Button by Using Microsoft Expression Blend</span></span>

<span data-ttu-id="2bc1d-103">このチュートリアルでは、Microsoft Expression Blend を使用して WPF のカスタマイズされたボタンを作成する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-103">This walkthrough steps you through the process of creating a WPF customized button using Microsoft Expression Blend.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2bc1d-104">Microsoft Expression Blend は、[!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] を生成することによって機能し、これがコンパイルされて実行可能プログラムが作成されます。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-104">Microsoft Expression Blend works by generating [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] that is then compiled to make the executable program.</span></span> <span data-ttu-id="2bc1d-105">XAML を直接操作する場合は、Blend ではなく Visual Studio で XAML を使用して、これと同じアプリケーションを作成するもう 1 つのチュートリアルが用意されています。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-105">If you would rather work with XAML directly, there is another walkthrough that creates the same application as this one using XAML with Visual Studio rather than Blend.</span></span> <span data-ttu-id="2bc1d-106">詳細については、[XAML を使用したボタンの作成](walkthrough-create-a-button-by-using-xaml.md)に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-106">See [Create a Button by Using XAML](walkthrough-create-a-button-by-using-xaml.md) for more information.</span></span>

<span data-ttu-id="2bc1d-107">次の図は、作成するカスタマイズされたボタンを示しています。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-107">The following illustration shows the customized button that you will create.</span></span>

![作成するカスタマイズされたボタン](./media/custom-button-blend-intro.jpg)

## <a name="convert-a-shape-to-a-button"></a><span data-ttu-id="2bc1d-109">シェイプをボタンに変換する</span><span class="sxs-lookup"><span data-stu-id="2bc1d-109">Convert a Shape to a Button</span></span>

<span data-ttu-id="2bc1d-110">このチュートリアルの最初の部分では、カスタム ボタンの外観を独自に作成します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-110">In the first part of this walkthrough you create the custom look of the custom button.</span></span> <span data-ttu-id="2bc1d-111">これを行うには、最初に四角形をボタンに変換します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-111">To do this, you first convert a rectangle to a button.</span></span> <span data-ttu-id="2bc1d-112">次に、ボタンのテンプレートにその他のシェイプを追加して、より複雑な外観のボタンを作成します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-112">You then add additional shapes to the template of the button, creating a more complex looking button.</span></span> <span data-ttu-id="2bc1d-113">通常のボタンから始めてそれをカスタマイズしないのはなぜでしょうか。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-113">Why not start with a regular button and customize it?</span></span> <span data-ttu-id="2bc1d-114">それは、ボタンには、不要な組み込みの機能が含まれるためです。カスタム ボタンの場合は、四角形から始める方が簡単です。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-114">Because a button has built-in functionality that you do not need; for custom buttons, it is easier to start with a rectangle.</span></span>

### <a name="to-create-a-new-project-in-expression-blend"></a><span data-ttu-id="2bc1d-115">Expression Blend で新しいプロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="2bc1d-115">To create a new project in Expression Blend</span></span>

1. <span data-ttu-id="2bc1d-116">Expression Blend を起動します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-116">Start Expression Blend.</span></span> <span data-ttu-id="2bc1d-117">( **[スタート]** をクリックし、 **[すべてのプログラム]** 、 **[Microsoft Expression]** の順にポイントして、 **[Microsoft Expression Blend]** をクリックします。)</span><span class="sxs-lookup"><span data-stu-id="2bc1d-117">(Click **Start**, point to **All Programs**, point to **Microsoft Expression**, and then click **Microsoft Expression Blend**.)</span></span>

2. <span data-ttu-id="2bc1d-118">必要に応じて、アプリケーションを最大化します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-118">Maximize the application if needed.</span></span>

3. <span data-ttu-id="2bc1d-119">**[ファイル]** メニューの **[新しいプロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-119">On the **File** menu, click **New Project**.</span></span>

4. <span data-ttu-id="2bc1d-120">**[標準アプリケーション (.exe)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-120">Select **Standard Application (.exe)**.</span></span>

5. <span data-ttu-id="2bc1d-121">プロジェクトに `CustomButton` という名前を指定し、 **[OK]** を押します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-121">Name the project `CustomButton` and press **OK**.</span></span>

<span data-ttu-id="2bc1d-122">この時点で、空の WPF プロジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-122">At this point you have a blank WPF project.</span></span> <span data-ttu-id="2bc1d-123">F5 キーを押してアプリケーションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-123">You can press F5 to run the application.</span></span> <span data-ttu-id="2bc1d-124">ご想像のとおり、アプリケーションは空白のウィンドウだけで構成されています。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-124">As you might expect, the application consists of only a blank window.</span></span> <span data-ttu-id="2bc1d-125">次に、角丸四角形を作成してボタンに変換します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-125">Next, you create a rounded rectangle and convert it into a button.</span></span>

### <a name="to-convert-a-rectangle-to-a-button"></a><span data-ttu-id="2bc1d-126">四角形をボタンに変換するには</span><span class="sxs-lookup"><span data-stu-id="2bc1d-126">To convert a Rectangle to a Button</span></span>

1. <span data-ttu-id="2bc1d-127">**Window の Background プロパティを黒に設定する:** Window を選択し、 **[プロパティ] タブ** をクリックして、<xref:System.Windows.Controls.Control.Background%2A> プロパティを `Black` に設定します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-127">**Set the Window Background property to black:** Select the Window, click the **Properties Tab**, and set the <xref:System.Windows.Controls.Control.Background%2A> property to `Black`.</span></span>

    ![ボタンの背景を黒に設定する方法](./media/custom-button-blend-changebackground.png)

2. <span data-ttu-id="2bc1d-129">**Window のボタンとほぼ同じサイズになる四角形を描画する:** 左側のツール パネルで四角形のツールを選択し、Window 上に四角形をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-129">**Draw a rectangle approximately the size of a button on the Window:** Select the rectangle tool on the left-hand tool panel and drag the rectangle onto the Window.</span></span>

    ![四角形を描画する方法](./media/custom-button-blend-drawrect.png)

3. <span data-ttu-id="2bc1d-131">**四角形の角を丸める:** 四角形のコントロール ポイントをドラッグするか、<xref:System.Windows.Shapes.Rectangle.RadiusX%2A> と <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> のプロパティを直接設定します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-131">**Round out the corners of the rectangle:** Either drag the control points of the rectangle or directly set the <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> and <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> properties.</span></span> <span data-ttu-id="2bc1d-132"><xref:System.Windows.Shapes.Rectangle.RadiusX%2A> と <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> の値を 20 に設定します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-132">Set the values of <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> and <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> to 20.</span></span>

    ![四角形の角を丸くする方法](./media/custom-button-blend-roundcorners.png)

4. <span data-ttu-id="2bc1d-134">**四角形をボタンに変更する:** 四角形を選択します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-134">**Change the rectangle into a button:** Select the rectangle.</span></span> <span data-ttu-id="2bc1d-135">**[ツール]** メニューで **[ボタンの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-135">On the **Tools** menu, click **Make Button**.</span></span>

    ![シェイプをボタンにする方法](./media/custom-button-blend-makebutton.png)

5. <span data-ttu-id="2bc1d-137">**スタイルまたはテンプレートの範囲を指定する:** 次のようなダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-137">**Specify the scope of the style/template:** A dialog box like the following appears.</span></span>

    ![[スタイル リソースの作成] ダイアログ ボックス](./media/custom-button-blend-makebutton2.gif)

    <span data-ttu-id="2bc1d-139">**[リソース名 (キー)]** には、 **[すべてに適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-139">For **Resource name (Key)**, select **Apply to all**.</span></span>  <span data-ttu-id="2bc1d-140">これにより、生成されるスタイルとボタン テンプレートが、ボタンであるすべてのオブジェクトに適用されます。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-140">This will make the resulting style and button template apply to all objects that are buttons.</span></span> <span data-ttu-id="2bc1d-141">**[定義先]** には、 **[アプリケーション]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-141">For **Define in**, select **Application**.</span></span> <span data-ttu-id="2bc1d-142">これにより、生成されるスタイルとボタン テンプレートの対象範囲がアプリケーション全体になります。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-142">This will make the resulting style and button template have scope over the entire application.</span></span> <span data-ttu-id="2bc1d-143">これらの 2 つのボックスの値を設定すると、ボタンのスタイルとテンプレートはアプリケーション全体のすべてのボタンに適用されます。また、アプリケーションで作成したすべてのボタンで、既定でこのテンプレートが使用されます。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-143">When you set the values in these two boxes, the button style and template apply to all buttons within the entire application and any button you create in the application will, by default, use this template.</span></span>

## <a name="edit-the-button-template"></a><span data-ttu-id="2bc1d-144">ボタン テンプレートを編集する</span><span class="sxs-lookup"><span data-stu-id="2bc1d-144">Edit the Button Template</span></span>

<span data-ttu-id="2bc1d-145">これで、ボタンに変更された四角形ができました。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-145">You now have a rectangle that has been changed to a button.</span></span> <span data-ttu-id="2bc1d-146">このセクションでは、ボタンのテンプレートを変更し、その外観をさらにカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-146">In this section, you'll modify the template of the button and further customize how it looks.</span></span>

### <a name="to-edit-the-button-template-to-change-the-button-appearance"></a><span data-ttu-id="2bc1d-147">ボタン テンプレートを編集してボタンの外観を変更するには</span><span class="sxs-lookup"><span data-stu-id="2bc1d-147">To edit the button template to change the button appearance</span></span>

1. <span data-ttu-id="2bc1d-148">**テンプレートの編集ビューに移動する:** ボタンの外観をさらにカスタマイズするには、ボタン テンプレートを編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-148">**Go into edit template view:** To further customize the look of our button, we need to edit the button template.</span></span> <span data-ttu-id="2bc1d-149">このテンプレートは、四角形をボタンに変換したときに作成されたものです。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-149">This template was created when we converted the rectangle into a button.</span></span> <span data-ttu-id="2bc1d-150">ボタン テンプレートを編集するには、ボタンを右クリックして **[コントロール パーツ (テンプレート) の編集]** を選択し、 **[テンプレートの編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-150">To edit the button template, right-click the button and select **Edit Control Parts (Template)** and then **Edit Template**.</span></span>

    ![テンプレートを編集する方法](./media/custom-button-blend-edittemplate.jpg)

    <span data-ttu-id="2bc1d-152">テンプレート エディターでは、現在、ボタンが <xref:System.Windows.Shapes.Rectangle> と <xref:System.Windows.Controls.ContentPresenter> に分割されていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-152">In the template editor, notice that the button is now separated into a <xref:System.Windows.Shapes.Rectangle> and the <xref:System.Windows.Controls.ContentPresenter>.</span></span> <span data-ttu-id="2bc1d-153"><xref:System.Windows.Controls.ContentPresenter> は、ボタン内に内容を表示するために使用されます (たとえば、文字列 "Button")。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-153">The <xref:System.Windows.Controls.ContentPresenter> is used to present content within the button (for example, the string "Button").</span></span> <span data-ttu-id="2bc1d-154">Rectangle と <xref:System.Windows.Controls.ContentPresenter> はどちらも <xref:System.Windows.Controls.Grid> 内にレイアウトされます。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-154">Both the rectangle and <xref:System.Windows.Controls.ContentPresenter> are laid out inside of a <xref:System.Windows.Controls.Grid>.</span></span>

    ![四角形に表示されるコンポーネント](./media/custom-button-blend-templatepanel.png)

2. <span data-ttu-id="2bc1d-156">**テンプレート コンポーネントの名前を変更する:** テンプレート インベントリ内の四角形を右クリックして、<xref:System.Windows.Shapes.Rectangle> の名前を "[Rectangle]" から "outerRectangle" に変更し、"[ContentPresenter]" を "myContentPresenter" に変更します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-156">**Change the names of the template components:** Right-click the rectangle in the template inventory, change the <xref:System.Windows.Shapes.Rectangle> name from "[Rectangle]" to "outerRectangle", and change "[ContentPresenter]" to "myContentPresenter".</span></span>

    ![テンプレートのコンポーネント名を変更する方法](./media/custom-button-blend-renamecomponents.png)

3. <span data-ttu-id="2bc1d-158">**(ドーナツのように) 内側が空白になるように四角形を変更する:** **outerRectangle** を選択して、<xref:System.Windows.Shapes.Shape.Fill%2A> を "Transparent" に、<xref:System.Windows.Shapes.Shape.StrokeThickness%2A> を 5 に設定します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-158">**Alter the rectangle so that it is empty inside (like a donut):** Select **outerRectangle** and set <xref:System.Windows.Shapes.Shape.Fill%2A> to "Transparent" and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> to 5.</span></span>

    ![四角形を空白にする方法](./media/custom-button-blend-changerectproperties.png)

    <span data-ttu-id="2bc1d-160">次に、<xref:System.Windows.Shapes.Shape.Stroke%2A> を、テンプレートに設定する任意の色に設定します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-160">Then set the <xref:System.Windows.Shapes.Shape.Stroke%2A> to the color of whatever the template will be.</span></span> <span data-ttu-id="2bc1d-161">これを行うには、 **[ストローク]** の横にある小さな白いボックスをクリックし、 **[CustomExpression]** を選択して、ダイアログ ボックスに「{TemplateBinding Background}」と入力します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-161">To do this, click the small white box next to **Stroke**, select **CustomExpression**, and type "{TemplateBinding Background}" in the dialog box.</span></span>

    ![テンプレートの色の使用を設定する方法](./media/custom-button-blend-templatestroke.png)

4. <span data-ttu-id="2bc1d-163">**内部の四角形を作成する:** 次に、別の四角形を作成し ("innerRectangle" という名前を付けます)、**outerRectangle** の内部の上に対称的に配置します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-163">**Create an inner rectangle:** Now, create another rectangle (name it "innerRectangle") and position it symmetrically on the inside of **outerRectangle** .</span></span> <span data-ttu-id="2bc1d-164">このような作業では、ズームして、編集領域のボタンのサイズを大きくすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-164">For this kind of work, you will probably want to zoom to make the button larger in the editing area.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2bc1d-165">四角形の外観は、次の図のものとは異なる場合があります (たとえば、角が丸い場合があります)。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-165">Your rectangle might look different than the one in the figure (for example, it might have rounded corners).</span></span>

    ![別の四角形の中に四角形を作成する方法](./media/custom-button-blend-innerrectangleproperties.png)

5. <span data-ttu-id="2bc1d-167">**ContentPresenter を一番上に移動する:** この時点で、テキスト "Button" が表示されなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-167">**Move ContentPresenter to the top:** At this point, it is possible that the text "Button" will not be visible any longer.</span></span> <span data-ttu-id="2bc1d-168">そのような場合は、**innerRectangle** が **myContentPresenter** の上にあることが原因です。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-168">If this is so, this is because **innerRectangle** is on top of the **myContentPresenter**.</span></span> <span data-ttu-id="2bc1d-169">これを修正するには、**myContentPresenter** を **innerRectangle** の下にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-169">To fix this, drag **myContentPresenter** below **innerRectangle**.</span></span> <span data-ttu-id="2bc1d-170">以下のように、四角形と **myContentPresenter** の位置を変更します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-170">Reposition rectangles and **myContentPresenter** to look similar to below.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2bc1d-171">または、**myContentPresenter** を右クリックして **[Send Forward]\(前に送る\)** を押すことで、それを一番上に配置することもできます。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-171">Alternatively, you can also position **myContentPresenter** on top by right-clicking it and pressing **Send Forward**.</span></span>

    ![別のボタンの上にボタンを移動する方法](./media/custom-button-blend-innerrectangle2.png)

6. <span data-ttu-id="2bc1d-173">**innerRectangle の外観を変更する:** <xref:System.Windows.Shapes.Rectangle.RadiusX%2A>、<xref:System.Windows.Shapes.Rectangle.RadiusY%2A>、および <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> の値を 20 に設定します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-173">**Change the look of innerRectangle:** Set the <xref:System.Windows.Shapes.Rectangle.RadiusX%2A>, <xref:System.Windows.Shapes.Rectangle.RadiusY%2A>, and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> values to 20.</span></span> <span data-ttu-id="2bc1d-174">さらに、カスタム式 "{TemplateBinding Background}" ) を使用して <xref:System.Windows.Shapes.Shape.Fill%2A> をテンプレートの背景に設定し、<xref:System.Windows.Shapes.Shape.Stroke%2A> を "transparent" に設定します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-174">In addition, set the <xref:System.Windows.Shapes.Shape.Fill%2A> to the background of the template using the custom expression "{TemplateBinding Background}" ) and set <xref:System.Windows.Shapes.Shape.Stroke%2A> to "transparent".</span></span> <span data-ttu-id="2bc1d-175">**innerRectangle** の <xref:System.Windows.Shapes.Shape.Fill%2A> と <xref:System.Windows.Shapes.Shape.Stroke%2A> の設定は、**outerRectangle** の設定とは逆になっていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-175">Notice that the settings for the <xref:System.Windows.Shapes.Shape.Fill%2A> and <xref:System.Windows.Shapes.Shape.Stroke%2A> of **innerRectangle** are the opposite of those for **outerRectangle**.</span></span>

    ![四角形の外観を変更する方法](./media/custom-button-blend-glassrectangleproperties1.png)

7. <span data-ttu-id="2bc1d-177">**上部にグラス レイヤーを追加する:** ボタンの外観をカスタマイズする最後の手順は、上部にグラス レイヤーを追加することです。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-177">**Add a glass layer on top:** The final piece of customizing the look of the button is to add a glass layer on top.</span></span> <span data-ttu-id="2bc1d-178">このグラス レイヤーは、3 つ目の四角形で構成されます。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-178">This glass layer consists of a third rectangle.</span></span> <span data-ttu-id="2bc1d-179">グラスによってボタン全体が覆われるため、グラスの四角形のディメンションは **outerRectangle** と似たものになります。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-179">Because the glass will cover the entire button, the glass rectangle is similar in dimensions to the **outerRectangle**.</span></span> <span data-ttu-id="2bc1d-180">したがって、**outerRectangle** のコピーを作成するだけで、四角形を作成できます。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-180">Therefore, create the rectangle by simply making a copy of the **outerRectangle**.</span></span> <span data-ttu-id="2bc1d-181">**outerRectangle** を強調表示し、Ctrl + C キーと Ctrl + V キーを使用してコピーを作成します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-181">Highlight **outerRectangle** and use CTRL+C and CTRL+V to make a copy.</span></span> <span data-ttu-id="2bc1d-182">この新しい四角形に "glassCube" という名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-182">Name this new rectangle "glassCube".</span></span>

8. <span data-ttu-id="2bc1d-183">**必要に応じて glassCube の位置を変更する:** **glassCube** がまだボタン全体を覆うように配置されていない場合は、その位置にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-183">**Reposition glassCube if necessary:** If **glassCube** is not already positioned so that it covers the entire button, drag it into position.</span></span>

9. <span data-ttu-id="2bc1d-184">**glassCube に outerRectangle とは少し異なるシェイプを指定する:** **glassCube** のプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-184">**Give glassCube a slightly different shape than outerRectangle:** Change the properties of **glassCube**.</span></span> <span data-ttu-id="2bc1d-185">まず、<xref:System.Windows.Shapes.Rectangle.RadiusX%2A> と <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> のプロパティを 10 に変更し、<xref:System.Windows.Shapes.Shape.StrokeThickness%2A> を 2 に変更します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-185">Start off by changing the <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> and <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> properties to 10 and the <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> to 2.</span></span>

    ![glassCube の外観設定](./media/custom-button-blend-glasscubeappearance.gif)

10. <span data-ttu-id="2bc1d-187">**glassCube をグラスのように表示する:** <xref:System.Windows.Shapes.Shape.Fill%2A> をグラスのような外観に設定するには、75% 不透明な線状グラデーションを使用して、白色と透明を大体均等な間隔で 6 回交互に配置します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-187">**Make glassCube look like glass:** Set the <xref:System.Windows.Shapes.Shape.Fill%2A> to a glassy look by  using a linear gradient that is 75% opaque and alternates between the color White and Transparent over 6 approximately evenly spaced intervals.</span></span> <span data-ttu-id="2bc1d-188">グラデーション境界に設定するものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-188">This is what to set the gradient stops to:</span></span>

    - <span data-ttu-id="2bc1d-189">グラデーション境界 1:アルファ値が 75% の白</span><span class="sxs-lookup"><span data-stu-id="2bc1d-189">Gradient Stop 1: White with Alpha value of 75%</span></span>

    - <span data-ttu-id="2bc1d-190">グラデーション境界 2:透明</span><span class="sxs-lookup"><span data-stu-id="2bc1d-190">Gradient Stop 2: Transparent</span></span>

    - <span data-ttu-id="2bc1d-191">グラデーション境界 3:アルファ値が 75% の白</span><span class="sxs-lookup"><span data-stu-id="2bc1d-191">Gradient Stop 3: White with Alpha value of 75%</span></span>

    - <span data-ttu-id="2bc1d-192">グラデーション境界 4:透明</span><span class="sxs-lookup"><span data-stu-id="2bc1d-192">Gradient Stop 4: Transparent</span></span>

    - <span data-ttu-id="2bc1d-193">グラデーション境界 5:アルファ値が 75% の白</span><span class="sxs-lookup"><span data-stu-id="2bc1d-193">Gradient Stop 5: White with Alpha value of 75%</span></span>

    - <span data-ttu-id="2bc1d-194">グラデーション境界 6:透明</span><span class="sxs-lookup"><span data-stu-id="2bc1d-194">Gradient Stop 6: Transparent</span></span>

    <span data-ttu-id="2bc1d-195">これにより、"波形" グラスの外観が作成されます。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-195">This creates a "wavy" glass look.</span></span>

    ![グラスのような四角形](./media/custom-button-blend-glassrectangleproperties2.png)

11. <span data-ttu-id="2bc1d-197">**グラス レイヤーを非表示にする:** グラス レイヤーの外観を確認したので、 **[プロパティ] パネル** の **[外観] ペイン** に移動し、不透明度を 0% に設定して非表示にします。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-197">**Hide the glass layer:** Now that you see what the glassy layer looks like, go into the **Appearance pane** of the **Properties panel** and set the Opacity to 0% to hide it.</span></span> <span data-ttu-id="2bc1d-198">この後のセクションでは、プロパティ トリガーとイベントを使用して、グラス レイヤーの表示と操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-198">In the sections ahead, we'll use property triggers and events to show and manipulate the glass layer.</span></span>

    ![グラス四角形を非表示にする方法](./media/custom-button-glassrectangleproperties3.gif)

## <a name="customize-the-button-behavior"></a><span data-ttu-id="2bc1d-200">ボタンの動作をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="2bc1d-200">Customize the Button Behavior</span></span>

<span data-ttu-id="2bc1d-201">これまではテンプレートを編集することでボタンの表示をカスタマイズしましたが、このボタンは、通常のボタンのようにユーザーのアクションに応答することはありません (たとえば、マウスによるポイント、フォーカスの受け取り、クリックなどで外観を変更する場合)。次の 2 つの手順では、これらのような動作をカスタム ボタンに構築する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-201">At this point, you have customized the presentation of the button by editing its template, but the button does not react to user actions as typical buttons do (for example, changing appearance upon mouse-over, receiving focus, and clicking.) The next two procedures show how to build behaviors like these into the custom button.</span></span> <span data-ttu-id="2bc1d-202">まずシンプルなプロパティ トリガーから始めて、次にイベント トリガーとアニメーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-202">We'll start with simple property triggers, and then add event triggers and animations.</span></span>

### <a name="to-set-property-triggers"></a><span data-ttu-id="2bc1d-203">プロパティ トリガーを設定するには</span><span class="sxs-lookup"><span data-stu-id="2bc1d-203">To set property triggers</span></span>

1. <span data-ttu-id="2bc1d-204">**新しいプロパティ トリガーを作成する:** **glassCube** を選択した状態で、 **[トリガー]** パネルの **[+ プロパティ]** をクリックします (次の手順の後の図を参照)。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-204">**Create a new property trigger:** With **glassCube** selected, click **+ Property** in the **Triggers** panel (see the figure that follows the next step).</span></span> <span data-ttu-id="2bc1d-205">これにより、既定のプロパティ トリガーでプロパティ トリガーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-205">This creates a property trigger with a default property trigger.</span></span>

2. <span data-ttu-id="2bc1d-206">**IsMouseOver をトリガーによって使用されるプロパティにする:** プロパティを <xref:System.Windows.UIElement.IsMouseOver%2A> に変更します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-206">**Make IsMouseOver the property used by the trigger:** Change the property to <xref:System.Windows.UIElement.IsMouseOver%2A>.</span></span> <span data-ttu-id="2bc1d-207">これにより、<xref:System.Windows.UIElement.IsMouseOver%2A> プロパティが `true` のとき (ユーザーがマウスでボタンをポイントしたとき) にプロパティ トリガーがアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-207">This makes the property trigger activate when the <xref:System.Windows.UIElement.IsMouseOver%2A> property is `true` (when the user points to the button with the mouse).</span></span>

    ![プロパティでトリガーを設定する方法](./media/custom-button-blend-ismousedoverpropertytrigger.png)

3. <span data-ttu-id="2bc1d-209">**IsMouseOver で glassCube の 100% の不透明度をトリガーする:** **[Trigger recording is on]\(トリガーの記録オン\)** が表示されます (前の図を参照)。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-209">**IsMouseOver triggers opacity of 100% for glassCube:** Notice that the **Trigger recording is on** (see the preceding figure).</span></span> <span data-ttu-id="2bc1d-210">これは、記録がオンであるときに **glassCube** のプロパティ値に加えた変更が、<xref:System.Windows.UIElement.IsMouseOver%2A> が `true` のときに行われるアクションになることを意味します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-210">This means that any changes you make to the property values of **glassCube** while recording is on will become an action that takes place when <xref:System.Windows.UIElement.IsMouseOver%2A> is `true`.</span></span> <span data-ttu-id="2bc1d-211">記録中に、**glassCube** の <xref:System.Windows.UIElement.Opacity%2A> を 100% に変更します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-211">While recording, change the <xref:System.Windows.UIElement.Opacity%2A> of **glassCube** to 100%.</span></span>

    ![ボタンの不透明度を設定する方法](./media/custom-button-blend-ismousedoverpropertytrigger2.gif)

    <span data-ttu-id="2bc1d-213">これで、最初のプロパティ トリガーを作成できました。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-213">You have now created your first property trigger.</span></span> <span data-ttu-id="2bc1d-214">エディターの **[トリガー] パネル** によって、100% に変更される <xref:System.Windows.UIElement.Opacity%2A> が記録されたことがわかります。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-214">Notice that the **Triggers panel** of the editor has recorded the <xref:System.Windows.UIElement.Opacity%2A> being changed to 100%.</span></span>

    ![[トリガー] パネル](./media/custom-button-blend-propertytriggerinfo.png)

    <span data-ttu-id="2bc1d-216">F5 キーを押してアプリケーションを実行し、マウス ポインターをボタンの上と外部に移動します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-216">Press F5 to run the application, and move the mouse pointer over and off the button.</span></span> <span data-ttu-id="2bc1d-217">ボタンをマウスでポイントするとグラス レイヤーが表示され、ポインターが離れると消えるはずです。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-217">You should see the glass layer appear when you mouse-over the button and disappear when the pointer leaves.</span></span>

4. <span data-ttu-id="2bc1d-218">**IsMouseOver でストローク値の変更をトリガーする:** 他のいくつかのアクションを <xref:System.Windows.UIElement.IsMouseOver%2A> トリガーに関連付けてみましょう。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-218">**IsMouseOver triggers stroke value change:** Let's associate some other actions with the <xref:System.Windows.UIElement.IsMouseOver%2A> trigger.</span></span> <span data-ttu-id="2bc1d-219">記録が続いている間に、**glassCube** から **outerRectangle** に選択を切り替えます。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-219">While recording continues, switch your selection from **glassCube** to **outerRectangle**.</span></span> <span data-ttu-id="2bc1d-220">次に、**outerRectangle** の <xref:System.Windows.Shapes.Shape.Stroke%2A> をカスタム式 "{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" に設定します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-220">Then set the <xref:System.Windows.Shapes.Shape.Stroke%2A> of **outerRectangle** to the custom expression of "{DynamicResource {x:Static SystemColors.HighlightBrushKey}}".</span></span> <span data-ttu-id="2bc1d-221">これにより、<xref:System.Windows.Shapes.Shape.Stroke%2A> が、ボタンによって使用される一般的な強調表示色に設定されます。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-221">This sets the <xref:System.Windows.Shapes.Shape.Stroke%2A> to the typical highlight color used by buttons.</span></span> <span data-ttu-id="2bc1d-222">F5 キーを押して、ボタンにマウスをポイントしたときの効果を確認します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-222">Press F5 to see the effect when you mouse over the button.</span></span>

    ![ストロークを強調表示色に設定する方法](./media/custom-button-blend-ismousedoverpropertytrigger3.png)

5. <span data-ttu-id="2bc1d-224">**IsMouseOver でぼやけたテキストをトリガーする:** もう 1 つのアクションを <xref:System.Windows.UIElement.IsMouseOver%2A> プロパティ トリガーに関連付けてみましょう。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-224">**IsMouseOver triggers blurry text:** Let's associate one more action to the <xref:System.Windows.UIElement.IsMouseOver%2A> property trigger.</span></span> <span data-ttu-id="2bc1d-225">ボタンの上にグラスが表示されているときに、ボタンの内容が少しぼやけて表示されるようにします。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-225">Make the content of the button appear a little blurry when the glass appears over it.</span></span> <span data-ttu-id="2bc1d-226">これを行うには、ぼかしの <xref:System.Windows.Media.Effects.BitmapEffect> を <xref:System.Windows.Controls.ContentPresenter> (**myContentPresenter**) に適用します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-226">To do this, we can apply a blur <xref:System.Windows.Media.Effects.BitmapEffect> to the <xref:System.Windows.Controls.ContentPresenter> (**myContentPresenter**).</span></span>

    ![ボタンの内容をぼかす方法](./media/custom-button-blend-propertytriggerwithbitmapeffect.png)

    > [!NOTE]
    > <span data-ttu-id="2bc1d-228">**[プロパティ] パネル** を <xref:System.Windows.Media.Effects.BitmapEffect> の検索を行う前の状態に戻すには、**検索ボックス** のテキストをクリアします。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-228">To return the **Properties panel** back to what it was before you did the search for <xref:System.Windows.Media.Effects.BitmapEffect>, clear the text from the **Search box**.</span></span>

    <span data-ttu-id="2bc1d-229">これまでに、いくつかのアクションが関連付けられたプロパティ トリガーを使用して、マウス ポインターがボタン領域に出入りするときの強調表示の動作を作成しました。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-229">At this point, we have used a property trigger with several associated actions to create highlighting behavior for when the mouse pointer enters and leaves the button area.</span></span> <span data-ttu-id="2bc1d-230">ボタンのもう 1 つの一般的な動作は、フォーカスがあるときに強調表示することです (クリックされた後など)。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-230">Another typical behavior for a button is to highlight when it has focus (as after it is clicked).</span></span> <span data-ttu-id="2bc1d-231">このような動作を追加するには、<xref:System.Windows.UIElement.IsFocused%2A> プロパティに対するもう 1 つのプロパティ トリガーを追加します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-231">We can add such behavior by adding another property trigger for the <xref:System.Windows.UIElement.IsFocused%2A> property.</span></span>

6. <span data-ttu-id="2bc1d-232">**IsFocused のプロパティ トリガーを作成する:** <xref:System.Windows.UIElement.IsMouseOver%2A> の場合と同じ手順 (このセクションの最初の手順を参照) を使用して、<xref:System.Windows.UIElement.IsFocused%2A> プロパティに対するもう 1 つのプロパティ トリガーを作成します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-232">**Create property trigger for IsFocused:** Using the same procedure as for <xref:System.Windows.UIElement.IsMouseOver%2A> (see the first step of this section), create another property trigger for the <xref:System.Windows.UIElement.IsFocused%2A> property.</span></span> <span data-ttu-id="2bc1d-233">**[Trigger recording is on]\(トリガーの記録オン\)** の状態で、次のアクションをトリガーに追加します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-233">While **Trigger recording is on**, add the following actions to the trigger:</span></span>

    - <span data-ttu-id="2bc1d-234">**glassCube** の <xref:System.Windows.UIElement.Opacity%2A> を 100% にする。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-234">**glassCube** gets an <xref:System.Windows.UIElement.Opacity%2A> of 100%.</span></span>

    - <span data-ttu-id="2bc1d-235">**outerRectangle** の <xref:System.Windows.Shapes.Shape.Stroke%2A> カスタム式の値を "{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" にする。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-235">**outerRectangle** gets a <xref:System.Windows.Shapes.Shape.Stroke%2A> custom expression value of "{DynamicResource {x:Static SystemColors.HighlightBrushKey}}".</span></span>

<span data-ttu-id="2bc1d-236">このチュートリアルの最後の手順として、ボタンにアニメーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-236">As the final step in this walkthrough, we will add animations to the button.</span></span> <span data-ttu-id="2bc1d-237">これらのアニメーションは、イベント (具体的には、<xref:System.Windows.UIElement.MouseEnter> イベントと <xref:System.Windows.Controls.Primitives.ButtonBase.Click> イベント) によってトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-237">These animations will be triggered by events—specifically, the <xref:System.Windows.UIElement.MouseEnter> and <xref:System.Windows.Controls.Primitives.ButtonBase.Click> events.</span></span>

### <a name="to-use-event-triggers-and-animations-to-add-interactivity"></a><span data-ttu-id="2bc1d-238">イベント トリガーとアニメーションを使用してインタラクティビティを追加するには</span><span class="sxs-lookup"><span data-stu-id="2bc1d-238">To use event triggers and animations to add interactivity</span></span>

1. <span data-ttu-id="2bc1d-239">**MouseEnter イベント トリガーを作成する:** 新しいイベント トリガーを追加し、トリガーで使用するイベントとして [<xref:System.Windows.UIElement.MouseEnter>] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-239">**Create a MouseEnter Event Trigger:** Add a new event trigger and select <xref:System.Windows.UIElement.MouseEnter> as the event to use in the trigger.</span></span>

     ![MouseEnter イベント トリガーを作成する方法](./media/custom-button-blend-mouseovereventtrigger.png)

2. <span data-ttu-id="2bc1d-241">**アニメーション タイムラインを作成する:** 次に、アニメーション タイムラインを <xref:System.Windows.UIElement.MouseEnter> イベントに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-241">**Create an animation timeline:** Next, associate an animation timeline to the <xref:System.Windows.UIElement.MouseEnter> event.</span></span>

    ![アニメーション タイムラインをイベントに追加する方法](./media/custom-button-blend-mouseovereventtrigger2.png)

    <span data-ttu-id="2bc1d-243">**[OK]** を押して新しいタイムラインを作成すると、**タイムライン パネル** が表示され、デザインパネルに [Timeline recording is on]\(タイムラインの記録オン\) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-243">After you press **OK** to create a new timeline, a **Timeline Panel** appears and "Timeline recording is on" is visible in the design panel.</span></span> <span data-ttu-id="2bc1d-244">これは、タイムラインでプロパティの変更の記録を開始できることを意味します (プロパティの変更をアニメーション化)。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-244">This means we can start recording property changes in the timeline (animate property changes).</span></span>

    > [!NOTE]
    > <span data-ttu-id="2bc1d-245">表示内容を確認するために、ウィンドウやパネルのサイズを変更する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-245">You may need to resize your window and/or panels to see the display.</span></span>

    ![タイムライン パネル](./media/custom-button-blend-mouseovereventtrigger3.png)

3. <span data-ttu-id="2bc1d-247">**キーフレームを作成する:** アニメーションを作成するには、アニメーション化するオブジェクトを選択し、タイムライン上に複数のキーフレームを作成します。また、これらのキーフレームの間には、アニメーションで補間するプロパティ値を設定します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-247">**Create a keyframe:** To create an animation, select the object you want to animate, create two or more keyframes on the timeline, and for those keyframes, set the property values you want the animation to interpolate between.</span></span> <span data-ttu-id="2bc1d-248">次の図は、キーフレームを作成する手順を示しています。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-248">The following figure guides you through the creation of a keyframe.</span></span>

    ![キーフレームを作成する方法](./media/custom-button-blend-mouseovereventtrigger4.png)

4. <span data-ttu-id="2bc1d-250">**このキーフレームで glassCube を縮小する:** 2 番目のキーフレームを選択した状態で、**サイズ変換** を使用して、**glassCube** のサイズをフル サイズの 90% に縮小します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-250">**Shrink glassCube at this keyframe:** With the second keyframe selected, shrink the size of the **glassCube** to 90% of its full size using the **Size Transform**.</span></span>

    ![ボタンのサイズを縮小する方法](./media/custom-button-blend-sizetransform.png)

    <span data-ttu-id="2bc1d-252">F5 キーを押してアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-252">Press F5 to run the application.</span></span> <span data-ttu-id="2bc1d-253">マウス ポインターをボタンの上に移動します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-253">Move the mouse pointer over the button.</span></span> <span data-ttu-id="2bc1d-254">ボタンの上のグラス レイヤーが縮小されることがわかります。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-254">Notice that the glass layer shrinks on top of the button.</span></span>

5. <span data-ttu-id="2bc1d-255">**もう 1 つのイベント トリガーを作成し、別のアニメーションを関連付ける:** もう 1 つアニメーションを追加してみましょう。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-255">**Create another Event Trigger and associate a different animation with it:** Let's add one more animation.</span></span> <span data-ttu-id="2bc1d-256">前のイベント トリガー アニメーションの作成に使用したものと同様の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-256">Use a similar procedure to what you used to create the previous event trigger animation:</span></span>

    1. <span data-ttu-id="2bc1d-257"><xref:System.Windows.Controls.Primitives.ButtonBase.Click> イベントを使用して、新しいイベント トリガーを作成します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-257">Create a new event trigger using the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event.</span></span>

    2. <span data-ttu-id="2bc1d-258">新しいタイムラインを <xref:System.Windows.Controls.Primitives.ButtonBase.Click> イベントに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-258">Associate a new timeline with the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event.</span></span>

        ![新しいタイムラインを作成する方法](./media/custom-button-blend-clickeventtrigger1.png)

    3. <span data-ttu-id="2bc1d-260">このタイムラインに対して、2 つのキーフレームを作成します。1 つ目は 0.0 秒、2 つ目は 0.3 秒にします。ｌ</span><span class="sxs-lookup"><span data-stu-id="2bc1d-260">For this timeline, create two keyframes, one at 0.0 seconds and the second one at 0.3 seconds.</span></span>

    4. <span data-ttu-id="2bc1d-261">0\.3 秒のキーフレームが強調表示されている状態で、**回転変換の角度** を 360 度に設定します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-261">With the keyframe at 0.3 seconds highlighted, set the **Rotate Transform Angle** to 360 degrees.</span></span>

        ![回転変換を作成する方法](./media/custom-button-blend-rotatetransform.gif)

    5. <span data-ttu-id="2bc1d-263">F5 キーを押してアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-263">Press F5 to run the application.</span></span> <span data-ttu-id="2bc1d-264">ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-264">Click the button.</span></span> <span data-ttu-id="2bc1d-265">グラス レイヤーが回転することがわかります。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-265">Notice that the glass layer spins around.</span></span>

## <a name="conclusion"></a><span data-ttu-id="2bc1d-266">まとめ</span><span class="sxs-lookup"><span data-stu-id="2bc1d-266">Conclusion</span></span>

<span data-ttu-id="2bc1d-267">これでカスタマイズしたボタンが完成しました。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-267">You have completed a customized button.</span></span> <span data-ttu-id="2bc1d-268">これを行うためにボタン テンプレートを使用しました。これは、アプリケーション内のすべてのボタンに適用されました。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-268">You did this using a button template that was applied to all buttons in the application.</span></span> <span data-ttu-id="2bc1d-269">テンプレート編集モードを終了して (次の図を参照) さらにボタンを作成すると、それらは既定のボタンではなく、カスタム ボタンのような外観と動作を持つことが確認できます。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-269">If you leave the template editing mode (see the following figure) and create more buttons, you will see that they look and behave like your custom button rather than like the default button.</span></span>

![カスタム ボタン テンプレート](./media/custom-button-blend-scopeup.gif)

![同じテンプレートを使用する複数のボタン](./media/custom-button-blend-createmultiplebuttons.png)

<span data-ttu-id="2bc1d-272">F5 キーを押してアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-272">Press F5 to run the application.</span></span> <span data-ttu-id="2bc1d-273">ボタンをクリックして、すべての動作が同じであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-273">Click the buttons and notice how they all behave the same.</span></span>

<span data-ttu-id="2bc1d-274">テンプレートをカスタマイズしている間に、**innerRectangle** の <xref:System.Windows.Shapes.Shape.Fill%2A> プロパティと **outerRectangle** の <xref:System.Windows.Shapes.Shape.Stroke%2A> プロパティをテンプレートの背景 ({TemplateBinding Background}) に設定したことを思い出してください。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-274">Remember that while you were customizing the template, you set the <xref:System.Windows.Shapes.Shape.Fill%2A> property of **innerRectangle** and the <xref:System.Windows.Shapes.Shape.Stroke%2A> property **outerRectangle** to the template background ({TemplateBinding Background}).</span></span> <span data-ttu-id="2bc1d-275">このため、個々のボタンの背景色を設定すると、設定した背景がそのそれぞれのプロパティに使用されます。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-275">Because of this, when you set the background color of the individual buttons, the background you set will be used for those respective properties.</span></span> <span data-ttu-id="2bc1d-276">今すぐ背景を変更してみてください。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-276">Try changing the backgrounds now.</span></span> <span data-ttu-id="2bc1d-277">次の図では、さまざまなグラデーションが使用されています。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-277">In the following figure, different gradients are used.</span></span> <span data-ttu-id="2bc1d-278">したがって、テンプレートはボタンのようなコントロールを全体的にカスタマイズする場合に便利ですが、テンプレートを使用したコントロールは互いに異なる外観に変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-278">Therefore, although a template is useful for overall customization of controls like button, controls with templates can still be modified to look different from each other.</span></span>

<span data-ttu-id="2bc1d-279">![外観が異なる、同じテンプレートを使用したボタン](./media/custom-button-blend-blendconclusion.jpg "custom_button_blend_BlendConclusion")</span><span class="sxs-lookup"><span data-stu-id="2bc1d-279">![Buttons with the same template that look diferent](./media/custom-button-blend-blendconclusion.jpg "custom_button_blend_BlendConclusion")</span></span>

<span data-ttu-id="2bc1d-280">結論として、ボタン テンプレートをカスタマイズするプロセスを通じて、Microsoft Expression Blend で次の操作を行う方法を学習しました。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-280">In conclusion, in the process of customizing a button template you have learned how to do the following in Microsoft Expression Blend:</span></span>

- <span data-ttu-id="2bc1d-281">コントロールの外観をカスタマイズする。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-281">Customize the look of a control.</span></span>

- <span data-ttu-id="2bc1d-282">プロパティ トリガーを設定する。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-282">Set property triggers.</span></span> <span data-ttu-id="2bc1d-283">プロパティ トリガーは、コントロールだけでなく、ほとんどのオブジェクトで使用できるため、非常に便利です。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-283">Property triggers are very useful because they can be used on most objects, not just controls.</span></span>

- <span data-ttu-id="2bc1d-284">イベント トリガーを設定する。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-284">Set event triggers.</span></span> <span data-ttu-id="2bc1d-285">イベント トリガーは、コントロールだけでなく、ほとんどのオブジェクトで使用できるため、非常に便利です。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-285">Event triggers are very useful because they can be used on most objects, not just controls.</span></span>

- <span data-ttu-id="2bc1d-286">アニメーションを作成する。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-286">Create animations.</span></span>

- <span data-ttu-id="2bc1d-287">その他: グラデーションの作成、BitmapEffects の追加、変換の使用、オブジェクトの基本プロパティの設定。</span><span class="sxs-lookup"><span data-stu-id="2bc1d-287">Miscellaneous: create gradients, add BitmapEffects, use transforms, and set basic properties of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="2bc1d-288">関連項目</span><span class="sxs-lookup"><span data-stu-id="2bc1d-288">See also</span></span>

- [<span data-ttu-id="2bc1d-289">XAML を使用したボタンの作成</span><span class="sxs-lookup"><span data-stu-id="2bc1d-289">Create a Button by Using XAML</span></span>](walkthrough-create-a-button-by-using-xaml.md)
- [<span data-ttu-id="2bc1d-290">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="2bc1d-290">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [<span data-ttu-id="2bc1d-291">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="2bc1d-291">Animation Overview</span></span>](../graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="2bc1d-292">純色およびグラデーションによる塗りつぶしの概要</span><span class="sxs-lookup"><span data-stu-id="2bc1d-292">Painting with Solid Colors and Gradients Overview</span></span>](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="2bc1d-293">ビットマップ効果の概要</span><span class="sxs-lookup"><span data-stu-id="2bc1d-293">Bitmap Effects Overview</span></span>](../graphics-multimedia/bitmap-effects-overview.md)
