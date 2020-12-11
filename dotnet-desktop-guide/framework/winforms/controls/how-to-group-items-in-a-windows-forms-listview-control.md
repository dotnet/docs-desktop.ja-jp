---
title: ListView コントロール内の項目をグループ化する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- lists [Windows Forms], grouping items
- grouping
- list views [Windows Forms], grouping items
- groups
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 610416a1-8da4-436c-af19-5f19e654769b
ms.openlocfilehash: a1754d10de2bbb5895ae861cd17f4af1f18810e2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982119"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control"></a>方法: Windows フォーム ListView コントロールの項目をグループ化する
コントロールのグループ化機能を使用 <xref:System.Windows.Forms.ListView> すると、関連する項目のセットをグループに表示できます。 これらのグループは、グループタイトルを含む横方向のグループヘッダーによって画面上で区切られます。 グループを使用すると、 <xref:System.Windows.Forms.ListView> 項目をアルファベット順、日付形式、またはその他の論理グループ別にグループ化することで、大きなリストを簡単に移動できます。 次の図は、グループ化された項目を示しています。  
  
 ![奇数および偶数の ListView グループのスクリーンショット。](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)  

 グループ化を有効にするには、まずデザイナーまたはプログラムを使用して、1つ以上のグループを作成する必要があります。 グループを定義した後は、項目をグループに割り当てることができ <xref:System.Windows.Forms.ListView> ます。 プログラムを使用して、あるグループから別のグループに項目を移動することもできます。  
  
### <a name="to-add-groups"></a>グループを追加するには  
  
1. <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> コレクションの <xref:System.Windows.Forms.ListView.Groups%2A> メソッドを使用します。  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### <a name="to-remove-groups"></a>グループを削除するには  
  
1. <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A>コレクションのまたはメソッドを使用し <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> <xref:System.Windows.Forms.ListView.Groups%2A> ます。  
  
     メソッドは、 <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> 1 つのグループを削除します。メソッドは、 <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> リストからすべてのグループを削除します。  
  
    > [!NOTE]
    > グループを削除しても、そのグループ内の項目は削除されません。  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### <a name="to-assign-items-to-groups-or-move-items-between-groups"></a>グループに項目を割り当てる、またはグループ間で項目を移動するには  
  
1. <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType>個々の項目のプロパティを設定します。  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewGroup>
- [ListView コントロール](listview-control-windows-forms.md)
- [ListView コントロールの概要](listview-control-overview-windows-forms.md)
- [方法: Windows フォーム ListView コントロールで項目を追加および削除する](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
