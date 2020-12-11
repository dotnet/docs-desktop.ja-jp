---
title: '方法: ペンを使用して線を描画する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
ms.assetid: 0828c331-a438-4bdd-a4d6-3ef1e59e8795
ms.openlocfilehash: 263c0fbda377e64753cd2d607f633117b4b44253
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981735"
---
# <a name="how-to-use-a-pen-to-draw-lines"></a>方法: ペンを使用して線を描画する
線を描画するには、 <xref:System.Drawing.Graphics> オブジェクトとオブジェクトが必要 <xref:System.Drawing.Pen> です。 <xref:System.Drawing.Graphics>オブジェクトはメソッドを提供し、 <xref:System.Drawing.Graphics.DrawLine%2A> <xref:System.Drawing.Pen> オブジェクトは色や幅などの線の機能を格納します。  
  
## <a name="example"></a>例  
 次の例では、(20, 10) から (300, 100) までの線を描画します。 最初のステートメントでは、クラスコンストラクターを使用して、 <xref:System.Drawing.Pen.%23ctor%2A> 黒色のペンを作成します。 コンストラクターに渡される1つの引数 <xref:System.Drawing.Pen.%23ctor%2A> は、 <xref:System.Drawing.Color> メソッドを使用して作成されたオブジェクトです <xref:System.Drawing.Color.FromArgb%2A> 。 オブジェクトの作成に使用される値 <xref:System.Drawing.Color> (255、0、0、0) は、色のアルファ、赤、緑、および青のコンポーネントに対応します。 これらの値は、不透明な黒のペンを定義します。  
  
 [!code-csharp[System.Drawing.UsingAPen#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Drawing.Pen>
- [ペンを使用した直線と図形の描画](using-a-pen-to-draw-lines-and-shapes.md)
- [GDI+ でのペン、直線、および四角形](pens-lines-and-rectangles-in-gdi.md)
