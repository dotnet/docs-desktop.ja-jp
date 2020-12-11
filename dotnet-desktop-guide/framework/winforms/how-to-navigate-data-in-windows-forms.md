---
title: '方法: データを移動する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cursors [Windows Forms], data sources
- data sources [Windows Forms], Windows Forms
- Windows Forms, navigating
- CurrencyManager class [Windows Forms], navigating Windows Forms data
- data [Windows Forms], navigating
ms.assetid: 97360f7b-b181-4084-966a-4c62518f735b
ms.openlocfilehash: 2dd900b652b0ff21ea0eb0dbc5463b22c869ec7c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983287"
---
# <a name="how-to-navigate-data-in-windows-forms"></a><span data-ttu-id="7580f-102">方法: Windows フォームでデータ間を移動する</span><span class="sxs-lookup"><span data-stu-id="7580f-102">How to: Navigate Data in Windows Forms</span></span>
<span data-ttu-id="7580f-103">Windows アプリケーションでは、データソース内のレコード間を移動する最も簡単な方法は、 <xref:System.Windows.Forms.BindingSource> コンポーネントをデータソースにバインドしてから、コントロールをにバインドすることです <xref:System.Windows.Forms.BindingSource> 。</span><span class="sxs-lookup"><span data-stu-id="7580f-103">In a Windows application, the easiest way to navigate through records in a data source is to bind a <xref:System.Windows.Forms.BindingSource> component to the data source and then bind controls to the <xref:System.Windows.Forms.BindingSource>.</span></span> <span data-ttu-id="7580f-104">その後、、、およびの組み込みナビゲーションメソッドを使用でき <xref:System.Windows.Forms.BindingSource> <xref:System.Windows.Forms.BindingSource.MoveNext%2A> <xref:System.Windows.Forms.BindingSource.MoveLast%2A> <xref:System.Windows.Forms.BindingSource.MovePrevious%2A> <xref:System.Windows.Forms.BindingSource.MoveFirst%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="7580f-104">You can then use the built-in navigation method on the <xref:System.Windows.Forms.BindingSource> such a <xref:System.Windows.Forms.BindingSource.MoveNext%2A>, <xref:System.Windows.Forms.BindingSource.MoveLast%2A>, <xref:System.Windows.Forms.BindingSource.MovePrevious%2A> and <xref:System.Windows.Forms.BindingSource.MoveFirst%2A>.</span></span> <span data-ttu-id="7580f-105">これらのメソッドを使用する <xref:System.Windows.Forms.BindingSource.Position%2A> と <xref:System.Windows.Forms.BindingSource.Current%2A> 、のプロパティとプロパティが適切に調整され <xref:System.Windows.Forms.BindingSource> ます。</span><span class="sxs-lookup"><span data-stu-id="7580f-105">Using these methods will adjust the <xref:System.Windows.Forms.BindingSource.Position%2A> and <xref:System.Windows.Forms.BindingSource.Current%2A> properties of the <xref:System.Windows.Forms.BindingSource> appropriately.</span></span> <span data-ttu-id="7580f-106">また、プロパティを設定して、項目を検索し、現在の項目として設定することもでき <xref:System.Windows.Forms.BindingSource.Position%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="7580f-106">You can also find an item and set it as the current item by setting the <xref:System.Windows.Forms.BindingSource.Position%2A> property.</span></span>  
  
### <a name="to-increment-the-position-in-a-data-source"></a><span data-ttu-id="7580f-107">データソース内の位置をインクリメントするには</span><span class="sxs-lookup"><span data-stu-id="7580f-107">To increment the position in a data source</span></span>  
  
1. <span data-ttu-id="7580f-108">バインドされたデータののプロパティを、移動先の <xref:System.Windows.Forms.BindingSource.Position%2A> <xref:System.Windows.Forms.BindingSource> レコード位置に設定します。</span><span class="sxs-lookup"><span data-stu-id="7580f-108">Set the <xref:System.Windows.Forms.BindingSource.Position%2A> property of the <xref:System.Windows.Forms.BindingSource> for your bound data to the record position to go to.</span></span> <span data-ttu-id="7580f-109">をクリックしたときに、のメソッドを使用してプロパティをインクリメントする例を次に示し <xref:System.Windows.Forms.BindingSource.MoveNext%2A> <xref:System.Windows.Forms.BindingSource> <xref:System.Windows.Forms.BindingSource.Position%2A> `nextButton` ます。</span><span class="sxs-lookup"><span data-stu-id="7580f-109">The following example illustrates using the <xref:System.Windows.Forms.BindingSource.MoveNext%2A> method of the <xref:System.Windows.Forms.BindingSource> to increment the <xref:System.Windows.Forms.BindingSource.Position%2A> property when the `nextButton` is clicked.</span></span> <span data-ttu-id="7580f-110">は、 <xref:System.Windows.Forms.BindingSource> `Customers` データセットのテーブルに関連付けられてい `Northwind` ます。</span><span class="sxs-lookup"><span data-stu-id="7580f-110">The <xref:System.Windows.Forms.BindingSource> is associated with the `Customers` table of a dataset `Northwind`.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="7580f-111">この <xref:System.Windows.Forms.BindingSource.Position%2A> プロパティを最初または最後のレコードを超えた値に設定しても、エラーは発生しません。 .NET Framework では、リストの範囲外の値に位置を設定することができないためです。</span><span class="sxs-lookup"><span data-stu-id="7580f-111">Setting the <xref:System.Windows.Forms.BindingSource.Position%2A> property to a value beyond the first or last record does not result in an error, as the .NET Framework will not allow you to set the position to a value outside the bounds of the list.</span></span> <span data-ttu-id="7580f-112">最初または最後のレコードがなくなったかどうかを確認するためにアプリケーションで重要な場合は、データ要素数を超えるかどうかをテストするロジックを含めます。</span><span class="sxs-lookup"><span data-stu-id="7580f-112">If it is important in your application to know whether you have gone past the first or last record, include logic to test whether you will exceed the data element count.</span></span>  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.NavigatingData#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#4)]  
  
