---
title: Windows フォームアプリでのユーザー入力
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, user input
ms.assetid: 9d61fa96-70f7-4754-885a-49a4a6316bdb
ms.openlocfilehash: 8e82276f14519c4ef54948744c93014232bdff52
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984416"
---
# <a name="user-input-in-a-windows-forms-application"></a>Windows フォーム アプリケーションにおけるユーザー入力
Windows フォームでは、ユーザー入力は Windows メッセージの形式でアプリケーションに送信されます。 一連のオーバーライド可能なメソッドは、これらのメッセージをアプリケーション、フォーム、および制御レベルで処理します。 これらのメソッドは、マウスとキーボードのメッセージを受信すると、マウスやキーボードの入力に関する情報を取得するために処理できるイベントを発生させます。 多くの場合、Windows フォームアプリケーションは、これらのイベントを処理するだけで、すべてのユーザー入力を処理できます。 場合によっては、アプリケーション、フォーム、またはコントロールによって受信される前に特定のメッセージを傍受するために、メッセージを処理するメソッドの1つをオーバーライドすることが必要になる場合があります。  
  
## <a name="mouse-and-keyboard-events"></a>マウスとキーボードイベント  
 すべての Windows フォームコントロールは、マウスおよびキーボード入力に関連する一連のイベントを継承します。 たとえば、コントロールは、 <xref:System.Windows.Forms.Control.KeyPress> 押されたキーの文字コードを特定するためにイベントを処理したり、コントロールがイベントを処理してマウスクリックの位置を判断したりすることができ <xref:System.Windows.Forms.Control.MouseClick> ます。 マウスイベントとキーボードイベントの詳細については、「 [Windows フォームでの](mouse-events-in-windows-forms.md)[キーボードイベント](using-keyboard-events.md)とマウスイベントの使用」を参照してください。  
  
## <a name="methods-that-process-user-input-messages"></a>ユーザー入力メッセージを処理するメソッド  
 フォームとコントロールには、インターフェイスへのアクセス権 <xref:System.Windows.Forms.IMessageFilter> と、メッセージキュー内のさまざまなポイントで Windows メッセージを処理するオーバーライド可能なメソッドのセットがあります。 これらのメソッドにはすべて、 <xref:System.Windows.Forms.Message> Windows メッセージの下位レベルの詳細をカプセル化するパラメーターがあります。 これらのメソッドを実装またはオーバーライドしてメッセージを確認し、メッセージを使用するか、メッセージキュー内の次のコンシューマーにメッセージを渡すことができます。 次の表に、Windows フォーム内のすべての Windows メッセージを処理するメソッドを示します。  
  
|メソッド|メモ|  
|------------|-----------|  
|<xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A>|このメソッドは、キューに置かれた (ポストされた) Windows メッセージをアプリケーションレベルでインターセプトします。|  
|<xref:System.Windows.Forms.Control.PreProcessMessage%2A>|このメソッドは、Windows メッセージが処理される前に、フォームとコントロールレベルでインターセプトします。|  
|<xref:System.Windows.Forms.Control.WndProc%2A>|このメソッドは、Windows メッセージをフォームおよびコントロールレベルで処理します。|  
|<xref:System.Windows.Forms.Control.DefWndProc%2A>|このメソッドは、Windows メッセージの既定の処理をフォームとコントロールレベルで実行します。 これにより、ウィンドウの最小限の機能が提供されます。|  
|<xref:System.Windows.Forms.Control.OnNotifyMessage%2A>|このメソッドは、メッセージが処理された後に、フォームおよびコントロールレベルでメッセージをインターセプトします。 このメソッドが呼び出されるようにするには、 <xref:System.Windows.Forms.ControlStyles.EnableNotifyMessage> スタイルビットを設定する必要があります。|  
  
 キーボードとマウスのメッセージは、これらの種類のメッセージに固有のオーバーライド可能なメソッドの追加のセットによっても処理されます。 詳細については、「 [キーボード入力](how-keyboard-input-works.md) のしくみ」と「 [Windows フォームにおけるマウス入力の](how-mouse-input-works-in-windows-forms.md)しくみ」を参照してください。  
  
## <a name="see-also"></a>関連項目

- [Windows フォームでのユーザー入力](user-input-in-windows-forms.md)
- [Windows フォーム アプリケーションにおけるキーボード入力](keyboard-input-in-a-windows-forms-application.md)
- [Windows フォーム アプリケーションにおけるマウス入力](mouse-input-in-a-windows-forms-application.md)
