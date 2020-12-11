---
title: CheckBox のクリックに応答する
description: チェックボックスの状態に応じて、何らかのアクションを実行するように Windows フォームアプリケーションをプログラミングする方法について説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Click event [Windows Forms], CheckBox control
- CheckBox control [Windows Forms], Click events
- events [Windows Forms], Click events
- double-clicks
- check boxes [Windows Forms], responding to events
ms.assetid: c39f901e-8899-43b6-aa31-939cbf7089fb
ms.openlocfilehash: 58944bc421f990343b6c58484aaab3d79c8bda5e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980719"
---
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a><span data-ttu-id="af1ad-103">方法 : Windows フォーム CheckBox のクリックに応答する</span><span class="sxs-lookup"><span data-stu-id="af1ad-103">How to: Respond to Windows Forms CheckBox Clicks</span></span>
<span data-ttu-id="af1ad-104">ユーザーが Windows フォームコントロールをクリックするたび <xref:System.Windows.Forms.CheckBox> に、 <xref:System.Windows.Forms.Control.Click> イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="af1ad-104">Whenever a user clicks a Windows Forms <xref:System.Windows.Forms.CheckBox> control, the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span> <span data-ttu-id="af1ad-105">チェックボックスの状態に応じて、何らかのアクションを実行するようにアプリケーションをプログラミングできます。</span><span class="sxs-lookup"><span data-stu-id="af1ad-105">You can program your application to perform some action depending upon the state of the check box.</span></span>  
  
### <a name="to-respond-to-checkbox-clicks"></a><span data-ttu-id="af1ad-106">チェックボックスのクリックに応答するには</span><span class="sxs-lookup"><span data-stu-id="af1ad-106">To respond to CheckBox clicks</span></span>  
  
