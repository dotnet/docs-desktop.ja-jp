---
title: グラデーション ブラシを使用した図形の塗りつぶし
ms.date: 03/30/2017
helpviewer_keywords:
- brushes [Windows Forms], gradient brushes
- gradient brushes
- examples [Windows Forms], gradient brushes
ms.assetid: 2c6037b9-05bd-44c0-a22a-19584b722524
ms.openlocfilehash: 7ff555ba4fd81e9123e5f9e9feed38a0ec9d0a08
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981607"
---
# <a name="using-a-gradient-brush-to-fill-shapes"></a>グラデーション ブラシを使用した図形の塗りつぶし
グラデーションブラシを使用して、徐々に変化する色で図形を塗りつぶすことができます。 たとえば、横方向のグラデーションを使用すると、図形の左端から右端に移動したときに徐々に変化する色で図形を塗りつぶすことができます。 左端が黒 (赤、緑、青のコンポーネント0、0、0で表されます) と、赤 (255, 0, 0 で表されます) である四角形を想像してみてください。 四角形の幅が256ピクセルの場合、指定されたピクセルの赤の要素は、その左のピクセルの赤の要素より1大きい値になります。 行の左端のピクセルにはカラーコンポーネント (0, 0, 0) があり、2番目のピクセルは (1, 0, 0)、3番目のピクセルは (2, 0, 0) のようになります。これは、カラーコンポーネント (255, 0, 0) を持つ右端のピクセルに到達するまで続きます。 これらの補間カラー値は、色グラデーションを構成します。  
  
 線状グラデーションは、水平方向、垂直方向、または平行移動したときに、指定した斜線に色が変化します。 パスの内側と境界について移動すると、パスのグラデーションの色が変わります。 パスのグラデーションをカスタマイズして、さまざまな効果を実現できます。  
  
 次の図は、線状グラデーションブラシで塗りつぶされた四角形と、パスグラデーションブラシで塗りつぶされた楕円を示しています。  
  
 ![楕円のグラデーションブラシで塗りつぶされた四角形。](./media/using-a-gradient-brush-to-fill-shapes/rectangle-ellipse-gradient-brush.png)  
  
## <a name="in-this-section"></a>このセクションの内容  
 [方法: 線形グラデーションを作成する](how-to-create-a-linear-gradient.md)  
 クラスを使用して線形グラデーションを作成する方法について説明し <xref:System.Drawing.Drawing2D.LinearGradientBrush> ます。  
  
 [方法: パス グラデーションを作成する](how-to-create-a-path-gradient.md)  
 クラスを使用してパスグラデーションを作成する方法について説明し <xref:System.Drawing.Drawing2D.PathGradientBrush> ます。  
  
 [方法: グラデーションに対してガンマ補正を適用する](how-to-apply-gamma-correction-to-a-gradient.md)  
 グラデーションブラシでガンマ補正を使用する方法について説明します。  
  
## <a name="reference"></a>リファレンス  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>  
 このクラスの説明が含まれ、そのすべてのメンバーへのリンクがあります。  
  
 <xref:System.Drawing.Drawing2D.PathGradientBrush?displayProperty=nameWithType>  
 このクラスの説明が含まれ、そのすべてのメンバーへのリンクがあります。
