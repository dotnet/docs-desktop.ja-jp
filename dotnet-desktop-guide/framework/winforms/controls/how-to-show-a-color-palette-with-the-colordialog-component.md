---
title: '方法: ColorDialog コンポーネントを使用してカラー パレットを表示する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- palettes [Windows Forms], showing color
- color dialog box [Windows Forms], showing color palettes
- colors [Windows Forms], allowing users to select
- color palettes [Windows Forms], dialog box
- ColorDialog component [Windows Forms], showing color palettes
- color palettes [Windows Forms], showing in ColorDialog component
- colors [Windows Forms], showing palettes
ms.assetid: ee050f61-dbc8-4436-ba22-51360981ab48
ms.openlocfilehash: 0406ef7a32678bd149c0024348a7adf1f0b72926
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982808"
---
# <a name="how-to-show-a-color-palette-with-the-colordialog-component"></a>方法: ColorDialog コンポーネントを使用してカラー パレットを表示する
[ColorDialog](colordialog-component-windows-forms.md)コンポーネントは、色のパレットを表示し、ユーザーが選択した色を含むプロパティを返します。  
  
### <a name="to-choose-a-color-using-the-colordialog-component"></a>ColorDialog コンポーネントを使用して色を選択するには  
  
1. メソッドを使用してダイアログボックスを表示し <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> ます。  
  
2. プロパティを使用して、 <xref:System.Windows.Forms.DialogResult> ダイアログボックスがどのように閉じられたかを確認します。  
  
3. コンポーネントのプロパティを使用して、 <xref:System.Windows.Forms.ColorDialog.Color%2A> <xref:System.Windows.Forms.ColorDialog> 選択した色を設定します。  
  
     次の例では、 <xref:System.Windows.Forms.Button> コントロールの <xref:System.Windows.Forms.Control.Click> イベントハンドラーによってコンポーネントが開かれ <xref:System.Windows.Forms.ColorDialog> ます。 色が選択され、ユーザーが **[OK]** をクリックすると、 <xref:System.Windows.Forms.Button> コントロールの背景色が、選択した色に設定されます。 この例では、フォームにコントロールとコンポーネントがあることを前提としてい <xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.ColorDialog> ます。  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles Button1.Click  
       If ColorDialog1.ShowDialog() = DialogResult.OK Then  
          Button1.BackColor = ColorDialog1.Color  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(colorDialog1.ShowDialog() == DialogResult.OK)  
       {  
          button1.BackColor = colorDialog1.Color;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,
          System::EventArgs ^ e)  
       {  
          if(colorDialog1->ShowDialog() == DialogResult::OK)  
          {  
             button1->BackColor = colorDialog1->Color;  
          }  
       }  
    ```  
  
     (Visual C#、Visual C++)フォームのコンストラクターに次のコードを配置して、イベントハンドラーを登録します。  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.ColorDialog>
- [ColorDialog コンポーネント](colordialog-component-windows-forms.md)
