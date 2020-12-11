---
title: '方法: 開いている図形を塗りつぶす'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- open figures [Windows Forms], filling
- figures [Windows Forms], filling
ms.assetid: 5a36b0e4-f1f4-46c0-a85a-22ae98491950
ms.openlocfilehash: 6ecea7d3edb0c3e25fb4e69ff12b88019e530021
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981339"
---
# <a name="how-to-fill-open-figures"></a>方法: 開いている図形を塗りつぶす
メソッドにオブジェクトを渡すことによって、パスを埋めることができ <xref:System.Drawing.Drawing2D.GraphicsPath> <xref:System.Drawing.Graphics.FillPath%2A> ます。 メソッドは、 <xref:System.Drawing.Graphics.FillPath%2A> パスに現在設定されている塗りつぶしモード (代替またはワインディング) に従ってパスを塗りつぶします。 パスに開いている図形がある場合は、その図形が閉じられているかのようにパスが塗りつぶされます。 GDI + は、終了点から開始点までの直線を描画することで、図形を閉じます。  
  
## <a name="example"></a>例  
 次の例では、1つの開いている図形 (弧) と1つの閉じた図形 (楕円) を含むパスを作成します。 メソッドは、 <xref:System.Drawing.Graphics.FillPath%2A> 既定の塗りつぶしモード () に従ってパスを設定し <xref:System.Drawing.Drawing2D.FillMode.Alternate> ます。  
  
 次の図は、コード例の出力を示しています。 開いている <xref:System.Drawing.Drawing2D.FillMode.Alternate> 図形が終了点から開始点までの直線で閉じられているかのように、パスが (に従って) 塗りつぶされていることに注意してください。  
  
 ![FillPath メソッドの出力を示す図](./media/how-to-fill-open-figures/fill-path-alternate-mode.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Drawing.Drawing2D.GraphicsPath>
- [GDI+ でのグラフィックス パス](graphics-paths-in-gdi.md)
