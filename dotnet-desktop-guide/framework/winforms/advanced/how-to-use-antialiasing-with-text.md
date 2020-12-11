---
title: '方法: テキストでのアンチエイリアシングの使用'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings [Windows Forms], smoothing drawn
- antialiasing [Windows Forms], using with text
- text [Windows Forms], smoothing
- text [Windows Forms], antialiasing
- strings [Windows Forms], antialiasing when drawing
ms.assetid: 48fc34f3-f236-4b01-a0cb-f0752e6d22ae
ms.openlocfilehash: 632ed329173d134495a424b34ca7c71e402607bf
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981728"
---
# <a name="how-to-use-antialiasing-with-text"></a>方法: テキストでのアンチエイリアシングの使用
*アンチエイリアシング* とは、描画されたグラフィックスとテキストのギザギザの端を滑らかにして、外観や読みやすさを向上させることを指します。 マネージ GDI + クラスを使用すると、高品質のアンチエイリアシングテキストと、低品質のテキストを表示できます。 通常、品質の高いレンダリングは、低品質のレンダリングよりも処理時間が長くなります。 テキスト品質レベルを設定するには、 <xref:System.Drawing.Graphics.TextRenderingHint%2A> のプロパティを <xref:System.Drawing.Graphics> 列挙体のいずれかの要素に設定します。 <xref:System.Drawing.Text.TextRenderingHint>  
  
## <a name="example"></a>例  
 次のコード例では、2つの異なる品質設定を使用してテキストを描画します。  
  
 [!code-csharp[System.Drawing.FontsAndText#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.FontsAndText#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#21)]  

 次の図は、コード例の出力を示しています。  
  
 ![2つの異なる品質設定のテキストを表示するスクリーンショット。](./media/how-to-use-antialiasing-with-text/antialiasing-text-quality-settings.png)  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 上記のコード例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、のパラメーターであるを必要とし <xref:System.Windows.Forms.PaintEventHandler> ます。  
  
## <a name="see-also"></a>関連項目

- [フォントとテキストの使用](using-fonts-and-text.md)
