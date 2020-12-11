---
title: '方法: 階層 XML データでマスター詳細パターンを使用する'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: eb8dbdd8-5871-42bb-a16b-04e655fea677
ms.openlocfilehash: 0fe42d57fcaf4acee09340fdb3f5df73d7291566
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982616"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-xml-data"></a>方法: 階層 XML データでマスター詳細パターンを使用する
この例では、XML データでマスター詳細シナリオを実装する方法を示します。  
  
## <a name="example"></a>例  
 この例は、「[階層データでマスター詳細パターンを使用する](how-to-use-the-master-detail-pattern-with-hierarchical-data.md)」で説明されている例の XML データ バージョンです。 この例では、データは `League.xml` ファイルのものです。 <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> プロパティにバインドすることによって、3 番目の <xref:System.Windows.Controls.ListBox> コントロールで、2 番目の <xref:System.Windows.Controls.ListBox> の選択の変更が追跡されていることに注意してください。  
  
 [!code-xaml[MasterDetailXml#HowTo1](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto1)]  
[!code-xaml[MasterDetailXml#HowTo2](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto2)]  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.HierarchicalDataTemplate>
- [方法トピック](data-binding-how-to-topics.md)
