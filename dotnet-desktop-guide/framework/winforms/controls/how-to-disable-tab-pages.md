---
title: '方法: タブ ページを無効化する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tab pages [Windows Forms], hiding in forms
- TabControl control [Windows Forms], disabling pages
ms.assetid: adcc6618-8a34-4ee1-bbe3-47e732de6a59
ms.openlocfilehash: 9074aedb81a485267dc4faff92e0fe8d0d3b467f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982136"
---
# <a name="how-to-disable-tab-pages"></a><span data-ttu-id="1a9cf-102">方法: タブ ページを無効化する</span><span class="sxs-lookup"><span data-stu-id="1a9cf-102">How to: Disable Tab Pages</span></span>
<span data-ttu-id="1a9cf-103">場合によっては、Windows フォームアプリケーション内で使用できるデータへのアクセスを制限する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a9cf-103">On some occasions, you will want to restrict access to data that is available within your Windows Forms application.</span></span> <span data-ttu-id="1a9cf-104">この例の1つとして、タブコントロールのタブページにデータが表示されている場合があります。管理者は、ゲストまたは下位レベルのユーザーから制限するタブページに関する情報を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="1a9cf-104">One example of this might be when you have data displayed in the tab pages of a tab control; administrators could have information on a tab page that you would want to restrict from guest or lower-level users.</span></span>  
  
### <a name="to-disable-tab-pages-programmatically"></a><span data-ttu-id="1a9cf-105">プログラムによってタブページを無効にするには</span><span class="sxs-lookup"><span data-stu-id="1a9cf-105">To disable tab pages programmatically</span></span>  
  
1. <span data-ttu-id="1a9cf-106">タブコントロールのイベントを処理するコードを記述し <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> ます。</span><span class="sxs-lookup"><span data-stu-id="1a9cf-106">Write code to handle the tab control's <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event.</span></span> <span data-ttu-id="1a9cf-107">これは、ユーザーが1つのタブから次のタブに切り替えたときに発生するイベントです。</span><span class="sxs-lookup"><span data-stu-id="1a9cf-107">This is the event that is raised when the user switches from one tab to the next.</span></span>  
  
2. <span data-ttu-id="1a9cf-108">資格情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="1a9cf-108">Check credentials.</span></span> <span data-ttu-id="1a9cf-109">表示される情報に応じて、ユーザーがタブを表示できるようにする前に、ユーザーがログインしたユーザー名または他の形式の資格情報を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="1a9cf-109">Depending upon the information presented, you may want to check the user name the user has logged in with or some other form of credentials before allowing the user to view the tab.</span></span>  
  
3. <span data-ttu-id="1a9cf-110">ユーザーが適切な資格情報を持っている場合は、クリックされたタブを表示します。</span><span class="sxs-lookup"><span data-stu-id="1a9cf-110">If the user has appropriate credentials, display the tab that was clicked.</span></span> <span data-ttu-id="1a9cf-111">ユーザーが適切な資格情報を持っていない場合は、メッセージボックスまたはその他のユーザーインターフェイスを表示して、アクセス権がないことを示し、最初のタブに戻ります。</span><span class="sxs-lookup"><span data-stu-id="1a9cf-111">If the user does not have appropriate credentials, display a message box or some other user interface indicating that they do not have access, and return to the initial tab.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="1a9cf-112">実稼働アプリケーションにこの機能を実装する場合は、フォームのイベント中にこの資格情報の確認を実行でき <xref:System.Windows.Forms.Form.Load> ます。</span><span class="sxs-lookup"><span data-stu-id="1a9cf-112">When you implement this functionality in your production applications, you can perform this credential check during the form's <xref:System.Windows.Forms.Form.Load> event.</span></span> <span data-ttu-id="1a9cf-113">これにより、ユーザーインターフェイスを表示する前にタブを非表示にすることができます。これは、プログラミングの方法としてははるかに簡潔です。</span><span class="sxs-lookup"><span data-stu-id="1a9cf-113">This will allow you to hide the tab before any user interface is shown, which is a much cleaner approach to programming.</span></span> <span data-ttu-id="1a9cf-114">次に示す方法 (資格情報を確認し、イベント中にタブを無効にする) は、説明を目的としてい <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> ます。</span><span class="sxs-lookup"><span data-stu-id="1a9cf-114">The methodology used below (checking credentials and disabling the tab during the <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event) is for illustrative purposes.</span></span>  
  
