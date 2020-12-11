---
title: '方法: 領域でクリッピングを使用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regions [Windows Forms], clipping
- regions [Windows Forms], restricting drawing surface
ms.assetid: 43d121b4-e14c-4901-b25c-2d6c25ba4e29
ms.openlocfilehash: e62be137b36a2f369c02151466154f6b3bab090b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981239"
---
# <a name="how-to-use-clipping-with-a-region"></a>方法: 領域でクリッピングを使用する
クラスのプロパティの1つ <xref:System.Drawing.Graphics> はクリップ領域です。 特定のオブジェクトによって実行 <xref:System.Drawing.Graphics> されるすべての描画は、そのオブジェクトのクリップ領域に制限され <xref:System.Drawing.Graphics> ます。 クリップ領域は、メソッドを呼び出すことによって設定でき <xref:System.Drawing.Graphics.SetClip%2A> ます。  
  
## <a name="example"></a>例  
 次の例では、1つの多角形で構成されるパスを構築します。 次に、そのパスに基づいて、領域を構築します。 領域は <xref:System.Drawing.Graphics.SetClip%2A> オブジェクトのメソッドに渡され、 <xref:System.Drawing.Graphics> 2 つの文字列が描画されます。  
  
 次の図は、クリップされた文字列を示しています。  
  
 ![クリップされた文字列を示すスクリーンショット。](./media/how-to-use-clipping-with-a-region/clipped-strings-polygon.png)  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.MiscLegacyTopics#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、のパラメーターであるを必要とし <xref:System.Windows.Forms.PaintEventHandler> ます。  
  
## <a name="see-also"></a>関連項目

- [GDI+ での領域](regions-in-gdi.md)
- [領域の使用](using-regions.md)
