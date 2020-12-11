---
title: コマンドラインから Windows フォームアプリケーションを作成する
titleSuffix: ''
description: コマンドラインから Windows フォームアプリケーションを作成して実行するための基本的な手順を実行する方法について説明します。
ms.date: 03/14/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, application development from command line
- Windows Forms, getting started
- Windows Forms, creating basic form
ms.assetid: 45ad3f8b-1c26-4c9f-91a9-3bb0759a47a4
ms.openlocfilehash: 3fbec6bce1517e1f3aef52adc3b31facf75d6143
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974353"
---
# <a name="how-to-create-a-windows-forms-application-from-the-command-line"></a><span data-ttu-id="eb89b-103">方法: コマンドラインから Windows フォームアプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="eb89b-103">How to: Create a Windows Forms application from the command line</span></span>

<span data-ttu-id="eb89b-104">次の手順では、コマンドラインから Windows フォーム アプリケーションを作成して実行するために完了する必要のある基本的な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="eb89b-104">The following procedures describe the basic steps that you must complete to create and run a Windows Forms application from the command line.</span></span> <span data-ttu-id="eb89b-105">Visual Studio では、これらの手順に対する広範なサポートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="eb89b-105">There is extensive support for these procedures in Visual Studio.</span></span>  <span data-ttu-id="eb89b-106">「 [チュートリアル: WPF での Windows フォームコントロールのホスト](/dotnet/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf)」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb89b-106">Also see [Walkthrough: Hosting a Windows Forms Control in WPF](/dotnet/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf).</span></span>
  
## <a name="procedure"></a><span data-ttu-id="eb89b-107">手順</span><span class="sxs-lookup"><span data-stu-id="eb89b-107">Procedure</span></span>  
  
#### <a name="to-create-the-form"></a><span data-ttu-id="eb89b-108">フォームを作成するには</span><span class="sxs-lookup"><span data-stu-id="eb89b-108">To create the form</span></span>  
  
