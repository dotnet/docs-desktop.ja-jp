---
title: Graphics オブジェクトの状態の管理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], managing state
- graphics [Windows Forms], clipping
ms.assetid: 6207cad1-7a34-4bd6-bfc1-db823ca7a73e
ms.openlocfilehash: d1e7e6eac775ca779fb68605adcc9bc2b9915e49
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981200"
---
# <a name="managing-the-state-of-a-graphics-object"></a>Graphics オブジェクトの状態の管理
<xref:System.Drawing.Graphics>クラスは GDI + の中心にあります。 任意のオブジェクトを描画するには、オブジェクトを取得し、 <xref:System.Drawing.Graphics> そのプロパティを設定して、メソッド <xref:System.Drawing.Graphics.DrawLine%2A> 、、 <xref:System.Drawing.Graphics.DrawImage%2A> <xref:System.Drawing.Graphics.DrawString%2A> 、およびのように呼び出します。  
  
 次の例では、 <xref:System.Drawing.Graphics.DrawRectangle%2A> オブジェクトのメソッドを呼び出し <xref:System.Drawing.Graphics> ます。 メソッドに渡される最初の引数 <xref:System.Drawing.Graphics.DrawRectangle%2A> は <xref:System.Drawing.Pen> オブジェクトです。  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Blue) ' Opaque blue  
graphics.DrawRectangle(pen, 10, 10, 200, 100)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Blue);  // Opaque blue  
graphics.DrawRectangle(pen, 10, 10, 200, 100);  
```  
  
## <a name="graphics-state"></a>グラフィックスの状態  
 オブジェクトは、やなどの <xref:System.Drawing.Graphics> 描画メソッドを提供するだけではありません <xref:System.Drawing.Graphics.DrawLine%2A> <xref:System.Drawing.Graphics.DrawRectangle%2A> 。 <xref:System.Drawing.Graphics>また、オブジェクトはグラフィックスの状態も保持します。これは次のカテゴリに分類できます。  
  
- 品質設定  
  
- 変換  
  
- 領域のクリッピング  
  
### <a name="quality-settings"></a>品質設定  
 <xref:System.Drawing.Graphics>オブジェクトには、描画される項目の品質に影響を与えるいくつかのプロパティがあります。 たとえば、プロパティを設定して、 <xref:System.Drawing.Graphics.TextRenderingHint%2A> テキストに適用されるアンチエイリアシングの種類 (存在する場合) を指定できます。 品質に影響を与える他のプロパティは、、、 <xref:System.Drawing.Graphics.SmoothingMode%2A> <xref:System.Drawing.Graphics.CompositingMode%2A> <xref:System.Drawing.Graphics.CompositingQuality%2A> 、および <xref:System.Drawing.Graphics.InterpolationMode%2A> です。  
  
 次の例では、スムージングモードがに設定された楕円と、スムージングモードがに設定されている2つの楕円を描画し <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed> ます。  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Blue)  
  
graphics.SmoothingMode = SmoothingMode.AntiAlias  
graphics.DrawEllipse(pen, 0, 0, 200, 100)  
graphics.SmoothingMode = SmoothingMode.HighSpeed  
graphics.DrawEllipse(pen, 0, 150, 200, 100)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Blue);  
  
graphics.SmoothingMode = SmoothingMode.AntiAlias;  
graphics.DrawEllipse(pen, 0, 0, 200, 100);  
graphics.SmoothingMode = SmoothingMode.HighSpeed;  
graphics.DrawEllipse(pen, 0, 150, 200, 100);  
```  
  
