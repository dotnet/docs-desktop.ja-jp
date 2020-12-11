---
title: ColorDialog コンポーネントの外観の変更
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ColorDialog component [Windows Forms], examples
- ColorDialog component [Windows Forms], formatting appearance
- color dialog box [Windows Forms], configuring appearance
ms.assetid: bba4e262-1cd7-4f63-89cf-330a36f7b539
ms.openlocfilehash: 0402d7f3c03a0771512a03ac54e1b093c9fe6e9b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982224"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-colordialog-component"></a>方法: Windows フォーム ColorDialog コンポーネントの表示形式を変更する
Windows フォームコンポーネントの外観は、多くの <xref:System.Windows.Forms.ColorDialog> プロパティを使用して構成できます。 ダイアログボックスには2つのセクションがあります。1つは基本色を示し、もう1つはユーザーがカスタムカラーを定義できるようにするものです。  
  
 ほとんどのプロパティは、ダイアログボックスからユーザーが選択できる色を制限します。 プロパティがに設定されている場合 <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> `true` 、ユーザーはカスタムの色を定義できます。 <xref:System.Windows.Forms.ColorDialog.FullOpen%2A> `true` ダイアログボックスを展開してカスタムカラーを定義する場合、プロパティはです。それ以外の場合は、ユーザーは [カスタム色の定義] ボタンをクリックする必要があります。 <xref:System.Windows.Forms.ColorDialog.AnyColor%2A>プロパティがに設定されている場合 `true` 、ダイアログボックスには基本色のセットで使用可能なすべての色が表示されます。 <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>プロパティがに設定されている場合 `true` 、ユーザーはディザーカラーを選択することはできません。選択できるのは純色だけです。  
  
 <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A>プロパティがに設定されている場合 `true` 、ダイアログボックスに [ヘルプ] ボタンが表示されます。 ユーザーが [ヘルプ] ボタンをクリックすると、 <xref:System.Windows.Forms.ColorDialog> コンポーネントの <xref:System.Windows.Forms.CommonDialog.HelpRequest> イベントが発生します。  
  
### <a name="to-configure-the-appearance-of-the-color-dialog-box"></a>[色] ダイアログボックスの外観を構成するには  
  
1. 、、 <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> <xref:System.Windows.Forms.ColorDialog.AnyColor%2A> 、およびの各プロパティを <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> 目的の値に設定します。  
  
    ```vb  
    ColorDialog1.AllowFullOpen = True  
    ColorDialog1.AnyColor = True  
    ColorDialog1.SolidColorOnly = False  
    ColorDialog1.ShowHelp = True  
    ```  
  
    ```csharp  
    colorDialog1.AllowFullOpen = true;  
    colorDialog1.AnyColor = true;  
    colorDialog1.SolidColorOnly = false;  
    colorDialog1.ShowHelp = true;  
    ```  
  
    ```cpp  
    colorDialog1->AllowFullOpen = true;  
    colorDialog1->AnyColor = true;  
    colorDialog1->SolidColorOnly = false;  
    colorDialog1->ShowHelp = true;  
    ```  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.ColorDialog>
- [ColorDialog コンポーネント](colordialog-component-windows-forms.md)
- [ColorDialog コンポーネントの概要](colordialog-component-overview-windows-forms.md)
