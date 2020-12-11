---
title: RichTextBox コントロール
ms.date: 03/30/2017
helpviewer_keywords:
- text boxes
- RichTextBox control [Windows Forms]
- rich edit controls
ms.assetid: 3225f2ef-c6d9-4bd4-9d3e-2219e58edbf2
ms.openlocfilehash: 9d26ec7bfc4d75b304bbc9dc98dbbeaed64effe7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981472"
---
# <a name="richtextbox-control-windows-forms"></a><span data-ttu-id="6e839-102">RichTextBox コントロール (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="6e839-102">RichTextBox Control (Windows Forms)</span></span>
<span data-ttu-id="6e839-103">Windows フォーム `RichTextBox` コントロールは、書式設定を使用してテキストを表示、入力、および操作するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="6e839-103">The Windows Forms `RichTextBox` control is used for displaying, entering, and manipulating text with formatting.</span></span> <span data-ttu-id="6e839-104">コントロールは、 `RichTextBox` コントロールが行うすべての処理を実行しますが、 <xref:System.Windows.Forms.TextBox> フォント、色、およびリンクを表示したり、ファイルからテキストや埋め込み画像を読み込んだり、編集操作を元に戻したりやり直したり、指定された文字を検索したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="6e839-104">The `RichTextBox` control does everything the <xref:System.Windows.Forms.TextBox> control does, but it can also display fonts, colors, and links; load text and embedded images from a file; undo and redo editing operations; and find specified characters.</span></span> <span data-ttu-id="6e839-105">コントロールは、 `RichTextBox` 通常、Microsoft word などのワードプロセッシングアプリケーションに似たテキスト操作と表示機能を提供するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="6e839-105">The `RichTextBox` control is typically used to provide text manipulation and display features similar to word processing applications such as Microsoft Word.</span></span> <span data-ttu-id="6e839-106">コントロールと同様に、コントロールには <xref:System.Windows.Forms.TextBox> `RichTextBox` スクロールバーを表示できますが、コントロールとは異なり、水平スクロールバーと <xref:System.Windows.Forms.TextBox> 垂直スクロールバーの両方が既定で表示され、追加のスクロールバーの設定があります。</span><span class="sxs-lookup"><span data-stu-id="6e839-106">Like the <xref:System.Windows.Forms.TextBox> control, the `RichTextBox` control can display scroll bars; but unlike the <xref:System.Windows.Forms.TextBox> control, it displays both horizontal and vertical scrollbars by default and has additional scrollbar settings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6e839-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6e839-107">In This Section</span></span>  
 [<span data-ttu-id="6e839-108">RichTextBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="6e839-108">RichTextBox Control Overview</span></span>](richtextbox-control-overview-windows-forms.md)  
 <span data-ttu-id="6e839-109">`RichTextBox`ユーザーが書式設定オプションを使用してテキストを入力、表示、および操作できるようにする、コントロールの一般的な概念について説明します。</span><span class="sxs-lookup"><span data-stu-id="6e839-109">Introduces the general concepts of the `RichTextBox` control, which allows users to enter, display, and manipulate text with formatting options.</span></span>  
  
 [<span data-ttu-id="6e839-110">方法: Windows フォームの RichTextBox コントロールにおける書式属性の変更を確認する</span><span class="sxs-lookup"><span data-stu-id="6e839-110">How to: Determine When Formatting Attributes Change in the Windows Forms RichTextBox Control</span></span>](determine-when-formatting-attributes-change-wf-richtextbox-control.md)  
 <span data-ttu-id="6e839-111">コントロールのフォントおよび段落書式設定の変更を追跡する方法について説明し `RichTextBox` ます。</span><span class="sxs-lookup"><span data-stu-id="6e839-111">Explains how to keep track of changes in font and paragraph formatting in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="6e839-112">方法: Windows フォームの RichTextBox コントロールにスクロール バーを表示する</span><span class="sxs-lookup"><span data-stu-id="6e839-112">How to: Display Scroll Bars in the Windows Forms RichTextBox Control</span></span>](how-to-display-scroll-bars-in-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="6e839-113">コントロールのスクロールバーで使用できる多くの選択肢について説明し `RichTextBox` ます。</span><span class="sxs-lookup"><span data-stu-id="6e839-113">Describes the many choices available for scroll bars in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="6e839-114">方法: Windows フォームの RichTextBox コントロールを使用して Web スタイルのリンクを表示する</span><span class="sxs-lookup"><span data-stu-id="6e839-114">How to: Display Web-Style Links with the Windows Forms RichTextBox Control</span></span>](how-to-display-web-style-links-with-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="6e839-115">コントロールから Web サイトにリンクする方法について説明 `RichTextBox` します。</span><span class="sxs-lookup"><span data-stu-id="6e839-115">Explains how to link to Web sites from the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="6e839-116">方法: Windows フォームの RichTextBox コントロールにおけるドラッグ アンド ドロップ操作を有効にする</span><span class="sxs-lookup"><span data-stu-id="6e839-116">How to: Enable Drag-and-Drop Operations with the Windows Forms RichTextBox Control</span></span>](enable-drag-and-drop-operations-with-wf-richtextbox-control.md)  
 <span data-ttu-id="6e839-117">コントロールにデータをドラッグする手順について説明 `RichTextBox` します。</span><span class="sxs-lookup"><span data-stu-id="6e839-117">Provides instructions for dragging data into the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="6e839-118">方法: Windows フォームの RichTextBox コントロールにファイルを読み込む</span><span class="sxs-lookup"><span data-stu-id="6e839-118">How to: Load Files into the Windows Forms RichTextBox Control</span></span>](how-to-load-files-into-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="6e839-119">既存のファイルをコントロールに読み込む手順について説明 `RichTextBox` します。</span><span class="sxs-lookup"><span data-stu-id="6e839-119">Provides instructions for loading an existing file into the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="6e839-120">方法: Windows フォームの RichTextBox コントロールを使用してファイルを保存する</span><span class="sxs-lookup"><span data-stu-id="6e839-120">How to: Save Files with the Windows Forms RichTextBox Control</span></span>](how-to-save-files-with-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="6e839-121">コントロールの内容をファイルに保存する方法について説明し `RichTextBox` ます。</span><span class="sxs-lookup"><span data-stu-id="6e839-121">Provides instructions for saving the contents of the `RichTextBox` control to a file.</span></span>  
  
 [<span data-ttu-id="6e839-122">方法: Windows フォームの RichTextBox コントロールのフォント属性を設定する</span><span class="sxs-lookup"><span data-stu-id="6e839-122">How to: Set Font Attributes for the Windows Forms RichTextBox Control</span></span>](how-to-set-font-attributes-for-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="6e839-123">コントロール内のテキストのフォントファミリ、サイズ、スタイル、および色を設定する方法について説明し `RichTextBox` ます。</span><span class="sxs-lookup"><span data-stu-id="6e839-123">Describes how to set the font family, size, style, and color of text in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="6e839-124">方法: Windows フォームの RichTextBox コントロールを使用してインデント、ぶら下げインデント、箇条書き段落を設定する</span><span class="sxs-lookup"><span data-stu-id="6e839-124">How to: Set Indents, Hanging Indents, and Bulleted Paragraphs with the Windows Forms RichTextBox Control</span></span>](set-indents-hanging-indents-bulleted-paragraphs-with-wf-richtextbox.md)  
 <span data-ttu-id="6e839-125">コントロールの段落の書式を設定する方法について説明し `RichTextBox` ます。</span><span class="sxs-lookup"><span data-stu-id="6e839-125">Describes how to format paragraphs in the `RichTextBox` control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="6e839-126">リファレンス</span><span class="sxs-lookup"><span data-stu-id="6e839-126">Reference</span></span>  
 <span data-ttu-id="6e839-127"><xref:System.Windows.Forms.RichTextBox> クラス</span><span class="sxs-lookup"><span data-stu-id="6e839-127"><xref:System.Windows.Forms.RichTextBox> class</span></span>  
 <span data-ttu-id="6e839-128">このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="6e839-128">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6e839-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e839-129">Related Sections</span></span>  
 [<span data-ttu-id="6e839-130">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="6e839-130">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="6e839-131">Windows フォーム コントロールの完全な一覧を、使用に関する情報リンクと共に提供します。</span><span class="sxs-lookup"><span data-stu-id="6e839-131">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>  
  
 [<span data-ttu-id="6e839-132">TextBox コントロール</span><span class="sxs-lookup"><span data-stu-id="6e839-132">TextBox Control</span></span>](textbox-control-windows-forms.md)  
 <span data-ttu-id="6e839-133"><xref:System.Windows.Forms.TextBox>ユーザーからの編集可能な複数行入力を許可する、コントロールの一般的な概念について説明します。</span><span class="sxs-lookup"><span data-stu-id="6e839-133">Introduces the general concepts of the <xref:System.Windows.Forms.TextBox> control, which allows editable, multiline input from the user.</span></span>
