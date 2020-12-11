---
title: TextBox コントロールの挿入ポイントを制御する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], insertion point
- insertion points [Windows Forms], TextBox controls
- text boxes [Windows Forms], controlling insertion point
ms.assetid: 5bee7d34-5121-429e-ab1f-d8ff67bc74c1
ms.openlocfilehash: fd4803820921f0c922a4ce885f809abee8fd4c6c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982211"
---
# <a name="how-to-control-the-insertion-point-in-a-windows-forms-textbox-control"></a><span data-ttu-id="2742d-102">方法: Windows フォーム TextBox コントロールでのカーソル位置を制御する</span><span class="sxs-lookup"><span data-stu-id="2742d-102">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>
<span data-ttu-id="2742d-103">Windows フォームコントロールが <xref:System.Windows.Forms.TextBox> まずフォーカスを受け取ると、テキストボックス内の既定の挿入は既存のテキストの左側に挿入されます。</span><span class="sxs-lookup"><span data-stu-id="2742d-103">When a Windows Forms <xref:System.Windows.Forms.TextBox> control first receives the focus, the default insertion within the text box is to the left of any existing text.</span></span> <span data-ttu-id="2742d-104">ユーザーは、キーボードまたはマウスを使用して、挿入ポイントを移動できます。</span><span class="sxs-lookup"><span data-stu-id="2742d-104">The user can move the insertion point with the keyboard or the mouse.</span></span> <span data-ttu-id="2742d-105">テキストボックスでフォーカスが失われた場合は、ユーザーが最後に配置した場所に挿入ポイントが配置されます。</span><span class="sxs-lookup"><span data-stu-id="2742d-105">If the text box loses and then regains the focus, the insertion point will be wherever the user last placed it.</span></span>  
  
 <span data-ttu-id="2742d-106">場合によっては、この動作をユーザーに混乱ことがあります。</span><span class="sxs-lookup"><span data-stu-id="2742d-106">In some cases, this behavior can be disconcerting to the user.</span></span> <span data-ttu-id="2742d-107">ワードプロセッシングアプリケーションでは、既存のテキストの後に新しい文字が表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="2742d-107">In a word processing application, the user might expect new characters to appear after any existing text.</span></span> <span data-ttu-id="2742d-108">データ入力アプリケーションでは、ユーザーは既存のエントリを置き換えるために新しい文字が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2742d-108">In a data entry application, the user might expect new characters to replace any existing entry.</span></span> <span data-ttu-id="2742d-109"><xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A>プロパティとプロパティを使用すると、 <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> 目的に合わせて動作を変更できます。</span><span class="sxs-lookup"><span data-stu-id="2742d-109">The <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> and <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> properties enable you to modify the behavior to suit your purpose.</span></span>  
  
### <a name="to-control-the-insertion-point-in-a-textbox-control"></a><span data-ttu-id="2742d-110">TextBox コントロールの挿入位置を制御するには</span><span class="sxs-lookup"><span data-stu-id="2742d-110">To control the insertion point in a TextBox control</span></span>  
  
1. <span data-ttu-id="2742d-111"><xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> プロパティに適切な値を設定します。</span><span class="sxs-lookup"><span data-stu-id="2742d-111">Set the <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property to an appropriate value.</span></span> <span data-ttu-id="2742d-112">0の場合、挿入ポイントは最初の文字のすぐ左に配置されます。</span><span class="sxs-lookup"><span data-stu-id="2742d-112">Zero places the insertion point immediately to the left of the first character.</span></span>  
  
