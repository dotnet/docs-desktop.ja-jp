---
title: デザイン時にカスタムコントロールをデバッグする
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- debugging [Visual Studio], walkthroughs
- custom controls [Windows Forms], walkthroughs
- visual editors
- debugging [Visual Studio], Windows Forms
- custom controls [Windows Forms], debugging
- designers
- controls [Windows Forms], debugging
- walkthroughs [Windows Forms], debugging
- design-time debugging
ms.assetid: 1fd83ccd-3798-42fc-85a3-6cba99467387
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: d9e292a1219c24571bcb35db2fe357b0197c8812
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982723"
---
# <a name="walkthrough-debug-custom-windows-forms-controls-at-design-time"></a><span data-ttu-id="89378-102">チュートリアル: カスタム Windows フォーム コントロールのデザイン時のデバッグ</span><span class="sxs-lookup"><span data-stu-id="89378-102">Walkthrough: Debug Custom Windows Forms Controls at Design Time</span></span>

<span data-ttu-id="89378-103">カスタムコントロールを作成すると、多くの場合、デザイン時の動作をデバッグする必要があることがわかります。</span><span class="sxs-lookup"><span data-stu-id="89378-103">When you create a custom control, you will often find it necessary to debug its design-time behavior.</span></span> <span data-ttu-id="89378-104">これは、カスタムコントロールのカスタムデザイナーを作成する場合に特に当てはまります。</span><span class="sxs-lookup"><span data-stu-id="89378-104">This is especially true if you are authoring a custom designer for your custom control.</span></span> <span data-ttu-id="89378-105">詳細については、「 [チュートリアル: Visual Studio の Design-Time 機能を利用する Windows フォームコントロールの作成](creating-a-wf-control-design-time-features.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89378-105">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](creating-a-wf-control-design-time-features.md).</span></span>

<span data-ttu-id="89378-106">他の .NET Framework クラスをデバッグする場合と同様に、Visual Studio を使用してカスタムコントロールをデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="89378-106">You can debug your custom controls using Visual Studio, just as you would debug any other .NET Framework classes.</span></span> <span data-ttu-id="89378-107">違いは、カスタムコントロールのコードを実行している Visual Studio の別のインスタンスをデバッグすることです。</span><span class="sxs-lookup"><span data-stu-id="89378-107">The difference is that you will debug a separate instance of Visual Studio that is running your custom control's code.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="89378-108">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="89378-108">Create the project</span></span>

<span data-ttu-id="89378-109">最初にアプリケーションのプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="89378-109">The first step is to create the application project.</span></span> <span data-ttu-id="89378-110">このプロジェクトは、カスタムコントロールをホストするアプリケーションをビルドするために使用します。</span><span class="sxs-lookup"><span data-stu-id="89378-110">You will use this project to build the application that hosts the custom control.</span></span>

<span data-ttu-id="89378-111">Visual Studio で、Windows アプリケーションプロジェクトを作成し、デバッグの **例** として名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="89378-111">In Visual Studio, create a Windows Application project, and name it **DebuggingExample**.</span></span>

## <a name="create-the-control-library-project"></a><span data-ttu-id="89378-112">コントロールライブラリプロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="89378-112">Create the control library project</span></span>

1. <span data-ttu-id="89378-113">ソリューションに **Windows コントロールライブラリ** プロジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="89378-113">Add a **Windows Control Library** project to the solution.</span></span>

2. <span data-ttu-id="89378-114">DebugControlLibrary プロジェクトに新しい **UserControl** 項目を追加します。</span><span class="sxs-lookup"><span data-stu-id="89378-114">Add a new **UserControl** item to the DebugControlLibrary project.</span></span> <span data-ttu-id="89378-115">**Debugcontrol** という名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="89378-115">Name it **DebugControl**.</span></span>

3. <span data-ttu-id="89378-116">**ソリューションエクスプローラー** で、ベース名が UserControl1 のコードファイルを削除して、プロジェクトの既定のコントロールを削除します。</span><span class="sxs-lookup"><span data-stu-id="89378-116">In **Solution Explorer**, delete the project's default control by deleting the code file with a base name of UserControl1.</span></span>

4. <span data-ttu-id="89378-117">ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="89378-117">Build the solution.</span></span>

## <a name="checkpoint"></a><span data-ttu-id="89378-118">Checkpoint</span><span class="sxs-lookup"><span data-stu-id="89378-118">Checkpoint</span></span>

<span data-ttu-id="89378-119">この時点で、 **ツールボックス** にカスタムコントロールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="89378-119">At this point, you will be able to see your custom control in the **Toolbox**.</span></span>

<span data-ttu-id="89378-120">進行状況を確認するには、 **Debugcontrollibrary Components** という名前の新しいタブを探し、クリックして選択します。</span><span class="sxs-lookup"><span data-stu-id="89378-120">To check your progress, find the new tab called **DebugControlLibrary Components** and click to select it.</span></span> <span data-ttu-id="89378-121">開いたときに、コントロールが **Debugcontrol** として表示され、その横に既定のアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="89378-121">When it opens, you will see your control listed as **DebugControl** with the default icon beside it.</span></span>

## <a name="add-a-property-to-your-custom-control"></a><span data-ttu-id="89378-122">カスタムコントロールにプロパティを追加する</span><span class="sxs-lookup"><span data-stu-id="89378-122">Add a property to your custom control</span></span>

<span data-ttu-id="89378-123">カスタムコントロールのコードがデザイン時に実行されていることを示すために、プロパティを追加し、プロパティを実装するコードにブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="89378-123">To demonstrate that your custom control's code is running at design-time, you will add a property and set a breakpoint in the code that implements the property.</span></span>

1. <span data-ttu-id="89378-124">**コードエディター** で **debugcontrol** を開きます。</span><span class="sxs-lookup"><span data-stu-id="89378-124">Open **DebugControl** in the **Code Editor**.</span></span> <span data-ttu-id="89378-125">クラス定義に次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="89378-125">Add the following code to the class definition:</span></span>

    ```vb
    Private demoStringValue As String = Nothing
    <BrowsableAttribute(true)>
    Public Property DemoString() As String

        Get
            Return Me.demoStringValue
        End Get

        Set(ByVal value As String)
            Me.demoStringValue = value
        End Set

    End Property
    ```

    ```csharp
    private string demoStringValue = null;
    [Browsable(true)]
    public string DemoString
    {
        get
        {
            return this.demoStringValue;
        }
        set
        {
            demoStringValue = value;
        }
    }
    ```

2. <span data-ttu-id="89378-126">ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="89378-126">Build the solution.</span></span>

## <a name="add-your-custom-control-to-the-host-form"></a><span data-ttu-id="89378-127">カスタムコントロールをホストフォームに追加する</span><span class="sxs-lookup"><span data-stu-id="89378-127">Add your custom control to the host form</span></span>

<span data-ttu-id="89378-128">カスタムコントロールのデザイン時動作をデバッグするには、カスタムコントロールクラスのインスタンスをホストフォームに配置します。</span><span class="sxs-lookup"><span data-stu-id="89378-128">To debug the design-time behavior of your custom control, you will place an instance of the custom control class on a host form.</span></span>

1. <span data-ttu-id="89378-129">"デバッグの例" プロジェクトで、 **Windows フォームデザイナー** で Form1 を開きます。</span><span class="sxs-lookup"><span data-stu-id="89378-129">In the "DebuggingExample" project, open Form1 in the **Windows Forms Designer**.</span></span>

2. <span data-ttu-id="89378-130">[ **ツールボックス**] で [ **Debugcontrollibrary コンポーネント** ] タブを開き、 **debugcontrol** インスタンスをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="89378-130">In the **Toolbox**, open the **DebugControlLibrary Components** tab and drag a **DebugControl** instance onto the form.</span></span>

3. <span data-ttu-id="89378-131">`DemoString`[**プロパティ**] ウィンドウでカスタムプロパティを見つけます。</span><span class="sxs-lookup"><span data-stu-id="89378-131">Find the `DemoString` custom property in the **Properties** window.</span></span> <span data-ttu-id="89378-132">他のプロパティと同様に、値を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="89378-132">Note that you can change its value as you would any other property.</span></span> <span data-ttu-id="89378-133">また、プロパティを選択すると、プロパティ `DemoString` の説明文字列が [ **プロパティ** ] ウィンドウの下部に表示されることにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="89378-133">Also note that when the `DemoString` property is selected, the property's description string appears at the bottom of the **Properties** window.</span></span>

## <a name="set-up-the-project-for-design-time-debugging"></a><span data-ttu-id="89378-134">デザイン時デバッグ用にプロジェクトを設定する</span><span class="sxs-lookup"><span data-stu-id="89378-134">Set up the project for design-time debugging</span></span>

<span data-ttu-id="89378-135">カスタムコントロールのデザイン時動作をデバッグするには、カスタムコントロールのコードを実行している Visual Studio の別のインスタンスをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="89378-135">To debug your custom control's design-time behavior, you will debug a separate instance of Visual Studio that is running your custom control's code.</span></span>

1. <span data-ttu-id="89378-136">**ソリューションエクスプローラー** で **debugcontrollibrary** プロジェクトを右クリックし、[**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="89378-136">Right-click on the **DebugControlLibrary** project in the **Solution Explorer** and select **Properties**.</span></span>

2. <span data-ttu-id="89378-137">**Debugcontrollibrary** プロパティシートで、[**デバッグ**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="89378-137">In the **DebugControlLibrary** property sheet, select the **Debug** tab.</span></span>

     <span data-ttu-id="89378-138">[ **開始アクション** ] セクションで、[ **外部プログラムの開始**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="89378-138">In the **Start Action** section, select **Start external program**.</span></span> <span data-ttu-id="89378-139">Visual Studio の別のインスタンスをデバッグする場合は、[visual studio のプロパティウィンドウ] の省略記号ボタン ([...]) をクリックして、 ![ ](./media/visual-studio-ellipsis-button.png) VISUAL studio IDE を参照します。</span><span class="sxs-lookup"><span data-stu-id="89378-139">You will be debugging a separate instance of Visual Studio, so click the ellipsis (![The Ellipsis button (...) in the Properties window of Visual Studio](./media/visual-studio-ellipsis-button.png)) button to browse for the Visual Studio IDE.</span></span> <span data-ttu-id="89378-140">実行可能ファイルの名前は **devenv.exe** であり、を既定の場所にインストールした場合、そのパスは *% ProgramFiles (x86)% \ Microsoft Visual Studio\2019 \\ \<edition> \Common7\IDE* になります。</span><span class="sxs-lookup"><span data-stu-id="89378-140">The name of the executable file is **devenv.exe**, and if you installed to the default location, its path is *%ProgramFiles(x86)%\Microsoft Visual Studio\2019\\\<edition>\Common7\IDE*.</span></span>

3. <span data-ttu-id="89378-141">**[OK]** を選択してダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="89378-141">Select **OK** to close the dialog box.</span></span>

4. <span data-ttu-id="89378-142">**Debugcontrollibrary** プロジェクトを右クリックし、[**スタートアッププロジェクトに設定**] を選択して、このデバッグ構成を有効にします。</span><span class="sxs-lookup"><span data-stu-id="89378-142">Right-click the **DebugControlLibrary** project and select **Set as StartUp Project** to enable this debugging configuration.</span></span>

## <a name="debug-your-custom-control-at-design-time"></a><span data-ttu-id="89378-143">デザイン時にカスタムコントロールをデバッグする</span><span class="sxs-lookup"><span data-stu-id="89378-143">Debug your custom control at design time</span></span>

<span data-ttu-id="89378-144">これで、デザインモードで実行されるカスタムコントロールをデバッグする準備ができました。</span><span class="sxs-lookup"><span data-stu-id="89378-144">Now you are ready to debug your custom control as it runs in design mode.</span></span> <span data-ttu-id="89378-145">デバッグセッションを開始すると、Visual Studio の新しいインスタンスが作成され、それを使用して "デバッグの例" ソリューションが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="89378-145">When you start the debugging session, a new instance of Visual Studio will be created, and you will use it to load the "DebuggingExample" solution.</span></span> <span data-ttu-id="89378-146">**フォームデザイナー** で Form1 を開くと、カスタムコントロールのインスタンスが作成され、実行が開始されます。</span><span class="sxs-lookup"><span data-stu-id="89378-146">When you open Form1 in the **Forms Designer**, an instance of your custom control will be created and will start running.</span></span>

1. <span data-ttu-id="89378-147">**コードエディター** で **debugcontrol** ソースファイルを開き、プロパティのアクセサーにブレークポイントを設定し `Set` `DemoString` ます。</span><span class="sxs-lookup"><span data-stu-id="89378-147">Open the **DebugControl** source file in the **Code Editor** and place a breakpoint on the `Set` accessor of the `DemoString` property.</span></span>

2. <span data-ttu-id="89378-148">**F5** キーを押してデバッグセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="89378-148">Press **F5** to start the debugging session.</span></span> <span data-ttu-id="89378-149">Visual Studio の新しいインスタンスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="89378-149">A new instance of Visual Studio is created.</span></span> <span data-ttu-id="89378-150">インスタンスは、次の2つの方法で区別できます。</span><span class="sxs-lookup"><span data-stu-id="89378-150">You can distinguish between the instances in two ways:</span></span>

    - <span data-ttu-id="89378-151">デバッグインスタンスのタイトルバーで、という単語が **実行さ** れています。</span><span class="sxs-lookup"><span data-stu-id="89378-151">The debugging instance has the word **Running** in its title bar</span></span>

    - <span data-ttu-id="89378-152">デバッグインスタンスの **デバッグ** ツールバーに [**開始**] ボタンが無効になっている</span><span class="sxs-lookup"><span data-stu-id="89378-152">The debugging instance has the **Start** button on its **Debug** toolbar disabled</span></span>

   <span data-ttu-id="89378-153">ブレークポイントは、デバッグインスタンスで設定されます。</span><span class="sxs-lookup"><span data-stu-id="89378-153">Your breakpoint is set in the debugging instance.</span></span>

3. <span data-ttu-id="89378-154">Visual Studio の新しいインスタンスで、"デバッグの例" ソリューションを開きます。</span><span class="sxs-lookup"><span data-stu-id="89378-154">In the new instance of Visual Studio, open the "DebuggingExample" solution.</span></span> <span data-ttu-id="89378-155">[**ファイル**] メニューから [**最近使ったプロジェクト**] を選択すると、ソリューションを簡単に見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="89378-155">You can easily find the solution by selecting **Recent Projects** from the **File** menu.</span></span> <span data-ttu-id="89378-156">"デバッグ例 .sln" ソリューションファイルは、最近使用したファイルとして一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="89378-156">The "DebuggingExample.sln" solution file will be listed as the most recently used file.</span></span>

4. <span data-ttu-id="89378-157">**フォームデザイナー** で Form1 を開き、 **debugcontrol** コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="89378-157">Open Form1 in the **Forms Designer** and select the **DebugControl** control.</span></span>

5. <span data-ttu-id="89378-158">`DemoString` プロパティの値を変更します。</span><span class="sxs-lookup"><span data-stu-id="89378-158">Change the value of the `DemoString` property.</span></span> <span data-ttu-id="89378-159">変更をコミットすると、Visual Studio のデバッグインスタンスがフォーカスを取得し、ブレークポイントで実行が停止します。</span><span class="sxs-lookup"><span data-stu-id="89378-159">When you commit the change, the debugging instance of Visual Studio acquires focus and execution stops at your breakpoint.</span></span> <span data-ttu-id="89378-160">他のコードと同じように、プロパティアクセサーを1ステップずつ実行できます。</span><span class="sxs-lookup"><span data-stu-id="89378-160">You can single-step through the property accessor just as your would any other code.</span></span>

6. <span data-ttu-id="89378-161">デバッグを停止するには、Visual Studio のホストされたインスタンスを終了するか、デバッグインスタンスで [ **デバッグの停止** ] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="89378-161">To stop debugging, exit the hosted instance of Visual Studio or select the **Stop Debugging** button in the debugging instance.</span></span>

## <a name="next-steps"></a><span data-ttu-id="89378-162">次のステップ</span><span class="sxs-lookup"><span data-stu-id="89378-162">Next steps</span></span>

<span data-ttu-id="89378-163">デザイン時にカスタムコントロールをデバッグできるようになったので、Visual Studio IDE とのコントロールの相互作用を拡張する多くの可能性があります。</span><span class="sxs-lookup"><span data-stu-id="89378-163">Now that you can debug your custom controls at design time, there are many possibilities for expanding your control's interaction with the Visual Studio IDE.</span></span>

- <span data-ttu-id="89378-164">クラスのプロパティを使用して、 <xref:System.ComponentModel.Component.DesignMode%2A> <xref:System.ComponentModel.Component> デザイン時にのみ実行されるコードを記述できます。</span><span class="sxs-lookup"><span data-stu-id="89378-164">You can use the <xref:System.ComponentModel.Component.DesignMode%2A> property of the <xref:System.ComponentModel.Component> class to write code that will only execute at design time.</span></span> <span data-ttu-id="89378-165">詳細については、「<xref:System.ComponentModel.Component.DesignMode%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89378-165">For details, see <xref:System.ComponentModel.Component.DesignMode%2A>.</span></span>

- <span data-ttu-id="89378-166">コントロールのプロパティには、デザイナーとのカスタムコントロールの対話を操作するために適用できる属性がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="89378-166">There are several attributes you can apply to your control's properties to manipulate your custom control's interaction with the designer.</span></span> <span data-ttu-id="89378-167">これらの属性は、名前空間で見つけることができ <xref:System.ComponentModel?displayProperty=nameWithType> ます。</span><span class="sxs-lookup"><span data-stu-id="89378-167">You can find these attributes in the <xref:System.ComponentModel?displayProperty=nameWithType> namespace.</span></span>

- <span data-ttu-id="89378-168">カスタムコントロールのカスタムデザイナーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="89378-168">You can write a custom designer for your custom control.</span></span> <span data-ttu-id="89378-169">これにより、Visual Studio によって公開される拡張可能なデザイナーインフラストラクチャを使用して、デザインエクスペリエンスを完全に制御できます。</span><span class="sxs-lookup"><span data-stu-id="89378-169">This gives you complete control over the design experience using the extensible designer infrastructure exposed by Visual Studio.</span></span> <span data-ttu-id="89378-170">詳細については、「 [チュートリアル: Visual Studio の Design-Time 機能を利用する Windows フォームコントロールの作成](creating-a-wf-control-design-time-features.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89378-170">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](creating-a-wf-control-design-time-features.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="89378-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="89378-171">See also</span></span>

- [<span data-ttu-id="89378-172">チュートリアル: Visual Studio の Design-Time 機能を利用する Windows フォームコントロールの作成</span><span class="sxs-lookup"><span data-stu-id="89378-172">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)
