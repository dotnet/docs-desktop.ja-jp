---
title: '方法: 直線、曲線、および形状から図形を作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- figures [Windows Forms], creating from shapes
- figures [Windows Forms], creating from lines
ms.assetid: 82fd56c7-b443-4765-9b7c-62ce030656ec
ms.openlocfilehash: c8cf7a7e08bed56fb704bba4e30ff369bc3fcf89
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974829"
---
# <a name="how-to-create-figures-from-lines-curves-and-shapes"></a>方法: 直線、曲線、および形状から図形を作成する
図形を作成するには、を構築してから、やなどのメソッドを呼び出して、 <xref:System.Drawing.Drawing2D.GraphicsPath> <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> パスにプリミティブを追加します。  
  
## <a name="example"></a>例  
 次のコード例では、図を含むパスを作成します。  
  
- 最初の例では、1つの図形を含むパスを作成します。 この図は、1つの円弧で構成されています。円弧は、既定の座標系で反時計回りに、-180 度のスイープ角度を持ちます。  
  
- 2番目の例では、2つの図形を持つパスを作成します。 最初の図は、円弧の後に線を付けたものです。 2番目の図は、曲線の後に直線が続く線です。 最初の図形は開いたままになり、2番目の図形は閉じています。  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#21)]  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#22)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 前の例は、Windows フォームで使用するように設計されており <xref:System.Windows.Forms.PaintEventArgs> `e` 、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Drawing.Drawing2D.GraphicsPath>
- [パスの作成および描画](constructing-and-drawing-paths.md)
- [ペンを使用した直線と図形の描画](using-a-pen-to-draw-lines-and-shapes.md)
