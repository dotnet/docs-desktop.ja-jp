---
title: グローバル変換とローカル変換
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- matrices [Windows Forms], using transformations
- transformations [Windows Forms], global
- transformations [Windows Forms], local
ms.assetid: b601d66d-d572-4f11-9d2e-92f0dc8893f3
ms.openlocfilehash: f62efb31e95b0797272997fadbc28459579a0de0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96979795"
---
# <a name="global-and-local-transformations"></a>グローバル変換とローカル変換
グローバル変換は、特定のオブジェクトによって描画されるすべてのアイテムに適用される変換です <xref:System.Drawing.Graphics> 。 一方、ローカル変換は、描画される特定の項目に適用される変換です。  
  
## <a name="global-transformations"></a>グローバル変換  
 グローバル変換を作成するには、 <xref:System.Drawing.Graphics> オブジェクトを構築し、そのプロパティを操作し <xref:System.Drawing.Graphics.Transform%2A> ます。 <xref:System.Drawing.Graphics.Transform%2A>プロパティは <xref:System.Drawing.Drawing2D.Matrix> オブジェクトであるため、アフィン変換の任意のシーケンスを保持できます。 プロパティに格納されている変換 <xref:System.Drawing.Graphics.Transform%2A> は、ワールド変換と呼ばれます。 クラスには <xref:System.Drawing.Graphics> <xref:System.Drawing.Graphics.MultiplyTransform%2A> 、、、 <xref:System.Drawing.Graphics.RotateTransform%2A> <xref:System.Drawing.Graphics.ScaleTransform%2A> 、およびという複合ワールド変換を構築するためのメソッドがいくつか用意されて <xref:System.Drawing.Graphics.TranslateTransform%2A> います。 次の例では、楕円を2回描画します。ワールド変換を作成する前に1回、その後に1回です。 変換は、最初に y 方向の0.5 係数で拡大縮小し、次に x 方向に50単位を変換してから30°回転します。  
  
 [!code-csharp[System.Drawing.CoordinateSystems#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.CoordinateSystems#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#21)]  
  
 次の図は、変換に関係するマトリックスを示しています。  
  
 ![変換](./media/aboutgdip05-art14.gif "AboutGdip05_art14")  
  
> [!NOTE]
> 前の例では、楕円は、クライアント領域の左上隅にある座標系の原点を中心に回転しています。 これにより、独自の中心点について楕円を回転する場合とは異なる結果が生成されます。  
  
## <a name="local-transformations"></a>ローカル変換  
 ローカル変換は、描画される特定の項目に適用されます。 たとえば、オブジェクトには、 <xref:System.Drawing.Drawing2D.GraphicsPath> <xref:System.Drawing.Drawing2D.GraphicsPath.Transform%2A> そのパスのデータポイントを変換できるメソッドがあります。 次の例では、変換なしの四角形と回転変換を含むパスを描画します。 (ワールド変換がないと仮定します)。  
  
 [!code-csharp[System.Drawing.CoordinateSystems#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.CoordinateSystems#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#22)]  
  
 ワールド変換とローカル変換を組み合わせて、さまざまな結果を得ることができます。 たとえば、ワールド変換を使用して座標系を変更し、ローカル変換を使用して、新しい座標系で描画されたオブジェクトの回転と拡大縮小を行うことができます。  
  
 クライアント領域の左端から200ピクセルの原点を持つ座標系と、クライアント領域の上端から150ピクセルを使用するとします。 さらに、測定単位をピクセルにする必要があるとします。 x 軸は右を指し、y 軸は上向きになります。 既定の座標系では y 軸が下向きになっているため、横軸全体で反射を行う必要があります。 次の図は、このようなリフレクションのマトリックスを示しています。  
  
 ![変換](./media/aboutgdip05-art15.gif "AboutGdip05_art15")  
  
 次に、200ユニットを右および150単位に変換する必要があるとします。  
  
 次の例では、オブジェクトのワールド変換を設定することによって、記述した座標系を確立し <xref:System.Drawing.Graphics> ます。  
  
 [!code-csharp[System.Drawing.CoordinateSystems#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.CoordinateSystems#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#23)]  
  
 次のコード (前の例の最後にあります) では、新しい座標系の原点の左下隅にある単一の四角形で構成されるパスを作成します。 四角形は、ローカル変換なしで1回、ローカル変換で1回入力します。 ローカル変換は、係数2の後に30度回転する水平方向のスケーリングで構成されます。  
  
 [!code-csharp[System.Drawing.CoordinateSystems#24](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#24)]
 [!code-vb[System.Drawing.CoordinateSystems#24](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#24)]  
  
 次の図は、新しい座標系と2つの四角形を示しています。  
  
 ![変換](./media/aboutgdip05-art16.gif "AboutGdip05_art16")  
  
## <a name="see-also"></a>関連項目

- [座標系と変換](coordinate-systems-and-transformations.md)
- [マネージド GDI+ での変換の使用](using-transformations-in-managed-gdi.md)
