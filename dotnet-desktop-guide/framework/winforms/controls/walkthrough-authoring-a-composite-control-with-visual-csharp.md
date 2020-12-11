---
title: 'チュートリアル : Visual C# による複合コントロールの作成'
ms.date: 03/30/2017
dev_langs:
- CSharp
helpviewer_keywords:
- custom controls [C#]
- user controls [Windows Forms], creating with Visual C#
- UserControl class [Windows Forms], walkthroughs
- user controls [C#]
- custom controls [Windows Forms], creating
ms.assetid: f88481a8-c746-4a36-9479-374ce5f2e91f
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 3ad9aad026a1a6a1266845736d7651db77fd5d5c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982100"
---
# <a name="walkthrough-author-a-composite-control-with-c"></a><span data-ttu-id="f863d-102">チュートリアル: C を使用した複合コントロールの作成\#</span><span class="sxs-lookup"><span data-stu-id="f863d-102">Walkthrough: Author a Composite Control with C\#</span></span>

<span data-ttu-id="f863d-103">複合コントロールは、カスタム グラフィカル インターフェイスを作成し、再利用するための手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="f863d-103">Composite controls provide a means by which custom graphical interfaces can be created and reused.</span></span> <span data-ttu-id="f863d-104">複合コントロールは、基本的には視覚的に表示されるコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="f863d-104">A composite control is essentially a component with a visual representation.</span></span> <span data-ttu-id="f863d-105">そのため、複合コントロールは、1 つ以上の Windows フォーム コントロール、コンポーネント、または機能を拡張できるコード ブロックで構成されます。コード ブロックでは、ユーザー入力の検証、表示プロパティの変更、作成者が必要とする他のタスクの実行などによって機能を拡張します。</span><span class="sxs-lookup"><span data-stu-id="f863d-105">As such, it might consist of one or more Windows Forms controls, components, or blocks of code that can extend functionality by validating user input, modifying display properties, or performing other tasks required by the author.</span></span> <span data-ttu-id="f863d-106">複合コントロールは、他のコントロールと同様に Windows フォームに配置できます。</span><span class="sxs-lookup"><span data-stu-id="f863d-106">Composite controls can be placed on Windows Forms in the same manner as other controls.</span></span> <span data-ttu-id="f863d-107">このチュートリアルの前半では、`ctlClock` という単純な複合コントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="f863d-107">In the first part of this walkthrough, you create a simple composite control called `ctlClock`.</span></span> <span data-ttu-id="f863d-108">チュートリアルの後半では、継承によって `ctlClock` の機能を拡張します。</span><span class="sxs-lookup"><span data-stu-id="f863d-108">In the second part of the walkthrough, you extend the functionality of `ctlClock` through inheritance.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="f863d-109">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="f863d-109">Create the Project</span></span>

<span data-ttu-id="f863d-110">新しいプロジェクトを作成するときは、ルート名前空間、アセンブリ名、プロジェクト名を設定し、既定のコンポーネントが適切な名前空間に含まれるようにするために、プロジェクトの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="f863d-110">When you create a new project, you specify its name to set the root namespace, assembly name, and project name, and ensure that the default component will be in the correct namespace.</span></span>

### <a name="to-create-the-ctlclocklib-control-library-and-the-ctlclock-control"></a><span data-ttu-id="f863d-111">ctlClockLib コントロール ライブラリと ctlClock コントロールを作成するには</span><span class="sxs-lookup"><span data-stu-id="f863d-111">To create the ctlClockLib control library and the ctlClock control</span></span>

1. <span data-ttu-id="f863d-112">Visual Studio で、新しい **Windows フォームコントロールライブラリ** プロジェクトを作成し、 **ctlClockLib** という名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="f863d-112">In Visual Studio, create a new **Windows Forms Control Library** project, and name it **ctlClockLib**.</span></span>

     <span data-ttu-id="f863d-113">プロジェクト名 `ctlClockLib` は、既定でルート名前空間にも割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="f863d-113">The project name, `ctlClockLib`, is also assigned to the root namespace by default.</span></span> <span data-ttu-id="f863d-114">ルート名前空間は、アセンブリ内のコンポーネント名の修飾に使用されます。</span><span class="sxs-lookup"><span data-stu-id="f863d-114">The root namespace is used to qualify the names of components in the assembly.</span></span> <span data-ttu-id="f863d-115">たとえば、`ctlClock` という名前のコンポーネントが 2 つのアセンブリに含まれている場合、`ctlClockLib.ctlClock.` を使用して目的の `ctlClock` コンポーネントを指定できます。</span><span class="sxs-lookup"><span data-stu-id="f863d-115">For example, if two assemblies provide components named `ctlClock`, you can specify your `ctlClock` component using `ctlClockLib.ctlClock.`</span></span>

2. <span data-ttu-id="f863d-116">**ソリューションエクスプローラー** で、[ **UserControl1.cs**] を右クリックし、[**名前の変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f863d-116">In **Solution Explorer**, right-click **UserControl1.cs**, and then click **Rename**.</span></span> <span data-ttu-id="f863d-117">ファイル名を `ctlClock.cs` に変更します。</span><span class="sxs-lookup"><span data-stu-id="f863d-117">Change the file name to `ctlClock.cs`.</span></span> <span data-ttu-id="f863d-118">コード要素 "UserControl1" へのすべての参照の名前を変更するかどうかを確認するメッセージが表示されたら、[ **はい** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f863d-118">Click the **Yes** button when you are asked if you want to rename all references to the code element "UserControl1".</span></span>

    > [!NOTE]
    > <span data-ttu-id="f863d-119">既定では、複合コントロールは、 <xref:System.Windows.Forms.UserControl> システムによって提供されるクラスから継承されます。</span><span class="sxs-lookup"><span data-stu-id="f863d-119">By default, a composite control inherits from the <xref:System.Windows.Forms.UserControl> class provided by the system.</span></span> <span data-ttu-id="f863d-120">クラスは、 <xref:System.Windows.Forms.UserControl> すべての複合コントロールに必要な機能を提供し、標準のメソッドとプロパティを実装します。</span><span class="sxs-lookup"><span data-stu-id="f863d-120">The <xref:System.Windows.Forms.UserControl> class provides functionality required by all composite controls, and implements standard methods and properties.</span></span>

3. <span data-ttu-id="f863d-121">**[ファイル]** メニューの **[すべて保存]** をクリックして、プロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="f863d-121">On the **File** menu, click **Save All** to save the project.</span></span>

## <a name="add-windows-controls-and-components-to-the-composite-control"></a><span data-ttu-id="f863d-122">Windows コントロールとコンポーネントを複合コントロールに追加する</span><span class="sxs-lookup"><span data-stu-id="f863d-122">Add Windows Controls and Components to the Composite Control</span></span>

<span data-ttu-id="f863d-123">ビジュアル インターフェイスは、複合コントロールに不可欠な部分です。</span><span class="sxs-lookup"><span data-stu-id="f863d-123">A visual interface is an essential part of your composite control.</span></span> <span data-ttu-id="f863d-124">このビジュアル インターフェイスは、デザイナー画面に 1 つ以上の Windows コントロールを追加することによって実装されます。</span><span class="sxs-lookup"><span data-stu-id="f863d-124">This visual interface is implemented by the addition of one or more Windows controls to the designer surface.</span></span> <span data-ttu-id="f863d-125">次の例では、複合コントロールに Windows コントロールを組み込み、機能を実装するコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="f863d-125">In the following demonstration, you will incorporate Windows controls into your composite control and write code to implement functionality.</span></span>

### <a name="to-add-a-label-and-a-timer-to-your-composite-control"></a><span data-ttu-id="f863d-126">複合コントロールに Label と Timer を追加するには</span><span class="sxs-lookup"><span data-stu-id="f863d-126">To add a Label and a Timer to your composite control</span></span>

1. <span data-ttu-id="f863d-127">**ソリューションエクスプローラー** で、[ **ctlClock.cs**] を右クリックし、[**デザイナーの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f863d-127">In **Solution Explorer**, right-click **ctlClock.cs**, and then click **View Designer**.</span></span>

2. <span data-ttu-id="f863d-128">**ツールボックス** の **[コモン コントロール]** ノードを展開し、**[Label]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="f863d-128">In the **Toolbox**, expand the **Common Controls** node, and then double-click **Label**.</span></span>

     <span data-ttu-id="f863d-129"><xref:System.Windows.Forms.Label>という名前のコントロール `label1` がデザイナー画面上のコントロールに追加されます。</span><span class="sxs-lookup"><span data-stu-id="f863d-129">A <xref:System.Windows.Forms.Label> control named `label1` is added to your control on the designer surface.</span></span>

3. <span data-ttu-id="f863d-130">デザイナーで **[label1]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f863d-130">In the designer, click **label1**.</span></span> <span data-ttu-id="f863d-131">[プロパティ] ウィンドウで、次のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="f863d-131">In the Properties window, set the following properties.</span></span>

    |<span data-ttu-id="f863d-132">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f863d-132">Property</span></span>|<span data-ttu-id="f863d-133">変更後の値</span><span class="sxs-lookup"><span data-stu-id="f863d-133">Change to</span></span>|
    |--------------|---------------|
    |<span data-ttu-id="f863d-134">**名前**</span><span class="sxs-lookup"><span data-stu-id="f863d-134">**Name**</span></span>|`lblDisplay`|
    |<span data-ttu-id="f863d-135">**Text**</span><span class="sxs-lookup"><span data-stu-id="f863d-135">**Text**</span></span>|`(blank space)`|
    |<span data-ttu-id="f863d-136">**TextAlign**</span><span class="sxs-lookup"><span data-stu-id="f863d-136">**TextAlign**</span></span>|`MiddleCenter`|
    |<span data-ttu-id="f863d-137">**フォントのサイズ**</span><span class="sxs-lookup"><span data-stu-id="f863d-137">**Font.Size**</span></span>|`14`|

4. <span data-ttu-id="f863d-138">**ツールボックス** の **[コンポーネント]** ノードを展開し、**[Timer]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="f863d-138">In the **Toolbox**, expand the **Components** node, and then double-click **Timer**.</span></span>

     <span data-ttu-id="f863d-139">はコンポーネントであるため <xref:System.Windows.Forms.Timer> 、実行時に視覚的に表示されることはありません。</span><span class="sxs-lookup"><span data-stu-id="f863d-139">Because a <xref:System.Windows.Forms.Timer> is a component, it has no visual representation at run time.</span></span> <span data-ttu-id="f863d-140">そのため、コントロールと共にデザイナー画面に表示されるのではなく、**コンポーネント デザイナー** (デザイナー画面の下部にあるトレイ) に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f863d-140">Therefore, it does not appear with the controls on the designer surface, but rather in the **Component Designer** (a tray at the bottom of the designer surface).</span></span>

5. <span data-ttu-id="f863d-141">**コンポーネントデザイナー** で [ **timer1**] をクリックし、プロパティをに設定し、 <xref:System.Windows.Forms.Timer.Interval%2A> `1000` <xref:System.Windows.Forms.Timer.Enabled%2A> プロパティをに設定し `true` ます。</span><span class="sxs-lookup"><span data-stu-id="f863d-141">In the **Component Designer**, click **timer1**, and then set the <xref:System.Windows.Forms.Timer.Interval%2A> property to `1000` and the <xref:System.Windows.Forms.Timer.Enabled%2A> property to `true`.</span></span>

     <span data-ttu-id="f863d-142">プロパティは、 <xref:System.Windows.Forms.Timer.Interval%2A> コンポーネントがティックする頻度を制御し <xref:System.Windows.Forms.Timer> ます。</span><span class="sxs-lookup"><span data-stu-id="f863d-142">The <xref:System.Windows.Forms.Timer.Interval%2A> property controls the frequency with which the <xref:System.Windows.Forms.Timer> component ticks.</span></span> <span data-ttu-id="f863d-143">`timer1` が時を刻むたびに、`timer1_Tick` イベントのコードが実行されます。</span><span class="sxs-lookup"><span data-stu-id="f863d-143">Each time `timer1` ticks, it runs the code in the `timer1_Tick` event.</span></span> <span data-ttu-id="f863d-144">このプロパティは、タイマーの刻み間隔をミリ秒単位で表します。</span><span class="sxs-lookup"><span data-stu-id="f863d-144">The interval represents the number of milliseconds between ticks.</span></span>

6. <span data-ttu-id="f863d-145">**コンポーネント デザイナー** で **[timer1]** をダブルクリックして、`ctlClock` の `timer1_Tick` イベントに移動します。</span><span class="sxs-lookup"><span data-stu-id="f863d-145">In the **Component Designer**, double-click **timer1** to go to the `timer1_Tick` event for `ctlClock`.</span></span>

7. <span data-ttu-id="f863d-146">コードを次のコード サンプルのように変更します。</span><span class="sxs-lookup"><span data-stu-id="f863d-146">Modify the code so that it resembles the following code sample.</span></span> <span data-ttu-id="f863d-147">アクセス修飾子を `private` から `protected` に必ず変更してください。</span><span class="sxs-lookup"><span data-stu-id="f863d-147">Be sure to change the access modifier from `private` to `protected`.</span></span>

    ```csharp
    protected void timer1_Tick(object sender, System.EventArgs e)
    {
        // Causes the label to display the current time.
        lblDisplay.Text = DateTime.Now.ToLongTimeString();
    }
    ```

     <span data-ttu-id="f863d-148">このコードにより、現在の時刻が `lblDisplay` に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f863d-148">This code will cause the current time to be shown in `lblDisplay`.</span></span> <span data-ttu-id="f863d-149">`timer1` の間隔が `1000` に設定されているため、このイベントは 1000 ミリ秒ごとに発生します。したがって、現在の時刻が 1 秒ごとに更新されます。</span><span class="sxs-lookup"><span data-stu-id="f863d-149">Because the interval of `timer1` was set to `1000`, this event will occur every thousand milliseconds, thus updating the current time every second.</span></span>

8. <span data-ttu-id="f863d-150">`virtual` キーワードを使用して、メソッドをオーバーライド可能に変更します。</span><span class="sxs-lookup"><span data-stu-id="f863d-150">Modify the method to be overridable with the `virtual` keyword.</span></span> <span data-ttu-id="f863d-151">詳細については、後述の「複合コントロールの継承」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f863d-151">For more information, see the  "Inheriting from a User Control" section below.</span></span>

    ```csharp
    protected virtual void timer1_Tick(object sender, System.EventArgs e)
    ```

9. <span data-ttu-id="f863d-152">**[ファイル]** メニューの **[すべて保存]** をクリックして、プロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="f863d-152">On the **File** menu, click **Save All** to save the project.</span></span>

## <a name="add-properties-to-the-composite-control"></a><span data-ttu-id="f863d-153">複合コントロールにプロパティを追加する</span><span class="sxs-lookup"><span data-stu-id="f863d-153">Add Properties to the Composite Control</span></span>

<span data-ttu-id="f863d-154">時計コントロールは、 <xref:System.Windows.Forms.Label> <xref:System.Windows.Forms.Timer> それぞれ独自のプロパティのセットを持つコントロールとコンポーネントをカプセル化するようになりました。</span><span class="sxs-lookup"><span data-stu-id="f863d-154">Your clock control now encapsulates a <xref:System.Windows.Forms.Label> control and a <xref:System.Windows.Forms.Timer> component, each with its own set of inherent properties.</span></span> <span data-ttu-id="f863d-155">時計コントロールを今後使用するユーザーは、これらのコントロールの個々のプロパティにアクセスすることはできませんが、適切なコード ブロックを記述することで、カスタム プロパティを作成して公開できます。</span><span class="sxs-lookup"><span data-stu-id="f863d-155">While the individual properties of these controls will not be accessible to subsequent users of your control, you can create and expose custom properties by writing the appropriate blocks of code.</span></span> <span data-ttu-id="f863d-156">次の手順では、ユーザーが背景とテキストの色を変更できるようにするプロパティをコントロールに追加します。</span><span class="sxs-lookup"><span data-stu-id="f863d-156">In the following procedure, you will add properties to your control that enable the user to change the color of the background and text.</span></span>

### <a name="to-add-a-property-to-your-composite-control"></a><span data-ttu-id="f863d-157">複合コントロールにプロパティを追加するには</span><span class="sxs-lookup"><span data-stu-id="f863d-157">To add a property to your composite control</span></span>

1. <span data-ttu-id="f863d-158">**ソリューションエクスプローラー** で、[ **ctlClock.cs**] を右クリックし、[**コードの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f863d-158">In **Solution Explorer**, right-click **ctlClock.cs**, and then click **View Code**.</span></span>

     <span data-ttu-id="f863d-159">コントロールの **コード エディター** が開きます。</span><span class="sxs-lookup"><span data-stu-id="f863d-159">The **Code Editor** for your control opens.</span></span>

2. <span data-ttu-id="f863d-160">`public partial class ctlClock` ステートメントを探します。</span><span class="sxs-lookup"><span data-stu-id="f863d-160">Locate the `public partial class ctlClock` statement.</span></span> <span data-ttu-id="f863d-161">左中かっこ (`{)` の下に次のコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="f863d-161">Beneath the opening brace (`{)`, type the following code.</span></span>

    ```csharp
    private Color colFColor;
    private Color colBColor;
    ```

     <span data-ttu-id="f863d-162">これらのステートメントにより、作成するプロパティの値の格納に使用するプライベート変数が作成されます。</span><span class="sxs-lookup"><span data-stu-id="f863d-162">These statements create the private variables that you will use to store the values for the properties you are about to create.</span></span>

3. <span data-ttu-id="f863d-163">手順 2. の変数の宣言の下に、次のコードを入力するか貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="f863d-163">Enter or paste the following code beneath the variable declarations from step 2.</span></span>

    ```csharp
    // Declares the name and type of the property.
    public Color ClockBackColor
    {
        // Retrieves the value of the private variable colBColor.
        get
        {
            return colBColor;
        }
        // Stores the selected value in the private variable colBColor, and
        // updates the background color of the label control lblDisplay.
        set
        {
            colBColor = value;
            lblDisplay.BackColor = colBColor;
        }
    }
    // Provides a similar set of instructions for the foreground color.
    public Color ClockForeColor
    {
        get
        {
            return colFColor;
        }
        set
        {
            colFColor = value;
            lblDisplay.ForeColor = colFColor;
        }
    }
    ```

     <span data-ttu-id="f863d-164">上記のコードは、このコントロールを今後使用するユーザーが、`ClockForeColor` と `ClockBackColor` の 2 つのカスタム プロパティを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="f863d-164">The preceding code makes two custom properties, `ClockForeColor` and `ClockBackColor`, available to subsequent users of this control.</span></span> <span data-ttu-id="f863d-165">`get` ステートメントと `set` ステートメントは、プロパティ値を格納および取得できるようにし、そのプロパティに適した機能を実装するコードを提供します。</span><span class="sxs-lookup"><span data-stu-id="f863d-165">The `get` and `set` statements provide for storage and retrieval of the property value, as well as code to implement functionality appropriate to the property.</span></span>

4. <span data-ttu-id="f863d-166">**[ファイル]** メニューの **[すべて保存]** をクリックして、プロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="f863d-166">On the **File** menu, click **Save All** to save the project.</span></span>

## <a name="test-the-control"></a><span data-ttu-id="f863d-167">コントロールをテストする</span><span class="sxs-lookup"><span data-stu-id="f863d-167">Test the Control</span></span>

<span data-ttu-id="f863d-168">コントロールはスタンドアロン アプリケーションではないため、コンテナー内でホストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f863d-168">Controls are not stand-alone applications; they must be hosted in a container.</span></span> <span data-ttu-id="f863d-169">**UserControl Test Container** でコントロールの実行時の動作をテストし、プロパティを実行します。</span><span class="sxs-lookup"><span data-stu-id="f863d-169">Test your control's run-time behavior and exercise its properties with the **UserControl Test Container**.</span></span> <span data-ttu-id="f863d-170">詳細については、「 [方法: UserControl の Run-Time 動作をテストする](how-to-test-the-run-time-behavior-of-a-usercontrol.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f863d-170">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

### <a name="to-test-your-control"></a><span data-ttu-id="f863d-171">コントロールをテストするには</span><span class="sxs-lookup"><span data-stu-id="f863d-171">To test your control</span></span>

1. <span data-ttu-id="f863d-172">**F5** キーを押してプロジェクトをビルドし、 **UserControl テストコンテナー** でコントロールを実行します。</span><span class="sxs-lookup"><span data-stu-id="f863d-172">Press **F5** to build the project and run your control in the **UserControl Test Container**.</span></span>

2. <span data-ttu-id="f863d-173">テスト コンテナーのプロパティ グリッドで、`ClockBackColor` プロパティを探し、このプロパティを選択してカラー パレットを表示します。</span><span class="sxs-lookup"><span data-stu-id="f863d-173">In the test container's property grid, locate the `ClockBackColor` property, and then select the property to display the color palette.</span></span>

3. <span data-ttu-id="f863d-174">任意の色をクリックして選択します。</span><span class="sxs-lookup"><span data-stu-id="f863d-174">Choose a color by clicking it.</span></span>

   <span data-ttu-id="f863d-175">コントロールの背景色が選択した色に変更されます。</span><span class="sxs-lookup"><span data-stu-id="f863d-175">The background color of your control changes to the color you selected.</span></span>

4. <span data-ttu-id="f863d-176">同様のイベント シーケンスを使用して、`ClockForeColor` プロパティが予想どおりに機能していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f863d-176">Use a similar sequence of events to verify that the `ClockForeColor` property is functioning as expected.</span></span>

   <span data-ttu-id="f863d-177">このセクションとこれまでのセクションでは、コンポーネントと Windows コントロールをコードと組み合わせてパッケージ化し、複合コントロールの形でカスタム機能を提供する方法を説明しました。</span><span class="sxs-lookup"><span data-stu-id="f863d-177">In this section and the preceding sections, you have seen how components and Windows controls can be combined with code and packaging to provide custom functionality in the form of a composite control.</span></span> <span data-ttu-id="f863d-178">また、複合コントロールのプロパティを公開し、完了後にコントロールをテストする方法も説明しました。</span><span class="sxs-lookup"><span data-stu-id="f863d-178">You have learned to expose properties in your composite control, and how to test your control after it is complete.</span></span> <span data-ttu-id="f863d-179">次のセクションでは、`ctlClock` をベースとして使用して、継承された複合コントロールを作成する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="f863d-179">In the next section you will learn how to construct an inherited composite control using `ctlClock` as a base.</span></span>

## <a name="inherit-from-a-composite-control"></a><span data-ttu-id="f863d-180">複合コントロールから継承する</span><span class="sxs-lookup"><span data-stu-id="f863d-180">Inherit from a Composite Control</span></span>

<span data-ttu-id="f863d-181">これまでのセクションでは、Windows コントロール、コンポーネント、コードを組み合わせて、再利用可能な複合コントロールを作成する方法を説明しました。</span><span class="sxs-lookup"><span data-stu-id="f863d-181">In the previous sections, you learned how to combine Windows controls, components, and code into reusable composite controls.</span></span> <span data-ttu-id="f863d-182">作成した複合コントロールをベースとして使用して、他のコントロールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f863d-182">Your composite control can now be used as a base upon which other controls can be built.</span></span> <span data-ttu-id="f863d-183">基本クラスからクラスを派生するプロセスは "*継承*" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="f863d-183">The process of deriving a class from a base class is called *inheritance*.</span></span> <span data-ttu-id="f863d-184">このセクションでは、`ctlAlarmClock` という複合コントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="f863d-184">In this section, you will create a composite control called `ctlAlarmClock`.</span></span> <span data-ttu-id="f863d-185">このコントロールは、親コントロールである `ctlClock` から派生します。</span><span class="sxs-lookup"><span data-stu-id="f863d-185">This control will be derived from its parent control, `ctlClock`.</span></span> <span data-ttu-id="f863d-186">ここでは、親のメソッドをオーバーライドし、新しいメソッドとプロパティを追加して、`ctlClock` の機能を拡張する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="f863d-186">You will learn to extend the functionality of `ctlClock` by overriding parent methods and adding new methods and properties.</span></span>

<span data-ttu-id="f863d-187">継承されたコントロールを作成するには、まず、親から派生します。</span><span class="sxs-lookup"><span data-stu-id="f863d-187">The first step in creating an inherited control is to derive it from its parent.</span></span> <span data-ttu-id="f863d-188">これにより、親コントロールのプロパティ、メソッド、グラフィカル特性をすべて備えた新しいコントロールが作成されます。このコントロールをベースとして使用して、新しい機能や変更された機能を追加できます。</span><span class="sxs-lookup"><span data-stu-id="f863d-188">This action creates a new control that has all of the properties, methods, and graphical characteristics of the parent control, but can also act as a base for the addition of new or modified functionality.</span></span>

### <a name="to-create-the-inherited-control"></a><span data-ttu-id="f863d-189">継承されたコントロールを作成するには</span><span class="sxs-lookup"><span data-stu-id="f863d-189">To create the inherited control</span></span>

1. <span data-ttu-id="f863d-190">**ソリューションエクスプローラー** で、[ **ctlClockLib**] を右クリックして [**追加**] をポイントし、[**ユーザーコントロール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f863d-190">In **Solution Explorer**, right-click **ctlClockLib**, point to **Add**, and then click **User Control**.</span></span>

     <span data-ttu-id="f863d-191">**[新しい項目の追加]** ダイアログ ボックスが開きます。</span><span class="sxs-lookup"><span data-stu-id="f863d-191">The **Add New Item** dialog box opens.</span></span>

2. <span data-ttu-id="f863d-192">**[継承されたユーザー コントロール]** テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="f863d-192">Select the **Inherited User Control** template.</span></span>

3. <span data-ttu-id="f863d-193">**[名前]** ボックスに「`ctlAlarmClock.cs`」と入力し、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f863d-193">In the **Name** box, type `ctlAlarmClock.cs`, and then click **Add**.</span></span>

     <span data-ttu-id="f863d-194">**[継承ピッカー]** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f863d-194">The **Inheritance Picker** dialog box appears.</span></span>

4. <span data-ttu-id="f863d-195">**[コンポーネント名]** の **[ctlClock]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="f863d-195">Under **Component Name**, double-click **ctlClock**.</span></span>

5. <span data-ttu-id="f863d-196">**ソリューションエクスプローラー** で、現在のプロジェクトを参照します。</span><span class="sxs-lookup"><span data-stu-id="f863d-196">In **Solution Explorer**, browse through the current projects.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f863d-197">現在のプロジェクトに、**ctlAlarmClock.cs** というファイルが追加されています。</span><span class="sxs-lookup"><span data-stu-id="f863d-197">A file called **ctlAlarmClock.cs** has been added to the current project.</span></span>

### <a name="add-the-alarm-properties"></a><span data-ttu-id="f863d-198">アラームのプロパティを追加する</span><span class="sxs-lookup"><span data-stu-id="f863d-198">Add the Alarm Properties</span></span>

<span data-ttu-id="f863d-199">複合コントロールにプロパティを追加する場合と同様に、継承されたコントロールにプロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="f863d-199">Properties are added to an inherited control in the same way they are added to a composite control.</span></span> <span data-ttu-id="f863d-200">ここでは、プロパティ宣言の構文を使用して、コントロールに 2 つのプロパティを追加します。`AlarmTime` プロパティは、アラームを鳴らす日時の値を格納し、`AlarmSet` プロパティは、アラームが設定されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="f863d-200">You will now use the property declaration syntax to add two properties to your control: `AlarmTime`, which will store the value of the date and time the alarm is to go off, and `AlarmSet`, which will indicate whether the alarm is set.</span></span>

#### <a name="to-add-properties-to-your-composite-control"></a><span data-ttu-id="f863d-201">複合コントロールにプロパティを追加するには</span><span class="sxs-lookup"><span data-stu-id="f863d-201">To add properties to your composite control</span></span>

1. <span data-ttu-id="f863d-202">**ソリューションエクスプローラー** で、[ **ctlAlarmClock**] を右クリックし、[**コードの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f863d-202">In **Solution Explorer**, right-click **ctlAlarmClock**, and then click **View Code**.</span></span>

2. <span data-ttu-id="f863d-203">`public class` ステートメントを探します。</span><span class="sxs-lookup"><span data-stu-id="f863d-203">Locate the `public class` statement.</span></span> <span data-ttu-id="f863d-204">コントロールは `ctlClockLib.ctlClock` から継承されています。</span><span class="sxs-lookup"><span data-stu-id="f863d-204">Note that your control inherits from `ctlClockLib.ctlClock`.</span></span> <span data-ttu-id="f863d-205">左中かっこ (`{)` ステートメントの下に次のコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="f863d-205">Beneath the opening brace (`{)` statement, type the following code.</span></span>

    ```csharp
    private DateTime dteAlarmTime;
    private bool blnAlarmSet;
    // These properties will be declared as public to allow future
    // developers to access them.
    public DateTime AlarmTime
    {
        get
        {
            return dteAlarmTime;
        }
        set
        {
            dteAlarmTime = value;
        }
    }
    public bool AlarmSet
    {
        get
        {
            return blnAlarmSet;
        }
        set
        {
            blnAlarmSet = value;
        }
    }
    ```

### <a name="add-to-the-graphical-interface-of-the-control"></a><span data-ttu-id="f863d-206">コントロールのグラフィカルインターフェイスに追加します。</span><span class="sxs-lookup"><span data-stu-id="f863d-206">Add to the Graphical Interface of the Control</span></span>

<span data-ttu-id="f863d-207">継承されたコントロールには、継承元のコントロールと同じビジュアル インターフェイスがあります。</span><span class="sxs-lookup"><span data-stu-id="f863d-207">Your inherited control has a visual interface that is identical to the control it inherits from.</span></span> <span data-ttu-id="f863d-208">継承されたコントロールは親コントロールと同じ内在コントロールを持ちますが、内在コントロールのプロパティは、明確に公開されていない限り使用できません。</span><span class="sxs-lookup"><span data-stu-id="f863d-208">It possesses the same constituent controls as its parent control, but the properties of the constituent controls will not be available unless they were specifically exposed.</span></span> <span data-ttu-id="f863d-209">複合コントロールに追加する場合と同様に、継承された複合コントロールのグラフィカル インターフェイスに追加できます。</span><span class="sxs-lookup"><span data-stu-id="f863d-209">You may add to the graphical interface of an inherited composite control in the same manner as you would add to any composite control.</span></span> <span data-ttu-id="f863d-210">引き続き、アラーム時計のビジュアル インターフェイスに、アラームが鳴っているときに点滅するラベル コントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="f863d-210">To continue adding to your alarm clock's visual interface, you will add a label control that will flash when the alarm is sounding.</span></span>

#### <a name="to-add-the-label-control"></a><span data-ttu-id="f863d-211">ラベル コントロールを追加するには</span><span class="sxs-lookup"><span data-stu-id="f863d-211">To add the label control</span></span>

1. <span data-ttu-id="f863d-212">**ソリューションエクスプローラー** で、[ **ctlAlarmClock**] を右クリックし、[**デザイナーの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f863d-212">In **Solution Explorer**, right-click **ctlAlarmClock**, and then click **View Designer**.</span></span>

     <span data-ttu-id="f863d-213">メイン ウィンドウに、`ctlAlarmClock` のデザイナーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f863d-213">The designer for `ctlAlarmClock` opens in the main window.</span></span>

2. <span data-ttu-id="f863d-214">コントロールの表示部分をクリックし、[プロパティ] ウィンドウを表示します。</span><span class="sxs-lookup"><span data-stu-id="f863d-214">Click the display portion of the control, and view the Properties window.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f863d-215">すべてのプロパティが表示されていますが、淡色表示になっています。</span><span class="sxs-lookup"><span data-stu-id="f863d-215">While all the properties are displayed, they are dimmed.</span></span> <span data-ttu-id="f863d-216">これは、これらのプロパティが `lblDisplay` に対してネイティブであり、[プロパティ] ウィンドウで変更したりアクセスしたりすることはできないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="f863d-216">This indicates that these properties are native to `lblDisplay` and cannot be modified or accessed in the Properties window.</span></span> <span data-ttu-id="f863d-217">既定では、複合コントロールに含まれているコントロールは `private` であり、どのような方法でもプロパティにはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="f863d-217">By default, controls contained in a composite control are `private`, and their properties are not accessible by any means.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f863d-218">複合コントロールを今後使用するユーザーが、その内部のコントロールにアクセスできるようにする場合は、内部のコントロールを `public` または `protected` として宣言します。</span><span class="sxs-lookup"><span data-stu-id="f863d-218">If you want subsequent users of your composite control to have access to its internal controls, declare them as `public` or `protected`.</span></span> <span data-ttu-id="f863d-219">これにより、適切なコードを使用して、複合コントロールに含まれているコントロールのプロパティの設定や変更が可能になります。</span><span class="sxs-lookup"><span data-stu-id="f863d-219">This will allow you to set and modify properties of controls contained within your composite control by using the appropriate code.</span></span>

3. <span data-ttu-id="f863d-220"><xref:System.Windows.Forms.Label>複合コントロールにコントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="f863d-220">Add a <xref:System.Windows.Forms.Label> control to your composite control.</span></span>

4. <span data-ttu-id="f863d-221">マウスを使用して、 <xref:System.Windows.Forms.Label> コントロールを表示ボックスのすぐ下にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="f863d-221">Using the mouse, drag the <xref:System.Windows.Forms.Label> control immediately beneath the display box.</span></span> <span data-ttu-id="f863d-222">[プロパティ] ウィンドウで、次のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="f863d-222">In the Properties window, set the following properties.</span></span>

    |<span data-ttu-id="f863d-223">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f863d-223">Property</span></span>|<span data-ttu-id="f863d-224">設定</span><span class="sxs-lookup"><span data-stu-id="f863d-224">Setting</span></span>|
    |--------------|-------------|
    |<span data-ttu-id="f863d-225">**名前**</span><span class="sxs-lookup"><span data-stu-id="f863d-225">**Name**</span></span>|`lblAlarm`|
    |<span data-ttu-id="f863d-226">**Text**</span><span class="sxs-lookup"><span data-stu-id="f863d-226">**Text**</span></span>|<span data-ttu-id="f863d-227">**知ら!**</span><span class="sxs-lookup"><span data-stu-id="f863d-227">**Alarm!**</span></span>|
    |<span data-ttu-id="f863d-228">**TextAlign**</span><span class="sxs-lookup"><span data-stu-id="f863d-228">**TextAlign**</span></span>|`MiddleCenter`|
    |<span data-ttu-id="f863d-229">**[表示]**</span><span class="sxs-lookup"><span data-stu-id="f863d-229">**Visible**</span></span>|`false`|

### <a name="add-the-alarm-functionality"></a><span data-ttu-id="f863d-230">アラーム機能を追加する</span><span class="sxs-lookup"><span data-stu-id="f863d-230">Add the Alarm Functionality</span></span>

<span data-ttu-id="f863d-231">前の手順では、複合コントロールでアラーム機能を有効にするためのプロパティとコントロールを追加しました。</span><span class="sxs-lookup"><span data-stu-id="f863d-231">In the previous procedures, you added properties and a control that will enable alarm functionality in your composite control.</span></span> <span data-ttu-id="f863d-232">この手順では、現在の時刻をアラームの時刻と比較して、2 つの時刻が同じである場合にアラームを点滅させるコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="f863d-232">In this procedure, you will add code to compare the current time to the alarm time and, if they are the same, to flash an alarm.</span></span> <span data-ttu-id="f863d-233">`ctlClock` の `timer1_Tick` メソッドをオーバーライドし、コードを追加することで、`ctlClock` の固有の機能をすべて保持しながら、`ctlAlarmClock` の機能を拡張します。</span><span class="sxs-lookup"><span data-stu-id="f863d-233">By overriding the `timer1_Tick` method of `ctlClock` and adding additional code to it, you will extend the capability of `ctlAlarmClock` while retaining all of the inherent functionality of `ctlClock`.</span></span>

#### <a name="to-override-the-timer1_tick-method-of-ctlclock"></a><span data-ttu-id="f863d-234">ctlClock の timer1_Tick メソッドをオーバーライドするには</span><span class="sxs-lookup"><span data-stu-id="f863d-234">To override the timer1_Tick method of ctlClock</span></span>

1. <span data-ttu-id="f863d-235">**コード エディター** で、`private bool blnAlarmSet;` ステートメントを探します。</span><span class="sxs-lookup"><span data-stu-id="f863d-235">In the **Code Editor**, locate the `private bool blnAlarmSet;` statement.</span></span> <span data-ttu-id="f863d-236">このステートメントのすぐ下に、次のステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="f863d-236">Immediately beneath it, add the following statement.</span></span>

    ```csharp
    private bool blnColorTicker;
    ```

2. <span data-ttu-id="f863d-237">**コード エディター** で、クラスの末尾にある右中かっこ (`})` を探します。</span><span class="sxs-lookup"><span data-stu-id="f863d-237">In the **Code Editor**, locate the closing brace (`})` at the end of the class.</span></span> <span data-ttu-id="f863d-238">中かっこの直前に次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="f863d-238">Just before the brace, add the following code.</span></span>

    ```csharp
    protected override void timer1_Tick(object sender, System.EventArgs e)
    {
        // Calls the Timer1_Tick method of ctlClock.
        base.timer1_Tick(sender, e);
        // Checks to see if the alarm is set.
        if (AlarmSet == false)
            return;
        else
            // If the date, hour, and minute of the alarm time are the same as
            // the current time, flash an alarm.
        {
            if (AlarmTime.Date == DateTime.Now.Date && AlarmTime.Hour ==
                DateTime.Now.Hour && AlarmTime.Minute == DateTime.Now.Minute)
            {
                // Sets lblAlarmVisible to true, and changes the background color based on
                // the value of blnColorTicker. The background color of the label
                // will flash once per tick of the clock.
                lblAlarm.Visible = true;
                if (blnColorTicker == false)
                {
                    lblAlarm.BackColor = Color.Red;
                    blnColorTicker = true;
                }
                else
                {
                    lblAlarm.BackColor = Color.Blue;
                    blnColorTicker = false;
                }
            }
            else
            {
                // Once the alarm has sounded for a minute, the label is made
                // invisible again.
                lblAlarm.Visible = false;
            }
        }
    }
    ```

     <span data-ttu-id="f863d-239">このコードを追加すると、いくつかのタスクが実行されます。</span><span class="sxs-lookup"><span data-stu-id="f863d-239">The addition of this code accomplishes several tasks.</span></span> <span data-ttu-id="f863d-240">`override` ステートメントは、基本コントロールから継承されたメソッドの代わりに、このメソッドを使用するようコントロールに指示します。</span><span class="sxs-lookup"><span data-stu-id="f863d-240">The `override` statement directs the control to use this method in place of the method that was inherited from the base control.</span></span> <span data-ttu-id="f863d-241">このメソッドが呼び出されると、メソッドは `base.timer1_Tick` ステートメントを呼び出して、オーバーライドしたメソッドを呼び出します。これにより、元のコントロールに組み込まれたすべての機能がこのコントロールに継承されます。</span><span class="sxs-lookup"><span data-stu-id="f863d-241">When this method is called, it calls the method it overrides by invoking the `base.timer1_Tick` statement, ensuring that all of the functionality incorporated in the original control is reproduced in this control.</span></span> <span data-ttu-id="f863d-242">その後、メソッドは追加のコードを実行してアラーム機能を組み込みます。</span><span class="sxs-lookup"><span data-stu-id="f863d-242">It then runs additional code to incorporate the alarm functionality.</span></span> <span data-ttu-id="f863d-243">アラームが発生すると、点滅するラベル コントロールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f863d-243">A flashing label control will appear when the alarm occurs.</span></span>

     <span data-ttu-id="f863d-244">これで、アラーム時計コントロールはほぼ完成です。</span><span class="sxs-lookup"><span data-stu-id="f863d-244">Your alarm clock control is almost complete.</span></span> <span data-ttu-id="f863d-245">あとはアラームを止める方法を実装するだけです。</span><span class="sxs-lookup"><span data-stu-id="f863d-245">The only thing that remains is to implement a way to turn it off.</span></span> <span data-ttu-id="f863d-246">これを行うには、`lblAlarm_Click` メソッドにコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="f863d-246">To do this, you will add code to the `lblAlarm_Click` method.</span></span>

#### <a name="to-implement-the-shutoff-method"></a><span data-ttu-id="f863d-247">停止メソッドを実装するには</span><span class="sxs-lookup"><span data-stu-id="f863d-247">To implement the shutoff method</span></span>

1. <span data-ttu-id="f863d-248">**ソリューションエクスプローラー** で、[ **ctlAlarmClock.cs**] を右クリックし、[**デザイナーの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f863d-248">In **Solution Explorer**, right-click **ctlAlarmClock.cs**, and then click **View Designer**.</span></span>

     <span data-ttu-id="f863d-249">デザイナーが開きます。</span><span class="sxs-lookup"><span data-stu-id="f863d-249">The designer opens.</span></span>

2. <span data-ttu-id="f863d-250">コントロールにボタンを追加します。</span><span class="sxs-lookup"><span data-stu-id="f863d-250">Add a button to the control.</span></span> <span data-ttu-id="f863d-251">ボタンのプロパティを次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="f863d-251">Set the properties of the button as follows.</span></span>

    |<span data-ttu-id="f863d-252">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f863d-252">Property</span></span>|<span data-ttu-id="f863d-253">値</span><span class="sxs-lookup"><span data-stu-id="f863d-253">Value</span></span>|
    |--------------|-----------|
    |<span data-ttu-id="f863d-254">**名前**</span><span class="sxs-lookup"><span data-stu-id="f863d-254">**Name**</span></span>|`btnAlarmOff`|
    |<span data-ttu-id="f863d-255">**Text**</span><span class="sxs-lookup"><span data-stu-id="f863d-255">**Text**</span></span>|<span data-ttu-id="f863d-256">**Disable Alarm**</span><span class="sxs-lookup"><span data-stu-id="f863d-256">**Disable Alarm**</span></span>|

3. <span data-ttu-id="f863d-257">デザイナーで **[btnAlarmOff]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="f863d-257">In the designer, double-click **btnAlarmOff**.</span></span>

     <span data-ttu-id="f863d-258">**コード エディター** が開き、`private void btnAlarmOff_Click` 行が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f863d-258">The **Code Editor** opens to the `private void btnAlarmOff_Click` line.</span></span>

4. <span data-ttu-id="f863d-259">このメソッドを次のコードのように変更します。</span><span class="sxs-lookup"><span data-stu-id="f863d-259">Modify this method so that it resembles the following code.</span></span>

    ```csharp
    private void btnAlarmOff_Click(object sender, System.EventArgs e)
    {
        // Turns off the alarm.
        AlarmSet = false;
        // Hides the flashing label.
        lblAlarm.Visible = false;
    }
    ```

5. <span data-ttu-id="f863d-260">**[ファイル]** メニューの **[すべて保存]** をクリックして、プロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="f863d-260">On the **File** menu, click **Save All** to save the project.</span></span>

### <a name="use-the-inherited-control-on-a-form"></a><span data-ttu-id="f863d-261">フォームで継承されたコントロールを使用する</span><span class="sxs-lookup"><span data-stu-id="f863d-261">Use the Inherited Control on a Form</span></span>

<span data-ttu-id="f863d-262">継承されたコントロールは、基本クラスコントロールをテストしたときと同じ方法でテストでき `ctlClock` ます。 **F5** キーを押してプロジェクトをビルドし、 **UserControl テストコンテナー** でコントロールを実行します。</span><span class="sxs-lookup"><span data-stu-id="f863d-262">You can test your inherited control the same way you tested the base class control, `ctlClock`: Press **F5** to build the project and run your control in the **UserControl Test Container**.</span></span> <span data-ttu-id="f863d-263">詳細については、「 [方法: UserControl の Run-Time 動作をテストする](how-to-test-the-run-time-behavior-of-a-usercontrol.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f863d-263">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

<span data-ttu-id="f863d-264">コントロールを使用するには、フォーム上でコントロールをホストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f863d-264">To put your control to use, you will need to host it on a form.</span></span> <span data-ttu-id="f863d-265">標準の複合コントロールと同様に、継承された複合コントロールをスタンドアロンにすることはできないので、フォームまたは他のコンテナー内でホストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f863d-265">As with a standard composite control, an inherited composite control cannot stand alone and must be hosted in a form or other container.</span></span> <span data-ttu-id="f863d-266">`ctlAlarmClock` は機能が拡張されているため、テストするには追加のコードが必要となります。</span><span class="sxs-lookup"><span data-stu-id="f863d-266">Since `ctlAlarmClock` has a greater depth of functionality, additional code is required to test it.</span></span> <span data-ttu-id="f863d-267">次の手順では、`ctlAlarmClock` の機能をテストするための簡単なプログラムを作成します。</span><span class="sxs-lookup"><span data-stu-id="f863d-267">In this procedure, you will write a simple program to test the functionality of `ctlAlarmClock`.</span></span> <span data-ttu-id="f863d-268">`ctlAlarmClock` の `AlarmTime` プロパティを設定して表示するコードを記述し、固有の機能をテストします。</span><span class="sxs-lookup"><span data-stu-id="f863d-268">You will write code to set and display the `AlarmTime` property of `ctlAlarmClock`, and will test its inherent functions.</span></span>

#### <a name="to-build-and-add-your-control-to-a-test-form"></a><span data-ttu-id="f863d-269">コントロールをビルドしてテスト フォームに追加するには</span><span class="sxs-lookup"><span data-stu-id="f863d-269">To build and add your control to a test form</span></span>

1. <span data-ttu-id="f863d-270">**ソリューションエクスプローラー** で、[ **ctlClockLib**] を右クリックし、[**ビルド**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f863d-270">In **Solution Explorer**, right-click **ctlClockLib**, and then click **Build**.</span></span>

2. <span data-ttu-id="f863d-271">新しい **Windows フォームアプリケーション** プロジェクトをソリューションに追加し、 **Test** という名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="f863d-271">Add a new **Windows Forms Application** project to the solution, and name it **Test**.</span></span>

3. <span data-ttu-id="f863d-272">**ソリューションエクスプローラー** で、テストプロジェクトの [**参照設定**] ノードを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="f863d-272">In **Solution Explorer**, right-click the **References** node for your test project.</span></span> <span data-ttu-id="f863d-273">**[参照の追加]** をクリックして、**[参照の追加]** ダイアログ ボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="f863d-273">Click **Add Reference** to display the **Add Reference** dialog box.</span></span> <span data-ttu-id="f863d-274">**[プロジェクト]** というラベルのタブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f863d-274">Click the tab labeled **Projects**.</span></span> <span data-ttu-id="f863d-275">**[プロジェクト名]** に `ctlClockLib` プロジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f863d-275">Your `ctlClockLib` project will be listed under **Project Name**.</span></span> <span data-ttu-id="f863d-276">プロジェクトをダブルクリックして、テスト プロジェクトへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="f863d-276">Double-click the project to add the reference to the test project.</span></span>

4. <span data-ttu-id="f863d-277">**ソリューションエクスプローラー** で、[**テスト**] を右クリックし、[**ビルド**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f863d-277">In **Solution Explorer**, right-click **Test**, and then click **Build**.</span></span>

5. <span data-ttu-id="f863d-278">**ツールボックス** で、**[ctlClockLib コンポーネント]** ノードを展開します。</span><span class="sxs-lookup"><span data-stu-id="f863d-278">In the **Toolbox**, expand the **ctlClockLib Components** node.</span></span>

6. <span data-ttu-id="f863d-279">**[ctlAlarmClock]** をダブルクリックして、`ctlAlarmClock` のコピーをフォームに追加します。</span><span class="sxs-lookup"><span data-stu-id="f863d-279">Double-click **ctlAlarmClock** to add a copy of `ctlAlarmClock` to your form.</span></span>

7. <span data-ttu-id="f863d-280">**ツールボックス** で、[ **DateTimePicker** ] を見つけてダブルクリックし、フォームにコントロールを追加します。次に、[ラベル] を <xref:System.Windows.Forms.DateTimePicker> <xref:System.Windows.Forms.Label> ダブルクリックしてコントロールを追加します。 </span><span class="sxs-lookup"><span data-stu-id="f863d-280">In the **Toolbox**, locate and double-click **DateTimePicker** to add a <xref:System.Windows.Forms.DateTimePicker> control to your form, and then add a <xref:System.Windows.Forms.Label> control by double-clicking **Label**.</span></span>

8. <span data-ttu-id="f863d-281">マウスを使用して、各コントロールをフォーム上の使いやすい場所に配置します。</span><span class="sxs-lookup"><span data-stu-id="f863d-281">Use the mouse to position the controls in a convenient place on the form.</span></span>

9. <span data-ttu-id="f863d-282">これらのコントロールのプロパティを次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="f863d-282">Set the properties of these controls in the following manner.</span></span>

    |<span data-ttu-id="f863d-283">コントロール</span><span class="sxs-lookup"><span data-stu-id="f863d-283">Control</span></span>|<span data-ttu-id="f863d-284">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f863d-284">Property</span></span>|<span data-ttu-id="f863d-285">値</span><span class="sxs-lookup"><span data-stu-id="f863d-285">Value</span></span>|
    |-------------|--------------|-----------|
    |`label1`|<span data-ttu-id="f863d-286">**Text**</span><span class="sxs-lookup"><span data-stu-id="f863d-286">**Text**</span></span>|`(blank space)`|
    ||<span data-ttu-id="f863d-287">**名前**</span><span class="sxs-lookup"><span data-stu-id="f863d-287">**Name**</span></span>|`lblTest`|
    |`dateTimePicker1`|<span data-ttu-id="f863d-288">**名前**</span><span class="sxs-lookup"><span data-stu-id="f863d-288">**Name**</span></span>|`dtpTest`|
    ||<span data-ttu-id="f863d-289">**形式**</span><span class="sxs-lookup"><span data-stu-id="f863d-289">**Format**</span></span>|<xref:System.Windows.Forms.DateTimePickerFormat.Time>|

10. <span data-ttu-id="f863d-290">デザイナーで **[dtpTest]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="f863d-290">In the designer, double-click **dtpTest**.</span></span>

     <span data-ttu-id="f863d-291">**コード エディター** が開き、`private void dtpTest_ValueChanged` が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f863d-291">The **Code Editor** opens to `private void dtpTest_ValueChanged`.</span></span>

11. <span data-ttu-id="f863d-292">コードを次のように変更します。</span><span class="sxs-lookup"><span data-stu-id="f863d-292">Modify the code so that it resembles the following.</span></span>

    ```csharp
    private void dtpTest_ValueChanged(object sender, System.EventArgs e)
    {
        ctlAlarmClock1.AlarmTime = dtpTest.Value;
        ctlAlarmClock1.AlarmSet = true;
        lblTest.Text = "Alarm Time is " +
            ctlAlarmClock1.AlarmTime.ToShortTimeString();
    }
    ```

12. <span data-ttu-id="f863d-293">**ソリューションエクスプローラー** で、[**テスト**] を右クリックし、[**スタートアッププロジェクトに設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f863d-293">In **Solution Explorer**, right-click **Test**, and then click **Set as StartUp Project**.</span></span>

13. <span data-ttu-id="f863d-294">**[デバッグ]** メニューの **[デバッグの開始]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f863d-294">On the **Debug** menu, click **Start Debugging**.</span></span>

     <span data-ttu-id="f863d-295">テスト プログラムが起動します。</span><span class="sxs-lookup"><span data-stu-id="f863d-295">The test program starts.</span></span> <span data-ttu-id="f863d-296">コントロールで現在の時刻が更新され、 `ctlAlarmClock` コントロールに開始時刻が表示されていることに注意して <xref:System.Windows.Forms.DateTimePicker> ください。</span><span class="sxs-lookup"><span data-stu-id="f863d-296">Note that the current time is updated in the `ctlAlarmClock` control, and that the starting time is shown in the <xref:System.Windows.Forms.DateTimePicker> control.</span></span>

14. <span data-ttu-id="f863d-297">時間の分を表示するをクリックし <xref:System.Windows.Forms.DateTimePicker> ます。</span><span class="sxs-lookup"><span data-stu-id="f863d-297">Click the <xref:System.Windows.Forms.DateTimePicker> where the minutes of the hour are displayed.</span></span>

15. <span data-ttu-id="f863d-298">キーボードを使用して、`ctlAlarmClock` に表示されている現在の時刻の 1 分後の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="f863d-298">Using the keyboard, set a value for minutes that is one minute greater than the current time shown by `ctlAlarmClock`.</span></span>

     <span data-ttu-id="f863d-299">アラーム設定の時刻が `lblTest` に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f863d-299">The time for the alarm setting is shown in `lblTest`.</span></span> <span data-ttu-id="f863d-300">表示時刻がアラーム設定時刻になるまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="f863d-300">Wait for the displayed time to reach the alarm setting time.</span></span> <span data-ttu-id="f863d-301">表示時刻がアラーム設定時刻になると、`lblAlarm` が点滅します。</span><span class="sxs-lookup"><span data-stu-id="f863d-301">When the displayed time reaches the time to which the alarm is set, the `lblAlarm` will flash.</span></span>

16. <span data-ttu-id="f863d-302">`btnAlarmOff` をクリックしてアラームを止めます。</span><span class="sxs-lookup"><span data-stu-id="f863d-302">Turn off the alarm by clicking `btnAlarmOff`.</span></span> <span data-ttu-id="f863d-303">これでアラームをリセットできます。</span><span class="sxs-lookup"><span data-stu-id="f863d-303">You may now reset the alarm.</span></span>

<span data-ttu-id="f863d-304">この記事では、いくつかの重要な概念について説明しました。</span><span class="sxs-lookup"><span data-stu-id="f863d-304">This article has covered a number of key concepts.</span></span> <span data-ttu-id="f863d-305">コントロールとコンポーネントを複合コントロール コンテナーに組み込んで複合コントロールを作成する方法を説明しました。</span><span class="sxs-lookup"><span data-stu-id="f863d-305">You have learned to create a composite control by combining controls and components into a composite control container.</span></span> <span data-ttu-id="f863d-306">また、コントロールにプロパティを追加する方法と、カスタム機能を実装するコードを記述する方法も説明しました。</span><span class="sxs-lookup"><span data-stu-id="f863d-306">You have learned to add properties to your control, and to write code to implement custom functionality.</span></span> <span data-ttu-id="f863d-307">最後のセクションでは、継承によって特定の複合コントロールの機能を拡張する方法と、ホスト メソッドをオーバーライドすることでメソッドの機能を変更する方法を説明しました。</span><span class="sxs-lookup"><span data-stu-id="f863d-307">In the last section, you learned to extend the functionality of a given composite control through inheritance, and to alter the functionality of host methods by overriding those methods.</span></span>

## <a name="see-also"></a><span data-ttu-id="f863d-308">関連項目</span><span class="sxs-lookup"><span data-stu-id="f863d-308">See also</span></span>

- [<span data-ttu-id="f863d-309">さまざまなカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="f863d-309">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
- <span data-ttu-id="f863d-310">[方法: [ツールボックス アイテムの選択] ダイアログ ボックスにコントロールを表示する](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)</span><span class="sxs-lookup"><span data-stu-id="f863d-310">[How to: Display a Control in the Choose Toolbox Items Dialog Box](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)</span></span>
- [<span data-ttu-id="f863d-311">チュートリアル : Visual C# による Windows フォーム コントロールからの継承</span><span class="sxs-lookup"><span data-stu-id="f863d-311">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
