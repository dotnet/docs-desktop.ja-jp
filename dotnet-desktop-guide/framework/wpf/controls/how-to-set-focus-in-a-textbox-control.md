---
title: '方法: TextBox コントロールにフォーカスを設定する'
description: Focus メソッドを使用して、Windows Presentation Foundation の TextBox コントロールにフォーカスを設定する方法について学習します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- focus [WPF], setting
- TextBox control [WPF], setting focus
ms.assetid: 24b61b45-dc2d-425e-9839-b017af7ab86f
ms.openlocfilehash: e4c6a174ba0353b89225d2337f138f9feeac947c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983275"
---
# <a name="how-to-set-focus-in-a-textbox-control"></a>方法: TextBox コントロールにフォーカスを設定する
この例では、<xref:System.Windows.UIElement.Focus%2A> メソッドを使用して <xref:System.Windows.Controls.TextBox> コントロールにフォーカスを設定する方法を示します。  
  
## <a name="example"></a>例  
 次の [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] 例では、*tbFocusMe* という名前の単純な <xref:System.Windows.Controls.TextBox> コントロールを示します。  
  
 [!code-xaml[TextBox_MiscCode#_TextBoxFocusXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxfocusxaml)]  
  
## <a name="example"></a>例  
 次の例では、<xref:System.Windows.UIElement.Focus%2A> メソッドが呼び出され、*tbFocusMe*. という名前の <xref:System.Windows.Controls.TextBox> コントロールにフォーカスが設定されます。  
  
 [!code-csharp[TextBox_MiscCode#_FocusTextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_focustextbox)]
 [!code-vb[TextBox_MiscCode#_FocusTextBox](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_focustextbox)]  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.UIElement.Focusable%2A>
- <xref:System.Windows.UIElement.IsFocused%2A>
- [TextBox の概要](textbox-overview.md)
- [RichTextBox の概要](richtextbox-overview.md)
