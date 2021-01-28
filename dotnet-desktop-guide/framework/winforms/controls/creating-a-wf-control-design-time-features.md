---
title: Visual Studio の Design-Time 機能を利用するコントロールを作成する
description: デザイン時機能を利用する Windows フォームでカスタムコントロールのカスタムデザイナーを作成する方法について説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms controls, creating
- design-time functionality [Windows Forms], Windows Forms
- DocumentDesigner class [Windows Forms]
- walkthroughs [Windows Forms], controls
ms.assetid: 6f487c59-cb38-4afa-ad2e-95edacb1d626
ms.openlocfilehash: b58a466e026d06d795134f3930f7259972cb39b9
ms.sourcegitcommit: 7f48b9ecf8a30db42c8ecea0dd4df577736631a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957462"
---
# <a name="walkthrough-create-a-control-that-takes-advantage-of-design-time-features"></a><span data-ttu-id="a6e24-103">チュートリアル: デザイン時機能を活用したコントロールの作成</span><span class="sxs-lookup"><span data-stu-id="a6e24-103">Walkthrough: Create a control that takes advantage of design-time features</span></span>

<span data-ttu-id="a6e24-104">カスタムコントロールのデザイン時のエクスペリエンスは、関連するカスタムデザイナーを作成することによって拡張できます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-104">The design-time experience for a custom control can be enhanced by authoring an associated custom designer.</span></span>

<span data-ttu-id="a6e24-105">この記事では、カスタムコントロールのカスタムデザイナーを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-105">This article illustrates how to create a custom designer for a custom control.</span></span> <span data-ttu-id="a6e24-106">`MarqueeControl`型とという名前の関連付けられたデザイナークラスを実装し `MarqueeControlRootDesigner` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-106">You'll implement a `MarqueeControl` type and an associated designer class called `MarqueeControlRootDesigner`.</span></span>

<span data-ttu-id="a6e24-107">この型は、アニメーション化さ `MarqueeControl` れたライトと点滅するテキストを含むシアターマーキーに似た表示を実装します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-107">The `MarqueeControl` type implements a display similar to a theater marquee with animated lights and flashing text.</span></span>

<span data-ttu-id="a6e24-108">このコントロールのデザイナーは、デザイン時のカスタムエクスペリエンスを提供するために、デザイン環境と対話します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-108">The designer for this control interacts with the design environment to provide a custom design-time experience.</span></span> <span data-ttu-id="a6e24-109">カスタムデザイナーを使用すると、アニメーション化さ `MarqueeControl` れたライトと、さまざまな組み合わせで点滅するテキストを使用して、カスタム実装を組み立てることができます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-109">With the custom designer, you can assemble a custom `MarqueeControl` implementation with animated lights and flashing text in many combinations.</span></span> <span data-ttu-id="a6e24-110">アセンブルされたコントロールは、他の Windows フォームコントロールと同様に、フォーム上で使用できます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-110">You can use the assembled control on a form like any other Windows Forms control.</span></span>

<span data-ttu-id="a6e24-111">このチュートリアルを終了すると、カスタムコントロールは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="a6e24-111">When you're finished with this walkthrough, your custom control will look something like the following:</span></span>

![テキストと [開始] および [停止] ボタンを示すマーキーを表示するアプリ。](./media/creating-a-wf-control-design-time-features/demo-marquee-control.gif)

