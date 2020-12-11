---
title: ListView コントロールを使用して項目を追加および削除する
description: 項目を指定してプロパティを割り当てることによって、Windows フォーム ListView コントロールで項目を追加および削除する方法について説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], populating
- list views [Windows Forms], adding list items
- ListView control [Windows Forms], adding list items
ms.assetid: 1b35a80a-edd8-495f-a807-a28c4aae52c6
ms.openlocfilehash: db374ded69bcbd93527381d75a8ff751a1c9abe6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974141"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control"></a><span data-ttu-id="4b256-103">方法: Windows フォーム ListView コントロールで項目を追加および削除する</span><span class="sxs-lookup"><span data-stu-id="4b256-103">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>
<span data-ttu-id="4b256-104">項目を Windows フォームコントロールに追加するプロセスは、 <xref:System.Windows.Forms.ListView> 主に項目を指定し、その項目にプロパティを割り当てることによって構成されます。</span><span class="sxs-lookup"><span data-stu-id="4b256-104">The process of adding an item to a Windows Forms <xref:System.Windows.Forms.ListView> control consists primarily of specifying the item and assigning properties to it.</span></span> <span data-ttu-id="4b256-105">リスト項目の追加または削除は、いつでも行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4b256-105">Adding or removing list items can be done at any time.</span></span>  
  
### <a name="to-add-items-programmatically"></a><span data-ttu-id="4b256-106">プログラムによって項目を追加するには</span><span class="sxs-lookup"><span data-stu-id="4b256-106">To add items programmatically</span></span>  
  
1. <span data-ttu-id="4b256-107"><xref:System.Windows.Forms.ListView.ListViewItemCollection.Add%2A>プロパティのメソッドを使用し <xref:System.Windows.Forms.ListView.Items%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="4b256-107">Use the <xref:System.Windows.Forms.ListView.ListViewItemCollection.Add%2A> method of the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#11)]  
  
### <a name="to-remove-items-programmatically"></a><span data-ttu-id="4b256-108">プログラムによって項目を削除するには</span><span class="sxs-lookup"><span data-stu-id="4b256-108">To remove items programmatically</span></span>  
  
1. <span data-ttu-id="4b256-109"><xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A>プロパティのメソッドまたはメソッドを使用し <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> <xref:System.Windows.Forms.ListView.Items%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="4b256-109">Use the <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> or <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> method of the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span> <span data-ttu-id="4b256-110">メソッドは、 <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> 1 つの項目を削除します。メソッドは、 <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> リストからすべての項目を削除します。</span><span class="sxs-lookup"><span data-stu-id="4b256-110">The <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> method removes a single item; the <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> method removes all items from the list.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a><span data-ttu-id="4b256-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="4b256-111">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- [<span data-ttu-id="4b256-112">ListView コントロール</span><span class="sxs-lookup"><span data-stu-id="4b256-112">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="4b256-113">ListView コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="4b256-113">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
