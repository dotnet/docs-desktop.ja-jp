---
title: '方法: 文字列に引用符を挿入する'
description: テキストの文字列に引用符を配置する方法について説明します。 また、引用符フィールドを定数として使用する方法についても説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- quotation marks
- TextBox control [Windows Forms], displaying quotation marks
- quotation marks [Windows Forms], adding to strings in text boxes
ms.assetid: 68bdc3f3-4177-4eab-99cd-cac17a82b515
ms.openlocfilehash: 08a3e2ab5662cbbf7825890ab430fddcd7b4a9ce
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974778"
---
# <a name="how-to-put-quotation-marks-in-a-string-windows-forms"></a><span data-ttu-id="6948c-104">方法 : 文字列に引用符を挿入する (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="6948c-104">How to: Put Quotation Marks in a String (Windows Forms)</span></span>
<span data-ttu-id="6948c-105">テキストの文字列に引用符 (" ") を挿入することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="6948c-105">Sometimes you might want to place quotation marks (" ") in a string of text.</span></span> <span data-ttu-id="6948c-106">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6948c-106">For example:</span></span>  
  
 <span data-ttu-id="6948c-107">私は、「私たちは、</span><span class="sxs-lookup"><span data-stu-id="6948c-107">She said, "You deserve a treat!"</span></span>  
  
 <span data-ttu-id="6948c-108">別の方法として、フィールドを <xref:Microsoft.VisualBasic.ControlChars.Quote> 定数として使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="6948c-108">As an alternative, you can also use the <xref:Microsoft.VisualBasic.ControlChars.Quote> field as a constant.</span></span>  
  
### <a name="to-place-quotation-marks-in-a-string-in-your-code"></a><span data-ttu-id="6948c-109">コードの文字列に引用符を挿入するには</span><span class="sxs-lookup"><span data-stu-id="6948c-109">To place quotation marks in a string in your code</span></span>  
  
1. <span data-ttu-id="6948c-110">Visual Basic で、行内に2つの引用符を埋め込み引用符として挿入します。</span><span class="sxs-lookup"><span data-stu-id="6948c-110">In Visual Basic, insert two quotation marks in a row as an embedded quotation mark.</span></span> <span data-ttu-id="6948c-111">Visual C# と Visual C++ で、エスケープシーケンス "を \\ 埋め込み引用符として挿入します。</span><span class="sxs-lookup"><span data-stu-id="6948c-111">In Visual C# and Visual C++, insert the escape sequence \\" as an embedded quotation mark.</span></span> <span data-ttu-id="6948c-112">たとえば、上記の文字列を作成するには、次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="6948c-112">For example, to create the preceding string, use the following code.</span></span>  
  
    ```vb  
    Private Sub InsertQuote()  
       TextBox1.Text = "She said, ""You deserve a treat!"" "  
    End Sub  
    ```  
  
    ```csharp  
    private void InsertQuote(){  
       textBox1.Text = "She said, \"You deserve a treat!\" ";  
    }  
    ```  
  
    ```cpp  
    private:  
       void InsertQuote()  
       {  
          textBox1->Text = "She said, \"You deserve a treat!\" ";  
       }  
    ```  
  
     <span data-ttu-id="6948c-113">または</span><span class="sxs-lookup"><span data-stu-id="6948c-113">-or-</span></span>  
  
2. <span data-ttu-id="6948c-114">引用符を表す ASCII 文字または Unicode 文字を挿入します。</span><span class="sxs-lookup"><span data-stu-id="6948c-114">Insert the ASCII or Unicode character for a quotation mark.</span></span> <span data-ttu-id="6948c-115">Visual Basic では、ASCII 文字 (34) を使用します。</span><span class="sxs-lookup"><span data-stu-id="6948c-115">In Visual Basic, use the ASCII character (34).</span></span> <span data-ttu-id="6948c-116">Visual C# では、Unicode 文字 (\u0022) を使用します。</span><span class="sxs-lookup"><span data-stu-id="6948c-116">In Visual C#, use the Unicode character (\u0022).</span></span>  
  
    ```vb  
    Private Sub InsertAscii()  
       TextBox1.Text = "She said, " & Chr(34) & "You deserve a treat!" & Chr(34)  
    End Sub  
    ```  
  
    ```csharp  
    private void InsertAscii(){  
       textBox1.Text = "She said, " + '\u0022' + "You deserve a treat!" + '\u0022';  
    }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="6948c-117">この例では、基本文字セットの文字を指定するユニバーサル文字名を使用できないため、\u0022 を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="6948c-117">In this example, you cannot use \u0022 because you cannot use a universal character name that designates a character in the basic character set.</span></span> <span data-ttu-id="6948c-118">使用した場合、C3851 が発生します。</span><span class="sxs-lookup"><span data-stu-id="6948c-118">Otherwise, you produce C3851.</span></span> <span data-ttu-id="6948c-119">詳細については、「[コンパイラ エラー C3851](/cpp/error-messages/compiler-errors-2/compiler-error-c3851)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6948c-119">For more information, see [Compiler Error C3851](/cpp/error-messages/compiler-errors-2/compiler-error-c3851).</span></span>  
  
     <span data-ttu-id="6948c-120">または</span><span class="sxs-lookup"><span data-stu-id="6948c-120">-or-</span></span>  
  
3. <span data-ttu-id="6948c-121">文字の定数を定義し、必要に応じてその定数を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="6948c-121">You can also define a constant for the character, and use it where needed.</span></span>  
  
    ```vb  
    Const quote As String = """"  
    TextBox1.Text = "She said, " & quote & "You deserve a treat!" & quote  
    ```  
  
    ```csharp  
    const string quote = "\"";  
    textBox1.Text = "She said, " + quote +  "You deserve a treat!"+ quote ;  
    ```  
  
    ```cpp  
    const String^ quote = "\"";  
    textBox1->Text = String::Concat("She said, ",  
       const_cast<String^>(quote), "You deserve a treat!",  
       const_cast<String^>(quote));  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6948c-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="6948c-122">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- <xref:Microsoft.VisualBasic.ControlChars.Quote>
- [<span data-ttu-id="6948c-123">TextBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="6948c-123">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="6948c-124">方法: Windows フォーム TextBox コントロールでのカーソル位置を制御する</span><span class="sxs-lookup"><span data-stu-id="6948c-124">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="6948c-125">方法: Windows フォームの TextBox コントロールを使用してパスワード テキスト ボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="6948c-125">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="6948c-126">方法: 読み取り専用テキスト ボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="6948c-126">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="6948c-127">方法: Windows フォーム TextBox コントロールでテキストを選択する</span><span class="sxs-lookup"><span data-stu-id="6948c-127">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="6948c-128">方法: Windows フォーム TextBox コントロールで複数行を表示する</span><span class="sxs-lookup"><span data-stu-id="6948c-128">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="6948c-129">TextBox コントロール</span><span class="sxs-lookup"><span data-stu-id="6948c-129">TextBox Control</span></span>](textbox-control-windows-forms.md)
