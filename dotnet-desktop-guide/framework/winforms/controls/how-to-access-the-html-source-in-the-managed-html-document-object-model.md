---
title: '方法: マネージド HTML DOM (Document Object Model) の HTML ソースにアクセスする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- managed HTML DOM
- HTML [Windows Forms], accessing in Windows Forms
ms.assetid: 53db79fa-8a5e-448e-88c2-f54ace3860b6
ms.openlocfilehash: 2db3e5a16268d71d972a84d65b3f0aa37771923c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981483"
---
# <a name="how-to-access-the-html-source-in-the-managed-html-document-object-model"></a>方法: マネージド HTML DOM (Document Object Model) の HTML ソースにアクセスする

<xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> コントロールの <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> プロパティおよび <xref:System.Windows.Forms.WebBrowser> プロパティは、現在のドキュメントが最初に表示されたときに存在した HTML を返します。 ただし、<xref:System.Windows.Forms.HtmlElement.AppendChild%2A> や <xref:System.Windows.Forms.HtmlElement.InnerHtml%2A> のようなメソッド呼び出しやプロパティ呼び出しを使用してページを変更すると、<xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> や <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> を呼び出したときにこれらの変更は表示されません。 DOM の最新の HTML ソースを取得するには、HTML 要素の <xref:System.Windows.Forms.HtmlElement.OuterHtml%2A> プロパティを呼び出す必要があります。  
  
 次の手順では、動的ソースを取得し、別のショートカット メニューに表示する方法を示します。  
  
### <a name="retrieving-the-dynamic-source-with-the-outerhtml-property"></a>OuterHtml プロパティを使用した動的ソースの取得  
  
1. 新しい Windows フォーム アプリケーションを作成します。 1つのを使用して開始し、 <xref:System.Windows.Forms.Form> それを呼び出し `Form1` ます。  
  
2. <xref:System.Windows.Forms.WebBrowser>Windows フォームアプリケーションでコントロールをホストし、という名前を指定し `WebBrowser1` ます。 詳細については、「 [方法: Windows フォームアプリケーションに Web ブラウザーの機能を追加](how-to-add-web-browser-capabilities-to-a-windows-forms-application.md)する」を参照してください。  
  
3. アプリケーションで、という2つ目のを作成 <xref:System.Windows.Forms.Form> `CodeForm` します。  
  
4. <xref:System.Windows.Forms.RichTextBox>にコントロールを追加 `CodeForm` し、その <xref:System.Windows.Forms.Control.Dock%2A> プロパティをに設定し `Fill` ます。  
  
5. という名前のパブリックプロパティを作成 `CodeForm` `Code` します。  
  
     [!code-csharp[DisplayWebBrowserCode#1](~/samples/snippets/csharp/VS_Snippets_Winforms/DisplayWebBrowserCode/CS/CodeForm.cs#1)]
     [!code-vb[DisplayWebBrowserCode#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/DisplayWebBrowserCode/VB/CodeForm.vb#1)]  
  
6. という名前のコントロールをに追加 <xref:System.Windows.Forms.Button> `Button1` し、 <xref:System.Windows.Forms.Form> イベントを監視し <xref:System.Windows.Forms.Control.Click> ます。 イベントの監視の詳細については、「 [イベント](/dotnet/standard/events/index)」を参照してください。  
  
7. <xref:System.Windows.Forms.Control.Click> イベント ハンドラーに次のコードを追加します。  
  
     [!code-csharp[DisplayWebBrowserCode#2](~/samples/snippets/csharp/VS_Snippets_Winforms/DisplayWebBrowserCode/CS/Form1.cs#2)]
     [!code-vb[DisplayWebBrowserCode#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/DisplayWebBrowserCode/VB/Form1.vb#2)]  
  
## <a name="robust-programming"></a>信頼性の高いプログラミング  

 <xref:System.Windows.Forms.WebBrowser.Document%2A> の値を取得する前に、必ずテストしてください。 現在のページの読み込みが完了していない場合、<xref:System.Windows.Forms.WebBrowser.Document%2A> またはその 1 つ以上の子オブジェクトが初期化されていない可能性があります。  
  
## <a name="see-also"></a>関連項目

- [マネージド HTML DOM (Document Object Model) の使用](using-the-managed-html-document-object-model.md)
- [WebBrowser コントロールの概要](webbrowser-control-overview.md)
