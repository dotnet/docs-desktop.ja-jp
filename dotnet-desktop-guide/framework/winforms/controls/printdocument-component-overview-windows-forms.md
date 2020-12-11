---
title: PrintDocument コンポーネントの概要
ms.date: 03/30/2017
f1_keywords:
- PrintDocument
helpviewer_keywords:
- PrintDocument component [Windows Forms], about PrintDocument component
- printing [Windows Forms], PrintDocument component
ms.assetid: b59b4b60-dce5-42ca-8421-3a54a2f7bab0
ms.openlocfilehash: 96b18a44853d836cb0f16ba0e8372a825e998b74
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980554"
---
# <a name="printdocument-component-overview-windows-forms"></a><span data-ttu-id="7c8f7-102">PrintDocument コンポーネントの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="7c8f7-102">PrintDocument Component Overview (Windows Forms)</span></span>

<span data-ttu-id="7c8f7-103">Windows フォーム [PrintDocument](printdocument-component-windows-forms.md) コンポーネントを使用して、印刷対象を示すプロパティを設定し、Windows ベースのアプリケーション内でドキュメントを印刷できます。</span><span class="sxs-lookup"><span data-stu-id="7c8f7-103">The Windows Forms [PrintDocument](printdocument-component-windows-forms.md) component is used to set the properties that describe what to print and the ability to print the document within Windows-based applications.</span></span> <span data-ttu-id="7c8f7-104">このコンポーネントは、ドキュメント印刷のあらゆる側面を制御するために、[PrintDialog](printdialog-component-windows-forms.md) コンポーネントと組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="7c8f7-104">It can be used in conjunction with the [PrintDialog](printdialog-component-windows-forms.md) component to be in control of all aspects of document printing.</span></span>

## <a name="working-with-the-printdocument-component"></a><span data-ttu-id="7c8f7-105">PrintDocument コンポーネントの操作</span><span class="sxs-lookup"><span data-stu-id="7c8f7-105">Working with the PrintDocument Component</span></span>

<span data-ttu-id="7c8f7-106">コンポーネントに関連する主なシナリオは、次の2つです <xref:System.Drawing.Printing.PrintDocument> 。</span><span class="sxs-lookup"><span data-stu-id="7c8f7-106">Two of the main scenarios that involve the <xref:System.Drawing.Printing.PrintDocument> component are:</span></span>

- <span data-ttu-id="7c8f7-107">簡易印刷ジョブ (個々のテキスト ファイルを印刷する場合など)。</span><span class="sxs-lookup"><span data-stu-id="7c8f7-107">Simple print jobs, such as printing an individual text file.</span></span> <span data-ttu-id="7c8f7-108">このような場合は、コンポーネントを <xref:System.Drawing.Printing.PrintDocument> Windows フォームに追加し、イベントハンドラーでファイルを出力するプログラミングロジックを追加し <xref:System.Drawing.Printing.PrintDocument.PrintPage> ます。</span><span class="sxs-lookup"><span data-stu-id="7c8f7-108">In such a case you would add the <xref:System.Drawing.Printing.PrintDocument> component to a Windows Form, then add programming logic that prints a file in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler.</span></span> <span data-ttu-id="7c8f7-109">プログラミングロジックは、 <xref:System.Drawing.Printing.PrintDocument.Print%2A> ドキュメントを印刷するメソッドとなする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c8f7-109">The programming logic should culminate with the <xref:System.Drawing.Printing.PrintDocument.Print%2A> method to print the document.</span></span> <span data-ttu-id="7c8f7-110">このメソッドは、 <xref:System.Drawing.Graphics> クラスのプロパティに含まれるオブジェクトを <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> <xref:System.Drawing.Printing.PrintPageEventArgs> プリンターに送信します。</span><span class="sxs-lookup"><span data-stu-id="7c8f7-110">This method sends a <xref:System.Drawing.Graphics> object, contained in the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class, to the printer.</span></span> <span data-ttu-id="7c8f7-111">コンポーネントを使用してテキストドキュメントを印刷する方法を示す例につい <xref:System.Drawing.Printing.PrintDocument> ては、「 [方法: Windows フォームで複数ページのテキストファイルを印刷](../advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c8f7-111">For an example that shows how to print a text document using the <xref:System.Drawing.Printing.PrintDocument> component, see [How to: Print a Multi-Page Text File in Windows Forms](../advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md).</span></span>

- <span data-ttu-id="7c8f7-112">より複雑な印刷ジョブ (作成した印刷ロジックを再利用する場合など)。</span><span class="sxs-lookup"><span data-stu-id="7c8f7-112">More complex print jobs, such as a situation where you will want to reuse printing logic you have written.</span></span> <span data-ttu-id="7c8f7-113">このような場合は、コンポーネントから新しいコンポーネントを派生させ、 <xref:System.Drawing.Printing.PrintDocument> イベントを[](/dotnet/visual-basic/language-reference/modifiers/overrides)オーバーライドします (「C# の Visual Basic または[オーバーライド](/dotnet/csharp/language-reference/keywords/override)のオーバーライド」を参照してください) <xref:System.Drawing.Printing.PrintDocument.PrintPage> 。</span><span class="sxs-lookup"><span data-stu-id="7c8f7-113">In such a case you would derive a new component from the <xref:System.Drawing.Printing.PrintDocument> component and override (see [Overrides](/dotnet/visual-basic/language-reference/modifiers/overrides) for Visual Basic or [override](/dotnet/csharp/language-reference/keywords/override) for C#) the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>

<span data-ttu-id="7c8f7-114">フォームに追加されると、 <xref:System.Drawing.Printing.PrintDocument> Visual Studio の Windows フォームデザイナーの下部にあるトレイにコンポーネントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7c8f7-114">When it is added to a form, the <xref:System.Drawing.Printing.PrintDocument> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="7c8f7-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="7c8f7-115">See also</span></span>

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="7c8f7-116">Windows フォームにおける印刷のサポート</span><span class="sxs-lookup"><span data-stu-id="7c8f7-116">Windows Forms Print Support</span></span>](../advanced/windows-forms-print-support.md)
- [<span data-ttu-id="7c8f7-117">PrintDocument コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7c8f7-117">PrintDocument Component</span></span>](printdocument-component-windows-forms.md)
