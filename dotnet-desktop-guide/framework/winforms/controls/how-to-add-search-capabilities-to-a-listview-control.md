---
title: '方法: ListView コントロールに検索機能を追加する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- lists [Windows Forms], enabling searching
- list views [Windows Forms], enabling searching
- ListView control [Windows Forms], adding search capabilities
- searching [Windows Forms], adding search capabilities to ListView control
ms.assetid: 557782d9-b705-4bab-b496-9938afddac82
ms.openlocfilehash: d5d4dae55fc9f0613ab6535b2fe57e262d0ef141
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982011"
---
# <a name="how-to-add-search-capabilities-to-a-listview-control"></a><span data-ttu-id="269d2-102">方法: ListView コントロールに検索機能を追加する</span><span class="sxs-lookup"><span data-stu-id="269d2-102">How to: Add Search Capabilities to a ListView Control</span></span>
<span data-ttu-id="269d2-103">多くの場合、コントロール内の項目の大きいリストを操作するときは、 <xref:System.Windows.Forms.ListView> ユーザーに検索機能を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="269d2-103">Oftentimes when working with a large list of items in a <xref:System.Windows.Forms.ListView> control, you want to offer search capabilities to the user.</span></span> <span data-ttu-id="269d2-104">コントロールは、 <xref:System.Windows.Forms.ListView> テキスト一致と位置検索という2つの異なる方法でこの機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="269d2-104">The <xref:System.Windows.Forms.ListView> control offers this capability in two different ways: text matching and location searching.</span></span>  
  
 <span data-ttu-id="269d2-105">メソッドを使用すると、 <xref:System.Windows.Forms.ListView.FindItemWithText%2A> <xref:System.Windows.Forms.ListView> 検索文字列およびオプションの開始インデックスと終了インデックスを指定して、リストまたは詳細ビューでテキスト検索を実行できます。</span><span class="sxs-lookup"><span data-stu-id="269d2-105">The <xref:System.Windows.Forms.ListView.FindItemWithText%2A> method allows you to perform a text search on a <xref:System.Windows.Forms.ListView> in list or details view, given a search string and an optional starting and ending index.</span></span> <span data-ttu-id="269d2-106">これに対し、メソッドを使用すると、 <xref:System.Windows.Forms.ListView.FindNearestItem%2A> <xref:System.Windows.Forms.ListView> x 座標と y 座標のセットと検索の方向を指定して、アイコンまたはタイルビュー内の項目を検索できます。</span><span class="sxs-lookup"><span data-stu-id="269d2-106">In contrast, the <xref:System.Windows.Forms.ListView.FindNearestItem%2A> method allows you to find an item in a <xref:System.Windows.Forms.ListView> in icon or tile view, given a set of x- and y-coordinates and a direction to search.</span></span>  
  
### <a name="to-find-an-item-using-text"></a><span data-ttu-id="269d2-107">テキストを使用して項目を検索するには</span><span class="sxs-lookup"><span data-stu-id="269d2-107">To find an item using text</span></span>  
  
1. <span data-ttu-id="269d2-108">プロパティを <xref:System.Windows.Forms.ListView> <xref:System.Windows.Forms.ListView.View%2A> またはに設定してを作成 <xref:System.Windows.Forms.View.Details> <xref:System.Windows.Forms.View.List> し、に <xref:System.Windows.Forms.ListView> 項目を設定します。</span><span class="sxs-lookup"><span data-stu-id="269d2-108">Create a <xref:System.Windows.Forms.ListView> with the <xref:System.Windows.Forms.ListView.View%2A> property set to <xref:System.Windows.Forms.View.Details> or <xref:System.Windows.Forms.View.List>, and then populate the <xref:System.Windows.Forms.ListView> with items.</span></span>  
  
2. <span data-ttu-id="269d2-109"><xref:System.Windows.Forms.ListView.FindItemWithText%2A>検索する項目のテキストを渡して、メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="269d2-109">Call the <xref:System.Windows.Forms.ListView.FindItemWithText%2A> method, passing the text of the item you would like to find.</span></span>  
  
3. <span data-ttu-id="269d2-110">次のコード例では、基本的なを作成し、 <xref:System.Windows.Forms.ListView> それに項目を設定し、ユーザーからのテキスト入力を使用してリスト内の項目を検索する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="269d2-110">The following code example demonstrates how to create a basic <xref:System.Windows.Forms.ListView>, populate it with items, and use text input from the user to find an item in the list.</span></span>  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#1)]  
  
### <a name="to-find-an-item-using-x--and-y-coordinates"></a><span data-ttu-id="269d2-111">X 座標と y 座標を使用して項目を検索するには</span><span class="sxs-lookup"><span data-stu-id="269d2-111">To find an item using x- and y-coordinates</span></span>  
  
1. <span data-ttu-id="269d2-112">プロパティを <xref:System.Windows.Forms.ListView> <xref:System.Windows.Forms.View> またはに設定してを作成 <xref:System.Windows.Forms.View.SmallIcon> <xref:System.Windows.Forms.View.LargeIcon> し、に <xref:System.Windows.Forms.ListView> 項目を設定します。</span><span class="sxs-lookup"><span data-stu-id="269d2-112">Create a <xref:System.Windows.Forms.ListView> with the <xref:System.Windows.Forms.View> property set to <xref:System.Windows.Forms.View.SmallIcon> or <xref:System.Windows.Forms.View.LargeIcon>, and then populate the <xref:System.Windows.Forms.ListView> with items.</span></span>  
  
2. <span data-ttu-id="269d2-113"><xref:System.Windows.Forms.ListView.FindNearestItem%2A>必要な x 座標と y 座標、および検索する方向を渡して、メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="269d2-113">Call the <xref:System.Windows.Forms.ListView.FindNearestItem%2A> method, passing the desired x- and y-coordinates and the direction you would like to search.</span></span>  
  
3. <span data-ttu-id="269d2-114">次のコード例では、基本的なアイコンを作成し <xref:System.Windows.Forms.ListView> 、それに項目を設定し、イベントをキャプチャして <xref:System.Windows.Forms.Control.MouseDown> 最も近い項目を上方向に検索する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="269d2-114">The following code example demonstrates how to create a basic icon <xref:System.Windows.Forms.ListView>, populate it with items, and capture the <xref:System.Windows.Forms.Control.MouseDown> event to find the nearest item in the up direction.</span></span>  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#2](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#2)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#2)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="269d2-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="269d2-115">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.FindItemWithText%2A>
- <xref:System.Windows.Forms.ListView.FindNearestItem%2A>
- [<span data-ttu-id="269d2-116">ListView コントロール</span><span class="sxs-lookup"><span data-stu-id="269d2-116">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="269d2-117">ListView コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="269d2-117">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="269d2-118">方法: Windows フォーム ListView コントロールで項目を追加および削除する</span><span class="sxs-lookup"><span data-stu-id="269d2-118">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
