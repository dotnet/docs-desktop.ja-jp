---
title: マネージド HTML DOM (Document Object Model) の非公開メンバーへのアクセス
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- unexposed members
- managed HTML DOM [Windows Forms], accessing unexposed members
ms.assetid: 762295bd-2355-4aa7-b43c-5bff997a33e6
ms.openlocfilehash: 525ef52ecbbc61fba787fa8286c56c638d837faf
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981127"
---
# <a name="accessing-unexposed-members-on-the-managed-html-document-object-model"></a><span data-ttu-id="aa38f-102">マネージド HTML DOM (Document Object Model) の非公開メンバーへのアクセス</span><span class="sxs-lookup"><span data-stu-id="aa38f-102">Accessing Unexposed Members on the Managed HTML Document Object Model</span></span>
<span data-ttu-id="aa38f-103">マネージ HTML ドキュメントオブジェクトモデル (DOM) には、すべての <xref:System.Windows.Forms.HtmlElement> html 要素が共通するプロパティ、メソッド、およびイベントを公開するというクラスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="aa38f-103">The managed HTML Document Object Model (DOM) contains a class called <xref:System.Windows.Forms.HtmlElement> that exposes the properties, methods, and events that all HTML elements have in common.</span></span> <span data-ttu-id="aa38f-104">ただし、マネージインターフェイスが直接公開しないメンバーにアクセスすることが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="aa38f-104">Sometimes, however, you will need to access members that the managed interface does not directly expose.</span></span> <span data-ttu-id="aa38f-105">このトピックでは、Web ページ内で定義されている JScript と VBScript 関数を含む、非公開メンバーにアクセスする2つの方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aa38f-105">This topic examines two ways for accessing unexposed members, including JScript and VBScript functions defined inside of a Web page.</span></span>  
  
## <a name="accessing-unexposed-members-through-managed-interfaces"></a><span data-ttu-id="aa38f-106">マネージインターフェイスを使用した非公開メンバーへのアクセス</span><span class="sxs-lookup"><span data-stu-id="aa38f-106">Accessing Unexposed Members through Managed Interfaces</span></span>  
 <span data-ttu-id="aa38f-107"><xref:System.Windows.Forms.HtmlDocument> とに <xref:System.Windows.Forms.HtmlElement> は、非公開メンバーへのアクセスを可能にする4つのメソッドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="aa38f-107"><xref:System.Windows.Forms.HtmlDocument> and <xref:System.Windows.Forms.HtmlElement> provide four methods that enable access to unexposed members.</span></span> <span data-ttu-id="aa38f-108">次の表は、型とそれらに対応するメソッドを示しています。</span><span class="sxs-lookup"><span data-stu-id="aa38f-108">The following table shows the types and their corresponding methods.</span></span>  
  
