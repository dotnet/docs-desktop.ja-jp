---
title: Windows フォームアプリで HTML ドキュメントビューアーを作成する
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WebBrowser control [Windows Forms], creating an HTML document viewer
- document viewers
- Windows Forms, creating document viewers
ms.assetid: 6a6338fe-f7ee-4f5e-9d8f-0465c57e9039
ms.openlocfilehash: 913bc86af034645b4b8cf3d69da4c9def58fc19c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982187"
---
# <a name="how-to-create-an-html-document-viewer-in-a-windows-forms-application"></a>方法: Windows フォーム アプリケーションで HTML ドキュメントビューアーを作成する
コントロールを使用して、 <xref:System.Windows.Forms.WebBrowser> インターネット Web ブラウザーのすべての機能を提供することなく、HTML ドキュメントを表示および印刷できます。 これは、HTML の書式設定機能を利用するが、信頼されていない Web コントロールや悪意のあるスクリプトコードを含む可能性のある任意の Web ページをユーザーが読み込まないようにする場合に便利です。 このようにコントロールの機能を制限することができます <xref:System.Windows.Forms.WebBrowser> 。たとえば、html 電子メールビューアーとして使用したり、アプリケーションで html 形式のヘルプを提供したりすることができます。  
  
### <a name="to-create-an-html-document-viewer"></a>HTML ドキュメントビューアーを作成するには  
  
1. プロパティをに設定すると <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> `false` 、 <xref:System.Windows.Forms.WebBrowser> コントロールがその上にドロップされたファイルを開かないようにします。  
  
     [!code-csharp[WebBrowserMisc#20](~/samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#20)]
     [!code-vb[WebBrowserMisc#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#20)]  
  
2. プロパティを、 <xref:System.Windows.Forms.WebBrowser.Url%2A> 表示する初期ファイルの場所に設定します。  
  
     [!code-csharp[WebBrowserMisc#21](~/samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#21)]
     [!code-vb[WebBrowserMisc#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#21)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 この例で必要な要素は次のとおりです。  
  
- `webBrowser1` という名前の <xref:System.Windows.Forms.WebBrowser> コントロール。  
  
- `System` アセンブリおよび `System.Windows.Forms` アセンブリへの参照。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>
- <xref:System.Windows.Forms.WebBrowser.Url%2A>
- [WebBrowser コントロールの概要](webbrowser-control-overview.md)
- [WebBrowser セキュリティ](webbrowser-security.md)
- [方法: WebBrowser コントロールで URL に移動する](how-to-navigate-to-a-url-with-the-webbrowser-control.md)
- [方法: WebBrowser コントロールを使用して印刷する](how-to-print-with-a-webbrowser-control.md)
