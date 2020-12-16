---
title: マウス イベントの使用
description: マウス イベントを使用したマウス入力の処理の概要。 各イベントは、関連付けられたデータを提供する場合があります。 この記事では、マウス関連のイベントの一覧を提供します。
ms.date: 10/26/2020
ms.topic: conceptual
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Click event [Windows Forms]
- mouse [Windows Forms], mouse events
- Click event
- MouseClick event
- DoubleClick event
- MouseDown event
- MouseEnter event
- MouseHover event
- MouseLeave event
- MouseMove event
- MouseUp event
- MouseWheel event
- mouse events
- events [Windows Forms], mouse
ms.openlocfilehash: 84d3fc0ef8bca25defead65590d1e50369e628b4
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96942170"
---
# <a name="using-mouse-events-windows-forms-net"></a>マウス イベントの使用 (Windows フォーム .NET)

多くの Windows フォーム プログラムでは、マウス イベントに対処することでマウス入力が処理されます。 この記事では、どのような場合に各イベントを使用するか、また各イベントがどのようなデータを提供するかについての詳細を含め、マウス イベントの概要について説明します。 一般的なイベントの詳細については、「[イベントの概要 (Windows フォーム .NET)](../forms/events.md)」を参照してください。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="mouse-events"></a>マウス イベント

マウス入力に応答する主な方法は、マウス イベントを処理することです。 次の表は、マウス イベントと、それがいつ発生するかの説明を示しています。

| マウス イベント                                          | 説明                                             |
|------------------------------------------------------|---------------------------------------------------------|
| <xref:System.Windows.Forms.Control.Click>            | このイベントは、マウス ボタンが離されたとき (通常は <xref:System.Windows.Forms.Control.MouseUp> イベントの前) に発生します。 このイベントのハンドラーは、型 <xref:System.EventArgs> の引数を受け取ります。 このイベントは、クリックがいつ発生したかを判断する必要がある場合にのみ処理します。                                                                             |
| <xref:System.Windows.Forms.Control.MouseClick>       | このイベントは、ユーザーがマウスでコントロールをクリックすると発生します。 このイベントのハンドラーは、型 <xref:System.Windows.Forms.MouseEventArgs> の引数を受け取ります。 クリックが発生したときにマウスに関する情報を取得する必要がある場合に、このイベントを処理します。                                                                                                   |
| <xref:System.Windows.Forms.Control.DoubleClick>      | このイベントは、コントロールがダブルクリックされたときに発生します。 このイベントのハンドラーは、型 <xref:System.EventArgs> の引数を受け取ります。 このイベントは、ダブルクリックがいつ発生したかを判断する必要がある場合にのみ処理します。                                                                                                                                             |
| <xref:System.Windows.Forms.Control.MouseDoubleClick> | このイベントは、ユーザーがマウスでコントロールをダブルクリックすると発生します。 このイベントのハンドラーは、型 <xref:System.Windows.Forms.MouseEventArgs> の引数を受け取ります。 ダブルクリックが発生したときにマウスに関する情報を取得する必要がある場合に、このイベントを処理します。                                                                                     |
| <xref:System.Windows.Forms.Control.MouseDown>        | このイベントは、マウス ポインターがコントロール上にあるときに、ユーザーがマウス ボタンを押すと発生します。 このイベントのハンドラーは、型 <xref:System.Windows.Forms.MouseEventArgs> の引数を受け取ります。                                                                                                                                                            |
| <xref:System.Windows.Forms.Control.MouseEnter>       | このイベントは、コントロールの種類に応じて、マウス ポインターがコントロールの境界線またはクライアント領域に入ったときに発生します。 このイベントのハンドラーは、型 <xref:System.EventArgs> の引数を受け取ります。                                                                                                                                                     |
| <xref:System.Windows.Forms.Control.MouseHover>       | このイベントは、マウス ポインターがコントロールの上に置かれたときに発生します。 このイベントのハンドラーは、型 <xref:System.EventArgs> の引数を受け取ります。                                                                                                                                                                                                      |
| <xref:System.Windows.Forms.Control.MouseLeave>       | このイベントは、コントロールの種類に応じて、マウス ポインターがコントロールの境界線またはクライアント領域から離れたときに発生します。 このイベントのハンドラーは、型 <xref:System.EventArgs> の引数を受け取ります。                                                                                                                                                 |
| <xref:System.Windows.Forms.Control.MouseMove>        | このイベントは、マウス ポインターがコントロール上で動かされたときに発生します。 このイベントのハンドラーは、型 <xref:System.Windows.Forms.MouseEventArgs> の引数を受け取ります。                                                                                                                                                                                   |
| <xref:System.Windows.Forms.Control.MouseUp>          | このイベントは、マウス ポインターがコントロール上にあり、ユーザーがマウス ボタンを離したときに発生します。 このイベントのハンドラーは、型 <xref:System.Windows.Forms.MouseEventArgs> の引数を受け取ります。                                                                                                                                                           |
| <xref:System.Windows.Forms.Control.MouseWheel>       | このイベントは、このコントロールの上にフォーカスがある状態でユーザーがマウス ホイールを使用したときに発生します。 このイベントのハンドラーは、型 <xref:System.Windows.Forms.MouseEventArgs> の引数を受け取ります。 <xref:System.Windows.Forms.MouseEventArgs> の <xref:System.Windows.Forms.MouseEventArgs.Delta%2A> プロパティを使用して、マウスのスクロール距離を決定できます。 |

