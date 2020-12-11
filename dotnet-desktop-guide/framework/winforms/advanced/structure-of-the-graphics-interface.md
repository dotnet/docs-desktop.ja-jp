---
title: グラフィックス インターフェイスの構造体
ms.date: 03/30/2017
helpviewer_keywords:
- GDI+, using managed interface
- graphics [Windows Forms], class structure
ms.assetid: 010a1e46-656b-40a1-8d5d-87aa05ee1243
ms.openlocfilehash: d3b16249b6bae4a113661f5a3a47097046ba20f1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96979723"
---
# <a name="structure-of-the-graphics-interface"></a>グラフィックス インターフェイスの構造体
GDI + に対するマネージクラスインターフェイスには、約60クラス、50列挙型、および8個の構造体が含まれています。 <xref:System.Drawing.Graphics>クラスは GDI + 機能の中核にあります。実際に線、曲線、数値、画像、テキストを描画するクラスです。  
  
## <a name="important-classes"></a>重要なクラス  
 多くのクラスは、クラスと連携して動作 <xref:System.Drawing.Graphics> します。 たとえば、メソッドは、 <xref:System.Drawing.Graphics.DrawLine%2A> <xref:System.Drawing.Pen> 描画される線の属性 (色、幅、ダッシュスタイル、および like) を保持するオブジェクトを受け取ります。 メソッドは、オブジェクト <xref:System.Drawing.Graphics.FillRectangle%2A> へのポインターを受け取ることができます <xref:System.Drawing.Drawing2D.LinearGradientBrush> 。これは、オブジェクトを使用して、 <xref:System.Drawing.Graphics> 徐々に変化する色で四角形に塗りつぶします。 <xref:System.Drawing.Font> オブジェクトと <xref:System.Drawing.StringFormat> オブジェクトは、オブジェクトがテキストを描画する方法に影響を及ぼし <xref:System.Drawing.Graphics> ます。 オブジェクトは、 <xref:System.Drawing.Drawing2D.Matrix> <xref:System.Drawing.Graphics> イメージの回転、拡大縮小、および反転に使用されるオブジェクトのワールド変換を格納および操作します。  
  
 GDI + には、 <xref:System.Drawing.Rectangle> <xref:System.Drawing.Point> <xref:System.Drawing.Size> グラフィックスデータを整理するための構造 (、、、など) がいくつか用意されています。 また、主に、特定のクラスは構造化データ型として機能します。 たとえば、クラスはクラスのヘルパーであり、クラスはクラス <xref:System.Drawing.Imaging.BitmapData> <xref:System.Drawing.Bitmap> <xref:System.Drawing.Drawing2D.PathData> のヘルパーです <xref:System.Drawing.Drawing2D.GraphicsPath> 。  
  
 GDI + は、関連する定数のコレクションであるいくつかの列挙を定義します。 たとえば、列挙には、 <xref:System.Drawing.Drawing2D.LineJoin> <xref:System.Drawing.Drawing2D.LineJoin.Bevel> <xref:System.Drawing.Drawing2D.LineJoin.Miter> <xref:System.Drawing.Drawing2D.LineJoin.Round> 2 つの行を結合するために使用できるスタイルを指定する、、およびの各要素が含まれています。  
  
## <a name="see-also"></a>関連項目

- [グラフィックスの概要](graphics-overview-windows-forms.md)
- [GDI+ マネージド コードについて](about-gdi-managed-code.md)
- [マネージド グラフィックス クラスの使用](using-managed-graphics-classes.md)
