---
title: NumericUpDown コントロールを使用して数値を設定して返す
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- numeric values [Windows Forms], Windows Forms
- Windows Forms, numeric values
- Windows Forms controls, NumericUpDown
- NumericUpDown control [Windows Forms], setting and returning values
ms.assetid: 5bd8f8cd-4c12-49ea-9cc3-2a647d064689
ms.openlocfilehash: a0b264fec9619b467c293bcb96278c4517775ac3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983535"
---
# <a name="how-to-set-and-return-numeric-values-with-the-windows-forms-numericupdown-control"></a>方法: Windows フォームの NumericUpDown コントロールを使用して数値を設定および取得する
Windows フォームコントロールの数値は、 <xref:System.Windows.Forms.NumericUpDown> そのプロパティによって決定され <xref:System.Windows.Forms.NumericUpDown.Value%2A> ます。 他のプロパティと同様に、コントロールの値の条件付きテストを記述できます。 <xref:System.Windows.Forms.NumericUpDown.Value%2A>プロパティが設定されたら、それに対して操作を実行するコードを記述して直接調整できます。または、メソッドとメソッドを呼び出すこともでき <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> ます。  
  
### <a name="to-set-the-numeric-value"></a>数値を設定するには  
  
1. <xref:System.Windows.Forms.NumericUpDown.Value%2A>コードまたはプロパティウィンドウでプロパティに値を割り当てます。  
  
    ```vb  
    NumericUpDown1.Value = 55  
    ```  
  
    ```csharp  
    numericUpDown1.Value = 55;  
    ```  
  
    ```cpp  
    numericUpDown1->Value = 55;  
    ```  
  
     または  
  
2. <xref:System.Windows.Forms.NumericUpDown.UpButton%2A>またはメソッドを呼び出し <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> て、プロパティで指定した量だけ値を増減させ <xref:System.Windows.Forms.NumericUpDown.Increment%2A> ます。  
  
    ```vb  
    NumericUpDown1.UpButton()  
    ```  
  
    ```csharp  
    numericUpDown1.UpButton();  
    ```  
  
    ```cpp  
    numericUpDown1->UpButton();  
    ```  
  
### <a name="to-return-the-numeric-value"></a>数値を取得するには  
  
- <xref:System.Windows.Forms.NumericUpDown.Value%2A>コード内のプロパティにアクセスします。  
  
    ```vb  
    If NumericUpDown1.Value >= 65 Then  
       MessageBox.Show("Age is: " & NumericUpDown1.Value.ToString)  
    Else  
       MessageBox.Show("The customer is ineligible for a senior citizen discount.")  
    End If  
    ```  
  
    ```csharp  
    if(numericUpDown1.Value >= 65)  
    {  
       MessageBox.Show("Age is: " + numericUpDown1.Value.ToString());  
    }  
    else  
    {  
       MessageBox.Show("The customer is ineligible for a senior citizen discount.");  
    }  
    ```  
  
    ```cpp  
    if(numericUpDown1->Value >= 65)  
    {  
       MessageBox::Show(String::Concat("Age is: ",  
          numericUpDown1->Value.ToString()));  
    }  
    else  
    {  
       MessageBox::Show  
          ("The customer is ineligible for a senior citizen discount.");  
    }  
    ```  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.NumericUpDown>
- <xref:System.Windows.Forms.NumericUpDown.Value%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.Increment%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.UpButton%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.DownButton%2A?displayProperty=nameWithType>
- [NumericUpDown コントロール](numericupdown-control-windows-forms.md)
- [NumericUpDown コントロールの概要](numericupdown-control-overview-windows-forms.md)
