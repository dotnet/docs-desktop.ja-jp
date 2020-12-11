---
title: TextBox コントロールで複数の行を表示する
description: 複数行を表示する方法については、Windows フォームテキストボックスコントロールで複数行、ワードラップ、およびスクロールバーの各プロパティを設定する方法について説明します。
ms.date: 03/30/2017
helpviewer_keywords:
- newline
- end of line
- ScrollBars property [Windows Forms], in TextBox control
- CRLF
- MultiLine property in TextBox control
- line-feed
- TextBox control [Windows Forms], viewing multiple lines
- carriage return
ms.assetid: 43173201-0b74-4067-a472-605029ca5f35
ms.openlocfilehash: e40d720bcd56366f4f06bfe2e2d347aaf9aa9d6c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980676"
---
# <a name="how-to-view-multiple-lines-in-the-windows-forms-textbox-control"></a><span data-ttu-id="4b994-103">方法: Windows フォーム TextBox コントロールで複数行を表示する</span><span class="sxs-lookup"><span data-stu-id="4b994-103">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>
<span data-ttu-id="4b994-104">既定では、Windows フォーム <xref:System.Windows.Forms.TextBox> コントロールには1行のテキストが表示され、スクロールバーは表示されません。</span><span class="sxs-lookup"><span data-stu-id="4b994-104">By default, the Windows Forms <xref:System.Windows.Forms.TextBox> control displays a single line of text and does not display scroll bars.</span></span> <span data-ttu-id="4b994-105">テキストが使用可能な領域を超えている場合は、テキストの一部だけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b994-105">If the text is longer than the available space, only part of the text is visible.</span></span> <span data-ttu-id="4b994-106">この既定の動作を変更するには <xref:System.Windows.Forms.TextBox.Multiline%2A> 、、 <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> 、およびの <xref:System.Windows.Forms.TextBox.ScrollBars%2A> 各プロパティを適切な値に設定します。</span><span class="sxs-lookup"><span data-stu-id="4b994-106">You can change this default behavior by setting the <xref:System.Windows.Forms.TextBox.Multiline%2A>, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>, and <xref:System.Windows.Forms.TextBox.ScrollBars%2A> properties to appropriate values.</span></span>  
  
### <a name="to-display-a-carriage-return-in-the-textbox-control"></a><span data-ttu-id="4b994-107">TextBox コントロールに復帰を表示するには</span><span class="sxs-lookup"><span data-stu-id="4b994-107">To display a carriage return in the TextBox control</span></span>  
  
- <span data-ttu-id="4b994-108">複数行で復帰を表示するには、 <xref:System.Windows.Forms.TextBox> プロパティを使用し <xref:System.Environment.NewLine%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="4b994-108">To display a carriage return in a multi-line <xref:System.Windows.Forms.TextBox>, use the <xref:System.Environment.NewLine%2A> property.</span></span>  
  
     <span data-ttu-id="4b994-109">エスケープ文字 () の解釈は言語固有であることに注意して \\ ください。</span><span class="sxs-lookup"><span data-stu-id="4b994-109">Be aware that the interpretation of escape characters (\\) is language-specific.</span></span> <span data-ttu-id="4b994-110">Visual Basic は `Chr$(13) & Chr$(10)` 、キャリッジリターンとラインフィード文字の組み合わせにを使用します。</span><span class="sxs-lookup"><span data-stu-id="4b994-110">Visual Basic uses `Chr$(13) & Chr$(10)` for the carriage return and linefeed character combination.</span></span>  
  
### <a name="to-view-multiple-lines-in-the-textbox-control"></a><span data-ttu-id="4b994-111">TextBox コントロールで複数の行を表示するには</span><span class="sxs-lookup"><span data-stu-id="4b994-111">To view multiple lines in the TextBox control</span></span>  
  
1. <span data-ttu-id="4b994-112"><xref:System.Windows.Forms.TextBox.Multiline%2A> プロパティを `true`に設定します。</span><span class="sxs-lookup"><span data-stu-id="4b994-112">Set the <xref:System.Windows.Forms.TextBox.Multiline%2A> property to `true`.</span></span> <span data-ttu-id="4b994-113"><xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>が `true` (既定値) の場合、コントロールのテキストは1つ以上の段落として表示されます。それ以外の場合は、コントロールの端で一部の行がクリップされる可能性があるリストとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b994-113">If <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> is `true` (the default), then the text in the control will appear as one or more paragraphs; otherwise it will appear as a list, in which some lines may be clipped at the edge of the control.</span></span>  
  
