---
title: '方法: 領域でヒット テストを使用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [Windows Forms], using regions
- regions [Windows Forms], hit testing
ms.assetid: 3a4c07cb-a40a-4d14-ad35-008f531910a8
ms.openlocfilehash: 136f15f1364fb2aed791b4a61d0f11411b055967
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981227"
---
# <a name="how-to-use-hit-testing-with-a-region"></a>方法: 領域でヒット テストを使用する
ヒットテストの目的は、カーソルが特定のオブジェクト (アイコンやボタンなど) 上にあるかどうかを判断することです。  
  
## <a name="example"></a>例  
 次の例では、2つの四角形領域の和集合を形成することによって、正形の領域を作成します。 変数が `point` 最新のクリックの場所を保持していると仮定します。 コードによって、 `point` がプラス形の領域にあるかどうかが確認されます。 点が領域内にある場合 (ヒット)、領域は不透明な赤のブラシで塗りつぶされます。 それ以外の場合、領域には半透明の赤のブラシが挿入されます。  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.MiscLegacyTopics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、のパラメーターであるを必要とし <xref:System.Windows.Forms.PaintEventHandler> ます。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Drawing.Region>
- [GDI+ での領域](regions-in-gdi.md)
- [方法: 領域でクリッピングを使用する](how-to-use-clipping-with-a-region.md)
