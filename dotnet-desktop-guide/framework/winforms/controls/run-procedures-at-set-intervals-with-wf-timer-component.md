---
title: タイマーコンポーネントを設定した間隔でプロシージャを実行する
description: Windows フォームの Timer コンポーネントを使用して、設定した間隔で、または設定した時間間隔でプロシージャを実行する方法について説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], timers
- timers [Windows Forms], event intervals
- initialization [Windows Forms], Timer components
- timers [Windows Forms], Windows-based
- Timer component [Windows Forms], initializing
- procedures [Windows Forms], specific time intervals
ms.assetid: 8025247a-2de4-4d86-b8ab-a8cb8aeab2ea
ms.openlocfilehash: e98dec93fa50e94b6f5df6c42cdd349a4a06de53
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983496"
---
# <a name="how-to-run-procedures-at-set-intervals-with-the-windows-forms-timer-component"></a><span data-ttu-id="aee66-103">方法: Windows フォームの Timer コンポーネントを使用して一定間隔でプロシージャを実行する</span><span class="sxs-lookup"><span data-stu-id="aee66-103">How to: Run Procedures at Set Intervals with the Windows Forms Timer Component</span></span>

<span data-ttu-id="aee66-104">ループが完了するまで特定の間隔で実行するプロシージャや、設定した間隔が経過した時点で実行するプロシージャを作成することがあるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="aee66-104">You might sometimes want to create a procedure that runs at specific time intervals until a loop has finished or that runs when a set time interval has elapsed.</span></span> <span data-ttu-id="aee66-105"><xref:System.Windows.Forms.Timer> コンポーネントにより、このようなプロシージャが可能になります。</span><span class="sxs-lookup"><span data-stu-id="aee66-105">The <xref:System.Windows.Forms.Timer> component makes such a procedure possible.</span></span>  
  
 <span data-ttu-id="aee66-106">このコンポーネントは、Windows フォームの環境用に設計されています。</span><span class="sxs-lookup"><span data-stu-id="aee66-106">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="aee66-107">サーバー環境に適したタイマーが必要な場合は、「[サーバー ベースのタイマーの概要](/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aee66-107">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="aee66-108"><xref:System.Windows.Forms.Timer> コンポーネントを使用する場合に、いくつかの制限があります。</span><span class="sxs-lookup"><span data-stu-id="aee66-108">There are some limitations when using the <xref:System.Windows.Forms.Timer> component.</span></span> <span data-ttu-id="aee66-109">詳細については、「 [Windows フォーム Timer コンポーネントの Interval プロパティの制限事項](limitations-of-the-timer-component-interval-property.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aee66-109">For more information, see [Limitations of the Windows Forms Timer Component's Interval Property](limitations-of-the-timer-component-interval-property.md).</span></span>  
  
## <a name="to-run-a-procedure-at-set-intervals-with-the-timer-component"></a><span data-ttu-id="aee66-110">Timer コンポーネントで設定された間隔でプロシージャを実行するには</span><span class="sxs-lookup"><span data-stu-id="aee66-110">To run a procedure at set intervals with the Timer component</span></span>  
  
1. <span data-ttu-id="aee66-111"><xref:System.Windows.Forms.Timer> をフォームに追加します。</span><span class="sxs-lookup"><span data-stu-id="aee66-111">Add a <xref:System.Windows.Forms.Timer> to your form.</span></span> <span data-ttu-id="aee66-112">プログラムでこれを実行する方法については、次の例のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="aee66-112">See the following Example section for an illustration of how to do this programmatically.</span></span> <span data-ttu-id="aee66-113">Visual Studio では、フォームへのコンポーネントの追加もサポートされています。</span><span class="sxs-lookup"><span data-stu-id="aee66-113">Visual Studio also has support for adding components to a form.</span></span> <span data-ttu-id="aee66-114">「 [方法: ユーザーインターフェイスを持たないコントロールを Windows フォームに追加](how-to-add-controls-without-a-user-interface-to-windows-forms.md)する」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="aee66-114">Also see [How to: Add Controls Without a User Interface to Windows Forms](how-to-add-controls-without-a-user-interface-to-windows-forms.md).</span></span>  
  
2. <span data-ttu-id="aee66-115">タイマーの <xref:System.Windows.Forms.Timer.Interval%2A> プロパティ (ミリ秒) を設定します。</span><span class="sxs-lookup"><span data-stu-id="aee66-115">Set the <xref:System.Windows.Forms.Timer.Interval%2A> property (in milliseconds) for the timer.</span></span> <span data-ttu-id="aee66-116">このプロパティは、プロシージャを再度実行する前に、経過する時間の長さを決定します。</span><span class="sxs-lookup"><span data-stu-id="aee66-116">This property determines how much time will pass before the procedure is run again.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="aee66-117">タイマー イベントの発生頻度が高いと、イベントに対応するときに使用されるプロセッサ時間も長くなります。</span><span class="sxs-lookup"><span data-stu-id="aee66-117">The more often a timer event occurs, the more processor time is used in responding to the event.</span></span> <span data-ttu-id="aee66-118">これにより、全体的なパフォーマンスが低下します。</span><span class="sxs-lookup"><span data-stu-id="aee66-118">This can slow down overall performance.</span></span> <span data-ttu-id="aee66-119">必要な間隔よりも小さな値を設定しないでください。</span><span class="sxs-lookup"><span data-stu-id="aee66-119">Do not set a smaller interval than you need.</span></span>  
  
3. <span data-ttu-id="aee66-120"><xref:System.Windows.Forms.Timer.Tick> イベント ハンドラーで適切なコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="aee66-120">Write appropriate code in the <xref:System.Windows.Forms.Timer.Tick> event handler.</span></span> <span data-ttu-id="aee66-121">このイベントで記述したコードは、<xref:System.Windows.Forms.Timer.Interval%2A> プロパティで指定した間隔で実行されます。</span><span class="sxs-lookup"><span data-stu-id="aee66-121">The code you write in this event will run at the interval specified in the <xref:System.Windows.Forms.Timer.Interval%2A> property.</span></span>  
  
4. <span data-ttu-id="aee66-122"><xref:System.Windows.Forms.Timer.Enabled%2A> プロパティを `true` に設定して、タイマーを開始します。</span><span class="sxs-lookup"><span data-stu-id="aee66-122">Set the <xref:System.Windows.Forms.Timer.Enabled%2A> property to `true` to start the timer.</span></span> <span data-ttu-id="aee66-123"><xref:System.Windows.Forms.Timer.Tick> イベントの発生が開始され、プロシージャが指定された間隔で実行されます。</span><span class="sxs-lookup"><span data-stu-id="aee66-123">The <xref:System.Windows.Forms.Timer.Tick> event will begin to occur, running your procedure at the set interval.</span></span>  
  
5. <span data-ttu-id="aee66-124">適切なタイミングで <xref:System.Windows.Forms.Timer.Enabled%2A> プロパティを `false` に設定し、プロシージャがもう一度実行されることがないようにします。</span><span class="sxs-lookup"><span data-stu-id="aee66-124">At the appropriate time, set the <xref:System.Windows.Forms.Timer.Enabled%2A> property to `false` to stop the procedure from running again.</span></span> <span data-ttu-id="aee66-125">間隔をに設定する `0` と、タイマーは停止しません。</span><span class="sxs-lookup"><span data-stu-id="aee66-125">Setting the interval to `0` does not cause the timer to stop.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aee66-126">例</span><span class="sxs-lookup"><span data-stu-id="aee66-126">Example</span></span>  

 <span data-ttu-id="aee66-127">この最初のコード例は、1 秒単位で 1 日の時間を追跡します。</span><span class="sxs-lookup"><span data-stu-id="aee66-127">This first code example tracks the time of day in one-second increments.</span></span> <span data-ttu-id="aee66-128">フォーム上で <xref:System.Windows.Forms.Button>、<xref:System.Windows.Forms.Label>、および <xref:System.Windows.Forms.Timer> コンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="aee66-128">It uses a <xref:System.Windows.Forms.Button>, a <xref:System.Windows.Forms.Label>, and a <xref:System.Windows.Forms.Timer> component on a form.</span></span> <span data-ttu-id="aee66-129"><xref:System.Windows.Forms.Timer.Interval%2A> プロパティが 1000 (1 秒に等しい) に設定されます。</span><span class="sxs-lookup"><span data-stu-id="aee66-129">The <xref:System.Windows.Forms.Timer.Interval%2A> property is set to 1000 (equal to one second).</span></span> <span data-ttu-id="aee66-130"><xref:System.Windows.Forms.Timer.Tick> イベントで、ラベルのキャプションが現在の時刻に設定されます。</span><span class="sxs-lookup"><span data-stu-id="aee66-130">In the <xref:System.Windows.Forms.Timer.Tick> event, the label's caption is set to the current time.</span></span> <span data-ttu-id="aee66-131">ボタンをクリックしたときに、<xref:System.Windows.Forms.Timer.Enabled%2A> プロパティが `false` に設定されると、タイマーがラベルのキャプションを更新しなくなります。</span><span class="sxs-lookup"><span data-stu-id="aee66-131">When the button is clicked, the <xref:System.Windows.Forms.Timer.Enabled%2A> property is set to `false`, stopping the timer from updating the label's caption.</span></span> <span data-ttu-id="aee66-132">次のコード例では、という名前のコントロール、という名前のコントロール、 <xref:System.Windows.Forms.Button> `Button1` およびと <xref:System.Windows.Forms.Timer> `Timer1` <xref:System.Windows.Forms.Label> いう名前のコントロール `Label1` を持つフォームが必要です。</span><span class="sxs-lookup"><span data-stu-id="aee66-132">The following code example requires that you have a form with a <xref:System.Windows.Forms.Button> control named `Button1`, a <xref:System.Windows.Forms.Timer> control named `Timer1`, and a <xref:System.Windows.Forms.Label> control named `Label1`.</span></span>  
  
```vb  
Private Sub InitializeTimer()  
   ' Run this procedure in an appropriate event.  
   ' Set to 1 second.  
   Timer1.Interval = 1000  
   ' Enable timer.  
   Timer1.Enabled = True  
   Button1.Text = "Enabled"  
End Sub  
x  
Private Sub Timer1_Tick(ByVal Sender As Object, ByVal e As EventArgs) Handles Timer1.Tick  
' Set the caption to the current time.  
   Label1.Text = DateTime.Now  
End Sub  
  
Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
      If Button1.Text = "Stop" Then  
         Button1.Text = "Start"  
         Timer1.Enabled = False  
      Else  
         Button1.Text = "Stop"  
         Timer1.Enabled = True  
      End If  
End Sub  
```  
  
```csharp  
private void InitializeTimer()  
{  
    // Call this procedure when the application starts.  
    // Set to 1 second.  
    Timer1.Interval = 1000;  
    Timer1.Tick += new EventHandler(Timer1_Tick);  
  
    // Enable timer.  
    Timer1.Enabled = true;  
  
    Button1.Text = "Stop";  
    Button1.Click += new EventHandler(Button1_Click);  
}  
  
private void Timer1_Tick(object Sender, EventArgs e)
{  
   // Set the caption to the current time.  
   Label1.Text = DateTime.Now.ToString();  
}  
  
private void Button1_Click(object sender, EventArgs e)  
{  
  if ( Button1.Text == "Stop" )  
  {  
    Button1.Text = "Start";  
    Timer1.Enabled = false;  
  }  
  else  
  {  
    Button1.Text = "Stop";  
    Timer1.Enabled = true;  
  }  
}  
```  
  
```cpp  
private:  
   void InitializeTimer()  
   {  
      // Run this procedure in an appropriate event.  
      // Set to 1 second.  
      timer1->Interval = 1000;  
      // Enable timer.  
      timer1->Enabled = true;  
      this->timer1->Tick += gcnew System::EventHandler(this,
                               &Form1::timer1_Tick);  
  
      button1->Text = S"Stop";  
      this->button1->Click += gcnew System::EventHandler(this,
                               &Form1::button1_Click);  
   }  
  
   void timer1_Tick(System::Object ^ sender,  
      System::EventArgs ^ e)  
   {  
      // Set the caption to the current time.  
      label1->Text = DateTime::Now.ToString();  
   }  
  
   void button1_Click(System::Object ^ sender,  
      System::EventArgs ^ e)  
   {  
      if ( button1->Text == "Stop" )  
      {  
         button1->Text = "Start";  
         timer1->Enabled = false;  
      }  
      else  
      {  
         button1->Text = "Stop";  
         timer1->Enabled = true;  
      }  
   }  
```  
  
## <a name="example"></a><span data-ttu-id="aee66-133">例</span><span class="sxs-lookup"><span data-stu-id="aee66-133">Example</span></span>  

 <span data-ttu-id="aee66-134">この 2 つ目のコード例は、ループが終了するまでにプロシージャを 600 ミリ秒ごとに実行します。</span><span class="sxs-lookup"><span data-stu-id="aee66-134">This second code example runs a procedure every 600 milliseconds until a loop has finished.</span></span> <span data-ttu-id="aee66-135">次のコード例では、という名前のコントロール、という名前のコントロール、 <xref:System.Windows.Forms.Button> `Button1` およびと <xref:System.Windows.Forms.Timer> `Timer1` <xref:System.Windows.Forms.Label> いう名前のコントロール `Label1` を持つフォームが必要です。</span><span class="sxs-lookup"><span data-stu-id="aee66-135">The following code example requires that you have a form with a <xref:System.Windows.Forms.Button> control named `Button1`, a <xref:System.Windows.Forms.Timer> control named `Timer1`, and a <xref:System.Windows.Forms.Label> control named `Label1`.</span></span>  
  
```vb  
' This variable will be the loop counter.  
Private counter As Integer  
  
Private Sub InitializeTimer()  
   ' Run this procedure in an appropriate event.  
   counter = 0  
   Timer1.Interval = 600  
   Timer1.Enabled = True  
End Sub  
  
Private Sub Timer1_Tick(ByVal sender As Object, ByVal e As System.EventArgs) Handles Timer1.Tick  
   If counter => 10 Then  
      ' Exit loop code.  
      Timer1.Enabled = False  
      counter = 0  
   Else  
      ' Run your procedure here.  
      ' Increment counter.  
      counter = counter + 1  
      Label1.Text = "Procedures Run: " & counter.ToString  
   End If  
End Sub  
```  
  
```csharp  
// This variable will be the loop counter.  
private int counter;  
  
private void InitializeTimer()  
{  
   // Run this procedure in an appropriate event.  
   counter = 0;  
   timer1.Interval = 600;  
   timer1.Enabled = true;  
   // Hook up timer's tick event handler.  
   this.timer1.Tick += new System.EventHandler(this.timer1_Tick);  
}  
  
private void timer1_Tick(object sender, System.EventArgs e)
{  
   if (counter >= 10)
   {  
      // Exit loop code.  
      timer1.Enabled = false;  
      counter = 0;  
   }  
   else  
   {  
      // Run your procedure here.  
      // Increment counter.  
      counter = counter + 1;  
      label1.Text = "Procedures Run: " + counter.ToString();  
      }  
}  
```  
  
```cpp  
private:  
   int counter;  
  
   void InitializeTimer()  
   {  
      // Run this procedure in an appropriate event.  
      counter = 0;  
      timer1->Interval = 600;  
      timer1->Enabled = true;  
      // Hook up timer's tick event handler.  
      this->timer1->Tick += gcnew System::EventHandler(this, &Form1::timer1_Tick);  
   }  
  
   void timer1_Tick(System::Object ^ sender,  
      System::EventArgs ^ e)  
   {  
      if (counter >= 10)
      {  
         // Exit loop code.  
         timer1->Enabled = false;  
         counter = 0;  
      }  
      else  
      {  
         // Run your procedure here.  
         // Increment counter.  
         counter = counter + 1;  
         label1->Text = String::Concat("Procedures Run: ",  
            counter.ToString());  
      }  
   }  
```  
  
## <a name="see-also"></a><span data-ttu-id="aee66-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="aee66-136">See also</span></span>

- <xref:System.Windows.Forms.Timer>
- [<span data-ttu-id="aee66-137">Timer コンポーネント</span><span class="sxs-lookup"><span data-stu-id="aee66-137">Timer Component</span></span>](timer-component-windows-forms.md)
- [<span data-ttu-id="aee66-138">Timer コンポーネントの概要</span><span class="sxs-lookup"><span data-stu-id="aee66-138">Timer Component Overview</span></span>](timer-component-overview-windows-forms.md)
