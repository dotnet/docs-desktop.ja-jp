---
title: '方法: 形状のアウトラインを描画する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Graphics.DrawEllipse
helpviewer_keywords:
- ellipses [Windows Forms], drawing
- circles [Windows Forms], drawing
- drawing [Windows Forms], shapes
- circular shapes
- forms [Windows Forms], drawing circular shapes
- circles
- outlined shapes [Windows Forms], examples
- outlined shapes [Windows Forms], drawing
- drawing [Windows Forms], circular shapes
- shapes [Windows Forms], drawing
ms.assetid: f4f9214c-607e-407d-8cdd-6549f0278451
ms.openlocfilehash: 019bbc19cc4b26c42f8539eccd93ec4ff87fab12
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981392"
---
# <a name="how-to-draw-an-outlined-shape"></a>方法: 形状のアウトラインを描画する
この例では、フォーム上に縁付き楕円と四角形を描画します。  
  
## <a name="example"></a>例  
 [!code-cpp[System.Drawing.ConceptualHowTos#6](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#6)]
 [!code-csharp[System.Drawing.ConceptualHowTos#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#6)]
 [!code-vb[System.Drawing.ConceptualHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#6)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 イベントハンドラーでは、このメソッドを呼び出すことはできません <xref:System.Windows.Forms.Form.Load> 。 フォームのサイズが変更されたり、別の形式で隠されたりした場合、描画コンテンツは再描画されません。 コンテンツが自動的に再描画されるようにするには、メソッドをオーバーライドする必要があり <xref:System.Windows.Forms.Control.OnPaint%2A> ます。  
  
## <a name="robust-programming"></a>信頼性の高いプログラミング  
 やオブジェクトなどの <xref:System.IDisposable.Dispose%2A> システムリソースを消費するオブジェクトに対しては、常にを呼び出す必要があり <xref:System.Drawing.Pen> <xref:System.Drawing.Graphics> ます。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Drawing.Graphics.DrawEllipse%2A>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- <xref:System.Drawing.Graphics.DrawRectangle%2A>
- [グラフィックス プログラミングについて](getting-started-with-graphics-programming.md)
- [ペンを使用した直線と図形の描画](using-a-pen-to-draw-lines-and-shapes.md)
- [Windows フォームにおけるグラフィックスと描画](graphics-and-drawing-in-windows-forms.md)
