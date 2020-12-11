---
title: '[キャンセル] ボタンとしてボタンを指定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 252f0834-e54b-44d9-96f7-ee5f50e94f2c
ms.openlocfilehash: 123b3e275065efadd24815320ea7d855808e60b9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982144"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button"></a><span data-ttu-id="92d25-102">方法: Windows フォームの Button コントロールをキャンセル ボタンとして指定する</span><span class="sxs-lookup"><span data-stu-id="92d25-102">How to: Designate a Windows Forms Button as the Cancel Button</span></span>
<span data-ttu-id="92d25-103">任意の Windows フォームで、 <xref:System.Windows.Forms.Button> [キャンセル] ボタンとしてコントロールを指定できます。</span><span class="sxs-lookup"><span data-stu-id="92d25-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the cancel button.</span></span> <span data-ttu-id="92d25-104">フォーム上の他のコントロールにフォーカスがあるかどうかに関係なく、ユーザーが ESC キーを押すたびに [キャンセル] ボタンがクリックされます。</span><span class="sxs-lookup"><span data-stu-id="92d25-104">A cancel button is clicked whenever the user presses the ESC key, regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="92d25-105">このようなボタンは、通常、ユーザーがアクションをコミットせずに操作をすばやく終了できるようにプログラミングされています。</span><span class="sxs-lookup"><span data-stu-id="92d25-105">Such a button is usually programmed to enable the user to quickly exit an operation without committing to any action.</span></span>  
  
### <a name="to-designate-the-cancel-button"></a><span data-ttu-id="92d25-106">[キャンセル] ボタンを指定するには</span><span class="sxs-lookup"><span data-stu-id="92d25-106">To designate the cancel button</span></span>  
  
1. <span data-ttu-id="92d25-107">フォームの <xref:System.Windows.Forms.Form.CancelButton%2A> プロパティを適切なコントロールに設定し <xref:System.Windows.Forms.Button> ます。</span><span class="sxs-lookup"><span data-stu-id="92d25-107">Set the form's <xref:System.Windows.Forms.Form.CancelButton%2A> property to the appropriate <xref:System.Windows.Forms.Button> control.</span></span>  
  
    ```vb  
    Private Sub SetCancelButton(ByVal myCancelBtn As Button)  
       Me.CancelButton = myCancelBtn  
    End Sub  
    ```  
  
    ```csharp  
    private void SetCancelButton(Button myCancelBtn)  
    {  
       this.CancelButton = myCancelBtn;  
    }  
    ```  
  
    ```cpp  
    private:  
       void SetCancelButton(Button ^ myCancelBtn)  
       {  
          this->CancelButton = myCancelBtn;  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="92d25-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="92d25-108">See also</span></span>

- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [<span data-ttu-id="92d25-109">Button コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="92d25-109">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="92d25-110">Windows フォームの Button コントロールを選択する方法</span><span class="sxs-lookup"><span data-stu-id="92d25-110">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="92d25-111">方法 : Windows フォームのボタンのクリックに応答する</span><span class="sxs-lookup"><span data-stu-id="92d25-111">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="92d25-112">方法: Windows フォームの Button コントロールを承認ボタンとして指定する</span><span class="sxs-lookup"><span data-stu-id="92d25-112">How to: Designate a Windows Forms Button as the Accept Button</span></span>](how-to-designate-a-windows-forms-button-as-the-accept-button.md)
- [<span data-ttu-id="92d25-113">Button コントロール</span><span class="sxs-lookup"><span data-stu-id="92d25-113">Button Control</span></span>](button-control-windows-forms.md)
