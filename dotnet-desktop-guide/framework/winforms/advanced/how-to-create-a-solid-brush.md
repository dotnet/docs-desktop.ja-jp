---
title: '方法: 純色ブラシを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- solid color brushes
- brushes [Windows Forms], examples
- brushes [Windows Forms], creating solid
ms.assetid: 85c3fe7d-fb1d-4591-8a9f-d75b556b90af
ms.openlocfilehash: ed9ec1f52b41c83b3cc6e36dedf97f1c00db42e6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974830"
---
# <a name="how-to-create-a-solid-brush"></a>方法: 純色ブラシを作成する
この例では、 <xref:System.Drawing.SolidBrush> オブジェクトが図形を塗りつぶすために使用できるオブジェクトを作成し <xref:System.Drawing.Graphics> ます。  
  
## <a name="example"></a>例  
 [!code-cpp[System.Drawing.ConceptualHowTos#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#1)]
 [!code-csharp[System.Drawing.ConceptualHowTos#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#1)]
 [!code-vb[System.Drawing.ConceptualHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#1)]  
  
## <a name="robust-programming"></a>信頼性の高いプログラミング  
 これらの使用が完了したら、 <xref:System.IDisposable.Dispose%2A> ブラシオブジェクトなどのシステムリソースを消費するオブジェクトに対してを呼び出す必要があります。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Drawing.SolidBrush>
- <xref:System.Drawing.Brush>
- [グラフィックス プログラミングについて](getting-started-with-graphics-programming.md)
- [GDI+ でのブラシと塗りつぶされた図形](brushes-and-filled-shapes-in-gdi.md)
- [ブラシを使用した図形の塗りつぶし](using-a-brush-to-fill-shapes.md)
