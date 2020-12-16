---
title: ドラッグ アンド ドロップによるマウスの動作
description: マウスを使ってドラッグ アンド ドロップを実行する方法など、Windows フォーム上のドラッグ アンド ドロップの動作について説明します。
ms.date: 10/26/2020
ms.topic: conceptual
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag and drop [Windows Forms], Windows Forms
- Windows Forms, drag and drop
ms.openlocfilehash: d434b0f0e80c610fffeea26a6fff44b43ca07fed
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96942162"
---
# <a name="drag-and-drop-mouse-behavior-overview-windows-forms-net"></a>ドラッグ アンド ドロップによるマウス動作の概要 (Windows フォーム .NET)

Windows フォームには、ドラッグ アンド ドロップの動作を実装する一連のメソッド、イベント、およびクラスが含まれています。 このトピックでは、Windows フォームでのドラッグ アンド ドロップのサポートの概要について説明します。<!-- TODO Also see [Drag-and-Drop Operations and Clipboard Support](./advanced/drag-and-drop-operations-and-clipboard-support.md).-->

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="drag-and-drop-events"></a>ドラッグ アンド ドロップのイベント

ドラッグ アンド ドロップ操作のイベントには、ドラッグ アンド ドロップ操作の現在のターゲットで発生するイベントと、ドラッグ アンド ドロップ操作のソースで発生するイベントの 2 つのカテゴリがあります。 ドラッグ アンド ドロップ操作を実行するには、これらのイベントを処理する必要があります。 これらのイベントのイベント引数で使用できる情報を操作することにより、ドラッグ アンド ドロップ操作を簡単に容易にすることができます。

## <a name="events-on-the-current-drop-target"></a>現在のドロップ ターゲットのイベント

次の表は、ドラッグ アンド ドロップ操作の現在のターゲットで発生するイベントを示します。

| マウス イベント                                   | 説明                                                                                                                                                                                            |
|-----------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <xref:System.Windows.Forms.Control.DragEnter> | このイベントは、オブジェクトがコントロールの境界内にドラッグされると発生します。 このイベントのハンドラーは、型 <xref:System.Windows.Forms.DragEventArgs> の引数を受け取ります。                              |
| <xref:System.Windows.Forms.Control.DragOver>  | このイベントは、マウス ポインターがコントロールの境界内にある間にオブジェクトがドラッグされるときに発生します。 このイベントのハンドラーは、型 <xref:System.Windows.Forms.DragEventArgs> の引数を受け取ります。 |
| <xref:System.Windows.Forms.Control.DragDrop>  | このイベントは、ドラッグ アンド ドロップ操作が完了したときに発生します。 このイベントのハンドラーは、型 <xref:System.Windows.Forms.DragEventArgs> の引数を受け取ります。                                      |
| <xref:System.Windows.Forms.Control.DragLeave> | このイベントは、オブジェクトがコントロールの境界外にドラッグされたときに発生します。 このイベントのハンドラーは、型 <xref:System.EventArgs> の引数を受け取ります。                                              |

<xref:System.Windows.Forms.DragEventArgs> クラスは、マウスのポインターの場所、マウス ボタンとキーボードの修飾子キーの現在の状態、ドラッグされているデータ、およびドラッグ イベントのソースによって許可される操作と操作に対するターゲットのドロップの効果を指定する <xref:System.Windows.Forms.DragDropEffects> の値を提供します。

## <a name="events-on-the-drop-source"></a>ドロップ ソースのイベント

次の表は、ドラッグ アンド ドロップ操作のソースで発生するイベントを示します。

