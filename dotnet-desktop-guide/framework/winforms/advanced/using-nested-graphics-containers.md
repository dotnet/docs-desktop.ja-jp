---
title: 入れ子になっているグラフィックス コンテナーの使用
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], nested containers
- graphics [Windows Forms], clipping
- graphics [Windows Forms], transformations in nested objects
ms.assetid: a0d9f178-43a4-4323-bb5a-d3e3f77ae6c1
ms.openlocfilehash: 460ebb37ee62691a1e282f756840121fd378ebd8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981192"
---
# <a name="using-nested-graphics-containers"></a>入れ子になっているグラフィックス コンテナーの使用
GDI + には、オブジェクトの状態の一部を一時的に置き換える、または拡張するために使用できるコンテナーが用意されて <xref:System.Drawing.Graphics> います。 コンテナーを作成するには、 <xref:System.Drawing.Graphics.BeginContainer%2A> オブジェクトのメソッドを呼び出し <xref:System.Drawing.Graphics> ます。 を繰り返し呼び出して、 <xref:System.Drawing.Graphics.BeginContainer%2A> 入れ子になったコンテナーを形成することができます。 への各呼び出し <xref:System.Drawing.Graphics.BeginContainer%2A> は、の呼び出しとペアにする必要があり <xref:System.Drawing.Graphics.EndContainer%2A> ます。  
  
## <a name="transformations-in-nested-containers"></a>入れ子になったコンテナー内の変換  
 次の例では、オブジェクト <xref:System.Drawing.Graphics> とそのオブジェクト内にコンテナーを作成し <xref:System.Drawing.Graphics> ます。 オブジェクトのワールド変換 <xref:System.Drawing.Graphics> は、x 方向の平行移動100単位と y 方向の80単位です。 コンテナーのワールド変換は30度回転です。 このコードによって、呼び出しが `DrawRectangle(pen, -60, -30, 120, 60)` 2 回行われます。 への最初の呼び出し <xref:System.Drawing.Graphics.DrawRectangle%2A> は、コンテナー内にあります。つまり、との呼び出しの間にを呼び出し <xref:System.Drawing.Graphics.BeginContainer%2A> <xref:System.Drawing.Graphics.EndContainer%2A> ます。 への2回目の呼び出しは、の <xref:System.Drawing.Graphics.DrawRectangle%2A> 呼び出しの後です <xref:System.Drawing.Graphics.EndContainer%2A> 。  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.MiscLegacyTopics#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#61)]  
  
 上のコードでは、コンテナー内から描画された四角形は、まず、コンテナー (回転) のワールド変換によって変換され、その後、 <xref:System.Drawing.Graphics> オブジェクト (平行移動) のワールド変換によって変換されます。 コンテナーの外側から描画される四角形は、オブジェクトのワールド変換 (変換) によってのみ変換され <xref:System.Drawing.Graphics> ます。 次の図は、2つの四角形を示しています。
  
 ![入れ子になったコンテナーを示す図。](./media/using-nested-graphics-containers/nested-containers-illustration.png)  
  
