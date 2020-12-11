---
title: 'チュートリアル: ステータス バー情報の実行時更新'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- status bars [Windows Forms], updating at run time
- status bars [Windows Forms], refreshing panels
- StatusBar control [Windows Forms], refreshing panels
- panels [Windows Forms], refreshing status bar
ms.assetid: cc2abb06-c082-49f7-a5a3-2fd1bbcb58d1
ms.openlocfilehash: a58f8698af95810e4f716aa2b105bb86be3f55e6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982696"
---
# <a name="walkthrough-updating-status-bar-information-at-run-time"></a><span data-ttu-id="43cb0-102">チュートリアル: ステータス バー情報の実行時更新</span><span class="sxs-lookup"><span data-stu-id="43cb0-102">Walkthrough: Updating Status Bar Information at Run Time</span></span>

> [!IMPORTANT]
> <span data-ttu-id="43cb0-103">コントロールとコントロールは、およびコントロール <xref:System.Windows.Forms.StatusStrip> <xref:System.Windows.Forms.ToolStripStatusLabel> に対して、機能の置き換えと追加を行います。ただし、コントロール <xref:System.Windows.Forms.StatusBar> とコントロールは、 <xref:System.Windows.Forms.StatusBarPanel> <xref:System.Windows.Forms.StatusBar> <xref:System.Windows.Forms.StatusBarPanel> 下位互換性と将来の使用の両方について、選択した場合に保持されます。</span><span class="sxs-lookup"><span data-stu-id="43cb0-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="43cb0-104">多くの場合、アプリケーションの状態の変化や他のユーザー操作に基づいて、ステータス バー パネルの内容を実行時に動的に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="43cb0-104">Often, a program will call for you to update the contents of status bar panels dynamically at run time, based on changes to application state or other user interaction.</span></span> <span data-ttu-id="43cb0-105">これは、CapsLock、NumLock、ScrollLock などのキーが有効化されたことをユーザーに通知したり、便利な情報として日付や時刻を表示したりするための一般的な方法です。</span><span class="sxs-lookup"><span data-stu-id="43cb0-105">This is a common way to signal users that keys such as the CAPS LOCK, NUM LOCK, or SCROLL LOCK are enabled, or to provide the date or a clock as a convenient reference.</span></span>  
  
 <span data-ttu-id="43cb0-106">次の例では、クラスのインスタンスを使用して <xref:System.Windows.Forms.StatusBarPanel> クロックをホストします。</span><span class="sxs-lookup"><span data-stu-id="43cb0-106">In the following example, you will use an instance of the <xref:System.Windows.Forms.StatusBarPanel> class to host a clock.</span></span>  
  
### <a name="to-get-the-status-bar-ready-for-updating"></a><span data-ttu-id="43cb0-107">ステータス バーを更新できる状態にするには</span><span class="sxs-lookup"><span data-stu-id="43cb0-107">To get the status bar ready for updating</span></span>  
  
1. <span data-ttu-id="43cb0-108">新しい Windows フォームを作成します。</span><span class="sxs-lookup"><span data-stu-id="43cb0-108">Create a new Windows form.</span></span>  
  
