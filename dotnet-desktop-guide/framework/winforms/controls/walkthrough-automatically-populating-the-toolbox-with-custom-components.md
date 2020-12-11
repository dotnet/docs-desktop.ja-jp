---
title: 'チュートリアル: ツールボックスへのカスタム コンポーネントの自動設定'
ms.date: 03/30/2017
helpviewer_keywords:
- IToolboxService interface
- Toolbox [Windows Forms], populating
- custom components [Windows Forms], adding to Toolbox
ms.assetid: 2fa1e3e8-6b9f-42b2-97c0-2be57444dba4
ms.openlocfilehash: 3ceebbf07c0241996479a6f7f72ab19f4cd9aa05
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982887"
---
# <a name="walkthrough-automatically-populating-the-toolbox-with-custom-components"></a><span data-ttu-id="f409b-102">チュートリアル: ツールボックスへのカスタム コンポーネントの自動設定</span><span class="sxs-lookup"><span data-stu-id="f409b-102">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>

<span data-ttu-id="f409b-103">現在開いているソリューションのプロジェクトによってコンポーネントが定義されている場合は、自動的に **ツールボックス** に表示され、ユーザーによる操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="f409b-103">If your components are defined by a project in the currently open solution, they will automatically appear in the **Toolbox**, with no action required by you.</span></span> <span data-ttu-id="f409b-104">[[ツールボックスアイテムの選択] ダイアログボックス (Visual Studio)](/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))を使用してカスタムコンポーネントを **ツールボックス** に手動で設定することもできますが、**ツールボックス** では、ソリューションのビルド出力に含まれるアイテムのうち、次のすべての特性を使用します。</span><span class="sxs-lookup"><span data-stu-id="f409b-104">You can also manually populate the **Toolbox** with your custom components by using the [Choose Toolbox Items Dialog Box (Visual Studio)](/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100)), but the **Toolbox** takes account of items in your solution's build outputs with all the following characteristics:</span></span>

- <span data-ttu-id="f409b-105">を実装し <xref:System.ComponentModel.IComponent> ます。</span><span class="sxs-lookup"><span data-stu-id="f409b-105">Implements <xref:System.ComponentModel.IComponent>;</span></span>

- <span data-ttu-id="f409b-106">がに設定されていません <xref:System.ComponentModel.ToolboxItemAttribute> `false` 。</span><span class="sxs-lookup"><span data-stu-id="f409b-106">Does not have <xref:System.ComponentModel.ToolboxItemAttribute> set to `false`;</span></span>

- <span data-ttu-id="f409b-107">がに設定されていません <xref:System.ComponentModel.DesignTimeVisibleAttribute> `false` 。</span><span class="sxs-lookup"><span data-stu-id="f409b-107">Does not have <xref:System.ComponentModel.DesignTimeVisibleAttribute> set to `false`.</span></span>

> [!NOTE]
> <span data-ttu-id="f409b-108">**ツールボックス** は参照チェーンに従っていないので、ソリューション内のプロジェクトでビルドされていない項目は表示されません。</span><span class="sxs-lookup"><span data-stu-id="f409b-108">The **Toolbox** does not follow reference chains, so it won't display items that are not built by a project in your solution.</span></span>

<span data-ttu-id="f409b-109">このチュートリアルでは、コンポーネントがビルドされた後に、 **ツールボックス** にカスタムコンポーネントを自動的に表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f409b-109">This walkthrough demonstrates how a custom component automatically appears in the **Toolbox** once the component is built.</span></span> <span data-ttu-id="f409b-110">このチュートリアルでは、以下のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="f409b-110">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="f409b-111">Windows フォームプロジェクトを作成しています。</span><span class="sxs-lookup"><span data-stu-id="f409b-111">Creating a Windows Forms project.</span></span>

- <span data-ttu-id="f409b-112">カスタムコンポーネントを作成しています。</span><span class="sxs-lookup"><span data-stu-id="f409b-112">Creating a custom component.</span></span>

- <span data-ttu-id="f409b-113">カスタムコンポーネントのインスタンスを作成する。</span><span class="sxs-lookup"><span data-stu-id="f409b-113">Creating an instance of a custom component.</span></span>

- <span data-ttu-id="f409b-114">カスタムコンポーネントのアンロードと再読み込み。</span><span class="sxs-lookup"><span data-stu-id="f409b-114">Unloading and reloading a custom component.</span></span>

