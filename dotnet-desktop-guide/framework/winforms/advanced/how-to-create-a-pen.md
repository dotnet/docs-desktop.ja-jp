---
title: '方法: ペンを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], creating pens
- pens [Windows Forms], creating
- Pen object
ms.assetid: 7fbea8b7-7ac1-4413-9c17-733a850381e3
ms.openlocfilehash: 69fe6157c710ae63df9dbf391a5d355d1c3f9765
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974845"
---
# <a name="how-to-create-a-pen"></a>方法: ペンを作成する
この例では、オブジェクトを作成し <xref:System.Drawing.Pen> ます。  
  
## <a name="example"></a>例  
 [!code-cpp[System.Drawing.ConceptualHowTos#3](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#3)]
 [!code-csharp[System.Drawing.ConceptualHowTos#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#3)]
 [!code-vb[System.Drawing.ConceptualHowTos#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#3)]  
  
## <a name="robust-programming"></a>信頼性の高いプログラミング  
 オブジェクトなどのシステムリソースを消費するオブジェクトの使用が完了したら <xref:System.Drawing.Pen> 、そのオブジェクトに対してを呼び出す必要があり <xref:System.Drawing.Pen.Dispose%2A> ます。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Drawing.Pen>
- [グラフィックス プログラミングについて](getting-started-with-graphics-programming.md)
- [GDI+ でのペン、直線、および四角形](pens-lines-and-rectangles-in-gdi.md)
