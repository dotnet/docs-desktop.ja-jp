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
# <a name="how-to-create-an-html-document-viewer-in-a-windows-forms-application"></a><span data-ttu-id="94b79-102">方法: Windows フォーム アプリケーションで HTML ドキュメントビューアーを作成する</span><span class="sxs-lookup"><span data-stu-id="94b79-102">How to: Create an HTML Document Viewer in a Windows Forms Application</span></span>
<span data-ttu-id="94b79-103">コントロールを使用して、 <xref:System.Windows.Forms.WebBrowser> インターネット Web ブラウザーのすべての機能を提供することなく、HTML ドキュメントを表示および印刷できます。</span><span class="sxs-lookup"><span data-stu-id="94b79-103">You can use the <xref:System.Windows.Forms.WebBrowser> control to display and print HTML documents without providing the full functionality of an Internet Web browser.</span></span> <span data-ttu-id="94b79-104">これは、HTML の書式設定機能を利用するが、信頼されていない Web コントロールや悪意のあるスクリプトコードを含む可能性のある任意の Web ページをユーザーが読み込まないようにする場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="94b79-104">This is useful when you want to take advantage of the formatting capabilities of HTML but do not want your users to load arbitrary Web pages that may contain untrusted Web controls or potentially malicious script code.</span></span> <span data-ttu-id="94b79-105">このようにコントロールの機能を制限することができます <xref:System.Windows.Forms.WebBrowser> 。たとえば、html 電子メールビューアーとして使用したり、アプリケーションで html 形式のヘルプを提供したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="94b79-105">You might want to restrict the capability of the <xref:System.Windows.Forms.WebBrowser> control in this manner, for example, to use it as an HTML email viewer or to provide HTML-formatted help in your application.</span></span>  
  
### <a name="to-create-an-html-document-viewer"></a><span data-ttu-id="94b79-106">HTML ドキュメントビューアーを作成するには</span><span class="sxs-lookup"><span data-stu-id="94b79-106">To create an HTML document viewer</span></span>  
  
1. <span data-ttu-id="94b79-107">プロパティをに設定すると <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> `false` 、 <xref:System.Windows.Forms.WebBrowser> コントロールがその上にドロップされたファイルを開かないようにします。</span><span class="sxs-lookup"><span data-stu-id="94b79-107">Set the <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> property to `false` to prevent the <xref:System.Windows.Forms.WebBrowser> control from opening files dropped onto it.</span></span>  
  
     [!code-csharp[WebBrowserMisc#20](~/samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#20)]
     [!code-vb[WebBrowserMisc#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#20)]  
  
2. <span data-ttu-id="94b79-108">プロパティを、 <xref:System.Windows.Forms.WebBrowser.Url%2A> 表示する初期ファイルの場所に設定します。</span><span class="sxs-lookup"><span data-stu-id="94b79-108">Set the <xref:System.Windows.Forms.WebBrowser.Url%2A> property to the location of the initial file to display.</span></span>  
  
     [!code-csharp[WebBrowserMisc#21](~/samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#21)]
     [!code-vb[WebBrowserMisc#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="94b79-109">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="94b79-109">Compiling the Code</span></span>  
 <span data-ttu-id="94b79-110">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="94b79-110">This example requires:</span></span>  
  
- <span data-ttu-id="94b79-111">`webBrowser1` という名前の <xref:System.Windows.Forms.WebBrowser> コントロール。</span><span class="sxs-lookup"><span data-stu-id="94b79-111">A <xref:System.Windows.Forms.WebBrowser> control named `webBrowser1`.</span></span>  
  
- <span data-ttu-id="94b79-112">`System` アセンブリおよび `System.Windows.Forms` アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="94b79-112">References to the `System` and `System.Windows.Forms` assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94b79-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="94b79-113">See also</span></span>

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>
- <xref:System.Windows.Forms.WebBrowser.Url%2A>
- [<span data-ttu-id="94b79-114">WebBrowser コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="94b79-114">WebBrowser Control Overview</span></span>](webbrowser-control-overview.md)
- [<span data-ttu-id="94b79-115">WebBrowser セキュリティ</span><span class="sxs-lookup"><span data-stu-id="94b79-115">WebBrowser Security</span></span>](webbrowser-security.md)
- [<span data-ttu-id="94b79-116">方法: WebBrowser コントロールで URL に移動する</span><span class="sxs-lookup"><span data-stu-id="94b79-116">How to: Navigate to a URL with the WebBrowser Control</span></span>](how-to-navigate-to-a-url-with-the-webbrowser-control.md)
- [<span data-ttu-id="94b79-117">方法: WebBrowser コントロールを使用して印刷する</span><span class="sxs-lookup"><span data-stu-id="94b79-117">How to: Print with a WebBrowser Control</span></span>](how-to-print-with-a-webbrowser-control.md)
