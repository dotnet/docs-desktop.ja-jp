---
title: '方法: マネージド HTML DOM (Document Object Model) の要素のスタイルを変更する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- managed HTML DOM [Windows Forms], changing styles on elements
ms.assetid: 154e8d9f-3e2d-4e8b-a6f3-c85a070e9cc1
ms.openlocfilehash: 728bc77db959e25fe31d2ff37288b2359dca852e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980932"
---
# <a name="how-to-change-styles-on-an-element-in-the-managed-html-document-object-model"></a>方法: マネージド HTML DOM (Document Object Model) の要素のスタイルを変更する

HTML のスタイルを使用して、ドキュメントとその要素の外観を制御できます。 <xref:System.Windows.Forms.HtmlDocument> と <xref:System.Windows.Forms.HtmlElement> <xref:System.Windows.Forms.HtmlElement.Style%2A> は、次の形式のスタイル文字列を受け取るプロパティをサポートしています。

`name1:value1;...;nameN:valueN;`

`DIV`フォントを Arial に設定し、すべてのテキストを太字に設定するスタイル文字列を含むの例を次に示します。

```html
<DIV style="font-face:arial;font-weight:bold;">
Hello, world!
</DIV>
```

プロパティを使用してスタイルを操作する際の問題点 <xref:System.Windows.Forms.HtmlElement.Style%2A> は、文字列から個々のスタイル設定を追加したり削除したりすることが煩雑になる可能性があることです。 たとえば、ユーザーが上にカーソルを置いたときに、前のテキストを斜体で表示 `DIV` し、カーソルがを離れると斜体にするという複雑な手順になり `DIV` ます。 多くのスタイルをこの方法で操作する必要がある場合、時間は問題になります。

次の手順には、HTML ドキュメントおよび要素のスタイルを簡単に操作するために使用できるコードが含まれています。 この手順では、新しいプロジェクトの作成やフォームへのコントロールの追加など、Windows フォームで基本的なタスクを実行する方法を理解している必要があります。

### <a name="to-process-style-changes-in-a-windows-forms-application"></a>Windows フォームアプリケーションでスタイルの変更を処理するには

1. 新しい Windows フォーム プロジェクトを作成します。

2. プログラミング言語に適した拡張機能で終了する新しいクラスファイルを作成します。

3. `StyleGenerator`このトピックの「Example」セクションのクラスコードをクラスファイルにコピーし、コードを保存します。

4. 次の HTML を Test.htm という名前のファイルに保存します。

    ```html
    <HTML>
        <BODY>

            <DIV style="font-face:arial;font-weight:bold;">
                Hello, world!
            </DIV><P>

            <DIV>
                Hello again, world!
            </DIV><P>

        </BODY>
    </HTML>
    ```

5. <xref:System.Windows.Forms.WebBrowser>という名前のコントロールを `webBrowser1` プロジェクトのメインフォームに追加します。

6. 次のコードをプロジェクトのコードファイルに追加します。

    > [!IMPORTANT]
    > イベント `webBrowser1_DocumentCompleted` ハンドラーがイベントのリスナーとして構成されていることを確認し <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> ます。 Visual Studio で、コントロールをダブルクリックします <xref:System.Windows.Forms.WebBrowser> 。テキストエディターで、プログラムによってリスナーを構成します。

     [!code-csharp[ManagedDOMStyles#2](~/samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/Form1.cs#2)]
     [!code-vb[ManagedDOMStyles#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/Form1.vb#2)]

7. プロジェクトを実行します。 カーソルを最初の行に対して実行して、 `DIV` コードの効果を観察します。

## <a name="example"></a>例

次のコード例は、 `StyleGenerator` 既存のスタイル値を解析し、スタイルの追加、変更、および削除をサポートし、要求された変更を含む新しいスタイル値を返すクラスの完全なコードを示しています。

[!code-csharp[ManagedDOMStyles#1](~/samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/StyleGenerator.cs#1)]
[!code-vb[ManagedDOMStyles#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/StyleGenerator.vb#1)]

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.HtmlElement>
