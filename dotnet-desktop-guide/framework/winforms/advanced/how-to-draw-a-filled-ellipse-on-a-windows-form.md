---
title: '方法: Windows フォームに塗りつぶした楕円を描画する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Graphics.FillEllipse
helpviewer_keywords:
- ellipses [Windows Forms], drawing
- circles [Windows Forms], drawing
- circular shapes
- drawing [Windows Forms], ellipses
- shapes [Windows Forms], drawing
- forms [Windows Forms], drawing ellipses
ms.assetid: 781db806-950d-4c5b-b022-493f7fd0c4a8
ms.openlocfilehash: 2e7be3f2c4c710bb24568dd2e70f6f5cc4706c63
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974400"
---
# <a name="how-to-draw-a-filled-ellipse-on-a-windows-form"></a>方法: Windows フォームに塗りつぶした楕円を描画する
この例では、フォームに塗りつぶされた楕円を描画します。  
  
## <a name="example"></a>例  
 [!code-cpp[System.Drawing.ConceptualHowTos#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#1)]
 [!code-csharp[System.Drawing.ConceptualHowTos#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#1)]
 [!code-vb[System.Drawing.ConceptualHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 イベントハンドラーでは、このメソッドを呼び出すことはできません <xref:System.Windows.Forms.Form.Load> 。 フォームのサイズが変更されたり、別の形式で隠されたりした場合、描画コンテンツは再描画されません。 コンテンツが自動的に再描画されるようにするには、メソッドをオーバーライドする必要があり <xref:System.Windows.Forms.Control.OnPaint%2A> ます。  
  
## <a name="robust-programming"></a>信頼性の高いプログラミング  
 やオブジェクトなどの <xref:System.IDisposable.Dispose%2A> システムリソースを消費するオブジェクトに対しては、常にを呼び出す必要があり <xref:System.Drawing.Brush> <xref:System.Drawing.Graphics> ます。  
  
## <a name="see-also"></a>関連項目

- [Windows フォームにおけるグラフィックスと描画](graphics-and-drawing-in-windows-forms.md)
- [グラフィックス プログラミングについて](getting-started-with-graphics-programming.md)
- [アルファ ブレンドの直線と塗りつぶし](alpha-blending-lines-and-fills.md)
- [ブラシを使用した図形の塗りつぶし](using-a-brush-to-fill-shapes.md)
