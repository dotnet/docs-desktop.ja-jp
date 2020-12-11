---
title: '方法: 複合コントロールを作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- UserControl class [Windows Forms], creating composite controls
- user controls [Windows Forms], creating
- user controls [Windows Forms], inheriting from
- composite controls [Windows Forms], creating
ms.assetid: 79c9cf05-5ab6-4a18-886d-88a64748b098
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 42ea424507b89576df8099fd4849dd2665135a55
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982588"
---
# <a name="how-to-author-composite-controls"></a><span data-ttu-id="6e5a3-102">方法: 複合コントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="6e5a3-102">How to: Author composite controls</span></span>

<span data-ttu-id="6e5a3-103">複合コントロールはさまざまな方法で使用できます。</span><span class="sxs-lookup"><span data-stu-id="6e5a3-103">Composite controls can be employed in many ways.</span></span> <span data-ttu-id="6e5a3-104">Windows デスクトップ アプリケーション プロジェクトの一部として複合コントロールを作成し、プロジェクト内のフォーム上でのみ使用することができます。</span><span class="sxs-lookup"><span data-stu-id="6e5a3-104">You can author them as part of a Windows desktop application project, and use them only on forms in the project.</span></span> <span data-ttu-id="6e5a3-105">または、Windows コントロール ライブラリ プロジェクトで複合コントロールを作成し、プロジェクトをアセンブリにコンパイルして、他のプロジェクトで使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="6e5a3-105">Or you can author them in a Windows Control Library project, compile the project into an assembly, and use the controls in other projects.</span></span> <span data-ttu-id="6e5a3-106">また、それらを継承し、ビジュアル継承を使用して、特殊な目的ですばやくカスタマイズすることもできます。</span><span class="sxs-lookup"><span data-stu-id="6e5a3-106">You can even inherit from them and use visual inheritance to customize them quickly for special purposes.</span></span>

## <a name="to-author-a-composite-control"></a><span data-ttu-id="6e5a3-107">複合コントロールを作成するには</span><span class="sxs-lookup"><span data-stu-id="6e5a3-107">To author a composite control</span></span>

1. <span data-ttu-id="6e5a3-108">Visual Studio で、新しい **Windows アプリケーション** プロジェクトを作成し、 **democontrolhost** という名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6e5a3-108">In Visual Studio, create a new **Windows Application** project, and name it **DemoControlHost**.</span></span>

