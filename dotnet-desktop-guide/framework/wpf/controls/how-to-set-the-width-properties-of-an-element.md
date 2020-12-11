---
title: '方法: 要素の Width プロパティを設定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- width properties [WPF]
- Panel control [WPF], width properties of elements
ms.assetid: 6ee04a9d-63f0-4f5b-a406-0a8cd4c35729
ms.openlocfilehash: fcdb8d58c17137d22edd4ee8cf6768c5d7def7c5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96979987"
---
# <a name="how-to-set-the-width-properties-of-an-element"></a>方法: 要素の Width プロパティを設定する
## <a name="example"></a>例  
 この例は、[!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] の 4 つの幅に関連するプロパティ間のレンダリング動作の違いを視覚的に示しています。  
  
 <xref:System.Windows.FrameworkElement> クラスでは、要素の幅の特性を記述する 4 つのプロパティが公開されています。 これらの 4 つのプロパティは競合する可能性があります。その場合、優先される値は次のように決定されます。<xref:System.Windows.FrameworkElement.MinWidth%2A> 値は <xref:System.Windows.FrameworkElement.MaxWidth%2A> 値より優先され、次に <xref:System.Windows.FrameworkElement.Width%2A> 値より優先されます。 4 つ目のプロパティの <xref:System.Windows.FrameworkElement.ActualWidth%2A> は読み取り専用であり、レイアウト プロセスとの相互作用によって決定された実際の幅が報告されます。  
  
 次の [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] の例では、<xref:System.Windows.Shapes.Rectangle> 要素 (`rect1`) を <xref:System.Windows.Controls.Canvas> の子として描画します。 <xref:System.Windows.FrameworkElement.MinWidth%2A>、<xref:System.Windows.FrameworkElement.MaxWidth%2A>、および <xref:System.Windows.FrameworkElement.Width%2A> のプロパティ値を表す一連の <xref:System.Windows.Controls.ListBox> 要素を使用して、<xref:System.Windows.Shapes.Rectangle> の width プロパティを変更できます。 この方法で、各プロパティの優先順位が視覚的に表示されます。  
  
 [!code-xaml[WidthMinWidthMaxWidth#1](~/samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#1)]  
[!code-xaml[WidthMinWidthMaxWidth#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#2)]  
  
 次のコードビハインドの例では、<xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> イベントによって発生するイベントを処理します。 各カスタム メソッドは、<xref:System.Windows.Controls.ListBox> から入力を受け取り、値を <xref:System.Double> として解析し、指定された幅に関連するプロパティに値を適用します。 幅の値も文字列に変換され、さまざまな <xref:System.Windows.Controls.TextBlock> 要素に書き込まれます (これらの要素の定義は、選択した XAML には表示されません)。  
  
 [!code-csharp[WidthMinWidthMaxWidth#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml.cs#3)]
 [!code-vb[WidthMinWidthMaxWidth#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WidthMinWidthMaxWidth/VisualBasic/Window1.xaml.vb#3)]  
  
 サンプル全体については、[Width プロパティの比較のサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Elements/WidthProperties)を参照してください。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.FrameworkElement.ActualWidth%2A>
- <xref:System.Windows.FrameworkElement.MaxWidth%2A>
- <xref:System.Windows.FrameworkElement.MinWidth%2A>
- <xref:System.Windows.FrameworkElement.Width%2A>
- [パネルの概要](panels-overview.md)
- [要素の Height プロパティを設定する](how-to-set-the-height-properties-of-an-element.md)
- [Width プロパティの比較のサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Elements/WidthProperties)