### <a name="to-check-whether-you-have-passed-the-end-or-beginning"></a><span data-ttu-id="7580f-113">終了を超えたかどうかを確認するには</span><span class="sxs-lookup"><span data-stu-id="7580f-113">To check whether you have passed the end or beginning</span></span>  
  
1. <span data-ttu-id="7580f-114"><xref:System.Windows.Forms.BindingSource.PositionChanged> イベントのイベント ハンドラーを作成します。</span><span class="sxs-lookup"><span data-stu-id="7580f-114">Create an event handler for the <xref:System.Windows.Forms.BindingSource.PositionChanged> event.</span></span> <span data-ttu-id="7580f-115">ハンドラーでは、提案された位置の値が実際のデータ要素数を超えたかどうかをテストできます。</span><span class="sxs-lookup"><span data-stu-id="7580f-115">In the handler, you can test whether the proposed position value has exceeded the actual data element count.</span></span>  
  
     <span data-ttu-id="7580f-116">次の例は、最後のデータ要素に到達したかどうかをテストする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="7580f-116">The following example illustrates how you can test whether you have reached the last data element.</span></span> <span data-ttu-id="7580f-117">この例では、最後の要素にある場合、フォームの [ **次へ** ] ボタンは無効になっています。</span><span class="sxs-lookup"><span data-stu-id="7580f-117">In the example, if you are at the last element, the **Next** button on the form is disabled.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="7580f-118">コード内で移動するリストを変更する場合は、ユーザーが新しいリストの長さ全体を参照できるように、 **[次へ** ] ボタンを再度有効にする必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7580f-118">Be aware that, should you change the list you are navigating in code, you should re-enable the **Next** button, so that users may browse the entire length of the new list.</span></span> <span data-ttu-id="7580f-119">また、使用して <xref:System.Windows.Forms.BindingSource.PositionChanged> いる特定ののイベントが <xref:System.Windows.Forms.BindingSource> イベント処理メソッドに関連付けられている必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7580f-119">Additionally, be aware that the above <xref:System.Windows.Forms.BindingSource.PositionChanged> event for the specific <xref:System.Windows.Forms.BindingSource> you are working with needs to be associated with its event-handling method.</span></span> <span data-ttu-id="7580f-120">イベントを処理するメソッドの例を次に示し <xref:System.Windows.Forms.BindingSource.PositionChanged> ます。</span><span class="sxs-lookup"><span data-stu-id="7580f-120">The following is an example of a method for handling the <xref:System.Windows.Forms.BindingSource.PositionChanged> event:</span></span>  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.NavigatingData#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#3)]  
  
### <a name="to-find-an-item-and-set-it-as-the-current-item"></a><span data-ttu-id="7580f-121">項目を検索して現在の項目として設定するには</span><span class="sxs-lookup"><span data-stu-id="7580f-121">To find an item and set it as the current item</span></span>  
  
1. <span data-ttu-id="7580f-122">現在のアイテムとして設定するレコードを探します。</span><span class="sxs-lookup"><span data-stu-id="7580f-122">Find the record you wish to set as the current item.</span></span> <span data-ttu-id="7580f-123"><xref:System.Windows.Forms.BindingSource.Find%2A> <xref:System.Windows.Forms.BindingSource> データソースがを実装している場合は、のメソッドを使用してこれを行うことができ <xref:System.ComponentModel.IBindingList> ます。</span><span class="sxs-lookup"><span data-stu-id="7580f-123">You can do this using the <xref:System.Windows.Forms.BindingSource.Find%2A> method of the <xref:System.Windows.Forms.BindingSource>, if your data source implements <xref:System.ComponentModel.IBindingList>.</span></span> <span data-ttu-id="7580f-124">を実装するデータソースの例 <xref:System.ComponentModel.IBindingList> <xref:System.ComponentModel.BindingList%601> として、とがあり <xref:System.Data.DataView> ます。</span><span class="sxs-lookup"><span data-stu-id="7580f-124">Some examples of data sources that implement <xref:System.ComponentModel.IBindingList> are <xref:System.ComponentModel.BindingList%601> and <xref:System.Data.DataView>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.NavigatingData#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="7580f-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="7580f-125">See also</span></span>

- [<span data-ttu-id="7580f-126">Windows フォームがサポートするデータ ソース</span><span class="sxs-lookup"><span data-stu-id="7580f-126">Data Sources Supported by Windows Forms</span></span>](data-sources-supported-by-windows-forms.md)
- [<span data-ttu-id="7580f-127">Windows フォーム データ バインディングの変更通知</span><span class="sxs-lookup"><span data-stu-id="7580f-127">Change Notification in Windows Forms Data Binding</span></span>](change-notification-in-windows-forms-data-binding.md)
- [<span data-ttu-id="7580f-128">データ連結と Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="7580f-128">Data Binding and Windows Forms</span></span>](data-binding-and-windows-forms.md)
- [<span data-ttu-id="7580f-129">Windows フォームでのデータ バインディング</span><span class="sxs-lookup"><span data-stu-id="7580f-129">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
