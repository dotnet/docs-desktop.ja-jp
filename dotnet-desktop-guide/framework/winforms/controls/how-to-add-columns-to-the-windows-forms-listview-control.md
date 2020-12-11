---
title: ListView コントロールに列を追加する
description: Windows フォーム ListView コントロールに列を追加して、各リスト項目に関するいくつかの種類の情報を表示する方法について説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
- list views [Windows Forms], adding columns
ms.assetid: 79174274-12ee-4a5d-80db-6ec02976d010
ms.openlocfilehash: 7ca4e86ca3a9679876f2525c49596534f175096a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981476"
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control"></a><span data-ttu-id="904c5-103">方法: Windows フォーム ListView コントロールに列を追加する</span><span class="sxs-lookup"><span data-stu-id="904c5-103">How to: Add Columns to the Windows Forms ListView Control</span></span>
<span data-ttu-id="904c5-104">詳細ビューでは、コントロールは、 <xref:System.Windows.Forms.ListView> 各リスト項目に対して複数の列を表示できます。</span><span class="sxs-lookup"><span data-stu-id="904c5-104">In the Details view, the <xref:System.Windows.Forms.ListView> control can display multiple columns for each list item.</span></span> <span data-ttu-id="904c5-105">列を使用して、各リスト項目に関するいくつかの種類の情報をユーザーに表示できます。</span><span class="sxs-lookup"><span data-stu-id="904c5-105">You can use the columns to display to the user several types of information about each list item.</span></span> <span data-ttu-id="904c5-106">たとえば、ファイルの一覧には、ファイル名、ファイルの種類、サイズ、ファイルが最後に変更された日付が表示されます。</span><span class="sxs-lookup"><span data-stu-id="904c5-106">For example, a list of files could display the file name, file type, size, and date the file was last modified.</span></span> <span data-ttu-id="904c5-107">作成後に列を設定する方法の詳細については、「 [方法: Windows フォーム ListView コントロールを使用して列にサブ項目を表示する](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="904c5-107">For information about populating the columns after they are created, see [How to: Display Subitems in Columns with the Windows Forms ListView Control](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).</span></span>  
  
### <a name="to-add-columns-programmatically"></a><span data-ttu-id="904c5-108">プログラムによって列を追加するには</span><span class="sxs-lookup"><span data-stu-id="904c5-108">To add columns programmatically</span></span>  
  
1. <span data-ttu-id="904c5-109">コントロールの <xref:System.Windows.Forms.ListView.View%2A> プロパティを <xref:System.Windows.Forms.View.Details> に設定します。</span><span class="sxs-lookup"><span data-stu-id="904c5-109">Set the control's <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Details>.</span></span>  
  
2. <span data-ttu-id="904c5-110"><xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A>リストビューのプロパティのメソッドを使用し <xref:System.Windows.Forms.ListView.Columns%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="904c5-110">Use the <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A> method of the list view's <xref:System.Windows.Forms.ListView.Columns%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="904c5-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="904c5-111">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- [<span data-ttu-id="904c5-112">ListView コントロール</span><span class="sxs-lookup"><span data-stu-id="904c5-112">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="904c5-113">ListView コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="904c5-113">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
