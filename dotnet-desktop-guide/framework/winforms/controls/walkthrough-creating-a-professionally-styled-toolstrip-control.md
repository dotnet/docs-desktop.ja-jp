---
title: 'チュートリアル: プロフェッショナル スタイルの ToolStrip コントロールの作成'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStripRenderer class [Windows Forms]
- toolbars [Windows Forms], walkthroughs
- ToolStrip control [Windows Forms], creating professionally styled controls
ms.assetid: b52339ae-f1d3-494e-996e-eb455614098a
ms.openlocfilehash: 3fd9175f47f9f1b35743dc69b462227fdfafe55d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983444"
---
# <a name="walkthrough-creating-a-professionally-styled-toolstrip-control"></a><span data-ttu-id="902c5-102">チュートリアル: プロフェッショナル スタイルの ToolStrip コントロールの作成</span><span class="sxs-lookup"><span data-stu-id="902c5-102">Walkthrough: Creating a Professionally Styled ToolStrip Control</span></span>

<span data-ttu-id="902c5-103">型から派生した独自のクラスを記述することにより、アプリケーションの <xref:System.Windows.Forms.ToolStrip> コントロールに洗練された外観と動作を与えることができ <xref:System.Windows.Forms.ToolStripProfessionalRenderer> ます。</span><span class="sxs-lookup"><span data-stu-id="902c5-103">You can give your application’s <xref:System.Windows.Forms.ToolStrip> controls a professional appearance and behavior by writing your own class derived from the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> type.</span></span>

<span data-ttu-id="902c5-104">このチュートリアルでは、コントロールを使用して、 <xref:System.Windows.Forms.ToolStrip> Microsoft® Outlook®によって提供される **ナビゲーションウィンドウ** に似た複合コントロールを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="902c5-104">This walkthrough demonstrates how to use <xref:System.Windows.Forms.ToolStrip> controls to create a composite control that resembles the **Navigation Pane** provided by Microsoft® Outlook®.</span></span> <span data-ttu-id="902c5-105">このチュートリアルでは、次のタスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="902c5-105">The following tasks are illustrated in this walkthrough:</span></span>

- <span data-ttu-id="902c5-106">Windows コントロールライブラリプロジェクトを作成しています。</span><span class="sxs-lookup"><span data-stu-id="902c5-106">Creating a Windows Control Library project.</span></span>

- <span data-ttu-id="902c5-107">StackView コントロールのデザイン。</span><span class="sxs-lookup"><span data-stu-id="902c5-107">Designing the StackView Control.</span></span>

- <span data-ttu-id="902c5-108">カスタムレンダラーを実装する。</span><span class="sxs-lookup"><span data-stu-id="902c5-108">Implementing a Custom Renderer.</span></span>

<span data-ttu-id="902c5-109">完了すると、Microsoft Office® XP コントロールの洗練された外観で、再利用可能なカスタムクライアントコントロールを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="902c5-109">When you are finished, you will have a reusable custom client control with the professional appearance of a Microsoft Office® XP control.</span></span>

