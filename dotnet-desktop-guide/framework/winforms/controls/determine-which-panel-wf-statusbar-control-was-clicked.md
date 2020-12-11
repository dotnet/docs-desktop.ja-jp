---
title: StatusBar コントロールでクリックされたパネルを確認する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- status bars [Windows Forms], determining panel clicked
- panels [Windows Forms], determining clicked
- StatusBar control [Windows Forms], coding panel click events
- StatusBar control [Windows Forms], determining panel clicked
- PanelClick event [Windows Forms], determining panel clicked
- Panel control [Windows Forms], determining click
ms.assetid: d14c6092-04b2-4a07-8ddf-0dd11277ff5f
ms.openlocfilehash: eb3b10d515ba5b62236594e063ca7f060b34b73e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974178"
---
# <a name="how-to-determine-which-panel-in-the-windows-forms-statusbar-control-was-clicked"></a><span data-ttu-id="2e0f6-102">方法: Windows フォームの StatusBar コントロールでクリックされたパネルを確認する</span><span class="sxs-lookup"><span data-stu-id="2e0f6-102">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>
> [!IMPORTANT]
> <span data-ttu-id="2e0f6-103">コントロールとコントロールは、およびコントロール <xref:System.Windows.Forms.StatusStrip> <xref:System.Windows.Forms.ToolStripStatusLabel> に対して、機能の置き換えと追加を行います。ただし、コントロール <xref:System.Windows.Forms.StatusBar> とコントロールは、 <xref:System.Windows.Forms.StatusBarPanel> <xref:System.Windows.Forms.StatusBar> <xref:System.Windows.Forms.StatusBarPanel> 下位互換性と将来の使用の両方について、選択した場合に保持されます。</span><span class="sxs-lookup"><span data-stu-id="2e0f6-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="2e0f6-104">ユーザーのクリックに応答するように [StatusBar コントロール](statusbar-control-windows-forms.md) コントロールをプログラミングするには、イベント内で case ステートメントを使用し <xref:System.Windows.Forms.StatusBar.PanelClick> ます。</span><span class="sxs-lookup"><span data-stu-id="2e0f6-104">To program the [StatusBar Control](statusbar-control-windows-forms.md) control to respond to user clicks, use a case statement within the <xref:System.Windows.Forms.StatusBar.PanelClick> event.</span></span> <span data-ttu-id="2e0f6-105">イベントには、クリックされたへの参照を含む引数 (パネル引数) が含まれてい <xref:System.Windows.Forms.StatusBarPanel> ます。</span><span class="sxs-lookup"><span data-stu-id="2e0f6-105">The event contains an argument (the panel argument), which contains a reference to the clicked <xref:System.Windows.Forms.StatusBarPanel>.</span></span> <span data-ttu-id="2e0f6-106">この参照を使用して、クリックされたパネルのインデックスを特定し、それに応じてプログラムを作成できます。</span><span class="sxs-lookup"><span data-stu-id="2e0f6-106">Using this reference, you can determine the index of the clicked panel, and program accordingly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2e0f6-107"><xref:System.Windows.Forms.StatusBar>コントロールの <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> プロパティがに設定されていることを確認し `true` ます。</span><span class="sxs-lookup"><span data-stu-id="2e0f6-107">Ensure that the <xref:System.Windows.Forms.StatusBar> control's <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property is set to `true`.</span></span>  
  
### <a name="to-determine-which-panel-was-clicked"></a><span data-ttu-id="2e0f6-108">クリックされたパネルを確認するには</span><span class="sxs-lookup"><span data-stu-id="2e0f6-108">To determine which panel was clicked</span></span>  
  
