---
title: '方法: コレクションにバインドして選択に基づく情報を表示する'
description: 次の例に従って、Windows Presentation Foundation (WPF) でコレクションにバインドし、選択に基づいて情報を表示する方法を確認します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], selecting data for views
- data binding [WPF], creating views of data collections
- data binding [WPF], selecting data for views
- data binding [WPF], binding to collections
ms.assetid: 952a7d76-dd29-49e5-86f5-32c4530e70eb
ms.openlocfilehash: fc0357edf24ac66e5465d1be9c59e83ee475b071
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974494"
---
# <a name="how-to-bind-to-a-collection-and-display-information-based-on-selection"></a><span data-ttu-id="8058e-103">方法: コレクションにバインドして選択に基づく情報を表示する</span><span class="sxs-lookup"><span data-stu-id="8058e-103">How to: Bind to a Collection and Display Information Based on Selection</span></span>
<span data-ttu-id="8058e-104">簡単なマスター詳細シナリオでは、<xref:System.Windows.Controls.ListBox> などのデータ バインドされた <xref:System.Windows.Controls.ItemsControl> があります。</span><span class="sxs-lookup"><span data-stu-id="8058e-104">In a simple master-detail scenario, you have a data-bound <xref:System.Windows.Controls.ItemsControl> such as a <xref:System.Windows.Controls.ListBox>.</span></span> <span data-ttu-id="8058e-105">ユーザーの選択に基づいて、選択された項目に関する詳細情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="8058e-105">Based on user selection, you display more information about the selected item.</span></span> <span data-ttu-id="8058e-106">この例では、このシナリオを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8058e-106">This example shows how to implement this scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8058e-107">例</span><span class="sxs-lookup"><span data-stu-id="8058e-107">Example</span></span>  
 <span data-ttu-id="8058e-108">この例の `People` は、`Person` クラスの <xref:System.Collections.ObjectModel.ObservableCollection%601> です。</span><span class="sxs-lookup"><span data-stu-id="8058e-108">In this example, `People` is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of `Person` classes.</span></span> <span data-ttu-id="8058e-109">この `Person` クラスには `FirstName`、`LastName`、`HomeTown` の 3 つのプロパティが含まれ、すべて `string` 型です。</span><span class="sxs-lookup"><span data-stu-id="8058e-109">This `Person` class contains three properties: `FirstName`, `LastName`, and `HomeTown`, all of type `string`.</span></span>  
  
 [!code-xaml[CollectionBinding#Source](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#source)]  
[!code-xaml[CollectionBinding#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#ui)]  
  
 <span data-ttu-id="8058e-110"><xref:System.Windows.Controls.ContentControl> では、`Person` の情報の表示方法を定義する次の <xref:System.Windows.DataTemplate> が使用されます。</span><span class="sxs-lookup"><span data-stu-id="8058e-110">The <xref:System.Windows.Controls.ContentControl> uses the following <xref:System.Windows.DataTemplate> that defines how the information of a `Person` is presented:</span></span>  
  
 [!code-xaml[CollectionBinding#DetailTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#detailtemplate)]  
  
 <span data-ttu-id="8058e-111">次に、この例で生成される内容のスクリーンショットを示します。</span><span class="sxs-lookup"><span data-stu-id="8058e-111">The following is a screenshot of what the example produces.</span></span> <span data-ttu-id="8058e-112"><xref:System.Windows.Controls.ContentControl> には、選択されたユーザーの他のプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8058e-112">The <xref:System.Windows.Controls.ContentControl> shows the other properties of the person selected.</span></span>  
  
 <span data-ttu-id="8058e-113">![コレクションへのバインディング](./media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")</span><span class="sxs-lookup"><span data-stu-id="8058e-113">![Binding to a collection](./media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")</span></span>  
  
 <span data-ttu-id="8058e-114">この例では、次の 2 つの点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="8058e-114">The two things to notice in this example are:</span></span>  
  
1. <span data-ttu-id="8058e-115"><xref:System.Windows.Controls.ListBox> と <xref:System.Windows.Controls.ContentControl> は同じソースにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="8058e-115">The <xref:System.Windows.Controls.ListBox> and the <xref:System.Windows.Controls.ContentControl> bind to the same source.</span></span> <span data-ttu-id="8058e-116">どちらのコントロールもコレクション オブジェクト全体にバインドされるため、両方のバインディングの <xref:System.Windows.Data.Binding.Path%2A> プロパティは指定されません。</span><span class="sxs-lookup"><span data-stu-id="8058e-116">The <xref:System.Windows.Data.Binding.Path%2A> properties of both bindings are not specified because both controls are binding to the entire collection object.</span></span>  
  
2. <span data-ttu-id="8058e-117">これを機能させるには、<xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> プロパティを `true` に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8058e-117">You must set the <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> property to `true` for this to work.</span></span> <span data-ttu-id="8058e-118">このプロパティを設定すると、選択された項目が常に <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A> として設定されます。</span><span class="sxs-lookup"><span data-stu-id="8058e-118">Setting this property ensures that the selected item is always set as the <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span></span> <span data-ttu-id="8058e-119">または、<xref:System.Windows.Controls.ListBox> で <xref:System.Windows.Data.CollectionViewSource> からデータが取得される場合は、選択と通貨が自動的に同期されます。</span><span class="sxs-lookup"><span data-stu-id="8058e-119">Alternatively, if the <xref:System.Windows.Controls.ListBox> gets it data from a <xref:System.Windows.Data.CollectionViewSource>, it synchronizes selection and currency automatically.</span></span>  
  
 <span data-ttu-id="8058e-120">`Person` クラスでは、次のように `ToString` メソッドがオーバーライドされていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8058e-120">Note that the `Person` class overrides the `ToString` method the following way.</span></span> <span data-ttu-id="8058e-121">既定では、<xref:System.Windows.Controls.ListBox> によって `ToString` が呼び出され、バインドされたコレクション内の各オブジェクトの文字列形式が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8058e-121">By default, the <xref:System.Windows.Controls.ListBox> calls `ToString` and displays a string representation of each object in the bound collection.</span></span> <span data-ttu-id="8058e-122">そのため、各 `Person` が <xref:System.Windows.Controls.ListBox> の名として表示されます。</span><span class="sxs-lookup"><span data-stu-id="8058e-122">That is why each `Person` appears as a first name in the <xref:System.Windows.Controls.ListBox>.</span></span>  
  
 [!code-csharp[CollectionBinding#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Data.cs#tostring)]
 [!code-vb[CollectionBinding#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionBinding/VisualBasic/Person.vb#tostring)]  
  
## <a name="see-also"></a><span data-ttu-id="8058e-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="8058e-123">See also</span></span>

- [<span data-ttu-id="8058e-124">階層データでマスター詳細パターンを使用する</span><span class="sxs-lookup"><span data-stu-id="8058e-124">Use the Master-Detail Pattern with Hierarchical Data</span></span>](how-to-use-the-master-detail-pattern-with-hierarchical-data.md)
- [<span data-ttu-id="8058e-125">階層 XML データでマスター詳細パターンを使用する</span><span class="sxs-lookup"><span data-stu-id="8058e-125">Use the Master-Detail Pattern with Hierarchical XML Data</span></span>](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)
- [<span data-ttu-id="8058e-126">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="8058e-126">Data Binding Overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
- [<span data-ttu-id="8058e-127">データ テンプレートの概要</span><span class="sxs-lookup"><span data-stu-id="8058e-127">Data Templating Overview</span></span>](data-templating-overview.md)
- [<span data-ttu-id="8058e-128">方法トピック</span><span class="sxs-lookup"><span data-stu-id="8058e-128">How-to Topics</span></span>](data-binding-how-to-topics.md)
