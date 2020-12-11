---
title: CheckBox コントロールでオプションを設定する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- checked
helpviewer_keywords:
- CheckBox control [Windows Forms], checked state
- check boxes [Windows Forms], using to set options
- CheckBox control [Windows Forms], using to set options
ms.assetid: 2ac70498-7e3e-4e07-8901-ccabaeb5fd3e
ms.openlocfilehash: 00b467836d8e60aeee51a010a6384abf7dd73c56
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980688"
---
# <a name="how-to-set-options-with-windows-forms-checkbox-controls"></a><span data-ttu-id="6422b-102">方法 : Windows フォームの CheckBox コントロールでオプションを設定する</span><span class="sxs-lookup"><span data-stu-id="6422b-102">How to: Set Options with Windows Forms CheckBox Controls</span></span>
<span data-ttu-id="6422b-103">Windows フォーム <xref:System.Windows.Forms.CheckBox> コントロールは、ユーザーに True/False または Yes/No オプションを提供するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="6422b-103">A Windows Forms <xref:System.Windows.Forms.CheckBox> control is used to give users True/False or Yes/No options.</span></span> <span data-ttu-id="6422b-104">コントロールが選択されると、そのコントロールにチェックマークが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6422b-104">The control displays a check mark when it is selected.</span></span>  
  
### <a name="to-set-options-with-checkbox-controls"></a><span data-ttu-id="6422b-105">CheckBox コントロールを使用してオプションを設定するには</span><span class="sxs-lookup"><span data-stu-id="6422b-105">To set options with CheckBox controls</span></span>  
  
1. <span data-ttu-id="6422b-106">プロパティの値を調べ <xref:System.Windows.Forms.CheckBox.Checked%2A> てその状態を確認し、その値を使用してオプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="6422b-106">Examine the value of the <xref:System.Windows.Forms.CheckBox.Checked%2A> property to determine its state, and use that value to set an option.</span></span>  
  
     <span data-ttu-id="6422b-107">次のコードサンプルでは、 <xref:System.Windows.Forms.CheckBox> コントロールのイベントが発生すると、この <xref:System.Windows.Forms.CheckBox.CheckedChanged> <xref:System.Windows.Forms.Control.AllowDrop%2A> チェックボックスがオンになっている場合、フォームのプロパティはに設定され `false` ます。</span><span class="sxs-lookup"><span data-stu-id="6422b-107">In the code sample below, when the <xref:System.Windows.Forms.CheckBox> control's <xref:System.Windows.Forms.CheckBox.CheckedChanged> event is raised, the form's <xref:System.Windows.Forms.Control.AllowDrop%2A> property is set to `false` if the check box is checked.</span></span> <span data-ttu-id="6422b-108">これは、ユーザーの操作を制限する必要がある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="6422b-108">This is useful for situations where you want to restrict user interaction.</span></span>  
  
    ```vb  
    Private Sub CheckBox1_CheckedChanged(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles CheckBox1.CheckedChanged  
       ' Determine the CheckState of the check box.  
       If CheckBox1.CheckState = CheckState.Checked Then  
          ' If checked, do not allow items to be dragged onto the form.  
          Me.AllowDrop = False  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void checkBox1_CheckedChanged(object sender, System.EventArgs e)  
    {  
       // Determine the CheckState of the check box.  
       if (checkBox1.CheckState == CheckState.Checked)
       {  
          // If checked, do not allow items to be dragged onto the form.  
          this.AllowDrop = false;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // Determine the CheckState of the check box.  
          if (checkBox1->CheckState == CheckState::Checked)
          {  
             // If checked, do not allow items to be dragged onto the form.  
             this->AllowDrop = false;  
          }  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6422b-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="6422b-109">See also</span></span>

- <xref:System.Windows.Forms.CheckBox>
- [<span data-ttu-id="6422b-110">CheckBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="6422b-110">CheckBox Control Overview</span></span>](checkbox-control-overview-windows-forms.md)
- [<span data-ttu-id="6422b-111">方法 : Windows フォーム CheckBox のクリックに応答する</span><span class="sxs-lookup"><span data-stu-id="6422b-111">How to: Respond to Windows Forms CheckBox Clicks</span></span>](how-to-respond-to-windows-forms-checkbox-clicks.md)
- [<span data-ttu-id="6422b-112">CheckBox コントロール</span><span class="sxs-lookup"><span data-stu-id="6422b-112">CheckBox Control</span></span>](checkbox-control-windows-forms.md)
