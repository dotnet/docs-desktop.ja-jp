---
title: '方法: DHTML コードとクライアント アプリケーション コード間の双方向の通信を実装する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- WebBrowser.ObjectForScripting
- WebBrowser.Document
helpviewer_keywords:
- WebBrowser control [Windows Forms], examples
- communications [Windows Forms], DHTML and client applications
- examples [Windows Forms], WebBrowser control
- WebBrowser control [Windows Forms], communication between DHTML and client application
- DHTML [Windows Forms], embedding in Windows Forms
ms.assetid: 55353a32-b09e-4479-a521-ff3a5ff9a708
ms.openlocfilehash: c047f8de55ad7b66a6bc417db1a2678dc87b59c1
ms.sourcegitcommit: 7f48b9ecf8a30db42c8ecea0dd4df577736631a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957267"
---
# <a name="how-to-implement-two-way-communication-between-dhtml-code-and-client-application-code"></a>方法: DHTML コードとクライアント アプリケーション コード間の双方向の通信を実装する

<xref:System.Windows.Forms.WebBrowser> コントロールを使用して、既存の動的 HTML (DHTML) Web アプリケーション コードを Windows フォーム クライアント アプリケーションに追加できます。 これは、DHTML ベースのコントロールの作成にかなりの開発時間を投資し、既存のコードを再作成せずに Windows フォームの機能が豊富なユーザー インターフェイスを利用したい場合に役立ちます。

<xref:System.Windows.Forms.WebBrowser> コントロールでは、<xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A> プロパティと <xref:System.Windows.Forms.WebBrowser.Document%2A> プロパティを通じて、クライアント アプリケーション コードと Web ページ内のスクリプト コードの間の双方向の通信を実装できます。 また、<xref:System.Windows.Forms.WebBrowser> コントロールを構成して、Web コントロールをアプリケーション フォームのその他のコントロールとシームレスに統合し、DHTML 実装を非表示にすることができます。 コントロールをシームレスに統合するには、背景色と視覚スタイルが残りのフォームと一致するように表示されるページの書式を設定し、<xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>、<xref:System.Windows.Forms.WebBrowser.IsWebBrowserContextMenuEnabled%2A>、および <xref:System.Windows.Forms.WebBrowser.WebBrowserShortcutsEnabled%2A> の各プロパティを使用して標準的なブラウザーの機能を無効にします。

## <a name="to-embed-dhtml-in-your-windows-forms-application"></a>Windows フォーム アプリケーションで DHTML を埋め込むには

1. <xref:System.Windows.Forms.WebBrowser> コントロールの <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> プロパティを `false` に設定し、<xref:System.Windows.Forms.WebBrowser> コントロールがその上にドロップされたファイルを開かないようにします。

     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#1)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#1)]

2. コントロールの <xref:System.Windows.Forms.WebBrowser.IsWebBrowserContextMenuEnabled%2A> プロパティを `false` に設定し、ユーザーが右クリックしたときに、<xref:System.Windows.Forms.WebBrowser> コントロールでショートカット メニューが表示されないようにします。

     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#2)]

3. コントロールの <xref:System.Windows.Forms.WebBrowser.WebBrowserShortcutsEnabled%2A> プロパティを `false` に設定して、<xref:System.Windows.Forms.WebBrowser> コントロールがショートカット キーに応答しないようにします。

     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#3)]

4. <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A>フォームのコンストラクターでプロパティを設定するか、メソッドをオーバーライド <xref:System.Windows.Forms.Form.OnLoad%2A> します。

     次のコードは、スクリプト オブジェクトに、フォーム クラス自体を使用します。

     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#4)]

5. スクリプトオブジェクトを実装します。

     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#5)]

6. 指定されたオブジェクトのパブリック プロパティおよびメソッドへのアクセスには、スクリプト コードで `window.external` オブジェクトを使用します。

     次の HTML コードは、ボタンのクリックからスクリプト オブジェクトでメソッドを呼び出す方法を示します。 コントロールの <xref:System.Windows.Forms.WebBrowser.Navigate%2A> メソッドを使用して読み込む、またはコントロールの <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> プロパティに割り当てる HTML ドキュメントの BODY 要素に、このコードをコピーします。

    ```html
    <button onclick="window.external.Test('called from script code')">
        call client code from script code
    </button>
    ```

7. アプリケーション コードが使用するスクリプト コードに関数を実装します。

     次の HTML SCRIPT 要素は、関数の例を提供しています。 コントロールの <xref:System.Windows.Forms.WebBrowser.Navigate%2A> メソッドを使用して読み込む、またはコントロールの <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> プロパティに割り当てる HTML ドキュメントの HEAD 要素に、このコードをコピーします。

    ```html
    <script>
    function test(message) {
        alert(message);
    }
    </script>
    ```

8. <xref:System.Windows.Forms.WebBrowser.Document%2A> プロパティを使用して、クライアント アプリケーション コードからスクリプト コードにアクセスします。

     たとえば、次のコードをボタンの <xref:System.Windows.Forms.Control.Click> イベント ハンドラーに追加します。

     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#8](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#8)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#8](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#8)]

9. DHTML のデバッグが完了したら、コントロールの <xref:System.Windows.Forms.WebBrowser.ScriptErrorsSuppressed%2A> プロパティを `true` に設定して、<xref:System.Windows.Forms.WebBrowser> コントロールがスクリプト コードの問題のエラー メッセージを表示しないようにします。

     [!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#9)]
     [!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#9)]

## <a name="example"></a>例

次の完全なコード例は、この機能を理解するために使用できるデモ アプリケーションを示します。 HTML コードは、個別の HTML ファイルから読み込まれる代わりに、<xref:System.Windows.Forms.WebBrowser.DocumentText%2A> プロパティを通じて <xref:System.Windows.Forms.WebBrowser> コントロールに読み込まれます。

[!code-csharp[System.Windows.Forms.WebBrowser.ObjectForScripting#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/CS/form1.cs#0)]
[!code-vb[System.Windows.Forms.WebBrowser.ObjectForScripting#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser.ObjectForScripting/vb/form1.vb#0)]

## <a name="compiling-the-code"></a>コードのコンパイル

このコードには、次のものが必要です。

- System アセンブリおよび System.Windows.Forms アセンブリへの参照。

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.Document%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A?displayProperty=nameWithType>
- [WebBrowser コントロール](webbrowser-control-windows-forms.md)