<span data-ttu-id="f409b-115">完了すると、作成したコンポーネントが **ツールボックス** に設定されていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="f409b-115">When you are finished, you will see that the **Toolbox** is populated with a component that you have created.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="f409b-116">プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="f409b-116">Create the project</span></span>

1. <span data-ttu-id="f409b-117">Visual Studio で、という名前の Windows ベースのアプリケーションプロジェクトを作成 `ToolboxExample` します ([**ファイル**] [  >  **新しい**  >  **プロジェクト**] [  >  **Visual C#** ] または [ **Visual Basic**  >  **クラシックデスクトップ**  >  **Windows フォームアプリケーション**])。</span><span class="sxs-lookup"><span data-stu-id="f409b-117">In Visual Studio, create a Windows-based application project called `ToolboxExample` (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="f409b-118">新しいコンポーネントをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="f409b-118">Add a new component to the project.</span></span> <span data-ttu-id="f409b-119">このプロジェクトに `DemoComponent`という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="f409b-119">Call it `DemoComponent`.</span></span>

     <span data-ttu-id="f409b-120">詳細については、「 [方法: 新しいプロジェクト項目を追加する](/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f409b-120">For more information, see [How to: Add New Project Items](/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100)).</span></span>

3. <span data-ttu-id="f409b-121">プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="f409b-121">Build the project.</span></span>

4. <span data-ttu-id="f409b-122">[ **ツール** ] メニューの [ **オプション** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f409b-122">From the **Tools** menu, click the **Options** item.</span></span> <span data-ttu-id="f409b-123">**Windows フォームデザイナー** 項目の下にある [**全般**] をクリックし、 **AutoToolboxPopulate** オプションが **True** に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f409b-123">Click **General** under the **Windows Forms Designer** item and ensure that the **AutoToolboxPopulate** option is set to **True**.</span></span>

## <a name="create-an-instance-of-a-custom-component"></a><span data-ttu-id="f409b-124">カスタムコンポーネントのインスタンスを作成する</span><span class="sxs-lookup"><span data-stu-id="f409b-124">Create an instance of a custom component</span></span>

<span data-ttu-id="f409b-125">次の手順では、フォームにカスタムコンポーネントのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="f409b-125">The next step is to create an instance of the custom component on the form.</span></span> <span data-ttu-id="f409b-126">**ツールボックス** は新しいコンポーネントのアカウントを自動的に作成するので、他のコンポーネントやコントロールを作成するのと同じように簡単です。</span><span class="sxs-lookup"><span data-stu-id="f409b-126">Because the **Toolbox** automatically accounts for the new component, this is as easy as creating any other component or control.</span></span>

1. <span data-ttu-id="f409b-127">**フォームデザイナー** でプロジェクトのフォームを開きます。</span><span class="sxs-lookup"><span data-stu-id="f409b-127">Open the project's form in the **Forms Designer**.</span></span>

2. <span data-ttu-id="f409b-128">**ツールボックス** で、[ **ToolboxExample Components**] という名前の新しいタブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f409b-128">In the **Toolbox**, click the new tab called **ToolboxExample Components**.</span></span>

     <span data-ttu-id="f409b-129">タブをクリックすると、 **Democomponent** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f409b-129">Once you click the tab, you will see **DemoComponent**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f409b-130">パフォーマンス上の理由から、 **ツールボックス** の自動設定された領域のコンポーネントにはカスタムビットマップが表示されず、 <xref:System.Drawing.ToolboxBitmapAttribute> はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f409b-130">For performance reasons, components in the auto-populated area of the **Toolbox** do not display custom bitmaps, and the <xref:System.Drawing.ToolboxBitmapAttribute> is not supported.</span></span> <span data-ttu-id="f409b-131">**ツール** ボックスにカスタムコンポーネントのアイコンを表示するには、 **[ツールボックスアイテムの選択**] ダイアログボックスを使用してコンポーネントを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="f409b-131">To display an icon for a custom component in the **Toolbox**, use the **Choose Toolbox Items** dialog box to load your component.</span></span>

3. <span data-ttu-id="f409b-132">コンポーネントをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="f409b-132">Drag your component onto your form.</span></span>

     <span data-ttu-id="f409b-133">コンポーネントのインスタンスが作成され、 **コンポーネントトレイ** に追加されます。</span><span class="sxs-lookup"><span data-stu-id="f409b-133">An instance of the component is created and added to the **Component Tray**.</span></span>

## <a name="unload-and-reload-a-custom-component"></a><span data-ttu-id="f409b-134">カスタムコンポーネントのアンロードと再読み込み</span><span class="sxs-lookup"><span data-stu-id="f409b-134">Unload and reload a custom component</span></span>

<span data-ttu-id="f409b-135">**ツールボックス** は、読み込まれた各プロジェクトのコンポーネントを考慮し、プロジェクトがアンロードされるときに、プロジェクトのコンポーネントへの参照を削除します。</span><span class="sxs-lookup"><span data-stu-id="f409b-135">The **Toolbox** takes account of the components in each loaded project, and when a project is unloaded, it removes references to the project's components.</span></span>

1. <span data-ttu-id="f409b-136">ソリューションからプロジェクトをアンロードします。</span><span class="sxs-lookup"><span data-stu-id="f409b-136">Unload the project from the solution.</span></span>

     <span data-ttu-id="f409b-137">プロジェクトのアンロードの詳細については、「 [方法: プロジェクトのアンロードと再読み込み](/previous-versions/visualstudio/visual-studio-2010/tt479x1t(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f409b-137">For more information about unloading projects, see [How to: Unload and Reload Projects](/previous-versions/visualstudio/visual-studio-2010/tt479x1t(v=vs.100)).</span></span> <span data-ttu-id="f409b-138">保存を確認するメッセージが表示されたら、[ **はい]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f409b-138">If you are prompted to save, choose **Yes**.</span></span>

2. <span data-ttu-id="f409b-139">新しい **Windows アプリケーション** プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="f409b-139">Add a new **Windows Application** project to the solution.</span></span> <span data-ttu-id="f409b-140">**デザイナー** でフォームを開きます。</span><span class="sxs-lookup"><span data-stu-id="f409b-140">Open the form in the **Designer**.</span></span>

     <span data-ttu-id="f409b-141">前のプロジェクトの [ **ToolboxExample Components** ] タブが消えました。</span><span class="sxs-lookup"><span data-stu-id="f409b-141">The **ToolboxExample Components** tab from the previous project is now gone.</span></span>

3. <span data-ttu-id="f409b-142">プロジェクトを再度読み込み `ToolboxExample` ます。</span><span class="sxs-lookup"><span data-stu-id="f409b-142">Reload the `ToolboxExample` project.</span></span>

     <span data-ttu-id="f409b-143">[ **ToolboxExample Components** ] タブが表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f409b-143">The **ToolboxExample Components** tab now reappears.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f409b-144">次のステップ</span><span class="sxs-lookup"><span data-stu-id="f409b-144">Next steps</span></span>

<span data-ttu-id="f409b-145">このチュートリアルでは、 **ツールボックス** がプロジェクトのコンポーネントを考慮していることを示しますが、 **ツールボックス** もコントロールを考慮します。</span><span class="sxs-lookup"><span data-stu-id="f409b-145">This walkthrough demonstrates that the **Toolbox** takes account of a project's components, but the **Toolbox** is also takes account of controls.</span></span> <span data-ttu-id="f409b-146">ソリューションからコントロールプロジェクトを追加したり削除したりして、独自のカスタムコントロールを試してみてください。</span><span class="sxs-lookup"><span data-stu-id="f409b-146">Experiment with your own custom controls by adding and removing control projects from your solution.</span></span>

## <a name="see-also"></a><span data-ttu-id="f409b-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="f409b-147">See also</span></span>

- <span data-ttu-id="f409b-148">[[全般] ([オプション] ダイアログ ボックス - [Windows フォーム デザイナー])](/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f409b-148">[General, Windows Forms Designer, Options Dialog Box](/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))</span></span>
- <span data-ttu-id="f409b-149">[方法: [ツールボックス] タブの操作](/previous-versions/visualstudio/visual-studio-2010/66kwe227(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f409b-149">[How to: Manipulate Toolbox Tabs](/previous-versions/visualstudio/visual-studio-2010/66kwe227(v=vs.100))</span></span>
- <span data-ttu-id="f409b-150">[[ツールボックス アイテムの選択] ダイアログ ボックス (Visual Studio)](/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f409b-150">[Choose Toolbox Items Dialog Box (Visual Studio)](/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))</span></span>
- [<span data-ttu-id="f409b-151">Windows フォームへのコントロールの追加</span><span class="sxs-lookup"><span data-stu-id="f409b-151">Putting Controls on Windows Forms</span></span>](putting-controls-on-windows-forms.md)
