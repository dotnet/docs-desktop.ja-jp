---
title: '方法: TextBox コントロールのテキストの先頭または末尾にカーソルを配置する'
description: Windows Presentation Foundation の TextBox コントロールのテキスト コンテンツの先頭または末尾にカーソルを配置する方法について学習します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- positioning cursor [WPF]
- TextBox control [WPF], positioning cursor
- cursor [WPF], positioning
ms.assetid: c771a0b8-c6b4-4240-aecd-a21d0ba51a2e
ms.openlocfilehash: 32a738c37bac07e660fe84e3707ba4352594928a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984919"
---
# <a name="how-to-position-the-cursor-at-the-beginning-or-end-of-text-in-a-textbox-control"></a>方法: TextBox コントロールのテキストの先頭または末尾にカーソルを配置する
この例からは、<xref:System.Windows.Controls.TextBox> コントロールのテキスト コンテンツの先頭または末尾にカーソルを置く方法がわかります。  
  
## <a name="example"></a>例  
 次の [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] コードでは、<xref:System.Windows.Controls.TextBox> コントロールが説明され、それに名前が割り当てられます。  
  
 [!code-xaml[TextBox_MiscCode#_MoveCursorXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_movecursorxaml)]  
  
## <a name="example"></a>例  
 <xref:System.Windows.Controls.TextBox> コントロールのコンテンツの先頭にカーソルを置くには、<xref:System.Windows.Controls.TextBox.Select%2A> メソッドを呼び出し、選択範囲の開始位置を 0 に、選択範囲の長さを 0 に指定します。  
  
 [!code-csharp[TextBox_MiscCode#_CursorToStart](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortostart)]
 [!code-vb[TextBox_MiscCode#_CursorToStart](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortostart)]  
  
## <a name="example"></a>例  
 <xref:System.Windows.Controls.TextBox> コントロールのコンテンツの末尾にカーソルを配置するには、<xref:System.Windows.Controls.TextBox.Select%2A> メソッドを呼び出し、選択範囲の開始位置をテキスト コンテンツの長さと同じに、選択範囲の長さを 0 に指定します  
  
 [!code-csharp[TextBox_MiscCode#_CursorToEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortoend)]
 [!code-vb[TextBox_MiscCode#_CursorToEnd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortoend)]  
  
## <a name="see-also"></a>関連項目

- [TextBox の概要](textbox-overview.md)
- [RichTextBox の概要](richtextbox-overview.md)
