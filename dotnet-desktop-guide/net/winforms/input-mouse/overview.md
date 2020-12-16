---
title: マウス入力の概要
description: .NET 用 Windows フォームでのマウス入力のしくみについて説明します。 マウス イベントは、フォームとコントロールによって発生し、マウスの位置とボタンの状態を表します。
ms.date: 10/26/2020
ms.topic: overview
helpviewer_keywords:
- Windows Forms, mouse input
- mouse [Windows Forms], input
ms.openlocfilehash: 3e85305796d724d9acdbcd2e7cb86e748c30b783
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96942234"
---
# <a name="overview-of-using-the-mouse-windows-forms-net"></a>マウスの使用の概要 (Windows フォーム .NET)

マウス入力の受信と処理は、すべての Windows アプリケーションの重要な部分です。 マウス イベントを処理してアプリケーションでアクションを実行したり、マウスの位置情報を使用してヒット テストやその他のアクションを実行したりすることができます。 また、アプリケーションのコントロールでマウス入力を処理する方法も変更できます。 この記事では、これらのマウス イベントの詳細と、マウスのシステム設定を取得して変更する方法について説明します。

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

Windows フォームでは、ユーザー入力は、[Windows メッセージ](/windows/win32/winmsg/about-messages-and-message-queues)の形式でアプリケーションに送信されます。 一連のオーバーライド可能なメソッドにより、これらのメッセージは、アプリケーション、フォーム、コントロールのレベルで処理されます。 これらのメソッドにより、マウス メッセージが受信されると、マウス入力に関する情報を取得するために処理できるイベントが発生します。 多くの場合、Windows フォーム アプリケーションは、これらのイベントに対処するだけで、すべてのユーザー入力を処理できます。 それ以外の場合は、アプリケーション、フォーム、またはコントロールが受信する前に、メッセージを処理するメソッドの 1 つをオーバーライドして、特定のメッセージを受け取ることができます。

## <a name="mouse-events"></a>マウス イベント

すべての Windows フォーム コントロールは、マウスおよびキーボード入力に関連する一連のイベントを継承します。 たとえば、コントロールは <xref:System.Windows.Forms.Control.MouseClick> イベントを処理して、マウス クリックの位置を判断できます。 マウス イベントの詳細については、「[マウス イベントの使用](events.md)」を参照してください。

## <a name="mouse-location-and-hit-testing"></a>マウスの位置とヒットテスト

ユーザーがマウスを動かすと、オペレーティング システムによってマウス ポインターが移動します。 マウス ポインターには、ホット スポットと呼ばれる 1 つのピクセルが含まれています。これをオペレーティング システムがポインターの位置として追跡し、認識します。 ユーザーがマウスを動かすか、マウス ボタンを押すと、<xref:System.Windows.Forms.Cursor.HotSpot%2A> を含む <xref:System.Windows.Forms.Control> によって適切なマウス イベントが発生します。

マウス イベントを処理するか、または <xref:System.Windows.Forms.Cursor> クラスの <xref:System.Windows.Forms.Cursor.Position%2A> プロパティを使用すると、<xref:System.Windows.Forms.MouseEventArgs> の <xref:System.Windows.Forms.MouseEventArgs.Location%2A> プロパティで、現在のマウス位置を取得できます。 マウスの位置情報を使用してヒットテストを実行し、マウスの位置に基づいてアクションを実行できます。 ヒットテスト機能は、<xref:System.Windows.Forms.ListView>、<xref:System.Windows.Forms.TreeView>、<xref:System.Windows.Forms.MonthCalendar>、<xref:System.Windows.Forms.DataGridView> コントロールなどの Windows フォームのいくつかのコントロールに組み込まれています。

ヒットテストは、<xref:System.Windows.Forms.Control.MouseHover> などの適切なマウスイベントと共に使用され、アプリケーションが特定のアクションを実行する必要があるかどうかを判断するのに非常に役立ちます。

## <a name="changing-mouse-input-settings"></a>マウスの入力設定の変更

コントロールがマウス入力を処理する方法は、コントロールから派生させ、<xref:System.Windows.Forms.Control.GetStyle%2A> と <xref:System.Windows.Forms.Control.SetStyle%2A> のメソッドを使用することで検出して変更することができます。 <xref:System.Windows.Forms.Control.SetStyle%2A> メソッドは、<xref:System.Windows.Forms.ControlStyles> 値のビットごとの組み合わせを取得して、コントロールに標準のクリック、ダブルクリックの動作が含まれるかどうか、またはコントロールにより独自のマウス処理が対処されるかどうかを決定します。 さらに、<xref:System.Windows.Forms.SystemInformation> クラスには、マウスの機能を説明し、マウスがオペレーティング システムとどのように対話するかを指定するプロパティが含まれています。 次の表に、これらのプロパティを要約します。

