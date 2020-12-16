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
# <a name="how-to-position-and-size-a-form-windows-forms-net"></a>フォームの位置とサイズを設定する方法 (Windows フォーム .NET)

フォームが作成されると、サイズと位置は最初に既定値に設定されます。 フォームの既定のサイズの幅と高さは、通常、_800x500_ ピクセルです。 フォームが表示されるときの最初の位置は、いくつかの異なる設定によって異なります。

フォームのサイズは、デザイン時に Visual Studio を使用して変更したり、実行時にコードを使用して変更したりできます。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="resize-with-the-designer"></a>デザイナーでサイズを変更する

プロジェクトに[新しいフォームを追加](how-to-add.md)した後、フォームのサイズは 2 つの異なる方法で設定されます。 まず、デザイナーでサイズ グリップを使用して設定できます。 右端、下端、または角をドラッグすることで、フォームのサイズを変更できます。

:::image type="content" source="media/how-to-position-and-resize/designer-grips.png" alt-text="ソリューション エクスプローラーを右クリックし、グリップを使用して Windows フォーム プロジェクトに新しいフォームを追加する":::

デザイナーが開いている間にフォームのサイズを変更する 2 番目の方法は、プロパティ ペインを使用することです。 フォームを選択し、Visual Studio で **[プロパティ]** ペインを見つけます。 下にスクロールして **[サイズ]** を展開します。 **[幅]** と **[高さ]** を手動で設定できます。

:::image type="content" source="media/how-to-position-and-resize/designer-properties-size.png" alt-text="ソリューション エクスプローラーを右クリックして、Windows フォーム プロジェクトに新しいフォームを追加する":::

## <a name="resize-in-code"></a>コードでサイズを変更する

フォームの初期サイズをデザイナーで設定した場合でも、コードを使用してサイズを変更できます。 コードを使用したフォームのサイズの変更は、アプリケーションによってフォームの既定のサイズが不十分であると判断された場合に便利です。

フォームのサイズを変更するには、フォームの幅と高さを表す <xref:System.Windows.Forms.Form.Size%2A> を変更します。

### <a name="resize-the-current-form"></a>現在のフォームのサイズを変更する

フォームのコンテキスト内でコードが実行されている限り、現在のフォームのサイズを変更できます。 たとえば、ボタンを含む `Form1` がある場合、それがクリックされたら `Click` イベント ハンドラーを呼び出して、フォームのサイズを変更します。

```csharp
private void button1_Click(object sender, EventArgs e) =>
    Size = new Size(250, 200);
```

```vb
Private Sub Button1_Click(sender As Object, e As EventArgs)
    Size = New Drawing.Size(250, 200)
End Sub
```

### <a name="resize-a-different-form"></a>別のフォームのサイズを変更する

別のフォームを作成した後、フォームを参照する変数を使用して、そのサイズを変更できます。 たとえば、2 つのフォーム `Form1` (この例でのスタートアップ フォーム) と `Form2` があるとします。 `Form1` には、クリックされると `Click` イベントを呼び出すボタンがあります。 このイベントのハンドラーにより、`Form2` フォームの新しいインスタンスが作成され、サイズが設定されてから、それが表示されます。

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

`Size` が手動で設定されていない場合、フォームの既定のサイズは、デザイン時に設定されたものになります。

## <a name="position-with-the-designer"></a>デザイナーで位置を設定する

フォーム インスタンスが作成されて表示されるときのフォームの初期位置は、<xref:System.Windows.Forms.Form.StartPosition%2A> プロパティによって決定されます。 <xref:System.Windows.Forms.Form.Location%2A> プロパティには、フォームの現在の位置が保持されています。 どちらのプロパティも、デザイナーを使用して設定できます。

:::image type="content" source="media/how-to-position-and-resize/startposition.png" alt-text="開始位置が強調表示されている Visual Studio のプロパティ ペイン":::

| FormStartPosition 列挙型 | 説明                                                                                                      |
|------------------------|------------------------------------------------------------------------------------------------------------------|
| CenterParent           | フォームは、親フォームの境界内の中央に配置されます。                                                       |
| CenterScreen           | フォームは現在の表示の中央に配置されます。                                                                     |
| 手動                 | フォームの位置は、[Location](xref:System.Windows.Forms.Form.Location%2A) プロパティによって決定されます。   |
| WindowsDefaultBounds   | フォームは、Windows の既定の位置に配置され、Windows によって決定される既定のサイズに設定されます。 |
| WindowsDefaultLocation | フォームは、Windows の既定の位置に配置され、サイズは変更されません。                                        |

[CenterParent](xref:System.Windows.Forms.FormStartPosition.CenterParent) の値は、マルチドキュメント インターフェイス (MDI) の子フォームであるフォーム、または <xref:System.Windows.Window.ShowDialog%2A> メソッドで表示される通常のフォームに対してのみ機能します。 `CenterParent` は、<xref:System.Windows.Window.Show%2A> メソッドで表示される通常のフォームには適用されません。 フォーム (`form` 変数) を別のフォーム (`parentForm` 変数) の中央に配置するには、次のコードを使用します。

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

## <a name="position-with-code"></a>コードで位置を設定する

デザイナーを使用するとフォームの開始位置を設定できますが、コードを使用すると、開始位置モードを変更したり、位置を手動で設定したりすることができます。 コードを使用したフォームの位置の設定は、画面や他のフォームを基準にしてフォームの位置とサイズを手動で設定する必要がある場合に便利です。

### <a name="move-the-current-form"></a>現在のフォームを移動する

フォームのコンテキスト内でコードが実行されている限り、現在のフォームを移動できます。 たとえば、ボタンを含む `Form1` がある場合、それがクリックされたら `Click` イベント ハンドラーを呼び出します。 この例では、ハンドラーにより、<xref:System.Windows.Forms.Form.Location%2A> プロパティが設定されることで、フォームの位置が画面の左上に変更されます。

```csharp
private void button1_Click(object sender, EventArgs e) =>
    Location = new Point(0, 0);
```

```vb
Private Sub Button1_Click(sender As Object, e As EventArgs)
    Location = New Drawing.Point(0, 0)
End Sub
```

### <a name="position-a-different-form"></a>別のフォームを配置する

別のフォームを作成した後、フォームを参照する変数を使用して、その位置を変更できます。 たとえば、2 つのフォーム `Form1` (この例でのスタートアップ フォーム) と `Form2` があるとします。 `Form1` には、クリックされると `Click` イベントを呼び出すボタンがあります。 このイベントのハンドラーにより、`Form2` フォームの新しいインスタンスが作成されて、サイズが設定されます。

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

`Size` が設定されていない場合、フォームの既定のサイズは、デザイン時に設定されたものになります。

## <a name="see-also"></a>関連項目

- [プロジェクトにフォームを追加する方法 (Windows フォーム .NET)](how-to-add.md)
- [イベントの概要 (Windows フォーム .NET)](events.md)
- [コントロールの位置とレイアウト (Windows フォーム .NET)](../controls/layout.md)
