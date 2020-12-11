---
title: Web ブラウザー機能をアプリに追加する
description: WebBrowser コントロールを使用して Windows フォームアプリケーションに web ブラウザーの機能を追加する方法について説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- WebBrowser control [Windows Forms], adding Web browser capabilities to your application
- WebBrowser control [Windows Forms], examples
- Web browsers [.NET Framework], adding to Windows Forms
- examples [Windows Forms], WebBrowser control
- Windows Forms, adding Web browser functionality
ms.assetid: 3871f072-b57a-435b-9976-e5da28df04a7
ms.openlocfilehash: a5a33961ac8301bda86bb5f34e65ac159308987f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981987"
---
# <a name="how-to-add-web-browser-capabilities-to-a-windows-forms-application"></a><span data-ttu-id="2f7a9-103">Windows フォームアプリケーションに web ブラウザーの機能を追加する方法</span><span class="sxs-lookup"><span data-stu-id="2f7a9-103">How to add web browser capabilities to a Windows Forms application</span></span>

<span data-ttu-id="2f7a9-104"><xref:System.Windows.Forms.WebBrowser> コントロールを使用して、Web ブラウザーの機能をアプリケーションに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="2f7a9-104">With the <xref:System.Windows.Forms.WebBrowser> control, you can add Web browser functionality to your application.</span></span> <span data-ttu-id="2f7a9-105">コントロールは、既定では、Web ブラウザーのように動作します。</span><span class="sxs-lookup"><span data-stu-id="2f7a9-105">The control works like a Web browser by default.</span></span> <span data-ttu-id="2f7a9-106"><xref:System.Windows.Forms.WebBrowser.Url%2A> プロパティを設定することで、最初の URL を読み込んだ後に、ハイパーリンクをクリックするか、キーボード ショートカットを使用して、ナビゲーション履歴で前または次に移動できます。</span><span class="sxs-lookup"><span data-stu-id="2f7a9-106">After you load an initial URL by setting the <xref:System.Windows.Forms.WebBrowser.Url%2A> property, you can navigate by clicking hyperlinks or by using keyboard shortcuts to move backward and forward through navigation history.</span></span> <span data-ttu-id="2f7a9-107">既定では、右クリックして表示されるショートカット メニューからその他のブラウザーの機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2f7a9-107">By default, you can access additional browser functionality through the right-click shortcut menu.</span></span> <span data-ttu-id="2f7a9-108">また、コントロールにドロップすることで、新しいドキュメントを開くこともできます。</span><span class="sxs-lookup"><span data-stu-id="2f7a9-108">You can also open new documents by dropping them onto the control.</span></span> <span data-ttu-id="2f7a9-109"><xref:System.Windows.Forms.WebBrowser> コントロールには、Internet Explorer に似たユーザー インターフェイスの機能を実装するために使用できる、いくつかのプロパティ、メソッド、およびイベントもあります。</span><span class="sxs-lookup"><span data-stu-id="2f7a9-109">The <xref:System.Windows.Forms.WebBrowser> control also has several properties, methods, and events that you can use to implement user interface features similar to those found in Internet Explorer.</span></span>

<span data-ttu-id="2f7a9-110">次のコード例では、アドレス バー、標準的なブラウザーのボタン、**[ファイル]** メニュー、ステータス バー、および現在のページのタイトルを表示するタイトル バーが実装されます。</span><span class="sxs-lookup"><span data-stu-id="2f7a9-110">The following code example implements an address bar, typical browser buttons, a **File** menu, a status bar, and a title bar that displays the current page title.</span></span>

## <a name="example"></a><span data-ttu-id="2f7a9-111">例</span><span class="sxs-lookup"><span data-stu-id="2f7a9-111">Example</span></span>

[!code-cpp[System.Windows.Forms.WebBrowser#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/CPP/form1.cpp#0)]
[!code-csharp[System.Windows.Forms.WebBrowser#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/CS/form1.cs#0)]
[!code-vb[System.Windows.Forms.WebBrowser#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/VB/form1.vb#0)]
  
## <a name="compile-the-code"></a><span data-ttu-id="2f7a9-112">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="2f7a9-112">Compile the code</span></span>

<span data-ttu-id="2f7a9-113">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2f7a9-113">This example requires:</span></span>

- <span data-ttu-id="2f7a9-114">`System`、`System.Drawing`、および `System.Windows.Forms` の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="2f7a9-114">References to the `System`, `System.Drawing`, and `System.Windows.Forms` assemblies.</span></span>

## <a name="see-also"></a><span data-ttu-id="2f7a9-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="2f7a9-115">See also</span></span>

- <xref:System.Windows.Forms.WebBrowser>
- [<span data-ttu-id="2f7a9-116">WebBrowser コントロール</span><span class="sxs-lookup"><span data-stu-id="2f7a9-116">WebBrowser Control</span></span>](webbrowser-control-windows-forms.md)