| プロパティ                                                               | 説明                                                                                                                                                            |
|------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A>       | 2 回のクリックがダブルクリックであるとオペレーティング システムに認識されるために、ユーザーがクリックする 2 つの位置が含まれている必要がある範囲のサイズ (ピクセル単位) を取得します。                     |
| <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A>       | マウスのアクションがダブルクリックであると認識されるための、1 回目のクリックと 2 回目のクリックの間の最大経過時間 (ミリ秒単位) を取得します。 |
| <xref:System.Windows.Forms.SystemInformation.MouseButtons%2A>          | マウスのボタンの数を取得します。                                                                                                                               |
| <xref:System.Windows.Forms.SystemInformation.MouseButtonsSwapped%2A>   | 左右のマウス ボタンの機能が入れ替わっているかどうかを示す値を取得します。                                                                   |
| <xref:System.Windows.Forms.SystemInformation.MouseHoverSize%2A>        | マウス静止メッセージが生成されるためにマウス静止時間が経過するまでマウス ポインターをとどめておく必要がある四角形の領域のサイズ (ピクセル単位) を取得します。        |
| <xref:System.Windows.Forms.SystemInformation.MouseHoverTime%2A>        | マウス静止メッセージが生成されるために静止領域内にマウス ポインターをとどめておく必要がある時間 (ミリ秒単位) を取得します。                                   |
| <xref:System.Windows.Forms.SystemInformation.MousePresent%2A>          | マウスが取り付けられているかどうかを示す値を取得します。                                                                                                                  |
| <xref:System.Windows.Forms.SystemInformation.MouseSpeed%2A>            | 現在のマウスの速度を示す値 (1 から 20) を取得します。                                                                                                         |
| <xref:System.Windows.Forms.SystemInformation.MouseWheelPresent%2A>     | マウス ホイール付きのマウスが取り付けられているかどうかを示す値を取得します。                                                                                               |
| <xref:System.Windows.Forms.SystemInformation.MouseWheelScrollDelta%2A> | マウス ホイールの 1 目盛りの回転で増分される差分値を取得します。                                                                                  |
| <xref:System.Windows.Forms.SystemInformation.MouseWheelScrollLines%2A> | マウス ホイールを回転したときにスクロールする行数を取得します。                                                                                                    |

## <a name="methods-that-process-user-input-messages"></a>ユーザー入力メッセージを処理するメソッド

フォームとコントロールは、<xref:System.Windows.Forms.IMessageFilter> インターフェイス、およびメッセージ キュー内のさまざまなポイントで Windows メッセージを処理するオーバーライド可能なメソッドのセットにアクセスできます。 これらのメソッドにはすべて、Windows メッセージの下位レベルの詳細をカプセル化する <xref:System.Windows.Forms.Message> パラメーターが含まれています。 これらのメソッドを実装またはオーバーライドしてメッセージを確認し、メッセージを使用するか、またはメッセージ キュー内の次のコンシューマーに渡すことができます。 次の表に、Windows フォームのすべての Windows メッセージを処理するメソッドを示します。

| メソッド     | メモ |
|------------|-----------|
| <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A> | このメソッドにより、キューに登録済み (ポスト済みとも呼ばれる) の Windows メッセージはアプリケーション レベルでインターセプトされます。|
| <xref:System.Windows.Forms.Control.PreProcessMessage%2A>       | このメソッドにより、Windows メッセージが、処理される前に、フォームおよびコントロール レベルでインターセプトされます。|
| <xref:System.Windows.Forms.Control.WndProc%2A>                 | このメソッドにより、Windows メッセージはフォームおよびコントロール レベルで処理されます。|
| <xref:System.Windows.Forms.Control.DefWndProc%2A>              | このメソッドにより、Windows メッセージの既定の処理はフォームおよびコントロール レベルで実行されます。 これにより、Windows の最小限の機能が提供されます。|
| <xref:System.Windows.Forms.Control.OnNotifyMessage%2A>         | このメソッドは、メッセージを、それが処理された後にフォームとコントロール レベルで受け取ります。 このメソッドが呼び出されるようにするには、<xref:System.Windows.Forms.ControlStyles.EnableNotifyMessage> スタイルのビットを設定する必要があります。|

## <a name="see-also"></a>関連項目

- [マウス イベントの使用 (Windows フォーム .NET)](events.md)
- [ドラッグ アンド ドロップによるマウス動作の概要 (Windows フォーム .NET)](drag-and-drop.md)
- [マウス ポインターを管理する (Windows フォーム .NET)](how-to-manage-cursor-pointer.md)
