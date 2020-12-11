---
title: '方法: データ CollectionView のオブジェクト間を移動する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CollectionView [WPF], navigating through objects
- data binding [WPF], navigating through objects in data CollectionView
- navigating through objects in data CollectionView [WPF]
ms.assetid: fcd37590-bce1-4ac9-8b74-3b96c7458b8a
ms.openlocfilehash: dc8b1e0dec0f99c3537587fe60cbecf165047f44
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981436"
---
# <a name="how-to-navigate-through-the-objects-in-a-data-collectionview"></a><span data-ttu-id="50ddc-102">方法: データ CollectionView のオブジェクト間を移動する</span><span class="sxs-lookup"><span data-stu-id="50ddc-102">How to: Navigate Through the Objects in a Data CollectionView</span></span>
<span data-ttu-id="50ddc-103">ビューでは、並べ替え、フィルター処理、グループ化に応じて、同じデータ コレクションを異なる方法で表示できます。</span><span class="sxs-lookup"><span data-stu-id="50ddc-103">Views allow the same data collection to be viewed in different ways, depending on sorting, filtering, or grouping.</span></span> <span data-ttu-id="50ddc-104">ビューでは、現在のレコード ポインターの概念が提供され、ポインターを移動できます。</span><span class="sxs-lookup"><span data-stu-id="50ddc-104">Views also provide a current record pointer concept and enable moving the pointer.</span></span> <span data-ttu-id="50ddc-105">この例では、<xref:System.Windows.Data.CollectionView> クラスで提供されている機能を使用して、現在のオブジェクトを取得する方法と、データ コレクション内のオブジェクト間を移動する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="50ddc-105">This example shows how to get the current object as well as navigate through the objects in a data collection using the functionality provided in the <xref:System.Windows.Data.CollectionView> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="50ddc-106">例</span><span class="sxs-lookup"><span data-stu-id="50ddc-106">Example</span></span>  
 <span data-ttu-id="50ddc-107">この例では、`myCollectionView` は、バインドされたコレクションに対するビューである <xref:System.Windows.Data.CollectionView> オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="50ddc-107">In this example, `myCollectionView` is a <xref:System.Windows.Data.CollectionView> object that is a view over a bound collection.</span></span>  
  
 <span data-ttu-id="50ddc-108">次の例では、`OnButton` はアプリケーションの `Previous` ボタンと `Next` ボタンのイベント ハンドラーであり、これらのボタンを使用してユーザーはデータ コレクション内を移動できます。</span><span class="sxs-lookup"><span data-stu-id="50ddc-108">In the following example, `OnButton` is an event handler for the `Previous` and `Next` buttons in an application, which are buttons that allow the user to navigate the data collection.</span></span> <span data-ttu-id="50ddc-109"><xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> プロパティと <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> プロパティによって、<xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> と <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A> を適切に呼び出すことができるように、現在のレコード ポインターがリストのそれぞれ先頭および末尾にあるかどうかが報告されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="50ddc-109">Note that the <xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> and <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> properties report whether the current record pointer has come to the beginning and the end of the list respectively so that <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> and <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A> can be called as appropriately.</span></span>  
  
 <span data-ttu-id="50ddc-110">ビューの <xref:System.Windows.Data.CollectionView.CurrentItem%2A> プロパティは、コレクション内の現在の注文項目を返すために、`Order` としてキャストされます。</span><span class="sxs-lookup"><span data-stu-id="50ddc-110">The <xref:System.Windows.Data.CollectionView.CurrentItem%2A> property of the view is cast as an `Order` to return the current order item in the collection.</span></span>  
  
 [!code-csharp[CollectionView#OnButton](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#onbutton)]
 [!code-vb[CollectionView#OnButton](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#onbutton)]  
  
## <a name="see-also"></a><span data-ttu-id="50ddc-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="50ddc-111">See also</span></span>

- [<span data-ttu-id="50ddc-112">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="50ddc-112">Data Binding Overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
- [<span data-ttu-id="50ddc-113">ビュー内のデータの並べ替え</span><span class="sxs-lookup"><span data-stu-id="50ddc-113">Sort Data in a View</span></span>](how-to-sort-data-in-a-view.md)
- [<span data-ttu-id="50ddc-114">ビュー内のデータをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="50ddc-114">Filter Data in a View</span></span>](how-to-filter-data-in-a-view.md)
- [<span data-ttu-id="50ddc-115">XAML でビューを使用してデータの並べ替えおよびグループ化を行う</span><span class="sxs-lookup"><span data-stu-id="50ddc-115">Sort and Group Data Using a View in XAML</span></span>](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [<span data-ttu-id="50ddc-116">方法トピック</span><span class="sxs-lookup"><span data-stu-id="50ddc-116">How-to Topics</span></span>](data-binding-how-to-topics.md)
