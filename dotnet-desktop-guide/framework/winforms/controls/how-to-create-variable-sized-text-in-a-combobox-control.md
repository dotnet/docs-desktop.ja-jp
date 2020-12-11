---
title: '方法: ComboBox コントロールにサイズ変更可能なテキストを作成する'
ms.date: 03/30/2017
dev_langs:
- vb
helpviewer_keywords:
- text [Windows Forms], drawing in combo boxes
- examples [Windows Forms], ComboBox control
- combo boxes [Windows Forms], drawing text
- ComboBox control [Windows Forms], examples [C#]
- ComboBox control [Windows Forms], drawing custom text
ms.assetid: ce39b9ea-e626-49fe-bd5a-f567f6d157df
ms.openlocfilehash: acc5ee47536772d98fcfe98849335933c24a41d7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980883"
---
# <a name="how-to-create-variable-sized-text-in-a-combobox-control"></a>方法: ComboBox コントロールにサイズ変更可能なテキストを作成する
この例は、コントロール内のテキストのカスタム描画を示して <xref:System.Windows.Forms.ComboBox> います。 項目が特定の条件を満たしている場合は、大きいフォントで描画され、赤色になります。

## <a name="example"></a>例

```vb
Private Sub ComboBox1_MeasureItem(ByVal sender As Object, ByVal e As _
System.Windows.Forms.MeasureItemEventArgs) Handles ComboBox1.MeasureItem
    Dim bFont As New Font("Arial", 8, FontStyle.Bold)
    Dim lFont As New Font("Arial", 12, FontStyle.Bold)
    Dim siText As SizeF

    If ComboBox1.Items().Item(e.Index) = "Two" Then
        siText = e.Graphics.MeasureString(ComboBox1.Items().Item(e.Index), _
lFont)
    Else
        siText = e.Graphics.MeasureString(ComboBox1.Items().Item(e.Index), bFont)
    End If

    e.ItemHeight = siText.Height
    e.ItemWidth = siText.Width
End Sub

Private Sub ComboBox1_DrawItem(ByVal sender As Object, ByVal e As _
System.Windows.Forms.DrawItemEventArgs) Handles ComboBox1.DrawItem
    Dim g As Graphics = e.Graphics
    Dim bFont As New Font("Arial", 8, FontStyle.Bold)
    Dim lFont As New Font("Arial", 12, FontStyle.Bold)

    If ComboBox1.Items().Item(e.Index) = "Two" Then
        g.DrawString(ComboBox1.Items.Item(e.Index), lfont, Brushes.Red, _
e.Bounds.X, e.Bounds.Y)
    Else
        g.DrawString(ComboBox1.Items.Item(e.Index), bFont, Brushes.Black, e.Bounds.X, e.Bounds.Y)
    End If
End Sub
```

## <a name="compiling-the-code"></a>コードのコンパイル
 この例で必要な要素は次のとおりです。

- Windows フォーム。

- <xref:System.Windows.Forms.ComboBox> `ListBox1` プロパティに3つの項目を持つという名前のコントロール。 <xref:System.Windows.Forms.ComboBox.Items%2A> この例では、3つの項目に名前が付けられて `"One", Two", and Three"` います。 <xref:System.Windows.Forms.ComboBox.DrawMode%2A>のプロパティは、 `ComboBox1` に設定する必要があり <xref:System.Windows.Forms.DrawMode.OwnerDrawVariable> ます。

    > [!NOTE]
    > この手法はコントロールにも適用 <xref:System.Windows.Forms.ListBox> できます。のをに置き換えることができ <xref:System.Windows.Forms.ListBox> <xref:System.Windows.Forms.ComboBox> ます。

- <xref:System.Windows.Forms?displayProperty=nameWithType> 名前空間と <xref:System.Drawing?displayProperty=nameWithType> 名前空間への参照。

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.ComboBox.DrawItem>
- <xref:System.Windows.Forms.DrawItemEventArgs>
- <xref:System.Windows.Forms.ComboBox.MeasureItem>
- [組み込みのオーナー描画サポートを備えたコントロール](controls-with-built-in-owner-drawing-support.md)
- [ListBox コントロール](listbox-control-windows-forms.md)
- [ComboBox コントロール](combobox-control-windows-forms.md)
