---
title: '方法: Windows フォームに縦書きテキストを描画する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- StringFormat.FormatFlags
- Graphics.DrawString
helpviewer_keywords:
- text [Windows Forms], drawing vertical
- strings [Windows Forms], drawing vertical
- text [Windows Forms], drawing
- text [Windows Forms], vertical text
ms.assetid: 717a6131-00f6-4373-b574-9894e8317799
ms.openlocfilehash: 660d7abae5463c976e60b7d9caeae8a798d122ca
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981355"
---
# <a name="how-to-draw-vertical-text-on-a-windows-form"></a>方法: Windows フォームに縦書きテキストを描画する
次のコード例では、のメソッドを使用して、フォームに縦書きテキストを描画する方法を示し <xref:System.Drawing.Graphics.DrawString%2A> <xref:System.Drawing.Graphics> ます。  
  
## <a name="example"></a>例  
 [!code-cpp[System.Drawing.ConceptualHowTos#8](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#8)]
 [!code-csharp[System.Drawing.ConceptualHowTos#8](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#8)]
 [!code-vb[System.Drawing.ConceptualHowTos#8](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#8)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 イベントハンドラーでは、このメソッドを呼び出すことはできません <xref:System.Windows.Forms.Form.Load> 。 フォームのサイズが変更されたり、別の形式で隠されたりした場合、描画コンテンツは再描画されません。 コンテンツが自動的に再描画されるようにするには、メソッドをオーバーライドする必要があり <xref:System.Windows.Forms.Control.OnPaint%2A> ます。  
  
## <a name="robust-programming"></a>信頼性の高いプログラミング  
 次の条件を満たす場合は、例外が発生する可能性があります。  
  
- Arial フォントがインストールされていません。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Drawing.Graphics.DrawString%2A>
- <xref:System.Drawing.StringFormat.FormatFlags%2A>
- <xref:System.Drawing.StringFormatFlags>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [グラフィックス プログラミングについて](getting-started-with-graphics-programming.md)
- [フォントとテキストの使用](using-fonts-and-text.md)
