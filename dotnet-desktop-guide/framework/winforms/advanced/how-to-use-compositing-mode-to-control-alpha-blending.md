---
title: '方法: 複合モードを使用してアルファ ブレンドを制御する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- alpha blending [Windows Forms], compositing
- colors [Windows Forms], blending
- colors [Windows Forms], controlling transparency
ms.assetid: f331df2d-b395-4b0a-95be-24fec8c9bbb5
ms.openlocfilehash: 6863e59efa25323f80933bf8ab595316b430ef53
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981723"
---
# <a name="how-to-use-compositing-mode-to-control-alpha-blending"></a>方法: 複合モードを使用してアルファ ブレンドを制御する
次の特性を持つオフスクリーンビットマップを作成することが必要になる場合があります。  
  
- 色には、255未満のアルファ値が含まれます。  
  
- ビットマップを作成すると、色はアルファブレンドされません。  
  
- 完成したビットマップを表示すると、ビットマップ内の色は、ディスプレイデバイスの背景色とアルファブレンドされます。  
  
 このようなビットマップを作成するには、空のオブジェクトを構築 <xref:System.Drawing.Bitmap> し、 <xref:System.Drawing.Graphics> そのビットマップに基づいてオブジェクトを構築します。 オブジェクトの合成モード <xref:System.Drawing.Graphics> をに設定し <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy?displayProperty=nameWithType> ます。  
  
## <a name="example"></a>例  
 次の例では、 <xref:System.Drawing.Graphics> オブジェクトに基づいてオブジェクトを作成し <xref:System.Drawing.Bitmap> ます。 このコードでは、 <xref:System.Drawing.Graphics> オブジェクトを2つの半透明ブラシ (アルファ = 160) と共に使用して、ビットマップに描画します。 このコードは、半透明のブラシを使用して赤の楕円と緑の楕円を塗りつぶします。 緑の楕円は赤い楕円と重なっていますが、オブジェクトの合成モード <xref:System.Drawing.Graphics> がに設定されているため、緑は赤とブレンドされません <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy> 。  
  
 このコードでは、画面にビットマップを2回描画します。1回は白の背景に、もう1回はマルチカラーの背景にします。 2つの楕円の一部であるビットマップのピクセルは、160のアルファ成分を持つため、楕円は画面の背景色とブレンドされます。  
  
 次の図は、コード例の出力を示しています。 省略記号は背景とブレンドされますが、互いにブレンドされることはありません。  
  
 ![楕円が背景とブレンドされていて、互いにブレンドされていないことを示す図。](./media/how-to-use-compositing-mode-to-control-alpha-blending/ellipses-blended-background.png)  
  
 このコード例には、次のステートメントが含まれています。  
  
 [!code-csharp[System.Drawing.AlphaBlending#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.AlphaBlending#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#41)]  
  
 楕円を背景と共に相互にブレンドする場合は、そのステートメントを次のように変更します。  
  
 [!code-csharp[System.Drawing.AlphaBlending#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.AlphaBlending#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#42)]  
  
 次の図は、変更されたコードの出力を示しています。  
  
 ![省略記号を背景に合わせて表示する図。](./media/how-to-use-compositing-mode-to-control-alpha-blending/blend-ellipses-background.png)  
  
 [!code-csharp[System.Drawing.AlphaBlending#43](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#43)]
 [!code-vb[System.Drawing.AlphaBlending#43](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#43)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、のパラメーターであるを必要とし <xref:System.Windows.Forms.PaintEventHandler> ます。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Drawing.Color.FromArgb%2A>
- [アルファ ブレンドの直線と塗りつぶし](alpha-blending-lines-and-fills.md)
