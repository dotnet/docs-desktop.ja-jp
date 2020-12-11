---
title: ErrorProvider コンポーネントを使用したフォーム検証のエラーアイコンの表示
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- errors [Windows Forms], displaying to users
- error icons
- ErrorProvider component [Windows Forms], displaying error icons
- error messages [Windows Forms], displaying icons
ms.assetid: 3b681a32-9db4-497b-a34b-34980eabee46
ms.openlocfilehash: a1e346e332db489351f59c9a0c03ae731baf3dc3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974159"
---
# <a name="how-to-display-error-icons-for-form-validation-with-the-windows-forms-errorprovider-component"></a><span data-ttu-id="1f802-102">方法: Windows フォーム ErrorProvider コンポーネントを使用してフォーム妥当性検査でエラー アイコンを表示する</span><span class="sxs-lookup"><span data-stu-id="1f802-102">How to: Display Error Icons for Form Validation with the Windows Forms ErrorProvider Component</span></span>
<span data-ttu-id="1f802-103">Windows フォームコンポーネントを使用し <xref:System.Windows.Forms.ErrorProvider> て、ユーザーが無効なデータを入力したときにエラーアイコンが表示されるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="1f802-103">You can use a Windows Forms <xref:System.Windows.Forms.ErrorProvider> component to display an error icon when the user enters invalid data.</span></span> <span data-ttu-id="1f802-104">フォームの間にタブを表示するには、フォーム上に少なくとも2つのコントロールが必要であるため、検証コードを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f802-104">You must have at least two controls on the form in order to tab between them and thereby invoke the validation code.</span></span>  
  
### <a name="to-display-an-error-icon-when-a-controls-value-is-invalid"></a><span data-ttu-id="1f802-105">コントロールの値が無効なときにエラーアイコンを表示するには</span><span class="sxs-lookup"><span data-stu-id="1f802-105">To display an error icon when a control's value is invalid</span></span>  
  
1. <span data-ttu-id="1f802-106">2つのコントロール (たとえば、テキストボックス) を Windows フォームに追加します。</span><span class="sxs-lookup"><span data-stu-id="1f802-106">Add two controls — for example, text boxes — to a Windows Form.</span></span>  
  
2. <span data-ttu-id="1f802-107"><xref:System.Windows.Forms.ErrorProvider>フォームにコンポーネントを追加します。</span><span class="sxs-lookup"><span data-stu-id="1f802-107">Add an <xref:System.Windows.Forms.ErrorProvider> component to the form.</span></span>  
  
3. <span data-ttu-id="1f802-108">最初のコントロールを選択し、そのイベントハンドラーにコードを追加し <xref:System.Windows.Forms.Control.Validating> ます。</span><span class="sxs-lookup"><span data-stu-id="1f802-108">Select the first control and add code to its <xref:System.Windows.Forms.Control.Validating> event handler.</span></span> <span data-ttu-id="1f802-109">このコードが正常に実行されるためには、プロシージャがイベントに接続されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f802-109">In order for this code to run properly, the procedure must be connected to the event.</span></span> <span data-ttu-id="1f802-110">詳細については、「 [方法: Windows フォームの実行時にイベントハンドラーを作成](../how-to-create-event-handlers-at-run-time-for-windows-forms.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f802-110">For more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
     <span data-ttu-id="1f802-111">次のコードは、ユーザーが入力したデータの有効性をテストします。データが無効な場合は、 <xref:System.Windows.Forms.ErrorProvider.SetError%2A> メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="1f802-111">The following code tests the validity of the data the user has entered; if the data is invalid, the <xref:System.Windows.Forms.ErrorProvider.SetError%2A> method is called.</span></span> <span data-ttu-id="1f802-112">メソッドの最初の引数は、 <xref:System.Windows.Forms.ErrorProvider.SetError%2A> アイコンを表示するコントロールを指定します。</span><span class="sxs-lookup"><span data-stu-id="1f802-112">The first argument of the <xref:System.Windows.Forms.ErrorProvider.SetError%2A> method specifies which control to display the icon next to.</span></span> <span data-ttu-id="1f802-113">2番目の引数は、表示するエラーテキストです。</span><span class="sxs-lookup"><span data-stu-id="1f802-113">The second argument is the error text to display.</span></span>  
  
    ```vb  
    Private Sub TextBox1_Validating(ByVal Sender As Object, _  
       ByVal e As System.ComponentModel.CancelEventArgs) Handles _  
       TextBox1.Validating  
          If Not IsNumeric(TextBox1.Text) Then  
             ErrorProvider1.SetError(TextBox1, "Not a numeric value.")  
          Else  
             ' Clear the error.  
             ErrorProvider1.SetError(TextBox1, "")  
          End If  
    End Sub  
    ```  
  
    ```csharp  
    protected void textBox1_Validating (object sender,  
       System.ComponentModel.CancelEventArgs e)  
    {  
       try  
       {  
          int x = Int32.Parse(textBox1.Text);  
          errorProvider1.SetError(textBox1, "");  
       }  
       catch (Exception ex)  
       {  
          errorProvider1.SetError(textBox1, "Not an integer value.");  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void textBox1_Validating(System::Object ^  sender,  
          System::ComponentModel::CancelEventArgs ^  e)  
       {  
          try  
          {  
             int x = Int32::Parse(textBox1->Text);  
             errorProvider1->SetError(textBox1, "");  
          }  
          catch (System::Exception ^ ex)  
          {  
             errorProvider1->SetError(textBox1, "Not an integer value.");  
          }  
       }  
    ```  
  
     <span data-ttu-id="1f802-114">(Visual C#、Visual C++)フォームのコンストラクターに次のコードを配置して、イベントハンドラーを登録します。</span><span class="sxs-lookup"><span data-stu-id="1f802-114">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.textBox1.Validating += new  
    System.ComponentModel.CancelEventHandler(this.textBox1_Validating);  
    ```  
  
    ```cpp  
    this->textBox1->Validating += gcnew  
       System::ComponentModel::CancelEventHandler  
       (this, &Form1::textBox1_Validating);  
    ```  
  
4. <span data-ttu-id="1f802-115">プロジェクトを実行します。</span><span class="sxs-lookup"><span data-stu-id="1f802-115">Run the project.</span></span> <span data-ttu-id="1f802-116">1つ目のコントロールに無効な (この例では数値以外の) データを入力し、tab キーを押します。</span><span class="sxs-lookup"><span data-stu-id="1f802-116">Type invalid (in this example, non-numeric) data into the first control, and then tab to the second.</span></span> <span data-ttu-id="1f802-117">エラーアイコンが表示されたら、マウスポインターをポイントしてエラーテキストを確認します。</span><span class="sxs-lookup"><span data-stu-id="1f802-117">When the error icon is displayed, point at it with the mouse pointer to see the error text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f802-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="1f802-118">See also</span></span>

- <xref:System.Windows.Forms.ErrorProvider.SetError%2A>
- [<span data-ttu-id="1f802-119">ErrorProvider コンポーネントの概要</span><span class="sxs-lookup"><span data-stu-id="1f802-119">ErrorProvider Component Overview</span></span>](errorprovider-component-overview-windows-forms.md)
- [<span data-ttu-id="1f802-120">方法: Windows フォーム ErrorProvider コンポーネントで DataSet 内にエラーを表示する</span><span class="sxs-lookup"><span data-stu-id="1f802-120">How to: View Errors Within a DataSet with the Windows Forms ErrorProvider Component</span></span>](view-errors-within-a-dataset-with-wf-errorprovider-component.md)