<span data-ttu-id="a6e24-113">完全なコードリストについては、「 [方法: Design-Time の機能を利用する Windows フォームコントロールを作成](/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6e24-113">For the complete code listing, see [How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120)).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a6e24-114">前提条件</span><span class="sxs-lookup"><span data-stu-id="a6e24-114">Prerequisites</span></span>

<span data-ttu-id="a6e24-115">このチュートリアルを完了するには、Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="a6e24-115">In order to complete this walkthrough, you'll need Visual Studio.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="a6e24-116">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="a6e24-116">Create the project</span></span>

<span data-ttu-id="a6e24-117">最初にアプリケーションのプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-117">The first step is to create the application project.</span></span> <span data-ttu-id="a6e24-118">このプロジェクトは、カスタムコントロールをホストするアプリケーションをビルドするために使用します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-118">You will use this project to build the application that hosts the custom control.</span></span>

<span data-ttu-id="a6e24-119">Visual Studio で、新しい Windows フォームアプリケーションプロジェクトを作成し、 **MarqueeControlTest** という名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-119">In Visual Studio, create a new Windows Forms Application project, and name it **MarqueeControlTest**.</span></span>

## <a name="create-the-control-library-project"></a><span data-ttu-id="a6e24-120">コントロールライブラリプロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="a6e24-120">Create the control library project</span></span>

1. <span data-ttu-id="a6e24-121">ソリューションに Windows フォームコントロールライブラリプロジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-121">Add a Windows Forms Control Library project to the solution.</span></span> <span data-ttu-id="a6e24-122">プロジェクトに **MarqueeControlLibrary** という名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-122">Name the project **MarqueeControlLibrary**.</span></span>

2. <span data-ttu-id="a6e24-123">**ソリューションエクスプローラー** を使用して、選択した言語に応じて、"UserControl1.cs" または "UserControl1" という名前のソースファイルを削除して、プロジェクトの既定のコントロールを削除します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-123">Using **Solution Explorer**, delete the project's default control by deleting the source file named "UserControl1.cs" or "UserControl1.vb", depending on your language of choice.</span></span>

3. <span data-ttu-id="a6e24-124">新しい項目を <xref:System.Windows.Forms.UserControl> プロジェクトに追加 `MarqueeControlLibrary` します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-124">Add a new <xref:System.Windows.Forms.UserControl> item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="a6e24-125">新しいソースファイルに **MarqueeControl** のベース名を指定します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-125">Give the new source file a base name of **MarqueeControl**.</span></span>

4. <span data-ttu-id="a6e24-126">**ソリューションエクスプローラー** を使用して、プロジェクトに新しいフォルダーを作成し `MarqueeControlLibrary` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-126">Using **Solution Explorer**, create a new folder in the `MarqueeControlLibrary` project.</span></span>

5. <span data-ttu-id="a6e24-127">**Design** フォルダーを右クリックし、新しいクラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-127">Right-click the **Design** folder and add a new class.</span></span> <span data-ttu-id="a6e24-128">**MarqueeControlRootDesigner** という名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-128">Name it **MarqueeControlRootDesigner**.</span></span>

6. <span data-ttu-id="a6e24-129">System.string アセンブリの型を使用する必要があるため、この参照をプロジェクトに追加し `MarqueeControlLibrary` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-129">You'll need to use types from the System.Design assembly, so add this reference to the `MarqueeControlLibrary` project.</span></span>

## <a name="reference-the-custom-control-project"></a><span data-ttu-id="a6e24-130">カスタムコントロールプロジェクトを参照する</span><span class="sxs-lookup"><span data-stu-id="a6e24-130">Reference the Custom Control Project</span></span>

<span data-ttu-id="a6e24-131">`MarqueeControlTest`カスタムコントロールをテストするには、プロジェクトを使用します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-131">You will use the `MarqueeControlTest` project to test the custom control.</span></span> <span data-ttu-id="a6e24-132">アセンブリにプロジェクト参照を追加すると、テストプロジェクトはカスタムコントロールを認識するようになり `MarqueeControlLibrary` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-132">The test project will become aware of the custom control when you add a project reference to the `MarqueeControlLibrary` assembly.</span></span>

<span data-ttu-id="a6e24-133">プロジェクトで `MarqueeControlTest` 、アセンブリへのプロジェクト参照を追加し `MarqueeControlLibrary` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-133">In the `MarqueeControlTest` project, add a project reference to the `MarqueeControlLibrary` assembly.</span></span> <span data-ttu-id="a6e24-134">アセンブリを直接参照するのではなく、[**参照の追加**] ダイアログボックスの [**プロジェクト**] タブを使用するようにしてください `MarqueeControlLibrary` 。</span><span class="sxs-lookup"><span data-stu-id="a6e24-134">Be sure to use the **Projects** tab in the **Add Reference** dialog box instead of referencing the `MarqueeControlLibrary` assembly directly.</span></span>

## <a name="define-a-custom-control-and-its-custom-designer"></a><span data-ttu-id="a6e24-135">カスタムコントロールとそのカスタムデザイナーを定義する</span><span class="sxs-lookup"><span data-stu-id="a6e24-135">Define a Custom Control and Its Custom Designer</span></span>

<span data-ttu-id="a6e24-136">カスタムコントロールはクラスから派生 <xref:System.Windows.Forms.UserControl> します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-136">Your custom control will derive from the <xref:System.Windows.Forms.UserControl> class.</span></span> <span data-ttu-id="a6e24-137">これにより、コントロールに他のコントロールを含めることができます。また、コントロールには、既定の機能が多数用意されています。</span><span class="sxs-lookup"><span data-stu-id="a6e24-137">This allows your control to contain other controls, and it gives your control a great deal of default functionality.</span></span>

<span data-ttu-id="a6e24-138">カスタムコントロールには、関連付けられたカスタムデザイナーがあります。</span><span class="sxs-lookup"><span data-stu-id="a6e24-138">Your custom control will have an associated custom designer.</span></span> <span data-ttu-id="a6e24-139">これにより、カスタムコントロール専用にカスタマイズされた独自のデザインエクスペリエンスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-139">This allows you to create a unique design experience tailored specifically for your custom control.</span></span>

<span data-ttu-id="a6e24-140">コントロールをデザイナーに関連付けるには、クラスを使用し <xref:System.ComponentModel.DesignerAttribute> ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-140">You associate the control with its designer by using the <xref:System.ComponentModel.DesignerAttribute> class.</span></span> <span data-ttu-id="a6e24-141">カスタムコントロールのデザイン時動作全体を開発しているため、カスタムデザイナーはインターフェイスを実装し <xref:System.ComponentModel.Design.IRootDesigner> ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-141">Because you are developing the entire design-time behavior of your custom control, the custom designer will implement the <xref:System.ComponentModel.Design.IRootDesigner> interface.</span></span>

### <a name="to-define-a-custom-control-and-its-custom-designer"></a><span data-ttu-id="a6e24-142">カスタムコントロールとそのカスタムデザイナーを定義するには</span><span class="sxs-lookup"><span data-stu-id="a6e24-142">To define a custom control and its custom designer</span></span>

1. <span data-ttu-id="a6e24-143">`MarqueeControl`**コードエディター** でソースファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-143">Open the `MarqueeControl` source file in the **Code Editor**.</span></span> <span data-ttu-id="a6e24-144">ファイルの先頭に、次の名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="a6e24-144">At the top of the file, import the following namespaces:</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#220](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#220)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#220](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#220)]

2. <span data-ttu-id="a6e24-145">を <xref:System.ComponentModel.DesignerAttribute> クラス宣言に追加し `MarqueeControl` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-145">Add the <xref:System.ComponentModel.DesignerAttribute> to the `MarqueeControl` class declaration.</span></span> <span data-ttu-id="a6e24-146">これにより、カスタムコントロールがデザイナーに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-146">This associates the custom control with its designer.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#240](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#240)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#240](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#240)]

3. <span data-ttu-id="a6e24-147">`MarqueeControlRootDesigner`**コードエディター** でソースファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-147">Open the `MarqueeControlRootDesigner` source file in the **Code Editor**.</span></span> <span data-ttu-id="a6e24-148">ファイルの先頭に、次の名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="a6e24-148">At the top of the file, import the following namespaces:</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#520](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#520)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#520](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#520)]

4. <span data-ttu-id="a6e24-149">`MarqueeControlRootDesigner`クラスを継承するようにの宣言を変更し <xref:System.Windows.Forms.Design.DocumentDesigner> ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-149">Change the declaration of `MarqueeControlRootDesigner` to inherit from the <xref:System.Windows.Forms.Design.DocumentDesigner> class.</span></span> <span data-ttu-id="a6e24-150">を適用して、 <xref:System.ComponentModel.ToolboxItemFilterAttribute> デザイナーと **ツールボックス** の対話を指定します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-150">Apply the <xref:System.ComponentModel.ToolboxItemFilterAttribute> to specify the designer interaction with the **Toolbox**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a6e24-151">クラスの定義は、 `MarqueeControlRootDesigner` MarqueeControlLibrary という名前空間で囲まれています。</span><span class="sxs-lookup"><span data-stu-id="a6e24-151">The definition for the `MarqueeControlRootDesigner` class has been enclosed in a namespace called MarqueeControlLibrary.Design.</span></span> <span data-ttu-id="a6e24-152">この宣言により、デザイン関連の型用に予約された特殊な名前空間にデザイナーが配置されます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-152">This declaration places the designer in a special namespace reserved for design-related types.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#530](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#530)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#530](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#530)]

5. <span data-ttu-id="a6e24-153">クラスのコンストラクターを定義し `MarqueeControlRootDesigner` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-153">Define the constructor for the `MarqueeControlRootDesigner` class.</span></span> <span data-ttu-id="a6e24-154"><xref:System.Diagnostics.Trace.WriteLine%2A>コンストラクター本体にステートメントを挿入します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-154">Insert a <xref:System.Diagnostics.Trace.WriteLine%2A> statement in the constructor body.</span></span> <span data-ttu-id="a6e24-155">これはデバッグに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-155">This will be useful for debugging.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#540](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#540)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#540](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#540)]

## <a name="create-an-instance-of-your-custom-control"></a><span data-ttu-id="a6e24-156">カスタムコントロールのインスタンスを作成する</span><span class="sxs-lookup"><span data-stu-id="a6e24-156">Create an instance of your custom control</span></span>

1. <span data-ttu-id="a6e24-157">新しい項目を <xref:System.Windows.Forms.UserControl> プロジェクトに追加 `MarqueeControlTest` します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-157">Add a new <xref:System.Windows.Forms.UserControl> item to the `MarqueeControlTest` project.</span></span> <span data-ttu-id="a6e24-158">新しいソースファイルに **DemoMarqueeControl** のベース名を指定します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-158">Give the new source file a base name of **DemoMarqueeControl**.</span></span>

2. <span data-ttu-id="a6e24-159">`DemoMarqueeControl`**コードエディター** でファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-159">Open the `DemoMarqueeControl` file in the **Code Editor**.</span></span> <span data-ttu-id="a6e24-160">ファイルの先頭に、名前空間をインポートし `MarqueeControlLibrary` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-160">At the top of the file, import the `MarqueeControlLibrary` namespace:</span></span>

   ```vb
   Imports MarqueeControlLibrary
   ```

   ```csharp
   using MarqueeControlLibrary;
   ```

3. <span data-ttu-id="a6e24-161">`DemoMarqueeControl`クラスを継承するようにの宣言を変更し `MarqueeControl` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-161">Change the declaration of `DemoMarqueeControl` to inherit from the `MarqueeControl` class.</span></span>

4. <span data-ttu-id="a6e24-162">プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="a6e24-162">Build the project.</span></span>

5. <span data-ttu-id="a6e24-163">Windows フォームデザイナーで Form1 を開きます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-163">Open Form1 in the Windows Forms Designer.</span></span>

6. <span data-ttu-id="a6e24-164">**ツールボックス** の [ **MarqueeControlTest Components** ] タブを見つけて開きます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-164">Find the **MarqueeControlTest Components** tab in the **Toolbox** and open it.</span></span> <span data-ttu-id="a6e24-165">`DemoMarqueeControl`**ツールボックス** からフォームにをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="a6e24-165">Drag a `DemoMarqueeControl` from the **Toolbox** onto your form.</span></span>

7. <span data-ttu-id="a6e24-166">プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="a6e24-166">Build the project.</span></span>

## <a name="set-up-the-project-for-design-time-debugging"></a><span data-ttu-id="a6e24-167">Design-Time デバッグ用にプロジェクトを設定する</span><span class="sxs-lookup"><span data-stu-id="a6e24-167">Set Up the Project for Design-Time Debugging</span></span>

<span data-ttu-id="a6e24-168">カスタムデザイン時のエクスペリエンスを開発している場合は、コントロールとコンポーネントをデバッグする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6e24-168">When you're developing a custom design-time experience, it will be necessary to debug your controls and components.</span></span> <span data-ttu-id="a6e24-169">デザイン時にデバッグを許可するようにプロジェクトを設定する簡単な方法があります。</span><span class="sxs-lookup"><span data-stu-id="a6e24-169">There is a simple way to set up your project to allow debugging at design time.</span></span> <span data-ttu-id="a6e24-170">詳細については、「 [チュートリアル: デザイン時のカスタム Windows フォームコントロールのデバッグ](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6e24-170">For more information, see [Walkthrough: Debugging Custom Windows Forms Controls at Design Time](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).</span></span>

1. <span data-ttu-id="a6e24-171">プロジェクトを右クリック `MarqueeControlLibrary` し、[ **プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-171">Right-click the `MarqueeControlLibrary` project and select **Properties**.</span></span>

2. <span data-ttu-id="a6e24-172">[ **MarqueeControlLibrary プロパティページ** ] ダイアログボックスで、[ **デバッグ** ] ページを選択します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-172">In the **MarqueeControlLibrary Property Pages** dialog box, select the **Debug** page.</span></span>

3. <span data-ttu-id="a6e24-173">[ **開始アクション** ] セクションで、[ **外部プログラムの開始**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-173">In the **Start Action** section, select **Start External Program**.</span></span> <span data-ttu-id="a6e24-174">Visual Studio の別のインスタンスをデバッグする場合は、[visual studio のプロパティウィンドウ] の省略記号ボタン ([...]) をクリックして、 ![ ](./media/visual-studio-ellipsis-button.png) VISUAL studio IDE を参照します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-174">You will be debugging a separate instance of Visual Studio, so click the ellipsis (![The Ellipsis button (...) in the Properties window of Visual Studio](./media/visual-studio-ellipsis-button.png)) button to browse for the Visual Studio IDE.</span></span> <span data-ttu-id="a6e24-175">実行可能ファイルの名前は devenv.exe であり、を既定の場所にインストールした場合、そのパスは *% ProgramFiles (x86)% \ Microsoft Visual Studio\2019 \\ \<edition>\Common7\IDE\devenv.exe* になります。</span><span class="sxs-lookup"><span data-stu-id="a6e24-175">The name of the executable file is devenv.exe, and if you installed to the default location, its path is *%ProgramFiles(x86)%\Microsoft Visual Studio\2019\\\<edition>\Common7\IDE\devenv.exe*.</span></span>

4. <span data-ttu-id="a6e24-176">**[OK]** を選択してダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-176">Select **OK** to close the dialog box.</span></span>

5. <span data-ttu-id="a6e24-177">MarqueeControlLibrary プロジェクトを右クリックし、[ **スタートアッププロジェクトに設定** ] を選択して、このデバッグ構成を有効にします。</span><span class="sxs-lookup"><span data-stu-id="a6e24-177">Right-click the MarqueeControlLibrary project and select **Set as StartUp Project** to enable this debugging configuration.</span></span>

## <a name="checkpoint"></a><span data-ttu-id="a6e24-178">Checkpoint</span><span class="sxs-lookup"><span data-stu-id="a6e24-178">Checkpoint</span></span>

<span data-ttu-id="a6e24-179">これで、カスタムコントロールのデザイン時動作をデバッグする準備ができました。</span><span class="sxs-lookup"><span data-stu-id="a6e24-179">You are now ready to debug the design-time behavior of your custom control.</span></span> <span data-ttu-id="a6e24-180">デバッグ環境が正しく設定されていることを確認したら、カスタムコントロールとカスタムデザイナーの関連付けをテストします。</span><span class="sxs-lookup"><span data-stu-id="a6e24-180">Once you've determined that the debugging environment is set up correctly, you'll test the association between the custom control and the custom designer.</span></span>

### <a name="to-test-the-debugging-environment-and-the-designer-association"></a><span data-ttu-id="a6e24-181">デバッグ環境とデザイナーの関連付けをテストするには</span><span class="sxs-lookup"><span data-stu-id="a6e24-181">To test the debugging environment and the designer association</span></span>

1. <span data-ttu-id="a6e24-182">**コードエディター** で MarqueeControlRootDesigner ソースファイルを開き、ステートメントにブレークポイントを設定し <xref:System.Diagnostics.Trace.WriteLine%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-182">Open the MarqueeControlRootDesigner source file in the **Code Editor** and place a breakpoint on the <xref:System.Diagnostics.Trace.WriteLine%2A> statement.</span></span>

2. <span data-ttu-id="a6e24-183">**F5** キーを押してデバッグセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-183">Press **F5** to start the debugging session.</span></span>

   <span data-ttu-id="a6e24-184">Visual Studio の新しいインスタンスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-184">A new instance of Visual Studio is created.</span></span>

3. <span data-ttu-id="a6e24-185">Visual Studio の新しいインスタンスで、MarqueeControlTest ソリューションを開きます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-185">In the new instance of Visual Studio, open the MarqueeControlTest solution.</span></span> <span data-ttu-id="a6e24-186">[**ファイル**] メニューから [**最近使ったプロジェクト**] を選択すると、ソリューションを簡単に見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-186">You can easily find the solution by selecting **Recent Projects** from the **File** menu.</span></span> <span data-ttu-id="a6e24-187">MarqueeControlTest ソリューションファイルは、最近使用したファイルとして一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-187">The MarqueeControlTest.sln solution file will be listed as the most recently used file.</span></span>

4. <span data-ttu-id="a6e24-188">`DemoMarqueeControl`デザイナーでを開きます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-188">Open the `DemoMarqueeControl` in the designer.</span></span>

   <span data-ttu-id="a6e24-189">Visual Studio のデバッグインスタンスによってフォーカスが取得され、ブレークポイントで実行が停止します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-189">The debugging instance of Visual Studio obtains focus and execution stops at your breakpoint.</span></span> <span data-ttu-id="a6e24-190">**F5** キーを押してデバッグセッションを続行します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-190">Press **F5** to continue the debugging session.</span></span>

<span data-ttu-id="a6e24-191">この時点で、カスタムコントロールとそれに関連付けられているカスタムデザイナーを開発およびデバッグするために、すべてが準備されています。</span><span class="sxs-lookup"><span data-stu-id="a6e24-191">At this point, everything is in place for you to develop and debug your custom control and its associated custom designer.</span></span> <span data-ttu-id="a6e24-192">この記事の残りの部分では、コントロールとデザイナーの機能を実装する方法の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-192">The remainder of this article concentrates on the details of implementing features of the control and the designer.</span></span>

## <a name="implement-the-custom-control"></a><span data-ttu-id="a6e24-193">カスタムコントロールを実装する</span><span class="sxs-lookup"><span data-stu-id="a6e24-193">Implement the Custom Control</span></span>

<span data-ttu-id="a6e24-194">は、 `MarqueeControl` <xref:System.Windows.Forms.UserControl> カスタマイズが少ししかないです。</span><span class="sxs-lookup"><span data-stu-id="a6e24-194">The `MarqueeControl` is a <xref:System.Windows.Forms.UserControl> with a little bit of customization.</span></span> <span data-ttu-id="a6e24-195">ここでは、2つのメソッドを公開しています。は `Start` 、マーキーアニメーションを開始し、はアニメーションを停止します。 `Stop`</span><span class="sxs-lookup"><span data-stu-id="a6e24-195">It exposes two methods: `Start`, which starts the marquee animation, and `Stop`, which stops the animation.</span></span> <span data-ttu-id="a6e24-196">には、インターフェイスを実装する子コントロールが含まれているため、それぞれの子コントロールを列挙し、を `MarqueeControl` `IMarqueeWidget` `Start` `Stop` `StartMarquee` `StopMarquee` 実装する各子コントロールで、それぞれのメソッドとメソッドをそれぞれ呼び出し `IMarqueeWidget` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-196">Because the `MarqueeControl` contains child controls that implement the `IMarqueeWidget` interface, `Start` and `Stop` enumerate each child control and call the `StartMarquee` and `StopMarquee` methods, respectively, on each child control that implements `IMarqueeWidget`.</span></span>

<span data-ttu-id="a6e24-197">`MarqueeBorder`コントロールとコントロールの外観 `MarqueeText` は、レイアウトに依存しているため、 `MarqueeControl` <xref:System.Windows.Forms.Control.OnLayout%2A> メソッドをオーバーライドし、 <xref:System.Windows.Forms.Control.PerformLayout%2A> この型の子コントロールに対してを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-197">The appearance of the `MarqueeBorder` and `MarqueeText` controls is dependent on the layout, so `MarqueeControl` overrides the <xref:System.Windows.Forms.Control.OnLayout%2A> method and calls <xref:System.Windows.Forms.Control.PerformLayout%2A> on child controls of this type.</span></span>

<span data-ttu-id="a6e24-198">これはカスタマイズの範囲です `MarqueeControl` 。</span><span class="sxs-lookup"><span data-stu-id="a6e24-198">This is the extent of the `MarqueeControl` customizations.</span></span> <span data-ttu-id="a6e24-199">実行時の機能はコントロールとコントロールによって実装され、 `MarqueeBorder` `MarqueeText` デザイン時の機能はクラスおよびクラスによって実装され `MarqueeBorderDesigner` `MarqueeControlRootDesigner` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-199">The run-time features are implemented by the `MarqueeBorder` and `MarqueeText` controls, and the design-time features are implemented by the `MarqueeBorderDesigner` and `MarqueeControlRootDesigner` classes.</span></span>

### <a name="to-implement-your-custom-control"></a><span data-ttu-id="a6e24-200">カスタムコントロールを実装するには</span><span class="sxs-lookup"><span data-stu-id="a6e24-200">To implement your custom control</span></span>

1. <span data-ttu-id="a6e24-201">`MarqueeControl`**コードエディター** でソースファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-201">Open the `MarqueeControl` source file in the **Code Editor**.</span></span> <span data-ttu-id="a6e24-202">`Start`メソッドとメソッドを実装し `Stop` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-202">Implement the `Start` and `Stop` methods.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#260](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#260)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#260](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#260)]

2. <span data-ttu-id="a6e24-203"><xref:System.Windows.Forms.Control.OnLayout%2A> メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="a6e24-203">Override the <xref:System.Windows.Forms.Control.OnLayout%2A> method.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#270](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#270)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#270](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#270)]

## <a name="create-a-child-control-for-your-custom-control"></a><span data-ttu-id="a6e24-204">カスタムコントロールの子コントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="a6e24-204">Create a Child Control for Your Custom Control</span></span>

<span data-ttu-id="a6e24-205">は、 `MarqueeControl` `MarqueeBorder` コントロールとコントロールという2種類の子コントロールをホストします `MarqueeText` 。</span><span class="sxs-lookup"><span data-stu-id="a6e24-205">The `MarqueeControl` will host two kinds of child control: the `MarqueeBorder` control and the `MarqueeText` control.</span></span>

- <span data-ttu-id="a6e24-206">`MarqueeBorder`: このコントロールは、端の周りに "ライト" の境界線を描画します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-206">`MarqueeBorder`: This control paints a border of "lights" around its edges.</span></span> <span data-ttu-id="a6e24-207">ライトが連続して点滅しているように見えます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-207">The lights flash in sequence, so they appear to be moving around the border.</span></span> <span data-ttu-id="a6e24-208">ライトフラッシュがというプロパティによって制御される速度 `UpdatePeriod` 。</span><span class="sxs-lookup"><span data-stu-id="a6e24-208">The speed at which the lights flash is controlled by a property called `UpdatePeriod`.</span></span> <span data-ttu-id="a6e24-209">他のいくつかのカスタムプロパティによって、コントロールの外観の他の側面が決まります。</span><span class="sxs-lookup"><span data-stu-id="a6e24-209">Several other custom properties determine other aspects of the control's appearance.</span></span> <span data-ttu-id="a6e24-210">と呼ばれる2つのメソッドは、 `StartMarquee` `StopMarquee` アニメーションの開始と停止を制御します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-210">Two methods, called `StartMarquee` and `StopMarquee`, control when the animation starts and stops.</span></span>

- <span data-ttu-id="a6e24-211">`MarqueeText`: このコントロールは、点滅する文字列を描画します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-211">`MarqueeText`: This control paints a flashing string.</span></span> <span data-ttu-id="a6e24-212">コントロールと同様に、 `MarqueeBorder` テキストが点滅する速度は、プロパティによって制御され `UpdatePeriod` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-212">Like the `MarqueeBorder` control, the speed at which the text flashes is controlled by the `UpdatePeriod` property.</span></span> <span data-ttu-id="a6e24-213">コントロールには、 `MarqueeText` `StartMarquee` `StopMarquee` コントロールに共通のメソッドとメソッドもあり `MarqueeBorder` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-213">The `MarqueeText` control also has the `StartMarquee` and `StopMarquee` methods in common with the `MarqueeBorder` control.</span></span>

<span data-ttu-id="a6e24-214">デザイン時に、を使用すると、 `MarqueeControlRootDesigner` これら2つのコントロール型を任意の組み合わせでに追加でき `MarqueeControl` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-214">At design time, the `MarqueeControlRootDesigner` allows these two control types to be added to a `MarqueeControl` in any combination.</span></span>

<span data-ttu-id="a6e24-215">2つのコントロールの共通機能は、と呼ばれるインターフェイスに分けられてい `IMarqueeWidget` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-215">Common features of the two controls are factored into an interface called `IMarqueeWidget`.</span></span> <span data-ttu-id="a6e24-216">これにより、は、 `MarqueeControl` マーキーに関連する子コントロールを検出し、特別な処理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-216">This allows the `MarqueeControl` to discover any Marquee-related child controls and give them special treatment.</span></span>

<span data-ttu-id="a6e24-217">定期的なアニメーション機能を実装するには、 <xref:System.ComponentModel.BackgroundWorker> 名前空間のオブジェクトを使用し <xref:System.ComponentModel?displayProperty=nameWithType> ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-217">To implement the periodic animation feature, you will use <xref:System.ComponentModel.BackgroundWorker> objects from the <xref:System.ComponentModel?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="a6e24-218">オブジェクトを使用することもでき <xref:System.Windows.Forms.Timer> ますが、多くの `IMarqueeWidget` オブジェクトが存在する場合、1つの UI スレッドがアニメーションを維持できないことがあります。</span><span class="sxs-lookup"><span data-stu-id="a6e24-218">You could use <xref:System.Windows.Forms.Timer> objects, but when many `IMarqueeWidget` objects are present, the single UI thread may be unable to keep up with the animation.</span></span>

### <a name="to-create-a-child-control-for-your-custom-control"></a><span data-ttu-id="a6e24-219">カスタムコントロールの子コントロールを作成するには</span><span class="sxs-lookup"><span data-stu-id="a6e24-219">To create a child control for your custom control</span></span>

1. <span data-ttu-id="a6e24-220">新しいクラス項目をプロジェクトに追加 `MarqueeControlLibrary` します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-220">Add a new class item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="a6e24-221">新しいソースファイルに "IMarqueeWidget" のベース名を指定します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-221">Give the new source file a base name of "IMarqueeWidget."</span></span>

2. <span data-ttu-id="a6e24-222">`IMarqueeWidget`**コードエディター** でソースファイルを開き、宣言をからに変更 `class` し `interface` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-222">Open the `IMarqueeWidget` source file in the **Code Editor** and change the declaration from `class` to `interface`:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#2)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#2)]

3. <span data-ttu-id="a6e24-223">次のコードをインターフェイスに追加して、 `IMarqueeWidget` 2 つのメソッドと、マーキーアニメーションを操作するプロパティを公開します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-223">Add the following code to the `IMarqueeWidget` interface to expose two methods and a property that manipulate the marquee animation:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#3)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#3)]

4. <span data-ttu-id="a6e24-224">新しい **カスタムコントロール** 項目をプロジェクトに追加 `MarqueeControlLibrary` します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-224">Add a new **Custom Control** item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="a6e24-225">新しいソースファイルに "MarqueeText" のベース名を指定します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-225">Give the new source file a base name of "MarqueeText."</span></span>

5. <span data-ttu-id="a6e24-226">コンポーネントを <xref:System.ComponentModel.BackgroundWorker> **ツールボックス** からコントロールにドラッグし `MarqueeText` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-226">Drag a <xref:System.ComponentModel.BackgroundWorker> component from the **Toolbox** onto your `MarqueeText` control.</span></span> <span data-ttu-id="a6e24-227">このコンポーネントを使用すると、 `MarqueeText` コントロール自体を非同期的に更新できます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-227">This component will allow the `MarqueeText` control to update itself asynchronously.</span></span>

6. <span data-ttu-id="a6e24-228">[ **プロパティ** ] ウィンドウで、 <xref:System.ComponentModel.BackgroundWorker> コンポーネントの `WorkerReportsProgress` プロパティと <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> プロパティを **true** に設定します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-228">In the **Properties** window, set the <xref:System.ComponentModel.BackgroundWorker> component's `WorkerReportsProgress` and <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> properties to **true**.</span></span> <span data-ttu-id="a6e24-229">これらの設定により、 <xref:System.ComponentModel.BackgroundWorker> コンポーネントは定期的にイベントを発生させ、非同期更新を取り消すことができ <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-229">These settings allow the <xref:System.ComponentModel.BackgroundWorker> component to periodically raise the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event and to cancel asynchronous updates.</span></span>

   <span data-ttu-id="a6e24-230">詳細については、「 [BackgroundWorker Component](backgroundworker-component.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6e24-230">For more information, see [BackgroundWorker Component](backgroundworker-component.md).</span></span>

7. <span data-ttu-id="a6e24-231">`MarqueeText`**コードエディター** でソースファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-231">Open the `MarqueeText` source file in the **Code Editor**.</span></span> <span data-ttu-id="a6e24-232">ファイルの先頭に、次の名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="a6e24-232">At the top of the file, import the following namespaces:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#120)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#120)]

8. <span data-ttu-id="a6e24-233">を継承し、インターフェイスを実装するように、の宣言を変更 `MarqueeText` <xref:System.Windows.Forms.Label> し `IMarqueeWidget` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-233">Change the declaration of `MarqueeText` to inherit from <xref:System.Windows.Forms.Label> and to implement the `IMarqueeWidget` interface:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#130)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#130)]

9. <span data-ttu-id="a6e24-234">公開されたプロパティに対応するインスタンス変数を宣言し、コンストラクターで初期化します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-234">Declare the instance variables that correspond to the exposed properties, and initialize them in the constructor.</span></span> <span data-ttu-id="a6e24-235">フィールドは、 `isLit` プロパティによって指定された色でテキストを描画するかどうかを決定し `LightColor` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-235">The `isLit` field determines if the text is to be painted in the color given by the `LightColor` property.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#140)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#140)]

10. <span data-ttu-id="a6e24-236">`IMarqueeWidget` インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-236">Implement the `IMarqueeWidget` interface.</span></span>

    <span data-ttu-id="a6e24-237">`StartMarquee`メソッドと `StopMarquee` メソッドは、 <xref:System.ComponentModel.BackgroundWorker> コンポーネントの <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> メソッドとメソッドを呼び出して、アニメーションを <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> 開始および停止します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-237">The `StartMarquee` and `StopMarquee` methods invoke the <xref:System.ComponentModel.BackgroundWorker> component's <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> and <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> methods to start and stop the animation.</span></span>

    <span data-ttu-id="a6e24-238"><xref:System.ComponentModel.CategoryAttribute.Category%2A>属性と <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> 属性はプロパティに適用さ `UpdatePeriod` れるため、"Marquee" と呼ばれるプロパティウィンドウのカスタムセクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-238">The <xref:System.ComponentModel.CategoryAttribute.Category%2A> and <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> attributes are applied to the `UpdatePeriod` property so it appears in a custom section of the Properties window called "Marquee."</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#150](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#150)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#150)]

11. <span data-ttu-id="a6e24-239">プロパティアクセサーを実装します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-239">Implement the property accessors.</span></span> <span data-ttu-id="a6e24-240">クライアントには `LightColor` 、との2つのプロパティを公開します。 `DarkColor`</span><span class="sxs-lookup"><span data-stu-id="a6e24-240">You'll expose two properties to clients: `LightColor` and `DarkColor`.</span></span> <span data-ttu-id="a6e24-241"><xref:System.ComponentModel.CategoryAttribute.Category%2A>これらの <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> プロパティには属性と属性が適用されるので、プロパティは "Marquee" と呼ばれるプロパティウィンドウのカスタムセクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-241">The <xref:System.ComponentModel.CategoryAttribute.Category%2A> and <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> attributes are applied to these properties, so the properties appear in a custom section of the Properties window called "Marquee."</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#160](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#160)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#160)]

12. <span data-ttu-id="a6e24-242">コンポーネントとイベントのハンドラーを実装し <xref:System.ComponentModel.BackgroundWorker> <xref:System.ComponentModel.BackgroundWorker.DoWork> <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-242">Implement the handlers for the <xref:System.ComponentModel.BackgroundWorker> component's <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> events.</span></span>

    <span data-ttu-id="a6e24-243"><xref:System.ComponentModel.BackgroundWorker.DoWork>イベントハンドラーは、によって指定されたミリ秒数の間スリープ状態に `UpdatePeriod` <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> なり、コードがを呼び出すことによってアニメーションを停止するまで、イベントを発生させ <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-243">The <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler sleeps for the number of milliseconds specified by `UpdatePeriod` then raises the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event, until your code stops the animation by calling <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>.</span></span>

    <span data-ttu-id="a6e24-244"><xref:System.ComponentModel.BackgroundWorker.ProgressChanged>イベントハンドラーは、テキストを淡色と濃色の状態の間で切り替えて、点滅のようにします。</span><span class="sxs-lookup"><span data-stu-id="a6e24-244">The <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event handler toggles the text between its light and dark state to give the appearance of flashing.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#180](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#180)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#180)]

13. <span data-ttu-id="a6e24-245">アニメーションを <xref:System.Windows.Forms.Control.OnPaint%2A> 有効にするには、メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="a6e24-245">Override the <xref:System.Windows.Forms.Control.OnPaint%2A> method to enable the animation.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#170](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#170)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#170)]

14. <span data-ttu-id="a6e24-246">**F6** キーを押してソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="a6e24-246">Press **F6** to build the solution.</span></span>

## <a name="create-the-marqueeborder-child-control"></a><span data-ttu-id="a6e24-247">MarqueeBorder 子コントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="a6e24-247">Create the MarqueeBorder Child Control</span></span>

<span data-ttu-id="a6e24-248">コントロールは、 `MarqueeBorder` コントロールよりも少し洗練されてい `MarqueeText` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-248">The `MarqueeBorder` control is slightly more sophisticated than the `MarqueeText` control.</span></span> <span data-ttu-id="a6e24-249">これにはさらに多くのプロパティがあり、メソッドのアニメーションも複雑になり <xref:System.Windows.Forms.Control.OnPaint%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-249">It has more properties and the animation in the <xref:System.Windows.Forms.Control.OnPaint%2A> method is more involved.</span></span> <span data-ttu-id="a6e24-250">原則として、コントロールと非常によく似てい `MarqueeText` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-250">In principle, it is quite similar to the `MarqueeText` control.</span></span>

<span data-ttu-id="a6e24-251">コントロールは `MarqueeBorder` 子コントロールを持つことができるため、イベントに注意する必要があり <xref:System.Windows.Forms.Control.Layout> ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-251">Because the `MarqueeBorder` control can have child controls, it needs to be aware of <xref:System.Windows.Forms.Control.Layout> events.</span></span>

### <a name="to-create-the-marqueeborder-control"></a><span data-ttu-id="a6e24-252">MarqueeBorder コントロールを作成するには</span><span class="sxs-lookup"><span data-stu-id="a6e24-252">To create the MarqueeBorder control</span></span>

1. <span data-ttu-id="a6e24-253">新しい **カスタムコントロール** 項目をプロジェクトに追加 `MarqueeControlLibrary` します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-253">Add a new **Custom Control** item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="a6e24-254">新しいソースファイルに "MarqueeBorder" のベース名を指定します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-254">Give the new source file a base name of "MarqueeBorder."</span></span>

2. <span data-ttu-id="a6e24-255">コンポーネントを <xref:System.ComponentModel.BackgroundWorker> **ツールボックス** からコントロールにドラッグし `MarqueeBorder` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-255">Drag a <xref:System.ComponentModel.BackgroundWorker> component from the **Toolbox** onto your `MarqueeBorder` control.</span></span> <span data-ttu-id="a6e24-256">このコンポーネントを使用すると、 `MarqueeBorder` コントロール自体を非同期的に更新できます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-256">This component will allow the `MarqueeBorder` control to update itself asynchronously.</span></span>

3. <span data-ttu-id="a6e24-257">[ **プロパティ** ] ウィンドウで、 <xref:System.ComponentModel.BackgroundWorker> コンポーネントの `WorkerReportsProgress` プロパティと <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> プロパティを **true** に設定します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-257">In the **Properties** window, set the <xref:System.ComponentModel.BackgroundWorker> component's `WorkerReportsProgress` and <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> properties to **true**.</span></span> <span data-ttu-id="a6e24-258">これらの設定により、 <xref:System.ComponentModel.BackgroundWorker> コンポーネントは定期的にイベントを発生させ、非同期更新を取り消すことができ <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-258">These settings allow the <xref:System.ComponentModel.BackgroundWorker> component to periodically raise the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event and to cancel asynchronous updates.</span></span> <span data-ttu-id="a6e24-259">詳細については、「 [BackgroundWorker Component](backgroundworker-component.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6e24-259">For more information, see [BackgroundWorker Component](backgroundworker-component.md).</span></span>

4. <span data-ttu-id="a6e24-260">**[プロパティ]** ウィンドウで、 **[イベント]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-260">In the **Properties** window, select the **Events** button.</span></span> <span data-ttu-id="a6e24-261">イベントおよびイベントのハンドラーをアタッチ <xref:System.ComponentModel.BackgroundWorker.DoWork> <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-261">Attach handlers for the <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> events.</span></span>

5. <span data-ttu-id="a6e24-262">`MarqueeBorder`**コードエディター** でソースファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-262">Open the `MarqueeBorder` source file in the **Code Editor**.</span></span> <span data-ttu-id="a6e24-263">ファイルの先頭に、次の名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="a6e24-263">At the top of the file, import the following namespaces:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#20)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#20)]

6. <span data-ttu-id="a6e24-264">から継承し、インターフェイスを実装するように、の宣言を変更 `MarqueeBorder` <xref:System.Windows.Forms.Panel> し `IMarqueeWidget` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-264">Change the declaration of `MarqueeBorder` to inherit from <xref:System.Windows.Forms.Panel> and to implement the `IMarqueeWidget` interface.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#30)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#30)]

7. <span data-ttu-id="a6e24-265">コントロールの状態を管理するための2つの列挙体を宣言 `MarqueeBorder` します。 `MarqueeSpinDirection` これは、ライトが境界の周りを "スピン" する方向を決定します。は、 `MarqueeLightShape` ライトの形状 (正方形または円形) を決定します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-265">Declare two enumerations for managing the `MarqueeBorder` control's state: `MarqueeSpinDirection`, which determines the direction in which the lights "spin" around the border, and `MarqueeLightShape`, which determines the shape of the lights (square or circular).</span></span> <span data-ttu-id="a6e24-266">これらの宣言は、クラス宣言の前に配置 `MarqueeBorder` します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-266">Place these declarations before the `MarqueeBorder` class declaration.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#97](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#97)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#97](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#97)]

8. <span data-ttu-id="a6e24-267">公開されたプロパティに対応するインスタンス変数を宣言し、コンストラクターで初期化します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-267">Declare the instance variables that correspond to the exposed properties, and initialize them in the constructor.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#40)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#40)]

9. <span data-ttu-id="a6e24-268">`IMarqueeWidget` インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-268">Implement the `IMarqueeWidget` interface.</span></span>

    <span data-ttu-id="a6e24-269">`StartMarquee`メソッドと `StopMarquee` メソッドは、 <xref:System.ComponentModel.BackgroundWorker> コンポーネントの <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> メソッドとメソッドを呼び出して、アニメーションを <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> 開始および停止します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-269">The `StartMarquee` and `StopMarquee` methods invoke the <xref:System.ComponentModel.BackgroundWorker> component's <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> and <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> methods to start and stop the animation.</span></span>

    <span data-ttu-id="a6e24-270">コントロールに `MarqueeBorder` 子コントロールを含めることができるため、メソッドは、 `StartMarquee` すべての子コントロールを列挙し、を `StartMarquee` 実装する子コントロールに対してを呼び出し `IMarqueeWidget` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-270">Because the `MarqueeBorder` control can contain child controls, the `StartMarquee` method enumerates all child controls and calls `StartMarquee` on those that implement `IMarqueeWidget`.</span></span> <span data-ttu-id="a6e24-271">メソッドには `StopMarquee` 同様の実装があります。</span><span class="sxs-lookup"><span data-stu-id="a6e24-271">The `StopMarquee` method has a similar implementation.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#50](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#50)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#50](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#50)]

10. <span data-ttu-id="a6e24-272">プロパティアクセサーを実装します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-272">Implement the property accessors.</span></span> <span data-ttu-id="a6e24-273">`MarqueeBorder`コントロールには、外観を制御するためのプロパティがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="a6e24-273">The `MarqueeBorder` control has several properties for controlling its appearance.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#60)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#60)]

11. <span data-ttu-id="a6e24-274">コンポーネントとイベントのハンドラーを実装し <xref:System.ComponentModel.BackgroundWorker> <xref:System.ComponentModel.BackgroundWorker.DoWork> <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-274">Implement the handlers for the <xref:System.ComponentModel.BackgroundWorker> component's <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> events.</span></span>

    <span data-ttu-id="a6e24-275"><xref:System.ComponentModel.BackgroundWorker.DoWork>イベントハンドラーは、によって指定されたミリ秒数の間スリープ状態に `UpdatePeriod` <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> なり、コードがを呼び出すことによってアニメーションを停止するまで、イベントを発生させ <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-275">The <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler sleeps for the number of milliseconds specified by `UpdatePeriod` then raises the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event, until your code stops the animation by calling <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>.</span></span>

    <span data-ttu-id="a6e24-276"><xref:System.ComponentModel.BackgroundWorker.ProgressChanged>イベントハンドラーは、他のライトの明るい/暗い状態が決定される "基本" ライトの位置をインクリメントし、メソッドを呼び出して <xref:System.Windows.Forms.Control.Refresh%2A> 、コントロール自体を再描画します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-276">The <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event handler increments the position of the "base" light, from which the light/dark state of the other lights is determined, and calls the <xref:System.Windows.Forms.Control.Refresh%2A> method to cause the control to repaint itself.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#90](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#90)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#90](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#90)]

12. <span data-ttu-id="a6e24-277">ヘルパーメソッドとを実装 `IsLit` し `DrawLight` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-277">Implement the helper methods, `IsLit` and `DrawLight`.</span></span>

    <span data-ttu-id="a6e24-278">メソッドは、 `IsLit` 指定された位置のライトの色を決定します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-278">The `IsLit` method determines the color of a light at a given position.</span></span> <span data-ttu-id="a6e24-279">"Lit" のライトは、プロパティによって指定された色で描画され `LightColor` ます。 "ダーク" は、プロパティによって指定された色で描画され `DarkColor` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-279">Lights that are "lit" are drawn in the color given by the `LightColor` property, and those that are "dark" are drawn in the color given by the `DarkColor` property.</span></span>

    <span data-ttu-id="a6e24-280">メソッドは、 `DrawLight` 適切な色、形状、および位置を使用してライトを描画します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-280">The `DrawLight` method draws a light using the appropriate color, shape, and position.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#80](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#80)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#80](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#80)]

13. <span data-ttu-id="a6e24-281"><xref:System.Windows.Forms.Control.OnLayout%2A> および <xref:System.Windows.Forms.Control.OnPaint%2A> メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="a6e24-281">Override the <xref:System.Windows.Forms.Control.OnLayout%2A> and <xref:System.Windows.Forms.Control.OnPaint%2A> methods.</span></span>

    <span data-ttu-id="a6e24-282">メソッドは、 <xref:System.Windows.Forms.Control.OnPaint%2A> コントロールの端に沿ってライトを描画し `MarqueeBorder` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-282">The <xref:System.Windows.Forms.Control.OnPaint%2A> method draws the lights along the edges of the `MarqueeBorder` control.</span></span>

    <span data-ttu-id="a6e24-283">メソッドは <xref:System.Windows.Forms.Control.OnPaint%2A> コントロールのディメンションに依存するため `MarqueeBorder` 、レイアウトが変更されるたびに呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6e24-283">Because the <xref:System.Windows.Forms.Control.OnPaint%2A> method depends on the dimensions of the `MarqueeBorder` control, you need to call it whenever the layout changes.</span></span> <span data-ttu-id="a6e24-284">これを実現するには、 <xref:System.Windows.Forms.Control.OnLayout%2A> をオーバーライドし、を呼び出し <xref:System.Windows.Forms.Control.Refresh%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-284">To achieve this, override <xref:System.Windows.Forms.Control.OnLayout%2A> and call <xref:System.Windows.Forms.Control.Refresh%2A>.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#70](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#70)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#70](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#70)]

## <a name="create-a-custom-designer-to-shadow-and-filter-properties"></a><span data-ttu-id="a6e24-285">カスタムデザイナーを作成してプロパティをシャドウおよびフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="a6e24-285">Create a Custom Designer to Shadow and Filter Properties</span></span>

<span data-ttu-id="a6e24-286">クラスは、 `MarqueeControlRootDesigner` ルートデザイナーの実装を提供します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-286">The `MarqueeControlRootDesigner` class provides the implementation for the root designer.</span></span> <span data-ttu-id="a6e24-287">で動作するこのデザイナーに加えて、 `MarqueeControl` コントロールに特に関連付けられたカスタムデザイナーが必要です `MarqueeBorder` 。</span><span class="sxs-lookup"><span data-stu-id="a6e24-287">In addition to this designer, which operates on the `MarqueeControl`, you'll need a custom designer that is specifically associated with the `MarqueeBorder` control.</span></span> <span data-ttu-id="a6e24-288">このデザイナーには、カスタムルートデザイナーのコンテキストに適したカスタム動作が用意されています。</span><span class="sxs-lookup"><span data-stu-id="a6e24-288">This designer provides custom behavior that is appropriate in the context of the custom root designer.</span></span>

<span data-ttu-id="a6e24-289">具体的には、は、 `MarqueeBorderDesigner` コントロールの特定のプロパティを "シャドウ" してフィルター処理し `MarqueeBorder` 、デザイン環境との相互作用を変更します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-289">Specifically, the `MarqueeBorderDesigner` will "shadow" and filter certain properties on the `MarqueeBorder` control, changing their interaction with the design environment.</span></span>

<span data-ttu-id="a6e24-290">コンポーネントのプロパティアクセサーへの呼び出しのインターセプトは、"シャドウ処理" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-290">Intercepting calls to a component's property accessor is known as "shadowing."</span></span> <span data-ttu-id="a6e24-291">これにより、デザイナーはユーザーが設定した値を追跡し、必要に応じてその値をデザイン対象のコンポーネントに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-291">It allows a designer to track the value set by the user and optionally pass that value to the component being designed.</span></span>

<span data-ttu-id="a6e24-292">この例では、 <xref:System.Windows.Forms.Control.Visible%2A> プロパティとプロパティがに <xref:System.Windows.Forms.Control.Enabled%2A> よってシャドウされます。これにより、 `MarqueeBorderDesigner` デザイン時にユーザーがコントロールを非表示にしたり無効にしたりすることができなくなり `MarqueeBorder` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-292">For this example, the <xref:System.Windows.Forms.Control.Visible%2A> and <xref:System.Windows.Forms.Control.Enabled%2A> properties will be shadowed by the `MarqueeBorderDesigner`, which prevents the user from making the `MarqueeBorder` control invisible or disabled during design time.</span></span>

<span data-ttu-id="a6e24-293">デザイナーでは、プロパティを追加および削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-293">Designers can also add and remove properties.</span></span> <span data-ttu-id="a6e24-294">この例では、プロパティは <xref:System.Windows.Forms.Control.Padding%2A> デザイン時に削除され `MarqueeBorder` ます。コントロールはプログラムによって、プロパティによって指定されたライトのサイズに基づいて余白を設定し `LightSize` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-294">For this example, the <xref:System.Windows.Forms.Control.Padding%2A> property will be removed at design time, because the `MarqueeBorder` control programmatically sets the padding based on the size of the lights specified by the `LightSize` property.</span></span>

<span data-ttu-id="a6e24-295">の基本クラス `MarqueeBorderDesigner` はです <xref:System.ComponentModel.Design.ComponentDesigner> 。これには、デザイン時にコントロールによって公開される属性、プロパティ、およびイベントを変更するためのメソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="a6e24-295">The base class for `MarqueeBorderDesigner` is <xref:System.ComponentModel.Design.ComponentDesigner>, which has methods that can change the attributes, properties, and events exposed by a control at design time:</span></span>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterProperties%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterAttributes%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterAttributes%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterEvents%2A>

- <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterEvents%2A>

<span data-ttu-id="a6e24-296">これらのメソッドを使用してコンポーネントのパブリックインターフェイスを変更する場合は、次の規則に従います。</span><span class="sxs-lookup"><span data-stu-id="a6e24-296">When changing the public interface of a component using these methods, follow these rules:</span></span>

- <span data-ttu-id="a6e24-297">メソッドでのみ項目を追加または削除する `PreFilter`</span><span class="sxs-lookup"><span data-stu-id="a6e24-297">Add or remove items in the `PreFilter` methods only</span></span>

- <span data-ttu-id="a6e24-298">メソッド内の既存の項目のみを変更する `PostFilter`</span><span class="sxs-lookup"><span data-stu-id="a6e24-298">Modify existing items in the `PostFilter` methods only</span></span>

- <span data-ttu-id="a6e24-299">常に基本実装をメソッドで呼び出す `PreFilter`</span><span class="sxs-lookup"><span data-stu-id="a6e24-299">Always call the base implementation first in the `PreFilter` methods</span></span>

- <span data-ttu-id="a6e24-300">メソッドの最後に基本実装を呼び出します。 `PostFilter`</span><span class="sxs-lookup"><span data-stu-id="a6e24-300">Always call the base implementation last in the `PostFilter` methods</span></span>

<span data-ttu-id="a6e24-301">これらの規則に従うことで、デザイン時環境のすべてのデザイナーが、デザインされているすべてのコンポーネントの一貫したビューを確実に表示できるようになります。</span><span class="sxs-lookup"><span data-stu-id="a6e24-301">Adhering to these rules ensures that all designers in the design-time environment have a consistent view of all components being designed.</span></span>

<span data-ttu-id="a6e24-302">クラスは、 <xref:System.ComponentModel.Design.ComponentDesigner> シャドウプロパティの値を管理するためのディクショナリを提供します。これにより、特定のインスタンス変数を作成する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="a6e24-302">The <xref:System.ComponentModel.Design.ComponentDesigner> class provides a dictionary for managing the values of shadowed properties, which relieves you of the need to create specific instance variables.</span></span>

### <a name="to-create-a-custom-designer-to-shadow-and-filter-properties"></a><span data-ttu-id="a6e24-303">プロパティをシャドウおよびフィルター処理するためのカスタムデザイナーを作成するには</span><span class="sxs-lookup"><span data-stu-id="a6e24-303">To create a custom designer to shadow and filter properties</span></span>

1. <span data-ttu-id="a6e24-304">**Design** フォルダーを右クリックし、新しいクラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-304">Right-click the **Design** folder and add a new class.</span></span> <span data-ttu-id="a6e24-305">ソースファイルに **MarqueeBorderDesigner** のベース名を指定します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-305">Give the source file a base name of **MarqueeBorderDesigner**.</span></span>

2. <span data-ttu-id="a6e24-306">**コードエディター** で MarqueeBorderDesigner ソースファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-306">Open the MarqueeBorderDesigner source file in the **Code Editor**.</span></span> <span data-ttu-id="a6e24-307">ファイルの先頭に、次の名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="a6e24-307">At the top of the file, import the following namespaces:</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#420](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#420)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#420](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#420)]

3. <span data-ttu-id="a6e24-308">を `MarqueeBorderDesigner` 継承するようにの宣言を変更 <xref:System.Windows.Forms.Design.ParentControlDesigner> します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-308">Change the declaration of `MarqueeBorderDesigner` to inherit from <xref:System.Windows.Forms.Design.ParentControlDesigner>.</span></span>

    <span data-ttu-id="a6e24-309">コントロールに `MarqueeBorder` 子コントロールを含めることができるため、はを `MarqueeBorderDesigner` 継承し <xref:System.Windows.Forms.Design.ParentControlDesigner> ます。これは、親子の相互作用を処理します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-309">Because the `MarqueeBorder` control can contain child controls, `MarqueeBorderDesigner` inherits from <xref:System.Windows.Forms.Design.ParentControlDesigner>, which handles the parent-child interaction.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#430](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#430)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#430](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#430)]

4. <span data-ttu-id="a6e24-310">の基本実装をオーバーライド <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A> します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-310">Override the base implementation of <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#450](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#450)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#450](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#450)]

5. <span data-ttu-id="a6e24-311"><xref:System.Windows.Forms.Control.Enabled%2A> プロパティと <xref:System.Windows.Forms.Control.Visible%2A> プロパティを実装します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-311">Implement the <xref:System.Windows.Forms.Control.Enabled%2A> and <xref:System.Windows.Forms.Control.Visible%2A> properties.</span></span> <span data-ttu-id="a6e24-312">これらの実装は、コントロールのプロパティをシャドウします。</span><span class="sxs-lookup"><span data-stu-id="a6e24-312">These implementations shadow the control's properties.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#440](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#440)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#440](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#440)]

## <a name="handle-component-changes"></a><span data-ttu-id="a6e24-313">コンポーネントの変更を処理する</span><span class="sxs-lookup"><span data-stu-id="a6e24-313">Handle Component Changes</span></span>

<span data-ttu-id="a6e24-314">クラスは、 `MarqueeControlRootDesigner` インスタンスのカスタムデザイン時エクスペリエンスを提供し `MarqueeControl` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-314">The `MarqueeControlRootDesigner` class provides the custom design-time experience for your `MarqueeControl` instances.</span></span> <span data-ttu-id="a6e24-315">デザイン時の機能のほとんどは、クラスから継承され <xref:System.Windows.Forms.Design.DocumentDesigner> ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-315">Most of the design-time functionality is inherited from the <xref:System.Windows.Forms.Design.DocumentDesigner> class.</span></span> <span data-ttu-id="a6e24-316">コードには、コンポーネントの変更の処理とデザイナー動詞の追加という2つのカスタマイズのカスタマイズが実装されます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-316">Your code will implement two specific customizations: handling component changes, and adding designer verbs.</span></span>

<span data-ttu-id="a6e24-317">ユーザーが `MarqueeControl` インスタンスをデザインすると、ルートデザイナーはとその子コントロールに対する変更を追跡し `MarqueeControl` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-317">As users design their `MarqueeControl` instances, your root designer will track changes to the `MarqueeControl` and its child controls.</span></span> <span data-ttu-id="a6e24-318">デザイン時環境には、コンポーネントの状態に対する変更を追跡するための便利なサービスが用意されて <xref:System.ComponentModel.Design.IComponentChangeService> います。</span><span class="sxs-lookup"><span data-stu-id="a6e24-318">The design-time environment offers a convenient service, <xref:System.ComponentModel.Design.IComponentChangeService>, for tracking changes to component state.</span></span>

<span data-ttu-id="a6e24-319">このサービスへの参照を取得するには、メソッドを使用して環境に対してクエリを実行し <xref:System.ComponentModel.Design.ComponentDesigner.GetService%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-319">You acquire a reference to this service by querying the environment with the <xref:System.ComponentModel.Design.ComponentDesigner.GetService%2A> method.</span></span> <span data-ttu-id="a6e24-320">クエリが成功した場合、デザイナーはイベントのハンドラーをアタッチ <xref:System.ComponentModel.Design.IComponentChangeService.ComponentChanged> し、デザイン時に一貫性のある状態を維持するために必要なすべてのタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-320">If the query is successful, your designer can attach a handler for the <xref:System.ComponentModel.Design.IComponentChangeService.ComponentChanged> event and perform whatever tasks are required to maintain a consistent state at design time.</span></span>

<span data-ttu-id="a6e24-321">クラスの場合は `MarqueeControlRootDesigner` 、に格納され <xref:System.Windows.Forms.Control.Refresh%2A> ている各オブジェクトに対してメソッドを呼び出し `IMarqueeWidget` `MarqueeControl` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-321">In the case of the `MarqueeControlRootDesigner` class, you will call the <xref:System.Windows.Forms.Control.Refresh%2A> method on each `IMarqueeWidget` object contained by the `MarqueeControl`.</span></span> <span data-ttu-id="a6e24-322">これにより、 `IMarqueeWidget` 親のようなプロパティが変更されたときに、オブジェクトが適切に再描画され <xref:System.Windows.Forms.Control.Size%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-322">This will cause the `IMarqueeWidget` object to repaint itself appropriately when properties like its parent's <xref:System.Windows.Forms.Control.Size%2A> are changed.</span></span>

### <a name="to-handle-component-changes"></a><span data-ttu-id="a6e24-323">コンポーネントの変更を処理するには</span><span class="sxs-lookup"><span data-stu-id="a6e24-323">To handle component changes</span></span>

1. <span data-ttu-id="a6e24-324">`MarqueeControlRootDesigner`**コードエディター** でソースファイルを開き、メソッドをオーバーライドし <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-324">Open the `MarqueeControlRootDesigner` source file in the **Code Editor** and override the <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> method.</span></span> <span data-ttu-id="a6e24-325">の基本実装を呼び出し、に対してクエリを実行し <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> <xref:System.ComponentModel.Design.IComponentChangeService> ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-325">Call the base implementation of <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> and query for the <xref:System.ComponentModel.Design.IComponentChangeService>.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#580](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#580)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#580](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#580)]

2. <span data-ttu-id="a6e24-326"><xref:System.ComponentModel.Design.IComponentChangeService.OnComponentChanged%2A>イベントハンドラーを実装します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-326">Implement the <xref:System.ComponentModel.Design.IComponentChangeService.OnComponentChanged%2A> event handler.</span></span> <span data-ttu-id="a6e24-327">送信コンポーネントの型をテストし、がの場合は `IMarqueeWidget` 、そのメソッドを呼び出し <xref:System.Windows.Forms.Control.Refresh%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-327">Test the sending component's type, and if it is an `IMarqueeWidget`, call its <xref:System.Windows.Forms.Control.Refresh%2A> method.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#560](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#560)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#560](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#560)]

## <a name="add-designer-verbs-to-your-custom-designer"></a><span data-ttu-id="a6e24-328">デザイナー動詞をカスタムデザイナーに追加する</span><span class="sxs-lookup"><span data-stu-id="a6e24-328">Add Designer Verbs to your Custom Designer</span></span>

<span data-ttu-id="a6e24-329">デザイナー動詞は、イベント ハンドラーにリンクされたメニュー コマンドです。</span><span class="sxs-lookup"><span data-stu-id="a6e24-329">A designer verb is a menu command linked to an event handler.</span></span> <span data-ttu-id="a6e24-330">デザイナー動詞は、デザイン時にコンポーネントのショートカットメニューに追加されます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-330">Designer verbs are added to a component's shortcut menu at design time.</span></span> <span data-ttu-id="a6e24-331">詳細については、「<xref:System.ComponentModel.Design.DesignerVerb>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6e24-331">For more information, see <xref:System.ComponentModel.Design.DesignerVerb>.</span></span>

<span data-ttu-id="a6e24-332">デザイナーに2つのデザイナー動詞を追加します。 **テストを実行** し、 **テストを停止** します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-332">You will add two designer verbs to your designers: **Run Test** and **Stop Test**.</span></span> <span data-ttu-id="a6e24-333">これらの動詞を使用すると、デザイン時にの実行時の動作を表示でき `MarqueeControl` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-333">These verbs will allow you to view the run-time behavior of the `MarqueeControl` at design time.</span></span> <span data-ttu-id="a6e24-334">これらの動詞はに追加され `MarqueeControlRootDesigner` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-334">These verbs will be added to `MarqueeControlRootDesigner`.</span></span>

<span data-ttu-id="a6e24-335">**実行テスト** が呼び出されると、動詞イベントハンドラーは `StartMarquee` に対してメソッドを呼び出し `MarqueeControl` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-335">When **Run Test** is invoked, the verb event handler will call the `StartMarquee` method on the `MarqueeControl`.</span></span> <span data-ttu-id="a6e24-336">**停止テスト** が呼び出されると、動詞イベントハンドラーは `StopMarquee` に対してメソッドを呼び出し `MarqueeControl` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-336">When **Stop Test** is invoked, the verb event handler will call the `StopMarquee` method on the `MarqueeControl`.</span></span> <span data-ttu-id="a6e24-337">メソッドとメソッドの実装では `StartMarquee` `StopMarquee` 、を実装する含まれるコントロールに対してこれらのメソッドを呼び出し `IMarqueeWidget` ます。これにより、含まれる `IMarqueeWidget` コントロールもテストに参加します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-337">The implementation of the `StartMarquee` and `StopMarquee` methods call these methods on contained controls that implement `IMarqueeWidget`, so any contained `IMarqueeWidget` controls will also participate in the test.</span></span>

### <a name="to-add-designer-verbs-to-your-custom-designers"></a><span data-ttu-id="a6e24-338">デザイナー動詞をカスタムデザイナーに追加するには</span><span class="sxs-lookup"><span data-stu-id="a6e24-338">To add designer verbs to your custom designers</span></span>

1. <span data-ttu-id="a6e24-339">クラスで、 `MarqueeControlRootDesigner` およびという名前のイベントハンドラーを追加し `OnVerbRunTest` `OnVerbStopTest` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-339">In the `MarqueeControlRootDesigner` class, add event handlers named `OnVerbRunTest` and `OnVerbStopTest`.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#570](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#570)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#570](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#570)]

2. <span data-ttu-id="a6e24-340">これらのイベントハンドラーを、対応するデザイナー動詞に接続します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-340">Connect these event handlers to their corresponding designer verbs.</span></span> <span data-ttu-id="a6e24-341">`MarqueeControlRootDesigner`<xref:System.ComponentModel.Design.DesignerVerbCollection>基底クラスからを継承します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-341">`MarqueeControlRootDesigner` inherits a <xref:System.ComponentModel.Design.DesignerVerbCollection> from its base class.</span></span> <span data-ttu-id="a6e24-342">2つの新しいオブジェクトを作成 <xref:System.ComponentModel.Design.DesignerVerb> し、メソッドでこのコレクションに追加し <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-342">You will create two new <xref:System.ComponentModel.Design.DesignerVerb> objects and add them to this collection in the <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> method.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#590](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#590)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#590](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#590)]

## <a name="create-a-custom-uitypeeditor"></a><span data-ttu-id="a6e24-343">カスタム UITypeEditor を作成する</span><span class="sxs-lookup"><span data-stu-id="a6e24-343">Create a Custom UITypeEditor</span></span>

<span data-ttu-id="a6e24-344">ユーザーに対してカスタムのデザイン時エクスペリエンスを作成する場合、多くの場合、プロパティウィンドウとのカスタム操作を作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a6e24-344">When you create a custom design-time experience for users, it is often desirable to create a custom interaction with the Properties window.</span></span> <span data-ttu-id="a6e24-345">これを行うには、を作成し <xref:System.Drawing.Design.UITypeEditor> ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-345">You can accomplish this by creating a <xref:System.Drawing.Design.UITypeEditor>.</span></span>

<span data-ttu-id="a6e24-346">`MarqueeBorder`コントロールは、プロパティウィンドウ内のいくつかのプロパティを公開します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-346">The `MarqueeBorder` control exposes several properties in the Properties window.</span></span> <span data-ttu-id="a6e24-347">これらのプロパティのうちの2つ `MarqueeSpinDirection` `MarqueeLightShape` は、列挙体によって表されます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-347">Two of these properties, `MarqueeSpinDirection` and `MarqueeLightShape` are represented by enumerations.</span></span> <span data-ttu-id="a6e24-348">UI 型エディターの使用方法を示すために、 `MarqueeLightShape` プロパティにはクラスが関連付けられてい <xref:System.Drawing.Design.UITypeEditor> ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-348">To illustrate the use of a UI type editor, the `MarqueeLightShape` property will have an associated <xref:System.Drawing.Design.UITypeEditor> class.</span></span>

### <a name="to-create-a-custom-ui-type-editor"></a><span data-ttu-id="a6e24-349">カスタム UI 型エディターを作成するには</span><span class="sxs-lookup"><span data-stu-id="a6e24-349">To create a custom UI type editor</span></span>

1. <span data-ttu-id="a6e24-350">`MarqueeBorder`**コードエディター** でソースファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-350">Open the `MarqueeBorder` source file in the **Code Editor**.</span></span>

2. <span data-ttu-id="a6e24-351">クラスの定義で `MarqueeBorder` 、から派生するというクラスを宣言し `LightShapeEditor` <xref:System.Drawing.Design.UITypeEditor> ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-351">In the definition of the `MarqueeBorder` class, declare a class called `LightShapeEditor` that derives from <xref:System.Drawing.Design.UITypeEditor>.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#96](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#96)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#96](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#96)]

3. <span data-ttu-id="a6e24-352"><xref:System.Windows.Forms.Design.IWindowsFormsEditorService>という名前のインスタンス変数を宣言 `editorService` します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-352">Declare an <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> instance variable called `editorService`.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#92](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#92)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#92](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#92)]

4. <span data-ttu-id="a6e24-353"><xref:System.Drawing.Design.UITypeEditor.GetEditStyle%2A> メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="a6e24-353">Override the <xref:System.Drawing.Design.UITypeEditor.GetEditStyle%2A> method.</span></span> <span data-ttu-id="a6e24-354">この実装はを返し <xref:System.Drawing.Design.UITypeEditorEditStyle.DropDown> ます。これは、を表示する方法をデザイン環境に指示し `LightShapeEditor` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-354">This implementation returns <xref:System.Drawing.Design.UITypeEditorEditStyle.DropDown>, which tells the design environment how to display the `LightShapeEditor`.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#93](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#93)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#93](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#93)]

5. <span data-ttu-id="a6e24-355"><xref:System.Drawing.Design.UITypeEditor.EditValue%2A> メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="a6e24-355">Override the <xref:System.Drawing.Design.UITypeEditor.EditValue%2A> method.</span></span> <span data-ttu-id="a6e24-356">この実装は、オブジェクトのデザイン環境に対してクエリを <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> 行います。</span><span class="sxs-lookup"><span data-stu-id="a6e24-356">This implementation queries the design environment for an <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> object.</span></span> <span data-ttu-id="a6e24-357">成功した場合は、が作成さ `LightShapeSelectionControl` れます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-357">If successful, it creates a `LightShapeSelectionControl`.</span></span> <span data-ttu-id="a6e24-358">を <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.DropDownControl%2A> 開始するためにメソッドが呼び出され `LightShapeEditor` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-358">The <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.DropDownControl%2A> method is invoked to start the `LightShapeEditor`.</span></span> <span data-ttu-id="a6e24-359">この呼び出しからの戻り値がデザイン環境に返されます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-359">The return value from this invocation is returned to the design environment.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#94](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#94)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#94](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#94)]

## <a name="create-a-view-control-for-your-custom-uitypeeditor"></a><span data-ttu-id="a6e24-360">カスタム UITypeEditor のビューコントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="a6e24-360">Create a View Control for your Custom UITypeEditor</span></span>

<span data-ttu-id="a6e24-361">プロパティは、 `MarqueeLightShape` との2種類のライトシェイプをサポートしてい `Square` `Circle` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-361">The `MarqueeLightShape` property supports two types of light shapes: `Square` and `Circle`.</span></span> <span data-ttu-id="a6e24-362">プロパティウィンドウでこれらの値をグラフィカルに表示する目的でのみ使用されるカスタムコントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-362">You will create a custom control used solely for the purpose of graphically displaying these values in the Properties window.</span></span> <span data-ttu-id="a6e24-363">このカスタムコントロールは、 <xref:System.Drawing.Design.UITypeEditor> プロパティウィンドウと対話するためにによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-363">This custom control will be used by your <xref:System.Drawing.Design.UITypeEditor> to interact with the Properties window.</span></span>

### <a name="to-create-a-view-control-for-your-custom-ui-type-editor"></a><span data-ttu-id="a6e24-364">カスタム UI 型エディターのビューコントロールを作成するには</span><span class="sxs-lookup"><span data-stu-id="a6e24-364">To create a view control for your custom UI type editor</span></span>

1. <span data-ttu-id="a6e24-365">新しい項目を <xref:System.Windows.Forms.UserControl> プロジェクトに追加 `MarqueeControlLibrary` します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-365">Add a new <xref:System.Windows.Forms.UserControl> item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="a6e24-366">新しいソースファイルに **LightShapeSelectionControl** のベース名を指定します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-366">Give the new source file a base name of **LightShapeSelectionControl**.</span></span>

2. <span data-ttu-id="a6e24-367">ツールボックスからに2つのコントロールをドラッグし <xref:System.Windows.Forms.Panel>  `LightShapeSelectionControl` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-367">Drag two <xref:System.Windows.Forms.Panel> controls from the **Toolbox** onto the `LightShapeSelectionControl`.</span></span> <span data-ttu-id="a6e24-368">とという名前を指定し `squarePanel` `circlePanel` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-368">Name them `squarePanel` and `circlePanel`.</span></span> <span data-ttu-id="a6e24-369">それらを並べて配置します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-369">Arrange them side by side.</span></span> <span data-ttu-id="a6e24-370"><xref:System.Windows.Forms.Control.Size%2A>両方のコントロールのプロパティ <xref:System.Windows.Forms.Panel> を **(60, 60)** に設定します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-370">Set the <xref:System.Windows.Forms.Control.Size%2A> property of both <xref:System.Windows.Forms.Panel> controls to **(60, 60)**.</span></span> <span data-ttu-id="a6e24-371"><xref:System.Windows.Forms.Control.Location%2A>コントロールのプロパティ `squarePanel` を **(8, 10)** に設定します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-371">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the `squarePanel` control to **(8, 10)**.</span></span> <span data-ttu-id="a6e24-372"><xref:System.Windows.Forms.Control.Location%2A>コントロールのプロパティ `circlePanel` を **(80, 10)** に設定します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-372">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the `circlePanel` control to **(80, 10)**.</span></span> <span data-ttu-id="a6e24-373">最後に、 <xref:System.Windows.Forms.Control.Size%2A> のプロパティ `LightShapeSelectionControl` を **(150, 80)** に設定します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-373">Finally, set the <xref:System.Windows.Forms.Control.Size%2A> property of the `LightShapeSelectionControl` to **(150, 80)**.</span></span>

3. <span data-ttu-id="a6e24-374">`LightShapeSelectionControl`**コードエディター** でソースファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-374">Open the `LightShapeSelectionControl` source file in the **Code Editor**.</span></span> <span data-ttu-id="a6e24-375">ファイルの先頭に、名前空間をインポートし <xref:System.Windows.Forms.Design?displayProperty=nameWithType> ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-375">At the top of the file, import the <xref:System.Windows.Forms.Design?displayProperty=nameWithType> namespace:</span></span>

   ```vb
   Imports System.Windows.Forms.Design
   ```

   ```csharp
   using System.Windows.Forms.Design;
   ```

4. <span data-ttu-id="a6e24-376"><xref:System.Windows.Forms.Control.Click>コントロールとコントロールのイベントハンドラーを実装 `squarePanel` `circlePanel` します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-376">Implement <xref:System.Windows.Forms.Control.Click> event handlers for the `squarePanel` and `circlePanel` controls.</span></span> <span data-ttu-id="a6e24-377">これらのメソッド <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.CloseDropDown%2A> は、カスタム編集セッションを終了するためにを呼び出し <xref:System.Drawing.Design.UITypeEditor> ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-377">These methods invoke <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.CloseDropDown%2A> to end the custom <xref:System.Drawing.Design.UITypeEditor> editing session.</span></span>

    [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#390](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#390)]
    [!code-vb[System.Windows.Forms.Design.DocumentDesigner#390](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#390)]

5. <span data-ttu-id="a6e24-378"><xref:System.Windows.Forms.Design.IWindowsFormsEditorService>という名前のインスタンス変数を宣言 `editorService` します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-378">Declare an <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> instance variable called `editorService`.</span></span>

   ```vb
   Private editorService As IWindowsFormsEditorService
   ```

   ```csharp
   private IWindowsFormsEditorService editorService;
   ```

6. <span data-ttu-id="a6e24-379">`MarqueeLightShape`という名前のインスタンス変数を宣言 `lightShapeValue` します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-379">Declare a `MarqueeLightShape` instance variable called `lightShapeValue`.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#330](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#330)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#330](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#330)]

7. <span data-ttu-id="a6e24-380">コンストラクターで、 `LightShapeSelectionControl` <xref:System.Windows.Forms.Control.Click> イベントハンドラーをとコントロールのイベントにアタッチし `squarePanel` `circlePanel` <xref:System.Windows.Forms.Control.Click> ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-380">In the `LightShapeSelectionControl` constructor, attach the <xref:System.Windows.Forms.Control.Click> event handlers to the `squarePanel` and `circlePanel` controls' <xref:System.Windows.Forms.Control.Click> events.</span></span> <span data-ttu-id="a6e24-381">また、 `MarqueeLightShape` デザイン環境からフィールドに値を割り当てるコンストラクターのオーバーロードを定義し `lightShapeValue` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-381">Also, define a constructor overload that assigns the `MarqueeLightShape` value from the design environment to the `lightShapeValue` field.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#340](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#340)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#340](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#340)]

8. <span data-ttu-id="a6e24-382">メソッドで <xref:System.ComponentModel.Component.Dispose%2A> 、イベントハンドラーをデタッチし <xref:System.Windows.Forms.Control.Click> ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-382">In the <xref:System.ComponentModel.Component.Dispose%2A> method, detach the <xref:System.Windows.Forms.Control.Click> event handlers.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#350](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#350)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#350](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#350)]

9. <span data-ttu-id="a6e24-383">**ソリューション エクスプローラー** で、 **[すべてのファイルを表示]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e24-383">In **Solution Explorer**, click the **Show All Files** button.</span></span> <span data-ttu-id="a6e24-384">LightShapeSelectionControl.Designer.cs または LightShapeSelectionControl ファイルを開き、メソッドの既定の定義を削除し <xref:System.ComponentModel.Component.Dispose%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-384">Open the LightShapeSelectionControl.Designer.cs or LightShapeSelectionControl.Designer.vb file, and remove the default definition of the <xref:System.ComponentModel.Component.Dispose%2A> method.</span></span>

10. <span data-ttu-id="a6e24-385">`LightShape` プロパティを実装します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-385">Implement the `LightShape` property.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#360](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#360)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#360](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#360)]

11. <span data-ttu-id="a6e24-386"><xref:System.Windows.Forms.Control.OnPaint%2A> メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="a6e24-386">Override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="a6e24-387">この実装では、塗りつぶされた正方形と円を描画します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-387">This implementation will draw a filled square and circle.</span></span> <span data-ttu-id="a6e24-388">また、1つの図形の周りに境界線を描画して、選択された値を強調表示します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-388">It will also highlight the selected value by drawing a border around one shape or the other.</span></span>

     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#380](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#380)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#380](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#380)]

## <a name="test-your-custom-control-in-the-designer"></a><span data-ttu-id="a6e24-389">デザイナーでカスタムコントロールをテストする</span><span class="sxs-lookup"><span data-stu-id="a6e24-389">Test your Custom Control in the Designer</span></span>

<span data-ttu-id="a6e24-390">この時点で、プロジェクトをビルドでき `MarqueeControlLibrary` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-390">At this point, you can build the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="a6e24-391">クラスを継承し、フォームで使用するコントロールを作成して、実装をテスト `MarqueeControl` します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-391">Test your implementation by creating a control that inherits from the `MarqueeControl` class and using it on a form.</span></span>

### <a name="to-create-a-custom-marqueecontrol-implementation"></a><span data-ttu-id="a6e24-392">カスタムの MarqueeControl 実装を作成するには</span><span class="sxs-lookup"><span data-stu-id="a6e24-392">To create a custom MarqueeControl implementation</span></span>

1. <span data-ttu-id="a6e24-393">Windows フォーム デザイナーで `DemoMarqueeControl` を開きます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-393">Open `DemoMarqueeControl` in the Windows Forms Designer.</span></span> <span data-ttu-id="a6e24-394">これにより、型のインスタンスが作成さ `DemoMarqueeControl` れ、型のインスタンスに表示され `MarqueeControlRootDesigner` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-394">This creates an instance of the `DemoMarqueeControl` type and displays it in an instance of the `MarqueeControlRootDesigner` type.</span></span>

2. <span data-ttu-id="a6e24-395">**ツールボックス** で、[ **MarqueeControlLibrary Components** ] タブを開きます。`MarqueeBorder`選択できるコントロールとコントロールが表示され `MarqueeText` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-395">In the **Toolbox**, open the **MarqueeControlLibrary Components** tab. You will see the `MarqueeBorder` and `MarqueeText` controls available for selection.</span></span>

3. <span data-ttu-id="a6e24-396">コントロールのインスタンスを `MarqueeBorder` デザインサーフェイスにドラッグし `DemoMarqueeControl` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-396">Drag an instance of the `MarqueeBorder` control onto the `DemoMarqueeControl` design surface.</span></span> <span data-ttu-id="a6e24-397">この `MarqueeBorder` コントロールを親コントロールにドッキングします。</span><span class="sxs-lookup"><span data-stu-id="a6e24-397">Dock this `MarqueeBorder` control to the parent control.</span></span>

4. <span data-ttu-id="a6e24-398">コントロールのインスタンスを `MarqueeText` デザインサーフェイスにドラッグし `DemoMarqueeControl` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-398">Drag an instance of the `MarqueeText` control onto the `DemoMarqueeControl` design surface.</span></span>

5. <span data-ttu-id="a6e24-399">ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="a6e24-399">Build the solution.</span></span>

6. <span data-ttu-id="a6e24-400">を右クリックし、 `DemoMarqueeControl` ショートカットメニューの [ **テストの実行** ] オプションを選択してアニメーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-400">Right-click the `DemoMarqueeControl` and from the shortcut menu select the **Run Test** option to start the animation.</span></span> <span data-ttu-id="a6e24-401">アニメーションを停止するには、[ **テストの停止** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e24-401">Click **Stop Test** to stop the animation.</span></span>

7. <span data-ttu-id="a6e24-402">デザイン ビューで **[Form1]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-402">Open **Form1** in Design view.</span></span>

8. <span data-ttu-id="a6e24-403">フォームに2つの <xref:System.Windows.Forms.Button> コントロールを配置します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-403">Place two <xref:System.Windows.Forms.Button> controls on the form.</span></span> <span data-ttu-id="a6e24-404">それらに `startButton` とという名前を設定 `stopButton` し、 <xref:System.Windows.Forms.Control.Text%2A> プロパティ値をそれぞれ **Start** および **Stop** に変更します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-404">Name them `startButton` and `stopButton`, and change the <xref:System.Windows.Forms.Control.Text%2A> property values to **Start** and **Stop**, respectively.</span></span>

9. <span data-ttu-id="a6e24-405"><xref:System.Windows.Forms.Control.Click>両方のコントロールにイベントハンドラーを実装 <xref:System.Windows.Forms.Button> します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-405">Implement <xref:System.Windows.Forms.Control.Click> event handlers for both <xref:System.Windows.Forms.Button> controls.</span></span>

10. <span data-ttu-id="a6e24-406">**ツールボックス** で、[ **MarqueeControlTest Components** ] タブを開きます。選択できるが表示され `DemoMarqueeControl` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-406">In the **Toolbox**, open the **MarqueeControlTest Components** tab. You will see the `DemoMarqueeControl` available for selection.</span></span>

11. <span data-ttu-id="a6e24-407">のインスタンスを `DemoMarqueeControl` **Form1** デザインサーフェイスにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="a6e24-407">Drag an instance of `DemoMarqueeControl` onto the **Form1** design surface.</span></span>

12. <span data-ttu-id="a6e24-408"><xref:System.Windows.Forms.Control.Click>イベントハンドラーで、 `Start` `Stop` でメソッドとメソッドを呼び出し `DemoMarqueeControl` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-408">In the <xref:System.Windows.Forms.Control.Click> event handlers, invoke the `Start` and `Stop` methods on the `DemoMarqueeControl`.</span></span>

    ```vb
    Private Sub startButton_Click(sender As Object, e As System.EventArgs)
        Me.demoMarqueeControl1.Start()
    End Sub 'startButton_Click

    Private Sub stopButton_Click(sender As Object, e As System.EventArgs)
    Me.demoMarqueeControl1.Stop()
    End Sub 'stopButton_Click
    ```

    ```csharp
    private void startButton_Click(object sender, System.EventArgs e)
    {
        this.demoMarqueeControl1.Start();
    }

    private void stopButton_Click(object sender, System.EventArgs e)
    {
        this.demoMarqueeControl1.Stop();
    }
    ```

13. <span data-ttu-id="a6e24-409">プロジェクトを `MarqueeControlTest` スタートアッププロジェクトとして設定し、実行します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-409">Set the `MarqueeControlTest` project as the startup project and run it.</span></span> <span data-ttu-id="a6e24-410">というフォームが表示され `DemoMarqueeControl` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-410">You will see the form displaying your `DemoMarqueeControl`.</span></span> <span data-ttu-id="a6e24-411">[ **開始** ] ボタンを選択して、アニメーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-411">Select the **Start** button to start the animation.</span></span> <span data-ttu-id="a6e24-412">テキストが点滅し、ライトが境界内を移動していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-412">You should see the text flashing and the lights moving around the border.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a6e24-413">次のステップ</span><span class="sxs-lookup"><span data-stu-id="a6e24-413">Next steps</span></span>

<span data-ttu-id="a6e24-414">は、 `MarqueeControlLibrary` カスタムコントロールおよび関連するデザイナーの単純な実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="a6e24-414">The `MarqueeControlLibrary` demonstrates a simple implementation of custom controls and associated designers.</span></span> <span data-ttu-id="a6e24-415">このサンプルは、いくつかの方法でより高度なものにすることができます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-415">You can make this sample more sophisticated in several ways:</span></span>

- <span data-ttu-id="a6e24-416">デザイナーでのプロパティの値を変更し `DemoMarqueeControl` ます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-416">Change the property values for the `DemoMarqueeControl` in the designer.</span></span> <span data-ttu-id="a6e24-417">`MarqueBorder`コントロールを追加し、親インスタンス内にドッキングして、入れ子になった効果を作成します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-417">Add more `MarqueBorder` controls and dock them within their parent instances to create a nested effect.</span></span> <span data-ttu-id="a6e24-418">と light 関連のプロパティについて、さまざまな設定を試してみて `UpdatePeriod` ください。</span><span class="sxs-lookup"><span data-stu-id="a6e24-418">Experiment with different settings for the `UpdatePeriod` and the light-related properties.</span></span>

- <span data-ttu-id="a6e24-419">の独自の実装を作成 `IMarqueeWidget` します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-419">Author your own implementations of `IMarqueeWidget`.</span></span> <span data-ttu-id="a6e24-420">たとえば、点滅する "ネオンサイン" や、複数のイメージを使用したアニメーション化された記号を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-420">You could, for example, create a flashing "neon sign" or an animated sign with multiple images.</span></span>

- <span data-ttu-id="a6e24-421">デザイン時のエクスペリエンスをさらにカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="a6e24-421">Further customize the design-time experience.</span></span> <span data-ttu-id="a6e24-422">とより多くのプロパティをシャドウすることもでき <xref:System.Windows.Forms.Control.Enabled%2A> <xref:System.Windows.Forms.Control.Visible%2A> ます。また、新しいプロパティを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="a6e24-422">You could try shadowing more properties than <xref:System.Windows.Forms.Control.Enabled%2A> and <xref:System.Windows.Forms.Control.Visible%2A>, and you could add new properties.</span></span> <span data-ttu-id="a6e24-423">新しいデザイナー動詞を追加して、子コントロールのドッキングなどの一般的なタスクを簡略化します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-423">Add new designer verbs to simplify common tasks like docking child controls.</span></span>

- <span data-ttu-id="a6e24-424">をライセンス `MarqueeControl` します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-424">License the `MarqueeControl`.</span></span>

- <span data-ttu-id="a6e24-425">コントロールのシリアル化方法とコードの生成方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="a6e24-425">Control how your controls are serialized and how code is generated for them.</span></span> <span data-ttu-id="a6e24-426">詳細については、「 [動的なソースコードの生成とコンパイル](/dotnet/framework/reflection-and-codedom/dynamic-source-code-generation-and-compilation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6e24-426">For more information, see [Dynamic Source Code Generation and Compilation](/dotnet/framework/reflection-and-codedom/dynamic-source-code-generation-and-compilation).</span></span>

## <a name="see-also"></a><span data-ttu-id="a6e24-427">関連項目</span><span class="sxs-lookup"><span data-stu-id="a6e24-427">See also</span></span>

- <xref:System.Windows.Forms.UserControl>
- <xref:System.Windows.Forms.Design.ParentControlDesigner>
- <xref:System.Windows.Forms.Design.DocumentDesigner>
- <xref:System.ComponentModel.Design.IRootDesigner>
- <xref:System.ComponentModel.Design.DesignerVerb>
- <xref:System.Drawing.Design.UITypeEditor>
- <xref:System.ComponentModel.BackgroundWorker>
