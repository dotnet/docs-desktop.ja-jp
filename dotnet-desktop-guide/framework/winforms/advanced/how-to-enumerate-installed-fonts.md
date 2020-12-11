---
title: '方法: インストールされているフォントを列挙する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [Windows Forms], enumerating installed
- examples [Windows Forms], fonts
ms.assetid: 26d74ef5-0f39-4eeb-8d20-00e66e014abe
ms.openlocfilehash: 92f27399cce9e03a4679c8a34fbdafcf28c32252
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981859"
---
# <a name="how-to-enumerate-installed-fonts"></a>方法: インストールされているフォントを列挙する
クラスは、 <xref:System.Drawing.Text.InstalledFontCollection> 抽象基本クラスから継承され <xref:System.Drawing.Text.FontCollection> ます。 オブジェクトを使用し <xref:System.Drawing.Text.InstalledFontCollection> て、コンピューターにインストールされているフォントを列挙できます。 <xref:System.Drawing.Text.FontCollection.Families%2A>オブジェクトのプロパティ <xref:System.Drawing.Text.InstalledFontCollection> は、オブジェクトの配列です <xref:System.Drawing.FontFamily> 。  
  
## <a name="example"></a>例  
 次の例では、コンピューターにインストールされているすべてのフォントファミリの名前を一覧表示します。 このコードは、 <xref:System.Drawing.FontFamily.Name%2A> <xref:System.Drawing.FontFamily> プロパティによって返される配列内の各オブジェクトのプロパティを取得し <xref:System.Drawing.Text.FontCollection.Families%2A> ます。 ファミリ名が取得されると、コンマ区切りのリストを形成するために連結されます。 次に、 <xref:System.Drawing.Graphics.DrawString%2A> クラスのメソッドは、 <xref:System.Drawing.Graphics> コンマ区切りのリストを四角形に描画します。  
  
 コード例を実行すると、出力は次の図に示すようになります。  
  
 ![インストールされているフォントファミリを示すスクリーンショット。](./media/how-to-enumerate-installed-fonts/list-installed-font-families.png)  
  
 [!code-csharp[System.Drawing.FontsAndText#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.FontsAndText#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、のパラメーターであるを必要とし <xref:System.Windows.Forms.PaintEventHandler> ます。 また、名前空間をインポートする必要があり <xref:System.Drawing.Text> ます。  
  
## <a name="see-also"></a>関連項目

- [フォントとテキストの使用](using-fonts-and-text.md)
