---
title: フォームの位置とサイズを設定する
description: .NET Windows フォームと Visual Studio でフォームのサイズと位置を設定する方法について説明します。 サイズと位置は、Visual Studio デザイナーまたはコードを使用して設定できます。
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- positioning Windows Forms
- resizing Windows Forms
- Windows Forms, location
- Windows Forms, size
ms.openlocfilehash: 4fdaff7589669ae2e216d08feda5368835b50b5b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96942362"
---
# <a name="how-to-position-and-size-a-form-windows-forms-net"></a><span data-ttu-id="cb1af-104">フォームの位置とサイズを設定する方法 (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="cb1af-104">How to position and size a form (Windows Forms .NET)</span></span>

<span data-ttu-id="cb1af-105">フォームが作成されると、サイズと位置は最初に既定値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="cb1af-105">When a form is created, the size and location is initially set to a default value.</span></span> <span data-ttu-id="cb1af-106">フォームの既定のサイズの幅と高さは、通常、_800x500_ ピクセルです。</span><span class="sxs-lookup"><span data-stu-id="cb1af-106">The default size of a form is generally a width and height of _800x500_ pixels.</span></span> <span data-ttu-id="cb1af-107">フォームが表示されるときの最初の位置は、いくつかの異なる設定によって異なります。</span><span class="sxs-lookup"><span data-stu-id="cb1af-107">The initial location, when the form is displayed, depends on a few different settings.</span></span>

<span data-ttu-id="cb1af-108">フォームのサイズは、デザイン時に Visual Studio を使用して変更したり、実行時にコードを使用して変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="cb1af-108">You can change the size of a form at design time with Visual Studio, and at run time with code.</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="resize-with-the-designer"></a><span data-ttu-id="cb1af-109">デザイナーでサイズを変更する</span><span class="sxs-lookup"><span data-stu-id="cb1af-109">Resize with the designer</span></span>

<span data-ttu-id="cb1af-110">プロジェクトに[新しいフォームを追加](how-to-add.md)した後、フォームのサイズは 2 つの異なる方法で設定されます。</span><span class="sxs-lookup"><span data-stu-id="cb1af-110">After [adding a new form](how-to-add.md) to the project, the size of a form is set in two different ways.</span></span> <span data-ttu-id="cb1af-111">まず、デザイナーでサイズ グリップを使用して設定できます。</span><span class="sxs-lookup"><span data-stu-id="cb1af-111">First, you can set it is with the size grips in the designer.</span></span> <span data-ttu-id="cb1af-112">右端、下端、または角をドラッグすることで、フォームのサイズを変更できます。</span><span class="sxs-lookup"><span data-stu-id="cb1af-112">By dragging either the right edge, bottom edge, or the corner, you can resize the form.</span></span>

:::image type="content" source="media/how-to-position-and-resize/designer-grips.png" alt-text="ソリューション エクスプローラーを右クリックし、グリップを使用して Windows フォーム プロジェクトに新しいフォームを追加する":::

<span data-ttu-id="cb1af-114">デザイナーが開いている間にフォームのサイズを変更する 2 番目の方法は、プロパティ ペインを使用することです。</span><span class="sxs-lookup"><span data-stu-id="cb1af-114">The second way you can resize the form while the designer is open, is through the properties pane.</span></span> <span data-ttu-id="cb1af-115">フォームを選択し、Visual Studio で **[プロパティ]** ペインを見つけます。</span><span class="sxs-lookup"><span data-stu-id="cb1af-115">Select the form, then find the **Properties** pane in Visual Studio.</span></span> <span data-ttu-id="cb1af-116">下にスクロールして **[サイズ]** を展開します。</span><span class="sxs-lookup"><span data-stu-id="cb1af-116">Scroll down to **size** and expand it.</span></span> <span data-ttu-id="cb1af-117">**[幅]** と **[高さ]** を手動で設定できます。</span><span class="sxs-lookup"><span data-stu-id="cb1af-117">You can set the **Width** and **Height** manually.</span></span>

:::image type="content" source="media/how-to-position-and-resize/designer-properties-size.png" alt-text="ソリューション エクスプローラーを右クリックして、Windows フォーム プロジェクトに新しいフォームを追加する":::

## <a name="resize-in-code"></a><span data-ttu-id="cb1af-119">コードでサイズを変更する</span><span class="sxs-lookup"><span data-stu-id="cb1af-119">Resize in code</span></span>

<span data-ttu-id="cb1af-120">フォームの初期サイズをデザイナーで設定した場合でも、コードを使用してサイズを変更できます。</span><span class="sxs-lookup"><span data-stu-id="cb1af-120">Even though the designer sets the starting size of a form, you can resize it through code.</span></span> <span data-ttu-id="cb1af-121">コードを使用したフォームのサイズの変更は、アプリケーションによってフォームの既定のサイズが不十分であると判断された場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="cb1af-121">Using code to resize a form is useful when something about your application determines that the default size of the form is insufficient.</span></span>

