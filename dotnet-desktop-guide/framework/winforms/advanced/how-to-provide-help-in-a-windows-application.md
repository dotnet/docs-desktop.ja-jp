---
title: '方法: Windows アプリケーションにヘルプを提供する'
ms.date: 03/30/2017
helpviewer_keywords:
- Help [Windows Forms], Windows applications
- HTML Help [Windows Forms], Windows Forms
- Windows applications [Windows Forms], providing Help
- HelpProvider component [Windows Forms]
- forms [Windows Forms], providing Help
ms.assetid: 7c4e5cec-2bd2-4f0b-8d75-c2b88929bd61
ms.openlocfilehash: ffae465518c15b4b8c9f3945ece9c6d3db85298f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981783"
---
# <a name="how-to-provide-help-in-a-windows-application"></a><span data-ttu-id="60ecc-102">方法: Windows アプリケーションにヘルプを提供する</span><span class="sxs-lookup"><span data-stu-id="60ecc-102">How to: Provide Help in a Windows Application</span></span>

<span data-ttu-id="60ecc-103">コンポーネントを使用して、 <xref:System.Windows.Forms.HelpProvider> ヘルプファイル内のヘルプトピックを Windows フォームの特定のコントロールにアタッチすることができます。</span><span class="sxs-lookup"><span data-stu-id="60ecc-103">You can make use of the <xref:System.Windows.Forms.HelpProvider> component to attach Help topics within a Help file to specific controls on Windows Forms.</span></span> <span data-ttu-id="60ecc-104">ヘルプ ファイルの形式には、HTML または HTMLHelp 1.x 以上を指定できます。</span><span class="sxs-lookup"><span data-stu-id="60ecc-104">The Help file can be either HTML or HTMLHelp 1.x or greater format.</span></span>

## <a name="provide-help"></a><span data-ttu-id="60ecc-105">ヘルプの提供</span><span class="sxs-lookup"><span data-stu-id="60ecc-105">Provide Help</span></span>

1. <span data-ttu-id="60ecc-106">Visual Studio の **ツールボックス** から、 <xref:System.Windows.Forms.HelpProvider> コンポーネントをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="60ecc-106">In Visual Studio, from the **Toolbox**, drag a <xref:System.Windows.Forms.HelpProvider> component to your form.</span></span>

     <span data-ttu-id="60ecc-107">コンポーネントは、Windows フォーム デザイナーの下部にあるトレイに配置されます。</span><span class="sxs-lookup"><span data-stu-id="60ecc-107">The component will reside in the tray at the bottom of the Windows Forms Designer.</span></span>

2. <span data-ttu-id="60ecc-108">[ **プロパティ** ] ウィンドウで、 <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> プロパティを .chm、col、.htm のいずれかのヘルプファイルに設定します。</span><span class="sxs-lookup"><span data-stu-id="60ecc-108">In the **Properties** window, set the <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> property to the .chm, .col, or .htm Help file.</span></span>

3. <span data-ttu-id="60ecc-109">フォーム上の別のコントロールを選択し、[ **プロパティ** ] ウィンドウでプロパティを設定し <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="60ecc-109">Select another control you have on your form, and in the **Properties** window, set the <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> property.</span></span>

     <span data-ttu-id="60ecc-110">これは、 <xref:System.Windows.Forms.HelpProvider> 適切なヘルプトピックを召喚するために、コンポーネントを使用してヘルプファイルに渡される文字列です。</span><span class="sxs-lookup"><span data-stu-id="60ecc-110">This is the string passed through the <xref:System.Windows.Forms.HelpProvider> component to your Help file to summon the appropriate Help topic.</span></span>

