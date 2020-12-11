---
title: '方法: OpenFileDialog コンポーネントを使用してファイルを開く'
ms.date: 02/11/2019
description: OpenFileDialog コンポーネントを使用して、ファイルを参照および選択するための [Windows] ダイアログボックスを開く方法について説明します。
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], opening files
- OpenFile method [Windows Forms], OpenFileDialog component
- files [Windows Forms], opening with OpenFileDialog component
ms.assetid: 9d88367a-cc21-4ffd-be74-89fd63767d35
ms.openlocfilehash: 7021aacf09d7d927322abf1c9aa883bbb29507a8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974794"
---
# <a name="how-to-open-files-with-the-openfiledialog"></a><span data-ttu-id="dff83-103">方法: OpenFileDialog を使用してファイルを開く</span><span class="sxs-lookup"><span data-stu-id="dff83-103">How to: Open files with the OpenFileDialog</span></span>

<span data-ttu-id="dff83-104">[ <xref:System.Windows.Forms.OpenFileDialog?displayProperty=nameWithType> Windows] ダイアログボックスが開き、ファイルを参照して選択できます。</span><span class="sxs-lookup"><span data-stu-id="dff83-104">The <xref:System.Windows.Forms.OpenFileDialog?displayProperty=nameWithType> component opens the Windows dialog box for browsing and selecting files.</span></span> <span data-ttu-id="dff83-105">選択したファイルを開いて読み取るに <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A?displayProperty=nameWithType> は、メソッドを使用するか、クラスのインスタンスを作成し <xref:System.IO.StreamReader?displayProperty=nameWithType> ます。</span><span class="sxs-lookup"><span data-stu-id="dff83-105">To open and read the selected files, you can use the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A?displayProperty=nameWithType> method, or create an instance of the <xref:System.IO.StreamReader?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="dff83-106">次の例では、両方の方法を示します。</span><span class="sxs-lookup"><span data-stu-id="dff83-106">The following examples show both approaches.</span></span>

<span data-ttu-id="dff83-107">.NET Framework では、プロパティを取得または設定するには、 <xref:System.Windows.Forms.FileDialog.FileName%2A> クラスによって権限レベルが付与されている必要があり <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> ます。</span><span class="sxs-lookup"><span data-stu-id="dff83-107">In .NET Framework, to get or set the <xref:System.Windows.Forms.FileDialog.FileName%2A> property requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="dff83-108">この例では、 <xref:System.Security.Permissions.FileIOPermission> アクセス許可チェックを実行し、部分信頼コンテキストで実行する場合は特権が不足しているため例外をスローできます。</span><span class="sxs-lookup"><span data-stu-id="dff83-108">The examples run a <xref:System.Security.Permissions.FileIOPermission> permission check, and can throw an exception due to insufficient privileges if run in a partial-trust context.</span></span> <span data-ttu-id="dff83-109">詳細については、「 [コードアクセスセキュリティの基礎](/dotnet/framework/misc/code-access-security-basics)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dff83-109">For more information, see [Code access security basics](/dotnet/framework/misc/code-access-security-basics).</span></span>

<span data-ttu-id="dff83-110">これらの例は、C# または Visual Basic のコマンドラインから .NET Framework アプリとしてビルドして実行できます。</span><span class="sxs-lookup"><span data-stu-id="dff83-110">You can build and run these examples as .NET Framework apps from the C# or Visual Basic command line.</span></span> <span data-ttu-id="dff83-111">詳細については、「 [csc.exeを使用したコマンドライン ](/dotnet/csharp/language-reference/compiler-options/command-line-building-with-csc-exe) からのビルド」または「 [コマンドラインからのビルド](/dotnet/visual-basic/reference/command-line-compiler/building-from-the-command-line)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dff83-111">For more information, see [Command-line building with csc.exe](/dotnet/csharp/language-reference/compiler-options/command-line-building-with-csc-exe) or [Build from the command line](/dotnet/visual-basic/reference/command-line-compiler/building-from-the-command-line).</span></span>

<span data-ttu-id="dff83-112">.NET Core 3.0 以降では、.NET Core Windows フォーム *\<folder name> .csproj* プロジェクトファイルを持つフォルダーから、Windows .net core アプリとして例をビルドして実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="dff83-112">Starting with .NET Core 3.0, you can also build and run the examples as Windows .NET Core apps from a folder that has a .NET Core Windows Forms *\<folder name>.csproj* project file.</span></span>

## <a name="example-read-a-file-as-a-stream-with-streamreader"></a><span data-ttu-id="dff83-113">例: StreamReader を使用してファイルをストリームとして読み取る</span><span class="sxs-lookup"><span data-stu-id="dff83-113">Example: Read a file as a stream with StreamReader</span></span>  
  
<span data-ttu-id="dff83-114">次の例では、Windows フォームコントロールのイベントハンドラーを使用して、メソッドを使用してを <xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.Control.Click> 開き <xref:System.Windows.Forms.OpenFileDialog> <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="dff83-114">The following example uses the Windows Forms <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler to open the <xref:System.Windows.Forms.OpenFileDialog> with the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span> <span data-ttu-id="dff83-115">ユーザーがファイルを選択して **[OK]** を選択すると、クラスのインスタンスによって <xref:System.IO.StreamReader> ファイルが読み取られ、その内容がフォームのテキストボックスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="dff83-115">After the user chooses a file and selects **OK**, an instance of the <xref:System.IO.StreamReader> class reads the file and displays its contents in the form's text box.</span></span> <span data-ttu-id="dff83-116">ファイルストリームからの読み取りの詳細については、「」および「」を参照してください <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> <xref:System.IO.FileStream.Read%2A?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="dff83-116">For more information about reading from file streams, see <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> and <xref:System.IO.FileStream.Read%2A?displayProperty=nameWithType>.</span></span>  

 [!code-csharp[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/vb/Form1.vb)]  

## <a name="example-open-a-file-from-a-filtered-selection-with-openfile"></a><span data-ttu-id="dff83-117">例: OpenFile を使用してフィルター選択された選択からファイルを開く</span><span class="sxs-lookup"><span data-stu-id="dff83-117">Example: Open a file from a filtered selection with OpenFile</span></span>

<span data-ttu-id="dff83-118">次の例では <xref:System.Windows.Forms.Button> 、コントロールのイベントハンドラーを使用して <xref:System.Windows.Forms.Control.Click> 、 <xref:System.Windows.Forms.OpenFileDialog> テキストファイルのみを表示するフィルターを指定してを開きます。</span><span class="sxs-lookup"><span data-stu-id="dff83-118">The following example uses the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler to open the <xref:System.Windows.Forms.OpenFileDialog> with a filter that shows only text files.</span></span> <span data-ttu-id="dff83-119">ユーザーがテキストファイルを選択して **[OK]** を選択した後、メソッドを使用して <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> メモ帳でファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="dff83-119">After the user chooses a text file and selects **OK**, the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method is used to open the file in Notepad.</span></span>

 [!code-csharp[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/vb/Form1.vb)]  

## <a name="see-also"></a><span data-ttu-id="dff83-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="dff83-120">See also</span></span>

- <xref:System.Windows.Forms.OpenFileDialog>
- [<span data-ttu-id="dff83-121">OpenFileDialog コンポーネント</span><span class="sxs-lookup"><span data-stu-id="dff83-121">OpenFileDialog component</span></span>](openfiledialog-component-windows-forms.md)