### <a name="transformations"></a>変換  
 オブジェクトは、 <xref:System.Drawing.Graphics> そのオブジェクトによって描画されるすべてのアイテムに適用される2つの変換 (ワールドおよび page) を保持し <xref:System.Drawing.Graphics> ます。 すべてのアフィン変換は、ワールド変換に格納できます。 アフィン変換には、拡大縮小、回転、反射、傾斜、および平行移動などがあります。 ページ変換を使用して、単位を変更することができます (ピクセルからインチなど)。 詳細については、「 [座標系と変換](coordinate-systems-and-transformations.md)」を参照してください。  
  
 次の例では、オブジェクトのワールド変換とページ変換を設定し <xref:System.Drawing.Graphics> ます。 ワールド変換は30度回転に設定されています。 ページ変換は、2番目に渡される座標がピクセルでは <xref:System.Drawing.Graphics.DrawEllipse%2A> なくミリメートルとして処理されるように設定されます。 このコードでは、2つの同じ呼び出しをメソッドに対して行い <xref:System.Drawing.Graphics.DrawEllipse%2A> ます。 ワールド変換は最初の呼び出しに適用され、 <xref:System.Drawing.Graphics.DrawEllipse%2A> 2 回目の呼び出しには両方の変換 (ワールドとページ) が適用され <xref:System.Drawing.Graphics.DrawEllipse%2A> ます。  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Red)  
  
graphics.ResetTransform()  
graphics.RotateTransform(30) ' world transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50)  
graphics.PageUnit = GraphicsUnit.Millimeter ' page transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Red);
  
graphics.ResetTransform();  
graphics.RotateTransform(30);                    // world transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50);  
graphics.PageUnit = GraphicsUnit.Millimeter;     // page transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50);  
```  
  
 次の図は、2つの楕円を示しています。 30度回転は、楕円の中心についてではなく、座標系の原点 (クライアント領域の左上隅) に関することに注意してください。 また、ペンの幅1は、最初の楕円に1ピクセル、2番目の楕円に1ミリメートルを意味します。  
  
 ![2つの楕円 (回転とペンの幅) を示す図。](./media/managing-the-state-of-a-graphics-object/set-rotation-pen-width-drawellipse-method.png)  
  
### <a name="clipping-region"></a>領域のクリッピング  
 オブジェクトは、 <xref:System.Drawing.Graphics> そのオブジェクトによって描画されるすべての項目に適用されるクリッピング領域を保持し <xref:System.Drawing.Graphics> ます。 クリッピング領域は、メソッドを呼び出すことによって設定でき <xref:System.Drawing.Graphics.SetClip%2A> ます。  
  
 次の例では、2つの四角形の和集合を形成することによって、正形の領域を作成します。 この領域は、オブジェクトのクリッピング領域として指定され <xref:System.Drawing.Graphics> ます。 次に、クリッピング領域の内部に制限されている2つの線を描画します。  
  
```vb  
Dim graphics As Graphics = e.Graphics  
  
' Opaque red, width 5  
Dim pen As New Pen(Color.Red, 5)  
  
' Opaque aqua  
Dim brush As New SolidBrush(Color.FromArgb(255, 180, 255, 255))  
  
' Create a plus-shaped region by forming the union of two rectangles.  
Dim [region] As New [Region](New Rectangle(50, 0, 50, 150))  
[region].Union(New Rectangle(0, 50, 150, 50))  
graphics.FillRegion(brush, [region])  
  
' Set the clipping region.  
graphics.SetClip([region], CombineMode.Replace)  
  
' Draw two clipped lines.  
graphics.DrawLine(pen, 0, 30, 150, 160)  
graphics.DrawLine(pen, 40, 20, 190, 150)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
  
// Opaque red, width 5  
Pen pen = new Pen(Color.Red, 5);
  
// Opaque aqua  
SolidBrush brush = new SolidBrush(Color.FromArgb(255, 180, 255, 255));
  
// Create a plus-shaped region by forming the union of two rectangles.  
Region region = new Region(new Rectangle(50, 0, 50, 150));  
region.Union(new Rectangle(0, 50, 150, 50));  
graphics.FillRegion(brush, region);  
  
// Set the clipping region.  
graphics.SetClip(region, CombineMode.Replace);  
  
// Draw two clipped lines.  
graphics.DrawLine(pen, 0, 30, 150, 160);  
graphics.DrawLine(pen, 40, 20, 190, 150);  
```  
  
 次の図は、クリップされた行を示しています。  
  
 ![制限されたクリップ領域を示す図。](./media/managing-the-state-of-a-graphics-object/set-clipping-region-setclip-method.png)  
  
## <a name="see-also"></a>関連項目

- [Windows フォームにおけるグラフィックスと描画](graphics-and-drawing-in-windows-forms.md)
- [入れ子になっているグラフィックス コンテナーの使用](using-nested-graphics-containers.md)
