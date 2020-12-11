---
title: キーボード入力のしくみ
ms.date: 03/30/2017
ms.topic: overview
helpviewer_keywords:
- keyboard input [Windows Forms], about keyboard input
- keyboards [Windows Forms], keyboard input
- Windows Forms, keyboard input
ms.assetid: 9a29433c-a180-49bb-b74c-d187786584c8
ms.openlocfilehash: aafc7b27cdd2d4c9c013a1f9632ee68ab2364dcd
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974370"
---
# <a name="how-keyboard-input-works"></a>キーボード入力のしくみ

Windows フォームは、Windows メッセージに応答してキーボード イベントを発生させることにより、キーボード入力を処理します。 多くの Windows フォーム アプリケーションは、キーボード イベントを処理することによってキーボード入力を排他的に処理します。 しかし、高度なキーボード入力のシナリオ (キーがコントロールに到達する前にインターセプトするなど) を実装するためには、キーボード メッセージのしくみについて理解することが必要です。 このトピックでは、Windows フォームが認識するキー データの種類について説明し、キーボード メッセージをルーティングする方法について概要を説明します。 キーボード イベントの詳細については、「[キーボード イベントの使用](using-keyboard-events.md)」を参照してください。  
  
## <a name="types-of-keys"></a>キーの種類  

 Windows フォームは、ビットごとの列挙体によって表される仮想キーコードとして、キーボード入力を識別し <xref:System.Windows.Forms.Keys> ます。 列挙体を使用すると <xref:System.Windows.Forms.Keys> 、一連の押されたキーを結合して1つの値にすることができます。 これらの値は、WM_KEYDOWN および WM_SYSKEYDOWN の Windows メッセージに付随する値になります。 イベントまたはイベントを処理することで、ほとんどの物理キーの押下を検出でき <xref:System.Windows.Forms.Control.KeyDown> <xref:System.Windows.Forms.Control.KeyUp> ます。 文字キーは列挙のサブセットであり、 <xref:System.Windows.Forms.Keys> WM_CHAR および WM_SYSCHAR Windows メッセージに付随する値に対応します。 押されたキーの組み合わせによって文字が生成される場合は、イベントを処理することによって文字を検出でき <xref:System.Windows.Forms.Control.KeyPress> ます。 または、 <xref:Microsoft.VisualBasic.Devices.Keyboard> Visual Basic プログラミングインターフェイスによって公開されたを使用して、どのキーが押されたかを検出し、キーを送信することもできます。 詳細については、「[Accessing the Keyboard (キーボードへのアクセス)](/dotnet/visual-basic/developing-apps/programming/computer-resources/accessing-the-keyboar)」を参照してください。  
  
## <a name="order-of-keyboard-events"></a>キーボード イベントの順序  

 先に説明したとおり、コントロール上では 3 つのキーボード関連のイベントが発生します。 イベントは一般に次の順序で発生します。  
  
1. ユーザーは "a" キーをプッシュし、キーは前処理され、ディスパッチされて、 <xref:System.Windows.Forms.Control.KeyDown> イベントが発生します。  
  
2. ユーザーは "a" キーを保持し、キーは前処理され、ディスパッチされて、 <xref:System.Windows.Forms.Control.KeyPress> イベントが発生します。  
  
     このイベントはユーザーがキーを押し続けているとき複数回発生します。  
  
3. ユーザーが "a" キーを解放すると、キーが前処理され、ディスパッチされて、 <xref:System.Windows.Forms.Control.KeyUp> イベントが発生します。  
  
## <a name="preprocessing-keys"></a>キーの前処理  

 他のメッセージと同様に、キーボードメッセージは <xref:System.Windows.Forms.Control.WndProc%2A> フォームまたはコントロールのメソッドで処理されます。 ただし、キーボードメッセージが処理される前に、メソッドは、 <xref:System.Windows.Forms.Control.PreProcessMessage%2A> 特殊文字キーと物理キーを処理するためにオーバーライドできる1つ以上のメソッドを呼び出します。 これらのメソッドをオーバーライドすると、コントロールがメッセージを処理する前に、特定のキーを検出してフィルターできます。 次の表に、実行される処理と、そのとき呼び出されるメソッドを、メソッドが呼び出される順に示します。  
  
