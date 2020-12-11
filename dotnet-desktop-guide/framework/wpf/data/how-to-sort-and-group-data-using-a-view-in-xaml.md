---
title: '方法: XAML でビューを使用してデータの並べ替えおよびグループ化を行う'
description: Windows Presentation Foundation (WPF) でグループ化、並べ替え、およびフィルター処理を行うためのデータ コレクションのビューを作成する方法について説明します。
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], grouping data in views in XAML
- XAML [WPF], sorting data in views
- grouping data in views in XAML [WPF]
- data binding [WPF], sorting data in views in XAML
- sorting data in views in XAML [WPF]
- XAML [WPF], grouping data in views
- views [WPF], sorting data
- views [WPF], grouping data
ms.assetid: 145c8c3f-dbdd-4d0d-816f-90b35eba7eda
ms.openlocfilehash: 9149df0867d6d37cf5160ee1bae1ef969a730641
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982039"
---
# <a name="how-to-sort-and-group-data-using-a-view-in-xaml"></a><span data-ttu-id="7a46b-103">方法: XAML でビューを使用してデータの並べ替えおよびグループ化を行う</span><span class="sxs-lookup"><span data-stu-id="7a46b-103">How to: Sort and Group Data Using a View in XAML</span></span>
<span data-ttu-id="7a46b-104">この例では、[!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] でデータ コレクションのビューを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7a46b-104">This example shows how to create a view of a data collection in [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="7a46b-105">ビューでは、グループ化、並べ替え、フィルター処理、現在の項目の概念などの機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7a46b-105">Views allow for the functionalities of grouping, sorting, filtering, and the notion of a current item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a46b-106">例</span><span class="sxs-lookup"><span data-stu-id="7a46b-106">Example</span></span>  
 <span data-ttu-id="7a46b-107">次の例では、*places* という名前の静的リソースは *Place* オブジェクトのコレクションとして定義されており、各 *Place* オブジェクトは市の名前と州で構成されます。</span><span class="sxs-lookup"><span data-stu-id="7a46b-107">In the following example, the static resource named *places* is defined as a collection of *Place* objects, in which each *Place* object is consisted of a city name and the state.</span></span> <span data-ttu-id="7a46b-108">プレフィックス *src* は、データソース *Places* が定義されている名前空間にマップされています。</span><span class="sxs-lookup"><span data-stu-id="7a46b-108">The prefix *src* is mapped to the namespace where the data source *Places* is defined.</span></span> <span data-ttu-id="7a46b-109">プレフィックス *scm* は `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` にマップされ、*dat* は `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"` にマップされています。</span><span class="sxs-lookup"><span data-stu-id="7a46b-109">The prefix *scm* maps to `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` and *dat* maps to `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`.</span></span>  
  
 <span data-ttu-id="7a46b-110">次の例では、市の名前によって並べ替えられ、州でグループ化された、データ コレクションのビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="7a46b-110">The following example creates a view of the data collection that is sorted by the city name and grouped by the state.</span></span>  
  
 [!code-xaml[CollectionViewSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#1)]  
  
 <span data-ttu-id="7a46b-111">その後、次の例のように、そのビューをバインディング ソースにすることができます。</span><span class="sxs-lookup"><span data-stu-id="7a46b-111">The view can then be a binding source, as in the following example:</span></span>  
  
 [!code-xaml[CollectionViewSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#2)]  
  
 <span data-ttu-id="7a46b-112"><xref:System.Windows.Data.XmlDataProvider> リソースで定義されている XML データへのバインディングでは、XML 名の前に @ 記号を付けます。</span><span class="sxs-lookup"><span data-stu-id="7a46b-112">For bindings to XML data defined in an <xref:System.Windows.Data.XmlDataProvider> resource, precede the XML name with an @ symbol.</span></span>  
  
 [!code-xaml[CollectionViewSource#XDPChunk](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#xdpchunk)]  
  
 [!code-xaml[CollectionViewSource#Attribute](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#attribute)]  
  
## <a name="see-also"></a><span data-ttu-id="7a46b-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="7a46b-113">See also</span></span>

- <xref:System.Windows.Data.CollectionViewSource>
- [<span data-ttu-id="7a46b-114">データ コレクションの既定のビューを取得する</span><span class="sxs-lookup"><span data-stu-id="7a46b-114">Get the Default View of a Data Collection</span></span>](how-to-get-the-default-view-of-a-data-collection.md)
- [<span data-ttu-id="7a46b-115">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="7a46b-115">Data Binding Overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
- [<span data-ttu-id="7a46b-116">方法トピック</span><span class="sxs-lookup"><span data-stu-id="7a46b-116">How-to Topics</span></span>](data-binding-how-to-topics.md)
