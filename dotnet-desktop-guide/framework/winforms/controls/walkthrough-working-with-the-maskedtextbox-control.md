---
title: 'チュートリアル: MaskedTextBox コントロールの使用'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- input [Windows Forms], controlling to ensure validity
- MaskedTextBox control [Windows Forms], walkthroughs
- MaskedTextBox control [Windows Forms], validation
- user input [Windows Forms], controlling
- text [Windows Forms], controls for input
ms.assetid: df60565e-5447-4110-92a6-be1f6ff5faa3
ms.openlocfilehash: db32b3ec88a07747ea3e286af9f04edce3f1ba3b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982688"
---
# <a name="walkthrough-working-with-the-maskedtextbox-control"></a><span data-ttu-id="a2b77-102">チュートリアル: MaskedTextBox コントロールの使用</span><span class="sxs-lookup"><span data-stu-id="a2b77-102">Walkthrough: Working with the MaskedTextBox Control</span></span>
<span data-ttu-id="a2b77-103">このチュートリアルでは、以下のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="a2b77-103">Tasks illustrated in this walkthrough include:</span></span>  
  
- <span data-ttu-id="a2b77-104">コントロールの初期化 <xref:System.Windows.Forms.MaskedTextBox></span><span class="sxs-lookup"><span data-stu-id="a2b77-104">Initializing the <xref:System.Windows.Forms.MaskedTextBox> control</span></span>  
  
- <span data-ttu-id="a2b77-105"><xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected>文字がマスクに準拠していない場合に、イベントハンドラーを使用してユーザーに警告する</span><span class="sxs-lookup"><span data-stu-id="a2b77-105">Using the <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> event handler to alert the user when a character does not conform to the mask</span></span>  
  
- <span data-ttu-id="a2b77-106">型をプロパティに割り当て <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> 、イベントハンドラーを使用して、コミットしようとして <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> いる値が型に対して有効でない場合にユーザーに警告します。</span><span class="sxs-lookup"><span data-stu-id="a2b77-106">Assigning a type to the <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> property and using the <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> event handler to alert the user when the value they're attempting to commit is not valid for the type</span></span>  
  
## <a name="creating-the-project-and-adding-a-control"></a><span data-ttu-id="a2b77-107">プロジェクトを作成し、コントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="a2b77-107">Creating the Project and Adding a Control</span></span>  
  
#### <a name="to-add-a-maskedtextbox-control-to-your-form"></a><span data-ttu-id="a2b77-108">MaskedTextBox コントロールをフォームに追加するには</span><span class="sxs-lookup"><span data-stu-id="a2b77-108">To add a MaskedTextBox control to your form</span></span>  
  
1. <span data-ttu-id="a2b77-109">コントロールを配置するフォームを開き <xref:System.Windows.Forms.MaskedTextBox> ます。</span><span class="sxs-lookup"><span data-stu-id="a2b77-109">Open the form on which you want to place the <xref:System.Windows.Forms.MaskedTextBox> control.</span></span>  
  
2. <span data-ttu-id="a2b77-110">コントロールを <xref:System.Windows.Forms.MaskedTextBox> [ **ツールボックス** ] からフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="a2b77-110">Drag a <xref:System.Windows.Forms.MaskedTextBox> control from the **Toolbox** to your form.</span></span>  
  
