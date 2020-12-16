---
title: キーボード入力の概要
description: .NET 用 Windows フォームでのキーボード入力のしくみについて説明します。 キーボード イベントはフォームおよびコントロールによって発生し、ボタンの押下または解放を表します。
ms.date: 10/26/2020
ms.topic: overview
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, keyboard input
- keyboard [Windows Forms], input
ms.openlocfilehash: dbebc89b4ec9e5824f7a1b44a75fe313c4ab683b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96942178"
---
# <a name="overview-of-using-the-keyboard-windows-forms-net"></a>キーボードの使用の概要 (Windows フォーム .NET)

Windows フォームでは、ユーザー入力は、[Windows メッセージ](/windows/win32/winmsg/about-messages-and-message-queues)の形式でアプリケーションに送信されます。 一連のオーバーライド可能なメソッドにより、これらのメッセージは、アプリケーション、フォーム、コントロールのレベルで処理されます。 これらのメソッドにより、キーボード メッセージが受信されると、キーボード入力に関する情報を取得するために処理できるイベントが発生します。 多くの場合、Windows フォーム アプリケーションは、これらのイベントに対処するだけで、すべてのユーザー入力を処理できます。 それ以外の場合は、アプリケーション、フォーム、またはコントロールで受信される前に特定のメッセージをインターセプトするために、アプリケーションで、メッセージを処理するメソッドの 1 つをオーバーライドすることが必要な場合があります。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="keyboard-events"></a>キーボード イベント

すべての Windows フォーム コントロールは、マウスおよびキーボード入力に関連する一連のイベントを継承します。 たとえば、コントロールでは、<xref:System.Windows.Forms.Control.KeyPress> イベントを処理し、押下されたキーの文字コードを判断できます。 詳細については、「[キーボード イベントの使用](events.md)」を参照してください。

## <a name="methods-that-process-user-input-messages"></a>ユーザー入力メッセージを処理するメソッド

フォームとコントロールは、<xref:System.Windows.Forms.IMessageFilter> インターフェイス、およびメッセージ キュー内のさまざまなポイントで Windows メッセージを処理するオーバーライド可能なメソッドのセットにアクセスできます。 これらのメソッドにはすべて、Windows メッセージの下位レベルの詳細をカプセル化する <xref:System.Windows.Forms.Message> パラメーターが含まれています。 これらのメソッドを実装またはオーバーライドしてメッセージを確認し、メッセージを使用するか、またはメッセージ キュー内の次のコンシューマーに渡すことができます。 次の表に、Windows フォームのすべての Windows メッセージを処理するメソッドを示します。

| メソッド     | メモ |
|------------|-----------|
| <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A> | このメソッドにより、キューに登録済み (ポスト済みとも呼ばれる) の Windows メッセージはアプリケーション レベルでインターセプトされます。|
| <xref:System.Windows.Forms.Control.PreProcessMessage%2A>       | このメソッドにより、Windows メッセージが、処理される前に、フォームおよびコントロール レベルでインターセプトされます。|
| <xref:System.Windows.Forms.Control.WndProc%2A>                 | このメソッドにより、Windows メッセージはフォームおよびコントロール レベルで処理されます。|
| <xref:System.Windows.Forms.Control.DefWndProc%2A>              | このメソッドにより、Windows メッセージの既定の処理はフォームおよびコントロール レベルで実行されます。 これにより、Windows の最小限の機能が提供されます。|
| <xref:System.Windows.Forms.Control.OnNotifyMessage%2A>         | このメソッドにより、メッセージは、処理された後、フォームおよびコントロール レベルでインターセプトされます。 このメソッドが呼び出されるようにするには、<xref:System.Windows.Forms.ControlStyles.EnableNotifyMessage> スタイルのビットを設定する必要があります。|

