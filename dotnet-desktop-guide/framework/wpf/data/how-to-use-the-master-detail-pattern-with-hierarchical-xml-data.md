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
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-xml-data"></a><span data-ttu-id="cbfc2-102">方法: 階層 XML データでマスター詳細パターンを使用する</span><span class="sxs-lookup"><span data-stu-id="cbfc2-102">How to: Use the Master-Detail Pattern with Hierarchical XML Data</span></span>
<span data-ttu-id="cbfc2-103">この例では、XML データでマスター詳細シナリオを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="cbfc2-103">This example shows how to implement the master-detail scenario with XML data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cbfc2-104">例</span><span class="sxs-lookup"><span data-stu-id="cbfc2-104">Example</span></span>  
 <span data-ttu-id="cbfc2-105">この例は、「[階層データでマスター詳細パターンを使用する](how-to-use-the-master-detail-pattern-with-hierarchical-data.md)」で説明されている例の XML データ バージョンです。</span><span class="sxs-lookup"><span data-stu-id="cbfc2-105">This example is the XML data version of the example discussed in [Use the Master-Detail Pattern with Hierarchical Data](how-to-use-the-master-detail-pattern-with-hierarchical-data.md).</span></span> <span data-ttu-id="cbfc2-106">この例では、データは `League.xml` ファイルのものです。</span><span class="sxs-lookup"><span data-stu-id="cbfc2-106">In this example, the data is from the file `League.xml`.</span></span> <span data-ttu-id="cbfc2-107"><xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> プロパティにバインドすることによって、3 番目の <xref:System.Windows.Controls.ListBox> コントロールで、2 番目の <xref:System.Windows.Controls.ListBox> の選択の変更が追跡されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="cbfc2-107">Note how the third <xref:System.Windows.Controls.ListBox> control tracks selection changes in the second <xref:System.Windows.Controls.ListBox> by binding to its <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> property.</span></span>  
  
 [!code-xaml[MasterDetailXml#HowTo1](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto1)]  
[!code-xaml[MasterDetailXml#HowTo2](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto2)]  
  
## <a name="see-also"></a><span data-ttu-id="cbfc2-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="cbfc2-108">See also</span></span>

- <xref:System.Windows.HierarchicalDataTemplate>
- [<span data-ttu-id="cbfc2-109">方法トピック</span><span class="sxs-lookup"><span data-stu-id="cbfc2-109">How-to Topics</span></span>](data-binding-how-to-topics.md)