1. <span data-ttu-id="eb89b-109">空のコードファイルに、次の `Imports` またはステートメントを入力し `using` ます。</span><span class="sxs-lookup"><span data-stu-id="eb89b-109">In an empty code file, type the following `Imports` or `using` statements:</span></span>  
  
     [!code-csharp[System.Windows.Forms.BasicForm#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.BasicForm#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#2)]  
  
2. <span data-ttu-id="eb89b-110">Form クラスから継承するという名前のクラスを宣言し `Form1` ます。</span><span class="sxs-lookup"><span data-stu-id="eb89b-110">Declare a class named `Form1` that inherits from the Form class:</span></span>
  
     [!code-csharp[System.Windows.Forms.BasicForm#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.BasicForm#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#3)]  
  
3. <span data-ttu-id="eb89b-111">のパラメーターなしのコンストラクターを作成 `Form1` します。</span><span class="sxs-lookup"><span data-stu-id="eb89b-111">Create a parameterless constructor for `Form1`.</span></span>
  
     <span data-ttu-id="eb89b-112">後続の手順で、コンストラクターにさらにコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="eb89b-112">You will add more code to the constructor in a subsequent procedure.</span></span>
  
     [!code-csharp[System.Windows.Forms.BasicForm#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.BasicForm#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#4)]  
  
4. <span data-ttu-id="eb89b-113">`Main` メソッドをクラスに追加します。</span><span class="sxs-lookup"><span data-stu-id="eb89b-113">Add a `Main` method to the class.</span></span>
  
    1. <span data-ttu-id="eb89b-114">を <xref:System.STAThreadAttribute> C# メソッドに適用し `Main` て、Windows フォームアプリケーションがシングルスレッドアパートメントであることを指定します。</span><span class="sxs-lookup"><span data-stu-id="eb89b-114">Apply the <xref:System.STAThreadAttribute> to the C# `Main` method to specify your Windows Forms application is a single-threaded apartment.</span></span> <span data-ttu-id="eb89b-115">(Visual Basic で開発された Windows フォームアプリケーションでは、既定でシングルスレッドアパートメントモデルが使用されるため、Visual Basic では属性は必要ありません)。</span><span class="sxs-lookup"><span data-stu-id="eb89b-115">(The attribute is not necessary in Visual Basic, since Windows forms applications developed with Visual Basic use a single-threaded apartment model by default.)</span></span>  
  
    2. <span data-ttu-id="eb89b-116"><xref:System.Windows.Forms.Application.EnableVisualStyles%2A>を呼び出して、オペレーティングシステムのスタイルをアプリケーションに適用します。</span><span class="sxs-lookup"><span data-stu-id="eb89b-116">Call <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> to apply operating system styles to your application.</span></span>  
  
    3. <span data-ttu-id="eb89b-117">フォームのインスタンスを作成して実行します。</span><span class="sxs-lookup"><span data-stu-id="eb89b-117">Create an instance of the form and run it.</span></span>  
  
     [!code-csharp[System.Windows.Forms.BasicForm#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.BasicForm#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#5)]  
  
#### <a name="to-compile-and-run-the-application"></a><span data-ttu-id="eb89b-118">アプリケーションをコンパイルして実行するには</span><span class="sxs-lookup"><span data-stu-id="eb89b-118">To compile and run the application</span></span>  
  
1. <span data-ttu-id="eb89b-119">.NET Framework コマンド プロンプトで、`Form1` クラスを作成したディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="eb89b-119">At the .NET Framework command prompt, navigate to the directory you created the `Form1` class.</span></span>  
  
2. <span data-ttu-id="eb89b-120">フォームをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="eb89b-120">Compile the form.</span></span>  
  
    - <span data-ttu-id="eb89b-121">C# を使用する場合は、次のように入力します。 `csc form1.cs`</span><span class="sxs-lookup"><span data-stu-id="eb89b-121">If you are using C#, type: `csc form1.cs`</span></span>  
  
         `-or-`  
  
    - <span data-ttu-id="eb89b-122">Visual Basic を使用している場合は、次のように入力します。 `vbc form1.vb`</span><span class="sxs-lookup"><span data-stu-id="eb89b-122">If you are using Visual Basic, type: `vbc form1.vb`</span></span>  
  
3. <span data-ttu-id="eb89b-123">コマンド プロンプトに `Form1.exe` を入力します。</span><span class="sxs-lookup"><span data-stu-id="eb89b-123">At the command prompt, type: `Form1.exe`</span></span>  
  
## <a name="adding-a-control-and-handling-an-event"></a><span data-ttu-id="eb89b-124">コントロールの追加とイベントの処理</span><span class="sxs-lookup"><span data-stu-id="eb89b-124">Adding a control and handling an event</span></span>

<span data-ttu-id="eb89b-125">前の手順は、コンパイルして実行する基本的な Windows フォームを作成する方法を示しました。</span><span class="sxs-lookup"><span data-stu-id="eb89b-125">The previous procedure steps demonstrated how to just create a basic Windows Form that compiles and runs.</span></span> <span data-ttu-id="eb89b-126">次の手順では、コントロールを作成してフォームに追加し、コントロールのイベントを処理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="eb89b-126">The next procedure will show you how to create and add a control to the form, and handle an event for the control.</span></span> <span data-ttu-id="eb89b-127">Windows フォームに追加できるコントロールの詳細については、「 [コントロールの Windows フォーム](./controls/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb89b-127">For more information about the controls you can add to Windows Forms, see [Windows Forms Controls](./controls/index.md).</span></span>
  
 <span data-ttu-id="eb89b-128">Windows フォーム アプリケーションを作成する方法を理解するだけでなく、イベント ベースのプログラミングとユーザー入力を処理する方法を理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb89b-128">In addition to understanding how to create Windows Forms applications, you should understand event-based programming and how to handle user input.</span></span> <span data-ttu-id="eb89b-129">詳細については、「 [Windows フォームでのイベントハンドラーの作成](creating-event-handlers-in-windows-forms.md)」および「[ユーザー入力の処理](./controls/handling-user-input.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb89b-129">For more information, see [Creating Event Handlers in Windows Forms](creating-event-handlers-in-windows-forms.md), and [Handling User Input](./controls/handling-user-input.md)</span></span>  
  
#### <a name="to-declare-a-button-control-and-handle-its-click-event"></a><span data-ttu-id="eb89b-130">ボタン コントロールを宣言して、クリック イベントを処理するには</span><span class="sxs-lookup"><span data-stu-id="eb89b-130">To declare a button control and handle its click event</span></span>  
  
1. <span data-ttu-id="eb89b-131">`button1` という名前のボタン コントロールを宣言します。</span><span class="sxs-lookup"><span data-stu-id="eb89b-131">Declare a button control named `button1`.</span></span>  
  
2. <span data-ttu-id="eb89b-132">コンストラクターでボタンを作成し、<xref:System.Windows.Forms.Control.Size%2A>、<xref:System.Windows.Forms.Control.Location%2A>、および <xref:System.Windows.Forms.Control.Text%2A> の各プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="eb89b-132">In the constructor, create the button and set its <xref:System.Windows.Forms.Control.Size%2A>, <xref:System.Windows.Forms.Control.Location%2A> and <xref:System.Windows.Forms.Control.Text%2A> properties.</span></span>  
  
3. <span data-ttu-id="eb89b-133">フォームにボタンを追加します。</span><span class="sxs-lookup"><span data-stu-id="eb89b-133">Add the button to the form.</span></span>  
  
     <span data-ttu-id="eb89b-134">次のコード例は、ボタンコントロールを宣言する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="eb89b-134">The following code example demonstrates how to declare the button control:</span></span>
  
     [!code-csharp[System.Windows.Forms.FormWithButton#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.FormWithButton#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#2)]  
  
4. <span data-ttu-id="eb89b-135">ボタンで <xref:System.Windows.Forms.Control.Click> イベントを処理するメソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="eb89b-135">Create a method to handle the <xref:System.Windows.Forms.Control.Click> event for the button.</span></span>  
  
5. <span data-ttu-id="eb89b-136">クリック イベント ハンドラーで、メッセージ "Hello World" と共に <xref:System.Windows.Forms.MessageBox> を表示します。</span><span class="sxs-lookup"><span data-stu-id="eb89b-136">In the click event handler, display a <xref:System.Windows.Forms.MessageBox> with the message, "Hello World".</span></span>  
  
     <span data-ttu-id="eb89b-137">次のコード例は、ボタンコントロールの click イベントを処理する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="eb89b-137">The following code example demonstrates how to handle the button control's click event:</span></span>
  
     [!code-csharp[System.Windows.Forms.FormWithButton#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.FormWithButton#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#3)]  
  
6. <span data-ttu-id="eb89b-138"><xref:System.Windows.Forms.Control.Click> イベントを作成したメソッドに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="eb89b-138">Associate the <xref:System.Windows.Forms.Control.Click> event with the method you created.</span></span>  
  
     <span data-ttu-id="eb89b-139">次のコード例は、イベントをメソッドに関連付ける方法を示します。</span><span class="sxs-lookup"><span data-stu-id="eb89b-139">The following code example demonstrates how to associate the event with the method.</span></span>  
  
     [!code-csharp[System.Windows.Forms.FormWithButton#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.FormWithButton#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#4)]  
  
7. <span data-ttu-id="eb89b-140">前の手順で説明したように、アプリケーションをコンパイルして実行します。</span><span class="sxs-lookup"><span data-stu-id="eb89b-140">Compile and run the application as described in the previous procedure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb89b-141">例</span><span class="sxs-lookup"><span data-stu-id="eb89b-141">Example</span></span>  

<span data-ttu-id="eb89b-142">次のコード例は、前の手順の完全な例です。</span><span class="sxs-lookup"><span data-stu-id="eb89b-142">The following code example is the complete example from the previous procedures:</span></span>
  
 [!code-csharp[System.Windows.Forms.FormWithButton#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.FormWithButton#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="eb89b-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="eb89b-143">See also</span></span>

- <xref:System.Windows.Forms.Form>
- <xref:System.Windows.Forms.Control>
- [<span data-ttu-id="eb89b-144">Windows フォームの表示形式の変更</span><span class="sxs-lookup"><span data-stu-id="eb89b-144">Changing the Appearance of Windows Forms</span></span>](changing-the-appearance-of-windows-forms.md)
- [<span data-ttu-id="eb89b-145">Windows フォーム アプリケーションの拡張</span><span class="sxs-lookup"><span data-stu-id="eb89b-145">Enhancing Windows Forms Applications</span></span>](./advanced/index.md)
- [<span data-ttu-id="eb89b-146">Windows フォームでのはじめに</span><span class="sxs-lookup"><span data-stu-id="eb89b-146">Getting Started with Windows Forms</span></span>](getting-started-with-windows-forms.md)