1. <span data-ttu-id="2e0f6-109">イベントハンドラーでは、 <xref:System.Windows.Forms.StatusBar.PanelClick> `Select Case` (Visual Basic) または `switch case` (Visual C# または Visual C++) のステートメントを使用して、クリックされたパネルを判別します。これを行うには、イベント引数でクリックしたパネルのインデックスを調べます。</span><span class="sxs-lookup"><span data-stu-id="2e0f6-109">In the <xref:System.Windows.Forms.StatusBar.PanelClick> event handler, use a `Select Case` (in Visual Basic) or `switch case` (Visual C# or Visual C++) statement to determine which panel was clicked by examining the index of the clicked panel in the event arguments.</span></span>  
  
     <span data-ttu-id="2e0f6-110">次のコード例では、 <xref:System.Windows.Forms.StatusBar> コントロール、 `StatusBar1` 、およびという2つのオブジェクトのプレゼンスをフォームに指定する必要があり <xref:System.Windows.Forms.StatusBarPanel> `StatusBarPanel1` `StatusBarPanel2` ます。</span><span class="sxs-lookup"><span data-stu-id="2e0f6-110">The following code example requires the presence, on the form, of a <xref:System.Windows.Forms.StatusBar> control, `StatusBar1`, and two <xref:System.Windows.Forms.StatusBarPanel> objects, `StatusBarPanel1` and `StatusBarPanel2`.</span></span>  
  
    ```vb  
    Private Sub StatusBar1_PanelClick(ByVal sender As System.Object, ByVal e As System.Windows.Forms.StatusBarPanelClickEventArgs) Handles StatusBar1.PanelClick  
       Select Case StatusBar1.Panels.IndexOf(e.StatusBarPanel)  
         Case 0  
           MessageBox.Show("You have clicked Panel One.")  
         Case 1  
           MessageBox.Show("You have clicked Panel Two.")  
       End Select  
    End Sub  
    ```  
  
    ```csharp  
    private void statusBar1_PanelClick(object sender,
    System.Windows.Forms.StatusBarPanelClickEventArgs e)  
    {  
       switch (statusBar1.Panels.IndexOf(e.StatusBarPanel))  
       {  
          case 0 :  
             MessageBox.Show("You have clicked Panel One.");  
             break;  
          case 1 :  
             MessageBox.Show("You have clicked Panel Two.");  
             break;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void statusBar1_PanelClick(System::Object ^  sender,  
          System::Windows::Forms::StatusBarPanelClickEventArgs ^  e)  
       {  
          switch (statusBar1->Panels->IndexOf(e->StatusBarPanel))  
          {  
             case 0 :  
                MessageBox::Show("You have clicked Panel One.");  
                break;  
             case 1 :  
                MessageBox::Show("You have clicked Panel Two.");  
                break;  
          }  
       }  
    ```  
  
     <span data-ttu-id="2e0f6-111">(Visual C#、Visual C++)フォームのコンストラクターに次のコードを配置して、イベントハンドラーを登録します。</span><span class="sxs-lookup"><span data-stu-id="2e0f6-111">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.statusBar1.PanelClick += new
       System.Windows.Forms.StatusBarPanelClickEventHandler
       (this.statusBar1_PanelClick);  
    ```  
  
    ```cpp  
    this->statusBar1->PanelClick += gcnew  
       System::Windows::Forms::StatusBarPanelClickEventHandler  
       (this, &Form1::statusBar1_PanelClick);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="2e0f6-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="2e0f6-112">See also</span></span>

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [<span data-ttu-id="2e0f6-113">方法: ステータス バー パネルのサイズを設定する</span><span class="sxs-lookup"><span data-stu-id="2e0f6-113">How to: Set the Size of Status-Bar Panels</span></span>](how-to-set-the-size-of-status-bar-panels.md)
- [<span data-ttu-id="2e0f6-114">チュートリアル: ステータス バー情報の実行時更新</span><span class="sxs-lookup"><span data-stu-id="2e0f6-114">Walkthrough: Updating Status Bar Information at Run Time</span></span>](walkthrough-updating-status-bar-information-at-run-time.md)
- [<span data-ttu-id="2e0f6-115">StatusBar コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="2e0f6-115">StatusBar Control Overview</span></span>](statusbar-control-overview-windows-forms.md)
