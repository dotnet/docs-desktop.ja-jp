---
title: BindingNavigator コントロールに [Load]、[Save]、[Cancel] の各ボタンを追加する
description: Windows フォーム BindingNavigator コントロールに [Load]、[Save]、[Cancel] の各ボタンを追加する方法について説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], manipulating
- BindingNavigator control [Windows Forms], adding buttons
ms.assetid: faa33042-186e-4bb2-8798-17ceb987ec62
ms.openlocfilehash: d4db91b8cfaf2df253d0c4cf5d8a66e9157d4986
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982952"
---
# <a name="how-to-add-load-save-and-cancel-buttons-to-the-windows-forms-bindingnavigator-control"></a><span data-ttu-id="3409e-103">方法: Windows フォーム BindingNavigator コントロールに [Load]、[Save]、[Cancel] の各ボタンを追加する</span><span class="sxs-lookup"><span data-stu-id="3409e-103">How to: Add Load, Save, and Cancel Buttons to the Windows Forms BindingNavigator Control</span></span>

<span data-ttu-id="3409e-104">コントロールは、 <xref:System.Windows.Forms.BindingNavigator> <xref:System.Windows.Forms.ToolStrip> データにバインドされているフォーム上のコントロールを移動および操作するための特殊な用途のコントロールです。</span><span class="sxs-lookup"><span data-stu-id="3409e-104">The <xref:System.Windows.Forms.BindingNavigator> control is a special-purpose <xref:System.Windows.Forms.ToolStrip> control that is intended for navigating and manipulating controls on your form that are bound to data.</span></span>

<span data-ttu-id="3409e-105">コントロールであるため、コンポーネントを簡単に変更して、 <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.BindingNavigator> ユーザーの追加または別のコマンドを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="3409e-105">Because it's a <xref:System.Windows.Forms.ToolStrip> control, the <xref:System.Windows.Forms.BindingNavigator> component can be easily modified to include additional or alternative commands for the user.</span></span>

<span data-ttu-id="3409e-106">次の手順では、 <xref:System.Windows.Forms.TextBox> コントロールがデータにバインドされ、 <xref:System.Windows.Forms.ToolStrip> フォームに追加されたコントロールが、[読み込み]、[保存]、および [キャンセル] の各ボタンを含むように変更されます。</span><span class="sxs-lookup"><span data-stu-id="3409e-106">In the following procedure, a <xref:System.Windows.Forms.TextBox> control is bound to data, and the <xref:System.Windows.Forms.ToolStrip> control that is added to the form is modified to include load, save, and cancel buttons.</span></span>

## <a name="add-load-save-and-cancel-buttons-to-the-bindingnavigator-component"></a><span data-ttu-id="3409e-107">[Load]、[save]、[cancel] の各ボタンを BindingNavigator コンポーネントに追加します。</span><span class="sxs-lookup"><span data-stu-id="3409e-107">Add load, save, and cancel buttons to the BindingNavigator component</span></span>

1. <span data-ttu-id="3409e-108">Visual Studio で、 <xref:System.Windows.Forms.TextBox> フォームにコントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="3409e-108">In Visual Studio, add a <xref:System.Windows.Forms.TextBox> control to your form.</span></span>

2. <span data-ttu-id="3409e-109"><xref:System.Windows.Forms.BindingSource>データソースにバインドされているにバインドします。</span><span class="sxs-lookup"><span data-stu-id="3409e-109">Bind it to a <xref:System.Windows.Forms.BindingSource>, which is bound to a data source.</span></span> <span data-ttu-id="3409e-110">この例では、 <xref:System.Windows.Forms.BindingSource> がデータベースにバインドされています。</span><span class="sxs-lookup"><span data-stu-id="3409e-110">For this example, the <xref:System.Windows.Forms.BindingSource> is bound to a database.</span></span>

3. <span data-ttu-id="3409e-111">データセットとテーブルアダプターが生成されたら、 <xref:System.Windows.Forms.BindingNavigator> コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="3409e-111">After the dataset and table adapter are generated, drag a <xref:System.Windows.Forms.BindingNavigator> control to the form.</span></span>

4. <span data-ttu-id="3409e-112">コントロール <xref:System.Windows.Forms.BindingNavigator> のプロパティを <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> 、 <xref:System.Windows.Forms.BindingSource> コントロールにバインドされているフォーム上のに設定します。</span><span class="sxs-lookup"><span data-stu-id="3409e-112">Set the <xref:System.Windows.Forms.BindingNavigator> control's <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> property to the <xref:System.Windows.Forms.BindingSource> on the form that is bound to the controls.</span></span>

5. <span data-ttu-id="3409e-113"><xref:System.Windows.Forms.BindingNavigator> コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="3409e-113">Select the <xref:System.Windows.Forms.BindingNavigator> control.</span></span>