4. <span data-ttu-id="60ecc-111">[ **プロパティ** ] ウィンドウで、 <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> プロパティを列挙体の値に設定し <xref:System.Windows.Forms.HelpNavigator> ます。</span><span class="sxs-lookup"><span data-stu-id="60ecc-111">In the **Properties** window, set the <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> property to a value of the <xref:System.Windows.Forms.HelpNavigator> enumeration.</span></span>

     <span data-ttu-id="60ecc-112">これにより、**HelpKeyword** プロパティがヘルプ システムに渡される方法が決まります。</span><span class="sxs-lookup"><span data-stu-id="60ecc-112">This determines the way in which the **HelpKeyword** property is passed to the Help system.</span></span> <span data-ttu-id="60ecc-113">設定できるオプションとその説明を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="60ecc-113">The following table shows the possible settings and their descriptions.</span></span>

    |<span data-ttu-id="60ecc-114">メンバー名</span><span class="sxs-lookup"><span data-stu-id="60ecc-114">Member Name</span></span>|<span data-ttu-id="60ecc-115">[説明]</span><span class="sxs-lookup"><span data-stu-id="60ecc-115">Description</span></span>|
    |-----------------|-----------------|
    |<span data-ttu-id="60ecc-116">AssociateIndex</span><span class="sxs-lookup"><span data-stu-id="60ecc-116">AssociateIndex</span></span>|<span data-ttu-id="60ecc-117">指定したトピックのインデックスを指定した URL で実行するように指定します。</span><span class="sxs-lookup"><span data-stu-id="60ecc-117">Specifies that the index for a specified topic is performed in the specified URL.</span></span>|
    |<span data-ttu-id="60ecc-118">Find</span><span class="sxs-lookup"><span data-stu-id="60ecc-118">Find</span></span>|<span data-ttu-id="60ecc-119">指定した URL の検索ページを表示するように指定します。</span><span class="sxs-lookup"><span data-stu-id="60ecc-119">Specifies that the search page of a specified URL is displayed.</span></span>|
    |<span data-ttu-id="60ecc-120">インデックス</span><span class="sxs-lookup"><span data-stu-id="60ecc-120">Index</span></span>|<span data-ttu-id="60ecc-121">指定した URL のインデックスを表示するように指定します。</span><span class="sxs-lookup"><span data-stu-id="60ecc-121">Specifies that the index of a specified URL is displayed.</span></span>|
    |<span data-ttu-id="60ecc-122">KeywordIndex</span><span class="sxs-lookup"><span data-stu-id="60ecc-122">KeywordIndex</span></span>|<span data-ttu-id="60ecc-123">検索するキーワードと、指定した URL で実行するアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="60ecc-123">Specifies a keyword to search for and the action to take in the specified URL.</span></span>|
    |<span data-ttu-id="60ecc-124">TableOfContents</span><span class="sxs-lookup"><span data-stu-id="60ecc-124">TableOfContents</span></span>|<span data-ttu-id="60ecc-125">HTML 1.0 ヘルプ ファイルの目次を表示するように指定します。</span><span class="sxs-lookup"><span data-stu-id="60ecc-125">Specifies that the table of contents of the HTML 1.0 Help file is displayed.</span></span>|
    |<span data-ttu-id="60ecc-126">トピック</span><span class="sxs-lookup"><span data-stu-id="60ecc-126">Topic</span></span>|<span data-ttu-id="60ecc-127">指定した URL によって参照されるトピックを表示するように指定します。</span><span class="sxs-lookup"><span data-stu-id="60ecc-127">Specifies that the topic referenced by the specified URL is displayed.</span></span>|

 <span data-ttu-id="60ecc-128">実行時に、 **HelpKeyword** プロパティと **HelpNavigator** プロパティを設定したコントロールにフォーカスがあるときに F1 キーを押すと、そのコンポーネントに関連付けられているヘルプファイルが開きます <xref:System.Windows.Forms.HelpProvider> 。</span><span class="sxs-lookup"><span data-stu-id="60ecc-128">At run time, pressing F1 when the control—for which you have set the **HelpKeyword** and **HelpNavigator** properties—has focus will open the Help file you associated with that <xref:System.Windows.Forms.HelpProvider> component.</span></span>

 <span data-ttu-id="60ecc-129">現在、**HelpNamespace** プロパティは HTMLHelp 1.x、HTMLHelp 2.0、および HTML の 3 つの形式のヘルプ ファイルをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="60ecc-129">Currently, the **HelpNamespace** property supports Help files in the following three formats: HTMLHelp 1.x, HTMLHelp 2.0, and HTML.</span></span> <span data-ttu-id="60ecc-130">したがって、 **Helpnamespace** プロパティを Web ページなどのアドレスに設定でき `http://` ます。</span><span class="sxs-lookup"><span data-stu-id="60ecc-130">Thus, you can set the **HelpNamespace** property to an `http://` address, such as a Web page.</span></span> <span data-ttu-id="60ecc-131">プロパティに http:// アドレスを設定すると、既定のブラウザーが開き、**HelpKeyword** プロパティに指定した文字列をアンカーとして使用して Web ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="60ecc-131">If this is done, it will open the default browser to the Web page with the string specified in the **HelpKeyword** property used as the anchor.</span></span> <span data-ttu-id="60ecc-132">アンカーは HTML ページの特定の部分にジャンプするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="60ecc-132">The anchor is used to jump to a specific part of an HTML page.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="60ecc-133">クライアントから送信された情報は、アプリケーションで使用する前に必ずチェックしてください。</span><span class="sxs-lookup"><span data-stu-id="60ecc-133">Be careful to check any information that is sent from a client before using it in your application.</span></span> <span data-ttu-id="60ecc-134">悪意のあるユーザーが、実行可能スクリプトや SQL ステートメントなどのコードの送信 (挿入) を試みる場合があります。</span><span class="sxs-lookup"><span data-stu-id="60ecc-134">Malicious users might try to send or inject executable script, SQL statements, or other code.</span></span> <span data-ttu-id="60ecc-135">ユーザーからの入力を表示したり、データベースに格納したり、操作したりする前に、安全でない可能性のある情報が含まれていないかどうかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="60ecc-135">Before you display a user's input, store it in a database, or work with it, check that it does not contain potentially unsafe information.</span></span> <span data-ttu-id="60ecc-136">一般的な確認方法としては、ユーザーから入力を受け取ったときに、正規表現を使用して、"SCRIPT" などのキーワードを検索します。</span><span class="sxs-lookup"><span data-stu-id="60ecc-136">A typical way to check is to use a regular expression to look for keywords such as "SCRIPT" when you receive input from a user.</span></span>

