---
title: TextBox コントロールを使用してパスワードテキストボックスを作成する
description: ユーザーが文字列を入力したときにプレースホルダー文字を表示する Windows フォームテキストを指定する方法について説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], entering passwords
- password boxes [Windows Forms], creating
- PasswordChar property in text boxes
- passwords [Windows Forms], input mask
- passwords [Windows Forms], password text box
ms.assetid: d105d6b9-3d50-44cd-80d8-2c0e2f486727
ms.openlocfilehash: 6d7e61eefa44ce3152aa77e3922bde471a4aeaf3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980915"
---
# <a name="how-to-create-a-password-text-box-with-the-windows-forms-textbox-control"></a><span data-ttu-id="a55b8-103">方法: Windows フォームの TextBox コントロールを使用してパスワード テキスト ボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="a55b8-103">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>

<span data-ttu-id="a55b8-104">パスワードボックスは、ユーザーが文字列を入力したときにプレースホルダー文字を表示する Windows フォームテキストボックスです。</span><span class="sxs-lookup"><span data-stu-id="a55b8-104">A password box is a Windows Forms text box that displays placeholder characters while a user types a string.</span></span>

### <a name="to-create-a-password-text-box"></a><span data-ttu-id="a55b8-105">パスワードテキストボックスを作成するには</span><span class="sxs-lookup"><span data-stu-id="a55b8-105">To create a password text box</span></span>

1. <span data-ttu-id="a55b8-106"><xref:System.Windows.Forms.TextBox.PasswordChar%2A>コントロールのプロパティ <xref:System.Windows.Forms.TextBox> を特定の文字に設定します。</span><span class="sxs-lookup"><span data-stu-id="a55b8-106">Set the <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property of the <xref:System.Windows.Forms.TextBox> control to a specific character.</span></span>

    <span data-ttu-id="a55b8-107">プロパティは、 <xref:System.Windows.Forms.TextBox.PasswordChar%2A> テキストボックスに表示される文字を指定します。</span><span class="sxs-lookup"><span data-stu-id="a55b8-107">The <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property specifies the character displayed in the text box.</span></span> <span data-ttu-id="a55b8-108">たとえば、[パスワード] ボックスにアスタリスクを表示する場合は、プロパティウィンドウのプロパティに \* を指定し <xref:System.Windows.Forms.TextBox.PasswordChar%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="a55b8-108">For example, if you want asterisks displayed in the password box, specify \* for the <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property in the Properties window.</span></span> <span data-ttu-id="a55b8-109">その後、ユーザーがテキストボックスに入力した文字に関係なく、アスタリスクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a55b8-109">Then, regardless of what character a user types in the text box, an asterisk is displayed.</span></span>

2. <span data-ttu-id="a55b8-110">Optionalプロパティを設定 <xref:System.Windows.Forms.TextBoxBase.MaxLength%2A> します。</span><span class="sxs-lookup"><span data-stu-id="a55b8-110">(Optional) Set the <xref:System.Windows.Forms.TextBoxBase.MaxLength%2A> property.</span></span> <span data-ttu-id="a55b8-111">プロパティは、テキストボックスに入力できる文字数を決定します。</span><span class="sxs-lookup"><span data-stu-id="a55b8-111">The property determines how many characters can be typed in the text box.</span></span> <span data-ttu-id="a55b8-112">最大長を超えた場合、システムはビープ音を出力し、テキストボックスはそれ以上文字を受け付けません。</span><span class="sxs-lookup"><span data-stu-id="a55b8-112">If the maximum length is exceeded, the system emits a beep and the text box does not accept any more characters.</span></span> <span data-ttu-id="a55b8-113">パスワードを推測しようとしているハッカーにパスワードの最大長が使用される可能性があるため、この操作は行わないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a55b8-113">Note that you may not wish to do this as the maximum length of a password may be of use to hackers who are trying to guess the password.</span></span>

    <span data-ttu-id="a55b8-114">次のコード例は、14文字までの文字列を受け取り、文字列の代わりにアスタリスクを表示するテキストボックスを初期化する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a55b8-114">The following code example shows how to initialize a text box that will accept a string up to 14 characters long and display asterisks in place of the string.</span></span> <span data-ttu-id="a55b8-115">`InitializeMyControl`プロシージャは自動的には実行されません。このプロシージャを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="a55b8-115">The `InitializeMyControl` procedure will not execute automatically; it must be called.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="a55b8-116">テキストボックスでプロパティを使用すると、他のユーザーが入力したユーザーが <xref:System.Windows.Forms.TextBox.PasswordChar%2A> ユーザーのパスワードを確認できないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="a55b8-116">Using the <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property on a text box can help ensure that other people will not be able to determine a user's password if they observe the user entering it.</span></span> <span data-ttu-id="a55b8-117">このセキュリティ対策では、アプリケーションロジックによって発生する可能性のあるパスワードの格納や転送については説明しません。</span><span class="sxs-lookup"><span data-stu-id="a55b8-117">This security measure does not cover any sort of storage or transmission of the password that can occur due to your application logic.</span></span> <span data-ttu-id="a55b8-118">入力したテキストは暗号化されていないため、他の機密データと同様に扱う必要があります。</span><span class="sxs-lookup"><span data-stu-id="a55b8-118">Because the text entered is not encrypted in any way, you should treat it as you would any other confidential data.</span></span> <span data-ttu-id="a55b8-119">このように表示されない場合でも、パスワードはまだプレーンテキスト文字列として扱われます (追加のセキュリティ対策を実装している場合を除く)。</span><span class="sxs-lookup"><span data-stu-id="a55b8-119">Even though it does not appear as such, the password is still being treated as a plain-text string (unless you have implemented some additional security measure).</span></span>

    ```vb
    Private Sub InitializeMyControl()
       ' Set to no text.
       TextBox1.Text = ""
       ' The password character is an asterisk.
       TextBox1.PasswordChar = "*"
       ' The control will allow no more than 14 characters.
       TextBox1.MaxLength = 14
    End Sub
    ```

    ```csharp
    private void InitializeMyControl()
    {
       // Set to no text.
       textBox1.Text = "";
       // The password character is an asterisk.
       textBox1.PasswordChar = '*';
       // The control will allow no more than 14 characters.
       textBox1.MaxLength = 14;
    }
    ```

    ```cpp
    private:
       void InitializeMyControl()
       {
          // Set to no text.
          textBox1->Text = "";
          // The password character is an asterisk.
          textBox1->PasswordChar = '*';
          // The control will allow no more than 14 characters.
          textBox1->MaxLength = 14;
       }
    ```

## <a name="see-also"></a><span data-ttu-id="a55b8-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="a55b8-120">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="a55b8-121">TextBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="a55b8-121">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="a55b8-122">方法: Windows フォーム TextBox コントロールでのカーソル位置を制御する</span><span class="sxs-lookup"><span data-stu-id="a55b8-122">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="a55b8-123">方法: 読み取り専用テキスト ボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="a55b8-123">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="a55b8-124">方法: 文字列に引用符を挿入する</span><span class="sxs-lookup"><span data-stu-id="a55b8-124">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="a55b8-125">方法: Windows フォーム TextBox コントロールでテキストを選択する</span><span class="sxs-lookup"><span data-stu-id="a55b8-125">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="a55b8-126">方法: Windows フォーム TextBox コントロールで複数行を表示する</span><span class="sxs-lookup"><span data-stu-id="a55b8-126">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="a55b8-127">TextBox コントロール</span><span class="sxs-lookup"><span data-stu-id="a55b8-127">TextBox Control</span></span>](textbox-control-windows-forms.md)