キーボードおよびマウス メッセージは、これらの種類のメッセージ固有のオーバーライド可能なメソッドの追加セットによっても処理されます。 詳細については、「[キーの前処理](#preprocessing-keys)」セクションを参照してください。 <!-- TODO mouse link -->.

## <a name="types-of-keys"></a>キーの種類

Windows フォームでは、キーボード入力をビット単位の <xref:System.Windows.Forms.Keys> 列挙型で表される仮想キー コードとして識別します。 <xref:System.Windows.Forms.Keys> 列挙型を使用すると、押下された一連のキーを組み合わせて単一の値を生成できます。 これらの値は、Windows メッセージ **WM_KEYDOWN** および **WM_SYSKEYDOWN** に付随する値に対応します。 ほとんどの物理的なキーの押下は、<xref:System.Windows.Forms.Control.KeyDown> または <xref:System.Windows.Forms.Control.KeyUp> イベントを処理することによって検出できます。 文字キーは <xref:System.Windows.Forms.Keys> 列挙型のサブセットであり、Windows メッセージ **WM_CHAR** および **WM_SYSCHAR** に付随する値に対応します。 押下されたキーを組み合わせて文字が生成される場合、<xref:System.Windows.Forms.Control.KeyPress> イベントを処理することにより、その文字を検出できます。 <!-- TODO is this still valid with .NET Core/5 ?? Alternatively, you can use <xref:Microsoft.VisualBasic.Devices.Keyboard>, exposed by Visual Basic programming interface, to discover which keys were pressed and send keys. For more information, see [Accessing the Keyboard](../../visual-basic/developing-apps/programming/computer-resources/accessing-the-keyboard.md).-->

## <a name="order-of-keyboard-events"></a>キーボード イベントの順序

先に説明したとおり、コントロール上では 3 つのキーボード関連のイベントが発生します。 イベントは一般に次の順序で発生します。

01. ユーザーが "a" キーを押すと、キーが前処理されてディスパッチされ、<xref:System.Windows.Forms.Control.KeyDown> イベントが発生します。
01. ユーザーは "a" キーを押したままで、キーが前処理されてディスパッチされ、<xref:System.Windows.Forms.Control.KeyPress> イベントが発生します。
    このイベントはユーザーがキーを押し続けているとき複数回発生します。
01. ユーザーが "a" キーを解放すると、キーが前処理されてディスパッチされ、<xref:System.Windows.Forms.Control.KeyUp> イベントが発生します。

## <a name="preprocessing-keys"></a>キーの前処理

他のメッセージと同様に、キーボード メッセージは、フォームまたはコントロールの <xref:System.Windows.Forms.Control.WndProc%2A> メソッドで処理されます。 ただし、キーボード メッセージが処理される前に、<xref:System.Windows.Forms.Control.PreProcessMessage%2A> メソッドによって 1 つ以上のメソッドが呼び出されます。これらをオーバーライドして、特殊文字キーと物理キーを扱うことができます。 これらのメソッドをオーバーライドすると、コントロールがメッセージを処理する前に、特定のキーを検出してフィルターできます。 次の表に、実行される処理と、そのとき呼び出されるメソッドを、メソッドが呼び出される順に示します。

### <a name="preprocessing-for-a-keydown-event"></a>KeyDown イベントの前処理

|アクション|関連メソッド|Notes|
|------------|--------------------|-----------|
|アクセラレータやメニュー ショートカットなどのコマンド キーの確認。|<xref:System.Windows.Forms.Control.ProcessCmdKey%2A>|このメソッドはコマンド キーを処理します。コマンド キーは通常のキーよりも優先順位が上です。 このメソッドが `true` を返した場合、キー メッセージはディスパッチされず、キー イベントも発生しません。 `false`が返される場合、<xref:System.Windows.Forms.Control.IsInputKey%2A> が呼び出されます`.`|
|前処理を必要とする特殊キーであるか、または <xref:System.Windows.Forms.Control.KeyDown> イベントを発生させ、コントロールにディスパッチされる必要がある通常の文字キーであるかを確認します。|<xref:System.Windows.Forms.Control.IsInputKey%2A>|メソッドによって `true`が返される場合、コントロールが通常の文字で、<xref:System.Windows.Forms.Control.KeyDown> イベントが発生することを意味します。 `false`の場合、<xref:System.Windows.Forms.Control.ProcessDialogKey%2A> が呼び出されます。 **注:** コントロールでキーまたはキーの組み合わせを確実に取得するために、<xref:System.Windows.Forms.Control.PreviewKeyDown> イベントを処理し、対象の 1 つまたは複数のキーの <xref:System.Windows.Forms.PreviewKeyDownEventArgs> の <xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A> を `true` に設定することができます。|
|移動キー (Esc、Tab、Return、または方向キー) の確認。|<xref:System.Windows.Forms.Control.ProcessDialogKey%2A>|このメソッドはコントロール内で特別な機能 (コントロールとその親コントロールの間のフォーカスの切り替えなど) を実行する物理キーを処理します。 即時コントロールでキーが処理されない場合、親コントロールで <xref:System.Windows.Forms.Control.ProcessDialogKey%2A> が呼び出されます。それでも処理されなければ、コントロールの呼び出しが階層構造の最上位のコントロールまで続けられます。 このメソッドが `true` を返した場合、前処理は完了し、キー イベントは生成されません。 `false` が返される場合、<xref:System.Windows.Forms.Control.KeyDown> イベントが発生します。|

### <a name="preprocessing-for-a-keypress-event"></a>KeyPress イベントの前処理

|アクション|関連メソッド|Notes|
|------------|--------------------|-----------|
|キーがコントロールによって処理される通常の文字であるかどうかの確認|<xref:System.Windows.Forms.Control.IsInputChar%2A>|文字が通常の文字である場合は、このメソッドによって `true` が返され、<xref:System.Windows.Forms.Control.KeyPress> イベントが発生します。それ以上の処理は行われません。 それ以外の場合、<xref:System.Windows.Forms.Control.ProcessDialogChar%2A> が呼び出されます。|
|文字がニーモニック (ボタン上の &OK など) かどうかの確認|<xref:System.Windows.Forms.Control.ProcessDialogChar%2A>|このメソッドは、<xref:System.Windows.Forms.Control.ProcessDialogKey%2A>と同様に、コントロール階層の上位まで呼び出されます。 コントロールがコンテナー コントロールである場合、それ自体と子コントロールで <xref:System.Windows.Forms.Control.ProcessMnemonic%2A> を呼び出すことにより、ニーモニックの確認が行われます。 <xref:System.Windows.Forms.Control.ProcessDialogChar%2A> によって `true`が返される場合、<xref:System.Windows.Forms.Control.KeyPress> イベントは発生しません。|

## <a name="processing-keyboard-messages"></a>キーボード メッセージの処理

キーボード メッセージは、フォームまたはコントロールの <xref:System.Windows.Forms.Control.WndProc%2A> メソッドに到達すると、オーバーライド可能な一連のメソッドによって処理されます。 これらの各メソッドによって、<xref:System.Boolean> 値が返されます。これは、キーボード メッセージがコントロールによって処理され、使用されたかどうかを指定します。 いずれかのメソッドが `true` を返した場合は、メッセージが処理されたと判断されるため、ベース コントロールまたは親コントロールにメッセージが渡されることはありません。 そうでない場合は、メッセージがメッセージ キューに残り、場合によってはそのコントロールのベースまたは親に含まれる別のメソッドで処理されます。 次の表に、キーボード メッセージを処理するメソッドを示します。

|メソッド|メモ|
|------------|-----------|
|<xref:System.Windows.Forms.Control.ProcessKeyMessage%2A>|このメソッドによって、コントロールの <xref:System.Windows.Forms.Control.WndProc%2A> メソッドによって受信されたすべてのキーボード メッセージが処理されます。|
|<xref:System.Windows.Forms.Control.ProcessKeyPreview%2A>|このメソッドは、キーボード メッセージを親コントロールに送信します。 <xref:System.Windows.Forms.Control.ProcessKeyPreview%2A> によって `true`が返された場合、キー イベントは生成されます。それ以外の場合、<xref:System.Windows.Forms.Control.ProcessKeyEventArgs%2A> が呼び出されます。|
|<xref:System.Windows.Forms.Control.ProcessKeyEventArgs%2A>|このメソッドにより、必要に応じて、<xref:System.Windows.Forms.Control.KeyDown>、<xref:System.Windows.Forms.Control.KeyPress>、<xref:System.Windows.Forms.Control.KeyUp> イベントが発生します。|

## <a name="overriding-keyboard-methods"></a>キーボード メソッドのオーバーライド

キーボード メッセージを処理するためにオーバーライドできるメソッドは多数ありますが、どのメソッドを選ぶかが非常に重要です。 次の表に、実行するタスクと、キーボード メソッドをオーバーライドする最善の方法を示します。 メソッドのオーバーライドの詳細については、「[継承 (C# プログラミング ガイド)](/dotnet/csharp/programming-guide/classes-and-structs/inheritance.md#abstract-and-virtual-methods)」 または [継承 (Visual Basic)](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md#overriding-properties-and-methods-in-derived-classes) に関する記事を参照してください

|タスク|メソッド|
|----------|------------|
|ナビゲーション キーをインターセプトして、<xref:System.Windows.Forms.Control.KeyDown> イベントを発生させます。 たとえば、テキスト ボックス内で Tab や Return を処理するなど。|<xref:System.Windows.Forms.Control.IsInputKey%2A> をオーバーライドします。 **注:** または、<xref:System.Windows.Forms.Control.PreviewKeyDown> イベントを処理し、対象の 1 つまたは複数のキーの <xref:System.Windows.Forms.PreviewKeyDownEventArgs> の <xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A> を `true` に設定することもできます。|
|コントロールで特別な入力処理や移動処理を実行する。 たとえば、リスト コントロールで方向キーを使用して選択項目を変更するなど。|<xref:System.Windows.Forms.Control.ProcessDialogKey%2A> をオーバーライドします。|
|ナビゲーション キーをインターセプトして、<xref:System.Windows.Forms.Control.KeyPress> イベントを発生させます。 たとえば、スピン ボックス コントロールで方向キーを複数回押して、項目の移動を加速するなど。|<xref:System.Windows.Forms.Control.IsInputChar%2A> をオーバーライドします。|
|<xref:System.Windows.Forms.Control.KeyPress> イベント中に、特殊な入力またはナビゲーションの処理を実行します。 たとえば、リスト コントロール内で "r" キーを押し続けると、r の文字で始まる項目にスキップするなど。|<xref:System.Windows.Forms.Control.ProcessDialogChar%2A> をオーバーライドします。|
|カスタムなニーモニックの処理を実行する。たとえば、ツール バーに配置されたオーナー描画ボタンのニーモニックを処理するなど。|<xref:System.Windows.Forms.Control.ProcessMnemonic%2A> をオーバーライドします。|

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.WndProc%2A>
- <xref:System.Windows.Forms.Control.PreProcessMessage%2A>
- [キーボード イベントの使用 (Windows フォーム .NET)](events.md)
- [キーボード キー イベントを変更する方法 (Windows フォーム .NET)](how-to-change-key-press.md)
- [修飾キーの押下を確認する方法 (Windows フォーム .NET)](how-to-check-modifier-key.md)
- [キーボード イベントをシミュレートする方法 (Windows フォーム .NET)](how-to-simulate-events.md)
- [フォームでキーボード入力メッセージを処理する方法 (Windows フォーム .NET)](how-to-handle-forms.md)
- [コントロールを追加する (Windows フォーム .NET)](../controls/how-to-add-to-a-form.md)
