---
title: ダイアログ ボックスの概要
description: 情報を収集して表示するために使用できる、Windows Foundation Presentation (WPF) のさまざまなダイアログ ボックスについて説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- modeless dialog boxes [WPF]
- dialog boxes [WPF]
- message boxes [WPF]
- modal dialog boxes [WPF]
ms.assetid: 0d23d544-a393-4a02-a3aa-d8cd5d3d6511
ms.openlocfilehash: db468f82445b8b6928b1713e779c95017a197da2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983132"
---
# <a name="dialog-boxes-overview"></a><span data-ttu-id="0fddf-103">ダイアログ ボックスの概要</span><span class="sxs-lookup"><span data-stu-id="0fddf-103">Dialog boxes overview</span></span>
<span data-ttu-id="0fddf-104">スタンドアロン アプリケーションには、通常、メイン ウィンドウがあり、そこには、アプリケーションが操作する主なデータが表示され、そのデータをメニュー バー、ツール バー、ステータス バーなどの [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] メカニズムを通じて処理する機能が公開されます。</span><span class="sxs-lookup"><span data-stu-id="0fddf-104">Standalone applications typically have a main window that both displays the main data over which the application operates and exposes the functionality to process that data through [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] mechanisms like menu bars, tool bars, and status bars.</span></span> <span data-ttu-id="0fddf-105">重要なアプリケーションは、次のようなことをするための追加のウィンドウを表示することもあります。</span><span class="sxs-lookup"><span data-stu-id="0fddf-105">A non-trivial application may also display additional windows to do the following:</span></span>  
  
- <span data-ttu-id="0fddf-106">固有の情報をユーザーに表示する。</span><span class="sxs-lookup"><span data-stu-id="0fddf-106">Display specific information to users.</span></span>  
  
- <span data-ttu-id="0fddf-107">ユーザーから情報を収集する。</span><span class="sxs-lookup"><span data-stu-id="0fddf-107">Gather information from users.</span></span>  
  
- <span data-ttu-id="0fddf-108">情報の表示と収集の両方を行う。</span><span class="sxs-lookup"><span data-stu-id="0fddf-108">Both display and gather information.</span></span>  
  
 <span data-ttu-id="0fddf-109">これらの種類のウィンドウは "*ダイアログ ボックス*" と呼ばれ、モーダルとモードレスの 2 種類があります。</span><span class="sxs-lookup"><span data-stu-id="0fddf-109">These types of windows are known as *dialog boxes*, and there are two types: modal and modeless.</span></span>  
  
 <span data-ttu-id="0fddf-110">"*モーダル*" ダイアログ ボックスは、機能が続行するにはユーザーからの追加データが必要なときに、機能によって表示されます。</span><span class="sxs-lookup"><span data-stu-id="0fddf-110">A *modal* dialog box is displayed by a function when the function needs additional data from a user to continue.</span></span> <span data-ttu-id="0fddf-111">機能は、モーダル ダイアログ ボックスに依存してデータを収集するため、モーダル ダイアログ ボックスが開いている間、ユーザーはアプリケーション内の他のウィンドウをアクティブ化することはできません。</span><span class="sxs-lookup"><span data-stu-id="0fddf-111">Because the function depends on the modal dialog box to gather data, the modal dialog box also prevents a user from activating other windows in the application while it remains open.</span></span> <span data-ttu-id="0fddf-112">ほとんどの場合、ユーザーは **[OK]** または **[キャンセル]** ボタンを押すことによって、モーダル ダイアログ ボックスの操作を終了したことをモーダル ダイアログ ボックスに知らせることができます。</span><span class="sxs-lookup"><span data-stu-id="0fddf-112">In most cases, a modal dialog box allows a user to signal when they have finished with the modal dialog box by pressing either an **OK** or **Cancel** button.</span></span> <span data-ttu-id="0fddf-113">**[OK]** ボタンを押すことは、ユーザーがデータを入力し、そのデータの処理を続行することを機能に求めていることを示します。</span><span class="sxs-lookup"><span data-stu-id="0fddf-113">Pressing the **OK** button indicates that a user has entered data and wants the function to continue processing with that data.</span></span> <span data-ttu-id="0fddf-114">**[キャンセル]** ボタンを押すことは、ユーザーが機能の実行を停止することを求めていることを示します。</span><span class="sxs-lookup"><span data-stu-id="0fddf-114">Pressing the **Cancel** button indicates that a user wants to stop the function from executing altogether.</span></span> <span data-ttu-id="0fddf-115">モーダル ダイアログ ボックスの最も一般的な例は、データを開く、保存する、および印刷するために表示されます。</span><span class="sxs-lookup"><span data-stu-id="0fddf-115">The most common examples of modal dialog boxes are shown to open, save, and print data.</span></span>  
  
 <span data-ttu-id="0fddf-116">一方、"*モードレス*" ダイアログ ボックスは、それが開いている間も、ユーザーは他のウィンドウをアクティブ化できます。</span><span class="sxs-lookup"><span data-stu-id="0fddf-116">A *modeless* dialog box, on the other hand, does not prevent a user from activating other windows while it is open.</span></span> <span data-ttu-id="0fddf-117">たとえば、ユーザーがドキュメント内の特定の単語の出現箇所を検索する場合、メイン ウィンドウは、多くの場合、ダイアログ ボックスを開いて、検索する単語をユーザーに尋ねます。</span><span class="sxs-lookup"><span data-stu-id="0fddf-117">For example, if a user wants to find occurrences of a particular word in a document, a main window will often open a dialog box to ask a user what word they are looking for.</span></span> <span data-ttu-id="0fddf-118">しかし、単語の検索中もユーザーはドキュメントを編集できるため、ダイアログ ボックスがモーダルである必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0fddf-118">Since finding a word doesn't prevent a user from editing the document, however, the dialog box doesn't need to be modal.</span></span> <span data-ttu-id="0fddf-119">モードレス ダイアログ ボックスには、少なくとも、ダイアログ ボックスを閉じる **[閉じる]** ボタンがあり、単語検索の検索条件に一致する次の単語を検索するための **[次を検索]** ボタンなど、特定の機能を実行するための追加のボタンが表示されることもあります。</span><span class="sxs-lookup"><span data-stu-id="0fddf-119">A modeless dialog box at least provides a **Close** button to close the dialog box, and may provide additional buttons to execute specific functions, such as a **Find Next** button to find the next word that matches the find criteria of a word search.</span></span>  
  
 <span data-ttu-id="0fddf-120">Windows Presentation Foundation (WPF) では、メッセージ ボックス、コモン ダイアログ ボックス、カスタム ダイアログ ボックスなど、いくつかの種類のダイアログ ボックスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="0fddf-120">Windows Presentation Foundation (WPF) allows you to create several types of dialog boxes, including message boxes, common dialog boxes, and custom dialog boxes.</span></span> <span data-ttu-id="0fddf-121">このトピックでは、それぞれについて説明し、該当する例として、[ダイアログ ボックスのサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox)を示します。</span><span class="sxs-lookup"><span data-stu-id="0fddf-121">This topic discusses each, and the [Dialog Box Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox) provides matching examples.</span></span>  

