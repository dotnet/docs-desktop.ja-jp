---
title: '方法: LINQ クエリの結果にバインドする'
ms.date: 03/30/2017
helpviewer_keywords:
- running a LINQ query [WPF], bind to results
- binding to LINQ query results [WPF]
ms.assetid: ff2844d9-17ed-4ea6-aab1-5111af0bc684
ms.openlocfilehash: 47f39319f2d6a6c67361157afaceb6d605ce01d1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974654"
---
# <a name="how-to-bind-to-the-results-of-a-linq-query"></a>方法: LINQ クエリの結果にバインドする

この例では、LINQ クエリを実行し、その結果にバインドする方法を示します。

## <a name="example"></a>例

次の例では、2 つのリスト ボックスを作成します。 最初のリスト ボックスには、3 つのリスト項目が含まれています。

[!code-xaml[LinqExample#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml#ui)]

最初のリスト ボックスで項目を選択すると、次のイベント ハンドラーが呼び出されます。 この例では、`Tasks` は `Task` オブジェクトのコレクションです。 `Task` クラスには、`Priority` という名前のプロパティがあります。 このイベント ハンドラーでは、選択した優先順位値を持つ `Task` オブジェクトのコレクションを返す LINQ クエリが実行された後、それが <xref:System.Windows.FrameworkElement.DataContext%2A> として設定されます。

[!code-csharp[LinqExample#Using](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#using)]
[!code-csharp[LinqExample#Tasks](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#tasks)]
[!code-csharp[LinqExample#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#handler)]

2 番目のリスト ボックスは、<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 値が `{Binding}` に設定されているため、そのコレクションにバインドされます。 その結果、返されたコレクションが (`myTaskTemplate` <xref:System.Windows.DataTemplate> に基づいて) 表示されます。

## <a name="see-also"></a>関連項目

- [XAML でデータをバインディング可能にする](how-to-make-data-available-for-binding-in-xaml.md)
- [コレクションにバインドして選択に基づく情報を表示する](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [WPF Version 4.5 の新機能](../getting-started/whats-new.md)
- [データ バインディングの概要](/dotnet/desktop-wpf/data/data-binding-overview)
