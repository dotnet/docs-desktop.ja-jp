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
# <a name="walkthrough-working-with-the-maskedtextbox-control"></a>チュートリアル: MaskedTextBox コントロールの使用
このチュートリアルでは、以下のタスクを行います。  
  
- コントロールの初期化 <xref:System.Windows.Forms.MaskedTextBox>  
  
- <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected>文字がマスクに準拠していない場合に、イベントハンドラーを使用してユーザーに警告する  
  
- 型をプロパティに割り当て <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> 、イベントハンドラーを使用して、コミットしようとして <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> いる値が型に対して有効でない場合にユーザーに警告します。  
  
## <a name="creating-the-project-and-adding-a-control"></a>プロジェクトを作成し、コントロールを追加する  
  
#### <a name="to-add-a-maskedtextbox-control-to-your-form"></a>MaskedTextBox コントロールをフォームに追加するには  
  
1. コントロールを配置するフォームを開き <xref:System.Windows.Forms.MaskedTextBox> ます。  
  
2. コントロールを <xref:System.Windows.Forms.MaskedTextBox> [ **ツールボックス** ] からフォームにドラッグします。  
  
3. コントロールを右クリックし、[ **プロパティ**] を選択します。 [ **プロパティ** ] ウィンドウで、 **Mask** プロパティを選択し、プロパティ名の横にある [.. **.** ] (省略記号) ボタンをクリックします。  
  
4. [ **定型入力** ] ダイアログボックスで、 **短い日付** のマスクを選択し、[ **OK**] をクリックします。  
  
5. [ **プロパティ** ] ウィンドウで、 <xref:System.Windows.Forms.MaskedTextBox.BeepOnError%2A> プロパティをに設定し `true` ます。 このプロパティにより、ユーザーがマスク定義に違反する文字を入力しようとするたびに、短いビープ音が鳴ります。  
  
 Mask プロパティでサポートされる文字の概要については、プロパティの「解説」を参照してください <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> 。  
  
## <a name="alert-the-user-to-input-errors"></a>エラーを入力するようユーザーに警告します  
  
#### <a name="add-a-balloon-tip-for-rejected-mask-input"></a>拒否するマスク入力にバルーンヒントを追加する  
  
1. **ツールボックス** に戻り、を <xref:System.Windows.Forms.ToolTip> フォームに追加します。  
  
2. 入力エラーが発生したときにを発生させるイベントのイベントハンドラーを作成し <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> <xref:System.Windows.Forms.ToolTip> ます。 バルーンヒントは、5秒間、またはユーザーがクリックするまで表示されたままになります。  
  
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
  
## <a name="alert-the-user-to-a-type-that-is-not-valid"></a>無効な種類のユーザーに警告します  
  
#### <a name="add-a-balloon-tip-for-invalid-data-types"></a>無効なデータ型にバルーンヒントを追加する  
  
1. フォームの <xref:System.Windows.Forms.Form.Load> イベントハンドラーで、 <xref:System.Type> 型を表すオブジェクトを <xref:System.DateTime> <xref:System.Windows.Forms.MaskedTextBox> コントロールのプロパティに割り当て <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> ます。  
  
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
  
2. <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> イベントのイベント ハンドラーを追加します。  
  
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
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.MaskedTextBox>
- [MaskedTextBox コントロール](maskedtextbox-control-windows-forms.md)