2. <span data-ttu-id="4b994-114"><xref:System.Windows.Forms.TextBox.ScrollBars%2A> プロパティに適切な値を設定します。</span><span class="sxs-lookup"><span data-stu-id="4b994-114">Set the <xref:System.Windows.Forms.TextBox.ScrollBars%2A> property to an appropriate value.</span></span>  
  
    |<span data-ttu-id="4b994-115">値</span><span class="sxs-lookup"><span data-stu-id="4b994-115">Value</span></span>|<span data-ttu-id="4b994-116">説明</span><span class="sxs-lookup"><span data-stu-id="4b994-116">Description</span></span>|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.ScrollBars.None>|<span data-ttu-id="4b994-117">この値は、ほとんど常にコントロールに収まらない段落の場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="4b994-117">Use this value if the text will be a paragraph that almost always fits the control.</span></span> <span data-ttu-id="4b994-118">テキストが長すぎて一度に表示できない場合、ユーザーはマウスポインターを使用してコントロール内を移動できます。</span><span class="sxs-lookup"><span data-stu-id="4b994-118">The user can use the mouse pointer to move around inside the control if the text is too long to display all at once.</span></span>|  
    |<xref:System.Windows.Forms.ScrollBars.Horizontal>|<span data-ttu-id="4b994-119">この値は、行の一覧を表示する場合に使用します。その中には、コントロールの幅よりも長い場合があり <xref:System.Windows.Forms.TextBox> ます。</span><span class="sxs-lookup"><span data-stu-id="4b994-119">Use this value if you want to display a list of lines, some of which may be longer than the width of the <xref:System.Windows.Forms.TextBox> control.</span></span>|  
    |<xref:System.Windows.Forms.ScrollBars.Both>|<span data-ttu-id="4b994-120">リストがコントロールの高さよりも長い場合は、この値を使用します。</span><span class="sxs-lookup"><span data-stu-id="4b994-120">Use this value if the list may be longer than the height of the control.</span></span>|  
  
3. <span data-ttu-id="4b994-121"><xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> プロパティに適切な値を設定します。</span><span class="sxs-lookup"><span data-stu-id="4b994-121">Set the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property to an appropriate value.</span></span>  
  
    |<span data-ttu-id="4b994-122">値</span><span class="sxs-lookup"><span data-stu-id="4b994-122">Value</span></span>|<span data-ttu-id="4b994-123">説明</span><span class="sxs-lookup"><span data-stu-id="4b994-123">Description</span></span>|  
    |-----------|-----------------|  
    |`false`|<span data-ttu-id="4b994-124">コントロール内のテキストは自動的に折り返されないため、改行に達するまで右にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="4b994-124">Text in the control will not automatically be wrapped, so it will scroll to the right until a line break is reached.</span></span> <span data-ttu-id="4b994-125"><xref:System.Windows.Forms.ScrollBars.Horizontal>上のスクロールバーまたはを選択した場合は、この値を使用し <xref:System.Windows.Forms.ScrollBars.Both> ます。</span><span class="sxs-lookup"><span data-stu-id="4b994-125">Use this value if you chose <xref:System.Windows.Forms.ScrollBars.Horizontal> scroll bars or <xref:System.Windows.Forms.ScrollBars.Both>, above.</span></span>|  
    |<span data-ttu-id="4b994-126">`true` (既定)</span><span class="sxs-lookup"><span data-stu-id="4b994-126">`true` (default)</span></span>|<span data-ttu-id="4b994-127">水平スクロールバーは表示されません。</span><span class="sxs-lookup"><span data-stu-id="4b994-127">The horizontal scrollbar will not appear.</span></span> <span data-ttu-id="4b994-128"><xref:System.Windows.Forms.ScrollBars.Vertical>1 つ以上の段落を表示する場合は、この値を使用し <xref:System.Windows.Forms.ScrollBars.None> ます。</span><span class="sxs-lookup"><span data-stu-id="4b994-128">Use this value if you chose <xref:System.Windows.Forms.ScrollBars.Vertical> scroll bars or <xref:System.Windows.Forms.ScrollBars.None>, above, to display one or more paragraphs.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4b994-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="4b994-129">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="4b994-130">TextBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="4b994-130">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="4b994-131">方法: Windows フォーム TextBox コントロールでのカーソル位置を制御する</span><span class="sxs-lookup"><span data-stu-id="4b994-131">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="4b994-132">方法: Windows フォームの TextBox コントロールを使用してパスワード テキスト ボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="4b994-132">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="4b994-133">方法: 読み取り専用テキスト ボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="4b994-133">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="4b994-134">方法: 文字列に引用符を挿入する</span><span class="sxs-lookup"><span data-stu-id="4b994-134">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="4b994-135">方法: Windows フォーム TextBox コントロールでテキストを選択する</span><span class="sxs-lookup"><span data-stu-id="4b994-135">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="4b994-136">TextBox コントロール</span><span class="sxs-lookup"><span data-stu-id="4b994-136">TextBox Control</span></span>](textbox-control-windows-forms.md)
