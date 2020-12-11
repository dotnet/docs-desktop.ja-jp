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
# <a name="how-to-change-styles-on-an-element-in-the-managed-html-document-object-model"></a><span data-ttu-id="9ebf5-102">方法: マネージド HTML DOM (Document Object Model) の要素のスタイルを変更する</span><span class="sxs-lookup"><span data-stu-id="9ebf5-102">How to: Change Styles on an Element in the Managed HTML Document Object Model</span></span>

<span data-ttu-id="9ebf5-103">HTML のスタイルを使用して、ドキュメントとその要素の外観を制御できます。</span><span class="sxs-lookup"><span data-stu-id="9ebf5-103">You can use styles in HTML to control the appearance of a document and its elements.</span></span> <span data-ttu-id="9ebf5-104"><xref:System.Windows.Forms.HtmlDocument> と <xref:System.Windows.Forms.HtmlElement> <xref:System.Windows.Forms.HtmlElement.Style%2A> は、次の形式のスタイル文字列を受け取るプロパティをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="9ebf5-104"><xref:System.Windows.Forms.HtmlDocument> and <xref:System.Windows.Forms.HtmlElement> support <xref:System.Windows.Forms.HtmlElement.Style%2A> properties that take style strings of the following format:</span></span>

`name1:value1;...;nameN:valueN;`

<span data-ttu-id="9ebf5-105">`DIV`フォントを Arial に設定し、すべてのテキストを太字に設定するスタイル文字列を含むの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9ebf5-105">Here is a `DIV` with a style string that sets the font to Arial and all text to bold:</span></span>

```html
<DIV style="font-face:arial;font-weight:bold;">
Hello, world!
</DIV>
```

<span data-ttu-id="9ebf5-106">プロパティを使用してスタイルを操作する際の問題点 <xref:System.Windows.Forms.HtmlElement.Style%2A> は、文字列から個々のスタイル設定を追加したり削除したりすることが煩雑になる可能性があることです。</span><span class="sxs-lookup"><span data-stu-id="9ebf5-106">The problem with manipulating styles using the <xref:System.Windows.Forms.HtmlElement.Style%2A> property is that it can prove cumbersome to add to and remove individual style settings from the string.</span></span> <span data-ttu-id="9ebf5-107">たとえば、ユーザーが上にカーソルを置いたときに、前のテキストを斜体で表示 `DIV` し、カーソルがを離れると斜体にするという複雑な手順になり `DIV` ます。</span><span class="sxs-lookup"><span data-stu-id="9ebf5-107">For example, it would become a complex procedure for you to render the previous text in italics whenever the user positions the cursor over the `DIV`, and take italics off when the cursor leaves the `DIV`.</span></span> <span data-ttu-id="9ebf5-108">多くのスタイルをこの方法で操作する必要がある場合、時間は問題になります。</span><span class="sxs-lookup"><span data-stu-id="9ebf5-108">Time would become an issue if you need to manipulate a large number of styles in this manner.</span></span>

<span data-ttu-id="9ebf5-109">次の手順には、HTML ドキュメントおよび要素のスタイルを簡単に操作するために使用できるコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9ebf5-109">The following procedure contains code that you can use to easily manipulate styles on HTML documents and elements.</span></span> <span data-ttu-id="9ebf5-110">この手順では、新しいプロジェクトの作成やフォームへのコントロールの追加など、Windows フォームで基本的なタスクを実行する方法を理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ebf5-110">The procedure requires that you know how to perform basic tasks in Windows Forms, such as creating a new project and adding a control to a form.</span></span>

### <a name="to-process-style-changes-in-a-windows-forms-application"></a><span data-ttu-id="9ebf5-111">Windows フォームアプリケーションでスタイルの変更を処理するには</span><span class="sxs-lookup"><span data-stu-id="9ebf5-111">To process style changes in a Windows Forms application</span></span>

1. <span data-ttu-id="9ebf5-112">新しい Windows フォーム プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="9ebf5-112">Create a new Windows Forms project.</span></span>

2. <span data-ttu-id="9ebf5-113">プログラミング言語に適した拡張機能で終了する新しいクラスファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="9ebf5-113">Create a new class file ending in the extension appropriate for your programming language.</span></span>

3. <span data-ttu-id="9ebf5-114">`StyleGenerator`このトピックの「Example」セクションのクラスコードをクラスファイルにコピーし、コードを保存します。</span><span class="sxs-lookup"><span data-stu-id="9ebf5-114">Copy the `StyleGenerator` class code in the Example section of this topic into the class file, and save the code.</span></span>

4. <span data-ttu-id="9ebf5-115">次の HTML を Test.htm という名前のファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="9ebf5-115">Save the following HTML to a file named Test.htm.</span></span>

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

5. <span data-ttu-id="9ebf5-116"><xref:System.Windows.Forms.WebBrowser>という名前のコントロールを `webBrowser1` プロジェクトのメインフォームに追加します。</span><span class="sxs-lookup"><span data-stu-id="9ebf5-116">Add a <xref:System.Windows.Forms.WebBrowser> control named `webBrowser1` to the main form of your project.</span></span>

6. <span data-ttu-id="9ebf5-117">次のコードをプロジェクトのコードファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="9ebf5-117">Add the following code to your project's code file.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="9ebf5-118">イベント `webBrowser1_DocumentCompleted` ハンドラーがイベントのリスナーとして構成されていることを確認し <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> ます。</span><span class="sxs-lookup"><span data-stu-id="9ebf5-118">Ensure that the `webBrowser1_DocumentCompleted` event handler is configured as a listener for the <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event.</span></span> <span data-ttu-id="9ebf5-119">Visual Studio で、コントロールをダブルクリックします <xref:System.Windows.Forms.WebBrowser> 。テキストエディターで、プログラムによってリスナーを構成します。</span><span class="sxs-lookup"><span data-stu-id="9ebf5-119">In Visual Studio, double-click on the <xref:System.Windows.Forms.WebBrowser> control; in a text editor, configure the listener programmatically.</span></span>

     [!code-csharp[ManagedDOMStyles#2](~/samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/Form1.cs#2)]
     [!code-vb[ManagedDOMStyles#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/Form1.vb#2)]

7. <span data-ttu-id="9ebf5-120">プロジェクトを実行します。</span><span class="sxs-lookup"><span data-stu-id="9ebf5-120">Run the project.</span></span> <span data-ttu-id="9ebf5-121">カーソルを最初の行に対して実行して、 `DIV` コードの効果を観察します。</span><span class="sxs-lookup"><span data-stu-id="9ebf5-121">Run your cursor over the first `DIV` to observe the effects of the code.</span></span>

## <a name="example"></a><span data-ttu-id="9ebf5-122">例</span><span class="sxs-lookup"><span data-stu-id="9ebf5-122">Example</span></span>

<span data-ttu-id="9ebf5-123">次のコード例は、 `StyleGenerator` 既存のスタイル値を解析し、スタイルの追加、変更、および削除をサポートし、要求された変更を含む新しいスタイル値を返すクラスの完全なコードを示しています。</span><span class="sxs-lookup"><span data-stu-id="9ebf5-123">The following code example shows the full code for the `StyleGenerator` class, which parses an existing style value, supports adding, changing, and removing styles, and returns a new style value with the requested changes.</span></span>

[!code-csharp[ManagedDOMStyles#1](~/samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/StyleGenerator.cs#1)]
[!code-vb[ManagedDOMStyles#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/StyleGenerator.vb#1)]

## <a name="see-also"></a><span data-ttu-id="9ebf5-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="9ebf5-124">See also</span></span>

- <xref:System.Windows.Forms.HtmlElement>