4. <span data-ttu-id="1a9cf-115">2つ以上のタブページがある場合は、必要に応じて、元のタブページとは異なるタブページを表示します。</span><span class="sxs-lookup"><span data-stu-id="1a9cf-115">Optionally, if you have more than two tab pages, display a tab page different from the original.</span></span>  
  
     <span data-ttu-id="1a9cf-116">次の例では、 <xref:System.Windows.Forms.CheckBox> 資格情報を確認する代わりにコントロールを使用しています。タブへのアクセス条件はアプリケーションによって異なります。</span><span class="sxs-lookup"><span data-stu-id="1a9cf-116">In the example below, a <xref:System.Windows.Forms.CheckBox> control is used in lieu of checking the credentials, as the criteria for access to the tab will vary by application.</span></span> <span data-ttu-id="1a9cf-117"><xref:System.Windows.Forms.TabControl.SelectedIndexChanged>イベントが発生すると、資格情報の確認が true (つまり、チェックボックスがオン) になっており、選択したタブが `TabPage2` (この例では機密情報が含まれているタブ)、 `TabPage2` が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a9cf-117">When the <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event is raised, if the credential check is true (that is, the check box is checked) and the selected tab is `TabPage2` (the tab with the confidential information, in this example), then `TabPage2` is displayed.</span></span> <span data-ttu-id="1a9cf-118">それ以外の場合 `TabPage3` は、が表示され、適切なアクセス特権がないことを示すメッセージボックスがユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a9cf-118">Otherwise, `TabPage3` is displayed and a message box is shown to the user, indicating they did not have appropriate access privileges.</span></span> <span data-ttu-id="1a9cf-119">次のコードは、 <xref:System.Windows.Forms.CheckBox> コントロール () と、 `CredentialCheck` <xref:System.Windows.Forms.TabControl> 3 つのタブページを持つコントロールを持つフォームを前提としています。</span><span class="sxs-lookup"><span data-stu-id="1a9cf-119">The code below assumes a form with a <xref:System.Windows.Forms.CheckBox> control (`CredentialCheck`) and a <xref:System.Windows.Forms.TabControl> control with three tab pages.</span></span>  
  
    ```vb  
    Private Sub TabControl1_SelectedIndexChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles TabControl1.SelectedIndexChanged  
       ' Check Credentials Here  
  
       If CredentialCheck.Checked = True And _
       TabControl1.SelectedTab Is TabPage2 Then  
          TabControl1.SelectedTab = TabPage2  
       ElseIf CredentialCheck.Checked = False _
       And TabControl1.SelectedTab Is TabPage2 Then  
          MessageBox.Show _
         ("Unable to load tab. You have insufficient access privileges.")  
          TabControl1.SelectedTab = TabPage3  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void tabControl1_SelectedIndexChanged(object sender, System.EventArgs e)  
    {  
        // Check Credentials Here  
  
        if ((CredentialCheck.Checked == true) && (tabControl1.SelectedTab == tabPage2))
        {  
            tabControl1.SelectedTab = tabPage2;  
        }  
        else if ((CredentialCheck.Checked == false) && (tabControl1.SelectedTab == tabPage2))  
        {  
            MessageBox.Show("Unable to load tab. You have insufficient access privileges.");  
            tabControl1.SelectedTab = tabPage3;  
        }  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void tabControl1_SelectedIndexChanged(  
          System::Object ^ sender,  
          System::EventArgs ^  e)  
       {  
          // Check Credentials Here  
          if ((CredentialCheck->Checked == true) &&  
              (tabControl1->SelectedTab == tabPage2))  
          {  
             tabControl1->SelectedTab = tabPage2;  
          }  
          else if ((CredentialCheck->Checked == false) &&  
                   (tabControl1->SelectedTab == tabPage2))  
          {  
             MessageBox::Show(String::Concat("Unable to load tab. ",  
                "You have insufficient access privileges."));  
             tabControl1->SelectedTab = tabPage3;  
          }  
       }  
    ```  
  
     <span data-ttu-id="1a9cf-120">(Visual C#、Visual C++)フォームのコンストラクターに次のコードを配置して、イベントハンドラーを登録します。</span><span class="sxs-lookup"><span data-stu-id="1a9cf-120">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.tabControl1.SelectedIndexChanged +=
       new System.EventHandler(this.tabControl1_SelectedIndexChanged);  
    ```  
  
    ```cpp  
    this->tabControl1->SelectedIndexChanged +=  
       gcnew System::EventHandler(this, &Form1::tabControl1_SelectedIndexChanged);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1a9cf-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="1a9cf-121">See also</span></span>

- [<span data-ttu-id="1a9cf-122">TabControl コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="1a9cf-122">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="1a9cf-123">方法: タブ ページにコントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="1a9cf-123">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="1a9cf-124">方法: Windows フォーム TabControl のタブを追加および削除する</span><span class="sxs-lookup"><span data-stu-id="1a9cf-124">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
- [<span data-ttu-id="1a9cf-125">方法: Windows フォーム TabControl の表示形式を変更する</span><span class="sxs-lookup"><span data-stu-id="1a9cf-125">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
