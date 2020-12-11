---
title: RichTextBox コントロールでの書式設定属性の変更を確認する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], text boxes
- RichTextBox control [Windows Forms], determining font changes
- text boxes [Windows Forms], determining font changes
- SelChange event
ms.assetid: bdfed015-f77a-41e5-b38f-f8629b2fa166
ms.openlocfilehash: a190c3479b58464763e0eefdd32d14e88a1f05e1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974179"
---
# <a name="how-to-determine-when-formatting-attributes-change-in-the-windows-forms-richtextbox-control"></a><span data-ttu-id="46210-102">方法: Windows フォームの RichTextBox コントロールにおける書式属性の変更を確認する</span><span class="sxs-lookup"><span data-stu-id="46210-102">How to: Determine When Formatting Attributes Change in the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="46210-103">Windows フォームコントロールの一般的な用途 <xref:System.Windows.Forms.RichTextBox> は、フォントオプションや段落スタイルなどの属性を使用してテキストを書式設定することです。</span><span class="sxs-lookup"><span data-stu-id="46210-103">A common use of the Windows Forms <xref:System.Windows.Forms.RichTextBox> control is formatting text with attributes such as font options or paragraph styles.</span></span> <span data-ttu-id="46210-104">多くのワードプロセッシングアプリケーションのように、アプリケーションでは、ツールバーを表示するためにテキストの書式設定の変更を追跡する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="46210-104">Your application may need to keep track of any changes in text formatting for the purpose of displaying a toolbar, as in many word-processing applications.</span></span>  
  
### <a name="to-respond-to-changes-in-formatting-attributes"></a><span data-ttu-id="46210-105">属性の書式設定の変更に応答するには</span><span class="sxs-lookup"><span data-stu-id="46210-105">To respond to changes in formatting attributes</span></span>  
  
1. <span data-ttu-id="46210-106"><xref:System.Windows.Forms.RichTextBox.SelectionChanged>属性の値に応じて適切なアクションを実行するために、イベントハンドラーにコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="46210-106">Write code in the <xref:System.Windows.Forms.RichTextBox.SelectionChanged> event handler to perform an appropriate action depending on the value of the attribute.</span></span> <span data-ttu-id="46210-107">次の例では、プロパティの値に応じてツールバーボタンの外観を変更し <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="46210-107">The following example changes the appearance of a toolbar button depending on the value of the <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> property.</span></span> <span data-ttu-id="46210-108">ツールバーボタンは、カーソルがコントロール内で移動したときにのみ更新されます。</span><span class="sxs-lookup"><span data-stu-id="46210-108">The toolbar button will only be updated when the insertion point is moved in the control.</span></span>  
  
     <span data-ttu-id="46210-109">次の例では、 <xref:System.Windows.Forms.RichTextBox> コントロールと、 <xref:System.Windows.Forms.ToolBar> ツールバーボタンを含むコントロールを含むフォームを想定しています。</span><span class="sxs-lookup"><span data-stu-id="46210-109">The example below assumes a form with a <xref:System.Windows.Forms.RichTextBox> control and a <xref:System.Windows.Forms.ToolBar> control that contains a toolbar button.</span></span> <span data-ttu-id="46210-110">ツールバーとツールバーボタンの詳細については、「 [方法: ツールバーコントロールにボタンを追加](how-to-add-buttons-to-a-toolbar-control.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46210-110">For more information about toolbars and toolbar buttons, see [How to: Add Buttons to a ToolBar Control](how-to-add-buttons-to-a-toolbar-control.md).</span></span>  
  
    ```vb  
    ' The following code assumes the existence of a toolbar control  
    ' with at least one toolbar button.  
    Private Sub RichTextBox1_SelectionChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles RichTextBox1.SelectionChanged  
       If RichTextBox1.SelectionBullet = True Then  
          ' Bullet button on toolbar should appear pressed  
          ToolBarButton1.Pushed = True  
       Else  
           ' Bullet button on toolbar should appear unpressed  
           ToolBarButton1.Pushed = False  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    // The following code assumes the existence of a toolbar control  
    // with at least one toolbar button.  
    private void richTextBox1_SelectionChanged(object sender,  
    System.EventArgs e)  
    {  
       if (richTextBox1.SelectionBullet == true)
       {  
          // Bullet button on toolbar should appear pressed  
          toolBarButton1.Pushed = true;  
       }  
       else
       {  
          // Bullet button on toolbar should appear unpressed  
          toolBarButton1.Pushed = false;  
       }  
    }  
    ```  
  
    ```cpp  
    // The following code assumes the existence of a toolbar control  
    // with at least one toolbar button.  
    private:  
       System::Void richTextBox1_SelectionChanged(  
          System::Object ^  sender, System::EventArgs ^  e)  
       {  
          if (richTextBox1->SelectionBullet == true)  
          {  
             // Bullet button on toolbar should appear pressed  
             toolBarButton1->Pushed = true;  
          }  
          else  
          {  
             // Bullet button on toolbar should appear unpressed  
             toolBarButton1->Pushed = false;  
          }  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="46210-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="46210-111">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox.SelectionChanged>
- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="46210-112">RichTextBox コントロール</span><span class="sxs-lookup"><span data-stu-id="46210-112">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="46210-113">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="46210-113">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
