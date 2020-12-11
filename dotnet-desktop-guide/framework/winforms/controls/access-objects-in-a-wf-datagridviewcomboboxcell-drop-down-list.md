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
# <a name="how-to-access-objects-in-a-windows-forms-datagridviewcomboboxcell-drop-down-list"></a><span data-ttu-id="b138c-102">方法: Windows フォームの DataGridViewComboBoxCell ドロップダウン リストのオブジェクトにアクセスする</span><span class="sxs-lookup"><span data-stu-id="b138c-102">How to: Access Objects in a Windows Forms DataGridViewComboBoxCell Drop-Down List</span></span>
<span data-ttu-id="b138c-103">コントロールと同様に、 <xref:System.Windows.Forms.ComboBox> <xref:System.Windows.Forms.DataGridViewComboBoxColumn> 型と型を使用すると、 <xref:System.Windows.Forms.DataGridViewComboBoxCell> 任意のオブジェクトをドロップダウンリストに追加できます。</span><span class="sxs-lookup"><span data-stu-id="b138c-103">Like the <xref:System.Windows.Forms.ComboBox> control, the <xref:System.Windows.Forms.DataGridViewComboBoxColumn> and <xref:System.Windows.Forms.DataGridViewComboBoxCell> types enable you to add arbitrary objects to their drop-down lists.</span></span> <span data-ttu-id="b138c-104">この機能を使用すると、対応するオブジェクトを別のコレクションに格納しなくても、ドロップダウンリストで複雑な状態を表すことができます。</span><span class="sxs-lookup"><span data-stu-id="b138c-104">With this feature, you can represent complex states in a drop-down list without having to store corresponding objects in a separate collection.</span></span>  
  
 <span data-ttu-id="b138c-105">コントロールとは異なり、 <xref:System.Windows.Forms.ComboBox> 型には <xref:System.Windows.Forms.DataGridView> <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> 現在選択されているオブジェクトを取得するためのプロパティがありません。</span><span class="sxs-lookup"><span data-stu-id="b138c-105">Unlike the <xref:System.Windows.Forms.ComboBox> control, the <xref:System.Windows.Forms.DataGridView> types do not have a <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> property for retrieving the currently selected object.</span></span> <span data-ttu-id="b138c-106">代わりに、 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType> プロパティまたはプロパティを <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType> ビジネスオブジェクトのプロパティの名前に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b138c-106">Instead, you must set the <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType> or <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType> property to the name of a property on your business object.</span></span> <span data-ttu-id="b138c-107">ユーザーが選択を行うと、ビジネスオブジェクトの指定されたプロパティによってセルプロパティが設定され <xref:System.Windows.Forms.DataGridViewCell.Value%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="b138c-107">When the user makes a selection, the indicated property of the business object sets the cell <xref:System.Windows.Forms.DataGridViewCell.Value%2A> property.</span></span>  
  
 <span data-ttu-id="b138c-108">セル値を使用してビジネスオブジェクトを取得するには、 `ValueMember` プロパティがビジネスオブジェクト自体への参照を返すプロパティを示す必要があります。</span><span class="sxs-lookup"><span data-stu-id="b138c-108">To retrieve the business object through the cell value, the `ValueMember` property must indicate a property that returns a reference to the business object itself.</span></span> <span data-ttu-id="b138c-109">したがって、ビジネスオブジェクトの型がコントロールの下にない場合は、継承によって型を拡張することによって、このようなプロパティを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b138c-109">Therefore, if the type of the business object is not under your control, you must add such a property by extending the type through inheritance.</span></span>  
  
 <span data-ttu-id="b138c-110">次の手順では、ビジネスオブジェクトを使用してドロップダウンリストに値を設定し、セルプロパティを使用してオブジェクトを取得する方法について説明し <xref:System.Windows.Forms.DataGridViewCell.Value%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="b138c-110">The following procedures demonstrate how to populate a drop-down list with business objects and retrieve the objects through the cell <xref:System.Windows.Forms.DataGridViewCell.Value%2A> property.</span></span>  
  
### <a name="to-add-business-objects-to-the-drop-down-list"></a><span data-ttu-id="b138c-111">ドロップダウンリストにビジネスオブジェクトを追加するには</span><span class="sxs-lookup"><span data-stu-id="b138c-111">To add business objects to the drop-down list</span></span>  
  
1. <span data-ttu-id="b138c-112">新しいを作成 <xref:System.Windows.Forms.DataGridViewComboBoxColumn> し、そのコレクションにデータを設定 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A> します。</span><span class="sxs-lookup"><span data-stu-id="b138c-112">Create a new <xref:System.Windows.Forms.DataGridViewComboBoxColumn> and populate its <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A> collection.</span></span> <span data-ttu-id="b138c-113">または、[列] <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> プロパティをビジネスオブジェクトのコレクションに設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="b138c-113">Alternatively, you can set the column <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> property to the collection of business objects.</span></span> <span data-ttu-id="b138c-114">ただし、コレクション内に対応するビジネスオブジェクトを作成しなくても、ドロップダウンリストに "未割り当て" を追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="b138c-114">In that case, however, you cannot add "unassigned" to the drop-down list without creating a corresponding business object in your collection.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#110)]  
  