|<span data-ttu-id="aa38f-109">メンバーの型</span><span class="sxs-lookup"><span data-stu-id="aa38f-109">Member Type</span></span>|<span data-ttu-id="aa38f-110">メソッド</span><span class="sxs-lookup"><span data-stu-id="aa38f-110">Method(s)</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="aa38f-111">プロパティ ( <xref:System.Windows.Forms.HtmlElement> )</span><span class="sxs-lookup"><span data-stu-id="aa38f-111">Properties (<xref:System.Windows.Forms.HtmlElement>)</span></span>|<xref:System.Windows.Forms.HtmlElement.GetAttribute%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.SetAttribute%2A>|  
|<span data-ttu-id="aa38f-112">メソッド</span><span class="sxs-lookup"><span data-stu-id="aa38f-112">Methods</span></span>|<xref:System.Windows.Forms.HtmlElement.InvokeMember%2A>|  
|<span data-ttu-id="aa38f-113">イベント ( <xref:System.Windows.Forms.HtmlDocument> )</span><span class="sxs-lookup"><span data-stu-id="aa38f-113">Events (<xref:System.Windows.Forms.HtmlDocument>)</span></span>|<xref:System.Windows.Forms.HtmlDocument.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlDocument.DetachEventHandler%2A>|  
|<span data-ttu-id="aa38f-114">イベント ( <xref:System.Windows.Forms.HtmlElement> )</span><span class="sxs-lookup"><span data-stu-id="aa38f-114">Events (<xref:System.Windows.Forms.HtmlElement>)</span></span>|<xref:System.Windows.Forms.HtmlElement.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.DetachEventHandler%2A>|  
|<span data-ttu-id="aa38f-115">イベント ( <xref:System.Windows.Forms.HtmlWindow> )</span><span class="sxs-lookup"><span data-stu-id="aa38f-115">Events (<xref:System.Windows.Forms.HtmlWindow>)</span></span>|<xref:System.Windows.Forms.HtmlWindow.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlWindow.DetachEventHandler%2A>|  
  
 <span data-ttu-id="aa38f-116">これらのメソッドを使用する場合は、基になる適切な型の要素があることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="aa38f-116">When you use these methods, it is assumed that you have an element of the correct underlying type.</span></span> <span data-ttu-id="aa38f-117">たとえば、 `Submit` `FORM` `FORM` ユーザーがサーバーに送信する前に、の値に対していくつかの事前処理を実行できるように、HTML ページで要素のイベントをリッスンするとします。</span><span class="sxs-lookup"><span data-stu-id="aa38f-117">Suppose that you want to listen to the `Submit` event of a `FORM` element on an HTML page, so that you can perform some pre-processing on the `FORM`'s values before the user submits them to the server.</span></span> <span data-ttu-id="aa38f-118">理想的には、HTML を制御できる場合は、一意の `FORM` 属性を持つようにを定義し `ID` ます。</span><span class="sxs-lookup"><span data-stu-id="aa38f-118">Ideally, if you have control over the HTML, you would define the `FORM` to have a unique `ID` attribute.</span></span>  
  
