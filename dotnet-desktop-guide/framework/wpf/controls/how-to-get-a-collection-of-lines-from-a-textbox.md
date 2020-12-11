---
title: '方法: TextBox から行のコレクションを取得する'
ms.date: 03/30/2017
helpviewer_keywords:
- lines [WPF], getting collection of
- TextBox control [WPF], getting collection of lines
ms.assetid: a12f529d-b926-47f6-92bf-cad5f17b532a
ms.openlocfilehash: b7b2f1c2e071388635fb50b1e3573fd7f44334dd
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984340"
---
# <a name="how-to-get-a-collection-of-lines-from-a-textbox"></a>方法: TextBox から行のコレクションを取得する
次の例では、<xref:System.Windows.Controls.TextBox> から一連のテキスト行を取得する方法を示します。  
  
## <a name="example"></a>例  
 次の例では、引数として <xref:System.Windows.Controls.TextBox> を受け取り、**TextBox** にテキスト行が含まれる <xref:System.Collections.Specialized.StringCollection> を返す単純なメソッドを示します。  <xref:System.Windows.Controls.TextBox.LineCount%2A> プロパティは、**TextBox** に現在含まれている行の数を決定するために使用されます。その後、各行を抽出し、それを行のコレクションに追加するために <xref:System.Windows.Controls.TextBox.GetLineText%2A> メソッドが使用されます。  
  
 [!code-csharp[TextBox_MiscCode#_TextBox_GetLines](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textbox_getlines)]  
  
## <a name="see-also"></a>関連項目

- [TextBox の概要](textbox-overview.md)
- [RichTextBox の概要](richtextbox-overview.md)
