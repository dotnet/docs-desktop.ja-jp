---
title: '方法: カラー行列を使用して単一色を変換する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image colors [Windows Forms], transforming
- color matrices [Windows Forms], using
ms.assetid: 44df4556-a433-49c0-ac0f-9a12063a5860
ms.openlocfilehash: 2df74e022b842f7e5c9ff80f6aeddfce51af5eab
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981751"
---
# <a name="how-to-use-a-color-matrix-to-transform-a-single-color"></a>方法: カラー行列を使用して単一色を変換する
GDI + には、 <xref:System.Drawing.Image> <xref:System.Drawing.Bitmap> イメージを格納および操作するためのクラスとクラスが用意されています。 <xref:System.Drawing.Image><xref:System.Drawing.Bitmap>オブジェクトとオブジェクトには、各ピクセルの色が32ビットの数値として格納されます。各ピクセルは、赤、緑、青、およびアルファにそれぞれ8ビットずつ格納されます。 4つの各コンポーネントは、0 ~ 255 の数値です。0は濃度を表し、255は完全な輝度を表します。 アルファコンポーネントは、色の透明度を指定します。0は完全に透明で、255は完全に不透明です。  
  
 カラーベクターは、(赤、緑、青、アルファ) の形式の4タプルです。 たとえば、カラーベクター (0、255、0、255) は、赤または青のない不透明色を表しますが、完全に輝度が緑色になっています。  
  
 色を表すためのもう1つの規則では、数値1を使用して完全に輝度を指定します。 この規則を使用すると、前の段落で説明した色がベクター (0, 1, 0, 1) によって表されます。 GDI + では、カラー変換を実行するときに、1の規則を使用して完全な強度を使用します。  
  
 カラーベクターに4×4の行列を掛けることによって、線形変換 (回転、拡大縮小、および like) をカラーベクターに適用できます。 ただし、4×4行列を使用して平行移動 (非線形) を実行することはできません。 ダミーの5番目の座標 (たとえば、数字 1) を各カラーベクターに追加する場合は、5×5行列を使用して、線形変換と翻訳の任意の組み合わせを適用できます。 線形変換とそれに続く変換で構成される変換は、アフィン変換と呼ばれます。  
  
 たとえば、色 (0.2、0.0、0.4、1.0) で開始し、次の変換を適用するとします。  
  
1. 赤のコンポーネントを2倍にする  
  
2. 赤、緑、および青のコンポーネントに0.2 を追加する  
  
 次の行列乗算では、変換のペアを一覧表示された順序で実行します。  
  
 ![変換乗算行列のスクリーンショット。](./media/how-to-use-a-color-matrix-to-transform-a-single-color/multiplication-color-matrix.gif)
  
 カラー行列の要素は、行と列によってインデックスが作成されます (0 から始まる)。 たとえば、マトリックス M の5番目の行と3番目の列のエントリは、M [4] [2] によって示されます。  
  
 次の図に示すように、5×5の id 行列は対角線に1つ、他のすべての場所で0になります。 Id 行列によってカラーベクターを乗算した場合、カラーベクターは変わりません。 カラー変換のマトリックスを作成する便利な方法は、id マトリックスから開始し、必要な変換を生成する小さな変更を行うことです。  
  
 ![カラー変換の 5 x 5 の id 行列のスクリーンショット。](./media/how-to-use-a-color-matrix-to-transform-a-single-color/5x5-identity-matrix-color-transformation.gif)  
  
 マトリックスと変換の詳細については、「 [座標系と変換](coordinate-systems-and-transformations.md)」を参照してください。  
  
## <a name="example"></a>例  
 次の例では、1つの色 (0.2、0.0、0.4、1.0) のイメージを取得し、前の段落で説明した変換を適用します。  
  
 次の図は、左側にある元の画像と右側の変換された画像を示しています。  
  
 ![左側に紫色の四角を、右側に fuchsia の四角形を入れます。](./media/how-to-use-a-color-matrix-to-transform-a-single-color/color-transformation.png)  
  
 次の例のコードでは、次の手順を使用して、色の色の色を実行します。  
  
1. オブジェクトを初期化 <xref:System.Drawing.Imaging.ColorMatrix> します。  
  
2. オブジェクトを作成 <xref:System.Drawing.Imaging.ImageAttributes> し、オブジェクト <xref:System.Drawing.Imaging.ColorMatrix> のメソッドにオブジェクトを渡し <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> <xref:System.Drawing.Imaging.ImageAttributes> ます。  
  
3. オブジェクトを <xref:System.Drawing.Imaging.ImageAttributes> <xref:System.Drawing.Graphics.DrawImage%2A> オブジェクトのメソッドに渡し <xref:System.Drawing.Graphics> ます。  
  
 [!code-csharp[System.Drawing.RecoloringImages#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.RecoloringImages#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。  
  
## <a name="see-also"></a>関連項目

- [イメージの色の変更](recoloring-images.md)
- [座標系と変換](coordinate-systems-and-transformations.md)