|マウス イベント|説明|
|-----------------|-----------------|
|<xref:System.Windows.Forms.Control.GiveFeedback>|このイベントは、ドラッグ操作中に発生します。 マウス ポインターを変更するなど、ドラッグ アンド ドロップ操作が実行されていることを示す視覚上の手掛かりをユーザーに示す機会を提供します。 このイベントのハンドラーは、型 <xref:System.Windows.Forms.GiveFeedbackEventArgs> の引数を受け取ります。|
|<xref:System.Windows.Forms.Control.QueryContinueDrag>|このイベントは、ドラッグ アンド ドロップ操作中に発生し、ドラッグ ソースがドラッグ アンド ドロップ操作をキャンセルする必要があるかどうかを決定できるようにします。 このイベントのハンドラーは、型 <xref:System.Windows.Forms.QueryContinueDragEventArgs> の引数を受け取ります。|

<xref:System.Windows.Forms.QueryContinueDragEventArgs> クラスは、マウス ボタンとキーボードの修飾子キーの現在の状態、ESC キーを押したかどうかを指定する値、およびドラッグ アンド ドロップ操作を続行するかどうかを指定するために設定できる <xref:System.Windows.Forms.DragAction> の値を提供します。

## <a name="performing-drag-and-drop"></a>ドラッグ アンド ドロップの実行

ドラッグ アンド ドロップ操作には、**ドラッグ ソース** と **ドロップ ターゲット** という 2 つのコンポーネントが常に含まれています。 ドラッグ アンド ドロップ操作を開始するには、コントロールをソースとして指定し、<xref:System.Windows.Forms.Control.MouseDown> イベントを処理します。 イベント ハンドラーで、ドロップに関連付けられたデータと <xref:System.Windows.DragDropEffects> 値を指定して <xref:System.Windows.DragDrop.DoDragDrop%2A> メソッドを呼び出します。

ターゲット コントロールの <xref:System.Windows.Forms.Control.AllowDrop> プロパティを `true` に設定して、そのコントロールでドラッグ アンド ドロップ操作を受け入れることができるようにします。 ターゲットによって 2 つのイベントが処理されます。1 つ目は、<xref:System.Windows.Forms.Control.DragOver> など、コントロールに対して行われているドラッグに応答するイベントです。 また、2 つ目は、ドロップ アクション自体のイベントです (<xref:System.Windows.Forms.Control.DragDrop>)。

次の例は、<xref:System.Windows.Forms.Label> コントロールから <xref:System.Windows.Forms.TextBox> へのドラッグを示しています。 ドラッグが完了すると、`TextBox` は、ラベルのテキストを自身に割り当てることで応答します。

```csharp
// Initiate the drag
private void label1_MouseDown(object sender, MouseEventArgs e) =>
    DoDragDrop(((Label)sender).Text, DragDropEffects.All);

// Set the effect filter and allow the drop on this control
private void textBox1_DragOver(object sender, DragEventArgs e) =>
    e.Effect = DragDropEffects.All;

// React to the drop on this control
private void textBox1_DragDrop(object sender, DragEventArgs e) =>
    textBox1.Text = (string)e.Data.GetData(typeof(string));
```

```vb
' Initiate the drag
Private Sub Label1_MouseDown(sender As Object, e As MouseEventArgs)
    DoDragDrop(DirectCast(sender, Label).Text, DragDropEffects.All)
End Sub

' Set the effect filter and allow the drop on this control
Private Sub TextBox1_DragOver(sender As Object, e As DragEventArgs)
    e.Effect = DragDropEffects.All
End Sub

' React to the drop on this control
Private Sub TextBox1_DragDrop(sender As Object, e As DragEventArgs)
    TextBox1.Text = e.Data.GetData(GetType(String))
End Sub
```

ドラッグの効果の詳細については、<xref:System.Windows.Forms.DragEventArgs.Data%2A> と <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A> に関する記事を参照してください。

## <a name="see-also"></a>関連項目

- [マウスの使用の概要 (Windows フォーム .NET)](overview.md)
- <xref:System.Windows.Forms.Control.DragDrop?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.DragEnter?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.DragLeave?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.DragOver?displayProperty=nameWithType>