## <a name="mouse-information"></a>マウスの情報

<xref:System.Windows.Forms.MouseEventArgs> は、マウス ボタンのクリック、およびマウスの動きの追跡に関連するマウス イベントのハンドラーに送信します。 <xref:System.Windows.Forms.MouseEventArgs> は、マウスのボタンが押された、およびマウスのホイールがスクロールされたといった、クライアント座標のマウス ポインターの場所を含む、マウスの現在の状態に関する情報を提供します。 マウス ポインターがコントロールの境界内に入った、または境界から出たときに発生するような、いくつかのマウスイベントは、それ以上の情報はなしで <xref:System.EventArgs> をイベント ハンドラーに送信します。

マウス ボタン、または、マウス ポインターの位置の現在の状態を確認して、マウス イベントの処理を回避する場合は、<xref:System.Windows.Forms.Control> クラスの <xref:System.Windows.Forms.Control.MouseButtons%2A> プロパティと <xref:System.Windows.Forms.Control.MousePosition%2A> プロパティも使用できます。 <xref:System.Windows.Forms.Control.MouseButtons%2A> は現在押されているマウス ボタンに関する情報を返します。 <xref:System.Windows.Forms.Control.MousePosition%2A> はマウス ポインターの画面の座標を返しますが、<xref:System.Windows.Forms.Cursor.Position%2A> によって返される値と同じです。

## <a name="converting-between-screen-and-client-coordinates"></a>画面の座標とクライアント座標の間の変換

マウスの位置情報は、クライアント座標の場合と画面の座標の場合があるため、ポインターの座標システムの変換が必要になることがあります。 これは、<xref:System.Windows.Forms.Control> クラスで利用できる <xref:System.Windows.Forms.Control.PointToClient%2A> メソッドと <xref:System.Windows.Forms.Control.PointToScreen%2A> メソッドを使用して簡単に実行できます。

## <a name="standard-click-event-behavior"></a>標準のクリック イベントの動作

マウスのクリック イベントを適切な順序で処理する場合は、Windows フォーム コントロールでクリック イベントが発生した順序を知る必要があります。 Windows フォームのコントロールはすべて、サポートされているマウス ボタンを押したときと離したときに同じ順序でクリック イベントを発生させますが、各コントロールについて、次のリストに記載する例外があります。 マウス ボタンのシングル クリックに対して発生したイベントの順序を次に示します。

01. <xref:System.Windows.Forms.Control.MouseDown> イベント。
01. <xref:System.Windows.Forms.Control.Click> イベント。
01. <xref:System.Windows.Forms.Control.MouseClick> イベント。
01. <xref:System.Windows.Forms.Control.MouseUp> イベント。

マウス ボタンのダブル クリックに対して発生したイベントの順序を次に示します。

01. <xref:System.Windows.Forms.Control.MouseDown> イベント。
01. <xref:System.Windows.Forms.Control.Click> イベント。
01. <xref:System.Windows.Forms.Control.MouseClick> イベント。
01. <xref:System.Windows.Forms.Control.MouseUp> イベント。
01. <xref:System.Windows.Forms.Control.MouseDown> イベント。
01. <xref:System.Windows.Forms.Control.DoubleClick> イベント。

    これは、対象のコントロールで <xref:System.Windows.Forms.ControlStyles.StandardDoubleClick> スタイルのビットが `true` に設定されているかどうかに応じて異なる場合があります。 <xref:System.Windows.Forms.ControlStyles> のビットの設定方法の詳細については、<xref:System.Windows.Forms.Control.SetStyle%2A> メソッドを参照してください。

01. <xref:System.Windows.Forms.Control.MouseDoubleClick> イベント。
01. <xref:System.Windows.Forms.Control.MouseUp> イベント。

### <a name="individual-controls"></a>個別のコントロール

次のコントロールは、標準のマウス クリック イベントの動作に準拠していません。

- <xref:System.Windows.Forms.Button>
- <xref:System.Windows.Forms.CheckBox>
- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.RadioButton>

  > [!NOTE]
  > <xref:System.Windows.Forms.ComboBox> コントロールについて、ユーザーが編集フィールド、ボタン、またはリスト内の項目をクリックすると、後述するイベントの動作が発生します。

  - **左クリック**: <xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick>
  - **右クリック**: クリック イベントは発生しません
  - **左ダブルクリック**: <xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick>
  - **右ダブルクリック**: クリック イベントは発生しません