3. <span data-ttu-id="a2b77-111">コントロールを右クリックし、[ **プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a2b77-111">Right-click the control and choose **Properties**.</span></span> <span data-ttu-id="a2b77-112">[ **プロパティ** ] ウィンドウで、 **Mask** プロパティを選択し、プロパティ名の横にある [.. **.** ] (省略記号) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a2b77-112">In the **Properties** window, select the **Mask** property and click the **...** (ellipsis) button next to the property name.</span></span>  
  
4. <span data-ttu-id="a2b77-113">[ **定型入力** ] ダイアログボックスで、 **短い日付** のマスクを選択し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a2b77-113">In the **Input Mask** dialog box, select the **Short Date** mask and click **OK**.</span></span>  
  
5. <span data-ttu-id="a2b77-114">[ **プロパティ** ] ウィンドウで、 <xref:System.Windows.Forms.MaskedTextBox.BeepOnError%2A> プロパティをに設定し `true` ます。</span><span class="sxs-lookup"><span data-stu-id="a2b77-114">In the **Properties** window set the <xref:System.Windows.Forms.MaskedTextBox.BeepOnError%2A> property to `true`.</span></span> <span data-ttu-id="a2b77-115">このプロパティにより、ユーザーがマスク定義に違反する文字を入力しようとするたびに、短いビープ音が鳴ります。</span><span class="sxs-lookup"><span data-stu-id="a2b77-115">This property causes a short beep to sound every time the user attempts to input a character that violates the mask definition.</span></span>  
  
 <span data-ttu-id="a2b77-116">Mask プロパティでサポートされる文字の概要については、プロパティの「解説」を参照してください <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> 。</span><span class="sxs-lookup"><span data-stu-id="a2b77-116">For a summary of the characters that the Mask property supports, see the Remarks section of the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
## <a name="alert-the-user-to-input-errors"></a><span data-ttu-id="a2b77-117">エラーを入力するようユーザーに警告します</span><span class="sxs-lookup"><span data-stu-id="a2b77-117">Alert the User to Input Errors</span></span>  
  
#### <a name="add-a-balloon-tip-for-rejected-mask-input"></a><span data-ttu-id="a2b77-118">拒否するマスク入力にバルーンヒントを追加する</span><span class="sxs-lookup"><span data-stu-id="a2b77-118">Add a balloon tip for rejected mask input</span></span>  
  
1. <span data-ttu-id="a2b77-119">**ツールボックス** に戻り、を <xref:System.Windows.Forms.ToolTip> フォームに追加します。</span><span class="sxs-lookup"><span data-stu-id="a2b77-119">Return to the **Toolbox** and add a <xref:System.Windows.Forms.ToolTip> to your form.</span></span>  
  
2. <span data-ttu-id="a2b77-120">入力エラーが発生したときにを発生させるイベントのイベントハンドラーを作成し <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> <xref:System.Windows.Forms.ToolTip> ます。</span><span class="sxs-lookup"><span data-stu-id="a2b77-120">Create an event handler for the <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> event that raises the <xref:System.Windows.Forms.ToolTip> when an input error occurs.</span></span> <span data-ttu-id="a2b77-121">バルーンヒントは、5秒間、またはユーザーがクリックするまで表示されたままになります。</span><span class="sxs-lookup"><span data-stu-id="a2b77-121">The balloon tip remains visible for five seconds, or until the user clicks it.</span></span>  
  
    ```csharp  
    public void Form1_Load(Object sender, EventArgs e)
    {  
        ... // Other initialization code  
        maskedTextBox1.Mask = "00/00/0000";  
        maskedTextBox1.MaskInputRejected += new MaskInputRejectedEventHandler(maskedTextBox1_MaskInputRejected)  
    }  
  
    void maskedTextBox1_MaskInputRejected(object sender, MaskInputRejectedEventArgs e)  
    {  
        toolTip1.ToolTipTitle = "Invalid Input";  
        toolTip1.Show("We're sorry, but only digits (0-9) are allowed in dates.", maskedTextBox1, maskedTextBox1.Location, 5000);  
    }  
    ```  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MyBase.Load  
        Me.ToolTip1.IsBalloon = True  
        Me.MaskedTextBox1.Mask = "00/00/0000"  
    End Sub  
  
    Private Sub MaskedTextBox1_MaskInputRejected(sender as Object, e as MaskInputRejectedEventArgs) Handles MaskedTextBox1.MaskInputRejected  
        ToolTip1.ToolTipTitle = "Invalid Input"  
        ToolTip1.Show("We're sorry, but only digits (0-9) are allowed in dates.", MaskedTextBox1, 5000)  
    End Sub  
    ```  
  
## <a name="alert-the-user-to-a-type-that-is-not-valid"></a><span data-ttu-id="a2b77-122">無効な種類のユーザーに警告します</span><span class="sxs-lookup"><span data-stu-id="a2b77-122">Alert the User to a Type that Is Not Valid</span></span>  
  
#### <a name="add-a-balloon-tip-for-invalid-data-types"></a><span data-ttu-id="a2b77-123">無効なデータ型にバルーンヒントを追加する</span><span class="sxs-lookup"><span data-stu-id="a2b77-123">Add a balloon tip for invalid data types</span></span>  
  
1. <span data-ttu-id="a2b77-124">フォームの <xref:System.Windows.Forms.Form.Load> イベントハンドラーで、 <xref:System.Type> 型を表すオブジェクトを <xref:System.DateTime> <xref:System.Windows.Forms.MaskedTextBox> コントロールのプロパティに割り当て <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="a2b77-124">In your form's <xref:System.Windows.Forms.Form.Load> event handler, assign a <xref:System.Type> object representing the <xref:System.DateTime> type to the <xref:System.Windows.Forms.MaskedTextBox> control's <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> property:</span></span>  
  
    ```csharp  
    private void Form1_Load(Object sender, EventArgs e)  
    {  
        // Other code  
        maskedTextBox1.ValidatingType = typeof(System.DateTime);  
        maskedTextBox1.TypeValidationCompleted += new TypeValidationEventHandler(maskedTextBox1_TypeValidationCompleted);  
    }  
    ```  
  
    ```vb  
    Private Sub Form1_Load(sender as Object, e as EventArgs)  
        // Other code  
        MaskedTextBox1.ValidatingType = GetType(System.DateTime)  
    End Sub  
    ```  
  
2. <span data-ttu-id="a2b77-125"><xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> イベントのイベント ハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="a2b77-125">Add an event handler for the <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> event:</span></span>  
  
    ```csharp  
    public void maskedTextBox1_TypeValidationCompleted(object sender, TypeValidationEventArgs e)  
    {  
        if (!e.IsValidInput)  
        {  
           toolTip1.ToolTipTitle = "Invalid Date Value";  
           toolTip1.Show("We're sorry, but the value you entered is not a valid date. Please change the value.", maskedTextBox1, 5000);  
           e.Cancel = true;  
        }  
    }  
    ```  
  
    ```vb  
    Public Sub MaskedTextBox1_TypeValidationCompleted(sender as Object, e as TypeValidationEventArgs)  
        If Not e.IsValidInput Then  
           ToolTip1.ToolTipTitle = "Invalid Date Value"  
           ToolTip1.Show("We're sorry, but the value you entered is not a valid date. Please change the value.", maskedTextBox1, 5000)  
           e.Cancel = True  
        End If  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a2b77-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="a2b77-126">See also</span></span>

- <xref:System.Windows.Forms.MaskedTextBox>
- [<span data-ttu-id="a2b77-127">MaskedTextBox コントロール</span><span class="sxs-lookup"><span data-stu-id="a2b77-127">MaskedTextBox Control</span></span>](maskedtextbox-control-windows-forms.md)
