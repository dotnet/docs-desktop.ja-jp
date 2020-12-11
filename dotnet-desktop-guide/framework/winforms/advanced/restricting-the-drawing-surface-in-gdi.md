---
title: GDI+ での描画サーフェイスの制限
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, clipping
- clipping [Windows Forms], using GDI+
- GDI+, restricting drawing surface
ms.assetid: 8b5f71d9-d2f0-4540-9c41-740f90fd4c26
ms.openlocfilehash: d0508166f905b45789ce638b03d0747dd6fa904e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981648"
---
# <a name="restricting-the-drawing-surface-in-gdi"></a>GDI+ での描画サーフェイスの制限
クリッピングには、特定の四角形または領域への描画の制限が含まれます。 次の図は、ハート形の領域にクリップされた文字列 "Hello" を示しています。  
  
 ![制限付き描画面](./media/aboutgdip02-art30.gif "AboutGdip02_Art30")  
  
## <a name="clipping-with-regions"></a>領域でのクリッピング  
 領域はパスから構築でき、パスには文字列のアウトラインを含めることができるため、表示されているテキストを使用してクリッピングを行うことができます。 次の図は、テキスト文字列の内部にクリップされた同心円の楕円のセットを示しています。  
  
 ![制限付き描画面](./media/aboutgdip02-art31.gif "AboutGdip02_Art31")  
  
 クリッピングを使用して描画するには、オブジェクトを作成し、 <xref:System.Drawing.Graphics> その <xref:System.Drawing.Graphics.Clip%2A> プロパティを設定して、同じオブジェクトの描画メソッドを呼び出し <xref:System.Drawing.Graphics> ます。  
  
 [!code-csharp[LinesCurvesAndShapes#91](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#91)]
 [!code-vb[LinesCurvesAndShapes#91](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#91)]  
  
## <a name="see-also"></a>関連項目

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Region?displayProperty=nameWithType>
- [直線、曲線、および図形](lines-curves-and-shapes.md)
- [領域の使用](using-regions.md)
