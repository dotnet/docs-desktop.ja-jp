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
# <a name="how-to-show-a-font-list-with-the-fontdialog-component"></a>方法: FontDialog コンポーネントを使用してフォントの一覧を表示する
[FontDialog](fontdialog-component-windows-forms.md)コンポーネントを使用すると、フォントを選択したり、表示の特性 (重みやサイズなど) を変更したりできます。  
  
 ダイアログボックスで選択したフォントがプロパティに返され <xref:System.Windows.Forms.FontDialog.Font%2A> ます。 したがって、ユーザーによって選択されたフォントを利用することは、プロパティの読み取りと同じように簡単です。  
  
### <a name="to-select-font-properties-using-the-fontdialog-component"></a>FontDialog コンポーネントを使用してフォントプロパティを選択するには  
  
1. メソッドを使用してダイアログボックスを表示し <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> ます。  
  
2. プロパティを使用して、 <xref:System.Windows.Forms.DialogResult> ダイアログボックスがどのように閉じられたかを確認します。  
  
3. 目的の <xref:System.Windows.Forms.FontDialog.Font%2A> フォントを設定するには、プロパティを使用します。  
  
     次の例では、 <xref:System.Windows.Forms.Button> コントロールの <xref:System.Windows.Forms.Control.Click> イベントハンドラーによってコンポーネントが開かれ <xref:System.Windows.Forms.FontDialog> ます。 フォントを選択し、ユーザーが **[OK]** をクリックすると、 <xref:System.Windows.Forms.FontDialog.Font%2A> フォーム上のコントロールのプロパティが、選択した <xref:System.Windows.Forms.TextBox> フォントに設定されます。 この例では、フォームに <xref:System.Windows.Forms.Button> コントロール、  <xref:System.Windows.Forms.TextBox> コントロール、およびコンポーネントが含まれていることを前提としてい <xref:System.Windows.Forms.FontDialog> ます。  
  
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
  
     (Visual C# および Visual C++)フォームのコンストラクターに次のコードを配置して、イベントハンドラーを登録します。  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.FontDialog>
- [FontDialog コンポーネント](fontdialog-component-windows-forms.md)