2. <span data-ttu-id="43cb0-109">フォームに <xref:System.Windows.Forms.StatusBar> コントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="43cb0-109">Add a <xref:System.Windows.Forms.StatusBar> control to your form.</span></span> <span data-ttu-id="43cb0-110">詳細については、「[方法 : Windows フォームにコントロールを追加する](how-to-add-controls-to-windows-forms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43cb0-110">For details, see [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
3. <span data-ttu-id="43cb0-111">コントロールにステータスバーパネルを追加 <xref:System.Windows.Forms.StatusBar> します。</span><span class="sxs-lookup"><span data-stu-id="43cb0-111">Add a status bar panel to your <xref:System.Windows.Forms.StatusBar> control.</span></span> <span data-ttu-id="43cb0-112">詳細については、「[方法 : StatusBar コントロールにパネルを追加する](how-to-add-panels-to-a-statusbar-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43cb0-112">For details, see [How to: Add Panels to a StatusBar Control](how-to-add-panels-to-a-statusbar-control.md).</span></span>  
  
4. <span data-ttu-id="43cb0-113"><xref:System.Windows.Forms.StatusBar>フォームに追加したコントロールについて、プロパティをに設定し <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> `true` ます。</span><span class="sxs-lookup"><span data-stu-id="43cb0-113">For the <xref:System.Windows.Forms.StatusBar> control you added to your form, set the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `true`.</span></span>  
  
5. <span data-ttu-id="43cb0-114"><xref:System.Windows.Forms.Timer>フォームに Windows フォームコンポーネントを追加します。</span><span class="sxs-lookup"><span data-stu-id="43cb0-114">Add a Windows Forms <xref:System.Windows.Forms.Timer> component to the form.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="43cb0-115">Windows フォーム <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> コンポーネントは、Windows フォーム環境向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="43cb0-115">The Windows Forms <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="43cb0-116">サーバー環境に適したタイマーが必要な場合は、「[サーバー ベースのタイマーの概要](/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43cb0-116">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span></span>  
  
6. <span data-ttu-id="43cb0-117"><xref:System.Windows.Forms.Timer.Enabled%2A> プロパティを `true`に設定します。</span><span class="sxs-lookup"><span data-stu-id="43cb0-117">Set the <xref:System.Windows.Forms.Timer.Enabled%2A> property to `true`.</span></span>  
  
7. <span data-ttu-id="43cb0-118"><xref:System.Windows.Forms.Timer.Interval%2A>のプロパティ <xref:System.Windows.Forms.Timer> を3万に設定します。</span><span class="sxs-lookup"><span data-stu-id="43cb0-118">Set the <xref:System.Windows.Forms.Timer.Interval%2A> property of the <xref:System.Windows.Forms.Timer> to 30000.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="43cb0-119"><xref:System.Windows.Forms.Timer.Interval%2A>コンポーネントのプロパティは、 <xref:System.Windows.Forms.Timer> 表示される時刻に正確な時刻が反映されるように、30秒 (3万ミリ秒) に設定されます。</span><span class="sxs-lookup"><span data-stu-id="43cb0-119">The <xref:System.Windows.Forms.Timer.Interval%2A> property of the <xref:System.Windows.Forms.Timer> component is set to 30 seconds (30,000 milliseconds) to ensure that an accurate time is reflected in the time displayed.</span></span>  
  
### <a name="to-implement-the-timer-to-update-the-status-bar"></a><span data-ttu-id="43cb0-120">タイマーを実装してステータス バーを更新するには</span><span class="sxs-lookup"><span data-stu-id="43cb0-120">To implement the timer to update the status bar</span></span>  
  
1. <span data-ttu-id="43cb0-121">コンポーネントのイベントハンドラーに次のコードを挿入して、 <xref:System.Windows.Forms.Timer> コントロールのパネルを更新し <xref:System.Windows.Forms.StatusBar> ます。</span><span class="sxs-lookup"><span data-stu-id="43cb0-121">Insert the following code into the event handler of the <xref:System.Windows.Forms.Timer> component to update the panel of the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
    ```vb  
    Private Sub Timer1_Tick(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Timer1.Tick  
       StatusBar1.Panels(0).Text = Now.ToShortTimeString  
    End Sub  
    ```  
  
    ```csharp  
    private void timer1_Tick(object sender, System.EventArgs e)  
    {  
       statusBar1.Panels[0].Text = DateTime.Now.ToShortTimeString();  
    }  
    ```  
  
    ```cpp  
    private:  
      System::Void timer1_Tick(System::Object ^ sender,  
        System::EventArgs ^ e)  
      {  
        statusBar1->Panels[0]->Text =  
          DateTime::Now.ToShortTimeString();  
      }  
    ```  
  
     <span data-ttu-id="43cb0-122">この時点で、アプリケーションを実行して、ステータス バー パネルで実行される時計を確認できる状態になります。</span><span class="sxs-lookup"><span data-stu-id="43cb0-122">At this point, you are ready to run the application and observe the clock running in the status bar panel.</span></span>  
  
### <a name="to-test-the-application"></a><span data-ttu-id="43cb0-123">アプリケーションをテストするには</span><span class="sxs-lookup"><span data-stu-id="43cb0-123">To test the application</span></span>  
  
1. <span data-ttu-id="43cb0-124">アプリケーションをデバッグし、F5 キーを押してアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="43cb0-124">Debug the application and press F5 to run it.</span></span> <span data-ttu-id="43cb0-125">デバッグの詳細については、「[Visual Studio でのデバッグ](/visualstudio/debugger/debugger-feature-tour)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43cb0-125">For details about debugging, see [Debugging in Visual Studio](/visualstudio/debugger/debugger-feature-tour).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="43cb0-126">ステータス バーに時計が表示されるまでに約 30 秒かかります。</span><span class="sxs-lookup"><span data-stu-id="43cb0-126">It will take approximately 30 seconds for the clock to appear in the status bar.</span></span> <span data-ttu-id="43cb0-127">これは、できるだけ正確な時刻を取得するためです。</span><span class="sxs-lookup"><span data-stu-id="43cb0-127">This is to get the most accurate time possible.</span></span> <span data-ttu-id="43cb0-128">反対に、時計がすぐに表示されるようにするには、 <xref:System.Windows.Forms.Timer.Interval%2A> 前の手順の手順 7. で設定したプロパティの値を小さくします。</span><span class="sxs-lookup"><span data-stu-id="43cb0-128">Conversely, to make the clock appear sooner, you can reduce the value of the <xref:System.Windows.Forms.Timer.Interval%2A> property you set in step 7 in the previous procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43cb0-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="43cb0-129">See also</span></span>

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [<span data-ttu-id="43cb0-130">方法: StatusBar コントロールにパネルを追加する</span><span class="sxs-lookup"><span data-stu-id="43cb0-130">How to: Add Panels to a StatusBar Control</span></span>](how-to-add-panels-to-a-statusbar-control.md)
- [<span data-ttu-id="43cb0-131">方法: Windows フォームの StatusBar コントロールでクリックされたパネルを確認する</span><span class="sxs-lookup"><span data-stu-id="43cb0-131">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](determine-which-panel-wf-statusbar-control-was-clicked.md)
- [<span data-ttu-id="43cb0-132">StatusBar コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="43cb0-132">StatusBar Control Overview</span></span>](statusbar-control-overview-windows-forms.md)