2. <span data-ttu-id="6e5a3-109">**[プロジェクト]** メニューの **[ユーザー コントロールの追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e5a3-109">On the **Project** menu, click **Add User Control**.</span></span>

3. <span data-ttu-id="6e5a3-110">**[新しい項目の追加]** ダイアログ ボックスで、クラス ファイル (.vb または .cs ファイル) に複合コントロールに付ける名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6e5a3-110">In the **Add New Item** dialog box, give the class file (.vb or .cs file) the name you want the composite control to have.</span></span>

4. <span data-ttu-id="6e5a3-111">[ **追加** ] ボタンを選択して、複合コントロールのクラスファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e5a3-111">Select the **Add** button to create the class file for the composite control.</span></span>

5. <span data-ttu-id="6e5a3-112">複合コントロールのサーフェスに **[ツールボックス]** からコントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="6e5a3-112">Add controls from the **Toolbox** to the composite control surface.</span></span>

6. <span data-ttu-id="6e5a3-113">複合コントロールまたはその内在コントロールによって発生したイベントを処理するために、イベント プロシージャにコードを配置します。</span><span class="sxs-lookup"><span data-stu-id="6e5a3-113">Place code in event procedures, to handle events raised by the composite control or by its constituent controls.</span></span>

7. <span data-ttu-id="6e5a3-114">複合コントロールのデザイナーを閉じて、メッセージが表示されたらファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="6e5a3-114">Close the designer for the composite control, and save the file when you are prompted.</span></span>

8. <span data-ttu-id="6e5a3-115">**[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e5a3-115">On the **Build** menu, click **Build Solution**.</span></span>

     <span data-ttu-id="6e5a3-116">カスタム コントロールが **[ツールボックス]** に表示されるようにプロジェクトをビルドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e5a3-116">The project must be built in order for custom controls to appear in the **Toolbox**.</span></span>

9. <span data-ttu-id="6e5a3-117">**[ツールボックス]** の **[DemoControlHost]** タブを使用して、コントロールのインスタンスを `Form1` に追加します。</span><span class="sxs-lookup"><span data-stu-id="6e5a3-117">Use the **DemoControlHost** tab of the **Toolbox** to add instances of your control to `Form1`.</span></span>

## <a name="to-author-a-control-class-library"></a><span data-ttu-id="6e5a3-118">コントロール クラス ライブラリを作成するには</span><span class="sxs-lookup"><span data-stu-id="6e5a3-118">To author a control class library</span></span>

1. <span data-ttu-id="6e5a3-119">新しい **Windows コントロール ライブラリ** プロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="6e5a3-119">Open a new **Windows Control Library** project.</span></span>

     <span data-ttu-id="6e5a3-120">既定では、プロジェクトに複合コントロールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6e5a3-120">By default, the project contains a composite control.</span></span>

2. <span data-ttu-id="6e5a3-121">上記の手順の説明に従ってコントロールとコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="6e5a3-121">Add controls and code as described in the procedure above.</span></span>

3. <span data-ttu-id="6e5a3-122">継承クラスで変更しないコントロールを選択して、このコントロールの **Modifiers** プロパティを **Private** に設定します。</span><span class="sxs-lookup"><span data-stu-id="6e5a3-122">Choose a control you do not want inheriting classes to change, and set the **Modifiers** property of this control to **Private**.</span></span>

4. <span data-ttu-id="6e5a3-123">DLL をビルドします。</span><span class="sxs-lookup"><span data-stu-id="6e5a3-123">Build the DLL.</span></span>

## <a name="to-inherit-from-a-composite-control-in-a-control-class-library"></a><span data-ttu-id="6e5a3-124">コントロール クラス ライブラリの複合コントロールから継承するには</span><span class="sxs-lookup"><span data-stu-id="6e5a3-124">To inherit from a composite control in a control class library</span></span>

1. <span data-ttu-id="6e5a3-125">**[ファイル]** メニューで、**[追加]** をポイントし、**[新しいプロジェクト]** を選択して、新しい **Windows アプリケーション** プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="6e5a3-125">On the **File** menu, point to **Add** and select **New Project** to add a new **Windows Application** project to the solution.</span></span>

2. <span data-ttu-id="6e5a3-126">**ソリューション エクスプローラー** で、新しいプロジェクトの **[参照設定]** フォルダーを右クリックし、**[参照の追加]** をクリックして **[参照の追加]** ダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="6e5a3-126">In **Solution Explorer**, right-click the **References** folder for the new project and choose **Add Reference** to open the **Add Reference** dialog box.</span></span>

3. <span data-ttu-id="6e5a3-127">**[プロジェクト]** タブを選択し、コントロール ライブラリ プロジェクトをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e5a3-127">Select the **Projects** tab and double-click your control library project.</span></span>

4. <span data-ttu-id="6e5a3-128">**[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e5a3-128">On the **Build** menu, click **Build Solution**.</span></span>

5. <span data-ttu-id="6e5a3-129">**ソリューション エクスプローラー** で、コントロール ライブラリ プロジェクトを右クリックし、ショートカット メニューの **[新しい項目の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e5a3-129">In **Solution Explorer**, right-click your control library project and select **Add New Item** from the shortcut menu.</span></span>

6. <span data-ttu-id="6e5a3-130">**[新しい項目の追加]** ダイアログ ボックスの **[継承されたユーザー コントロール]** テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="6e5a3-130">Select the **Inherited User Control** template from the **Add New Item** dialog box.</span></span>

7. <span data-ttu-id="6e5a3-131">**[継承ピッカー]** ダイアログ ボックスで、継承元のコントロールをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e5a3-131">In the **Inheritance Picker** dialog box, double-click the control you want to inherit from.</span></span>

     <span data-ttu-id="6e5a3-132">新しいコントロールがプロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="6e5a3-132">A new control is added to your project.</span></span>

8. <span data-ttu-id="6e5a3-133">新しいコントロールのビジュアル デザイナーを開き、別の内在コントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="6e5a3-133">Open the visual designer for the new control and add additional constituent controls.</span></span>

     <span data-ttu-id="6e5a3-134">DLL の複合コントロールから継承された内在コントロールを表示し、**Modifiers** プロパティが **Public** であるコントロールのプロパティを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="6e5a3-134">You can see the constituent controls that were inherited from the composite control in your DLL, and you can alter the properties of controls whose **Modifiers** property is **Public**.</span></span> <span data-ttu-id="6e5a3-135">**Modifiers** プロパティが **Private** であるコントロールのプロパティを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="6e5a3-135">You cannot change the properties of the control whose **Modifiers** property is **Private**.</span></span>

## <a name="see-also"></a><span data-ttu-id="6e5a3-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e5a3-136">See also</span></span>

- [<span data-ttu-id="6e5a3-137">チュートリアル: 複合コントロールの作成</span><span class="sxs-lookup"><span data-stu-id="6e5a3-137">Walkthrough: Authoring a Composite Control</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)
- [<span data-ttu-id="6e5a3-138">チュートリアル: Windows フォームコントロールからの継承</span><span class="sxs-lookup"><span data-stu-id="6e5a3-138">Walkthrough: Inheriting from a Windows Forms Control</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
- [<span data-ttu-id="6e5a3-139">コントロールの種類に関するアドバイス</span><span class="sxs-lookup"><span data-stu-id="6e5a3-139">Control Type Recommendations</span></span>](control-type-recommendations.md)
- [<span data-ttu-id="6e5a3-140">方法: Windows フォームのコントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="6e5a3-140">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)
- [<span data-ttu-id="6e5a3-141">さまざまなカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="6e5a3-141">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
