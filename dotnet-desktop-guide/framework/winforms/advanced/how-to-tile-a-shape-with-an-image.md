---
title: '方法: イメージを並べたパターンによって図形を塗りつぶす'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- texture brushes [Windows Forms], tiling images with
- images [Windows Forms], filling shapes with
- shapes [Windows Forms], tiling with images
- bitmaps [Windows Forms], filling shapes with
ms.assetid: 6d407891-6e5c-4495-a546-3da5604e9fb8
ms.openlocfilehash: a906db44a548361df2822efa24d1dd1849cb5a24
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981248"
---
# <a name="how-to-tile-a-shape-with-an-image"></a>方法: イメージを並べたパターンによって図形を塗りつぶす
タイルを横に配置してフロアをカバーできるのと同様に、四角形のイメージを相互に配置して、図形を塗りつぶす (並べて表示) ことができます。 図形の内部を並べて表示するには、テクスチャブラシを使用します。 オブジェクトを構築する場合 <xref:System.Drawing.TextureBrush> 、コンストラクターに渡す引数の1つは <xref:System.Drawing.Image> オブジェクトです。 テクスチャブラシを使用して図形の内部を描画する場合、図形にはこのイメージの繰り返しコピーが格納されます。  
  
 オブジェクトの "ラップモード" プロパティによっ <xref:System.Drawing.TextureBrush> て、四角形のグリッド内でイメージがどのように配置されるかが決まります。 グリッド内のすべてのタイルの向きを同じにすることも、イメージを1つのグリッド位置から次の位置に切り替えられるようにすることもできます。 反転は、水平方向、垂直方向、または両方にすることができます。 次の例は、さまざまな種類の反転のタイルを示しています。  
  
### <a name="to-tile-an-image"></a>イメージを並べて表示するには  
  
- この例では、次の75×75の画像を使用して、200×200の四角形を並べて表示します。  
  
 ![赤い家と1つのツリーを表示するタイルイメージ。](./media/how-to-tile-a-shape-with-an-image/rectangle-tile-200x200.gif)  
  
- 次の図は、イメージで四角形を並べて表示する方法を示しています。 すべてのタイルの向きが同じであることに注意してください。反転はありません。  
  
 ![すべてのタイルで同じ向きを使用して、イメージで並べて表示される四角形。](./media/how-to-tile-a-shape-with-an-image/rectangle-tiled-image-no-flip.gif)  
  
 [!code-csharp[System.Drawing.UsingABrush#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingABrush#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#31)]  
  
### <a name="to-flip-an-image-horizontally-while-tiling"></a>タイリング中に画像を水平に反転するには  
  
- この例では、同じ75×75の画像を使用して、200×200の四角形を塗りつぶします。 折り返しモードは、画像を水平方向に反転するように設定されています。 次の図は、イメージで四角形を並べて表示する方法を示しています。 あるタイルから、特定の行の次のタイルに移動すると、画像が水平方向に反転されることに注意してください。  
  
 ![水平方向に反転されたイメージで並べて表示される四角形。](./media/how-to-tile-a-shape-with-an-image/rectangle-tiled-image-horizontal-flip.gif)  
  
 [!code-csharp[System.Drawing.UsingABrush#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.UsingABrush#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#32)]  
  
### <a name="to-flip-an-image-vertically-while-tiling"></a>タイル処理中に画像を垂直方向に反転するには  
  
- この例では、同じ75×75の画像を使用して、200×200の四角形を塗りつぶします。 折り返しモードは、画像を垂直方向に反転するように設定されています。  
  
     [!code-csharp[System.Drawing.UsingABrush#33](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#33)]
     [!code-vb[System.Drawing.UsingABrush#33](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#33)]  
  
### <a name="to-flip-an-image-horizontally-and-vertically-while-tiling"></a>タイル処理中に画像を水平方向および垂直方向に反転するには  
  
- この例では、同じ75×75の画像を使用して、200×200の四角形を並べて表示します。 折り返しモードは、画像を水平方向および垂直方向に反転するように設定されています。 次の図は、イメージで四角形を並べて表示する方法を示しています。 特定の行で1つのタイルから次のタイルに移動すると、画像が水平方向に反転されます。また、あるタイルから特定の列の次のタイルに移動すると、画像が垂直方向に反転されます。  
  
 ![水平方向および垂直方向に反転されたイメージで並べて表示される四角形。](./media/how-to-tile-a-shape-with-an-image/rectangle-tiled-image-horizontal-vertical-flip.gif)  
  
 [!code-csharp[System.Drawing.UsingABrush#34](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.UsingABrush#34](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#34)]  
  
## <a name="see-also"></a>関連項目

- [ブラシを使用した図形の塗りつぶし](using-a-brush-to-fill-shapes.md)
