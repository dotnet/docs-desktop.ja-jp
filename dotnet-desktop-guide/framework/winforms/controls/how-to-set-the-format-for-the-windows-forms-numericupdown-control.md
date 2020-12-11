---
title: NumericUpDown コントロールの形式を設定する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- NumericUpDown control [Windows Forms], formatting values
- up-down controls [Windows Forms], formatting numeric values
ms.assetid: fa7c5557-6bfb-45b2-975d-8887b23b0ba0
ms.openlocfilehash: 5ef1c801e96bef7b92e7e69dc36491144c456eeb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982840"
---
# <a name="how-to-set-the-format-for-the-windows-forms-numericupdown-control"></a>方法: Windows フォームの NumericUpDown コントロールの書式を設定する
Windows フォームコントロールでの値の表示方法を構成でき <xref:System.Windows.Forms.NumericUpDown> ます。 プロパティは、 <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> 小数点の後に表示される数字の数を決定します。既定値は0です。 プロパティは、 <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> 3 桁の10進数の間に区切り記号を挿入するかどうかを決定します。既定値は `false` です。 プロパティがに設定されている場合、コントロールは、10進形式ではなく16進数で値を表示できます。 <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> `true` 既定値は `false` です。  
  
### <a name="to-format-the-numeric-value"></a>数値の書式を設定するには  
  
- <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A>プロパティを整数に設定し、プロパティをまたはに設定して、10進値を表示し <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> `true` `false` ます。  
  
    ```vb  
    NumericUpDown1.DecimalPlaces = 2  
    NumericUpDown1.ThousandsSeparator = True  
    ```  
  
    ```csharp  
    numericUpDown1.DecimalPlaces = 2;  
    numericUpDown1.ThousandsSeparator = true;  
    ```  
  
    ```cpp  
    numericUpDown1->DecimalPlaces = 2;  
    numericUpDown1->ThousandsSeparator = true;  
    ```  
  
     または  
  
- プロパティをに設定して、16進数の値を表示 <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> `true` します。  
  
    ```vb  
    NumericUpDown1.Hexadecimal = True  
    ```  
  
    ```csharp  
    numericUpDown1.Hexadecimal = true;  
    ```  
  
    ```cpp  
    numericUpDown1->Hexadecimal = true;  
    ```  
  
    > [!NOTE]
    > 値が16進数としてフォームに表示されている場合でも、プロパティに対して実行するすべてのテストでは、 <xref:System.Windows.Forms.NumericUpDown.Value%2A> その10進値がテストされます。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.NumericUpDown>
- [NumericUpDown コントロール](numericupdown-control-windows-forms.md)
- [NumericUpDown コントロールの概要](numericupdown-control-overview-windows-forms.md)
