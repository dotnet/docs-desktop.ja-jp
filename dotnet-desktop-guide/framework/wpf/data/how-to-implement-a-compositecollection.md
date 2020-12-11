---
title: '方法: CompositeCollection を実装する'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], CompositeCollection class
ms.assetid: 0d8fc84c-7920-427f-8ad7-d55ca656c170
ms.openlocfilehash: fe3b7fb1020ac8022113246453d8247ca241449c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985799"
---
# <a name="how-to-implement-a-compositecollection"></a>方法: CompositeCollection を実装する
## <a name="example"></a>例  
 次の例では、<xref:System.Windows.Data.CompositeCollection> クラスを使用して、複数のコレクションと項目を 1 つのリストとして表示する方法を示します。 この例では、`GreekGods` は `GreekGod` カスタム オブジェクトの <xref:System.Collections.ObjectModel.ObservableCollection%601> です。 データ テンプレートは、`GreekGod` オブジェクトと `GreekHero` オブジェクトがそれぞれゴールドとシアンの前景色で表示されるように定義されています。  
  
 [!code-xaml[CompositeCollections#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CompositeCollections/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Data.CollectionContainer>
- <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>
- <xref:System.Windows.Data.XmlDataProvider>
- <xref:System.Windows.DataTemplate>
- [データ バインディングの概要](/dotnet/desktop-wpf/data/data-binding-overview)
- [方法トピック](data-binding-how-to-topics.md)
