---
title: '方法: ファイルに関連付けられているアイコンを抽出する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a file name and its file type icon in a ListView control [Windows Forms]
- file name extension icons [Windows Forms], displaying in a ListView
- extracting icons associated with a file type [Windows Forms]
ms.assetid: 88e2ad8b-c34f-415a-84f2-dad756b5c928
ms.openlocfilehash: 28769144b0e1c631a31c3c541747a6215f861d0e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981343"
---
# <a name="how-to-extract-the-icon-associated-with-a-file-in-windows-forms"></a>方法: Windows フォームでファイルに関連付けられているアイコンを抽出する
多くのファイルには、関連付けられたファイルの種類を視覚的に表現するアイコンが組み込まれています。 たとえば、Microsoft Word 文書には、それらを Word 文書として識別するアイコンが含まれています。 リストコントロールまたはテーブルコントロールにファイルを表示する場合、各ファイル名の横にあるファイルの種類を表すアイコンを表示することができます。 これは、メソッドを使用して簡単に行うことができ <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A> ます。  
  
## <a name="example"></a>例  
 次のコード例は、ファイルに関連付けられたアイコンを抽出し、ファイル名とそれに関連付けられているアイコンをコントロールに表示する方法を示して <xref:System.Windows.Forms.ListView> います。  
  
 [!code-csharp[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 この例をコンパイルするには、次のようにします。  
  
- 前のコードを Windows フォームに貼り付け、 `ExtractAssociatedIconExample` フォームのコンストラクターまたはイベント処理メソッドからメソッドを呼び出し <xref:System.Windows.Forms.Form.Load> ます。  
  
     フォームが名前空間をインポートすることを確認する必要があり <xref:System.IO> ます。  
  
## <a name="see-also"></a>関連項目

- [イメージ、ビットマップ、およびメタファイル](images-bitmaps-and-metafiles.md)
- [ListView コントロール](../controls/listview-control-windows-forms.md)