## <a name="clipping-in-nested-containers"></a>入れ子になったコンテナー内のクリッピング  
 次の例は、入れ子になったコンテナーがクリッピング領域を処理する方法を示しています。 このコードでは、オブジェクト <xref:System.Drawing.Graphics> とそのオブジェクト内にコンテナーを作成し <xref:System.Drawing.Graphics> ます。 オブジェクトのクリッピング領域は <xref:System.Drawing.Graphics> 四角形で、コンテナーのクリッピング領域は楕円です。 このコードでは、メソッドを2回呼び出し <xref:System.Drawing.Graphics.DrawLine%2A> ます。 への最初の呼び出し <xref:System.Drawing.Graphics.DrawLine%2A> はコンテナー内にあり、への2回目の呼び出し <xref:System.Drawing.Graphics.DrawLine%2A> はコンテナー (への呼び出しの後) の外側に <xref:System.Drawing.Graphics.EndContainer%2A> あります。 最初の行は、2つのクリッピング領域の交差部分によってクリップされます。 2番目の行は、オブジェクトの四角形のクリッピング領域によってのみクリップされ <xref:System.Drawing.Graphics> ます。  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#62](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#62)]
 [!code-vb[System.Drawing.MiscLegacyTopics#62](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#62)]  
  
 次の図は、2つのクリップされた行を示しています。
  
 ![クリッピングされた行を含む入れ子になったコンテナーを示す図。](./media/using-nested-graphics-containers/nested-container-clipped-lines.png)  
  
 前の2つの例で示すように、入れ子になったコンテナーでは、変換とクリッピング領域が累積されます。 コンテナーとオブジェクトのワールド変換を設定した場合 <xref:System.Drawing.Graphics> 、両方の変換がコンテナー内から描画された項目に適用されます。 コンテナーの変換が最初に適用され、オブジェクトの変換が <xref:System.Drawing.Graphics> 2 番目に適用されます。 コンテナーとオブジェクトのクリッピング領域を設定した場合 <xref:System.Drawing.Graphics> 、コンテナー内から描画された項目は、2つのクリッピング領域の交差部分によってクリップされます。  
  
## <a name="quality-settings-in-nested-containers"></a>入れ子になったコンテナーの品質設定  
 入れ子になったコンテナーの品質設定 ( <xref:System.Drawing.Graphics.SmoothingMode%2A> 、 <xref:System.Drawing.Graphics.TextRenderingHint%2A> 、など) は累積されません。代わりに、コンテナーの品質設定によってオブジェクトの品質設定が一時的に置き換えられ <xref:System.Drawing.Graphics> ます。 新しいコンテナーを作成すると、そのコンテナーの品質設定が既定値に設定されます。 たとえば、 <xref:System.Drawing.Graphics> スムージングモードがのオブジェクトがあると <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> します。 コンテナーを作成すると、コンテナー内のスムージングモードが既定のスムージングモードになります。 コンテナーのスムージングモードは自由に設定できます。コンテナー内から描画された項目は、設定したモードに従って描画されます。 の呼び出しの後に描画 <xref:System.Drawing.Graphics.EndContainer%2A> される項目は、の呼び出しの前に配置されていたスムージングモード () に従って描画され <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> <xref:System.Drawing.Graphics.BeginContainer%2A> ます。  
  
## <a name="several-layers-of-nested-containers"></a>入れ子になったコンテナーの複数のレイヤー  
 オブジェクト内の1つのコンテナーに限定されません <xref:System.Drawing.Graphics> 。 前に入れ子になっている一連のコンテナーを作成できます。また、これらの入れ子になった各コンテナーのワールド変換、クリッピング領域、および品質設定を指定できます。 最も内側のコンテナーの内部から描画メソッドを呼び出すと、最も内側のコンテナーから順に、最も外側のコンテナーで終わる変換が適用されます。 最も内側のコンテナー内から描画された項目は、すべてのクリッピング領域の交差部分によってクリップされます。  
  
 次の例では、オブジェクトを作成 <xref:System.Drawing.Graphics> し、そのテキストレンダリングヒントをに設定し <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> ます。 このコードは2つのコンテナーを作成します。1つはもう一方に入れ子になっています。 外側のコンテナーのテキスト表示ヒントはに設定され、 <xref:System.Drawing.Text.TextRenderingHint.SingleBitPerPixel> 内部コンテナーのテキストレンダリングヒントはに設定され <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> ます。 このコードでは、内部コンテナーからの文字列、外側のコンテナーからの文字列、およびオブジェクト自体からの文字列をそれぞれ1つずつ描画します。 <xref:System.Drawing.Graphics>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#63](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#63)]
 [!code-vb[System.Drawing.MiscLegacyTopics#63](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#63)]  
  
 次の図は、3つの文字列を示しています。 内部コンテナーおよびオブジェクトから抽出された文字列 <xref:System.Drawing.Graphics> は、アンチエイリアシングによってスムージングされます。 外部コンテナーから描画された文字列は、 <xref:System.Drawing.Graphics.TextRenderingHint%2A> プロパティがに設定されているため、アンチエイリアシングによってスムージングされません <xref:System.Drawing.Text.TextRenderingHint.SingleBitPerPixel> 。  
  
 ![入れ子になったコンテナーから抽出された文字列を示す図。](./media/using-nested-graphics-containers/nested-containers-three-strings.png)  
  
## <a name="see-also"></a>関連項目

- <xref:System.Drawing.Graphics>
- [Graphics オブジェクトの状態の管理](managing-the-state-of-a-graphics-object.md)