1. <span data-ttu-id="af1ad-107">イベントハンドラーで、プロパティを使用して <xref:System.Windows.Forms.Control.Click> <xref:System.Windows.Forms.CheckBox.Checked%2A> コントロールの状態を確認し、必要な操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="af1ad-107">In the <xref:System.Windows.Forms.Control.Click> event handler, use the <xref:System.Windows.Forms.CheckBox.Checked%2A> property to determine the control's state, and perform any necessary action.</span></span>  
  
    ```vb  
    Private Sub CheckBox1_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles CheckBox1.Click  
       ' The CheckBox control's Text property is changed each time the
       ' control is clicked, indicating a checked or unchecked state.  
       If CheckBox1.Checked = True Then  
          CheckBox1.Text = "Checked"  
       Else  
          CheckBox1.Text = "Unchecked"  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void checkBox1_Click(object sender, System.EventArgs e)  
    {  
       // The CheckBox control's Text property is changed each time the
       // control is clicked, indicating a checked or unchecked state.  
       if (checkBox1.Checked)  
       {  
          checkBox1.Text = "Checked";  
       }  
       else  
       {  
          checkBox1.Text = "Unchecked";  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if (checkBox1->Checked)  
          {  
             checkBox1->Text = "Checked";  
          }  
          else  
          {  
             checkBox1->Text = "Unchecked";  
          }  
       }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="af1ad-108">ユーザーがコントロールをダブルクリックしようとすると <xref:System.Windows.Forms.CheckBox> 、各クリックは個別に処理されます。つまり、 <xref:System.Windows.Forms.CheckBox> コントロールはダブルクリックイベントをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="af1ad-108">If the user attempts to double-click the <xref:System.Windows.Forms.CheckBox> control, each click will be processed separately; that is, the <xref:System.Windows.Forms.CheckBox> control does not support the double-click event.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="af1ad-109"><xref:System.Windows.Forms.CheckBox.AutoCheck%2A>プロパティが `true` (既定値) の場合、が <xref:System.Windows.Forms.CheckBox> クリックされると、が自動的に選択またはクリアされます。</span><span class="sxs-lookup"><span data-stu-id="af1ad-109">When the <xref:System.Windows.Forms.CheckBox.AutoCheck%2A> property is `true` (the default), the <xref:System.Windows.Forms.CheckBox> is automatically selected or cleared when it is clicked.</span></span> <span data-ttu-id="af1ad-110">それ以外の場合は、 <xref:System.Windows.Forms.CheckBox.Checked%2A> イベントが発生したときにプロパティを手動で設定する必要があり <xref:System.Windows.Forms.Control.Click> ます。</span><span class="sxs-lookup"><span data-stu-id="af1ad-110">Otherwise, you must manually set the <xref:System.Windows.Forms.CheckBox.Checked%2A> property when the <xref:System.Windows.Forms.Control.Click> event occurs.</span></span>  
  
     <span data-ttu-id="af1ad-111">また、コントロールを使用して、一連 <xref:System.Windows.Forms.CheckBox> のアクションを決定することもできます。</span><span class="sxs-lookup"><span data-stu-id="af1ad-111">You can also use the <xref:System.Windows.Forms.CheckBox> control to determine a course of action.</span></span>  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a><span data-ttu-id="af1ad-112">チェックボックスがクリックされたときの動作を確認するには</span><span class="sxs-lookup"><span data-stu-id="af1ad-112">To determine a course of action when a check box is clicked</span></span>  
  
1. <span data-ttu-id="af1ad-113">Case ステートメントを使用してプロパティの値を照会し、一連の <xref:System.Windows.Forms.CheckBox.CheckState%2A> アクションを決定します。</span><span class="sxs-lookup"><span data-stu-id="af1ad-113">Use a case statement to query the value of the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property to determine a course of action.</span></span> <span data-ttu-id="af1ad-114">プロパティがに設定されている場合、プロパティは、 <xref:System.Windows.Forms.CheckBox.ThreeState%2A> `true` チェックする <xref:System.Windows.Forms.CheckBox.CheckState%2A> ボックスを表す3つの値、チェックをオフにするボックス、またはオプションが使用できないことを示すために淡色表示された状態でボックスが表示される3番目の中間状態を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="af1ad-114">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property may return three possible values, which represent the box being checked, the box being unchecked, or a third indeterminate state in which the box is displayed with a dimmed appearance to indicate the option is unavailable.</span></span>  
  
    ```vb  
    Private Sub CheckBox1_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles CheckBox1.Click  
       Select Case CheckBox1.CheckState  
          Case CheckState.Checked  
             ' Code for checked state.  
          Case CheckState.Unchecked  
             ' Code for unchecked state.  
          Case CheckState.Indeterminate  
             ' Code for indeterminate state.  
       End Select
    End Sub  
    ```  
  
    ```csharp  
    private void checkBox1_Click(object sender, System.EventArgs e)  
    {  
       switch(checkBox1.CheckState)  
       {  
          case CheckState.Checked:  
             // Code for checked state.  
             break;  
          case CheckState.Unchecked:  
             // Code for unchecked state.  
             break;  
          case CheckState.Indeterminate:  
             // Code for indeterminate state.  
             break;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          switch(checkBox1->CheckState) {  
             case CheckState::Checked:  
                // Code for checked state.  
                break;  
             case CheckState::Unchecked:  
                // Code for unchecked state.  
                break;  
             case CheckState::Indeterminate:  
                // Code for indeterminate state.  
                break;  
          }  
       }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="af1ad-115"><xref:System.Windows.Forms.CheckBox.ThreeState%2A>プロパティがに設定されている場合、 `true` プロパティは <xref:System.Windows.Forms.CheckBox.Checked%2A> `true` との両方に対してを返し <xref:System.Windows.Forms.CheckState.Checked> <xref:System.Windows.Forms.CheckState.Indeterminate> ます。</span><span class="sxs-lookup"><span data-stu-id="af1ad-115">When the <xref:System.Windows.Forms.CheckBox.ThreeState%2A> property is set to `true`, the <xref:System.Windows.Forms.CheckBox.Checked%2A> property returns `true` for both <xref:System.Windows.Forms.CheckState.Checked> and <xref:System.Windows.Forms.CheckState.Indeterminate>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af1ad-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="af1ad-116">See also</span></span>

- <xref:System.Windows.Forms.CheckBox>
- [<span data-ttu-id="af1ad-117">CheckBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="af1ad-117">CheckBox Control Overview</span></span>](checkbox-control-overview-windows-forms.md)
- [<span data-ttu-id="af1ad-118">方法 : Windows フォームの CheckBox コントロールでオプションを設定する</span><span class="sxs-lookup"><span data-stu-id="af1ad-118">How to: Set Options with Windows Forms CheckBox Controls</span></span>](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [<span data-ttu-id="af1ad-119">CheckBox コントロール</span><span class="sxs-lookup"><span data-stu-id="af1ad-119">CheckBox Control</span></span>](checkbox-control-windows-forms.md)
