---
title: GDI+ での領域
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, regions
- drawing [Windows Forms], regions
- regions
ms.assetid: 52184f9b-16dd-4bbd-85be-029112644ceb
ms.openlocfilehash: 33d4f4ecca7b9d777fa4eab5b6d031de10f03ccc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96979717"
---
# <a name="regions-in-gdi"></a>GDI+ での領域
領域は、出力デバイスの表示領域の一部です。 領域は、単純な (単一の四角形) か、複雑な (多角形と閉じた曲線の組み合わせ) ことができます。 次の図は、2つの領域を示しています。1つは四角形から構築され、もう1つはパスから構築されます。  
  
 ![リージョン](./media/aboutgdip02-art27.gif "AboutGdip02_Art27")  
  
## <a name="using-regions"></a>領域の使用  
 領域は、多くの場合、クリッピングとヒットテストに使用されます。 クリッピングでは、表示領域の特定の領域 (通常は更新が必要な部分) に描画を制限します。 ヒットテストでは、マウスボタンが押されたときにカーソルが画面の特定の領域内にあるかどうかを確認します。  
  
 領域は、四角形またはパスから構築できます。 また、既存の領域を組み合わせることによって、複雑な領域を作成することもできます。 クラスには <xref:System.Drawing.Region> 、領域を結合するための次のメソッドが用意されています。、、 <xref:System.Drawing.Region.Intersect%2A> 、、 <xref:System.Drawing.Region.Union%2A> <xref:System.Drawing.Region.Xor%2A> <xref:System.Drawing.Region.Exclude%2A> および <xref:System.Drawing.Region.Complement%2A> 。  
  
 2つのリージョンの交差部分は、両方のリージョンに属するすべてのポイントの集合です。 共用体は、一方または両方または両方の領域に属するすべての点のセットです。 領域の補数は、領域内に存在しないすべてのポイントのセットです。 次の図は、前の図に示した2つの領域の交差と和集合を示しています。  
  
 ![リージョン](./media/aboutgdip02-art28.gif "AboutGdip02_Art28")  
  
 領域 <xref:System.Drawing.Region.Xor%2A> のペアに適用されたメソッドは、ある領域に属するすべての点を含む領域を生成しますが、両方は含まれません。 メソッドは、 <xref:System.Drawing.Region.Exclude%2A> 領域のペアに適用され、2番目の領域にはない最初の領域のすべての点を含む領域を生成します。 次の図は、 <xref:System.Drawing.Region.Xor%2A> <xref:System.Drawing.Region.Exclude%2A> このトピックの冒頭に示した2つの領域にメソッドとメソッドを適用した結果として得られる領域を示しています。  
  
 ![リージョン](./media/aboutgdip02-art29.gif "AboutGdip02_Art29")  
  
 領域にデータを格納するには、オブジェクト、オブジェクト、 <xref:System.Drawing.Graphics> <xref:System.Drawing.Brush> およびオブジェクトが必要 <xref:System.Drawing.Region> です。 <xref:System.Drawing.Graphics>オブジェクトはメソッドを提供し、 <xref:System.Drawing.Graphics.FillRegion%2A> <xref:System.Drawing.Brush> オブジェクトは color や pattern などの塗りつぶしの属性を格納します。 次の例では、純色で領域を塗りつぶします。  
  
 [!code-csharp[LinesCurvesAndShapes#61](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#61)]
 [!code-vb[LinesCurvesAndShapes#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#61)]  
  
## <a name="see-also"></a>関連項目

- <xref:System.Drawing.Region?displayProperty=nameWithType>
- [直線、曲線、および図形](lines-curves-and-shapes.md)
- [領域の使用](using-regions.md)
