---
title: '方法: ToolStripTextBox を拡大して ToolStrip の残りの幅に合わせる'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text boxes [Windows Forms], stretching in ToolStrip control [Windows Forms]
- ToolStrip control [Windows Forms], stretching a text box
ms.assetid: 0e610fbf-85fe-414c-900c-9704a5dd5cc6
ms.openlocfilehash: c60cc2a377f08a73159f25b2ab5f2812d41f0c10
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982428"
---
# <a name="how-to-stretch-a-toolstriptextbox-to-fill-the-remaining-width-of-a-toolstrip-windows-forms"></a>方法 : ToolStripTextBox を拡大して ToolStrip の残りの幅に合わせる (Windows フォーム)
<xref:System.Windows.Forms.ToolStrip.Stretch%2A>コントロールのプロパティをに設定すると、コントロールによって、コンテナーのサイズが変更さ <xref:System.Windows.Forms.ToolStrip> `true` れたときに、そのコンテナーが端から端に挿入され、サイズが変更されます。 この構成では、などのコントロールの項目を拡張して、 <xref:System.Windows.Forms.ToolStripTextBox> 使用可能な領域を塗りつぶすことや、コントロールのサイズを変更したときのサイズを変更することが役に立つ場合があります。 この拡大は、Microsoft® Internet Explorer のアドレスバーと同様の外観と動作を実現する場合などに便利です。  
  
## <a name="example"></a>例  
 次のコード例では、から派生したクラスを <xref:System.Windows.Forms.ToolStripTextBox> と呼び `ToolStripSpringTextBox` ます。 このクラスは、 <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> <xref:System.Windows.Forms.ToolStrip> 他のすべての項目の合計幅が減算された後に、メソッドをオーバーライドして、親コントロールの使用可能な幅を計算します。 このコード例には、 <xref:System.Windows.Forms.Form> 新しい動作を示すクラスとクラスも用意されて `Program` います。  
  
 [!code-csharp[ToolStripSpringTextBox#00](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripSpringTextBox/cs/ToolStripSpringTextBox.cs#00)]
 [!code-vb[ToolStripSpringTextBox#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripSpringTextBox/vb/ToolStripSpringTextBox.vb#00)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 この例で必要な要素は次のとおりです。  
  
- System、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.Stretch%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripTextBox>
- <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A?displayProperty=nameWithType>
- [ToolStrip コントロールのアーキテクチャ](toolstrip-control-architecture.md)
- [方法: StatusStrip 内で Spring プロパティを対話的に使用する](how-to-use-the-spring-property-interactively-in-a-statusstrip.md)