```html  
<HTML>  
  
    <HEAD>  
        <TITLE>Form Page</TITLE>  
    </HEAD>  
  
    <BODY>  
        <FORM ID="form1">  
             ... form fields defined here ...  
        </FORM>  
    </BODY>  
  
</HTML>  
```  
  
 <span data-ttu-id="aa38f-119">このページをコントロールに読み込んだ後、メソッドを使用して <xref:System.Windows.Forms.WebBrowser> <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A> 、 `FORM` を引数として使用してを実行時に取得でき `form1` ます。</span><span class="sxs-lookup"><span data-stu-id="aa38f-119">After you load this page into the <xref:System.Windows.Forms.WebBrowser> control, you can use the <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A> method to retrieve the `FORM` at run time using `form1` as the argument.</span></span>  
  
 [!code-csharp[System.Windows.Forms.HtmlElement#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/CS/Form1.cs#10)]
 [!code-vb[System.Windows.Forms.HtmlElement#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/VB/Form1.vb#10)]  
  
## <a name="accessing-unmanaged-interfaces"></a><span data-ttu-id="aa38f-120">アンマネージインターフェイスへのアクセス</span><span class="sxs-lookup"><span data-stu-id="aa38f-120">Accessing Unmanaged Interfaces</span></span>  
 <span data-ttu-id="aa38f-121">また、各 DOM クラスによって公開されているアンマネージコンポーネントオブジェクトモデル (COM) インターフェイスを使用して、マネージ HTML DOM の非公開メンバーにアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="aa38f-121">You can also access unexposed members on the managed HTML DOM by using the unmanaged Component Object Model (COM) interfaces exposed by each DOM class.</span></span> <span data-ttu-id="aa38f-122">これは、非公開メンバーに対して複数の呼び出しを行う必要がある場合、または非公開メンバーがマネージ HTML DOM によってラップされていない他のアンマネージインターフェイスを返す場合に推奨されます。</span><span class="sxs-lookup"><span data-stu-id="aa38f-122">This is recommended if you have to make several calls against unexposed members, or if the unexposed members return other unmanaged interfaces not wrapped by the managed HTML DOM.</span></span>  
  
 <span data-ttu-id="aa38f-123">次の表は、マネージ HTML DOM を通じて公開されるすべてのアンマネージインターフェイスを示しています。</span><span class="sxs-lookup"><span data-stu-id="aa38f-123">The following table shows all of the unmanaged interfaces exposed through the managed HTML DOM.</span></span> <span data-ttu-id="aa38f-124">各リンクをクリックして、その使用法とコード例を説明します。</span><span class="sxs-lookup"><span data-stu-id="aa38f-124">Click on each link for an explanation of its usage and for example code.</span></span>  
  
|<span data-ttu-id="aa38f-125">Type</span><span class="sxs-lookup"><span data-stu-id="aa38f-125">Type</span></span>|<span data-ttu-id="aa38f-126">アンマネージインターフェイス</span><span class="sxs-lookup"><span data-stu-id="aa38f-126">Unmanaged Interface</span></span>|  
|----------|-------------------------|  
|<xref:System.Windows.Forms.HtmlDocument>|<xref:System.Windows.Forms.HtmlDocument.DomDocument%2A>|  
|<xref:System.Windows.Forms.HtmlElement>|<xref:System.Windows.Forms.HtmlElement.DomElement%2A>|  
|<xref:System.Windows.Forms.HtmlWindow>|<xref:System.Windows.Forms.HtmlWindow.DomWindow%2A>|  
|<xref:System.Windows.Forms.HtmlHistory>|<xref:System.Windows.Forms.HtmlHistory.DomHistory%2A>|  
  
 <span data-ttu-id="aa38f-127">COM インターフェイスを使用する最も簡単な方法は、アプリケーションからアンマネージ HTML DOM library (MSHTML.dll) への参照を追加することです。ただし、この方法はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="aa38f-127">The easiest way to use the COM interfaces is to add a reference to the unmanaged HTML DOM library (MSHTML.dll) from your application, although this is unsupported.</span></span> <span data-ttu-id="aa38f-128">詳細については、 [サポート技術情報の記事 934368](https://support.microsoft.com/kb/934368)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa38f-128">For more information, see [Knowledge Base Article 934368](https://support.microsoft.com/kb/934368).</span></span>  
  
## <a name="accessing-script-functions"></a><span data-ttu-id="aa38f-129">スクリプト関数へのアクセス</span><span class="sxs-lookup"><span data-stu-id="aa38f-129">Accessing Script Functions</span></span>  
 <span data-ttu-id="aa38f-130">HTML ページでは、JScript や VBScript などのスクリプト言語を使用して1つ以上の関数を定義できます。</span><span class="sxs-lookup"><span data-stu-id="aa38f-130">An HTML page can define one or more functions by using a scripting language such as JScript or VBScript.</span></span> <span data-ttu-id="aa38f-131">これらの関数はページ内のページ内に配置され、 `SCRIPT` 必要に応じて、または DOM のイベントに応答して実行できます。</span><span class="sxs-lookup"><span data-stu-id="aa38f-131">These functions are placed inside of a `SCRIPT` page in the page, and can be run on demand or in response to an event on the DOM.</span></span>  
  
 <span data-ttu-id="aa38f-132">HTML ページで定義したスクリプト関数は、メソッドを使用して呼び出すことができ <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="aa38f-132">You can call any script functions you define in an HTML page using the <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A> method.</span></span> <span data-ttu-id="aa38f-133">スクリプトメソッドが HTML 要素を返す場合は、キャストを使用して、この戻り結果をに変換でき <xref:System.Windows.Forms.HtmlElement> ます。</span><span class="sxs-lookup"><span data-stu-id="aa38f-133">If the script method returns an HTML element, you can use a cast to convert this return result to an <xref:System.Windows.Forms.HtmlElement>.</span></span> <span data-ttu-id="aa38f-134">詳細とコード例については、「」を参照してください <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A> 。</span><span class="sxs-lookup"><span data-stu-id="aa38f-134">For details and example code, see <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa38f-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="aa38f-135">See also</span></span>

- [<span data-ttu-id="aa38f-136">マネージド HTML DOM (Document Object Model) の使用</span><span class="sxs-lookup"><span data-stu-id="aa38f-136">Using the Managed HTML Document Object Model</span></span>](using-the-managed-html-document-object-model.md)