6. <span data-ttu-id="3409e-114">[デザイナーアクション] グリフ ( ![ 小さい黒い矢印) をクリックして [ ](./media/designer-actions-glyph.gif) **BindingNavigator タスク** ] ダイアログを表示し、[ **アイテムの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3409e-114">Click the designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) so the **BindingNavigator Tasks** dialog appears and select **Edit Items**.</span></span>

     <span data-ttu-id="3409e-115">**項目コレクションエディター** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3409e-115">The **Items Collection Editor** appears.</span></span>

7. <span data-ttu-id="3409e-116">**Items コレクションエディター** で、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3409e-116">In the **Items Collection Editor**, complete the following:</span></span>

    1. <span data-ttu-id="3409e-117"><xref:System.Windows.Forms.ToolStripSeparator> <xref:System.Windows.Forms.ToolStripButton> 適切な種類のを選択 <xref:System.Windows.Forms.ToolStripItem> し、[**追加**] ボタンをクリックして、3つの項目を追加します。</span><span class="sxs-lookup"><span data-stu-id="3409e-117">Add a <xref:System.Windows.Forms.ToolStripSeparator> and three <xref:System.Windows.Forms.ToolStripButton> items by selecting the appropriate type of <xref:System.Windows.Forms.ToolStripItem> and clicking the **Add** button.</span></span>

    2. <span data-ttu-id="3409e-118"><xref:System.Windows.Forms.ToolStripItem.Name%2A>ボタンのプロパティを **loadbutton**、 **Savebutton**、および **cancelbutton** にそれぞれ設定します。</span><span class="sxs-lookup"><span data-stu-id="3409e-118">Set the <xref:System.Windows.Forms.ToolStripItem.Name%2A> property of the buttons to **LoadButton**, **SaveButton**, and **CancelButton**, respectively.</span></span>

    3. <span data-ttu-id="3409e-119">[ <xref:System.Windows.Forms.ToolStripItem.Text%2A> **読み込み**]、[ **保存**]、 **[キャンセル]** の各ボタンのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="3409e-119">Set the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property of the buttons to **Load**, **Save**, and **Cancel**.</span></span>

    4. <span data-ttu-id="3409e-120"><xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A>各ボタンのプロパティを [**テキスト**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="3409e-120">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property for each of the buttons to **Text**.</span></span> <span data-ttu-id="3409e-121">または、このプロパティを **image** または **imageandtext** に設定し、プロパティに表示されるようにイメージを設定することもでき <xref:System.Windows.Forms.ToolStripItem.Image%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="3409e-121">Alternatively, you can set this property to **Image** or **ImageAndText**, and set the image to be displayed in the <xref:System.Windows.Forms.ToolStripItem.Image%2A> property.</span></span>

    5. <span data-ttu-id="3409e-122">**[OK]** をクリックしてダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="3409e-122">Click **OK** to close the dialog box.</span></span> <span data-ttu-id="3409e-123">ボタンがに追加され <xref:System.Windows.Forms.ToolStrip> ます。</span><span class="sxs-lookup"><span data-stu-id="3409e-123">The buttons are added to the <xref:System.Windows.Forms.ToolStrip>.</span></span>

8. <span data-ttu-id="3409e-124">フォームを右クリックし、[ **コードの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3409e-124">Right-click the form and choose **View Code**.</span></span>

9. <span data-ttu-id="3409e-125">コードエディターで、テーブルアダプターにデータを読み込むコード行を見つけます。</span><span class="sxs-lookup"><span data-stu-id="3409e-125">In the Code Editor, find the line of code that loads data into the table adapter.</span></span> <span data-ttu-id="3409e-126">このコードは、手順 2. でデータバインディングを設定したときに生成されました。</span><span class="sxs-lookup"><span data-stu-id="3409e-126">This code was generated when you set up the data binding in step 2.</span></span> <span data-ttu-id="3409e-127">コードは次のようになり `TableAdapterName.Fill(DataSetName.TableName)` ます。</span><span class="sxs-lookup"><span data-stu-id="3409e-127">The code should be similar to the following: `TableAdapterName.Fill(DataSetName.TableName)`.</span></span> <span data-ttu-id="3409e-128">通常、フォームのイベントに含まれ <xref:System.Windows.Forms.Form.Load> ます。</span><span class="sxs-lookup"><span data-stu-id="3409e-128">It will most likely be in the form's <xref:System.Windows.Forms.Form.Load> event.</span></span>

10. <span data-ttu-id="3409e-129">前に作成した読み込みのイベントのイベントハンドラーを作成 <xref:System.Windows.Forms.ToolStripItem.Click> し、  <xref:System.Windows.Forms.ToolStripButton> このデータ読み込みコードをそのイベントに移動します。</span><span class="sxs-lookup"><span data-stu-id="3409e-129">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Load** <xref:System.Windows.Forms.ToolStripButton> you created earlier and move this data-loading code into it.</span></span>

     <span data-ttu-id="3409e-130">これで、コードは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="3409e-130">Your code should now look similar to the following:</span></span>

    ```vb
    Private Sub LoadButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles LoadButton.Click
        TableAdapterName.Fill(DataSetName.TableName)
    End Sub
    ```

    ```csharp
    private void LoadButton_Click(System.Object sender,
        System.EventArgs e)
    {
        TableAdapterName.Fill(DataSetName.TableName);
    }
    ```

11. <span data-ttu-id="3409e-131">前の手順で作成した保存のイベントのイベントハンドラーを作成 <xref:System.Windows.Forms.ToolStripItem.Click>  <xref:System.Windows.Forms.ToolStripButton> し、コントロールがバインドされているテーブル内のデータを更新するコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="3409e-131">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Save**<xref:System.Windows.Forms.ToolStripButton> you created earlier and write code to update the data within the table the control is bound to.</span></span>

    ```vb
    Private Sub SaveButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles SaveButton.Click
        TableAdapterName.Update(DataSetName.TableName)
    End Sub
    ```

    ```csharp
    private void SaveButton_Click(System.Object sender,
        System.EventArgs e)
    {
        TableAdapterName.Update(DataSetName.TableName);
    }
    ```

    > [!NOTE]
    > <span data-ttu-id="3409e-132">場合によっては、コンポーネントに [保存] ボタンが既に存在してい <xref:System.Windows.Forms.BindingNavigator> ても、Windows フォームデザイナーによってコードが生成されていないことがあります。 </span><span class="sxs-lookup"><span data-stu-id="3409e-132">In some cases, the <xref:System.Windows.Forms.BindingNavigator> component already has a **Save** button, but no code has been generated by the Windows Forms Designer.</span></span> <span data-ttu-id="3409e-133">この場合は、 <xref:System.Windows.Forms.ToolStripItem.Click> 上にまったく新しいボタンを作成するのではなく、そのボタンのイベントハンドラーに上記のコードを配置でき <xref:System.Windows.Forms.ToolStrip> ます。</span><span class="sxs-lookup"><span data-stu-id="3409e-133">In this case, you can place the preceding code in the <xref:System.Windows.Forms.ToolStripItem.Click> event handler for that button, rather than creating an entirely new button on the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="3409e-134">ただし、ボタンは既定で無効になっているので、ボタンのプロパティをに設定して、 <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> ボタンが正しく機能するようにする必要があり `true` ます。</span><span class="sxs-lookup"><span data-stu-id="3409e-134">However, the button is disabled by default, so you must set the <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> property of the button to `true` to have the button function correctly.</span></span>

12. <span data-ttu-id="3409e-135">前に作成したキャンセルのイベントのイベントハンドラーを作成 <xref:System.Windows.Forms.ToolStripItem.Click>  <xref:System.Windows.Forms.ToolStripButton> し、表示されるデータレコードに対する変更を取り消すコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="3409e-135">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Cancel** <xref:System.Windows.Forms.ToolStripButton> you created earlier and write code to cancel any changes to the data record that is displayed.</span></span>

    ```vb
    Private Sub CancelButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles CancelButton.Click
        BindingSourceName.CancelEdit()
    End Sub
    ```

    ```csharp
    private void CancelButton_Click(System.Object sender, System.EventArgs e)
    {
        BindingSourceName.CancelEdit();
    }
    ```

    > [!NOTE]
    > <span data-ttu-id="3409e-136"><xref:System.Windows.Forms.BindingSource.CancelEdit%2A>メソッドのスコープは、データの行です。</span><span class="sxs-lookup"><span data-stu-id="3409e-136">The <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> method is scoped to the row of data.</span></span> <span data-ttu-id="3409e-137">次のレコードに移動する前に、個々のレコードを表示しているときに行ったすべての変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="3409e-137">Save any changes you make while viewing that individual record before navigating to the next record.</span></span>

## <a name="see-also"></a><span data-ttu-id="3409e-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="3409e-138">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.ToolStrip>
- [<span data-ttu-id="3409e-139">BindingNavigator コントロール</span><span class="sxs-lookup"><span data-stu-id="3409e-139">BindingNavigator Control</span></span>](bindingnavigator-control-windows-forms.md)
- [<span data-ttu-id="3409e-140">BindingSource コンポーネントの概要</span><span class="sxs-lookup"><span data-stu-id="3409e-140">BindingSource Component Overview</span></span>](bindingsource-component-overview.md)
