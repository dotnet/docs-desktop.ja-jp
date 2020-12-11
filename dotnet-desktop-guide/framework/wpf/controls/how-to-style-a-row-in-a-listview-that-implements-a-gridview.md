---
title: '方法: GridView を使用する ListView で行のスタイルを適用する'
ms.date: 03/30/2017
helpviewer_keywords:
- GridView controls [WPF], styling rows
- styling rows in ListViews implementing GridViews [WPF]
- ListView controls [WPF], styling rows with GridViews
ms.assetid: 2e406ba2-70a0-4e62-841f-0934859de76e
ms.openlocfilehash: 586c549cca6ef3089b37427c7983bb39e56509bf
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974662"
---
# <a name="how-to-style-a-row-in-a-listview-that-implements-a-gridview"></a>方法: GridView を実装する ListView で行のスタイルを設定する
この例では、モードを使用するコントロールの行のスタイルを指定する方法を示し <xref:System.Windows.Controls.ListView> <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.ListView.View%2A> ます。  
  
## <a name="example"></a>例  
 <xref:System.Windows.Controls.ListView> コントロールの行のスタイルを設定するには、<xref:System.Windows.Controls.ListView> コントロールで <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> を設定します。 <xref:System.Windows.Controls.ListViewItem> オブジェクトとして表される項目のスタイルを設定します。 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> を使用して、行の内容を表示するために使用される <xref:System.Windows.Controls.ControlTemplate> オブジェクトを参照します。  
  
 以下の例の抜粋元である完全なサンプルでは、XML データベースに格納されている曲情報のコレクションを表示します。 データベースの各曲にはレーティングフィールドがあり、このフィールドの値が曲情報の行を表示する方法を指定します。  
  
 次の例は、曲コレクション内の曲を表す <xref:System.Windows.Controls.ListViewItem> オブジェクトの <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> を定義する方法を示しています。 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> を使用して、曲情報の行を表示する方法を指定する <xref:System.Windows.Controls.ControlTemplate> オブジェクトを参照します。  
  
 [!code-xaml[ListViewItemStyleSnippet#ItemContainerStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#itemcontainerstyle)]  
  
 次の例は、テキスト文字列 `"Strongly Recommended"` を行に追加する <xref:System.Windows.Controls.ControlTemplate> を示しています。 このテンプレートは <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> 内で参照され、曲の評価の値が 5 の場合に表示されます。 <xref:System.Windows.Controls.ControlTemplate> には、<xref:System.Windows.Controls.GridView> ビュー モードで定義されている列に行の内容をレイアウトする <xref:System.Windows.Controls.GridViewRowPresenter> オブジェクトが含まれています。  
  
 [!code-xaml[ListViewItemStyleSnippet#ControlTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#controltemplate)]  
  
 次の例は、<xref:System.Windows.Controls.GridView> を定義しています。  
  
 [!code-xaml[ListViewItemStyleSnippet#GridView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#gridview)]  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [方法トピック](listview-how-to-topics.md)
- [ListView の概要](listview-overview.md)
- [スタイルとテンプレート](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
