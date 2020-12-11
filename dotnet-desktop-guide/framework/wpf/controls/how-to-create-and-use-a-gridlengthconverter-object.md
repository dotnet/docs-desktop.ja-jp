---
title: '方法: GridLengthConverter オブジェクトを作成および使用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], creating [WPF], GridLengthConverter objects
ms.assetid: 5ab75911-e36a-4825-80e4-081c57e8e182
ms.openlocfilehash: 7cf6e12c1f3f9530d4616f0cfdecff1f07820615
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984823"
---
# <a name="how-to-create-and-use-a-gridlengthconverter-object"></a>方法: GridLengthConverter オブジェクトを作成および使用する
## <a name="example"></a>例  
 <xref:System.Windows.GridLengthConverter> のインスタンスを作成し、使用する方法の例を次に示します。 この例では、`changeCol` という名称のカスタム メソッドが定義されます。<xref:System.Windows.Controls.ListBoxItem> の <xref:System.Windows.Controls.ContentControl.Content%2A> を <xref:System.Windows.GridLength> のインスタンスに変換する <xref:System.Windows.GridLengthConverter> に <xref:System.Windows.Controls.ListBoxItem> がこのメソッドによって渡されます。 この変換後の値が次に、<xref:System.Windows.Controls.ColumnDefinition> 要素の <xref:System.Windows.Controls.ColumnDefinition.Width%2A> プロパティの値として返されます。  
  
 この例では、`changeColVal` という名前の 2 つ目のカスタム メソッドも定義されています。 このカスタム メソッドでは、<xref:System.Windows.Controls.Slider> の <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> が <xref:System.String> に変換され、その値が要素の <xref:System.Windows.Controls.ColumnDefinition.Width%2A> として <xref:System.Windows.Controls.ColumnDefinition> に返されます。  
  
 別の [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] ファイルで <xref:System.Windows.Controls.ListBoxItem> のコンテンツが定義されることにご注意ください。  
  
 [!code-csharp[gridlengthConverterGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/gridlengthConverterGrid/CSharp/Window1.xaml.cs#1)]
 [!code-vb[gridlengthConverterGrid#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridlengthConverterGrid/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.GridLengthConverter>
- <xref:System.Windows.GridLength>
