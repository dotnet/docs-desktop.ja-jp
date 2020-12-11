---
title: デザイナーを使用して ListView コントロール内の項目をグループ化する
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- grouping
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 8b615000-69d9-4c64-acaf-b54fa09b69e3
ms.openlocfilehash: 935d8d75517e1028e686ca229f6ada656f58b01e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982487"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control-using-the-designer"></a>方法: デザイナーを使って Windows フォーム ListView コントロールの項目をグループ化する

コントロールのグループ化機能を <xref:System.Windows.Forms.ListView> 使用すると、関連する項目のセットをグループに表示できます。 これらのグループは、グループタイトルを含む横方向のグループヘッダーによって画面上で区切られます。 グループを使用すると、 <xref:System.Windows.Forms.ListView> 項目をアルファベット順、日付形式、またはその他の論理グループ別にグループ化することで、大きなリストを簡単に移動できます。 次の図は、グループ化された項目を示しています。

![奇数と偶数のグループに分割された数値。](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)

次の手順では、コントロールを含むフォームを含む **Windows アプリケーション** プロジェクトが必要です <xref:System.Windows.Forms.ListView> 。 このようなプロジェクトの設定の詳細については、「 [方法: Windows フォームアプリケーションプロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project) する」および「 [方法: Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)する」を参照してください。

グループ化を有効にするには、最初 <xref:System.Windows.Forms.ListViewGroup> にデザイナーまたはプログラムを使用して、1つ以上のオブジェクトを作成する必要があります。 グループを定義したら、それに項目を割り当てることができます。

## <a name="to-add-or-remove-groups-in-the-designer"></a>デザイナーでグループを追加または削除するには

1. [**プロパティ**] ウィンドウで、プロパティの横に **ある省略記号 (** ![ 省略記号ボタン ([...]) をクリックして、プロパティの横にある [プロパティウィンドウ ](./media/visual-studio-ellipsis-button.png) ] ボタンをクリックします。 <xref:System.Windows.Forms.ListView.Groups%2A>

     **ListViewGroup Collection エディター** が表示されます。

2. グループを追加するには、[ **追加** ] ボタンをクリックします。 その後、プロパティやプロパティなど、新しいグループのプロパティを設定でき <xref:System.Windows.Forms.ListViewGroup.Header%2A> <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A> ます。 グループを削除するには、グループを選択し、[ **削除** ] ボタンをクリックします。

## <a name="to-assign-items-to-groups-in-the-designer"></a>デザイナーで項目をグループに割り当てるには

1. [**プロパティ**] ウィンドウで、プロパティの横に **ある省略記号 (** ![ 省略記号ボタン ([...]) をクリックして、プロパティの横にある [プロパティウィンドウ ](./media/visual-studio-ellipsis-button.png) ] ボタンをクリックします。 <xref:System.Windows.Forms.ListView.Items%2A>

     **ListViewItem Collection エディター** が表示されます。

2. 新しい項目を追加するには、[ **追加** ] ボタンをクリックします。 その後、プロパティやプロパティなど、新しい項目のプロパティを設定でき <xref:System.Windows.Forms.ListViewItem.Text%2A> <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> ます。

3. プロパティを選択し、 <xref:System.Windows.Forms.ListViewItem.Group%2A> ドロップダウンリストからグループを選択します。

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A>
- <xref:System.Windows.Forms.ListViewGroup>
- [ListView コントロール](listview-control-windows-forms.md)
- [ListView コントロールの概要](listview-control-overview-windows-forms.md)
- [方法: Windows フォーム ListView コントロールで項目を追加および削除する](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
