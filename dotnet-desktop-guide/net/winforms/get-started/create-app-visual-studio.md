---
title: Visual Studio での新しいアプリの作成に関するチュートリアル
description: このチュートリアルでは、Visual Studio 2019 を使用して .NET 用の新しい Windows フォーム アプリを作成する方法について説明します。
ms.date: 10/26/2020
ms.topic: tutorial
dev_langs:
- csharp
- vb
ms.openlocfilehash: db0712aa642e54373f686fdd24a4747bf2d195e3
ms.sourcegitcommit: e8e3f6f23b5ddf9f5c4fe1ec5f6e0a8a609d49c8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "97004733"
---
# <a name="tutorial-create-a-new-winforms-app-windows-forms-net"></a><span data-ttu-id="bb95d-103">チュートリアル: 新しい WinForms アプリを作成する (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="bb95d-103">Tutorial: Create a new WinForms app (Windows Forms .NET)</span></span>

<span data-ttu-id="bb95d-104">この短いチュートリアルでは、Visual Studio で新しい Windows フォーム (WinForms) アプリを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bb95d-104">In this short tutorial, you'll learn how to create a new Windows Forms (WinForms) app with Visual Studio.</span></span> <span data-ttu-id="bb95d-105">最初のアプリが生成された後、コントロールを追加する方法と、イベントを処理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bb95d-105">Once the initial app has been generated, you'll learn how to add controls and how to handle events.</span></span> <span data-ttu-id="bb95d-106">このチュートリアルを終了すると、リスト ボックスに名前を追加する簡単なアプリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="bb95d-106">By the end of this tutorial, you'll have a simple app that adds names to a list box.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

<span data-ttu-id="bb95d-107">このチュートリアルでは、以下の内容を学習します。</span><span class="sxs-lookup"><span data-stu-id="bb95d-107">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="bb95d-108">新しい WinForms アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="bb95d-108">Create a new WinForms app</span></span>
> - <span data-ttu-id="bb95d-109">フォームにコントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="bb95d-109">Add controls to a form</span></span>
> - <span data-ttu-id="bb95d-110">コントロール イベントを処理してアプリの機能を提供する</span><span class="sxs-lookup"><span data-stu-id="bb95d-110">Handle control events to provide app functionality</span></span>
> - <span data-ttu-id="bb95d-111">アプリを実行する</span><span class="sxs-lookup"><span data-stu-id="bb95d-111">Run the app</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bb95d-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="bb95d-112">Prerequisites</span></span>