<a name="Message_Boxes"></a>
## <a name="message-boxes"></a><span data-ttu-id="0fddf-122">メッセージ ボックス</span><span class="sxs-lookup"><span data-stu-id="0fddf-122">Message boxes</span></span>  
 <span data-ttu-id="0fddf-123">"*メッセージ ボックス*" は、テキスト情報を表示するために使用され、ユーザーがボタンで意思決定を行うことができるダイアログ ボックスです。</span><span class="sxs-lookup"><span data-stu-id="0fddf-123">A *message box* is a dialog box that can be used to display textual information and to allow users to make decisions with buttons.</span></span> <span data-ttu-id="0fddf-124">次の図は、テキスト情報と質問を表示して、ユーザーが質問に回答するための 3 つのボタンを表示するメッセージ ボックスを示しています。</span><span class="sxs-lookup"><span data-stu-id="0fddf-124">The following figure shows a message box that displays textual information, asks a question, and provides the user with three buttons to answer the question.</span></span>  
  
 ![アプリケーションを終了する前にドキュメントへの変更を保存するかどうかを確認する [ワード プロセッサ] ダイアログ ボックス。](./media/dialog-boxes-overview/word-processor-dialog.png)  
  
 <span data-ttu-id="0fddf-126">メッセージ ボックスを作成するには、<xref:System.Windows.MessageBox> クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="0fddf-126">To create a message box, you use the <xref:System.Windows.MessageBox> class.</span></span> <span data-ttu-id="0fddf-127"><xref:System.Windows.MessageBox> では、次のようなコードを使用して、メッセージ ボックスのテキスト、タイトル、アイコン、およびボタンを構成できます。</span><span class="sxs-lookup"><span data-stu-id="0fddf-127"><xref:System.Windows.MessageBox> lets you configure the message box text, title, icon, and buttons, using code like the following.</span></span>  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxConfigureCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxconfigurecodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxConfigureCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxconfigurecodebehind)]  
  
 <span data-ttu-id="0fddf-128">メッセージ ボックスを表示するには、次のコードに示されているように、`static`<xref:System.Windows.MessageBox.Show%2A> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="0fddf-128">To show a message box, you call the `static`<xref:System.Windows.MessageBox.Show%2A> method, as demonstrated in the following code.</span></span>  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxShowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxshowcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxShowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxshowcodebehind)]  
  
 <span data-ttu-id="0fddf-129">メッセージ ボックスを表示するコードで、ユーザーの決定 (どのボタンが押されたか) を検出して処理する必要があるときには、コードは、次のコードに示されているように、メッセージ ボックスの結果を検査できます。</span><span class="sxs-lookup"><span data-stu-id="0fddf-129">When code that shows a message box needs to detect and process the user's decision (which button was pressed), the code can inspect the message box result, as shown in the following code.</span></span>  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxShowAndResultCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxshowandresultcodebehind1)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxShowAndResultCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxshowandresultcodebehind1)]  
  
 <span data-ttu-id="0fddf-130">メッセージ ボックスの使用の詳細については、<xref:System.Windows.MessageBox>、「[メッセージ ボックスのサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/MessageBox)」、および「[ダイアログ ボックスのサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0fddf-130">For more information on using message boxes, see <xref:System.Windows.MessageBox>, [MessageBox Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/MessageBox), and [Dialog Box Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox).</span></span>  
  
 <span data-ttu-id="0fddf-131"><xref:System.Windows.MessageBox> では単純なダイアログ ボックス ユーザー エクスペリエンスを提供できますが、<xref:System.Windows.MessageBox> を使用する利点は XAML ブラウザー アプリケーション (XBAP) など、部分信頼セキュリティ サンドボックス (「[セキュリティ](../security-wpf.md)」を参照) 内で実行するアプリケーションによって表示できる唯一の種類のウィンドウであることです。</span><span class="sxs-lookup"><span data-stu-id="0fddf-131">Although <xref:System.Windows.MessageBox> may offer a simple dialog box user experience, the advantage of using <xref:System.Windows.MessageBox> is that is the only type of window that can be shown by applications that run within a partial trust security sandbox (see [Security](../security-wpf.md)), such as XAML browser applications (XBAPs).</span></span>  
  
 <span data-ttu-id="0fddf-132">ほとんどのダイアログ ボックスは、テキスト、選択 (チェック ボックス)、相互に排他的な選択 (オプション ボタン)、リスト選択 (リスト ボックス、コンボ ボックス、ドロップダウン リスト ボックス) など、メッセージ ボックスの結果よりも複雑なデータを表示し、収集します。</span><span class="sxs-lookup"><span data-stu-id="0fddf-132">Most dialog boxes display and gather more complex data than the result of a message box, including text, selection (check boxes), mutually exclusive selection (radio buttons), and list selection (list boxes, combo boxes, drop-down list boxes).</span></span> <span data-ttu-id="0fddf-133">これらのために、Windows Presentation Foundation (WPF) には、いくつかのコモン ダイアログ ボックスが用意されていて、ユーザー独自のダイアログ ボックスを作成することもできますが、どちらの使用も、完全な信頼で実行しているアプリケーションに限られます。</span><span class="sxs-lookup"><span data-stu-id="0fddf-133">For these, Windows Presentation Foundation (WPF) provides several common dialog boxes and allows you to create your own dialog boxes, although the use of either is limited to applications running with full trust.</span></span>  
  
<a name="Common_Dialogs"></a>
## <a name="common-dialog-boxes"></a><span data-ttu-id="0fddf-134">コモン ダイアログ ボックス</span><span class="sxs-lookup"><span data-stu-id="0fddf-134">Common dialog boxes</span></span>  
 <span data-ttu-id="0fddf-135">Windows では、ファイルを開く、ファイルを保存する、印刷するためのダイアログ ボックスなど、すべてのアプリケーションに共通の、さまざまな再利用可能なダイアログ ボックスが実装されます。</span><span class="sxs-lookup"><span data-stu-id="0fddf-135">Windows implements a variety of reusable dialog boxes that are common to all applications, including dialog boxes for opening files, saving files, and printing.</span></span> <span data-ttu-id="0fddf-136">これらのダイアログ ボックスはオペレーティング システムによって実装されるため、そのオペレーティング システム上で実行するすべてのアプリケーション間で共有でき、ユーザー エクスペリエンスの一貫性を保つことができます。ユーザーが 1 つのアプリケーションで、オペレーティング システムによって提供されるダイアログ ボックスの使用に慣れると、他のアプリケーションでも、そのダイアログ ボックスの使用法を学ぶ必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0fddf-136">Since these dialog boxes are implemented by the operating system, they can be shared among all the applications that run on the operating system, which helps user experience consistency; when users are familiar with the use of an operating system-provided dialog box in one application, they don't need to learn how to use that dialog box in other applications.</span></span> <span data-ttu-id="0fddf-137">これらのダイアログ ボックスはすべてのアプリケーションで使用でき、一貫したユーザー エクスペリエンスの提供に役立つため、"*コモン ダイアログ ボックス*" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="0fddf-137">Because these dialog boxes are available to all applications and because they help provide a consistent user experience, they are known as *common dialog boxes*.</span></span>  
  
 <span data-ttu-id="0fddf-138">Windows Presentation Foundation (WPF) では、ファイルを開く、ファイルを保存する、および印刷コモン ダイアログ ボックスがカプセル化され、スタンドアロン アプリケーション内で使用できるマネージド クラスとして公開されます。</span><span class="sxs-lookup"><span data-stu-id="0fddf-138">Windows Presentation Foundation (WPF) encapsulates the open file, save file, and print common dialog boxes and exposes them as managed classes for you to use in standalone applications.</span></span> <span data-ttu-id="0fddf-139">このトピックでは、それぞれの概要を簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="0fddf-139">This topic provides a brief overview of each.</span></span>  
  
<a name="Open_File_Dialog"></a>
### <a name="open-file-dialog"></a><span data-ttu-id="0fddf-140">[ファイルを開く] ダイアログ</span><span class="sxs-lookup"><span data-stu-id="0fddf-140">Open File dialog</span></span>  
 <span data-ttu-id="0fddf-141">[ファイルを開く] ダイアログ ボックスは、次の図に示されているように、開くファイルの名前を取得するために、ファイルを開く機能によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="0fddf-141">The open file dialog box, shown in the following figure, is used by file opening functionality to retrieve the name of a file to open.</span></span>  
  
 ![ファイルを取得する場所を示す、開いているダイアログ ボックス。](./media/dialog-boxes-overview/open-file-dialog-box.png)  
  
 <span data-ttu-id="0fddf-143">[ファイルを開く] コモン ダイアログ ボックスは、<xref:Microsoft.Win32.OpenFileDialog> クラスとして実装され、<xref:Microsoft.Win32> 名前空間にあります。</span><span class="sxs-lookup"><span data-stu-id="0fddf-143">The common open file dialog box is implemented as the <xref:Microsoft.Win32.OpenFileDialog> class and is located in the <xref:Microsoft.Win32> namespace.</span></span> <span data-ttu-id="0fddf-144">次のコードは、[ファイルを開く] ダイアログ ボックスの作成、構成、および表示の方法と、結果を処理する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="0fddf-144">The following code shows how to create, configure, and show one, and how to process the result.</span></span>  
  
 [!code-csharp[DialogBoxesOverviewSnippets#OpenFileDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#openfiledialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#OpenFileDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#openfiledialogboxcodebehind)]  
  
 <span data-ttu-id="0fddf-145">ファイルを開くダイアログ ボックスの詳細については、「<xref:Microsoft.Win32.OpenFileDialog?displayProperty=nameWithType>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0fddf-145">For more information on the open file dialog box, see <xref:Microsoft.Win32.OpenFileDialog?displayProperty=nameWithType>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0fddf-146"><xref:Microsoft.Win32.OpenFileDialog> を使用すると、部分信頼で実行しているアプリケーションがファイル名を安全に取得できます (「[セキュリティ](../security-wpf.md)」を参照)。</span><span class="sxs-lookup"><span data-stu-id="0fddf-146"><xref:Microsoft.Win32.OpenFileDialog> can be used to safely retrieve file names by applications running with partial trust (see [Security](../security-wpf.md)).</span></span>  
  
<a name="Save_File_Dialog"></a>
### <a name="save-file-dialog-box"></a><span data-ttu-id="0fddf-147">[ファイルの保存] ダイアログ ボックス</span><span class="sxs-lookup"><span data-stu-id="0fddf-147">Save File dialog box</span></span>  
 <span data-ttu-id="0fddf-148">[ファイルの保存] ダイアログ ボックスは、次の図に示されているように、保存するファイルの名前を取得するために、ファイルを保存する機能によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="0fddf-148">The save file dialog box, shown in the following figure, is used by file saving functionality to retrieve the name of a file to save.</span></span>  
  
 ![ファイルを取得する場所を示す、[名前を付けて保存] ダイアログ ボックス。](./media/dialog-boxes-overview/save-file-dialog-box.png)  
  
 <span data-ttu-id="0fddf-150">[ファイルの保存] コモン ダイアログ ボックスは、<xref:Microsoft.Win32.SaveFileDialog> クラスとして実装され、<xref:Microsoft.Win32> 名前空間にあります。</span><span class="sxs-lookup"><span data-stu-id="0fddf-150">The common save file dialog box is implemented as the <xref:Microsoft.Win32.SaveFileDialog> class, and is located in the <xref:Microsoft.Win32> namespace.</span></span> <span data-ttu-id="0fddf-151">次のコードは、[ファイルを開く] ダイアログ ボックスの作成、構成、および表示の方法と、結果を処理する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="0fddf-151">The following code shows how to create, configure, and show one, and how to process the result.</span></span>  
  
 [!code-csharp[DialogBoxesOverviewSnippets#SaveFileDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#savefiledialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#SaveFileDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#savefiledialogboxcodebehind)]  
  
 <span data-ttu-id="0fddf-152">[ファイルの保存] ダイアログ ボックスの詳細については、「<xref:Microsoft.Win32.SaveFileDialog?displayProperty=nameWithType>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0fddf-152">For more information on the save file dialog box, see <xref:Microsoft.Win32.SaveFileDialog?displayProperty=nameWithType>.</span></span>  
  
<a name="Print_Dialog"></a>
### <a name="print-dialog-box"></a><span data-ttu-id="0fddf-153">[印刷] ダイアログ ボックス</span><span class="sxs-lookup"><span data-stu-id="0fddf-153">Print dialog box</span></span>

<span data-ttu-id="0fddf-154">次の図に示されているように、[印刷] ダイアログ ボックスは、ユーザーがデータを印刷するプリンターを選択し、構成するために、印刷機能によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="0fddf-154">The print dialog box, shown in the following figure, is used by printing functionality to choose and configure the printer that a user would like to print data to.</span></span>  
  
![[印刷] ダイアログ ボックスを表示するスクリーンショット。](./media/dialog-boxes-overview/print-data-dialog-box.png)  
  
<span data-ttu-id="0fddf-156">[印刷] コモン ダイアログ ボックスは、<xref:System.Windows.Controls.PrintDialog> クラスとして実装され、<xref:System.Windows.Controls> 名前空間にあります。</span><span class="sxs-lookup"><span data-stu-id="0fddf-156">The common print dialog box is implemented as the <xref:System.Windows.Controls.PrintDialog> class, and is located in the <xref:System.Windows.Controls> namespace.</span></span> <span data-ttu-id="0fddf-157">次のコードは、[印刷] ダイアログ ボックスの作成、構成、および表示の方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="0fddf-157">The following code shows how to create, configure, and show one.</span></span>  
  
 [!code-csharp[DialogBoxesOverviewSnippets#PrintDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#printdialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#PrintDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#printdialogboxcodebehind)]  
  
 <span data-ttu-id="0fddf-158">[印刷] ダイアログ ボックスの詳細については、「<xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0fddf-158">For more information on the print dialog box, see <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0fddf-159">WPF での印刷の詳細については、「[印刷の概要](../advanced/printing-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0fddf-159">For detailed discussion of printing in WPF, see [Printing Overview](../advanced/printing-overview.md).</span></span>  
  
<a name="Custom_Dialog_Boxes"></a>
## <a name="custom-dialog-boxes"></a><span data-ttu-id="0fddf-160">カスタム ダイアログ ボックス</span><span class="sxs-lookup"><span data-stu-id="0fddf-160">Custom dialog boxes</span></span>

<span data-ttu-id="0fddf-161">コモン ダイアログ ボックスは便利であり、可能なときにはコモン ダイアログ ボックスを使用する必要がありますが、ドメイン固有のダイアログ ボックスの要件はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="0fddf-161">While common dialog boxes are useful, and should be used when possible, they do not support the requirements of domain-specific dialog boxes.</span></span> <span data-ttu-id="0fddf-162">このような場合は、独自のダイアログ ボックスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fddf-162">In these cases, you need to create your own dialog boxes.</span></span> <span data-ttu-id="0fddf-163">これから説明するように、ダイアログ ボックスは、特殊な動作を持つウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="0fddf-163">As we'll see, a dialog box is a window with special behaviors.</span></span> <span data-ttu-id="0fddf-164"><xref:System.Windows.Window> は、これらの動作を実装するため、カスタムのモーダルおよびモードレス ダイアログ ボックスを作成するには、<xref:System.Windows.Window> を使用します。</span><span class="sxs-lookup"><span data-stu-id="0fddf-164"><xref:System.Windows.Window> implements those behaviors and, consequently, you use <xref:System.Windows.Window> to create custom modal and modeless dialog boxes.</span></span>  
  
<a name="Creating_a_Modal_Custom_Dialog_Box"></a>
### <a name="creating-a-modal-custom-dialog-box"></a><span data-ttu-id="0fddf-165">モーダルのカスタム ダイアログ ボックスの作成</span><span class="sxs-lookup"><span data-stu-id="0fddf-165">Creating a modal custom dialog box</span></span>

<span data-ttu-id="0fddf-166">このトピックでは、<xref:System.Windows.Window> を使用して一般的なモーダル ダイアログ ボックス実装を作成する方法を示し、`Margins` ダイアログ ボックスを例として使用します (「[ダイアログ ボックスのサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox)」を参照)。</span><span class="sxs-lookup"><span data-stu-id="0fddf-166">This topic shows how to use <xref:System.Windows.Window> to create a typical modal dialog box implementation, using the `Margins` dialog box as an example (see [Dialog Box Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox)).</span></span> <span data-ttu-id="0fddf-167">`Margins` ダイアログ ボックスを次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="0fddf-167">The `Margins` dialog box is shown in the following figure.</span></span>  
  
 ![左余白、上余白、右余白、および下余白を定義するフィールドを含む [余白] ダイアログ ボックス。](./media/dialog-boxes-overview/margin-size-dialog-box.png)  
  
#### <a name="configuring-a-modal-dialog-box"></a><span data-ttu-id="0fddf-169">モーダル ダイアログ ボックスの構成</span><span class="sxs-lookup"><span data-stu-id="0fddf-169">Configuring a modal dialog box</span></span>

<span data-ttu-id="0fddf-170">一般的なダイアログ ボックスのユーザー インターフェイスには、次の項目が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0fddf-170">The user interface for a typical dialog box includes the following:</span></span>  
  
- <span data-ttu-id="0fddf-171">必要なデータを収集するために必要なさまざまなコントロール。</span><span class="sxs-lookup"><span data-stu-id="0fddf-171">The various controls that are required to gather the desired data.</span></span>  
  
- <span data-ttu-id="0fddf-172">ユーザーがクリックすると、ダイアログ ボックスを閉じ、機能に戻り、処理を続行する **[OK]** ボタン。</span><span class="sxs-lookup"><span data-stu-id="0fddf-172">An **OK** button that users click to close the dialog box, return to the function, and continue processing.</span></span>  
  
- <span data-ttu-id="0fddf-173">ユーザーがクリックすると、ダイアログ ボックスを閉じ、機能が処理を続行するのを停止する **[キャンセル]** ボタン。</span><span class="sxs-lookup"><span data-stu-id="0fddf-173">A **Cancel** button that users click to close the dialog box and stop the function from further processing.</span></span>  
  
- <span data-ttu-id="0fddf-174">タイトル バーの **[閉じる]** ボタン。</span><span class="sxs-lookup"><span data-stu-id="0fddf-174">A **Close** button in the title bar.</span></span>  
  
- <span data-ttu-id="0fddf-175">アイコン。</span><span class="sxs-lookup"><span data-stu-id="0fddf-175">An icon.</span></span>  
  
- <span data-ttu-id="0fddf-176">**最小化** ボタン、**最大化** ボタン、および **元に戻す** ボタン。</span><span class="sxs-lookup"><span data-stu-id="0fddf-176">**Minimize**, **Maximize**, and **Restore** buttons.</span></span>  
  
- <span data-ttu-id="0fddf-177">ダイアログ ボックスを最小化、最大化、元に戻す、および閉じるための **[システム]** メニュー。</span><span class="sxs-lookup"><span data-stu-id="0fddf-177">A **System** menu to minimize, maximize, restore, and close the dialog box.</span></span>  
  
- <span data-ttu-id="0fddf-178">ダイアログ ボックスを開いたウィンドウの中央上の位置。</span><span class="sxs-lookup"><span data-stu-id="0fddf-178">A position above and in the center of the window that opened the dialog box.</span></span>  
  
- <span data-ttu-id="0fddf-179">可能な場合は、ダイアログ ボックスが小さすぎないようにサイズを変更し、ユーザーに便利な既定サイズを提供する機能。</span><span class="sxs-lookup"><span data-stu-id="0fddf-179">The ability to be resized where possible to prevent the dialog box from being too small, and to provide the user with a useful default size.</span></span> <span data-ttu-id="0fddf-180">これには、既定のディメンションと最小ディメンションの両方を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fddf-180">This requires that you set both the default and a minimum dimensions.</span></span>  
  
- <span data-ttu-id="0fddf-181">**[キャンセル]** ボタンを押すことと同じ効果を持つキーボード ショートカットとしての ESC キー。</span><span class="sxs-lookup"><span data-stu-id="0fddf-181">The ESC key as a keyboard shortcut that causes the **Cancel** button to be pressed.</span></span> <span data-ttu-id="0fddf-182">これを行うには、 **[キャンセル]** ボタンの <xref:System.Windows.Controls.Button.IsCancel%2A> プロパティを `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="0fddf-182">You do this by setting the <xref:System.Windows.Controls.Button.IsCancel%2A> property of the **Cancel** button to `true`.</span></span>  
  
- <span data-ttu-id="0fddf-183">**[OK]** ボタンを押すことと同じ効果を持つキーボード ショートカットとしての ENTER (または RETURN) キー。</span><span class="sxs-lookup"><span data-stu-id="0fddf-183">The ENTER (or RETURN) key as a keyboard shortcut that causes the **OK** button to be pressed.</span></span> <span data-ttu-id="0fddf-184">これを行うには、 **[OK]** ボタンの <xref:System.Windows.Controls.Button.IsDefault%2A> プロパティを `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="0fddf-184">You do this by setting the <xref:System.Windows.Controls.Button.IsDefault%2A> property of the **OK** button `true`.</span></span>  
  
<span data-ttu-id="0fddf-185">次のコードは、この構成の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="0fddf-185">The following code demonstrates this configuration.</span></span>  
  
[!code-xaml[MarginsDialogBox XAML file](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml?range=1-16,106-112)]  

[!code-csharp[MarginsDialogBox C# code-behind](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-12,67-68)]
[!code-vb[MarginsDialogBox VB code-behind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-11,61-62)]  
  
<span data-ttu-id="0fddf-186">ダイアログ ボックスのユーザー エクスペリエンスは、ダイアログ ボックスを開くウィンドウのメニュー バーにも及びます。</span><span class="sxs-lookup"><span data-stu-id="0fddf-186">The user experience for a dialog box also extends into the menu bar of the window that opens the dialog box.</span></span> <span data-ttu-id="0fddf-187">メニュー項目が、機能の続行には、ダイアログ ボックスでのユーザーの操作を必要とする機能を実行するときには、次に示されているように、その機能のメニュー項目の見出しに省略記号を付けます。</span><span class="sxs-lookup"><span data-stu-id="0fddf-187">When a menu item runs a function that requires user interaction through a dialog box before the function can continue, the menu item for the function will have an ellipsis in its header, as shown here.</span></span>  
  
[!code-xaml[Menu bar of MainWindow.Xaml file](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml#L26-L27)]  
  
<span data-ttu-id="0fddf-188">メニュー項目が、[バージョン情報] ダイアログ ボックスなど、ユーザーの操作を必要としないダイアログ ボックスを表示する機能を実行するときには、省略記号は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="0fddf-188">When a menu item runs a function that displays a dialog box which does not require user interaction, such as an About dialog box, an ellipsis is not required.</span></span>  
  
#### <a name="opening-a-modal-dialog-box"></a><span data-ttu-id="0fddf-189">モーダル ダイアログ ボックスを開く</span><span class="sxs-lookup"><span data-stu-id="0fddf-189">Opening a modal dialog box</span></span>

<span data-ttu-id="0fddf-190">ダイアログ ボックスは、通常、ワード プロセッサでドキュメントの余白を設定するなど、ドメイン固有の機能を実行するためにユーザーがメニュー項目を選択した結果として表示されます。</span><span class="sxs-lookup"><span data-stu-id="0fddf-190">A dialog box is typically shown as a result of a user selecting a menu item to perform a domain-specific function, such as setting the margins of a document in a word processor.</span></span> <span data-ttu-id="0fddf-191">ウィンドウをダイアログ ボックスとして表示するのは、通常のウィンドウを表示するのと同様ですが、ダイアログ ボックス固有の追加の構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="0fddf-191">Showing a window as a dialog box is similar to showing a normal window, although it requires additional dialog box-specific configuration.</span></span> <span data-ttu-id="0fddf-192">ダイアログ ボックスのインスタンス化、構成、および開くプロセスの全体を、次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="0fddf-192">The entire process of instantiating, configuring, and opening a dialog box is shown in the following code.</span></span>  
  
[!code-csharp[Opening a modal dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-11,78-88,193-195)]
[!code-vb[Opening a modal dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,58-67,130-132)]  

<span data-ttu-id="0fddf-193">ここでは、コードは、既定の情報 (現在の余白) をダイアログ ボックスに渡しています。</span><span class="sxs-lookup"><span data-stu-id="0fddf-193">Here, the code passes default information (the current margins) to the dialog box.</span></span> <span data-ttu-id="0fddf-194">また、<xref:System.Windows.Window.Owner%2A?displayProperty=nameWithType> プロパティに、ダイアログ ボックスを表示しているウィンドウへの参照を設定します。</span><span class="sxs-lookup"><span data-stu-id="0fddf-194">It also sets the <xref:System.Windows.Window.Owner%2A?displayProperty=nameWithType> property with a reference to the window that is showing the dialog box.</span></span> <span data-ttu-id="0fddf-195">一般には、常にダイアログ ボックスの所有者を設定して、すべてのダイアログ ボックスに共通のウィンドウ状態に関連する動作を提供する必要があります (詳細については、「[WPF ウィンドウの概要](wpf-windows-overview.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="0fddf-195">In general, you should always set the owner for a dialog box to provide window state-related behaviors that are common to all dialog boxes (see [WPF Windows Overview](wpf-windows-overview.md) for more information).</span></span>

> [!NOTE]
> <span data-ttu-id="0fddf-196">ダイアログ ボックスのユーザー インターフェイス (UI) オートメーションを所有者に提供する必要があります (「[UI オートメーションの概要](/dotnet/framework/ui-automation/ui-automation-overview)」を参照)。</span><span class="sxs-lookup"><span data-stu-id="0fddf-196">You must provide an owner to support user interface (UI) automation for dialog boxes (see [UI Automation Overview](/dotnet/framework/ui-automation/ui-automation-overview)).</span></span>

<span data-ttu-id="0fddf-197">構成されたダイアログ ボックスは、<xref:System.Windows.Window.ShowDialog%2A> メソッドを呼び出すことによって、モーダルとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="0fddf-197">After the dialog box is configured, it is shown modally by calling the <xref:System.Windows.Window.ShowDialog%2A> method.</span></span>  
  
#### <a name="validating-user-provided-data"></a><span data-ttu-id="0fddf-198">ユーザー指定データの検証</span><span class="sxs-lookup"><span data-stu-id="0fddf-198">Validating user-provided data</span></span>

<span data-ttu-id="0fddf-199">ダイアログ ボックスが開かれ、ユーザーが必要なデータを指定すると、ダイアログ ボックスは、指定されたデータが有効であることを確認する必要があります。これは、次のような理由からです。</span><span class="sxs-lookup"><span data-stu-id="0fddf-199">When a dialog box is opened and the user provides the required data, a dialog box is responsible for ensuring that the provided data is valid for the following reasons:</span></span>  
  
- <span data-ttu-id="0fddf-200">セキュリティの観点から、すべての入力を検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fddf-200">From a security perspective, all input should be validated.</span></span>  
  
- <span data-ttu-id="0fddf-201">ドメイン固有の観点から、データの検証は、誤ったデータがコードによって処理されて、例外がスローされるのを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="0fddf-201">From a domain-specific perspective, data validation prevents erroneous data from being processed by the code, which could potentially throw exceptions.</span></span>  
  
- <span data-ttu-id="0fddf-202">ユーザー エクスペリエンスの観点から、ダイアログ ボックスは、入力したデータが無効であることを示すことによって、ユーザーを支援できます。</span><span class="sxs-lookup"><span data-stu-id="0fddf-202">From a user-experience perspective, a dialog box can help users by showing them which data they have entered is invalid.</span></span>  
  
- <span data-ttu-id="0fddf-203">パフォーマンスの観点から、多層アプリケーションでのデータの検証は、特に、アプリケーションが Web サービスまたはサーバーベースのデータベースで構成される場合、クライアント層とアプリケーション層の間のラウンド トリップの回数を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="0fddf-203">From a performance perspective, data validation in a multi-tier application can reduce the number of round trips between the client and the application tiers, particularly when the application is composed of Web services or server-based databases.</span></span>  

<span data-ttu-id="0fddf-204">WPF 内でバインド コントロールを検証するには、検証規則を定義して、バインドに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fddf-204">To validate a bound control in WPF, you need to define a validation rule and associate it with the binding.</span></span> <span data-ttu-id="0fddf-205">検証規則は、<xref:System.Windows.Controls.ValidationRule> から派生するカスタム クラスです。</span><span class="sxs-lookup"><span data-stu-id="0fddf-205">A validation rule is a custom class that derives from <xref:System.Windows.Controls.ValidationRule>.</span></span> <span data-ttu-id="0fddf-206">次の例は、バインドされた値が <xref:System.Double> であり、指定された範囲内にあることを確認する検証規則 `MarginValidationRule` を示しています。</span><span class="sxs-lookup"><span data-stu-id="0fddf-206">The following example shows a validation rule, `MarginValidationRule`, which checks that a bound value is a <xref:System.Double> and is within a specified range.</span></span>  

[!code-csharp[Margin validation rules](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginValidationRule.cs)]
[!code-vb[Margin validation rules](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginValidationRule.vb)]  

<span data-ttu-id="0fddf-207">このコードでは、データを検証して適切な <xref:System.Windows.Controls.ValidationResult> を返す <xref:System.Windows.Controls.ValidationRule.Validate%2A> メソッドをオーバーライドすることによって、検証規則の検証ロジックを実装しています。</span><span class="sxs-lookup"><span data-stu-id="0fddf-207">In this code, the validation logic of a validation rule is implemented by overriding the <xref:System.Windows.Controls.ValidationRule.Validate%2A> method, which validates the data and returns an appropriate <xref:System.Windows.Controls.ValidationResult>.</span></span>  

<span data-ttu-id="0fddf-208">検証規則をバインド コントロールに関連付けるには、次のマークアップを使用します。</span><span class="sxs-lookup"><span data-stu-id="0fddf-208">To associate the validation rule with the bound control, you use the following markup.</span></span>  
  
[!code-xaml[Associating a validation rule with a control](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml?range=1-16,57-68,111-112)]

<span data-ttu-id="0fddf-209">検証規則が関連付けられた後、データがバインド コントロールに入力されると、WPF によって検証規則が自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="0fddf-209">Once the validation rule is associated, WPF will automatically apply it when data is entered into the bound control.</span></span> <span data-ttu-id="0fddf-210">コントロールに無効なデータが含まれているときには、次の図に示されているように、無効なコントロールの周囲に赤い境界線が WPF によって表示されます。</span><span class="sxs-lookup"><span data-stu-id="0fddf-210">When a control contains invalid data, WPF will display a red border around the invalid control, as shown in the following figure.</span></span>  
  
![無効な左余白の値の周囲に赤い枠線が付いた[余白] ダイアログ ボックス。](./media/dialog-boxes-overview/invalid-left-margin-dialog.png)  

<span data-ttu-id="0fddf-212">WPF では、ユーザーが有効なデータを入力するまで、ユーザーが無効なコントロールに制限されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="0fddf-212">WPF does not restrict a user to the invalid control until they have entered valid data.</span></span> <span data-ttu-id="0fddf-213">これは、ダイアログ ボックスとして適切な動作です。データが有効かどうかにかかわらず、ユーザーはダイアログ ボックス内のコントロールを自由に移動できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fddf-213">This is good behavior for a dialog box; a user should be able to freely navigate the controls in a dialog box whether or not data is valid.</span></span> <span data-ttu-id="0fddf-214">ただしこれは、ユーザーが無効なデータを入力して、 **[OK]** ボタンをクリックできることを意味します。</span><span class="sxs-lookup"><span data-stu-id="0fddf-214">However, this means a user can enter invalid data and press the **OK** button.</span></span> <span data-ttu-id="0fddf-215">このため、 **[OK]** ボタンが押されたときには、コードも <xref:System.Windows.Controls.Primitives.ButtonBase.Click> イベントを処理することによって、ダイアログ ボックス内のすべてのコントロールを検証する必要はあります。</span><span class="sxs-lookup"><span data-stu-id="0fddf-215">For this reason, your code also needs to validate all controls in a dialog box when the **OK** button is pressed by handling the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event.</span></span>  
  
[!code-csharp[Validating all controls in a dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-8,26-29,33-68)]
[!code-vb[Validating all controls in a dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-8,27-29,33-62)]  

<span data-ttu-id="0fddf-216">このコードでは、ウィンドウ上のすべての依存関係オブジェクトが列挙されます。いずれかが無効な場合 (<xref:System.Windows.Controls.Validation.GetHasError%2A> によって返される) は、無効なコントロールがフォーカスを取得し、`IsValid` メソッドでは `false` が返され、ウィンドウは無効とみなされます。</span><span class="sxs-lookup"><span data-stu-id="0fddf-216">This code enumerates all dependency objects on a window and, if any are invalid (as returned by <xref:System.Windows.Controls.Validation.GetHasError%2A>, the invalid control gets the focus, the `IsValid` method returns `false`, and the window is considered invalid.</span></span>  
  
<span data-ttu-id="0fddf-217">ダイアログ ボックスが有効な場合は、安全に閉じて、戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="0fddf-217">Once a dialog box is valid, it can safely close and return.</span></span> <span data-ttu-id="0fddf-218">復帰プロセスの一環として、呼び出し元の機能に結果を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fddf-218">As part of the return process, it needs to return a result to the calling function.</span></span>  
  
#### <a name="setting-the-modal-dialog-result"></a><span data-ttu-id="0fddf-219">モーダル ダイアログの結果を設定する</span><span class="sxs-lookup"><span data-stu-id="0fddf-219">Setting the modal dialog result</span></span>

<span data-ttu-id="0fddf-220"><xref:System.Windows.Window.ShowDialog%2A> を使用してダイアログ ボックスを開くことは、基本的にメソッドの呼び出しと似ています。<xref:System.Windows.Window.ShowDialog%2A> を使用してダイアログ ボックスを開いたコードは、<xref:System.Windows.Window.ShowDialog%2A> が戻るまで待機します。</span><span class="sxs-lookup"><span data-stu-id="0fddf-220">Opening a dialog box using <xref:System.Windows.Window.ShowDialog%2A> is fundamentally like calling a method: the code that opened the dialog box using <xref:System.Windows.Window.ShowDialog%2A> waits until <xref:System.Windows.Window.ShowDialog%2A> returns.</span></span> <span data-ttu-id="0fddf-221"><xref:System.Windows.Window.ShowDialog%2A> が戻ると、それを呼び出したコードは、ユーザーが **[OK]** ボタンを押したか、それとも **[キャンセル]** ボタンを押したかに基づいて、処理を続行するか、それとも処理を停止するかを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fddf-221">When <xref:System.Windows.Window.ShowDialog%2A> returns, the code that called it needs to decide whether to continue processing or stop processing, based on whether the user pressed the **OK** button or the **Cancel** button.</span></span> <span data-ttu-id="0fddf-222">この決定を容易にするために、ダイアログ ボックスは、ユーザーの選択を <xref:System.Windows.Window.ShowDialog%2A> メソッドから返された <xref:System.Boolean> 値として返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fddf-222">To facilitate this decision, the dialog box needs to return the user's choice as a <xref:System.Boolean> value that is returned from the <xref:System.Windows.Window.ShowDialog%2A> method.</span></span>  

<span data-ttu-id="0fddf-223">**[OK]** ボタンがクリックされたときに、<xref:System.Windows.Window.ShowDialog%2A> では `true` を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fddf-223">When the **OK** button is clicked, <xref:System.Windows.Window.ShowDialog%2A> should return `true`.</span></span> <span data-ttu-id="0fddf-224">このためには、 **[OK]** ボタンがクリックされたときに、ダイアログ ボックスの <xref:System.Windows.Window.DialogResult%2A> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="0fddf-224">This is achieved by setting the <xref:System.Windows.Window.DialogResult%2A> property of the dialog box when the **OK** button is clicked.</span></span>  

[!code-csharp[Responding to the OK button](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-8,25-27,32-33,67-68)]
[!code-vb[Responding to the OK button](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-8,27,31-33,61-62)]  

<span data-ttu-id="0fddf-225"><xref:System.Windows.Window.DialogResult%2A> プロパティを設定すると、ウィンドウも自動的に閉じられるため、<xref:System.Windows.Window.Close%2A> を明示的に呼び出す必要がなくなることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0fddf-225">Note that setting the <xref:System.Windows.Window.DialogResult%2A> property also causes the window to close automatically, which alleviates the need to explicitly call <xref:System.Windows.Window.Close%2A>.</span></span>  
  
<span data-ttu-id="0fddf-226">**[キャンセル]** ボタンがクリックされたときには、<xref:System.Windows.Window.ShowDialog%2A> は `false` を返す必要があり、<xref:System.Windows.Window.DialogResult%2A> プロパティを設定する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="0fddf-226">When the **Cancel** button is clicked, <xref:System.Windows.Window.ShowDialog%2A> should return `false`, which also requires setting the <xref:System.Windows.Window.DialogResult%2A> property.</span></span>  
  
[!code-csharp[Responding to the Cancel button](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-8,19-24,67-68)]
[!code-vb[Responding to the Cancel button](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-8,22-25,61-62)]  

<span data-ttu-id="0fddf-227">ボタンの <xref:System.Windows.Controls.Button.IsCancel%2A> プロパティが `true` に設定され、ユーザーが **[キャンセル]** ボタンか Esc キーを押すと、<xref:System.Windows.Window.DialogResult%2A> は自動的に `false` に設定されます。</span><span class="sxs-lookup"><span data-stu-id="0fddf-227">When a button's <xref:System.Windows.Controls.Button.IsCancel%2A> property is set to `true` and the user presses either the **Cancel** button or the ESC key, <xref:System.Windows.Window.DialogResult%2A> is automatically set to `false`.</span></span> <span data-ttu-id="0fddf-228">次のマークアップは、前のコードと同じ効果を持ち、<xref:System.Windows.Controls.Primitives.ButtonBase.Click> イベントを処理する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0fddf-228">The following markup has the same effect as the preceding code, without the need to handle the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event.</span></span>  
  
[!code-xaml[Markup instead of handling the Click event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#L109-L109)]  

<span data-ttu-id="0fddf-229">ユーザーがタイトル バーの **[閉じる]** ボタンを押すか、 **[システム]** メニューの **[閉じる]** メニュー項目を選ぶと、ダイアログ ボックスによって自動的に `false` が返されます。</span><span class="sxs-lookup"><span data-stu-id="0fddf-229">A dialog box automatically returns `false` when a user presses the **Close** button in the title bar or chooses the **Close** menu item from the **System** menu.</span></span>  

#### <a name="processing-data-returned-from-a-modal-dialog-box"></a><span data-ttu-id="0fddf-230">モーダル ダイアログ ボックスから返されたデータの処理</span><span class="sxs-lookup"><span data-stu-id="0fddf-230">Processing data returned from a modal dialog box</span></span>  

<span data-ttu-id="0fddf-231"><xref:System.Windows.Window.DialogResult%2A> がダイアログ ボックスによって設定されると、ダイアログ ボックスを開いた機能は、<xref:System.Windows.Window.ShowDialog%2A> が戻ったときに、<xref:System.Windows.Window.DialogResult%2A> プロパティを検査することによって、ダイアログ ボックスの結果を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="0fddf-231">When <xref:System.Windows.Window.DialogResult%2A> is set by a dialog box, the function that opened it can get the dialog box result by inspecting the <xref:System.Windows.Window.DialogResult%2A> property when <xref:System.Windows.Window.ShowDialog%2A> returns.</span></span>  
  
[!code-csharp[Processing data returned from the modal dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-10,77-79,89-96,194-195)]
[!code-vb[Processing data returned from the modal dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,58,69-73,131-132)]

<span data-ttu-id="0fddf-232">ダイアログの結果が `true` の場合、機能ではそれをキューとして使用して、ユーザーによって指定されたデータを取得し、処理します。</span><span class="sxs-lookup"><span data-stu-id="0fddf-232">If the dialog result is `true`, the function uses that as a cue to retrieve and process the data provided by the user.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0fddf-233"><xref:System.Windows.Window.ShowDialog%2A> が戻った後、ダイアログ ボックスを再び開くことはできません。</span><span class="sxs-lookup"><span data-stu-id="0fddf-233">After <xref:System.Windows.Window.ShowDialog%2A> has returned, a dialog box cannot be reopened.</span></span> <span data-ttu-id="0fddf-234">代わりに、新しいインスタンスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fddf-234">Instead, you need to create a new instance.</span></span>

<span data-ttu-id="0fddf-235">ダイアログの結果が `false` の場合、機能では処理を適切に終了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fddf-235">If the dialog result is `false`, the function should end processing appropriately.</span></span>  
  
<a name="Creating_a_Modeless_Custom_Dialog_Box"></a>
### <a name="creating-a-modeless-custom-dialog-box"></a><span data-ttu-id="0fddf-236">モードレス カスタム ダイアログ ボックスの作成</span><span class="sxs-lookup"><span data-stu-id="0fddf-236">Creating a modeless custom dialog box</span></span>

<span data-ttu-id="0fddf-237">次の図に示されている [検索] ダイアログ ボックスなどのモードレス ダイアログ ボックスは、基本的な外観はモーダル ダイアログ ボックスと同じです。</span><span class="sxs-lookup"><span data-stu-id="0fddf-237">A modeless dialog box, such as the Find Dialog Box shown in the following figure, has the same fundamental appearance as the modal dialog box.</span></span>  

![[検索] ダイアログ ボックスを表示するスクリーンショット。](./media/dialog-boxes-overview/find-modeless-dialog-box.png)  

<span data-ttu-id="0fddf-239">しかし、次のセクションで説明するように、動作は少し異なります。</span><span class="sxs-lookup"><span data-stu-id="0fddf-239">However, the behavior is slightly different, as described in the following sections.</span></span>  
  
#### <a name="opening-a-modeless-dialog-box"></a><span data-ttu-id="0fddf-240">モードレス ダイアログ ボックスを開く</span><span class="sxs-lookup"><span data-stu-id="0fddf-240">Opening a modeless dialog box</span></span>

<span data-ttu-id="0fddf-241">モードレス ダイアログ ボックスは、<xref:System.Windows.Window.Show%2A> メソッドを呼び出すことによって開かれます。</span><span class="sxs-lookup"><span data-stu-id="0fddf-241">A modeless dialog box is opened by calling the <xref:System.Windows.Window.Show%2A> method.</span></span>  

[!code-xaml[XAML to define a modeless dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml#L21-L22)]  

[!code-csharp[Opening a modeless dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-10,65-76,194-195)]
[!code-vb[Openng a modeless dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,18-23,131,132)]  

<span data-ttu-id="0fddf-242"><xref:System.Windows.Window.ShowDialog%2A> とは異なり、<xref:System.Windows.Window.Show%2A> は直ちに戻ります。</span><span class="sxs-lookup"><span data-stu-id="0fddf-242">Unlike <xref:System.Windows.Window.ShowDialog%2A>, <xref:System.Windows.Window.Show%2A> returns immediately.</span></span> <span data-ttu-id="0fddf-243">その結果、呼び出し元のウィンドウは、モードレス ダイアログ ボックスが閉じられたことを知ることができず、したがって、ダイアログ ボックスの結果を確認するタイミングを判断したり、ダイアログ ボックスからデータを取得して、さらに処理したりすることができません。</span><span class="sxs-lookup"><span data-stu-id="0fddf-243">Consequently, the calling window cannot tell when the modeless dialog box is closed and, therefore, does not know when to check for a dialog box result or get data from the dialog box for further processing.</span></span> <span data-ttu-id="0fddf-244">代わりに、ダイアログ ボックスは、別の方法を作成して、呼び出し元のウィンドウに処理用のデータを返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fddf-244">Instead, the dialog box needs to create an alternative way to return data to the calling window for processing.</span></span>  
  
#### <a name="processing-data-returned-from-a-modeless-dialog-box"></a><span data-ttu-id="0fddf-245">モードレス ダイアログ ボックスから返されたデータの処理</span><span class="sxs-lookup"><span data-stu-id="0fddf-245">Processing data returned from a modeless dialog box</span></span>  

<span data-ttu-id="0fddf-246">この例では、`FindDialogBox` によって、検索対象のテキストに応じて、特定の頻度ではなく、1 つ以上の検索結果がメイン ウィンドウに返されます。</span><span class="sxs-lookup"><span data-stu-id="0fddf-246">In this example, the `FindDialogBox` may return one or more find results to the main window, depending on the text being searched for without any specific frequency.</span></span> <span data-ttu-id="0fddf-247">モーダル ダイアログ ボックスと同様、モードレス ダイアログ ボックスは、プロパティを使用して結果を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="0fddf-247">As with a modal dialog box, a modeless dialog box can return results using properties.</span></span> <span data-ttu-id="0fddf-248">ただし、ダイアログ ボックスを所有しているウィンドウは、それらのプロパティを確認するタイミングを知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fddf-248">However, the window that owns the dialog box needs to know when to check those properties.</span></span> <span data-ttu-id="0fddf-249">これを可能にする方法の 1 つは、ダイアログ ボックスで、テキストが見つかったときに発生するイベントを実装することです。</span><span class="sxs-lookup"><span data-stu-id="0fddf-249">One way to enable this is for the dialog box to implement an event that is raised whenever text is found.</span></span> <span data-ttu-id="0fddf-250">`FindDialogBox` は、この目的で `TextFoundEvent` を実装し、最初にデリゲートを必要とします。</span><span class="sxs-lookup"><span data-stu-id="0fddf-250">`FindDialogBox` implements the `TextFoundEvent` for this purpose, which first requires a delegate.</span></span>  

[!code-csharp[The TextFoundEventHandler delegate](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/TextFoundEventHandler.cs)]
[!code-vb[The TextFoundEventHandler delegate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/TextFoundEventHandler.vb)]  

<span data-ttu-id="0fddf-251">`TextFoundEventHandler` デリゲートを使用して、`FindDialogBox` では `TextFoundEvent` が実装されます。</span><span class="sxs-lookup"><span data-stu-id="0fddf-251">Using the `TextFoundEventHandler` delegate, `FindDialogBox` implements the `TextFoundEvent`.</span></span>
  
[!code-csharp[The TextFound event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs?range=1-17,125-126)]
[!code-vb[The TextFound event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb?range=1-15,102-103)]

<span data-ttu-id="0fddf-252">その結果、`Find` では、検索結果が見つかった場合にイベントを発生させることができます。</span><span class="sxs-lookup"><span data-stu-id="0fddf-252">Consequently, `Find` can raise the event when a search result is found.</span></span>  
  
[!code-csharp[Raising the TextFound event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs?range=1-9,50-52,91-94,124-127)]
[!code-vb[Raising the TextFound event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb?range=1-9,15,60-64,102-103)]  

<span data-ttu-id="0fddf-253">そのとき、所有者ウィンドウは、このイベントを登録し、処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fddf-253">The owner window then needs to register with and handle this event.</span></span>

[!code-csharp[Registering and handling the event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-10,184-195)]
[!code-vb[Registering and handling the event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,126-132)]  

#### <a name="closing-a-modeless-dialog-box"></a><span data-ttu-id="0fddf-254">モードレス ダイアログ ボックスを閉じる</span><span class="sxs-lookup"><span data-stu-id="0fddf-254">Closing a modeless dialog box</span></span>

<span data-ttu-id="0fddf-255"><xref:System.Windows.Window.DialogResult%2A> は設定する必要がないため、モードレス ダイアログ ボックスは、次のような、システムによって提供されるメカニズムを使用して閉じることができます。</span><span class="sxs-lookup"><span data-stu-id="0fddf-255">Because <xref:System.Windows.Window.DialogResult%2A> does not need to be set, a modeless dialog can be closed using system provide mechanisms, including the following:</span></span>  
  
- <span data-ttu-id="0fddf-256">タイトル バーの **[閉じる]** ボタンをクリックする。</span><span class="sxs-lookup"><span data-stu-id="0fddf-256">Clicking the **Close** button in the title bar.</span></span>  
  
- <span data-ttu-id="0fddf-257">Alt キーを押しながら F4 キーを押す。</span><span class="sxs-lookup"><span data-stu-id="0fddf-257">Pressing ALT+F4.</span></span>  
  
- <span data-ttu-id="0fddf-258">**[システム]** メニューの **[閉じる]** を選択する。</span><span class="sxs-lookup"><span data-stu-id="0fddf-258">Choosing **Close** from the **System** menu.</span></span>  
  
<span data-ttu-id="0fddf-259">または、 **[閉じる]** ボタンがクリックされたときに、コードから <xref:System.Windows.Window.Close%2A> を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="0fddf-259">Alternatively, your code can call <xref:System.Windows.Window.Close%2A> when the **Close** button is clicked.</span></span>  

[!code-csharp[Calling the Close method](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs?range=1-9,119-126)]
[!code-vb[Calling the Close method](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb?range=1-9,99-103)]  

## <a name="see-also"></a><span data-ttu-id="0fddf-260">関連項目</span><span class="sxs-lookup"><span data-stu-id="0fddf-260">See also</span></span>

- [<span data-ttu-id="0fddf-261">ポップアップの概要</span><span class="sxs-lookup"><span data-stu-id="0fddf-261">Popup Overview</span></span>](../controls/popup-overview.md)
- [<span data-ttu-id="0fddf-262">ダイアログ ボックスのサンプル</span><span class="sxs-lookup"><span data-stu-id="0fddf-262">Dialog Box Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox)
