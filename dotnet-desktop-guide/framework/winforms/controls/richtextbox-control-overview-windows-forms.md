---
title: RichTextBox コントロールの概要
ms.date: 03/30/2017
f1_keywords:
- RichTextBox
helpviewer_keywords:
- RichTextBox control [Windows Forms], about RichTextBox control
- text boxes [Windows Forms], about text boxes
ms.assetid: 95081194-3dd4-4b84-9545-dd373e491eca
ms.openlocfilehash: 0d40967d97622b23e9dcb07e861f190327e6baba
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982447"
---
# <a name="richtextbox-control-overview-windows-forms"></a>RichTextBox コントロールの概要 (Windows フォーム)
Windows フォーム <xref:System.Windows.Forms.RichTextBox> コントロールは、書式設定を使用してテキストを表示、入力、および操作するために使用されます。 コントロールは、 <xref:System.Windows.Forms.RichTextBox> コントロールによって実行されるすべての操作を行います <xref:System.Windows.Forms.TextBox> が、フォント、色、およびリンクを表示したり、ファイルからテキストや埋め込み画像を読み込み、指定した文字を検索したりすることもできます。 コントロールは、 <xref:System.Windows.Forms.RichTextBox> 通常、Microsoft word などのワードプロセッシングアプリケーションに似たテキスト操作と表示機能を提供するために使用されます。 コントロールと同様に、コントロール <xref:System.Windows.Forms.TextBox> には <xref:System.Windows.Forms.RichTextBox> スクロールバーが表示されますが、コントロールとは異なり、 <xref:System.Windows.Forms.TextBox> 既定の設定では、必要に応じて水平スクロールバーと垂直スクロールバーの両方が表示され、さらにスクロールバーの設定があります。  
  
## <a name="working-with-the-richtextbox-control"></a>RichTextBox コントロールの操作  
 コントロールと同様に、 <xref:System.Windows.Forms.TextBox> 表示されるテキストはプロパティによって設定され <xref:System.Windows.Forms.RichTextBox.Text%2A> ます。 <xref:System.Windows.Forms.RichTextBox>コントロールには、テキストを書式設定するための多数のプロパティがあります。 これらのプロパティの詳細については、「[How to: Set Font Attributes for the Windows Forms RichTextBox Control (方法: Windows フォームの RichTextBox コントロールのフォント属性を設定)](how-to-set-font-attributes-for-the-windows-forms-richtextbox-control.md)」と「[How to: Set Indents, Hanging Indents, and Bulleted Paragraphs with the Windows Forms RichTextBox Control (方法: Windows フォームの RichTextBox コントロールを使用したインデント、ぶら下げインデント、および箇条書き段落の設定)](set-indents-hanging-indents-bulleted-paragraphs-with-wf-richtextbox.md)」参照してください。 ファイルを操作するために、 <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> メソッドとメソッドでは、 <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> プレーンテキスト、Unicode プレーンテキスト、リッチテキスト形式 (RTF) など、複数のファイル形式を表示して書き込むことができます。 使用可能なファイル形式は、「」に記載されてい <xref:System.Windows.Forms.RichTextBoxStreamType> ます。 メソッドを使用して、 <xref:System.Windows.Forms.RichTextBox.Find%2A> テキストまたは特定の文字の文字列を検索できます。  
  
 また、 <xref:System.Windows.Forms.RichTextBox> <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> プロパティをに設定し、イベントを処理するコードを記述することで、Web スタイルのリンク用のコントロールを使用することもでき `true` <xref:System.Windows.Forms.RichTextBox.LinkClicked> ます。 詳細については、「[How to: Display Web-Style Links with the Windows Forms RichTextBox Control (方法: Windows フォームの RichTextBox コントロールを使用して Web スタイルのリンクを表示する)](how-to-display-web-style-links-with-the-windows-forms-richtextbox-control.md)」を参照してください。 プロパティをに設定することによって、コントロール内のテキストの一部またはすべてをユーザーが操作できないようにすることができ <xref:System.Windows.Forms.RichTextBox.SelectionProtected%2A> `true` ます。  
  
 <xref:System.Windows.Forms.RichTextBox>メソッドとメソッドを呼び出すことにより、コントロールでほとんどの編集操作を元に戻したり、やり直したりでき <xref:System.Windows.Forms.TextBoxBase.Undo%2A> <xref:System.Windows.Forms.RichTextBox.Redo%2A> ます。 <xref:System.Windows.Forms.RichTextBox.CanRedo%2A>メソッドを使用すると、ユーザーが最後に元に戻した操作をコントロールに再適用できるかどうかを判断できます。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.RichTextBox>
- [RichTextBox コントロール](richtextbox-control-windows-forms.md)
- [TextBox コントロールの概要](textbox-control-overview-windows-forms.md)
