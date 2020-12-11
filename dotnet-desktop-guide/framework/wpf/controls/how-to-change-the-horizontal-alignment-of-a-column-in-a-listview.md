---
title: '方法: ListView の列の水平方向の配置を変更する'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], horizontal alignment [WPF]
ms.assetid: b9573e44-9dad-4d14-939c-7859ca372758
ms.openlocfilehash: cdf479fc9f84f88fccc877e9fdf8ca56d53c1c4b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984455"
---
# <a name="how-to-change-the-horizontal-alignment-of-a-column-in-a-listview"></a>方法: ListView の列の水平方向の配置を変更する
既定では、<xref:System.Windows.Controls.ListViewItem> の各列のコンテンツは左揃えになっています。 各列の配置を変更するには、<xref:System.Windows.DataTemplate> を指定して、<xref:System.Windows.DataTemplate> 内の要素の <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> プロパティを設定します。 このトピックでは、<xref:System.Windows.Controls.ListView> が既定でどのようにコンテンツを配置するのかについてと、<xref:System.Windows.Controls.ListView> 内の 1 つの列の配置を変更する方法について説明します。  
  
## <a name="example"></a>例  
 次の例では、`Title` 列と `ISBN` 列のデータが左揃えになっています。  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 `ISBN` 列の配置を変更するには、各 <xref:System.Windows.Controls.ListViewItem> の <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> プロパティが <xref:System.Windows.HorizontalAlignment.Stretch> となるように指定する必要があります。これにより、各 <xref:System.Windows.Controls.ListViewItem> 内の要素は、各列の幅全体にわたって、または幅全体に沿って配置されます。 <xref:System.Windows.Controls.ListView> はデータ ソースにバインドされるため、<xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> を設定するスタイルを作成する必要があります。 次に、<xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> プロパティを使用する代わりに、<xref:System.Windows.DataTemplate> を使用してコンテンツを表示する必要があります。 各テンプレートの `ISBN` を表示するには、<xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> プロパティが <xref:System.Windows.HorizontalAlignment.Right> に設定されている <xref:System.Windows.Controls.TextBlock> のみを <xref:System.Windows.DataTemplate> に含めることができます。  
  
 次の例では、`ISBN` 列を右揃えにするために必要なスタイルと <xref:System.Windows.DataTemplate> を定義し、<xref:System.Windows.DataTemplate> を参照するように <xref:System.Windows.Controls.GridViewColumn> を変更します。  
  
 [!code-xaml[ListViewHowTos#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#3)]  
[!code-xaml[ListViewHowTos#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#4)]  
  
## <a name="see-also"></a>関連項目

- [データ バインディングの概要](/dotnet/desktop-wpf/data/data-binding-overview)
- [データ テンプレートの概要](../data/data-templating-overview.md)
- [XMLDataProvider と XPath クエリを使用して XML データにバインドする](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [ListView の概要](listview-overview.md)