- <xref:System.Windows.Forms.TextBox>、<xref:System.Windows.Forms.RichTextBox>、<xref:System.Windows.Forms.ListBox>、<xref:System.Windows.Forms.MaskedTextBox> および <xref:System.Windows.Forms.CheckedListBox> の各コントロール

  > [!NOTE]
  > ユーザーがこれらのコントロール内で任意の場所をクリックすると、後述するイベントの動作が発生します。

  - **左クリック**: <xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick>
  - **右クリック**: クリック イベントは発生しません
  - **左ダブルクリック**: <xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick>、<xref:System.Windows.Forms.Control.DoubleClick>、<xref:System.Windows.Forms.Control.MouseDoubleClick>
  - **右ダブルクリック**: クリック イベントは発生しません

- <xref:System.Windows.Forms.ListView> コントロール

  > [!NOTE]
  > ユーザーが <xref:System.Windows.Forms.ListView> コントロールの項目をクリックした場合のみ、後述するイベントの動作が発生します。 コントロールのその他の場所をクリックした場合、イベントは発生しません。 後述するイベントに加えて、<xref:System.Windows.Forms.ListView.BeforeLabelEdit> と <xref:System.Windows.Forms.ListView.AfterLabelEdit> のイベントがあり、<xref:System.Windows.Forms.ListView> コントロールによる検証を使用する場合のためにまとめておきます。

  - **左クリック**: <xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick>
  - **右クリック**: <xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick>
  - **左ダブルクリック**: <xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>、<xref:System.Windows.Forms.Control.MouseDoubleClick>
  - **右ダブルクリック**: <xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>、<xref:System.Windows.Forms.Control.MouseDoubleClick>

- <xref:System.Windows.Forms.TreeView> コントロール

  > [!NOTE]
  > ユーザーが項目自体をクリックするか、<xref:System.Windows.Forms.TreeView> コントロールの項目の右側をクリックした場合にのみ、後述するイベントの動作が発生します。 コントロールのその他の場所をクリックした場合、イベントは発生しません。 後述するイベントに加えて、<xref:System.Windows.Forms.TreeView.BeforeCheck>、<xref:System.Windows.Forms.TreeView.BeforeSelect>、<xref:System.Windows.Forms.TreeView.BeforeLabelEdit>、<xref:System.Windows.Forms.TreeView.AfterSelect>、<xref:System.Windows.Forms.TreeView.AfterCheck>、および <xref:System.Windows.Forms.TreeView.AfterLabelEdit> の各イベントがあり、<xref:System.Windows.Forms.TreeView> コントロールを持つ検証を使用する場合のためにまとめておきます。

  - **左クリック**: <xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick>
  - **右クリック**: <xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick>
  - **左ダブルクリック**: <xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>、<xref:System.Windows.Forms.Control.MouseDoubleClick>
  - **右ダブルクリック**: <xref:System.Windows.Forms.Control.Click>、<xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>、<xref:System.Windows.Forms.Control.MouseDoubleClick>

## <a name="painting-behavior-of-toggle-controls"></a>切り替えコントロールの描画の動作

<xref:System.Windows.Forms.ButtonBase> クラスから派生するコントロールなど、切り替えコントロールには、次のようなマウス クリック イベントと組み合わせた独自の描画の動作があります。

01. ユーザーがマウス ボタンを押します。
01. 押された状態で、コントロールが描画します。
01. <xref:System.Windows.Forms.Control.MouseDown> イベントが発生します。
01. ユーザーがマウス ボタンを離します。
01. 離した状態でコントロールが描画します。
01. <xref:System.Windows.Forms.Control.Click> イベントが発生します。
01. <xref:System.Windows.Forms.Control.MouseClick> イベントが発生します。
01. <xref:System.Windows.Forms.Control.MouseUp> イベントが発生します。

    > [!NOTE]
    > マウス ボタンが押されているときにユーザーがポインターを切り替えコントロールの外に移動した (例 : <xref:System.Windows.Forms.Button> コントロールを押しているときにマウスを移動した) 場合、離された状態で切り替えコントロールが描画し、<xref:System.Windows.Forms.Control.MouseUp> イベントのみが発生します。 <xref:System.Windows.Forms.Control.Click> イベントまたは <xref:System.Windows.Forms.Control.MouseClick> イベントは、このような状況では発生しません。

## <a name="see-also"></a>関連項目

- [マウスの使用の概要 (Windows フォーム .NET)](overview.md)
- [マウス ポインターを管理する (Windows フォーム .NET)](how-to-manage-cursor-pointer.md)
- [マウス イベントをシミュレートする方法 (Windows フォーム .NET)](how-to-simulate-events.md)
- <xref:System.Windows.Forms.Control?displayProperty=nameWithType>
