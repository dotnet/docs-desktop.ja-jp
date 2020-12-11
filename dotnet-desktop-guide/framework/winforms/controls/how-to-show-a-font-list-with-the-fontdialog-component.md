---
title: '方法: FontDialog コンポーネントを使用してフォントの一覧を表示する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- fonts [Windows Forms], showing list
- FontDialog component [Windows Forms]
- fonts [Windows Forms], attributes
- Font property [Windows Forms], setting with FontDialog component
- Font dialog box [Windows Forms], displaying
- fonts [Windows Forms], selecting
ms.assetid: 35692c1b-0937-4b7a-9207-1ae6bdc244a0
ms.openlocfilehash: 05e9b5e1280d0318354b0d47f4d78f7ec1c5f4e7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983011"
---
# <a name="how-to-show-a-font-list-with-the-fontdialog-component"></a><span data-ttu-id="68c00-102">方法: FontDialog コンポーネントを使用してフォントの一覧を表示する</span><span class="sxs-lookup"><span data-stu-id="68c00-102">How to: Show a Font List with the FontDialog Component</span></span>
<span data-ttu-id="68c00-103">[FontDialog](fontdialog-component-windows-forms.md)コンポーネントを使用すると、フォントを選択したり、表示の特性 (重みやサイズなど) を変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="68c00-103">The [FontDialog](fontdialog-component-windows-forms.md) component allows users to select a font, as well as change its display aspects, such as its weight and size.</span></span>  
  
 <span data-ttu-id="68c00-104">ダイアログボックスで選択したフォントがプロパティに返され <xref:System.Windows.Forms.FontDialog.Font%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="68c00-104">The font selected in the dialog box is returned in the <xref:System.Windows.Forms.FontDialog.Font%2A> property.</span></span> <span data-ttu-id="68c00-105">したがって、ユーザーによって選択されたフォントを利用することは、プロパティの読み取りと同じように簡単です。</span><span class="sxs-lookup"><span data-stu-id="68c00-105">Thus, taking advantage of the font selected by the user is as easy as reading a property.</span></span>  
  
### <a name="to-select-font-properties-using-the-fontdialog-component"></a><span data-ttu-id="68c00-106">FontDialog コンポーネントを使用してフォントプロパティを選択するには</span><span class="sxs-lookup"><span data-stu-id="68c00-106">To select font properties using the FontDialog Component</span></span>  
  
1. <span data-ttu-id="68c00-107">メソッドを使用してダイアログボックスを表示し <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="68c00-107">Display the dialog box using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
2. <span data-ttu-id="68c00-108">プロパティを使用して、 <xref:System.Windows.Forms.DialogResult> ダイアログボックスがどのように閉じられたかを確認します。</span><span class="sxs-lookup"><span data-stu-id="68c00-108">Use the <xref:System.Windows.Forms.DialogResult> property to determine how the dialog box was closed.</span></span>  
  
3. <span data-ttu-id="68c00-109">目的の <xref:System.Windows.Forms.FontDialog.Font%2A> フォントを設定するには、プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="68c00-109">Use the <xref:System.Windows.Forms.FontDialog.Font%2A> property to set the desired font.</span></span>  
  
     <span data-ttu-id="68c00-110">次の例では、 <xref:System.Windows.Forms.Button> コントロールの <xref:System.Windows.Forms.Control.Click> イベントハンドラーによってコンポーネントが開かれ <xref:System.Windows.Forms.FontDialog> ます。</span><span class="sxs-lookup"><span data-stu-id="68c00-110">In the example below, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens a <xref:System.Windows.Forms.FontDialog> component.</span></span> <span data-ttu-id="68c00-111">フォントを選択し、ユーザーが **[OK]** をクリックすると、 <xref:System.Windows.Forms.FontDialog.Font%2A> フォーム上のコントロールのプロパティが、選択した <xref:System.Windows.Forms.TextBox> フォントに設定されます。</span><span class="sxs-lookup"><span data-stu-id="68c00-111">When a font is chosen and the user clicks **OK**, the <xref:System.Windows.Forms.FontDialog.Font%2A> property of a <xref:System.Windows.Forms.TextBox> control that is on the form is set to the chosen font.</span></span> <span data-ttu-id="68c00-112">この例では、フォームに <xref:System.Windows.Forms.Button> コントロール、  <xref:System.Windows.Forms.TextBox> コントロール、およびコンポーネントが含まれていることを前提としてい <xref:System.Windows.Forms.FontDialog> ます。</span><span class="sxs-lookup"><span data-stu-id="68c00-112">The example assumes your form has a <xref:System.Windows.Forms.Button> control, a  <xref:System.Windows.Forms.TextBox> control, and a <xref:System.Windows.Forms.FontDialog> component.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       If FontDialog1.ShowDialog() = DialogResult.OK Then  
          TextBox1.Font = FontDialog1.Font  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(fontDialog1.ShowDialog() == DialogResult.OK)  
       {  
          textBox1.Font = fontDialog1.Font;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if(fontDialog1->ShowDialog() == DialogResult::OK)  
          {  
             textBox1->Font = fontDialog1->Font;  
          }  
       }  
    ```  
  
     <span data-ttu-id="68c00-113">(Visual C# および Visual C++)フォームのコンストラクターに次のコードを配置して、イベントハンドラーを登録します。</span><span class="sxs-lookup"><span data-stu-id="68c00-113">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="68c00-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="68c00-114">See also</span></span>

- <xref:System.Windows.Forms.FontDialog>
- [<span data-ttu-id="68c00-115">FontDialog コンポーネント</span><span class="sxs-lookup"><span data-stu-id="68c00-115">FontDialog Component</span></span>](fontdialog-component-windows-forms.md)