<span data-ttu-id="cb1af-122">フォームのサイズを変更するには、フォームの幅と高さを表す <xref:System.Windows.Forms.Form.Size%2A> を変更します。</span><span class="sxs-lookup"><span data-stu-id="cb1af-122">To resize a form, change the <xref:System.Windows.Forms.Form.Size%2A>, which represents the width and height of the form.</span></span>

### <a name="resize-the-current-form"></a><span data-ttu-id="cb1af-123">現在のフォームのサイズを変更する</span><span class="sxs-lookup"><span data-stu-id="cb1af-123">Resize the current form</span></span>

<span data-ttu-id="cb1af-124">フォームのコンテキスト内でコードが実行されている限り、現在のフォームのサイズを変更できます。</span><span class="sxs-lookup"><span data-stu-id="cb1af-124">You can change the size of the current form as long as the code is running within the context of the form.</span></span> <span data-ttu-id="cb1af-125">たとえば、ボタンを含む `Form1` がある場合、それがクリックされたら `Click` イベント ハンドラーを呼び出して、フォームのサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="cb1af-125">For example, if you have `Form1` with a button on it, that when clicked invokes the `Click` event handler to resize the form:</span></span>

```csharp
private void button1_Click(object sender, EventArgs e) =>
    Size = new Size(250, 200);
```

```vb
Private Sub Button1_Click(sender As Object, e As EventArgs)
    Size = New Drawing.Size(250, 200)
End Sub
```

### <a name="resize-a-different-form"></a><span data-ttu-id="cb1af-126">別のフォームのサイズを変更する</span><span class="sxs-lookup"><span data-stu-id="cb1af-126">Resize a different form</span></span>

<span data-ttu-id="cb1af-127">別のフォームを作成した後、フォームを参照する変数を使用して、そのサイズを変更できます。</span><span class="sxs-lookup"><span data-stu-id="cb1af-127">You can change the size of another form after it's created by using the variable referencing the form.</span></span> <span data-ttu-id="cb1af-128">たとえば、2 つのフォーム `Form1` (この例でのスタートアップ フォーム) と `Form2` があるとします。</span><span class="sxs-lookup"><span data-stu-id="cb1af-128">For example, let's say you have two forms, `Form1` (the startup form in this example) and `Form2`.</span></span> <span data-ttu-id="cb1af-129">`Form1` には、クリックされると `Click` イベントを呼び出すボタンがあります。</span><span class="sxs-lookup"><span data-stu-id="cb1af-129">`Form1` has a button that when clicked, invokes the `Click` event.</span></span> <span data-ttu-id="cb1af-130">このイベントのハンドラーにより、`Form2` フォームの新しいインスタンスが作成され、サイズが設定されてから、それが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb1af-130">The handler of this event creates a new instance of the `Form2` form, sets the size, and then displays it:</span></span>

```csharp
private void button1_Click(object sender, EventArgs e)
{
    Form2 form = new Form2();
    form.Size = new Size(250, 200);
    form.Show();
}
```

```vb
Private Sub Button1_Click(sender As Object, e As EventArgs)
    Dim form = New Form2 With {
        .Size = New Drawing.Size(250, 200)
    }
    form.Show()
End Sub
```

<span data-ttu-id="cb1af-131">`Size` が手動で設定されていない場合、フォームの既定のサイズは、デザイン時に設定されたものになります。</span><span class="sxs-lookup"><span data-stu-id="cb1af-131">If the `Size` isn't manually set, the form's default size is what it was set to during design-time.</span></span>

## <a name="position-with-the-designer"></a><span data-ttu-id="cb1af-132">デザイナーで位置を設定する</span><span class="sxs-lookup"><span data-stu-id="cb1af-132">Position with the designer</span></span>

<span data-ttu-id="cb1af-133">フォーム インスタンスが作成されて表示されるときのフォームの初期位置は、<xref:System.Windows.Forms.Form.StartPosition%2A> プロパティによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="cb1af-133">When a form instance is created and displayed, the initial location of the form is determined by the <xref:System.Windows.Forms.Form.StartPosition%2A> property.</span></span> <span data-ttu-id="cb1af-134"><xref:System.Windows.Forms.Form.Location%2A> プロパティには、フォームの現在の位置が保持されています。</span><span class="sxs-lookup"><span data-stu-id="cb1af-134">The <xref:System.Windows.Forms.Form.Location%2A> property holds the current location the form.</span></span> <span data-ttu-id="cb1af-135">どちらのプロパティも、デザイナーを使用して設定できます。</span><span class="sxs-lookup"><span data-stu-id="cb1af-135">Both properties can be set through the designer.</span></span>