### <a name="preprocessing-for-a-keydown-event"></a>KeyDown イベントの前処理  
  
|アクション|関連メソッド|Notes|  
|------------|--------------------|-----------|  
|アクセラレータやメニュー ショートカットなどのコマンド キーの確認。|<xref:System.Windows.Forms.Control.ProcessCmdKey%2A>|このメソッドはコマンド キーを処理します。コマンド キーは通常のキーよりも優先順位が上です。 このメソッドが `true` を返した場合、キー メッセージはディスパッチされず、キー イベントも発生しません。 が返された場合 `false` 、 <xref:System.Windows.Forms.Control.IsInputKey%2A> が呼び出されます。`.`|  
|プリプロセスを必要とする特殊なキー、またはイベントを発生させてコントロールにディスパッチする必要がある通常の文字キーを確認し <xref:System.Windows.Forms.Control.KeyDown> ます。|<xref:System.Windows.Forms.Control.IsInputKey%2A>|メソッドがを返す場合 `true` 、コントロールが通常の文字であり、イベントが発生することを意味し <xref:System.Windows.Forms.Control.KeyDown> ます。 `false`の場合、 <xref:System.Windows.Forms.Control.ProcessDialogKey%2A> が呼び出されます。 **注:**  コントロールがキーまたはキーの組み合わせを取得できるようにするには、 <xref:System.Windows.Forms.Control.PreviewKeyDown> <xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A> 必要なキーに対してイベントを処理し、の <xref:System.Windows.Forms.PreviewKeyDownEventArgs> をに設定し `true` ます。|  
|移動キー (Esc、Tab、Return、または方向キー) の確認。|<xref:System.Windows.Forms.Control.ProcessDialogKey%2A>|このメソッドはコントロール内で特別な機能 (コントロールとその親コントロールの間のフォーカスの切り替えなど) を実行する物理キーを処理します。 イミディエイトコントロールがキーを処理しない場合、は <xref:System.Windows.Forms.Control.ProcessDialogKey%2A> 親コントロールで呼び出され、階層内の最上位のコントロールに対して呼び出されます。 このメソッドが `true` を返した場合、前処理は完了し、キー イベントは生成されません。 が返された場合 `false` 、 <xref:System.Windows.Forms.Control.KeyDown> イベントが発生します。|  
  
### <a name="preprocessing-for-a-keypress-event"></a>KeyPress イベントの前処理  
  
|アクション|関連メソッド|Notes|  
|------------|--------------------|-----------|  
|キーがコントロールによって処理される通常の文字であるかどうかの確認|<xref:System.Windows.Forms.Control.IsInputChar%2A>|文字が通常の文字の場合、このメソッドはを返し `true` 、 <xref:System.Windows.Forms.Control.KeyPress> イベントが発生し、それ以降のプリプロセスは実行されません。 それ以外 <xref:System.Windows.Forms.Control.ProcessDialogChar%2A> の場合は、が呼び出されます。|  
|文字がニーモニック (ボタン上の &OK など) かどうかの確認|<xref:System.Windows.Forms.Control.ProcessDialogChar%2A>|このメソッドは、に似 <xref:System.Windows.Forms.Control.ProcessDialogKey%2A> ていますが、コントロール階層の上位に呼び出されます。 コントロールがコンテナーコントロールである場合は、それ <xref:System.Windows.Forms.Control.ProcessMnemonic%2A> 自体とその子コントロールでを呼び出すことによって、ニーモニックを確認します。 が <xref:System.Windows.Forms.Control.ProcessDialogChar%2A> を返した場合 `true` 、 <xref:System.Windows.Forms.Control.KeyPress> イベントは発生しません。|  
  
## <a name="processing-keyboard-messages"></a>キーボード メッセージの処理  

 キーボードメッセージ <xref:System.Windows.Forms.Control.WndProc%2A> は、フォームまたはコントロールのメソッドに到着した後、オーバーライドできる一連のメソッドによって処理されます。 これらの各メソッドは、 <xref:System.Boolean> キーボードメッセージがコントロールによって処理および使用されたかどうかを示す値を返します。 いずれかのメソッドが `true` を返した場合は、メッセージが処理されたと判断されるため、ベース コントロールまたは親コントロールにメッセージが渡されることはありません。 そうでない場合は、メッセージがメッセージ キューに残り、場合によってはそのコントロールのベースまたは親に含まれる別のメソッドで処理されます。 次の表に、キーボード メッセージを処理するメソッドを示します。  
  