2. <span data-ttu-id="b138c-115"><xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> と <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="b138c-115">Set the <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> and <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> properties.</span></span> <span data-ttu-id="b138c-116"><xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> ドロップダウンリストに表示するビジネスオブジェクトのプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="b138c-116"><xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> indicates the property of the business object to display in the drop-down list.</span></span> <span data-ttu-id="b138c-117"><xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> ビジネスオブジェクトへの参照を返すプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="b138c-117"><xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> indicates the property that returns a reference to the business object.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#115)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#115)]  
  
3. <span data-ttu-id="b138c-118">ビジネスオブジェクト型に、現在のインスタンスへの参照を返すプロパティが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b138c-118">Make sure that your business object type contains a property that returns a reference to the current instance.</span></span> <span data-ttu-id="b138c-119">このプロパティは、前の手順でに割り当てられた値で名前が付けられている必要があり <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="b138c-119">This property must be named with the value assigned to <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> in the previous step.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#310)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#310)]  
  
### <a name="to-retrieve-the-currently-selected-business-object"></a><span data-ttu-id="b138c-120">現在選択されているビジネスオブジェクトを取得するには</span><span class="sxs-lookup"><span data-stu-id="b138c-120">To retrieve the currently selected business object</span></span>  
  
- <span data-ttu-id="b138c-121">セルプロパティを取得 <xref:System.Windows.Forms.DataGridViewCell.Value%2A> し、ビジネスオブジェクト型にキャストします。</span><span class="sxs-lookup"><span data-stu-id="b138c-121">Get the cell <xref:System.Windows.Forms.DataGridViewCell.Value%2A> property and cast it to the business object type.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#120)]  
  
## <a name="example"></a><span data-ttu-id="b138c-122">例</span><span class="sxs-lookup"><span data-stu-id="b138c-122">Example</span></span>  
 <span data-ttu-id="b138c-123">完全な例では、ドロップダウンリストでビジネスオブジェクトを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b138c-123">The complete example demonstrates the use of business objects in a drop-down list.</span></span> <span data-ttu-id="b138c-124">この例では、 <xref:System.Windows.Forms.DataGridView> コントロールはオブジェクトのコレクションにバインドされてい `Task` ます。</span><span class="sxs-lookup"><span data-stu-id="b138c-124">In the example, a <xref:System.Windows.Forms.DataGridView> control is bound to a collection of `Task` objects.</span></span> <span data-ttu-id="b138c-125">各 `Task` オブジェクトには、 `AssignedTo` `Employee` そのタスクに現在割り当てられているオブジェクトを示すプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="b138c-125">Each `Task` object has an `AssignedTo` property that indicates the `Employee` object currently assigned to that task.</span></span> <span data-ttu-id="b138c-126">列には、 `Assigned To` `Name` 割り当てられた各従業員のプロパティ値が表示され `Task.AssignedTo` ます。プロパティ値がの場合は、"未割り当て" と表示され `null` ます。</span><span class="sxs-lookup"><span data-stu-id="b138c-126">The `Assigned To` column displays the `Name` property value for each assigned employee, or "unassigned" if the `Task.AssignedTo` property value is `null`.</span></span>  
  
 <span data-ttu-id="b138c-127">この例の動作を表示するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b138c-127">To view the behavior of this example, perform the following steps:</span></span>  
  
1. <span data-ttu-id="b138c-128">列の割り当てを変更する `Assigned To` には、ドロップダウンリストから別の値を選択するか、コンボボックスのセルで CTRL + 0 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b138c-128">Change assignments in the `Assigned To` column by selecting different values from the drop-down lists or pressing CTRL+0 in a combo-box cell.</span></span>  
  
2. <span data-ttu-id="b138c-129">`Generate Report`現在の割り当てを表示する場合にクリックします。</span><span class="sxs-lookup"><span data-stu-id="b138c-129">Click `Generate Report` to display the current assignments.</span></span> <span data-ttu-id="b138c-130">これは、列の変更によってコレクションが自動的に更新されることを示して `Assigned To` `tasks` います。</span><span class="sxs-lookup"><span data-stu-id="b138c-130">This demonstrates that a change in the `Assigned To` column automatically updates the `tasks` collection.</span></span>  
  
3. <span data-ttu-id="b138c-131">この `Request Status` `RequestStatus` 行の現在のオブジェクトのメソッドを呼び出すには、ボタンをクリックし `Employee` ます。</span><span class="sxs-lookup"><span data-stu-id="b138c-131">Click a `Request Status` button to call the `RequestStatus` method of the current `Employee` object for that row.</span></span> <span data-ttu-id="b138c-132">これは、選択したオブジェクトが正常に取得されたことを示しています。</span><span class="sxs-lookup"><span data-stu-id="b138c-132">This demonstrates that the selected object has been successfully retrieved.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b138c-133">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="b138c-133">Compiling the Code</span></span>  
 <span data-ttu-id="b138c-134">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b138c-134">This example requires:</span></span>  
  
- <span data-ttu-id="b138c-135">System アセンブリおよび System.Windows.Forms アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="b138c-135">References to the System and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b138c-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="b138c-136">See also</span></span>

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
- [<span data-ttu-id="b138c-137">Windows フォーム DataGridView コントロールでのデータの表示</span><span class="sxs-lookup"><span data-stu-id="b138c-137">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