:::image type="content" source="media/how-to-position-and-resize/startposition.png" alt-text="開始位置が強調表示されている Visual Studio のプロパティ ペイン":::

| <span data-ttu-id="cb1af-137">FormStartPosition 列挙型</span><span class="sxs-lookup"><span data-stu-id="cb1af-137">FormStartPosition Enum</span></span> | <span data-ttu-id="cb1af-138">説明</span><span class="sxs-lookup"><span data-stu-id="cb1af-138">Description</span></span>                                                                                                      |
|------------------------|------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="cb1af-139">CenterParent</span><span class="sxs-lookup"><span data-stu-id="cb1af-139">CenterParent</span></span>           | <span data-ttu-id="cb1af-140">フォームは、親フォームの境界内の中央に配置されます。</span><span class="sxs-lookup"><span data-stu-id="cb1af-140">The form is centered within the bounds of its parent form.</span></span>                                                       |
| <span data-ttu-id="cb1af-141">CenterScreen</span><span class="sxs-lookup"><span data-stu-id="cb1af-141">CenterScreen</span></span>           | <span data-ttu-id="cb1af-142">フォームは現在の表示の中央に配置されます。</span><span class="sxs-lookup"><span data-stu-id="cb1af-142">The form is centered on the current display.</span></span>                                                                     |
| <span data-ttu-id="cb1af-143">手動</span><span class="sxs-lookup"><span data-stu-id="cb1af-143">Manual</span></span>                 | <span data-ttu-id="cb1af-144">フォームの位置は、[Location](xref:System.Windows.Forms.Form.Location%2A) プロパティによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="cb1af-144">The position of the form is determined by the [Location](xref:System.Windows.Forms.Form.Location%2A) property.</span></span>   |
| <span data-ttu-id="cb1af-145">WindowsDefaultBounds</span><span class="sxs-lookup"><span data-stu-id="cb1af-145">WindowsDefaultBounds</span></span>   | <span data-ttu-id="cb1af-146">フォームは、Windows の既定の位置に配置され、Windows によって決定される既定のサイズに設定されます。</span><span class="sxs-lookup"><span data-stu-id="cb1af-146">The form is positioned at the Windows default location and is resized to the default size determined by Windows.</span></span> |
| <span data-ttu-id="cb1af-147">WindowsDefaultLocation</span><span class="sxs-lookup"><span data-stu-id="cb1af-147">WindowsDefaultLocation</span></span> | <span data-ttu-id="cb1af-148">フォームは、Windows の既定の位置に配置され、サイズは変更されません。</span><span class="sxs-lookup"><span data-stu-id="cb1af-148">The form is positioned at the Windows default location and isn't resized.</span></span>                                        |

<span data-ttu-id="cb1af-149">[CenterParent](xref:System.Windows.Forms.FormStartPosition.CenterParent) の値は、マルチドキュメント インターフェイス (MDI) の子フォームであるフォーム、または <xref:System.Windows.Window.ShowDialog%2A> メソッドで表示される通常のフォームに対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="cb1af-149">The [CenterParent](xref:System.Windows.Forms.FormStartPosition.CenterParent) value only works with forms that are either a multiple document interface (MDI) child form, or a normal form that is displayed with the <xref:System.Windows.Window.ShowDialog%2A> method.</span></span> <span data-ttu-id="cb1af-150">`CenterParent` は、<xref:System.Windows.Window.Show%2A> メソッドで表示される通常のフォームには適用されません。</span><span class="sxs-lookup"><span data-stu-id="cb1af-150">`CenterParent` has no affect on a normal form that is displayed with the <xref:System.Windows.Window.Show%2A> method.</span></span> <span data-ttu-id="cb1af-151">フォーム (`form` 変数) を別のフォーム (`parentForm` 変数) の中央に配置するには、次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="cb1af-151">To center a form (`form` variable) to another form (`parentForm` variable), use the following code:</span></span>

```csharp
form.StartPosition = FormStartPosition.Manual;
form.Location = new Point(parentForm.Width / 2 - form.Width / 2 + parentForm.Location.X,
                          parentForm.Height / 2 - form.Height / 2 + parentForm.Location.Y);
form.Show();
```

```vb
form.StartPosition = Windows.Forms.FormStartPosition.CenterParent.Manual
form.Location = New Drawing.Point(parentForm.Width / 2 - form.Width / 2 + parentForm.Location.X,
                                  parentForm.Height / 2 - form.Height / 2 + parentForm.Location.Y)

form.Show()
```

## <a name="position-with-code"></a><span data-ttu-id="cb1af-152">コードで位置を設定する</span><span class="sxs-lookup"><span data-stu-id="cb1af-152">Position with code</span></span>

