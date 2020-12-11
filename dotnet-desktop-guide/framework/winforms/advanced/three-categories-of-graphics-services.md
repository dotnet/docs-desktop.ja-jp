---
title: グラフィックス サービスの 3 つのカテゴリ
ms.date: 03/30/2017
helpviewer_keywords:
- imaging
- graphics [Windows Forms], categories
- 2D vector graphics
- vector graphics
- typography
ms.assetid: 068c0ef3-f6ee-4d58-a7b6-eb2531ead408
ms.openlocfilehash: fa7391ef0f7170ddb9d9d24aa5a1a03635bf46e0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96975226"
---
# <a name="three-categories-of-graphics-services"></a>グラフィックス サービスの 3 つのカテゴリ
Windows フォームのグラフィックスオファリングは、次の3つの広範なカテゴリに分類されます。  
  
- 2次元 (2-d) ベクターグラフィックス  
  
- イメージング  
  
- 文字体裁  
  
## <a name="2d-vector-graphics"></a>2D ベクターグラフィックス  
 直線、曲線、および図形などの2次元ベクターグラフィックスは、座標系の点のセットによって指定されるプリミティブです。 たとえば、直線は2つのエンドポイントによって指定され、四角形は、左上隅の位置と幅と高さを示す数値のペアを指定する点によって指定されます。 単純なパスは、直線で結ばれた点の配列によって指定されます。 ベジエスプラインは、4つのコントロールポイントによって指定された高度な曲線です。  
  
 GDI + には、プリミティブ自体、プリミティブの描画方法に関する情報を格納するクラス、および実際に描画を実行するクラスに関する情報を格納するクラスと構造体が用意されています。 たとえば、 <xref:System.Drawing.Rectangle> 構造体は四角形の位置とサイズを格納します。 <xref:System.Drawing.Pen> クラスは、線の色、線の幅、および線のスタイルに関する情報を格納し <xref:System.Drawing.Graphics> ます。クラスには、線、四角形、パス、およびその他の図形を描画するためのメソッドが用意されています。 また、 <xref:System.Drawing.Brush> 閉じた図形とパスに色またはパターンを設定する方法に関する情報を格納するクラスもいくつかあります。  
  
 ベクターイメージ (グラフィックスコマンドのシーケンス) をメタファイルに記録できます。 GDI + には、 <xref:System.Drawing.Imaging.Metafile> メタファイルの記録、表示、および保存のためのクラスが用意されています。 クラスとクラスを使用すると、 <xref:System.Drawing.Imaging.MetafileHeader> <xref:System.Drawing.Imaging.MetaHeader> メタファイルヘッダーに格納されているデータを検査できます。  
  
## <a name="imaging"></a>イメージング  
 ベクターグラフィックスの手法では、特定の種類の画像を表示するのは困難または不可能です。 たとえば、ツールバーボタンの画像やアイコンとして表示される画像は、直線や曲線のコレクションとして指定するのが困難です。 混雑している野球スタジアムの高解像度デジタル写真は、ベクター手法を使用した作成がさらに困難です。 この種類のイメージはビットマップとして格納されます。これは、画面上の個々のドットの色を表す数値の配列です。 GDI + には、 <xref:System.Drawing.Bitmap> ビットマップを表示、操作、および保存するためのクラスが用意されています。  
  
## <a name="typography"></a>文字体裁  
 タイポグラフィは、さまざまなフォント、サイズ、スタイルでテキストを表示します。 GDI + は、この複雑なタスクを広範にサポートしています。 GDI + の新機能の1つは、サブピクセルアンチエイリアシングです。これにより、LCD 画面に表示されるテキストがより滑らかになります。  
  
 さらに、Windows フォームには、クラスの GDI 機能を使用してテキストを描画するオプションが用意されて <xref:System.Windows.Forms.TextRenderer> います。  
  
## <a name="see-also"></a>関連項目

- [グラフィックスの概要](graphics-overview-windows-forms.md)
- [GDI+ マネージド コードについて](about-gdi-managed-code.md)
- [マネージド グラフィックス クラスの使用](using-managed-graphics-classes.md)
