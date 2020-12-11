---
title: TextBox コントロール
description: 編集可能なテキストに使用し、読み取り専用にするなど、Windows フォーム TextBox コントロールのさまざまな側面について説明します。
ms.date: 03/30/2017
helpviewer_keywords:
- text boxes
- TextBox control [Windows Forms]
ms.assetid: e5a06987-8aec-4271-b196-2245ba992d62
ms.openlocfilehash: 026f6d2653e41dabd3db7490660b6ce19846d397
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982404"
---
# <a name="textbox-control-windows-forms"></a><span data-ttu-id="ab470-103">TextBox コントロール (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="ab470-103">TextBox Control (Windows Forms)</span></span>
<span data-ttu-id="ab470-104">Windows フォームテキストボックスを使用して、ユーザーからの入力を取得したり、テキストを表示したりします。</span><span class="sxs-lookup"><span data-stu-id="ab470-104">Windows Forms text boxes are used to get input from the user or to display text.</span></span> <span data-ttu-id="ab470-105">コントロールは、 `TextBox` 通常、編集可能なテキストに使用されますが、読み取り専用にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="ab470-105">The `TextBox` control is generally used for editable text, although it can also be made read-only.</span></span> <span data-ttu-id="ab470-106">テキストボックスでは、複数の行を表示したり、テキストをコントロールのサイズに折り返したり、基本的な書式を追加したりできます。</span><span class="sxs-lookup"><span data-stu-id="ab470-106">Text boxes can display multiple lines, wrap text to the size of the control, and add basic formatting.</span></span> <span data-ttu-id="ab470-107">コントロール `TextBox` では、コントロールに表示または入力されるテキストに対して1つの形式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ab470-107">The `TextBox` control allows a single format for text displayed or entered in the control.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ab470-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ab470-108">In This Section</span></span>  
 [<span data-ttu-id="ab470-109">TextBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="ab470-109">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)  
 <span data-ttu-id="ab470-110">このコントロールについて、および主な機能とプロパティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ab470-110">Explains what this control is and its key features and properties.</span></span>  
  
 [<span data-ttu-id="ab470-111">方法: Windows フォーム TextBox コントロールでのカーソル位置を制御する</span><span class="sxs-lookup"><span data-stu-id="ab470-111">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 <span data-ttu-id="ab470-112">エディットコントロールがフォーカスを取得するときに挿入ポイントが表示される位置を指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ab470-112">Gives directions for specifying where the insertion point appears when an edit control first gets the focus.</span></span>  
  
 [<span data-ttu-id="ab470-113">方法: Windows フォームの TextBox コントロールを使用してパスワード テキスト ボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="ab470-113">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 <span data-ttu-id="ab470-114">テキストボックスに入力された内容を非表示にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ab470-114">Explains how to conceal what is typed into a text box.</span></span>  
  
 [<span data-ttu-id="ab470-115">方法: 読み取り専用テキスト ボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="ab470-115">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)  
 <span data-ttu-id="ab470-116">テキストボックスの内容が変更されないようにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ab470-116">Describes how to prevent the contents of a text box from being changed.</span></span>  
  
 [<span data-ttu-id="ab470-117">方法: 文字列に引用符を挿入する</span><span class="sxs-lookup"><span data-stu-id="ab470-117">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 <span data-ttu-id="ab470-118">テキストボックス内の文字列に引用符を追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ab470-118">Explains adding quotation marks to a string in a text box.</span></span>  
  
 [<span data-ttu-id="ab470-119">方法: Windows フォーム TextBox コントロールでテキストを選択する</span><span class="sxs-lookup"><span data-stu-id="ab470-119">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)  
 <span data-ttu-id="ab470-120">テキストボックス内のテキストを強調表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ab470-120">Explains how to highlight text in a text box.</span></span>  
  
 [<span data-ttu-id="ab470-121">方法: Windows フォーム TextBox コントロールで複数行を表示する</span><span class="sxs-lookup"><span data-stu-id="ab470-121">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 <span data-ttu-id="ab470-122">テキストボックスをスクロール可能にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ab470-122">Describes how to make a text box scrollable.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ab470-123">リファレンス</span><span class="sxs-lookup"><span data-stu-id="ab470-123">Reference</span></span>  
 <span data-ttu-id="ab470-124"><xref:System.Windows.Forms.TextBox> クラス</span><span class="sxs-lookup"><span data-stu-id="ab470-124"><xref:System.Windows.Forms.TextBox> class</span></span>  
 <span data-ttu-id="ab470-125">このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="ab470-125">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ab470-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="ab470-126">Related Sections</span></span>  
 [<span data-ttu-id="ab470-127">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="ab470-127">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="ab470-128">Windows フォーム コントロールの完全な一覧を、使用に関する情報リンクと共に提供します。</span><span class="sxs-lookup"><span data-stu-id="ab470-128">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