<span data-ttu-id="cb1af-153">デザイナーを使用するとフォームの開始位置を設定できますが、コードを使用すると、開始位置モードを変更したり、位置を手動で設定したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="cb1af-153">Even though the designer can be used to set the starting location of a form, you can use code either change the starting position mode or set the location manually.</span></span> <span data-ttu-id="cb1af-154">コードを使用したフォームの位置の設定は、画面や他のフォームを基準にしてフォームの位置とサイズを手動で設定する必要がある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="cb1af-154">Using code to position a form is useful if you need to manually position and size a form in relation to the screen or other forms.</span></span>

### <a name="move-the-current-form"></a><span data-ttu-id="cb1af-155">現在のフォームを移動する</span><span class="sxs-lookup"><span data-stu-id="cb1af-155">Move the current form</span></span>

<span data-ttu-id="cb1af-156">フォームのコンテキスト内でコードが実行されている限り、現在のフォームを移動できます。</span><span class="sxs-lookup"><span data-stu-id="cb1af-156">You can move the current form as long as the code is running within the context of the form.</span></span> <span data-ttu-id="cb1af-157">たとえば、ボタンを含む `Form1` がある場合、それがクリックされたら `Click` イベント ハンドラーを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="cb1af-157">For example, if you have `Form1` with a button on it, that when clicked invokes the `Click` event handler.</span></span> <span data-ttu-id="cb1af-158">この例では、ハンドラーにより、<xref:System.Windows.Forms.Form.Location%2A> プロパティが設定されることで、フォームの位置が画面の左上に変更されます。</span><span class="sxs-lookup"><span data-stu-id="cb1af-158">The handler in this example changes the location of the form to the top-left of the screen by setting the <xref:System.Windows.Forms.Form.Location%2A> property:</span></span>

```csharp
private void button1_Click(object sender, EventArgs e) =>
    Location = new Point(0, 0);
```

```vb
Private Sub Button1_Click(sender As Object, e As EventArgs)
    Location = New Drawing.Point(0, 0)
End Sub
```

### <a name="position-a-different-form"></a><span data-ttu-id="cb1af-159">別のフォームを配置する</span><span class="sxs-lookup"><span data-stu-id="cb1af-159">Position a different form</span></span>

<span data-ttu-id="cb1af-160">別のフォームを作成した後、フォームを参照する変数を使用して、その位置を変更できます。</span><span class="sxs-lookup"><span data-stu-id="cb1af-160">You can change the location of another form after it's created by using the variable referencing the form.</span></span> <span data-ttu-id="cb1af-161">たとえば、2 つのフォーム `Form1` (この例でのスタートアップ フォーム) と `Form2` があるとします。</span><span class="sxs-lookup"><span data-stu-id="cb1af-161">For example, let's say you have two forms, `Form1` (the startup form in this example) and `Form2`.</span></span> <span data-ttu-id="cb1af-162">`Form1` には、クリックされると `Click` イベントを呼び出すボタンがあります。</span><span class="sxs-lookup"><span data-stu-id="cb1af-162">`Form1` has a button that when clicked, invokes the `Click` event.</span></span> <span data-ttu-id="cb1af-163">このイベントのハンドラーにより、`Form2` フォームの新しいインスタンスが作成されて、サイズが設定されます。</span><span class="sxs-lookup"><span data-stu-id="cb1af-163">The handler of this event creates a new instance of the `Form2` form and sets the size:</span></span>

```csharp
private void button1_Click(object sender, EventArgs e)
{
    Form2 form = new Form2();
    form.Size = new Size(250, 200);
    form.Show();
}
```

```vb
Private Sub Button1_Click(sender As Object, e As EventArgs)
    Dim form = New Form2 With {
        .Size = New Drawing.Size(250, 200)
    }
    form.Show()
End Sub
```

<span data-ttu-id="cb1af-164">`Size` が設定されていない場合、フォームの既定のサイズは、デザイン時に設定されたものになります。</span><span class="sxs-lookup"><span data-stu-id="cb1af-164">If the `Size` isn't set, the form's default size is what it was set to at design-time.</span></span>

## <a name="see-also"></a><span data-ttu-id="cb1af-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="cb1af-165">See also</span></span>

- [<span data-ttu-id="cb1af-166">プロジェクトにフォームを追加する方法 (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="cb1af-166">How to add a form to a project (Windows Forms .NET)</span></span>](how-to-add.md)
- [<span data-ttu-id="cb1af-167">イベントの概要 (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="cb1af-167">Events overview (Windows Forms .NET)</span></span>](events.md)
- [<span data-ttu-id="cb1af-168">コントロールの位置とレイアウト (Windows フォーム .NET)</span><span class="sxs-lookup"><span data-stu-id="cb1af-168">Position and layout of controls (Windows Forms .NET)</span></span>](../controls/layout.md)