<span data-ttu-id="902c5-110">このトピックのコードを単一のリストとしてコピーする方法については、「 [方法: プロフェッショナルスタイルの ToolStrip コントロールを作成](how-to-create-a-professionally-styled-toolstrip-control.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="902c5-110">To copy the code in this topic as a single listing, see [How to: Create a Professionally Styled ToolStrip Control](how-to-create-a-professionally-styled-toolstrip-control.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="902c5-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="902c5-111">Prerequisites</span></span>

<span data-ttu-id="902c5-112">このチュートリアルを完了するには、Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="902c5-112">You'll need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-control-library-project"></a><span data-ttu-id="902c5-113">コントロールライブラリプロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="902c5-113">Create the control library project</span></span>

1. <span data-ttu-id="902c5-114">Visual Studio で、という名前の新しい Windows コントロールライブラリプロジェクトを作成 `StackViewLibrary` します。</span><span class="sxs-lookup"><span data-stu-id="902c5-114">In Visual Studio, create a new Windows Control Library project named `StackViewLibrary`.</span></span>

2. <span data-ttu-id="902c5-115">**ソリューションエクスプローラー** で、選択した言語に応じて、"UserControl1.cs" または "UserControl1" という名前のソースファイルを削除して、プロジェクトの既定のコントロールを削除します。</span><span class="sxs-lookup"><span data-stu-id="902c5-115">In **Solution Explorer**, delete the project's default control by deleting the source file named "UserControl1.cs" or "UserControl1.vb", depending on your language of choice.</span></span>

     <span data-ttu-id="902c5-116">詳細については、「 [方法: 項目を削除、削除、および除外する](/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="902c5-116">For more information, see [How to: Remove, Delete, and Exclude Items](/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100)).</span></span>

3. <span data-ttu-id="902c5-117"><xref:System.Windows.Forms.UserControl> **Stackviewlibrary** プロジェクトに新しい項目を追加します。</span><span class="sxs-lookup"><span data-stu-id="902c5-117">Add a new <xref:System.Windows.Forms.UserControl> item to the **StackViewLibrary** project.</span></span> <span data-ttu-id="902c5-118">新しいソースファイルにのベース名を指定 `StackView` します。</span><span class="sxs-lookup"><span data-stu-id="902c5-118">Give the new source file a base name of `StackView`.</span></span>

## <a name="design-the-stackview-control"></a><span data-ttu-id="902c5-119">StackView コントロールのデザイン</span><span class="sxs-lookup"><span data-stu-id="902c5-119">Design the StackView control</span></span>

<span data-ttu-id="902c5-120">コントロールは、 `StackView` 1 つの子コントロールを持つ複合コントロールです <xref:System.Windows.Forms.ToolStrip> 。</span><span class="sxs-lookup"><span data-stu-id="902c5-120">The `StackView` control is a composite control with one child <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="902c5-121">複合コントロールの詳細については、「 [カスタムコントロールの種類](varieties-of-custom-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="902c5-121">For more information about composite controls, see [Varieties of Custom Controls](varieties-of-custom-controls.md).</span></span>

1. <span data-ttu-id="902c5-122">**ツールボックス** から <xref:System.Windows.Forms.ToolStrip> デザイン画面にコントロールをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="902c5-122">From the **Toolbox**, drag a <xref:System.Windows.Forms.ToolStrip> control to the design surface.</span></span>

2. <span data-ttu-id="902c5-123">[ **プロパティ** ] ウィンドウで、 <xref:System.Windows.Forms.ToolStrip> 次の表に従ってコントロールのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="902c5-123">In the **Properties** window, set the <xref:System.Windows.Forms.ToolStrip> control's properties according to the following table.</span></span>

    |<span data-ttu-id="902c5-124">プロパティ</span><span class="sxs-lookup"><span data-stu-id="902c5-124">Property</span></span>|<span data-ttu-id="902c5-125">値</span><span class="sxs-lookup"><span data-stu-id="902c5-125">Value</span></span>|
    |--------------|-----------|
    |<span data-ttu-id="902c5-126">名前</span><span class="sxs-lookup"><span data-stu-id="902c5-126">Name</span></span>|`stackStrip`|
    |<span data-ttu-id="902c5-127">CanOverflow</span><span class="sxs-lookup"><span data-stu-id="902c5-127">CanOverflow</span></span>|`false`|
    |<span data-ttu-id="902c5-128">ドッキング</span><span class="sxs-lookup"><span data-stu-id="902c5-128">Dock</span></span>|<xref:System.Windows.Forms.DockStyle.Bottom>|
    |<span data-ttu-id="902c5-129">フォント</span><span class="sxs-lookup"><span data-stu-id="902c5-129">Font</span></span>|`Tahoma, 10pt, style=Bold`|
    |<span data-ttu-id="902c5-130">GripStyle</span><span class="sxs-lookup"><span data-stu-id="902c5-130">GripStyle</span></span>|<xref:System.Windows.Forms.ToolStripGripStyle.Hidden>|
    |<span data-ttu-id="902c5-131">LayoutStyle</span><span class="sxs-lookup"><span data-stu-id="902c5-131">LayoutStyle</span></span>|<xref:System.Windows.Forms.ToolStripLayoutStyle.VerticalStackWithOverflow>|
    |<span data-ttu-id="902c5-132">パディング</span><span class="sxs-lookup"><span data-stu-id="902c5-132">Padding</span></span>|`0, 7, 0, 0`|
    |<span data-ttu-id="902c5-133">RenderMode</span><span class="sxs-lookup"><span data-stu-id="902c5-133">RenderMode</span></span>|<xref:System.Windows.Forms.ToolStripRenderMode.Professional>|

3. <span data-ttu-id="902c5-134">Windows フォームデザイナーで、 <xref:System.Windows.Forms.ToolStrip> コントロールの [ **追加** ] ボタンをクリックし、 <xref:System.Windows.Forms.ToolStripButton> コントロールにを追加し `stackStrip` ます。</span><span class="sxs-lookup"><span data-stu-id="902c5-134">In the Windows Forms Designer, click the <xref:System.Windows.Forms.ToolStrip> control's **Add** button and add a <xref:System.Windows.Forms.ToolStripButton> to the `stackStrip` control.</span></span>

4. <span data-ttu-id="902c5-135">[ **プロパティ** ] ウィンドウで、 <xref:System.Windows.Forms.ToolStripButton> 次の表に従ってコントロールのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="902c5-135">In the **Properties** window, set the <xref:System.Windows.Forms.ToolStripButton> control's properties according to the following table.</span></span>

    |<span data-ttu-id="902c5-136">プロパティ</span><span class="sxs-lookup"><span data-stu-id="902c5-136">Property</span></span>|<span data-ttu-id="902c5-137">値</span><span class="sxs-lookup"><span data-stu-id="902c5-137">Value</span></span>|
    |--------------|-----------|
    |<span data-ttu-id="902c5-138">名前</span><span class="sxs-lookup"><span data-stu-id="902c5-138">Name</span></span>|`mailStackButton`|
    |<span data-ttu-id="902c5-139">CheckOnClick</span><span class="sxs-lookup"><span data-stu-id="902c5-139">CheckOnClick</span></span>|<span data-ttu-id="902c5-140">true</span><span class="sxs-lookup"><span data-stu-id="902c5-140">true</span></span>|
    |<span data-ttu-id="902c5-141">CheckState</span><span class="sxs-lookup"><span data-stu-id="902c5-141">CheckState</span></span>|<xref:System.Windows.Forms.CheckState.Checked>|
    |<span data-ttu-id="902c5-142">System.windows.forms.toolstripitem.displaystyle</span><span class="sxs-lookup"><span data-stu-id="902c5-142">DisplayStyle</span></span>|<xref:System.Windows.Forms.ToolStripItemDisplayStyle.ImageAndText>|
    |<span data-ttu-id="902c5-143">ImageAlign</span><span class="sxs-lookup"><span data-stu-id="902c5-143">ImageAlign</span></span>|<xref:System.Drawing.ContentAlignment.MiddleLeft>|
    |<span data-ttu-id="902c5-144">ImageScaling</span><span class="sxs-lookup"><span data-stu-id="902c5-144">ImageScaling</span></span>|<xref:System.Windows.Forms.ToolStripItemImageScaling.None>|
    |<span data-ttu-id="902c5-145">ImageTransparentColor</span><span class="sxs-lookup"><span data-stu-id="902c5-145">ImageTransparentColor</span></span>|`238, 238, 238`|
    |<span data-ttu-id="902c5-146">余白</span><span class="sxs-lookup"><span data-stu-id="902c5-146">Margin</span></span>|`0, 0, 0, 0`|
    |<span data-ttu-id="902c5-147">[間隔]</span><span class="sxs-lookup"><span data-stu-id="902c5-147">Padding</span></span>|`3, 3, 3, 3`|
    |<span data-ttu-id="902c5-148">Text</span><span class="sxs-lookup"><span data-stu-id="902c5-148">Text</span></span>|<span data-ttu-id="902c5-149">**電子**</span><span class="sxs-lookup"><span data-stu-id="902c5-149">**Mail**</span></span>|
    |<span data-ttu-id="902c5-150">TextAlign</span><span class="sxs-lookup"><span data-stu-id="902c5-150">TextAlign</span></span>|<xref:System.Drawing.ContentAlignment.MiddleLeft>|

5. <span data-ttu-id="902c5-151">さらに3つのコントロールについて、手順 7. を繰り返し <xref:System.Windows.Forms.ToolStripButton> ます。</span><span class="sxs-lookup"><span data-stu-id="902c5-151">Repeat step 7 for three more <xref:System.Windows.Forms.ToolStripButton> controls.</span></span>

     <span data-ttu-id="902c5-152">コントロールに、、およびという名前を指定し `calendarStackButton` `contactsStackButton` `tasksStackButton` ます。</span><span class="sxs-lookup"><span data-stu-id="902c5-152">Name the controls `calendarStackButton`, `contactsStackButton`, and `tasksStackButton`.</span></span> <span data-ttu-id="902c5-153">プロパティの値 <xref:System.Windows.Forms.Control.Text%2A> をそれぞれ **Calendar**、 **Contacts**、および **Tasks** に設定します。</span><span class="sxs-lookup"><span data-stu-id="902c5-153">Set the value of the <xref:System.Windows.Forms.Control.Text%2A> property to **Calendar**, **Contacts**, and **Tasks**, respectively.</span></span>

## <a name="handle-events"></a><span data-ttu-id="902c5-154">イベントを処理する</span><span class="sxs-lookup"><span data-stu-id="902c5-154">Handle events</span></span>

<span data-ttu-id="902c5-155">コントロールを正しく動作させるには、2つのイベントが重要です `StackView` 。</span><span class="sxs-lookup"><span data-stu-id="902c5-155">Two events are important to make the `StackView` control behave correctly.</span></span> <span data-ttu-id="902c5-156">イベントを処理して <xref:System.Windows.Forms.UserControl.Load> 、コントロールを正しく配置します。</span><span class="sxs-lookup"><span data-stu-id="902c5-156">Handle the <xref:System.Windows.Forms.UserControl.Load> event to position the control correctly.</span></span> <span data-ttu-id="902c5-157">それぞれのイベントを処理して、コントロール <xref:System.Windows.Forms.ToolStripItem.Click> <xref:System.Windows.Forms.ToolStripButton> `StackView` の状態の動作をコントロールと同様にし <xref:System.Windows.Forms.RadioButton> ます。</span><span class="sxs-lookup"><span data-stu-id="902c5-157">Handle the <xref:System.Windows.Forms.ToolStripItem.Click> event for each <xref:System.Windows.Forms.ToolStripButton> to give the `StackView` control state behavior similar to the <xref:System.Windows.Forms.RadioButton> control.</span></span>

1. <span data-ttu-id="902c5-158">[Windows フォームデザイナーで、コントロールを選択し `StackView` ます。</span><span class="sxs-lookup"><span data-stu-id="902c5-158">In the Windows Forms Designer, select the `StackView` control.</span></span>

2. <span data-ttu-id="902c5-159">**[プロパティ]** ウィンドウで、**[イベント]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="902c5-159">In the **Properties** window, click **Events**.</span></span>

3. <span data-ttu-id="902c5-160">イベントハンドラーを生成するには、Load イベントをダブルクリックし `StackView_Load` ます。</span><span class="sxs-lookup"><span data-stu-id="902c5-160">Double-click the Load event to generate the `StackView_Load` event handler.</span></span>

4. <span data-ttu-id="902c5-161">`StackView_Load` イベント ハンドラーで、次のコードをコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="902c5-161">In the `StackView_Load` event handler, copy and paste the following code.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#3)]

5. <span data-ttu-id="902c5-162">[Windows フォームデザイナーで、コントロールを選択し `mailStackButton` ます。</span><span class="sxs-lookup"><span data-stu-id="902c5-162">In the Windows Forms Designer, select the `mailStackButton` control.</span></span>

6. <span data-ttu-id="902c5-163">**[プロパティ]** ウィンドウで、**[イベント]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="902c5-163">In the **Properties** window, click **Events**.</span></span>

7. <span data-ttu-id="902c5-164">Click イベントをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="902c5-164">Double-click the Click event.</span></span>

     <span data-ttu-id="902c5-165">Windows フォームデザイナーによって、イベントハンドラーが生成され `mailStackButton_Click` ます。</span><span class="sxs-lookup"><span data-stu-id="902c5-165">The Windows Forms Designer generates the `mailStackButton_Click` event handler.</span></span>

8. <span data-ttu-id="902c5-166">`mailStackButton_Click`イベントハンドラーの名前をに変更 `stackButton_Click` します。</span><span class="sxs-lookup"><span data-stu-id="902c5-166">Rename the `mailStackButton_Click` event handler to `stackButton_Click`.</span></span>

     <span data-ttu-id="902c5-167">詳細については、「 [コードシンボルの名前変更のリファクタリング](/visualstudio/ide/reference/rename)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="902c5-167">For more information, see [Rename a code symbol refactoring](/visualstudio/ide/reference/rename).</span></span>

9. <span data-ttu-id="902c5-168">イベントハンドラーに次のコードを挿入し `stackButton_Click` ます。</span><span class="sxs-lookup"><span data-stu-id="902c5-168">Insert the following code into the `stackButton_Click` event handler.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#4)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#4)]

10. <span data-ttu-id="902c5-169">[Windows フォームデザイナーで、コントロールを選択し `calendarStackButton` ます。</span><span class="sxs-lookup"><span data-stu-id="902c5-169">In the Windows Forms Designer, select the `calendarStackButton` control.</span></span>

11. <span data-ttu-id="902c5-170">[ **プロパティ** ] ウィンドウで、click イベントをイベントハンドラーに設定し `stackButton_Click` ます。</span><span class="sxs-lookup"><span data-stu-id="902c5-170">In the **Properties** window, set the Click event to the `stackButton_Click` event handler.</span></span>

12. <span data-ttu-id="902c5-171">コントロールとコントロールに対して、手順 10. および 11. を繰り返し `contactsStackButton` `tasksStackButton` ます。</span><span class="sxs-lookup"><span data-stu-id="902c5-171">Repeat steps 10 and 11 for the `contactsStackButton` and `tasksStackButton` controls.</span></span>

## <a name="define-icons"></a><span data-ttu-id="902c5-172">アイコンの定義</span><span class="sxs-lookup"><span data-stu-id="902c5-172">Define icons</span></span>

<span data-ttu-id="902c5-173">各 `StackView` ボタンにはアイコンが関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="902c5-173">Each `StackView` button has an associated icon.</span></span> <span data-ttu-id="902c5-174">便宜上、各アイコンは Base64 でエンコードされた文字列として表され、が作成される前に逆シリアル化され <xref:System.Drawing.Bitmap> ます。</span><span class="sxs-lookup"><span data-stu-id="902c5-174">For convenience, each icon is represented as a Base64-encoded string, which is deserialized before a <xref:System.Drawing.Bitmap> is created from it.</span></span> <span data-ttu-id="902c5-175">運用環境では、ビットマップデータをリソースとして格納し、アイコンが Windows フォームデザイナーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="902c5-175">In a production environment, you store bitmap data as a resource, and your icons appear in the Windows Forms Designer.</span></span> <span data-ttu-id="902c5-176">詳細については、「 [方法: Windows フォームに背景画像を追加](/previous-versions/visualstudio/visual-studio-2010/dff9f95f(v=vs.100))する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="902c5-176">For more information, see [How to: Add Background Images to Windows Forms](/previous-versions/visualstudio/visual-studio-2010/dff9f95f(v=vs.100)).</span></span>

1. <span data-ttu-id="902c5-177">コードエディターで、次のコードをクラス定義に挿入し `StackView` ます。</span><span class="sxs-lookup"><span data-stu-id="902c5-177">In the Code Editor, insert the following code into the `StackView` class definition.</span></span> <span data-ttu-id="902c5-178">このコードでは、アイコンのビットマップを初期化し <xref:System.Windows.Forms.ToolStripButton> ます。</span><span class="sxs-lookup"><span data-stu-id="902c5-178">This code initializes the bitmaps for the <xref:System.Windows.Forms.ToolStripButton> icons.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#2)]

2. <span data-ttu-id="902c5-179">`InitializeImages`クラスコンストラクターにメソッドの呼び出しを追加 `StackView` します。</span><span class="sxs-lookup"><span data-stu-id="902c5-179">Add a call to the `InitializeImages` method in the `StackView` class constructor.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]

## <a name="implement-a-custom-renderer"></a><span data-ttu-id="902c5-180">カスタムレンダラーを実装する</span><span class="sxs-lookup"><span data-stu-id="902c5-180">Implement a custom renderer</span></span>

<span data-ttu-id="902c5-181">`StackView`クラスから派生するクラスを実装するコントロールのほとんどの要素をカスタマイズでき <xref:System.Windows.Forms.ToolStripRenderer> ます。</span><span class="sxs-lookup"><span data-stu-id="902c5-181">You can customize most elements of the `StackView` control my implementing a class that derives from the <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span> <span data-ttu-id="902c5-182">この手順では、 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> グリップをカスタマイズし、コントロールのグラデーションの背景を描画するクラスを実装し <xref:System.Windows.Forms.ToolStripButton> ます。</span><span class="sxs-lookup"><span data-stu-id="902c5-182">In this procedure, you will implement a <xref:System.Windows.Forms.ToolStripProfessionalRenderer> class that customizes the grip and draws gradient backgrounds for the <xref:System.Windows.Forms.ToolStripButton> controls.</span></span>

1. <span data-ttu-id="902c5-183">コントロール定義に次のコードを挿入し `StackView` ます。</span><span class="sxs-lookup"><span data-stu-id="902c5-183">Insert the following code into the `StackView` control definition.</span></span>

     <span data-ttu-id="902c5-184">これは、クラスの定義です。これは、、、およびの各メソッドをオーバーライドして `StackRenderer` <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip> 、 <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder> <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> カスタムの外観を生成します。</span><span class="sxs-lookup"><span data-stu-id="902c5-184">This is the definition for the `StackRenderer` class, which overrides the <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip>, <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder>, and <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> methods to produce a custom appearance.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#10)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#10)]

2. <span data-ttu-id="902c5-185">`StackView`コントロールのコンストラクターで、クラスの新しいインスタンスを作成 `StackRenderer` し、このインスタンスを `stackStrip` コントロールのプロパティに割り当て <xref:System.Windows.Forms.ToolStrip.Renderer%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="902c5-185">In the `StackView` control's constructor, create a new instance of the `StackRenderer` class and assign this instance to the `stackStrip` control's <xref:System.Windows.Forms.ToolStrip.Renderer%2A> property.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]

## <a name="test-the-stackview-control"></a><span data-ttu-id="902c5-186">StackView コントロールをテストする</span><span class="sxs-lookup"><span data-stu-id="902c5-186">Test the StackView control</span></span>

<span data-ttu-id="902c5-187">`StackView`コントロールはクラスから派生 <xref:System.Windows.Forms.UserControl> します。</span><span class="sxs-lookup"><span data-stu-id="902c5-187">The `StackView` control derives from the <xref:System.Windows.Forms.UserControl> class.</span></span> <span data-ttu-id="902c5-188">そのため、 **UserControl テストコンテナー** を使用してコントロールをテストできます。</span><span class="sxs-lookup"><span data-stu-id="902c5-188">Therefore, you can test the control with the **UserControl Test Container**.</span></span> <span data-ttu-id="902c5-189">詳細については、「 [方法: UserControl の Run-Time 動作をテストする](how-to-test-the-run-time-behavior-of-a-usercontrol.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="902c5-189">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

1. <span data-ttu-id="902c5-190">**F5** キーを押してプロジェクトをビルドし、 **UserControl テストコンテナー** を開始します。</span><span class="sxs-lookup"><span data-stu-id="902c5-190">Press **F5** to build the project and start the **UserControl Test Container**.</span></span>

2. <span data-ttu-id="902c5-191">コントロールのボタンの上にポインターを移動し、 `StackView` ボタンをクリックすると、選択した状態の外観が表示されます。</span><span class="sxs-lookup"><span data-stu-id="902c5-191">Move the pointer over the buttons of the `StackView` control, and then click a button to see the appearance of its selected state.</span></span>

## <a name="next-steps"></a><span data-ttu-id="902c5-192">次のステップ</span><span class="sxs-lookup"><span data-stu-id="902c5-192">Next steps</span></span>

<span data-ttu-id="902c5-193">このチュートリアルでは、Office XP コントロールのプロフェッショナルな外観を使用して、再利用可能なカスタムクライアントコントロールを作成しました。</span><span class="sxs-lookup"><span data-stu-id="902c5-193">In this walkthrough, you have created a reusable custom client control with the professional appearance of an Office XP control.</span></span> <span data-ttu-id="902c5-194">コントロールファミリは、 <xref:System.Windows.Forms.ToolStrip> 他のさまざまな用途に使用できます。</span><span class="sxs-lookup"><span data-stu-id="902c5-194">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>

- <span data-ttu-id="902c5-195">を使用して、コントロールのショートカットメニューを作成 <xref:System.Windows.Forms.ContextMenuStrip> します。</span><span class="sxs-lookup"><span data-stu-id="902c5-195">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="902c5-196">詳細については、「 [ContextMenu コンポーネントの概要](contextmenu-component-overview-windows-forms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="902c5-196">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>

- <span data-ttu-id="902c5-197">自動的に設定された標準メニューを使用してフォームを作成します。</span><span class="sxs-lookup"><span data-stu-id="902c5-197">Create a form with an automatically populated standard menu.</span></span> <span data-ttu-id="902c5-198">詳細については、「 [チュートリアル: フォームに標準メニュー項目を提供する](walkthrough-providing-standard-menu-items-to-a-form.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="902c5-198">For more information, see [Walkthrough: Providing Standard Menu Items to a Form](walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>

- <span data-ttu-id="902c5-199">ドッキングコントロールを使用して、マルチドキュメントインターフェイス (MDI) フォームを作成 <xref:System.Windows.Forms.ToolStrip> します。</span><span class="sxs-lookup"><span data-stu-id="902c5-199">Create a multiple document interface (MDI) form with docking <xref:System.Windows.Forms.ToolStrip> controls.</span></span> <span data-ttu-id="902c5-200">詳細については、「 [方法: メニューのマージと ToolStrip コントロールを使用して MDI フォームを作成](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="902c5-200">For more information, see [How to: Create an MDI Form with Menu Merging and ToolStrip Controls](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="902c5-201">関連項目</span><span class="sxs-lookup"><span data-stu-id="902c5-201">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="902c5-202">ToolStrip コントロール</span><span class="sxs-lookup"><span data-stu-id="902c5-202">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
- [<span data-ttu-id="902c5-203">方法: フォームに標準メニュー項目を追加する</span><span class="sxs-lookup"><span data-stu-id="902c5-203">How to: Provide Standard Menu Items to a Form</span></span>](how-to-provide-standard-menu-items-to-a-form.md)
