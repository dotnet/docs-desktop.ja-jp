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
# <a name="textbox-control-overview-windows-forms"></a>TextBox コントロールの概要 (Windows フォーム)
Windows フォームテキストボックスを使用して、ユーザーからの入力を取得したり、テキストを表示したりします。 コントロールは、 <xref:System.Windows.Forms.TextBox> 通常、編集可能なテキストに使用されますが、読み取り専用にすることもできます。 テキストボックスでは、複数の行を表示したり、テキストをコントロールのサイズに折り返したり、基本的な書式を追加したりできます。 コントロールは、 <xref:System.Windows.Forms.TextBox> コントロールに表示または入力されるテキストに対して1つの書式スタイルを提供します。 複数の種類の書式設定されたテキストを表示するには、コントロールを使用し <xref:System.Windows.Forms.RichTextBox> ます。 詳細については、「 [RichTextBox コントロールの概要](richtextbox-control-overview-windows-forms.md)」を参照してください。  
  
## <a name="working-with-the-textbox-control"></a>TextBox コントロールの操作  
 コントロールによって表示されるテキストは、プロパティに含まれてい <xref:System.Windows.Forms.TextBox.Text%2A> ます。 既定では、テキストボックスに最大2048文字を入力できます。 プロパティをに設定すると <xref:System.Windows.Forms.TextBox.Multiline%2A> `true` 、最大 32 KB のテキストを入力できます。 プロパティは、 <xref:System.Windows.Forms.TextBox.Text%2A> デザイン時に、[プロパティ] ウィンドウ、コードの実行時、または実行時のユーザー入力によって設定できます。 テキストボックスの現在の内容は、実行時にプロパティを読み取って取得でき <xref:System.Windows.Forms.TextBox.Text%2A> ます。  
  
 次のコード例では、実行時にコントロールのテキストを設定します。 `InitializeMyControl`プロシージャは自動的には実行されません。このプロシージャを呼び出す必要があります。  
  
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
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.TextBox>
- [方法: Windows フォーム TextBox コントロールでのカーソル位置を制御する](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [方法: Windows フォームの TextBox コントロールを使用してパスワード テキスト ボックスを作成する](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [方法: 読み取り専用テキスト ボックスを作成する](how-to-create-a-read-only-text-box-windows-forms.md)
- [方法: 文字列に引用符を挿入する](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [方法: Windows フォーム TextBox コントロールでテキストを選択する](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [方法: Windows フォーム TextBox コントロールで複数行を表示する](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [TextBox コントロール](textbox-control-windows-forms.md)
