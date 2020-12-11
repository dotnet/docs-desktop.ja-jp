---
title: DataGridView コントロールの列の並べ替えモード
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], sort modes
- DataGridView control [Windows Forms], sort mode
ms.assetid: 43715887-2df9-4da7-bcf1-b9c7c842b2bf
ms.openlocfilehash: d1e2f582c9759332e0ed963cb7f88ee052616c45
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974291"
---
# <a name="column-sort-modes-in-the-windows-forms-datagridview-control"></a>Windows フォーム DataGridView コントロール内の列の並べ替えモード
<xref:System.Windows.Forms.DataGridView> 列には3つの並べ替えモードがあります。 各列の並べ替えモードは、 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> 次の列挙値のいずれかに設定できる、列のプロパティによって指定され <xref:System.Windows.Forms.DataGridViewColumnSortMode> ます。  
  
|`DataGridViewColumnSortMode` 値|説明|  
|----------------------------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic>|テキストボックスの列の既定値。 列ヘッダーを選択に使用しない限り、列ヘッダーをクリックすると、自動的に <xref:System.Windows.Forms.DataGridView> この列によってが並べ替えられ、並べ替え順序を示すグリフが表示されます。|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable>|テキストボックス以外の列の既定値。 この列はプログラムで並べ替えることができます。ただし、並べ替えのためのものではないため、並べ替えグリフ用の領域は予約されていません。|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.Programmatic>|この列はプログラムで並べ替えることができ、領域は並べ替えグリフ用に予約されています。|  
  
 意味のある <xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable> 順序付けが可能な値が含まれている場合は、既定の列の並べ替えモードを変更することができます。 たとえば、アイテムの状態を表す数値を含むデータベース列がある場合は、データベース列に画像列をバインドすることで、これらの数値を対応するアイコンとして表示できます。 その後、イベントのハンドラーで数値セル値を画像表示値に変更でき <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> ます。 この場合、 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> プロパティをに設定する <xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic> と、ユーザーが列を並べ替えることができるようになります。 自動並べ替えを使用すると、ユーザーは、数値に対応する状態に自然な順序が設定されていない場合でも、同じ状態の項目をグループ化できます。 チェックボックスの列は、同じ状態の項目をグループ化するために自動並べ替えが役立つもう1つの例です。  
  
 <xref:System.Windows.Forms.DataGridView>設定に関係なく、任意の列または複数の列の値によって、プログラムによってを並べ替えることができ <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> ます。 プログラムによる並べ替えは、並べ替えに独自のユーザーインターフェイス (UI) を提供したり、カスタムの並べ替えを実装したりする場合に便利です。 <xref:System.Windows.Forms.DataGridView>列ヘッダーの選択を有効にするように選択モードを設定する場合などに、独自の並べ替え UI を提供すると便利です。 この場合、列ヘッダーは並べ替えに使用できませんが、ヘッダーに適切な並べ替えグリフが表示されるようにするには、プロパティをに設定し <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> <xref:System.Windows.Forms.DataGridViewColumnSortMode.Programmatic> ます。  
  
 プログラムによる並べ替えモードに設定されている列は、並べ替えグリフを自動的に表示しません。 これらの列では、プロパティを設定することによって、自分でグリフを表示する必要があり <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType> ます。 これは、カスタムの並べ替えの柔軟性を必要とする場合に必要です。 たとえば、複数の列でを並べ替える場合 <xref:System.Windows.Forms.DataGridView> は、複数の並べ替えグリフを表示するか、並べ替えグリフを使用しないようにすることができます。  
  
 プログラムを使用して、任意の列でを並べ替えることができますが、ボタン列などの一部の列には、意味 <xref:System.Windows.Forms.DataGridView> のある順序付けが可能な値が含まれていない場合があります。 これらの列の場合、 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> のプロパティ設定は、 <xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable> 並べ替えに使用されないことを示します。したがって、並べ替えグリフのヘッダーに領域を予約する必要はありません。  
  
 <xref:System.Windows.Forms.DataGridView>が並べ替えられている場合は、プロパティとプロパティの値を確認することで、並べ替え列と並べ替え順序の両方を確認でき <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> <xref:System.Windows.Forms.DataGridView.SortOrder%2A> ます。 これらの値は、カスタムの並べ替え操作の後に意味がありません。 カスタム並べ替えの詳細については、このトピックで後述する「カスタム並べ替え」セクションを参照してください。  
  
 バインドさ <xref:System.Windows.Forms.DataGridView> れた列とバインドされていない列の両方を含むコントロールを並べ替える場合、バインドされていない列の値は自動的に保持されません。 これらの値を維持するには、プロパティをに設定 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> し、 `true` イベントとイベントを処理することによって、仮想モードを実装する必要があり <xref:System.Windows.Forms.DataGridView.CellValueNeeded> <xref:System.Windows.Forms.DataGridView.CellValuePushed> ます。 詳細については、「 [方法: Windows フォーム DataGridView コントロールで仮想モードを実装](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)する」を参照してください。 バインドモードでの非バインド列による並べ替えはサポートされていません。  
  
