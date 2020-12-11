---
title: Button のクリックに応答する
description: Windows フォームボタンのクリックに応答する方法について説明します。 Windows フォームボタンコントロールの最も基本的な用途は、ボタンがクリックされたときにコードを実行することです。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], responding to Click events
- events [Windows Forms], Click events
- Click event [Windows Forms], Button control
- MouseDown event
- Button control [Windows Forms], click response
- double-clicks
- examples [Windows Forms], controls
- Click event [Windows Forms], responding to
ms.assetid: 7a4951bd-369c-4662-b246-28ad83eda484
ms.openlocfilehash: 5c458d56dbd6f1cab8e88bdbb86ede958367e5c4
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974757"
---
# <a name="how-to-respond-to-windows-forms-button-clicks"></a><span data-ttu-id="cda2f-104">方法 : Windows フォームのボタンのクリックに応答する</span><span class="sxs-lookup"><span data-stu-id="cda2f-104">How to: Respond to Windows Forms Button Clicks</span></span>
<span data-ttu-id="cda2f-105">Windows フォームコントロールの最も基本的な用途 <xref:System.Windows.Forms.Button> は、ボタンがクリックされたときにコードを実行することです。</span><span class="sxs-lookup"><span data-stu-id="cda2f-105">The most basic use of a Windows Forms <xref:System.Windows.Forms.Button> control is to run some code when the button is clicked.</span></span>  
  
 <span data-ttu-id="cda2f-106">コントロールをクリックすると <xref:System.Windows.Forms.Button> 、、、イベントなどの他のイベントも多数生成さ <xref:System.Windows.Forms.Control.MouseEnter> <xref:System.Windows.Forms.Control.MouseDown> <xref:System.Windows.Forms.Control.MouseUp> れます。</span><span class="sxs-lookup"><span data-stu-id="cda2f-106">Clicking a <xref:System.Windows.Forms.Button> control also generates a number of other events, such as the <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseDown>, and <xref:System.Windows.Forms.Control.MouseUp> events.</span></span> <span data-ttu-id="cda2f-107">これらの関連イベントにイベントハンドラーをアタッチする場合は、それらのアクションが競合していないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="cda2f-107">If you intend to attach event handlers for these related events, be sure that their actions do not conflict.</span></span> <span data-ttu-id="cda2f-108">たとえば、ボタンをクリックすると、ユーザーがテキストボックスに入力した情報がクリアされた場合、ボタンの上にマウスポインターを置くと、その時点で存在しない情報を示すツールヒントが表示されません。</span><span class="sxs-lookup"><span data-stu-id="cda2f-108">For example, if clicking the button clears information that the user has typed in a text box, pausing the mouse pointer over the button should not display a tool tip with that now-nonexistent information.</span></span>  
  
 <span data-ttu-id="cda2f-109">ユーザーがコントロールをダブルクリックしようとすると <xref:System.Windows.Forms.Button> 、各クリックは個別に処理されます。つまり、コントロールはダブルクリックイベントをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="cda2f-109">If the user attempts to double-click the <xref:System.Windows.Forms.Button> control, each click will be processed separately; that is, the control does not support the double-click event.</span></span>  
  
### <a name="to-respond-to-a-button-click"></a><span data-ttu-id="cda2f-110">ボタンのクリックに応答するには</span><span class="sxs-lookup"><span data-stu-id="cda2f-110">To respond to a button click</span></span>  
  
- <span data-ttu-id="cda2f-111">ボタンの [実行するコードを記述してください] をクリックし `Click` <xref:System.EventHandler> ます。</span><span class="sxs-lookup"><span data-stu-id="cda2f-111">In the button's `Click` <xref:System.EventHandler> write the code to run.</span></span> <span data-ttu-id="cda2f-112">`Button1_Click` コントロールにバインドされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cda2f-112">`Button1_Click` must be bound to the control.</span></span> <span data-ttu-id="cda2f-113">詳細については、「 [方法: Windows フォームの実行時にイベントハンドラーを作成](../how-to-create-event-handlers-at-run-time-for-windows-forms.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cda2f-113">For more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       MessageBox.Show("Button1 was clicked")  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       MessageBox.Show("button1 was clicked");  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          MessageBox::Show("button1 was clicked");  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="cda2f-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="cda2f-114">See also</span></span>

- [<span data-ttu-id="cda2f-115">Button コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="cda2f-115">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="cda2f-116">Windows フォームの Button コントロールを選択する方法</span><span class="sxs-lookup"><span data-stu-id="cda2f-116">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="cda2f-117">Button コントロール</span><span class="sxs-lookup"><span data-stu-id="cda2f-117">Button Control</span></span>](button-control-windows-forms.md)