2. <span data-ttu-id="2742d-113">Optionalプロパティを、 <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> 選択するテキストの長さに設定します。</span><span class="sxs-lookup"><span data-stu-id="2742d-113">(Optional) Set the <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> property to the length of the text you want to select.</span></span>  
  
     <span data-ttu-id="2742d-114">次のコードは、常に0への挿入ポイントを返します。</span><span class="sxs-lookup"><span data-stu-id="2742d-114">The code below always returns the insertion point to 0.</span></span> <span data-ttu-id="2742d-115">`TextBox1_Enter`イベントハンドラーはコントロールにバインドされている必要があります。詳細については、「 [Windows フォームでのイベントハンドラーの作成](../creating-event-handlers-in-windows-forms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2742d-115">The `TextBox1_Enter` event handler must be bound to the control; for more information, see [Creating Event Handlers in Windows Forms](../creating-event-handlers-in-windows-forms.md).</span></span>  
  
    ```vb  
    Private Sub TextBox1_Enter(ByVal sender As Object, ByVal e As System.EventArgs) Handles TextBox1.Enter  
       TextBox1.SelectionStart = 0  
       TextBox1.SelectionLength = 0  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_Enter(Object sender, System.EventArgs e) {  
       textBox1.SelectionStart = 0;  
       textBox1.SelectionLength = 0;  
    }  
    ```  
  
    ```cpp  
    private:  
       void textBox1_Enter(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          textBox1->SelectionStart = 0;  
          textBox1->SelectionLength = 0;  
       }  
    ```  
  
## <a name="making-the-insertion-point-visible-by-default"></a><span data-ttu-id="2742d-116">既定で挿入ポイントを表示する</span><span class="sxs-lookup"><span data-stu-id="2742d-116">Making the Insertion Point Visible by Default</span></span>  
 <span data-ttu-id="2742d-117"><xref:System.Windows.Forms.TextBox>既定では、コントロールがタブオーダーの最初の位置にある場合にのみ、挿入ポイントは新しいフォームに表示され <xref:System.Windows.Forms.TextBox> ます。</span><span class="sxs-lookup"><span data-stu-id="2742d-117">The <xref:System.Windows.Forms.TextBox> insertion point is visible by default in a new form only if the <xref:System.Windows.Forms.TextBox> control is first in the tab order.</span></span> <span data-ttu-id="2742d-118">そうしないと、キーボードまたはマウスを使用してフォーカスを移動した場合にのみ、挿入ポイントが表示され <xref:System.Windows.Forms.TextBox> ます。</span><span class="sxs-lookup"><span data-stu-id="2742d-118">Otherwise, the insertion point appears only if you give the <xref:System.Windows.Forms.TextBox> the focus with either the keyboard or the mouse.</span></span>  
  
#### <a name="to-make-the-text-box-insertion-point-visible-by-default-on-a-new-form"></a><span data-ttu-id="2742d-119">テキストボックスの挿入ポイントが既定で新しいフォームに表示されるようにするには</span><span class="sxs-lookup"><span data-stu-id="2742d-119">To make the text box insertion point visible by default on a new form</span></span>  
  
- <span data-ttu-id="2742d-120"><xref:System.Windows.Forms.TextBox>コントロールの <xref:System.Windows.Forms.Control.TabIndex%2A> プロパティをに設定し `0` ます。</span><span class="sxs-lookup"><span data-stu-id="2742d-120">Set the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.Control.TabIndex%2A> property to `0`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2742d-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="2742d-121">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="2742d-122">TextBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="2742d-122">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="2742d-123">方法: Windows フォームの TextBox コントロールを使用してパスワード テキスト ボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="2742d-123">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="2742d-124">方法: 読み取り専用テキスト ボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="2742d-124">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="2742d-125">方法: 文字列に引用符を挿入する</span><span class="sxs-lookup"><span data-stu-id="2742d-125">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="2742d-126">方法: Windows フォーム TextBox コントロールでテキストを選択する</span><span class="sxs-lookup"><span data-stu-id="2742d-126">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="2742d-127">方法: Windows フォーム TextBox コントロールで複数行を表示する</span><span class="sxs-lookup"><span data-stu-id="2742d-127">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="2742d-128">TextBox コントロール</span><span class="sxs-lookup"><span data-stu-id="2742d-128">TextBox Control</span></span>](textbox-control-windows-forms.md)
