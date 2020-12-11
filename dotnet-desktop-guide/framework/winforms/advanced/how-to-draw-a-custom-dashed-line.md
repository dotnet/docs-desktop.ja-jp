---
title: '方法: カスタム破線を描画する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines [Windows Forms], custom
- lines [Windows Forms], drawing
- lines [Windows Forms], dashed
ms.assetid: cd0ed96a-cce4-47b9-b58a-3bae2e3d1bee
ms.openlocfilehash: d2184a8d7d7f24b8f631818608ab4bcdb89857c7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974404"
---
# <a name="how-to-draw-a-custom-dashed-line"></a>方法: カスタム破線を描画する
GDI + には、列挙体に示されている複数のダッシュスタイルが用意されてい <xref:System.Drawing.Drawing2D.DashStyle> ます。 これらの標準の破線スタイルがニーズに合わない場合は、カスタムダッシュパターンを作成できます。  
  
## <a name="example"></a>例  
 カスタム破線を描画するには、配列にダッシュとスペースの長さを設定し、オブジェクトのプロパティの値として配列を割り当て <xref:System.Drawing.Pen.DashPattern%2A> <xref:System.Drawing.Pen> ます。 次の例では、配列に基づいてカスタム破線を描画し `{5, 2, 15, 4}` ます。 配列の要素をペンの幅5で乗算すると、が表示さ `{25, 10, 75, 20}` れます。 表示されるダッシュの長さは 25 ~ 75 の間で、スペースは 10 ~ 20 の範囲で交互に表示されます。  
  
 結果として得られる破線を次の図に示します。 最後のダッシュは25単位にする必要があることに注意してください。これにより、行を (405, 5) で終わらせることができます。  
  
 ![破線を示す図。](./media/how-to-draw-a-custom-dashed-line/dashed-line-illustration.gif "pens6")  
  
 [!code-csharp[System.Drawing.UsingAPen#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.UsingAPen#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 Windows フォームを作成し、フォームのイベントを処理し <xref:System.Windows.Forms.Control.Paint> ます。 前のコードをイベントハンドラーに貼り付け <xref:System.Windows.Forms.Control.Paint> ます。  
  
## <a name="see-also"></a>関連項目

- [ペンを使用した直線と図形の描画](using-a-pen-to-draw-lines-and-shapes.md)
