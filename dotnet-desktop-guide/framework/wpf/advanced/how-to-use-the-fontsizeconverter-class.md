---
title: '方法: FontSizeConverter クラスを使用する'
ms.date: 03/30/2017
helpviewer_keywords:
- FontSizeConverter objects [WPF]
- typography [WPF], FontSizeConverter objects
ms.assetid: 3b0592bd-7223-4860-a108-a5d72f3a9178
ms.openlocfilehash: b4662ef60866150008d84f22de44852b65373282
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985192"
---
# <a name="how-to-use-the-fontsizeconverter-class"></a>方法: FontSizeConverter クラスを使用する
## <a name="example"></a>例  
 この例では、<xref:System.Windows.FontSizeConverter> のインスタンスを作成し、それを使用してフォント サイズを変更する方法を示します。  
  
 この例では、`changeSize` という名前のカスタム メソッドを定義します。このメソッドでは、別の [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] ファイルで定義されている <xref:System.Windows.Controls.ListBoxItem> のコンテンツを <xref:System.Double> のインスタンスに変換し、その後で <xref:System.String> に変換します。 このメソッドでは、<xref:System.Windows.Controls.ListBoxItem> を <xref:System.Windows.FontSizeConverter> オブジェクトに渡します。これにより、<xref:System.Windows.Controls.ListBoxItem> の <xref:System.Windows.Controls.ContentControl.Content%2A> が <xref:System.Double> のインスタンスに変換されます。 次に、この値は、<xref:System.Windows.Controls.TextBlock> 要素の <xref:System.Windows.Controls.TextBlock.FontSize%2A> プロパティの値として返されます。  
  
 この例では、`changeFamily` という名前の 2 番目のカスタム メソッドも定義されています。 このメソッドでは、<xref:System.Windows.Controls.ListBoxItem> の <xref:System.Windows.Controls.ContentControl.Content%2A> が <xref:System.String> に変換され、その値が <xref:System.Windows.Controls.TextBlock> 要素の <xref:System.Windows.Controls.TextBlock.FontFamily%2A> プロパティに渡されます。  
  
 この例は実行できません。  
  
 [!code-csharp[FontSizeConverter#1](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSizeConverter/CSharp/Window1.xaml.cs#1)]  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.FontSizeConverter>
