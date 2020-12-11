---
title: 'チュートリアル : DesignerSerializationVisibilityAttribute を使用した、標準データ型のコレクションのシリアル化'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- serialization [Windows Forms], collections
- standard types [Windows Forms], collections
- collections [Windows Forms], serializing
- collections [Windows Forms], standard types
ms.assetid: 020c9df4-fdc5-4dae-815a-963ecae5668c
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 06ef484ffed76bad124ca33d240a4054fd937c14
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974149"
---
# <a name="walkthrough-serialize-collections-of-standard-types"></a><span data-ttu-id="d11b8-102">チュートリアル: 標準型のコレクションのシリアル化</span><span class="sxs-lookup"><span data-stu-id="d11b8-102">Walkthrough: Serialize collections of standard types</span></span>

<span data-ttu-id="d11b8-103">カスタムコントロールによって、コレクションがプロパティとして公開されることがあります。</span><span class="sxs-lookup"><span data-stu-id="d11b8-103">Your custom controls will sometimes expose a collection as a property.</span></span> <span data-ttu-id="d11b8-104">このチュートリアルでは、クラスを使用して、 <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> デザイン時にコレクションをシリアル化する方法を制御する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d11b8-104">This walkthrough demonstrates how to use the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> class to control how a collection is serialized at design time.</span></span> <span data-ttu-id="d11b8-105"><xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content>コレクションプロパティに値を適用すると、プロパティが確実にシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="d11b8-105">Applying the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> value to your collection property ensures that the property will be serialized.</span></span>

