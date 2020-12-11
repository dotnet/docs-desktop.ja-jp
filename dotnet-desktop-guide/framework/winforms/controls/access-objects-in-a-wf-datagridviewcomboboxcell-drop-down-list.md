---
title: DataGridViewComboBoxCell Drop-Down リストのオブジェクトへのアクセス
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], accessing objects in combo box cells
- combo boxes [Windows Forms], in DataGridView control
- combo boxes [Windows Forms], accessing objects in DataGridViewComboBoxCell drop-down lists
ms.assetid: bcbe794a-d1fa-47f8-b5a3-5f085b32097d
ms.openlocfilehash: 7e76ab1ac9089778e4371f4ee65b06d5ebc570bf
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96975194"
---
# <a name="how-to-access-objects-in-a-windows-forms-datagridviewcomboboxcell-drop-down-list"></a>方法: Windows フォームの DataGridViewComboBoxCell ドロップダウン リストのオブジェクトにアクセスする
コントロールと同様に、 <xref:System.Windows.Forms.ComboBox> <xref:System.Windows.Forms.DataGridViewComboBoxColumn> 型と型を使用すると、 <xref:System.Windows.Forms.DataGridViewComboBoxCell> 任意のオブジェクトをドロップダウンリストに追加できます。 この機能を使用すると、対応するオブジェクトを別のコレクションに格納しなくても、ドロップダウンリストで複雑な状態を表すことができます。  
  
 コントロールとは異なり、 <xref:System.Windows.Forms.ComboBox> 型には <xref:System.Windows.Forms.DataGridView> <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> 現在選択されているオブジェクトを取得するためのプロパティがありません。 代わりに、 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType> プロパティまたはプロパティを <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType> ビジネスオブジェクトのプロパティの名前に設定する必要があります。 ユーザーが選択を行うと、ビジネスオブジェクトの指定されたプロパティによってセルプロパティが設定され <xref:System.Windows.Forms.DataGridViewCell.Value%2A> ます。  
  
 セル値を使用してビジネスオブジェクトを取得するには、 `ValueMember` プロパティがビジネスオブジェクト自体への参照を返すプロパティを示す必要があります。 したがって、ビジネスオブジェクトの型がコントロールの下にない場合は、継承によって型を拡張することによって、このようなプロパティを追加する必要があります。  
  
 次の手順では、ビジネスオブジェクトを使用してドロップダウンリストに値を設定し、セルプロパティを使用してオブジェクトを取得する方法について説明し <xref:System.Windows.Forms.DataGridViewCell.Value%2A> ます。  
  
### <a name="to-add-business-objects-to-the-drop-down-list"></a>ドロップダウンリストにビジネスオブジェクトを追加するには  
  
1. 新しいを作成 <xref:System.Windows.Forms.DataGridViewComboBoxColumn> し、そのコレクションにデータを設定 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A> します。 または、[列] <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> プロパティをビジネスオブジェクトのコレクションに設定することもできます。 ただし、コレクション内に対応するビジネスオブジェクトを作成しなくても、ドロップダウンリストに "未割り当て" を追加することはできません。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#110)]  
  
2. <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> と <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> プロパティを設定します。 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> ドロップダウンリストに表示するビジネスオブジェクトのプロパティを示します。 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> ビジネスオブジェクトへの参照を返すプロパティを示します。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#115)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#115)]  
  
3. ビジネスオブジェクト型に、現在のインスタンスへの参照を返すプロパティが含まれていることを確認します。 このプロパティは、前の手順でに割り当てられた値で名前が付けられている必要があり <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> ます。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#310)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#310)]  
  
### <a name="to-retrieve-the-currently-selected-business-object"></a>現在選択されているビジネスオブジェクトを取得するには  
  
- セルプロパティを取得 <xref:System.Windows.Forms.DataGridViewCell.Value%2A> し、ビジネスオブジェクト型にキャストします。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#120)]  
  
## <a name="example"></a>例  
 完全な例では、ドロップダウンリストでビジネスオブジェクトを使用する方法を示します。 この例では、 <xref:System.Windows.Forms.DataGridView> コントロールはオブジェクトのコレクションにバインドされてい `Task` ます。 各 `Task` オブジェクトには、 `AssignedTo` `Employee` そのタスクに現在割り当てられているオブジェクトを示すプロパティがあります。 列には、 `Assigned To` `Name` 割り当てられた各従業員のプロパティ値が表示され `Task.AssignedTo` ます。プロパティ値がの場合は、"未割り当て" と表示され `null` ます。  
  
 この例の動作を表示するには、次の手順を実行します。  
  
1. 列の割り当てを変更する `Assigned To` には、ドロップダウンリストから別の値を選択するか、コンボボックスのセルで CTRL + 0 キーを押します。  
  
2. `Generate Report`現在の割り当てを表示する場合にクリックします。 これは、列の変更によってコレクションが自動的に更新されることを示して `Assigned To` `tasks` います。  
  
3. この `Request Status` `RequestStatus` 行の現在のオブジェクトのメソッドを呼び出すには、ボタンをクリックし `Employee` ます。 これは、選択したオブジェクトが正常に取得されたことを示しています。  
  
 [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#000)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 この例で必要な要素は次のとおりです。  
  
- System アセンブリおよび System.Windows.Forms アセンブリへの参照。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxCell>
- <xref:System.Windows.Forms.DataGridViewComboBoxCell.Items%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxCell.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCell.Value%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ComboBox>
- [Windows フォーム DataGridView コントロールでのデータの表示](displaying-data-in-the-windows-forms-datagridview-control.md)
