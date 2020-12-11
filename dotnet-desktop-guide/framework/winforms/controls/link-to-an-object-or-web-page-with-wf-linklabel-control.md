---
title: LinkLabel コントロールを使用してオブジェクトまたは Web ページにリンクする
description: Windows フォーム LinkLabel コントロールを使用して、オブジェクトまたは web ページへの Web スタイルのリンクを作成する方法について説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], LinkLabel control
- Windows Forms, linking to objects
- Web page link control
- linking [Windows Forms], to other forms
- Windows Forms, linking to Web pages
- links [Windows Forms], to other forms
- LinkLabel control [Windows Forms], linking to object or Web page
- LinkLabel control [Windows Forms], examples
ms.assetid: 6c91c975-3cb7-4504-82f0-fc6255f8fb85
ms.openlocfilehash: a5fb1c03e9a8d82fe77f4133ba04c42114787d23
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980643"
---
# <a name="how-to-link-to-an-object-or-web-page-with-the-windows-forms-linklabel-control"></a><span data-ttu-id="6482a-103">方法: Windows フォーム LinkLabel コントロールでオブジェクトまたは Web ページにリンクする</span><span class="sxs-lookup"><span data-stu-id="6482a-103">How to: Link to an Object or Web Page with the Windows Forms LinkLabel Control</span></span>

