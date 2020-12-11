---
title: '方法: アクティブな MDI 子フォームを特定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Clipboard [Windows Forms], copying data to
- MDI [Windows Forms], child windows
- child forms
- MDI [Windows Forms], activating forms
- MDI [Windows Forms], locating focus
ms.assetid: 33880ec3-0207-4c2b-a616-ff140443cc0f
ms.openlocfilehash: 57491faa10c182630d41565ba236d65e393929b3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974408"
---
# <a name="how-to-determine-the-active-mdi-child"></a><span data-ttu-id="a8614-102">方法: アクティブな MDI 子フォームを特定する</span><span class="sxs-lookup"><span data-stu-id="a8614-102">How to: Determine the Active MDI Child</span></span>
<span data-ttu-id="a8614-103">場合によっては、現在アクティブな子フォームにフォーカスがあるコントロールを操作するコマンドを用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8614-103">On occasion, you will want to provide a command that operates on the control that has focus on the currently active child form.</span></span> <span data-ttu-id="a8614-104">たとえば、選択したテキストを子フォームのテキストボックスからクリップボードにコピーするとします。</span><span class="sxs-lookup"><span data-stu-id="a8614-104">For example, suppose you want to copy selected text from the child form's text box to the Clipboard.</span></span> <span data-ttu-id="a8614-105">標準の [ <xref:System.Windows.Forms.Control.Click> 編集] メニューの [コピー] メニュー項目のイベントを使用して、選択したテキストをクリップボードにコピーするプロシージャを作成します。</span><span class="sxs-lookup"><span data-stu-id="a8614-105">You would create a procedure that copies selected text to the Clipboard using the <xref:System.Windows.Forms.Control.Click> event of the Copy menu item on the standard Edit menu.</span></span>  
  
 <span data-ttu-id="a8614-106">MDI アプリケーションは、同じ子フォームのインスタンスを多数持つことができるため、使用するフォームをプロシージャが認識している必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8614-106">Because an MDI application can have many instances of the same child form, the procedure needs to know which form to use.</span></span> <span data-ttu-id="a8614-107">正しいフォームを指定するには、 <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> プロパティを使用します。このプロパティは、フォーカスのある子フォーム、または最も最近アクティブだった子フォームを返します。</span><span class="sxs-lookup"><span data-stu-id="a8614-107">To specify the correct form, use the <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> property, which returns the child form that has the focus or that was most recently active.</span></span>  
  
 <span data-ttu-id="a8614-108">フォームに複数のコントロールがある場合は、アクティブなコントロールを指定する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="a8614-108">When you have several controls on a form, you also need to specify which control is active.</span></span> <span data-ttu-id="a8614-109">プロパティと同様 <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> に、 <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> プロパティは、アクティブな子フォームにフォーカスがあるコントロールを返します。</span><span class="sxs-lookup"><span data-stu-id="a8614-109">Like the <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> property, the <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> property returns the control with the focus on the active child form.</span></span> <span data-ttu-id="a8614-110">次の手順は、子フォームメニュー、MDI フォームのメニュー、またはツールバーボタンから呼び出すことができるコピー手順を示しています。</span><span class="sxs-lookup"><span data-stu-id="a8614-110">The procedure below illustrates a copy procedure that can be called from a child form menu, a menu on the MDI form, or a toolbar button.</span></span>  
  
### <a name="to-determine-the-active-mdi-child-to-copy-its-text-to-the-clipboard"></a><span data-ttu-id="a8614-111">アクティブな MDI 子を特定するには (テキストをクリップボードにコピーする場合)</span><span class="sxs-lookup"><span data-stu-id="a8614-111">To determine the active MDI child (to copy its text to the Clipboard)</span></span>  
  
1. <span data-ttu-id="a8614-112">メソッド内で、アクティブな子フォームのアクティブなコントロールのテキストをクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="a8614-112">Within a method, copy the text of the active control of the active child form to the Clipboard.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="a8614-113">この例では、 `Form1` コントロールを含む mdi 子ウィンドウが1つ以上ある mdi 親フォーム () があることを前提としてい <xref:System.Windows.Forms.RichTextBox> ます。</span><span class="sxs-lookup"><span data-stu-id="a8614-113">This example assumes there is an MDI parent form (`Form1`) that has one or more MDI child windows containing a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="a8614-114">詳細については、「 [MDI 親フォームの作成](how-to-create-mdi-parent-forms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8614-114">For more information, see [Creating MDI Parent Forms](how-to-create-mdi-parent-forms.md).</span></span>  
  
    ```vb  
    Public Sub mniCopy_Click(ByVal sender As Object, _  
       ByVal e As System.EventArgs) Handles mniCopy.Click  
  
       ' Determine the active child form.  
       Dim activeChild As Form = Me.ActiveMDIChild  
  
       ' If there is an active child form, find the active control, which  
       ' in this example should be a RichTextBox.  
       If (Not activeChild Is Nothing) Then  
          Dim theBox As RichTextBox = _  
            TryCast(activeChild.ActiveControl, RichTextBox)  
  
          If (Not theBox Is Nothing) Then  
             'Put selected text on Clipboard.  
             Clipboard.SetDataObject(theBox.SelectedText)  
          Else  
             MessageBox.Show("You need to select a RichTextBox.")  
          End If  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    protected void mniCopy_Click (object sender, System.EventArgs e)  
    {  
       // Determine the active child form.  
       Form activeChild = this.ActiveMdiChild;  
  
       // If there is an active child form, find the active control, which  
       // in this example should be a RichTextBox.  
       if (activeChild != null)  
       {
          try  
          {  
             RichTextBox theBox = (RichTextBox)activeChild.ActiveControl;  
             if (theBox != null)  
             {  
                // Put the selected text on the Clipboard.  
                Clipboard.SetDataObject(theBox.SelectedText);  
  
             }  
          }  
          catch  
          {  
             MessageBox.Show("You need to select a RichTextBox.");  
          }  
       }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a8614-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="a8614-115">See also</span></span>

- [<span data-ttu-id="a8614-116">マルチ ドキュメント インターフェイス (MDI) アプリケーション</span><span class="sxs-lookup"><span data-stu-id="a8614-116">Multiple-Document Interface (MDI) Applications</span></span>](multiple-document-interface-mdi-applications.md)
- [<span data-ttu-id="a8614-117">方法: MDI 親フォームを作成する</span><span class="sxs-lookup"><span data-stu-id="a8614-117">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="a8614-118">方法: MDI 子フォームを作成する</span><span class="sxs-lookup"><span data-stu-id="a8614-118">How to: Create MDI Child Forms</span></span>](how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="a8614-119">方法: アクティブな MDI 子フォームにデータを送信する</span><span class="sxs-lookup"><span data-stu-id="a8614-119">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)
- [<span data-ttu-id="a8614-120">方法: MDI 子フォームを配置する</span><span class="sxs-lookup"><span data-stu-id="a8614-120">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)
