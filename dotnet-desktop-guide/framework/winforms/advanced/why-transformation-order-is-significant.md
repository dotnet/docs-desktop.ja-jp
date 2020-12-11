---
title: 変換順序が重要となる理由
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], order significance
ms.assetid: 37d5f9dc-a5cf-4475-aa5d-34d714e808a9
ms.openlocfilehash: 08927ebaa460e19e558dce22f39c13c31f0e49d0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981148"
---
# <a name="why-transformation-order-is-significant"></a>変換順序が重要となる理由
1つの <xref:System.Drawing.Drawing2D.Matrix> オブジェクトには、1つの変換または一連の変換を格納できます。 後者は複合変換と呼ばれます。 複合変換の行列は、個々の変換の行列を乗算することによって取得されます。  
  
## <a name="composite-transform-examples"></a>複合変換の例  
 複合変換では、個々の変換の順序が重要になります。 たとえば、最初に回転した後、スケーリングしてから平行移動した場合、最初に変換してから回転してからスケールする場合とは異なる結果が得られます。 GDI + では、複合変換は左から右に構築されます。 S、R、および T がそれぞれスケール、回転、および変換の各マトリックスである場合、product SRT (この順序で) は、最初にスケーリングし、次に回転してから変換する複合変換のマトリックスです。 Product SRT によって生成されるマトリックスは、product TRS によって生成されるマトリックスとは異なります。  
  
 理由の1つは、回転やスケーリングなどの変換が、座標系の原点に対して行われるということです。 原点から中央に配置されているオブジェクトをスケーリングすると、原点から離れた位置にあるオブジェクトをスケーリングする場合とは異なる結果が生成されます。 同様に、原点から中央に配置されているオブジェクトを回転すると、原点から離れた位置にあるオブジェクトを回転した場合とは異なる結果が生成されます。  
  
 次の例では、スケール、回転、および平行移動 (この順序で) を組み合わせて、複合変換を作成します。 メソッドに渡される引数は、 <xref:System.Drawing.Drawing2D.MatrixOrder.Append> <xref:System.Drawing.Graphics.RotateTransform%2A> 回転がスケーリングに従うことを示します。 同様に、メソッドに渡される引数は、 <xref:System.Drawing.Drawing2D.MatrixOrder.Append> <xref:System.Drawing.Graphics.TranslateTransform%2A> 平行移動が回転に従うことを示します。 <xref:System.Drawing.Drawing2D.MatrixOrder.Append> および <xref:System.Drawing.Drawing2D.MatrixOrder.Prepend> は列挙体のメンバーです <xref:System.Drawing.Drawing2D.MatrixOrder> 。  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.MiscLegacyTopics#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#21)]  
  
 次の例では、前の例と同じメソッドを呼び出しますが、呼び出しの順序は逆になります。 結果として得られる操作の順序は最初に変換され、次に回転してから、スケーリングが行われます。これにより、最初のスケールとは異なる結果が生成され、回転してから平行移動します。  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.MiscLegacyTopics#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#22)]  
  
 複合変換で個々の変換の順序を逆にする方法の1つは、メソッド呼び出しの順序を逆にすることです。 操作の順序を制御するもう1つの方法は、マトリックスの順序引数を変更することです。 次の例は、前の例と同じですが、がに変更されている点が異なり <xref:System.Drawing.Drawing2D.MatrixOrder.Append> <xref:System.Drawing.Drawing2D.MatrixOrder.Prepend> ます。 行列乗算は、順序 SRT で実行されます。ここで、S、R、および T は、それぞれスケール、回転、および平行移動のマトリックスです。 複合変換の順序は、最初にスケールし、次に回転してから平行移動します。  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.MiscLegacyTopics#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#23)]  
  
 直前の例の結果は、このトピックの最初の例の結果と同じです。 これは、メソッド呼び出しの順序と行列乗算の順序を逆にしたためです。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Drawing.Drawing2D.Matrix>
- [座標系と変換](coordinate-systems-and-transformations.md)
- [マネージド GDI+ での変換の使用](using-transformations-in-managed-gdi.md)