<span data-ttu-id="6482a-104">Windows フォーム <xref:System.Windows.Forms.LinkLabel> コントロールを使用すると、フォーム上に Web スタイルのリンクを作成できます。</span><span class="sxs-lookup"><span data-stu-id="6482a-104">The Windows Forms <xref:System.Windows.Forms.LinkLabel> control allows you to create Web-style links on your form.</span></span> <span data-ttu-id="6482a-105">リンクをクリックすると、その色を変更してリンクがアクセスされたことを示すことができます。</span><span class="sxs-lookup"><span data-stu-id="6482a-105">When the link is clicked, you can change its color to indicate the link has been visited.</span></span> <span data-ttu-id="6482a-106">色の変更の詳細については、「 [方法: Windows フォーム LinkLabel コントロールの外観を変更する](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6482a-106">For more information on changing the color, see [How to: Change the Appearance of the Windows Forms LinkLabel Control](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md).</span></span>

## <a name="linking-to-another-form"></a><span data-ttu-id="6482a-107">リンク (別のフォームに)</span><span class="sxs-lookup"><span data-stu-id="6482a-107">Linking to Another Form</span></span>

#### <a name="to-link-to-another-form-with-a-linklabel-control"></a><span data-ttu-id="6482a-108">LinkLabel コントロールを使用して別のフォームにリンクするには</span><span class="sxs-lookup"><span data-stu-id="6482a-108">To link to another form with a LinkLabel control</span></span>

1. <span data-ttu-id="6482a-109">プロパティを <xref:System.Windows.Forms.LinkLabel.Text%2A> 適切なキャプションに設定します。</span><span class="sxs-lookup"><span data-stu-id="6482a-109">Set the <xref:System.Windows.Forms.LinkLabel.Text%2A> property to an appropriate caption.</span></span>

2. <span data-ttu-id="6482a-110">プロパティを設定し <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> て、キャプションのどの部分がリンクとして示されるかを決定します。</span><span class="sxs-lookup"><span data-stu-id="6482a-110">Set the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property to determine which part of the caption will be indicated as a link.</span></span> <span data-ttu-id="6482a-111">どのように表示されるかは、リンクラベルの外観に関連するプロパティによって異なります。</span><span class="sxs-lookup"><span data-stu-id="6482a-111">How it is indicated depends on the appearance-related properties of the link label.</span></span> <span data-ttu-id="6482a-112"><xref:System.Windows.Forms.LinkLabel.LinkArea%2A>値は、 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 2 つの数値、開始文字の位置、および文字数を含むオブジェクトによって表されます。</span><span class="sxs-lookup"><span data-stu-id="6482a-112">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> value is represented by a <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> object containing two numbers, the starting character position and the number of characters.</span></span> <span data-ttu-id="6482a-113">プロパティは、 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 次のような方法でプロパティウィンドウまたはコードで設定できます。</span><span class="sxs-lookup"><span data-stu-id="6482a-113">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property can be set in the Properties window or in code in a manner similar to the following:</span></span>

    ```vb
    ' In this code example, the link area has been set to begin
    ' at the first character and extend for eight characters.
    ' You may need to modify this based on the text entered in Step 1.
    LinkLabel1.LinkArea = New LinkArea(0, 8)
    ```

    ```csharp
    // In this code example, the link area has been set to begin
    // at the first character and extend for eight characters.
    // You may need to modify this based on the text entered in Step 1.
    linkLabel1.LinkArea = new LinkArea(0,8);
    ```

    ```cpp
    // In this code example, the link area has been set to begin
    // at the first character and extend for eight characters.
    // You may need to modify this based on the text entered in Step 1.
    linkLabel1->LinkArea = LinkArea(0,8);
    ```

3. <span data-ttu-id="6482a-114"><xref:System.Windows.Forms.LinkLabel.LinkClicked>イベントハンドラーで、メソッドを呼び出し <xref:System.Windows.Forms.Form.Show%2A> て、プロジェクト内の別のフォームを開き、 <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> プロパティをに設定し `true` ます。</span><span class="sxs-lookup"><span data-stu-id="6482a-114">In the <xref:System.Windows.Forms.LinkLabel.LinkClicked> event handler, invoke the <xref:System.Windows.Forms.Form.Show%2A> method to open another form in the project, and set the <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> property to `true`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6482a-115">クラスのインスタンスは、 <xref:System.Windows.Forms.LinkLabelLinkClickedEventArgs> クリックされたコントロールへの参照を保持して <xref:System.Windows.Forms.LinkLabel> いるため、オブジェクトをキャストする必要はありません `sender` 。</span><span class="sxs-lookup"><span data-stu-id="6482a-115">An instance of the <xref:System.Windows.Forms.LinkLabelLinkClickedEventArgs> class carries a reference to the <xref:System.Windows.Forms.LinkLabel> control that was clicked, so there is no need to cast the `sender` object.</span></span>

    ```vb
    Protected Sub LinkLabel1_LinkClicked(ByVal Sender As System.Object, _
       ByVal e As System.Windows.Forms.LinkLabelLinkClickedEventArgs) _
       Handles LinkLabel1.LinkClicked
       ' Show another form.
       Dim f2 As New Form()
       f2.Show
       LinkLabel1.LinkVisited = True
    End Sub
    ```

    ```csharp
    protected void linkLabel1_LinkClicked(object sender, System. Windows.Forms.LinkLabelLinkClickedEventArgs e)
    {
       // Show another form.
       Form f2 = new Form();
       f2.Show();
       linkLabel1.LinkVisited = true;
    }
    ```

    ```cpp
    private:
       void linkLabel1_LinkClicked(System::Object ^  sender,
          System::Windows::Forms::LinkLabelLinkClickedEventArgs ^  e)
       {
          // Show another form.
          Form ^ f2 = new Form();
          f2->Show();
          linkLabel1->LinkVisited = true;
       }
    ```

## <a name="linking-to-a-web-page"></a><span data-ttu-id="6482a-116">Web ページへのリンク</span><span class="sxs-lookup"><span data-stu-id="6482a-116">Linking to a Web Page</span></span>

<span data-ttu-id="6482a-117"><xref:System.Windows.Forms.LinkLabel>コントロールを使用して、既定のブラウザーで Web ページを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="6482a-117">The <xref:System.Windows.Forms.LinkLabel> control can also be used to display a Web page with the default browser.</span></span>

#### <a name="to-start-internet-explorer-and-link-to-a-web-page-with-a-linklabel-control"></a><span data-ttu-id="6482a-118">Internet Explorer を起動し、LinkLabel コントロールを使用して Web ページにリンクするには</span><span class="sxs-lookup"><span data-stu-id="6482a-118">To start Internet Explorer and link to a Web page with a LinkLabel control</span></span>

1. <span data-ttu-id="6482a-119">プロパティを <xref:System.Windows.Forms.LinkLabel.Text%2A> 適切なキャプションに設定します。</span><span class="sxs-lookup"><span data-stu-id="6482a-119">Set the <xref:System.Windows.Forms.LinkLabel.Text%2A> property to an appropriate caption.</span></span>

2. <span data-ttu-id="6482a-120">プロパティを設定し <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> て、キャプションのどの部分がリンクとして示されるかを決定します。</span><span class="sxs-lookup"><span data-stu-id="6482a-120">Set the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property to determine which part of the caption will be indicated as a link.</span></span>

3. <span data-ttu-id="6482a-121">イベントハンドラーでは、 <xref:System.Windows.Forms.LinkLabel.LinkClicked> 例外処理ブロックの途中で、2番目のプロシージャを呼び出します。このプロシージャは、プロパティをに設定し、メソッドを使用して <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> `true` <xref:System.Diagnostics.Process.Start%2A> URL で既定のブラウザーを起動します。</span><span class="sxs-lookup"><span data-stu-id="6482a-121">In the <xref:System.Windows.Forms.LinkLabel.LinkClicked> event handler, in the midst of an exception-handling block, call a second procedure that sets the <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> property to `true` and uses the <xref:System.Diagnostics.Process.Start%2A> method to start the default browser with a URL.</span></span> <span data-ttu-id="6482a-122">メソッドを使用するには、 <xref:System.Diagnostics.Process.Start%2A> 名前空間への参照を追加する必要があり <xref:System.Diagnostics?displayProperty=nameWithType> ます。</span><span class="sxs-lookup"><span data-stu-id="6482a-122">To use the <xref:System.Diagnostics.Process.Start%2A> method you need to add a reference to the <xref:System.Diagnostics?displayProperty=nameWithType> namespace.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="6482a-123">以下のコードを部分信頼環境 (共有ドライブなど) で実行すると、メソッドが呼び出されたときに JIT コンパイラが失敗し `VisitLink` ます。</span><span class="sxs-lookup"><span data-stu-id="6482a-123">If the code below is run in a partial-trust environment (such as on a shared drive), the JIT compiler fails when the `VisitLink` method is called.</span></span> <span data-ttu-id="6482a-124">`System.Diagnostics.Process.Start`ステートメントにより、リンク確認要求が失敗します。</span><span class="sxs-lookup"><span data-stu-id="6482a-124">The `System.Diagnostics.Process.Start` statement causes a link demand that fails.</span></span> <span data-ttu-id="6482a-125">メソッドが呼び出されたときに例外をキャッチすることにより、 `VisitLink` 次のコードは、JIT コンパイラが失敗した場合にエラーが適切に処理されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6482a-125">By catching the exception when the `VisitLink` method is called, the code below ensures that if the JIT compiler fails, the error is handled gracefully.</span></span>

    ```vb
    Private Sub LinkLabel1_LinkClicked(ByVal sender As System.Object, _
       ByVal e As System.Windows.Forms.LinkLabelLinkClickedEventArgs) _
       Handles LinkLabel1.LinkClicked
       Try
          VisitLink()
       Catch ex As Exception
          ' The error message
          MessageBox.Show("Unable to open link that was clicked.")
       End Try
    End Sub

    Sub VisitLink()
       ' Change the color of the link text by setting LinkVisited
       ' to True.
       LinkLabel1.LinkVisited = True
       ' Call the Process.Start method to open the default browser
       ' with a URL:
       System.Diagnostics.Process.Start("http://www.microsoft.com")
    End Sub
    ```

    ```csharp
    private void linkLabel1_LinkClicked(object sender, System.Windows.Forms.LinkLabelLinkClickedEventArgs e)
    {
       try
       {
          VisitLink();
       }
       catch (Exception ex )
       {
          MessageBox.Show("Unable to open link that was clicked.");
       }
    }

    private void VisitLink()
    {
       // Change the color of the link text by setting LinkVisited
       // to true.
       linkLabel1.LinkVisited = true;
       //Call the Process.Start method to open the default browser
       //with a URL:
       System.Diagnostics.Process.Start("http://www.microsoft.com");
    }
    ```

    ```cpp
    private:
       void linkLabel1_LinkClicked(System::Object ^  sender,
          System::Windows::Forms::LinkLabelLinkClickedEventArgs ^  e)
       {
          try
          {
             VisitLink();
          }
          catch (Exception ^ ex)
          {
             MessageBox::Show("Unable to open link that was clicked.");
          }
       }
    private:
       void VisitLink()
       {
          // Change the color of the link text by setting LinkVisited
          // to true.
          linkLabel1->LinkVisited = true;
          // Call the Process.Start method to open the default browser
          // with a URL:
          System::Diagnostics::Process::Start("http://www.microsoft.com");
       }
    ```

## <a name="see-also"></a><span data-ttu-id="6482a-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="6482a-126">See also</span></span>

- <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>
- [<span data-ttu-id="6482a-127">LinkLabel コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="6482a-127">LinkLabel Control Overview</span></span>](linklabel-control-overview-windows-forms.md)
- [<span data-ttu-id="6482a-128">方法: Windows フォーム LinkLabel コントロールの表示形式を変更する</span><span class="sxs-lookup"><span data-stu-id="6482a-128">How to: Change the Appearance of the Windows Forms LinkLabel Control</span></span>](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
- [<span data-ttu-id="6482a-129">LinkLabel コントロール</span><span class="sxs-lookup"><span data-stu-id="6482a-129">LinkLabel Control</span></span>](linklabel-control-windows-forms.md)
