---
title: TextBox コントロールの概要
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- TextBox
helpviewer_keywords:
- TextBox control [Windows Forms], about TextBox controls
- text boxes [Windows Forms], adding
ms.assetid: d1a9c7f5-fa53-480a-a75c-158f8649ea2f
ms.openlocfilehash: 06ab460d720d17331881b5ba653263160eaf3cb3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96980035"
---
# <a name="textbox-control-overview-windows-forms"></a><span data-ttu-id="b33b7-102">TextBox コントロールの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="b33b7-102">TextBox Control Overview (Windows Forms)</span></span>
<span data-ttu-id="b33b7-103">Windows フォームテキストボックスを使用して、ユーザーからの入力を取得したり、テキストを表示したりします。</span><span class="sxs-lookup"><span data-stu-id="b33b7-103">Windows Forms text boxes are used to get input from the user or to display text.</span></span> <span data-ttu-id="b33b7-104">コントロールは、 <xref:System.Windows.Forms.TextBox> 通常、編集可能なテキストに使用されますが、読み取り専用にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="b33b7-104">The <xref:System.Windows.Forms.TextBox> control is generally used for editable text, although it can also be made read-only.</span></span> <span data-ttu-id="b33b7-105">テキストボックスでは、複数の行を表示したり、テキストをコントロールのサイズに折り返したり、基本的な書式を追加したりできます。</span><span class="sxs-lookup"><span data-stu-id="b33b7-105">Text boxes can display multiple lines, wrap text to the size of the control, and add basic formatting.</span></span> <span data-ttu-id="b33b7-106">コントロールは、 <xref:System.Windows.Forms.TextBox> コントロールに表示または入力されるテキストに対して1つの書式スタイルを提供します。</span><span class="sxs-lookup"><span data-stu-id="b33b7-106">The <xref:System.Windows.Forms.TextBox> control provides a single format style for text displayed or entered into the control.</span></span> <span data-ttu-id="b33b7-107">複数の種類の書式設定されたテキストを表示するには、コントロールを使用し <xref:System.Windows.Forms.RichTextBox> ます。</span><span class="sxs-lookup"><span data-stu-id="b33b7-107">To display multiple types of formatted text, use the <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="b33b7-108">詳細については、「 [RichTextBox コントロールの概要](richtextbox-control-overview-windows-forms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b33b7-108">For more information, see [RichTextBox Control Overview](richtextbox-control-overview-windows-forms.md).</span></span>  
  
## <a name="working-with-the-textbox-control"></a><span data-ttu-id="b33b7-109">TextBox コントロールの操作</span><span class="sxs-lookup"><span data-stu-id="b33b7-109">Working with the TextBox Control</span></span>  
 <span data-ttu-id="b33b7-110">コントロールによって表示されるテキストは、プロパティに含まれてい <xref:System.Windows.Forms.TextBox.Text%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="b33b7-110">The text displayed by the control is contained in the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span> <span data-ttu-id="b33b7-111">既定では、テキストボックスに最大2048文字を入力できます。</span><span class="sxs-lookup"><span data-stu-id="b33b7-111">By default, you can enter up to 2048 characters in a text box.</span></span> <span data-ttu-id="b33b7-112">プロパティをに設定すると <xref:System.Windows.Forms.TextBox.Multiline%2A> `true` 、最大 32 KB のテキストを入力できます。</span><span class="sxs-lookup"><span data-stu-id="b33b7-112">If you set the <xref:System.Windows.Forms.TextBox.Multiline%2A> property to `true`, you can enter up to 32 KB of text.</span></span> <span data-ttu-id="b33b7-113">プロパティは、 <xref:System.Windows.Forms.TextBox.Text%2A> デザイン時に、[プロパティ] ウィンドウ、コードの実行時、または実行時のユーザー入力によって設定できます。</span><span class="sxs-lookup"><span data-stu-id="b33b7-113">The <xref:System.Windows.Forms.TextBox.Text%2A> property can be set at design time with the Properties Window, at run time in code, or by user input at run time.</span></span> <span data-ttu-id="b33b7-114">テキストボックスの現在の内容は、実行時にプロパティを読み取って取得でき <xref:System.Windows.Forms.TextBox.Text%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="b33b7-114">The current contents of a text box can be retrieved at run time by reading the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span>  
  
 <span data-ttu-id="b33b7-115">次のコード例では、実行時にコントロールのテキストを設定します。</span><span class="sxs-lookup"><span data-stu-id="b33b7-115">The following code example sets text in the control at run time.</span></span> <span data-ttu-id="b33b7-116">`InitializeMyControl`プロシージャは自動的には実行されません。このプロシージャを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="b33b7-116">The `InitializeMyControl` procedure will not execute automatically; it must be called.</span></span>  
  
```vb  
Private Sub InitializeMyControl()  
   ' Put some text into the control first.  
   TextBox1.Text = "This is a TextBox control."  
End Sub  
```  
  
```csharp  
private void InitializeMyControl() {  
   // Put some text into the control first.  
   textBox1.Text = "This is a TextBox control.";  
}  
```  
  
```cpp  
private:  
   void InitializeMyControl()  
   {  
      // Put some text into the control first.  
      textBox1->Text = "This is a TextBox control.";  
   }  
```  
  
## <a name="see-also"></a><span data-ttu-id="b33b7-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="b33b7-117">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="b33b7-118">方法: Windows フォーム TextBox コントロールでのカーソル位置を制御する</span><span class="sxs-lookup"><span data-stu-id="b33b7-118">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="b33b7-119">方法: Windows フォームの TextBox コントロールを使用してパスワード テキスト ボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="b33b7-119">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="b33b7-120">方法: 読み取り専用テキスト ボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="b33b7-120">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="b33b7-121">方法: 文字列に引用符を挿入する</span><span class="sxs-lookup"><span data-stu-id="b33b7-121">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="b33b7-122">方法: Windows フォーム TextBox コントロールでテキストを選択する</span><span class="sxs-lookup"><span data-stu-id="b33b7-122">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="b33b7-123">方法: Windows フォーム TextBox コントロールで複数行を表示する</span><span class="sxs-lookup"><span data-stu-id="b33b7-123">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="b33b7-124">TextBox コントロール</span><span class="sxs-lookup"><span data-stu-id="b33b7-124">TextBox Control</span></span>](textbox-control-windows-forms.md)
