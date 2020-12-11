---
title: '方法: サムネイル イメージを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thumbnail images [Windows Forms], creating
- images [Windows Forms], creating thumbnails
ms.assetid: e956242a-1e5b-4217-a3cf-5f3fb45d00ba
ms.openlocfilehash: 786a92d99f5e7a0c27f502efa9a5fe617ac4d4d6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974415"
---
# <a name="how-to-create-thumbnail-images"></a>方法: サムネイル イメージを作成する
サムネイル画像は、イメージの小さなバージョンです。 オブジェクトのメソッドを呼び出すことにより、サムネイルイメージを作成でき <xref:System.Drawing.Image.GetThumbnailImage%2A> <xref:System.Drawing.Image> ます。  
  
## <a name="example"></a>例  
 次の例では、 <xref:System.Drawing.Image> JPG ファイルからオブジェクトを構築します。 元のイメージの幅は640ピクセル、高さは479ピクセルです。 このコードでは、幅100ピクセル、高さ100ピクセルのサムネイル画像を作成します。  
  
 サムネイル画像を次の図に示します。  
  
 ![出力サムネイルを示すスクリーンショット。](./media/how-to-create-thumbnail-images/construct-thumbnail-image.png)  
  
> [!NOTE]
> この例では、コールバックメソッドが宣言されていますが、使用されていません。 これは、GDI + のすべてのバージョンをサポートします。  
  
 [!code-csharp[System.Drawing.WorkingWithImages#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.WorkingWithImages#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。 この例を実行するには、次の手順に従います。  
  
1. 新しい Windows フォーム アプリケーションを作成します。  
  
2. サンプルコードをフォームに追加します。  
  
3. フォームのイベントのハンドラーを作成します。 <xref:System.Windows.Forms.Control.Paint>  
  
4. ハンドラーで <xref:System.Windows.Forms.Control.Paint> 、メソッドを呼び出し、 `GetThumbnail` `e` にを渡し <xref:System.Windows.Forms.PaintEventArgs> ます。  
  
5. サムネイルを作成するイメージファイルを検索します。  
  
6. メソッドで `GetThumbnail` 、イメージのパスとファイル名を指定します。  
  
7. F5 キーを押して、例を実行します。  
  
     100の100サムネイル画像がフォームに表示されます。  
  
## <a name="see-also"></a>関連項目

- [イメージ、ビットマップ、およびメタファイル](images-bitmaps-and-metafiles.md)
- [イメージ、ビットマップ、アイコン、およびメタファイルの操作](working-with-images-bitmaps-icons-and-metafiles.md)