<span data-ttu-id="d11b8-106">このトピックのコードを単一のリストとしてコピーする方法については、「 [方法: DesignerSerializationVisibilityAttribute を使用して標準型のコレクションをシリアル化](/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d11b8-106">To copy the code in this topic as a single listing, see [How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120)).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d11b8-107">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d11b8-107">Prerequisites</span></span>

<span data-ttu-id="d11b8-108">このチュートリアルを完了するには Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="d11b8-108">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-a-control-with-a-serializable-collection"></a><span data-ttu-id="d11b8-109">シリアル化可能なコレクションを持つコントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="d11b8-109">Create a control with a serializable collection</span></span>

<span data-ttu-id="d11b8-110">最初の手順では、シリアル化可能なコレクションをプロパティとして持つコントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="d11b8-110">The first step is to create a control that has a serializable collection as a property.</span></span> <span data-ttu-id="d11b8-111">このコレクションの内容は、[**プロパティ**] ウィンドウからアクセスできる **コレクションエディター** を使用して編集できます。</span><span class="sxs-lookup"><span data-stu-id="d11b8-111">You can edit the contents of this collection using the **Collection Editor**, which you can access from the **Properties** window.</span></span>

1. <span data-ttu-id="d11b8-112">Visual Studio で、Windows コントロールライブラリプロジェクトを作成し、「 **Serializationdemocontrollib**」という名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d11b8-112">In Visual Studio, create a Windows Control Library project, and name it **SerializationDemoControlLib**.</span></span>

2. <span data-ttu-id="d11b8-113">`UserControl1` の名前を `SerializationDemoControl` に変更します。</span><span class="sxs-lookup"><span data-stu-id="d11b8-113">Rename `UserControl1` to `SerializationDemoControl`.</span></span> <span data-ttu-id="d11b8-114">詳細については、「 [コードシンボルの名前変更のリファクタリング](/visualstudio/ide/reference/rename)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d11b8-114">For more information, see [Rename a code symbol refactoring](/visualstudio/ide/reference/rename).</span></span>

3. <span data-ttu-id="d11b8-115">[ **プロパティ** ] ウィンドウで、プロパティの値 <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> を **10** に設定します。</span><span class="sxs-lookup"><span data-stu-id="d11b8-115">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> property to **10**.</span></span>

4. <span data-ttu-id="d11b8-116"><xref:System.Windows.Forms.TextBox>にコントロールを配置し `SerializationDemoControl` ます。</span><span class="sxs-lookup"><span data-stu-id="d11b8-116">Place a <xref:System.Windows.Forms.TextBox> control in the `SerializationDemoControl`.</span></span>

5. <span data-ttu-id="d11b8-117"><xref:System.Windows.Forms.TextBox> コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="d11b8-117">Select the <xref:System.Windows.Forms.TextBox> control.</span></span> <span data-ttu-id="d11b8-118">[ **プロパティ** ] ウィンドウで、次のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="d11b8-118">In the **Properties** window, set the following properties.</span></span>

    |<span data-ttu-id="d11b8-119">プロパティ</span><span class="sxs-lookup"><span data-stu-id="d11b8-119">Property</span></span>|<span data-ttu-id="d11b8-120">変更後の値</span><span class="sxs-lookup"><span data-stu-id="d11b8-120">Change to</span></span>|
    |--------------|---------------|
    |<span data-ttu-id="d11b8-121">**Multiline**</span><span class="sxs-lookup"><span data-stu-id="d11b8-121">**Multiline**</span></span>|`true`|
    |<span data-ttu-id="d11b8-122">**ドッキング**</span><span class="sxs-lookup"><span data-stu-id="d11b8-122">**Dock**</span></span>|<xref:System.Windows.Forms.DockStyle.Fill>|
    |<span data-ttu-id="d11b8-123">**スクロールバー**</span><span class="sxs-lookup"><span data-stu-id="d11b8-123">**ScrollBars**</span></span>|<xref:System.Windows.Forms.ScrollBars.Vertical>|
    |<span data-ttu-id="d11b8-124">**ReadOnly**</span><span class="sxs-lookup"><span data-stu-id="d11b8-124">**ReadOnly**</span></span>|`true`|

6. <span data-ttu-id="d11b8-125">**コードエディター** で、にという名前の文字列配列フィールドを宣言 `stringsValue` `SerializationDemoControl` します。</span><span class="sxs-lookup"><span data-stu-id="d11b8-125">In the **Code Editor**, declare a string array field named `stringsValue` in `SerializationDemoControl`.</span></span>

     [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#4)]
     [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#4)]
     [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#4)]

7. <span data-ttu-id="d11b8-126">`Strings`でプロパティを定義し `SerializationDemoControl` ます。</span><span class="sxs-lookup"><span data-stu-id="d11b8-126">Define the `Strings` property on the `SerializationDemoControl`.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d11b8-127"><xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content>値は、コレクションのシリアル化を有効にするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d11b8-127">The <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> value is used to enable serialization of the collection.</span></span>

   [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#5)]
   [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#5)]
   [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#5)]

8. <span data-ttu-id="d11b8-128">**F5** キーを押してプロジェクトをビルドし、 **UserControl テストコンテナー** でコントロールを実行します。</span><span class="sxs-lookup"><span data-stu-id="d11b8-128">Press **F5** to build the project and run your control in the **UserControl Test Container**.</span></span>

9. <span data-ttu-id="d11b8-129"> <xref:System.Windows.Forms.PropertyGrid> **UserControl テストコンテナー** ので、Strings プロパティを見つけます。</span><span class="sxs-lookup"><span data-stu-id="d11b8-129">Find the **Strings** property in the <xref:System.Windows.Forms.PropertyGrid> of the **UserControl Test Container**.</span></span> <span data-ttu-id="d11b8-130">[ **文字列** ] プロパティを選択し、省略記号 ( ![ Visual Studio のプロパティウィンドウの省略記号ボタン (...)) を選択して、 ](./media/visual-studio-ellipsis-button.png) **文字列コレクションエディター** を開きます。</span><span class="sxs-lookup"><span data-stu-id="d11b8-130">Select the **Strings** property, then select the ellipsis (![The Ellipsis button (...) in the Properties window of Visual Studio](./media/visual-studio-ellipsis-button.png)) button to open the **String Collection Editor**.</span></span>

10. <span data-ttu-id="d11b8-131">**文字列コレクションエディター** でいくつかの文字列を入力します。</span><span class="sxs-lookup"><span data-stu-id="d11b8-131">Enter several strings in the **String Collection Editor**.</span></span> <span data-ttu-id="d11b8-132">各文字列の末尾にある **enter** キーを押して区切ります。</span><span class="sxs-lookup"><span data-stu-id="d11b8-132">Separate them by pressing the **Enter** key at the end of each string.</span></span> <span data-ttu-id="d11b8-133">文字列の入力が完了したら、[ **OK** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d11b8-133">Click **OK** when you are finished entering strings.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d11b8-134">入力した文字列は、のに表示され <xref:System.Windows.Forms.TextBox> `SerializationDemoControl` ます。</span><span class="sxs-lookup"><span data-stu-id="d11b8-134">The strings you typed appear in the <xref:System.Windows.Forms.TextBox> of the `SerializationDemoControl`.</span></span>

## <a name="serialize-a-collection-property"></a><span data-ttu-id="d11b8-135">コレクションプロパティをシリアル化する</span><span class="sxs-lookup"><span data-stu-id="d11b8-135">Serialize a collection property</span></span>

<span data-ttu-id="d11b8-136">コントロールのシリアル化動作をテストするには、コントロールをフォームに配置し、コレクション **エディター** を使用してコレクションの内容を変更します。</span><span class="sxs-lookup"><span data-stu-id="d11b8-136">To test the serialization behavior of your control, you will place it on a form and change the contents of the collection with the **Collection Editor**.</span></span> <span data-ttu-id="d11b8-137">シリアル化されたコレクションの状態を確認するには、 **Windows フォームデザイナー** がコードを出力する特別なデザイナーファイルを調べます。</span><span class="sxs-lookup"><span data-stu-id="d11b8-137">You can see the serialized collection state by looking at a special designer file into which the **Windows Forms Designer** emits code.</span></span>

1. <span data-ttu-id="d11b8-138">Windows アプリケーションプロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="d11b8-138">Add a Windows Application project to the solution.</span></span> <span data-ttu-id="d11b8-139">プロジェクトに `SerializationDemoControlTest` という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="d11b8-139">Name the project `SerializationDemoControlTest`.</span></span>

2. <span data-ttu-id="d11b8-140">[ **ツールボックス**] で、[ **Serializationdemocontrollib Components**] という名前のタブを探します。</span><span class="sxs-lookup"><span data-stu-id="d11b8-140">In the **Toolbox**, find the tab named **SerializationDemoControlLib Components**.</span></span> <span data-ttu-id="d11b8-141">このタブには、が `SerializationDemoControl` あります。</span><span class="sxs-lookup"><span data-stu-id="d11b8-141">In this tab, you will find the `SerializationDemoControl`.</span></span> <span data-ttu-id="d11b8-142">詳細については、「[チュートリアル : ツールボックスへのカスタム コンポーネントの自動設定](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d11b8-142">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>

3. <span data-ttu-id="d11b8-143">を `SerializationDemoControl` フォームに配置します。</span><span class="sxs-lookup"><span data-stu-id="d11b8-143">Place a `SerializationDemoControl` on your form.</span></span>

4. <span data-ttu-id="d11b8-144">`Strings`[**プロパティ**] ウィンドウでプロパティを見つけます。</span><span class="sxs-lookup"><span data-stu-id="d11b8-144">Find the `Strings` property in the **Properties** window.</span></span> <span data-ttu-id="d11b8-145">`Strings`プロパティをクリックし、[ ![ Visual Studio のプロパティウィンドウ] の省略記号ボタン ([...]) をクリックして、 ](./media/visual-studio-ellipsis-button.png) **文字列コレクションエディター** を開きます。</span><span class="sxs-lookup"><span data-stu-id="d11b8-145">Click the `Strings` property, then click the ellipsis (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button to open the **String Collection Editor**.</span></span>

5. <span data-ttu-id="d11b8-146">**文字列コレクションエディター** でいくつかの文字列を入力します。</span><span class="sxs-lookup"><span data-stu-id="d11b8-146">Type several strings in the **String Collection Editor**.</span></span> <span data-ttu-id="d11b8-147">各文字列の末尾で **enter** キーを押して区切ります。</span><span class="sxs-lookup"><span data-stu-id="d11b8-147">Separate them by pressing **Enter** at the end of each string.</span></span> <span data-ttu-id="d11b8-148">文字列の入力が完了したら、[ **OK** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d11b8-148">Click **OK** when you are finished entering strings.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d11b8-149">入力した文字列は、のに表示され <xref:System.Windows.Forms.TextBox> `SerializationDemoControl` ます。</span><span class="sxs-lookup"><span data-stu-id="d11b8-149">The strings you typed appear in the <xref:System.Windows.Forms.TextBox> of the `SerializationDemoControl`.</span></span>

6. <span data-ttu-id="d11b8-150">**ソリューション エクスプローラー** で、 **[すべてのファイルを表示]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d11b8-150">In **Solution Explorer**, click the **Show All Files** button.</span></span>

7. <span data-ttu-id="d11b8-151">**Form1** ノードを開きます。</span><span class="sxs-lookup"><span data-stu-id="d11b8-151">Open the **Form1** node.</span></span> <span data-ttu-id="d11b8-152">その下には、 **Form1.Designer.cs** または **form1.vb** という名前のファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="d11b8-152">Beneath it is a file called **Form1.Designer.cs** or **Form1.Designer.vb**.</span></span> <span data-ttu-id="d11b8-153">これは、フォームとその子コントロールのデザイン時の状態を表すコードを **Windows フォームデザイナー** が出力するファイルです。</span><span class="sxs-lookup"><span data-stu-id="d11b8-153">This is the file into which the **Windows Forms Designer** emits code representing the design-time state of your form and its child controls.</span></span> <span data-ttu-id="d11b8-154">**コードエディター** でこのファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="d11b8-154">Open this file in the **Code Editor**.</span></span>

8. <span data-ttu-id="d11b8-155">**Windows フォームデザイナーで生成されたコード** という名前の領域を開き、 **serializationDemoControl1** というラベルが付いたセクションを検索します。</span><span class="sxs-lookup"><span data-stu-id="d11b8-155">Open the region called **Windows Form Designer generated code** and find the section labeled **serializationDemoControl1**.</span></span> <span data-ttu-id="d11b8-156">このラベルの下には、コントロールのシリアル化された状態を表すコードがあります。</span><span class="sxs-lookup"><span data-stu-id="d11b8-156">Beneath this label is the code representing the serialized state of your control.</span></span> <span data-ttu-id="d11b8-157">手順 5. で入力した文字列は、プロパティへの代入の中に表示され `Strings` ます。</span><span class="sxs-lookup"><span data-stu-id="d11b8-157">The strings you typed in step 5 appear in an assignment to the `Strings` property.</span></span> <span data-ttu-id="d11b8-158">C# および Visual Basic の次のコード例では、文字列 "red"、"オレンジ"、および "黄" を入力した場合と同様のコードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d11b8-158">The following code examples in C# and Visual Basic, show code similar to what you will see if you typed the strings "red", "orange", and "yellow".</span></span>

    ```csharp
    this.serializationDemoControl1.Strings = new string[] {
            "red",
            "orange",
            "yellow"};
    ```

    ```vb
    Me.serializationDemoControl1.Strings = New String() {"red", "orange", "yellow"}
    ```

9. <span data-ttu-id="d11b8-159">**コードエディター** で、プロパティのの値 <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> をに変更し `Strings` <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden> ます。</span><span class="sxs-lookup"><span data-stu-id="d11b8-159">In the **Code Editor**, change the value of the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> on the `Strings` property to <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>.</span></span>

    ```csharp
    [DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)]
    ```

    ```vb
    <DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)> _
    ```

10. <span data-ttu-id="d11b8-160">ソリューションをリビルドし、手順3と4を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="d11b8-160">Rebuild the solution and repeat steps 3 and 4.</span></span>

> [!NOTE]
> <span data-ttu-id="d11b8-161">この場合、 **Windows フォームデザイナー** はプロパティに割り当てを出力しません `Strings` 。</span><span class="sxs-lookup"><span data-stu-id="d11b8-161">In this case, the **Windows Forms Designer** emits no assignment to the `Strings` property.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d11b8-162">次のステップ</span><span class="sxs-lookup"><span data-stu-id="d11b8-162">Next steps</span></span>

<span data-ttu-id="d11b8-163">標準型のコレクションをシリアル化する方法を理解したら、カスタムコントロールをデザイン時環境により深く統合することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="d11b8-163">Once you know how to serialize a collection of standard types, consider integrating your custom controls more deeply into the design-time environment.</span></span> <span data-ttu-id="d11b8-164">次のトピックでは、カスタムコントロールのデザイン時統合を強化する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d11b8-164">The following topics describe how to enhance the design-time integration of your custom controls:</span></span>

- <span data-ttu-id="d11b8-165">[デザイン時アーキテクチャ](/previous-versions/visualstudio/visual-studio-2013/c5z9s1h4(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="d11b8-165">[Design-Time Architecture](/previous-versions/visualstudio/visual-studio-2013/c5z9s1h4(v=vs.120))</span></span>

- [<span data-ttu-id="d11b8-166">Windows フォーム コントロールの属性</span><span class="sxs-lookup"><span data-stu-id="d11b8-166">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)

- <span data-ttu-id="d11b8-167">[デザイナーのシリアル化の概要](/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="d11b8-167">[Designer Serialization Overview](/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span></span>

- [<span data-ttu-id="d11b8-168">チュートリアル: Visual Studio の Design-Time 機能を利用する Windows フォームコントロールの作成</span><span class="sxs-lookup"><span data-stu-id="d11b8-168">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)

## <a name="see-also"></a><span data-ttu-id="d11b8-169">関連項目</span><span class="sxs-lookup"><span data-stu-id="d11b8-169">See also</span></span>

- <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>
- [<span data-ttu-id="d11b8-170">チュートリアル: ツールボックスへのカスタム コンポーネントの自動設定</span><span class="sxs-lookup"><span data-stu-id="d11b8-170">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
