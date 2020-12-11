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
# <a name="how-to-set-and-return-numeric-values-with-the-windows-forms-numericupdown-control"></a><span data-ttu-id="9449b-102">方法: Windows フォームの NumericUpDown コントロールを使用して数値を設定および取得する</span><span class="sxs-lookup"><span data-stu-id="9449b-102">How to: Set and Return Numeric Values with the Windows Forms NumericUpDown Control</span></span>
<span data-ttu-id="9449b-103">Windows フォームコントロールの数値は、 <xref:System.Windows.Forms.NumericUpDown> そのプロパティによって決定され <xref:System.Windows.Forms.NumericUpDown.Value%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="9449b-103">The numeric value of the Windows Forms <xref:System.Windows.Forms.NumericUpDown> control is determined by its <xref:System.Windows.Forms.NumericUpDown.Value%2A> property.</span></span> <span data-ttu-id="9449b-104">他のプロパティと同様に、コントロールの値の条件付きテストを記述できます。</span><span class="sxs-lookup"><span data-stu-id="9449b-104">You can write conditional tests for the control's value just as with any other property.</span></span> <span data-ttu-id="9449b-105"><xref:System.Windows.Forms.NumericUpDown.Value%2A>プロパティが設定されたら、それに対して操作を実行するコードを記述して直接調整できます。または、メソッドとメソッドを呼び出すこともでき <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="9449b-105">Once the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property is set, you can adjust it directly by writing code to perform operations on it, or you can call the <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> and <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> methods.</span></span>  
  
### <a name="to-set-the-numeric-value"></a><span data-ttu-id="9449b-106">数値を設定するには</span><span class="sxs-lookup"><span data-stu-id="9449b-106">To set the numeric value</span></span>  
  
1. <span data-ttu-id="9449b-107"><xref:System.Windows.Forms.NumericUpDown.Value%2A>コードまたはプロパティウィンドウでプロパティに値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="9449b-107">Assign a value to the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property in code or in the Properties window.</span></span>  
  
    ```vb  
    NumericUpDown1.Value = 55  
    ```  
  
    ```csharp  
    numericUpDown1.Value = 55;  
    ```  
  
    ```cpp  
    numericUpDown1->Value = 55;  
    ```  
  
     <span data-ttu-id="9449b-108">または</span><span class="sxs-lookup"><span data-stu-id="9449b-108">-or-</span></span>  
  
2. <span data-ttu-id="9449b-109"><xref:System.Windows.Forms.NumericUpDown.UpButton%2A>またはメソッドを呼び出し <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> て、プロパティで指定した量だけ値を増減させ <xref:System.Windows.Forms.NumericUpDown.Increment%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="9449b-109">Call the <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> or <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> method to increase or decrease the value by the amount specified in the <xref:System.Windows.Forms.NumericUpDown.Increment%2A> property.</span></span>  
  
    ```vb  
    NumericUpDown1.UpButton()  
    ```  
  
    ```csharp  
    numericUpDown1.UpButton();  
    ```  
  
    ```cpp  
    numericUpDown1->UpButton();  
    ```  
  
### <a name="to-return-the-numeric-value"></a><span data-ttu-id="9449b-110">数値を取得するには</span><span class="sxs-lookup"><span data-stu-id="9449b-110">To return the numeric value</span></span>  
  
- <span data-ttu-id="9449b-111"><xref:System.Windows.Forms.NumericUpDown.Value%2A>コード内のプロパティにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="9449b-111">Access the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property in code.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9449b-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="9449b-112">See also</span></span>

- <xref:System.Windows.Forms.NumericUpDown>
- <xref:System.Windows.Forms.NumericUpDown.Value%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.Increment%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.UpButton%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.DownButton%2A?displayProperty=nameWithType>
- [<span data-ttu-id="9449b-113">NumericUpDown コントロール</span><span class="sxs-lookup"><span data-stu-id="9449b-113">NumericUpDown Control</span></span>](numericupdown-control-windows-forms.md)
- [<span data-ttu-id="9449b-114">NumericUpDown コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="9449b-114">NumericUpDown Control Overview</span></span>](numericupdown-control-overview-windows-forms.md)