## <a name="programmatic-sorting"></a>プログラムによる並べ替え  
 <xref:System.Windows.Forms.DataGridView>メソッドを呼び出すことによって、プログラムでを並べ替えることができ <xref:System.Windows.Forms.DataGridView.Sort%2A> ます。  
  
 `Sort(DataGridViewColumn,ListSortDirection)`メソッドのオーバーロードは、 <xref:System.Windows.Forms.DataGridView.Sort%2A> <xref:System.Windows.Forms.DataGridViewColumn> <xref:System.ComponentModel.ListSortDirection> パラメーターとしてと列挙値を受け取ります。 このオーバーロードは、意味のある順序を指定できるが、自動並べ替えを構成しない値を持つ列で並べ替える場合に便利です。 このオーバーロードを呼び出し、プロパティ値がの列を渡すと <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> <xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic?displayProperty=nameWithType> 、 <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> <xref:System.Windows.Forms.DataGridView.SortOrder%2A> プロパティとプロパティが自動的に設定され、適切な並べ替えグリフが列ヘッダーに表示されます。  
  
> [!NOTE]
> プロパティを <xref:System.Windows.Forms.DataGridView> 設定して、コントロールが外部データソースにバインドされている場合、バインドされて <xref:System.Windows.Forms.DataGridView.DataSource%2A> `Sort(DataGridViewColumn,ListSortDirection)` いない列に対してはメソッドオーバーロードは機能しません。 また、プロパティがの場合は <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> `true` 、バインドされた列に対してのみこのオーバーロードを呼び出すことができます。 列がデータバインドされているかどうかを判断するには、プロパティ値を確認し <xref:System.Windows.Forms.DataGridViewColumn.IsDataBound%2A> ます。 バインドモードでの非バインド列の並べ替えはサポートされていません。  
  
## <a name="custom-sorting"></a>カスタム並べ替え  
 をカスタマイズするに <xref:System.Windows.Forms.DataGridView> は、 `Sort(IComparer)` メソッドのオーバーロードを使用する <xref:System.Windows.Forms.DataGridView.Sort%2A> か、イベントを処理し <xref:System.Windows.Forms.DataGridView.SortCompare> ます。  
  
 `Sort(IComparer)`メソッドオーバーロードは、インターフェイスを実装するクラスのインスタンスを <xref:System.Collections.IComparer> パラメーターとして受け取ります。 このオーバーロードは、カスタムの並べ替えを提供する場合に便利です。たとえば、列の値に自然な並べ替え順序が設定されていない場合や、自然な並べ替え順序が適切でない場合などです。 この場合、自動並べ替えを使用することはできませんが、列ヘッダーをクリックしてユーザーが並べ替えられるようにすることもできます。 <xref:System.Windows.Forms.DataGridView.ColumnHeaderMouseClick>列ヘッダーを選択に使用しない場合は、イベントのハンドラーでこのオーバーロードを呼び出すことができます。  
  
> [!NOTE]
> `Sort(IComparer)`メソッドオーバーロードは、 <xref:System.Windows.Forms.DataGridView> コントロールが外部データソースにバインドされておらず、プロパティ値がの場合にのみ機能し <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> `false` ます。 外部データソースにバインドされている列の並べ替えをカスタマイズするには、データソースによって提供される並べ替え操作を使用する必要があります。 仮想モードでは、バインドされていない列に対して独自の並べ替え操作を提供する必要があります。  
  
 メソッドオーバーロードを使用するには、 `Sort(IComparer)` インターフェイスを実装する独自のクラスを作成する必要があり <xref:System.Collections.IComparer> ます。 このインターフェイスでは、メソッドの <xref:System.Collections.IComparer.Compare%2A?displayProperty=nameWithType> <xref:System.Windows.Forms.DataGridView> <xref:System.Windows.Forms.DataGridViewRow> オーバーロードが呼び出されたときにがオブジェクトを入力として渡すメソッドを実装するために、クラスが必要です `Sort(IComparer)` 。 これにより、任意の列の値に基づいて、正しい行の順序を計算できます。  
  
 メソッドのオーバーロードでは、 `Sort(IComparer)` プロパティとプロパティが設定されない <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> ため、 <xref:System.Windows.Forms.DataGridView.SortOrder%2A> 並べ替えグリフを表示するようにプロパティを常に設定する必要があり <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType> ます。  
  
 メソッドオーバーロードの代わりに `Sort(IComparer)` 、イベントのハンドラーを実装することによって、カスタムの並べ替えを行うことができ <xref:System.Windows.Forms.DataGridView.SortCompare> ます。 このイベントは、自動並べ替えを行うように構成された列のヘッダーをユーザーがクリックしたとき、またはメソッドのオーバーロードを呼び出したときに発生し `Sort(DataGridViewColumn,ListSortDirection)` <xref:System.Windows.Forms.DataGridView.Sort%2A> ます。 イベントは、コントロール内の行の各ペアに対して発生し、正しい順序を計算できるようにします。  
  
> [!NOTE]
> <xref:System.Windows.Forms.DataGridView.SortCompare>プロパティが設定されている場合、 <xref:System.Windows.Forms.DataGridView.DataSource%2A> またはプロパティの <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 値がの場合、イベントは発生しません `true` 。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.SortedColumn%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.SortOrder%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType>
- [Windows フォームの DataGridView コントロールでのデータの並べ替え](sorting-data-in-the-windows-forms-datagridview-control.md)
- [方法: Windows フォーム DataGridView コントロール内の列の並べ替えモードを設定する](set-the-sort-modes-for-columns-wf-datagridview-control.md)
- [方法: Windows フォーム DataGridView コントロールの並べ替え機能をカスタマイズする](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)
