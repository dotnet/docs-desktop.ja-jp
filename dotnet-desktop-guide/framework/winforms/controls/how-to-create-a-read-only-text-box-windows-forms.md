---
title: '方法: 読み取り専用テキスト ボックスを作成する'
description: 編集可能な Windows フォームテキストボックスを読み取り専用の Windows フォームテキストボックスに変換する方法について説明します。
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
ms.openlocfilehash: 5baa7c66d5f16560a4ea23861d563b099592957f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982564"
---
# <a name="how-to-create-a-read-only-text-box-windows-forms"></a><span data-ttu-id="b0907-103">方法 : 読み取り専用テキスト ボックスを作成する (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="b0907-103">How to: Create a Read-Only Text Box (Windows Forms)</span></span>

<span data-ttu-id="b0907-104">編集可能な Windows フォームテキストボックスを読み取り専用のコントロールに変換できます。</span><span class="sxs-lookup"><span data-stu-id="b0907-104">You can transform an editable Windows Forms text box into a read-only control.</span></span> <span data-ttu-id="b0907-105">たとえば、テキストボックスには通常は編集されているが、現在はアプリケーションの状態によっては編集されていない値が表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="b0907-105">For example, the text box may display a value that is usually edited but may not be currently, due to the state of the application.</span></span>

## <a name="to-create-a-read-only-text-box"></a><span data-ttu-id="b0907-106">読み取り専用のテキストボックスを作成するには</span><span class="sxs-lookup"><span data-stu-id="b0907-106">To create a read-only text box</span></span>

1. <span data-ttu-id="b0907-107"><xref:System.Windows.Forms.TextBox>コントロールの <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> プロパティをに設定し `true` ます。</span><span class="sxs-lookup"><span data-stu-id="b0907-107">Set the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> property to `true`.</span></span> <span data-ttu-id="b0907-108">プロパティがに設定されている `true` 場合でも、ユーザーはテキストボックス内のテキストをスクロールして強調表示することができ、変更は許可されません。</span><span class="sxs-lookup"><span data-stu-id="b0907-108">With the property set to `true`, users can still scroll and highlight text in a text box without allowing changes.</span></span> <span data-ttu-id="b0907-109">**Copy** コマンドはテキストボックスで機能しますが、**切り取り** と **貼り付け** のコマンドは機能しません。</span><span class="sxs-lookup"><span data-stu-id="b0907-109">A **Copy** command is functional in a text box, but **Cut** and **Paste** commands are not.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b0907-110">プロパティは、実行時の <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> ユーザーの操作にのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="b0907-110">The <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> property only affects user interaction at run time.</span></span> <span data-ttu-id="b0907-111">テキストボックスの内容は、テキストボックスのプロパティを変更することで、実行時にプログラムによって変更することもでき <xref:System.Windows.Forms.TextBox.Text%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="b0907-111">You can still change text box contents programmatically at run time by changing the <xref:System.Windows.Forms.TextBox.Text%2A> property of the text box.</span></span>

## <a name="see-also"></a><span data-ttu-id="b0907-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="b0907-112">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="b0907-113">TextBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="b0907-113">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="b0907-114">方法: Windows フォーム TextBox コントロールでのカーソル位置を制御する</span><span class="sxs-lookup"><span data-stu-id="b0907-114">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="b0907-115">方法: Windows フォームの TextBox コントロールを使用してパスワード テキスト ボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="b0907-115">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="b0907-116">方法: 文字列に引用符を挿入する</span><span class="sxs-lookup"><span data-stu-id="b0907-116">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="b0907-117">方法: Windows フォーム TextBox コントロールでテキストを選択する</span><span class="sxs-lookup"><span data-stu-id="b0907-117">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="b0907-118">方法: Windows フォーム TextBox コントロールで複数行を表示する</span><span class="sxs-lookup"><span data-stu-id="b0907-118">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="b0907-119">TextBox コントロール</span><span class="sxs-lookup"><span data-stu-id="b0907-119">TextBox Control</span></span>](textbox-control-windows-forms.md)