- [<span data-ttu-id="bb95d-113">Visual Studio 2019 バージョン 16.8 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="bb95d-113">Visual Studio 2019 version 16.8 or later versions</span></span>](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019+desktopguide+winforms)
  - <span data-ttu-id="bb95d-114">[Visual Studio デスクトップ ワークロード](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-workloads)を選択します</span><span class="sxs-lookup"><span data-stu-id="bb95d-114">Select the [Visual Studio Desktop workload](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-workloads)</span></span>
  - <span data-ttu-id="bb95d-115">[.NET 5 の個別のコンポーネント](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-individual-components)を選択します</span><span class="sxs-lookup"><span data-stu-id="bb95d-115">Select the [.NET 5 individual component](/visualstudio/install/modify-visual-studio?view=vs-2019&preserve-view=true#modify-individual-components)</span></span>

## <a name="create-a-winforms-app"></a><span data-ttu-id="bb95d-116">WinForms アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="bb95d-116">Create a WinForms app</span></span>

<span data-ttu-id="bb95d-117">新しいアプリを作成するための最初のステップは、Visual Studio を開き、テンプレートからアプリを生成することです。</span><span class="sxs-lookup"><span data-stu-id="bb95d-117">The first step to creating a new app is opening Visual Studio and generating the app from a template.</span></span>

01. <span data-ttu-id="bb95d-118">Visual Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="bb95d-118">Open Visual Studio.</span></span>
01. <span data-ttu-id="bb95d-119">**[新しいプロジェクトの作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bb95d-119">Select **Create a new project**.</span></span>

    :::image type="content" source="media/create-app-visual-studio/vs-create-new-project.png" alt-text="Visual Studio 2019 for .NET で新しい Windows フォーム プロジェクトを作成する":::

01. <span data-ttu-id="bb95d-121">**[テンプレートの検索]** ボックスに「**winforms**」と入力し、<kbd>Enter</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="bb95d-121">In the **Search for templates** box, type **winforms**, and then press <kbd>Enter</kbd>.</span></span>
01. <span data-ttu-id="bb95d-122">**[コード言語]** ドロップダウンで、 **[C#]** または **[Visual Basic]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bb95d-122">In the **code language** dropdown, choose **C#** or **Visual Basic**.</span></span>
01. <span data-ttu-id="bb95d-123">テンプレートの一覧で **Windows フォーム アプリ (.NET)** を選択し、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bb95d-123">In the templates list, select **Windows Forms App (.NET)** and then click **Next**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="bb95d-124">**Windows フォーム アプリ (.NET _Framework_)** テンプレートは選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="bb95d-124">Don't select the **Windows Forms App (.NET _Framework_)** template.</span></span>

    :::image type="content" source="media/create-app-visual-studio/vs-template-search.png" alt-text="Visual Studio 2019 for .NET で Windows フォーム テンプレートを検索する":::

01. <span data-ttu-id="bb95d-126">**[新しいプロジェクトの構成]** ウィンドウで、 **[プロジェクト名]** を「**Names**」に設定し、 **[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bb95d-126">In the **Configure your new project** window, set the **Project name** to **Names** and click **Create**.</span></span>

    <span data-ttu-id="bb95d-127">**[場所]** の設定を調整することで、プロジェクトを別のフォルダーに保存することもできます。</span><span class="sxs-lookup"><span data-stu-id="bb95d-127">You can also save your project to a different folder by adjusting the **Location** setting.</span></span>

    :::image type="content" source="media/create-app-visual-studio/vs-config-new-project.png" alt-text="Visual Studio 2019 for .NET で新しい Windows フォーム プロジェクトを構成する":::

<span data-ttu-id="bb95d-129">アプリが生成されると、Visual Studio のデザイナー ペインに既定のフォーム _Form1_ が開かれます。</span><span class="sxs-lookup"><span data-stu-id="bb95d-129">Once the app is generated, Visual Studio should open the designer pane for the default form, _Form1_.</span></span> <span data-ttu-id="bb95d-130">フォーム デザイナーが表示されない場合は、 **[ソリューション エクスプローラー]** ペインでフォームをダブルクリックして、デザイナー ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="bb95d-130">If the form designer isn't visible, double-click on the form in the **Solution Explorer** pane to open the designer window.</span></span>

### <a name="important-parts-of-visual-studio"></a><span data-ttu-id="bb95d-131">Visual Studio の重要な部分</span><span class="sxs-lookup"><span data-stu-id="bb95d-131">Important parts of Visual Studio</span></span>

<span data-ttu-id="bb95d-132">Visual Studio での WinForms のサポートには、アプリを作成するときに対話する 4 つの重要なコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="bb95d-132">Support for WinForms in Visual Studio has four important components that you'll interact with as you create an app:</span></span>

:::image type="content" source="media/create-app-visual-studio/vs-main-window.png" alt-text=".NET 用の Windows フォーム プロジェクトを作成するときに理解しておく必要のある Visual Studio の重要なコンポーネント":::

01. <span data-ttu-id="bb95d-134">ソリューション エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="bb95d-134">Solution Explorer</span></span>

    <span data-ttu-id="bb95d-135">プロジェクトのファイル、コード、フォーム、リソースのすべてがこのペインに表示されます。</span><span class="sxs-lookup"><span data-stu-id="bb95d-135">All if your project files, code, forms, resources, will appear in this pane.</span></span>

02. <span data-ttu-id="bb95d-136">Properties</span><span class="sxs-lookup"><span data-stu-id="bb95d-136">Properties</span></span>

    <span data-ttu-id="bb95d-137">このペインには、選択した項目に基づいて構成できるプロパティ設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bb95d-137">This pane shows property settings you can configure based on the item selected.</span></span> <span data-ttu-id="bb95d-138">たとえば、 **[ソリューション エクスプローラー]** から項目を選択した場合、そのファイルに関連するプロパティ設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bb95d-138">For example, if you select an item from **Solution Explorer**, you'll see property settings related to the file.</span></span> <span data-ttu-id="bb95d-139">**[デザイナー]** でオブジェクトを選択した場合は、コントロールまたはフォームの設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bb95d-139">If you select an object in the **Designer**, you'll see settings for the control or form.</span></span>

03. <span data-ttu-id="bb95d-140">フォーム デザイナー</span><span class="sxs-lookup"><span data-stu-id="bb95d-140">Form Designer</span></span>

    <span data-ttu-id="bb95d-141">これは、フォーム用のデザイナーです。</span><span class="sxs-lookup"><span data-stu-id="bb95d-141">This is the designer for the form.</span></span> <span data-ttu-id="bb95d-142">対話型であり、 **[ツールボックス]** からオブジェクトをドラッグ アンド ドロップすることができます。</span><span class="sxs-lookup"><span data-stu-id="bb95d-142">It's interactive and you can drag-and-drop objects from the **Toolbox**.</span></span> <span data-ttu-id="bb95d-143">デザイナーで項目を選択して移動することにより、アプリのユーザー インターフェイス (UI) を視覚的に作成できます。</span><span class="sxs-lookup"><span data-stu-id="bb95d-143">By selecting and moving items in the designer, you can visually compose the user interface (UI) for your app.</span></span>

04. <span data-ttu-id="bb95d-144">ツールボックス</span><span class="sxs-lookup"><span data-stu-id="bb95d-144">Toolbox</span></span>

    <span data-ttu-id="bb95d-145">ツールボックスには、フォームに追加できるすべてのコントロールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="bb95d-145">The toolbox contains all of the controls you can add to a form.</span></span> <span data-ttu-id="bb95d-146">現在のフォームにコントロールを追加するには、コントロールをダブルクリックするか、コントロールをドラッグ アンド ドロップします。</span><span class="sxs-lookup"><span data-stu-id="bb95d-146">To add a control to the current form, double-click a control or drag-and-drop the control.</span></span>

## <a name="add-controls-to-the-form"></a><span data-ttu-id="bb95d-147">コントロールをフォームに追加する</span><span class="sxs-lookup"><span data-stu-id="bb95d-147">Add controls to the form</span></span>

<span data-ttu-id="bb95d-148">_Form1_ のフォーム デザイナーを開いた状態で、 **[ツールボックス]** ペインを使用して、次のコントロールをフォームに追加します。</span><span class="sxs-lookup"><span data-stu-id="bb95d-148">With the _Form1_ form designer open, use the **Toolbox** pane to add the following controls to the form:</span></span>

- <span data-ttu-id="bb95d-149">ラベル</span><span class="sxs-lookup"><span data-stu-id="bb95d-149">Label</span></span>
- <span data-ttu-id="bb95d-150">Button</span><span class="sxs-lookup"><span data-stu-id="bb95d-150">Button</span></span>
- <span data-ttu-id="bb95d-151">Listbox</span><span class="sxs-lookup"><span data-stu-id="bb95d-151">Listbox</span></span>
- <span data-ttu-id="bb95d-152">テキストボックス</span><span class="sxs-lookup"><span data-stu-id="bb95d-152">Textbox</span></span>

<span data-ttu-id="bb95d-153">次の設定に従って、コントロールの位置とサイズを設定できます。</span><span class="sxs-lookup"><span data-stu-id="bb95d-153">You can position and size the controls according to the following settings.</span></span> <span data-ttu-id="bb95d-154">次に示すスクリーンショットと一致するように視覚的に動かすか、各コントロールをクリックして **[プロパティ]** ペインで設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="bb95d-154">Either visually move them to match the screenshot that follows, or click on each control and configure the settings in the **Properties** pane.</span></span> <span data-ttu-id="bb95d-155">フォームのタイトル領域をクリックして、フォームを選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="bb95d-155">You can also click on the form title area to select the form:</span></span>

| <span data-ttu-id="bb95d-156">Object</span><span class="sxs-lookup"><span data-stu-id="bb95d-156">Object</span></span>      | <span data-ttu-id="bb95d-157">設定</span><span class="sxs-lookup"><span data-stu-id="bb95d-157">Setting</span></span>  | <span data-ttu-id="bb95d-158">値</span><span class="sxs-lookup"><span data-stu-id="bb95d-158">Value</span></span>      |
|-------------|----------|------------|
| <span data-ttu-id="bb95d-159">**形式**</span><span class="sxs-lookup"><span data-stu-id="bb95d-159">**Form**</span></span>    | <span data-ttu-id="bb95d-160">Text</span><span class="sxs-lookup"><span data-stu-id="bb95d-160">Text</span></span>     | `Names`    |
|             | <span data-ttu-id="bb95d-161">サイズ</span><span class="sxs-lookup"><span data-stu-id="bb95d-161">Size</span></span>     | `268, 180` |
|             |          |            |
| <span data-ttu-id="bb95d-162">**Label**</span><span class="sxs-lookup"><span data-stu-id="bb95d-162">**Label**</span></span>   | <span data-ttu-id="bb95d-163">場所</span><span class="sxs-lookup"><span data-stu-id="bb95d-163">Location</span></span> | `12, 9`    |
|             | <span data-ttu-id="bb95d-164">Text</span><span class="sxs-lookup"><span data-stu-id="bb95d-164">Text</span></span>     | `Names`    |
|             |          |            |
| <span data-ttu-id="bb95d-165">**Listbox**</span><span class="sxs-lookup"><span data-stu-id="bb95d-165">**Listbox**</span></span> | <span data-ttu-id="bb95d-166">名前</span><span class="sxs-lookup"><span data-stu-id="bb95d-166">Name</span></span>     | `lstNames` |
|             | <span data-ttu-id="bb95d-167">場所</span><span class="sxs-lookup"><span data-stu-id="bb95d-167">Location</span></span> | `12, 27`   |
|             | <span data-ttu-id="bb95d-168">サイズ</span><span class="sxs-lookup"><span data-stu-id="bb95d-168">Size</span></span>     | `120, 94`  |
|             |          |            |
| <span data-ttu-id="bb95d-169">**テキスト ボックス**</span><span class="sxs-lookup"><span data-stu-id="bb95d-169">**Textbox**</span></span> | <span data-ttu-id="bb95d-170">名前</span><span class="sxs-lookup"><span data-stu-id="bb95d-170">Name</span></span>     | `txtName`  |
|             | <span data-ttu-id="bb95d-171">場所</span><span class="sxs-lookup"><span data-stu-id="bb95d-171">Location</span></span> | `138, 26`  |
|             | <span data-ttu-id="bb95d-172">サイズ</span><span class="sxs-lookup"><span data-stu-id="bb95d-172">Size</span></span>     | `100, 23`  |
|             |          |            |
| <span data-ttu-id="bb95d-173">**Button**</span><span class="sxs-lookup"><span data-stu-id="bb95d-173">**Button**</span></span>  | <span data-ttu-id="bb95d-174">名前</span><span class="sxs-lookup"><span data-stu-id="bb95d-174">Name</span></span>     | `btnAdd`   |
|             | <span data-ttu-id="bb95d-175">場所</span><span class="sxs-lookup"><span data-stu-id="bb95d-175">Location</span></span> | `138, 55`  |
|             | <span data-ttu-id="bb95d-176">サイズ</span><span class="sxs-lookup"><span data-stu-id="bb95d-176">Size</span></span>     | `100, 23`  |
|             | <span data-ttu-id="bb95d-177">Text</span><span class="sxs-lookup"><span data-stu-id="bb95d-177">Text</span></span>     | `Add Name` |

<span data-ttu-id="bb95d-178">次のようなフォームがデザイナーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="bb95d-178">You should have a form in the designer that looks similar to the following:</span></span>

:::image type="content" source="media/create-app-visual-studio/vs-form-preview.png" alt-text="Windows フォーム for .NET 用のフォームが開かれた Visual Studio 2019 デザイナー":::

## <a name="handle-events"></a><span data-ttu-id="bb95d-180">イベントを処理する</span><span class="sxs-lookup"><span data-stu-id="bb95d-180">Handle events</span></span>

<span data-ttu-id="bb95d-181">フォームへのすべてのコントロールのレイアウトが済んだので、コントロールのイベントを処理してユーザー入力に応答する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb95d-181">Now that the form has all of its controls laid out, you need to handle the events of the controls to respond to user input.</span></span> <span data-ttu-id="bb95d-182">フォーム デザイナーをまだ開いたままにして、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bb95d-182">With the form designer still open, perform the following steps:</span></span>

01. <span data-ttu-id="bb95d-183">フォーム上のボタン コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="bb95d-183">Select the button control on the form.</span></span>
01. **[プロパティ]** ペインでイベント アイコン :::image type="icon" source="media/create-app-visual-studio/icon-events.png" border="false"::: をクリックして、ボタンのイベントの一覧を表示します。
01. <span data-ttu-id="bb95d-185">**Click** イベントを見つけてダブルクリックし、イベント ハンドラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="bb95d-185">Find the **Click** event and double-click it to generate an event handler.</span></span>

    <span data-ttu-id="bb95d-186">この操作により、次のコードがフォームに追加されます。</span><span class="sxs-lookup"><span data-stu-id="bb95d-186">This action adds the following code to the the form:</span></span>

    ```csharp
    private void btnAdd_Click(object sender, EventArgs e)
    {

    }
    ```

    ```vb
    Private Sub btnAdd_Click(sender As Object, e As EventArgs) Handles btnAdd.Click

    End Sub
    ```

    <span data-ttu-id="bb95d-187">このハンドラーに作成するコードにより、`txtName` テキスト ボックス コントロールで指定された名前を、`lstNames` リスト ボックス コントロールに追加します。</span><span class="sxs-lookup"><span data-stu-id="bb95d-187">The code we'll put in this handler will add the name specified by the `txtName` textbox control to the `lstNames` listbox control.</span></span> <span data-ttu-id="bb95d-188">ただし、名前の追加に 2 つの条件を設けます。指定された名前が空白であってはならず、名前が既に存在していてはなりません。</span><span class="sxs-lookup"><span data-stu-id="bb95d-188">However, we want there to be two conditions to adding the name: the name provided must not be blank, and the name must not already exist.</span></span>

01. <span data-ttu-id="bb95d-189">次のコードでは、名前を `lstNames` コントロールに追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bb95d-189">The following code demonstrates adding a name to the `lstNames` control:</span></span>

    ```csharp
    private void btnAdd_Click(object sender, EventArgs e)
    {
        if (!string.IsNullOrWhiteSpace(txtName.Text) && !lstNames.Items.Contains(txtName.Text))
            lstNames.Items.Add(txtName.Text);
    }
    ```

    ```vb
    Private Sub btnAdd_Click(sender As Object, e As EventArgs) Handles btnAdd.Click
        If Not String.IsNullOrWhiteSpace(txtName.Text) And Not lstNames.Items.Contains(txtName.Text) Then
            lstNames.Items.Add(txtName.Text)
        End If
    End Sub
    ```

## <a name="run-the-app"></a><span data-ttu-id="bb95d-190">アプリを実行する</span><span class="sxs-lookup"><span data-stu-id="bb95d-190">Run the app</span></span>

<span data-ttu-id="bb95d-191">イベントをコーディングしたので、<kbd>F5</kbd> キーを押すか、メニューから **[デバッグ]**  >  **[デバッグの開始]** を選択して、アプリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="bb95d-191">Now that the event has been coded, you can run the app by pressing the <kbd>F5</kbd> key or by selecting **Debug** > **Start Debugging** from the menu.</span></span> <span data-ttu-id="bb95d-192">フォームが表示され、テキスト ボックスに名前を入力し、ボタンをクリックすることによってそれを追加できます。</span><span class="sxs-lookup"><span data-stu-id="bb95d-192">The form displays and you can enter a name in the textbox and then add it by clicking the button.</span></span>

:::image type="content" source="media/create-app-visual-studio/app-running.png" alt-text="Windows フォーム for .NET アプリの実行。":::

## <a name="next-steps"></a><span data-ttu-id="bb95d-194">次のステップ</span><span class="sxs-lookup"><span data-stu-id="bb95d-194">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="bb95d-195">Windows フォームの詳細を学習する</span><span class="sxs-lookup"><span data-stu-id="bb95d-195">Learn more about Windows Forms</span></span>](../overview/index.md)
