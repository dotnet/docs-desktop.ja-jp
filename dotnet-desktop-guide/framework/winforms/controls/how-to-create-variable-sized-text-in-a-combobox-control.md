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
# <a name="how-to-create-variable-sized-text-in-a-combobox-control"></a><span data-ttu-id="b1571-102">方法: ComboBox コントロールにサイズ変更可能なテキストを作成する</span><span class="sxs-lookup"><span data-stu-id="b1571-102">How to: Create Variable Sized Text in a ComboBox Control</span></span>
<span data-ttu-id="b1571-103">この例は、コントロール内のテキストのカスタム描画を示して <xref:System.Windows.Forms.ComboBox> います。</span><span class="sxs-lookup"><span data-stu-id="b1571-103">This example demonstrates custom drawing of text in a <xref:System.Windows.Forms.ComboBox> control.</span></span> <span data-ttu-id="b1571-104">項目が特定の条件を満たしている場合は、大きいフォントで描画され、赤色になります。</span><span class="sxs-lookup"><span data-stu-id="b1571-104">When an item meets a certain criteria, it is drawn in a larger font and turned red.</span></span>

## <a name="example"></a><span data-ttu-id="b1571-105">例</span><span class="sxs-lookup"><span data-stu-id="b1571-105">Example</span></span>

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

## <a name="compiling-the-code"></a><span data-ttu-id="b1571-106">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="b1571-106">Compiling the Code</span></span>
 <span data-ttu-id="b1571-107">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b1571-107">This example requires:</span></span>

- <span data-ttu-id="b1571-108">Windows フォーム。</span><span class="sxs-lookup"><span data-stu-id="b1571-108">A Windows form.</span></span>

- <span data-ttu-id="b1571-109"><xref:System.Windows.Forms.ComboBox> `ListBox1` プロパティに3つの項目を持つという名前のコントロール。 <xref:System.Windows.Forms.ComboBox.Items%2A></span><span class="sxs-lookup"><span data-stu-id="b1571-109">A <xref:System.Windows.Forms.ComboBox> control named `ListBox1` with three items in the <xref:System.Windows.Forms.ComboBox.Items%2A> property.</span></span> <span data-ttu-id="b1571-110">この例では、3つの項目に名前が付けられて `"One", Two", and Three"` います。</span><span class="sxs-lookup"><span data-stu-id="b1571-110">In this example, the three items are named `"One", Two", and Three"`.</span></span> <span data-ttu-id="b1571-111"><xref:System.Windows.Forms.ComboBox.DrawMode%2A>のプロパティは、 `ComboBox1` に設定する必要があり <xref:System.Windows.Forms.DrawMode.OwnerDrawVariable> ます。</span><span class="sxs-lookup"><span data-stu-id="b1571-111">The <xref:System.Windows.Forms.ComboBox.DrawMode%2A> property of `ComboBox1` must be set to <xref:System.Windows.Forms.DrawMode.OwnerDrawVariable>.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b1571-112">この手法はコントロールにも適用 <xref:System.Windows.Forms.ListBox> できます。のをに置き換えることができ <xref:System.Windows.Forms.ListBox> <xref:System.Windows.Forms.ComboBox> ます。</span><span class="sxs-lookup"><span data-stu-id="b1571-112">This technique is also applicable to the <xref:System.Windows.Forms.ListBox> control — you can substitute a <xref:System.Windows.Forms.ListBox> for the <xref:System.Windows.Forms.ComboBox>.</span></span>

- <span data-ttu-id="b1571-113"><xref:System.Windows.Forms?displayProperty=nameWithType> 名前空間と <xref:System.Drawing?displayProperty=nameWithType> 名前空間への参照。</span><span class="sxs-lookup"><span data-stu-id="b1571-113">References to the <xref:System.Windows.Forms?displayProperty=nameWithType> and <xref:System.Drawing?displayProperty=nameWithType> namespaces.</span></span>

## <a name="see-also"></a><span data-ttu-id="b1571-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="b1571-114">See also</span></span>

- <xref:System.Windows.Forms.ComboBox.DrawItem>
- <xref:System.Windows.Forms.DrawItemEventArgs>
- <xref:System.Windows.Forms.ComboBox.MeasureItem>
- [<span data-ttu-id="b1571-115">組み込みのオーナー描画サポートを備えたコントロール</span><span class="sxs-lookup"><span data-stu-id="b1571-115">Controls with Built-In Owner-Drawing Support</span></span>](controls-with-built-in-owner-drawing-support.md)
- [<span data-ttu-id="b1571-116">ListBox コントロール</span><span class="sxs-lookup"><span data-stu-id="b1571-116">ListBox Control</span></span>](listbox-control-windows-forms.md)
- [<span data-ttu-id="b1571-117">ComboBox コントロール</span><span class="sxs-lookup"><span data-stu-id="b1571-117">ComboBox Control</span></span>](combobox-control-windows-forms.md)
