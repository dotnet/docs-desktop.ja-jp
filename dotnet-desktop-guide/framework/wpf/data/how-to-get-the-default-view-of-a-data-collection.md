---
title: '方法: データ コレクションの既定のビューを取得する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], creating views of
- data binding [WPF], creating views of data collections
ms.assetid: b641e96c-c2f6-42ea-9c5d-bac81176ad65
ms.openlocfilehash: 17ec2a40bf2c274f50b39875a23541932438a317
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985803"
---
# <a name="how-to-get-the-default-view-of-a-data-collection"></a>方法: データ コレクションの既定のビューを取得する
ビューでは、並べ替え、フィルター処理、グループ化の条件に応じて、同じデータ コレクションを異なる方法で表示できます。 すべてのコレクションには既定の共有ビューが 1 つあり、バインディングでソースとしてコレクションが指定されているときに、実際のバインディング ソースとして使用されます。 この例では、コレクションの既定のビューを取得する方法を示します。  
  
## <a name="example"></a>例  
 ビューを作成するには、コレクションへのオブジェクト参照が必要です。 このデータ オブジェクトは、独自のコードビハインド オブジェクトの参照、データ コンテキストの取得、データ ソースのプロパティの取得、またはバインディングのプロパティの取得によって、取得することができます。 この例では、データ オブジェクトの <xref:System.Windows.FrameworkElement.DataContext%2A> を取得し、それを使用してこのコレクションの既定のコレクション ビューを直接取得する方法を示します。  
  
 [!code-csharp[CollectionView#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#2)]
 [!code-vb[CollectionView#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#2)]  
  
 この例では、ルート要素は <xref:System.Windows.Controls.StackPanel> です。 <xref:System.Windows.FrameworkElement.DataContext%2A> は *myDataSource* に設定されています。これは、*Order* オブジェクトの <xref:System.Collections.ObjectModel.ObservableCollection%601> であるデータ プロバイダーを参照します。  
  
 [!code-xaml[CollectionView#CollectionViewDataContext](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml#collectionviewdatacontext)]  
  
 または、<xref:System.Windows.Data.CollectionViewSource> クラスを使用して、独自のコレクション ビューをインスタンス化し、それにバインドすることもできます。 このコレクション ビューは、それに直接バインドするコントロールによってのみ共有されます。 例については、「[データ バインディングの概要](/dotnet/desktop-wpf/data/data-binding-overview)」の「ビューの作成方法」セクションを参照してください。  
  
 コレクション ビューによって提供される機能の例については、「[ビュー内のデータの並べ替え](how-to-sort-data-in-a-view.md)」、「[ビュー内のデータをフィルター処理する](how-to-filter-data-in-a-view.md)」、および「[データ CollectionView のオブジェクト間を移動する](how-to-navigate-through-the-objects-in-a-data-collectionview.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目

- [XAML でビューを使用してデータの並べ替えおよびグループ化を行う](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [方法トピック](data-binding-how-to-topics.md)
