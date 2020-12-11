---
title: '方法: Windows フォームにテキストを描画する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- forms [Windows Forms], drawing text
- text [Windows Forms], drawing
ms.assetid: 5d2447a9-21a1-4adc-b954-5516f2bb9b2c
ms.openlocfilehash: dc99a863765cd617c2ab4a636286f42f5e8daf79
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981371"
---
# <a name="how-to-draw-text-on-a-windows-form"></a>方法: Windows フォームにテキストを描画する
次のコード例は、のメソッドを使用して、フォームにテキストを描画する方法を示して <xref:System.Drawing.Graphics.DrawString%2A> <xref:System.Drawing.Graphics> います。 または、を使用し <xref:System.Windows.Forms.TextRenderer> てフォーム上のテキストを描画することもできます。 詳細については、「 [方法: GDI を使用してテキストを描画する](how-to-draw-text-with-gdi.md)」を参照してください。  
  
## <a name="example"></a>例  
 [!code-cpp[System.Drawing.ConceptualHowTos#7](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#7)]
 [!code-csharp[System.Drawing.ConceptualHowTos#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#7)]
 [!code-vb[System.Drawing.ConceptualHowTos#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#7)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 <xref:System.Drawing.Graphics.DrawString%2A>イベントハンドラーでメソッドを呼び出すことはできません <xref:System.Windows.Forms.Form.Load> 。 フォームのサイズが変更されたり、別の形式で隠されたりした場合、描画コンテンツは再描画されません。 コンテンツが自動的に再描画されるようにするには、メソッドをオーバーライドする必要があり <xref:System.Windows.Forms.Control.OnPaint%2A> ます。  
  
## <a name="robust-programming"></a>信頼性の高いプログラミング  
 次の条件を満たす場合は、例外が発生する可能性があります。  
  
- Arial フォントがインストールされていません。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Drawing.Graphics.DrawString%2A>
- <xref:System.Windows.Forms.TextRenderer.DrawText%2A>
- <xref:System.Drawing.StringFormat.FormatFlags%2A>
- <xref:System.Drawing.StringFormatFlags>
- <xref:System.Windows.Forms.TextFormatFlags>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [グラフィックス プログラミングについて](getting-started-with-graphics-programming.md)
- [方法: GDI を使用してテキストを描画する](how-to-draw-text-with-gdi.md)