|メソッド|メモ|  
|------------|-----------|  
|<xref:System.Windows.Forms.Control.ProcessKeyMessage%2A>|このメソッドは、コントロールのメソッドによって受信されたすべてのキーボードメッセージを処理 <xref:System.Windows.Forms.Control.WndProc%2A> します。|  
|<xref:System.Windows.Forms.Control.ProcessKeyPreview%2A>|このメソッドは、キーボード メッセージを親コントロールに送信します。 がを <xref:System.Windows.Forms.Control.ProcessKeyPreview%2A> 返す場合 `true` 、キーイベントは生成されません。それ以外 <xref:System.Windows.Forms.Control.ProcessKeyEventArgs%2A> の場合は、が呼び出されます。|  
|<xref:System.Windows.Forms.Control.ProcessKeyEventArgs%2A>|このメソッドは <xref:System.Windows.Forms.Control.KeyDown> 、必要に応じて、、、 <xref:System.Windows.Forms.Control.KeyPress> およびの <xref:System.Windows.Forms.Control.KeyUp> 各イベントを発生させます。|  
  
## <a name="overriding-keyboard-methods"></a>キーボード メソッドのオーバーライド  

 キーボード メッセージを処理するためにオーバーライドできるメソッドは多数ありますが、どのメソッドを選ぶかが非常に重要です。 次の表に、実行するタスクと、キーボード メソッドをオーバーライドする最善の方法を示します。 メソッドのオーバーライドの詳細については、「 [派生クラスのプロパティとメソッドのオーバーライド](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics#overriding-properties-and-methods-in-derived-classes)」を参照してください。  
  
|タスク|メソッド|  
|----------|------------|  
|ナビゲーションキーをインターセプトし、イベントを発生させ <xref:System.Windows.Forms.Control.KeyDown> ます。 たとえば、テキスト ボックス内で Tab や Return を処理するなど。|<xref:System.Windows.Forms.Control.IsInputKey%2A> をオーバーライドします。 **注:**  または、イベントを処理し、 <xref:System.Windows.Forms.Control.PreviewKeyDown> <xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A> <xref:System.Windows.Forms.PreviewKeyDownEventArgs> 必要なキーに対してのセットをに設定することもでき `true` ます。|  
|コントロールで特別な入力処理や移動処理を実行する。 たとえば、リスト コントロールで方向キーを使用して選択項目を変更するなど。|<xref:System.Windows.Forms.Control.ProcessDialogKey%2A> をオーバーライドします。|  
|ナビゲーションキーをインターセプトし、イベントを発生させ <xref:System.Windows.Forms.Control.KeyPress> ます。 たとえば、スピン ボックス コントロールで方向キーを複数回押して、項目の移動を加速するなど。|<xref:System.Windows.Forms.Control.IsInputChar%2A> をオーバーライドします。|  
|イベント中に特殊な入力またはナビゲーション処理を実行 <xref:System.Windows.Forms.Control.KeyPress> します。 たとえば、リスト コントロール内で "r" キーを押し続けると、r の文字で始まる項目にスキップするなど。|<xref:System.Windows.Forms.Control.ProcessDialogChar%2A> をオーバーライドします。|  
|カスタムなニーモニックの処理を実行する。たとえば、ツール バーに配置されたオーナー描画ボタンのニーモニックを処理するなど。|<xref:System.Windows.Forms.Control.ProcessMnemonic%2A> をオーバーライドします。|  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.WndProc%2A>
- <xref:System.Windows.Forms.Control.PreProcessMessage%2A>
- [My.Computer.Keyboard オブジェクト](/dotnet/visual-basic/language-reference/objects/my-computer-keyboard-object)
- [キーボードへのアクセス](/dotnet/visual-basic/developing-apps/programming/computer-resources/accessing-the-keyboar)
- [キーボード イベントの使用](using-keyboard-events.md)
