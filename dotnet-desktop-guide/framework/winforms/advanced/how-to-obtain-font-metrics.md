---
title: '方法: フォント メトリックを取得する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [Windows Forms], obtaining metrics
- font metrics [Windows Forms], obtaining
ms.assetid: ff7c0616-67f7-4fa2-84ee-b8d642f2b09b
ms.openlocfilehash: 7d7ad92199bb8a8f01290066f8ae023a14c2f9ce
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981807"
---
# <a name="how-to-obtain-font-metrics"></a>方法: フォント メトリックを取得する
クラスには、 <xref:System.Drawing.FontFamily> 特定のファミリ/スタイルの組み合わせに対してさまざまなメトリックを取得する次のメソッドが用意されています。  
  
- <xref:System.Drawing.FontFamily.GetEmHeight%2A>FontStyle  
  
- <xref:System.Drawing.FontFamily.GetCellAscent%2A>FontStyle  
  
- <xref:System.Drawing.FontFamily.GetCellDescent%2A>FontStyle  
  
- <xref:System.Drawing.FontFamily.GetLineSpacing%2A>FontStyle  
  
 これらのメソッドによって返される値はフォントデザイン単位であるため、特定のオブジェクトのサイズと単位に依存し <xref:System.Drawing.Font> ません。  
  
 次の図は、さまざまなメトリックを示しています。
  
 ![フォントメトリックの図: アセント、降下、および行間。](./media/how-to-obtain-font-metrics/various-font-metrics.png)  
  
## <a name="example"></a>例  
 次の例では、Arial フォントファミリの標準スタイルのメトリックを表示します。 また、このコードでは、 <xref:System.Drawing.Font> 16 ピクセルのサイズで (Arial ファミリに基づく) オブジェクトを作成し、その特定のオブジェクトのメトリック (ピクセル単位) を表示し <xref:System.Drawing.Font> ます。  
  
 次の図は、コード例の出力を示しています。
  
 ![Arial フォントメトリックのコード出力の例。](./media/how-to-obtain-font-metrics/example-output-code-arial-font.png)  
  
 前の図の出力の最初の2行に注意してください。 <xref:System.Drawing.Font>オブジェクトは16のサイズを返し、オブジェクトは <xref:System.Drawing.FontFamily> em の高さ2048を返します。 この2つの数値 (16 と 2048) は、オブジェクトのフォントデザイン単位と単位 (この場合はピクセル) を変換するためのキーです <xref:System.Drawing.Font> 。  
  
 たとえば、次のようにして、アセントをデザイン単位からピクセルに変換できます。  
  
 ![デザイン単位からピクセルへの変換を示す数式](./media/how-to-obtain-font-metrics/convert-font-units-example.png)  
  
 次のコードでは、オブジェクトのデータメンバーを設定することによってテキストを垂直方向に配置し <xref:System.Drawing.PointF.Y%2A> <xref:System.Drawing.PointF> ます。 Y 座標は、 `font.Height` テキストの新しい行ごとにによって増加します。 <xref:System.Drawing.Font.Height%2A>オブジェクトのプロパティは、 <xref:System.Drawing.Font> その特定のオブジェクトの行間 (ピクセル単位) を返し <xref:System.Drawing.Font> ます。 この例では、によって返される数値 <xref:System.Drawing.Font.Height%2A> は19です。 これは、行間隔メトリックをピクセルに変換することによって取得された (整数に切り上げられた) 数値と同じであることに注意してください。  
  
 Em の高さ (サイズまたは em サイズとも呼ばれます) は、アセントと降下の合計ではないことに注意してください。 アセントと降下の合計は、セルの高さと呼ばれます。 セルの高さから内部の先頭を引いた値が em の高さと同じになります。 セルの高さに外部の先頭を加えた値は、行間と同じになります。  
  
 [!code-csharp[System.Drawing.FontsAndText#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.FontsAndText#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、のパラメーターであるを必要とし <xref:System.Windows.Forms.PaintEventHandler> ます。  
  
## <a name="see-also"></a>関連項目

- [Windows フォームにおけるグラフィックスと描画](graphics-and-drawing-in-windows-forms.md)
- [フォントとテキストの使用](using-fonts-and-text.md)
