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
# <a name="how-to-set-the-format-for-the-windows-forms-numericupdown-control"></a><span data-ttu-id="99d7a-102">方法: Windows フォームの NumericUpDown コントロールの書式を設定する</span><span class="sxs-lookup"><span data-stu-id="99d7a-102">How to: Set the Format for the Windows Forms NumericUpDown Control</span></span>
<span data-ttu-id="99d7a-103">Windows フォームコントロールでの値の表示方法を構成でき <xref:System.Windows.Forms.NumericUpDown> ます。</span><span class="sxs-lookup"><span data-stu-id="99d7a-103">You can configure how values are displayed in the Windows Forms <xref:System.Windows.Forms.NumericUpDown> control.</span></span> <span data-ttu-id="99d7a-104">プロパティは、 <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> 小数点の後に表示される数字の数を決定します。既定値は0です。</span><span class="sxs-lookup"><span data-stu-id="99d7a-104">The <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> property determines how many numbers appear after the decimal point; the default is 0.</span></span> <span data-ttu-id="99d7a-105">プロパティは、 <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> 3 桁の10進数の間に区切り記号を挿入するかどうかを決定します。既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="99d7a-105">The <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> property determines whether a separator will be inserted between every three decimal digits; the default is `false`.</span></span> <span data-ttu-id="99d7a-106">プロパティがに設定されている場合、コントロールは、10進形式ではなく16進数で値を表示できます。 <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> `true` 既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="99d7a-106">The control can display values in hexadecimal instead of decimal format, if the <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> property is set to `true`; the default is `false`.</span></span>  
  
### <a name="to-format-the-numeric-value"></a><span data-ttu-id="99d7a-107">数値の書式を設定するには</span><span class="sxs-lookup"><span data-stu-id="99d7a-107">To format the numeric value</span></span>  
  
- <span data-ttu-id="99d7a-108"><xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A>プロパティを整数に設定し、プロパティをまたはに設定して、10進値を表示し <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> `true` `false` ます。</span><span class="sxs-lookup"><span data-stu-id="99d7a-108">Display a decimal value by setting the <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> property to an integer and setting the <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> property to `true` or `false`.</span></span>  
  
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
  
     <span data-ttu-id="99d7a-109">または</span><span class="sxs-lookup"><span data-stu-id="99d7a-109">-or-</span></span>  
  
- <span data-ttu-id="99d7a-110">プロパティをに設定して、16進数の値を表示 <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> `true` します。</span><span class="sxs-lookup"><span data-stu-id="99d7a-110">Display a hexadecimal value by setting the <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> property to `true`.</span></span>  
  
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
    > <span data-ttu-id="99d7a-111">値が16進数としてフォームに表示されている場合でも、プロパティに対して実行するすべてのテストでは、 <xref:System.Windows.Forms.NumericUpDown.Value%2A> その10進値がテストされます。</span><span class="sxs-lookup"><span data-stu-id="99d7a-111">Even if the value is displayed on the form as hexadecimal, any tests you perform on the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property will be testing its decimal value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99d7a-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="99d7a-112">See also</span></span>

- <xref:System.Windows.Forms.NumericUpDown>
- [<span data-ttu-id="99d7a-113">NumericUpDown コントロール</span><span class="sxs-lookup"><span data-stu-id="99d7a-113">NumericUpDown Control</span></span>](numericupdown-control-windows-forms.md)
- [<span data-ttu-id="99d7a-114">NumericUpDown コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="99d7a-114">NumericUpDown Control Overview</span></span>](numericupdown-control-overview-windows-forms.md)
