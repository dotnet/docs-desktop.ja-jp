---
title: ワールド変換の使用
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], world transformation
- world transformation [Windows Forms], examples
ms.assetid: 1e717711-1361-448e-aa49-0f3ec43110c9
ms.openlocfilehash: f40d7e8cb814344365e8b88c2659751903b79d77
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981184"
---
# <a name="using-the-world-transformation"></a>ワールド変換の使用
ワールド変換は、クラスのプロパティです <xref:System.Drawing.Graphics> 。 ワールド変換を指定する数値は、 <xref:System.Drawing.Drawing2D.Matrix> 3 ×3行列を表すオブジェクトに格納されます。 <xref:System.Drawing.Drawing2D.Matrix>クラスとクラスには、 <xref:System.Drawing.Graphics> ワールド変換行列の数値を設定するためのいくつかのメソッドがあります。  
  
## <a name="different-types-of-transformations"></a>さまざまな種類の変換  
 次の例では、最初に50×50の四角形を作成し、原点 (0, 0) で検索します。 原点は、クライアント領域の左上隅にあります。  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.MiscLegacyTopics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#11)]  
  
 次のコードは、x 方向の1.75 係数で四角形を拡大し、y 方向の0.5 の係数で四角形を縮小するスケーリング変換を適用します。  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.MiscLegacyTopics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#12)]  
  
 結果として、x 方向ではなく、元の方向よりも短い四角形が生成されます。  
  
 スケーリングではなく四角形を回転させるには、次のコードを使用します。  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.MiscLegacyTopics#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#13)]  
  
 四角形を変換するには、次のコードを使用します。  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#14](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.MiscLegacyTopics#14](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#14)]  
  
## <a name="see-also"></a>関連項目

- <xref:System.Drawing.Drawing2D.Matrix>
- [座標系と変換](coordinate-systems-and-transformations.md)
- [マネージド GDI+ での変換の使用](using-transformations-in-managed-gdi.md)
