---
title: '方法: フォント ファミリとフォントを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- font families [Windows Forms], constructing
- fonts [Windows Forms], constructing
ms.assetid: d3a4a223-9492-4b54-9afd-db1c31c3cefd
ms.openlocfilehash: 2d609525858c7a8ff77c0b86900b4fc7d6b4e39a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974428"
---
# <a name="how-to-construct-font-families-and-fonts"></a>方法: フォント ファミリとフォントを作成する
GDI + は、同じタイプフェイスを持つフォントをグループ化しますが、スタイルはフォントファミリによって異なります。 たとえば、Arial フォントファミリには、次のフォントが含まれています。  
  
- Arial 通常  
  
- Arial 太字  
  
- Arial 斜体  
  
- Arial 太字斜体  
  
 GDI + では、標準、太字、斜体、太字の斜体の4つのスタイルを使用してファミリを形成します。 *ナロー* や *丸い* などの形容詞は、スタイルとは見なされません。代わりに、ファミリ名の一部になります。 たとえば、Arial ナローは、次のメンバーを持つフォントファミリです。  
  
- Arial ナロー標準  
  
- Arial ナロー Bold  
  
- Arial ナロー斜体  
  
- Arial ナロー太字斜体  
  
 GDI + を使用してテキストを描画するには、オブジェクトとオブジェクトを構築する必要があり <xref:System.Drawing.FontFamily> <xref:System.Drawing.Font> ます。 <xref:System.Drawing.FontFamily>オブジェクトはタイプフェイス (Arial など) を指定し、オブジェクトは <xref:System.Drawing.Font> サイズ、スタイル、および単位を指定します。  
  
## <a name="example"></a>例  
 次の例では、サイズが16ピクセルの通常スタイルの Arial フォントを構築します。 次のコードでは、コンストラクターに渡される最初の引数 <xref:System.Drawing.Font.%23ctor%2A> は <xref:System.Drawing.FontFamily> オブジェクトです。 2番目の引数は、4番目の引数によって識別される単位で計測されるフォントのサイズを指定します。 3番目の引数は、スタイルを識別します。  
  
 <xref:System.Drawing.GraphicsUnit.Pixel> は列挙体のメンバーで、 <xref:System.Drawing.GraphicsUnit> <xref:System.Drawing.FontStyle.Regular> は列挙体のメンバーです <xref:System.Drawing.FontStyle> 。  
  
 [!code-csharp[System.Drawing.FontsAndText#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.FontsAndText#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、のパラメーターであるを必要とし <xref:System.Windows.Forms.PaintEventHandler> ます。  
  
## <a name="see-also"></a>関連項目

- [フォントとテキストの使用](using-fonts-and-text.md)
- [Windows フォームにおけるグラフィックスと描画](graphics-and-drawing-in-windows-forms.md)