<span data-ttu-id="60ecc-137"><xref:System.Windows.Forms.HelpProvider>Windows フォームのコントロールのヘルプファイルを表示するように構成している場合でも、コンポーネントを使用してポップアップヘルプを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="60ecc-137">You can also use the <xref:System.Windows.Forms.HelpProvider> component to show pop-up Help, even if you have it configured to display Help files for the controls on your Windows Forms.</span></span> <span data-ttu-id="60ecc-138">詳細については、「[方法: ポップアップ ヘルプを表示する](how-to-display-pop-up-help.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60ecc-138">For more information, see [How to: Display Pop-up Help](how-to-display-pop-up-help.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="60ecc-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="60ecc-139">See also</span></span>

- [<span data-ttu-id="60ecc-140">方法: ポップアップ ヘルプを表示する</span><span class="sxs-lookup"><span data-stu-id="60ecc-140">How to: Display Pop-up Help</span></span>](how-to-display-pop-up-help.md)
- [<span data-ttu-id="60ecc-141">ツールヒントを使用したコントロールのヘルプ</span><span class="sxs-lookup"><span data-stu-id="60ecc-141">Control Help Using ToolTips</span></span>](control-help-using-tooltips.md)
- [<span data-ttu-id="60ecc-142">Windows フォームでのヘルプの統合</span><span class="sxs-lookup"><span data-stu-id="60ecc-142">Integrating User Help in Windows Forms</span></span>](integrating-user-help-in-windows-forms.md)
- [<span data-ttu-id="60ecc-143">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="60ecc-143">Windows Forms</span></span>](../index.yml)
