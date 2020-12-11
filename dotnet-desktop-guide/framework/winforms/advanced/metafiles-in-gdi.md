---
title: GDI+ でのメタファイル
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], metafiles
- GDI+, metafiles
- metafiles
ms.assetid: 51da872c-c783-440f-8bf6-1e580a966c31
ms.openlocfilehash: df54289722cf12bad840722c6eafdaa43279a5dc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96979771"
---
# <a name="metafiles-in-gdi"></a>GDI+ でのメタファイル
GDI + には、 <xref:System.Drawing.Imaging.Metafile> メタファイルを記録および表示できるようにクラスが用意されています。 メタファイルは、ベクターイメージとも呼ばれ、一連の描画コマンドと設定として格納されるイメージです。 オブジェクトに記録されたコマンドと設定は、 <xref:System.Drawing.Imaging.Metafile> メモリに格納することも、ファイルまたはストリームに保存することもできます。  
  
## <a name="metafile-formats"></a>メタファイル形式  
 GDI + では、次の形式で格納されたメタファイルを表示できます。  
  
- Windows メタファイル (WMF)  
  
- 拡張メタファイル (EMF)  
  
- EMF +  
  
 GDI + では、EMF および EMF + 形式でメタファイルを記録できますが、WMF 形式では記録できません。  
  
 EMF + は、GDI + レコードを格納できる EMF の拡張機能です。 EMF + 形式には、EMF + のみと EMF + Dual の2種類があります。 EMF + 唯一のメタファイルには GDI + レコードのみが含まれます。 このようなメタファイルは GDI + によって表示できますが、GDI では表示できません。 EMF + デュアルメタファイルには、GDI + および GDI レコードが含まれます。 EMF + デュアルメタファイル内の各 GDI + レコードは、代替 GDI レコードとペアになります。 このようなメタファイルは、GDI + または GDI によって表示できます。  
  
 次の例では、以前にファイルとして保存されたメタファイルを表示します。 メタファイルは、(100, 100) の左上隅に表示されます。  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#21)]  
  
## <a name="see-also"></a>関連項目

- [イメージ、ビットマップ、およびメタファイル](images-bitmaps-and-metafiles.md)
