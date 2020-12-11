---
title: DataGridView コントロールのセルスタイル
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], styles
- data grids [Windows Forms], cell styles
ms.assetid: dbb75ed6-8804-4232-8382-f9920c2e380c
ms.openlocfilehash: fe56033a5adbe7719c64695c8f9ebc4f3644fc65
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981559"
---
# <a name="cell-styles-in-the-windows-forms-datagridview-control"></a>Windows フォーム DataGridView コントロールでのセルのスタイル
コントロール内の各セル <xref:System.Windows.Forms.DataGridView> は、テキスト形式、背景色、前景色、フォントなど、独自のスタイルを持つことができます。 ただし、通常は、複数のセルで特定のスタイル特性を共有します。  
  
 スタイルを共有するセルのグループには、特定の行または列内のすべてのセル、特定の値を含むすべてのセル、またはコントロール内のすべてのセルを含めることができます。 これらのグループが重なっているため、各セルのスタイル情報が複数の場所から取得される場合があります。 たとえば、コントロール内のすべてのセルで同じフォントを使用する必要があり、通貨の <xref:System.Windows.Forms.DataGridView> 列のセルだけが通貨形式を使用するようにし、負の値を持つ通貨セルのみが赤の前景色を使用するようにすることができます。  
  
## <a name="the-datagridviewcellstyle-class"></a>DataGridViewCellStyle クラス  
 クラスには <xref:System.Windows.Forms.DataGridViewCellStyle> 、visual スタイルに関連する次のプロパティが含まれています。  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A> および <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionBackColor%2A> および <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionForeColor%2A>  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A>  
  
 このクラスには、書式設定に関連する次のプロパティも含まれています。  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> および <xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A>  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> および <xref:System.Windows.Forms.DataGridViewCellStyle.DataSourceNullValue%2A>  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A>  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A>  
  
- <xref:System.Windows.Forms.DataGridViewCellStyle.Padding%2A>  
  
 これらのプロパティおよびその他のセルスタイルのプロパティの詳細については、 <xref:System.Windows.Forms.DataGridViewCellStyle> 以下の「関連項目」セクションに記載されているリファレンスドキュメントとトピックを参照してください。  
  
## <a name="using-datagridviewcellstyle-objects"></a>DataGridViewCellStyle オブジェクトの使用  
 <xref:System.Windows.Forms.DataGridViewCellStyle> <xref:System.Windows.Forms.DataGridView> 、、、およびの各 <xref:System.Windows.Forms.DataGridViewColumn> <xref:System.Windows.Forms.DataGridViewRow> <xref:System.Windows.Forms.DataGridViewCell> クラスとその派生クラスのさまざまなプロパティからオブジェクトを取得できます。 これらのプロパティのいずれかがまだ設定されていない場合は、その値を取得すると新しいオブジェクトが作成され <xref:System.Windows.Forms.DataGridViewCellStyle> ます。 独自のオブジェクトをインスタンス化 <xref:System.Windows.Forms.DataGridViewCellStyle> して、これらのプロパティに割り当てることもできます。  
  
 複数の要素間でオブジェクトを共有することによって、スタイル情報の不要な重複を回避でき <xref:System.Windows.Forms.DataGridViewCellStyle> <xref:System.Windows.Forms.DataGridView> ます。 コントロール、列、および行の各レベルで設定されたスタイルによって、各レベルがセルレベルまでフィルター処理されるため、上記のレベルとは異なる各レベルのスタイルプロパティのみを設定することにより、スタイルの重複を回避することもできます。 詳細については、後の「スタイルの継承」セクションを参照してください。  
  
 次の表に、オブジェクトを取得または設定する主なプロパティを示し <xref:System.Windows.Forms.DataGridViewCellStyle> ます。  
  
|プロパティ|クラス|説明|  
|--------------|-------------|-----------------|  
|`DefaultCellStyle`|<xref:System.Windows.Forms.DataGridView>、 <xref:System.Windows.Forms.DataGridViewColumn> 、 <xref:System.Windows.Forms.DataGridViewRow> 、およびの各派生クラス|コントロール全体 (ヘッダーセルを含む)、列、または行内のすべてのセルで使用される既定のスタイルを取得または設定します。|  
|<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|コントロールのすべての行で使用される既定のセルスタイルを取得または設定します。 これには、ヘッダーセルは含まれません。|  
|<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|コントロールの交互の行で使用される既定のセルスタイルを取得または設定します。 元帳に似た効果を作成するために使用します。|  
|<xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|コントロールの行ヘッダーによって使用される既定のセルスタイルを取得または設定します。 Visual スタイルが有効になっている場合、現在のテーマによってオーバーライドされます。|  
|<xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>|<xref:System.Windows.Forms.DataGridView>|コントロールの列ヘッダーによって使用される既定のセルスタイルを取得または設定します。 Visual スタイルが有効になっている場合、現在のテーマによってオーバーライドされます。|  
|<xref:System.Windows.Forms.DataGridViewCell.Style%2A>|<xref:System.Windows.Forms.DataGridViewCell> および派生クラス|セルレベルで指定されたスタイルを取得または設定します。 これらのスタイルは、上位レベルから継承されたスタイルよりも優先されます。|  
|`InheritedStyle`|<xref:System.Windows.Forms.DataGridViewCell>、 <xref:System.Windows.Forms.DataGridViewRow> 、 <xref:System.Windows.Forms.DataGridViewColumn> 、およびの各派生クラス|上位レベルから継承されたスタイルを含む、セル、行、または列に現在適用されているすべてのスタイルを取得します。|  
  
 前述のように、 <xref:System.Windows.Forms.DataGridViewCellStyle> プロパティが以前に設定されていない場合、スタイルプロパティの値を取得すると、新しいオブジェクトが自動的にインスタンス化されます。 これらのオブジェクトを不必要に作成しないように、行クラスと列クラスにはプロパティがあり、プロパティ <xref:System.Windows.Forms.DataGridViewBand.HasDefaultCellStyle%2A> <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A> が設定されているかどうかを確認できます。 同様に、セルクラスには、 <xref:System.Windows.Forms.DataGridViewCell.HasStyle%2A> <xref:System.Windows.Forms.DataGridViewCell.Style%2A> プロパティが設定されているかどうかを示すプロパティがあります。  
  
 各スタイルプロパティには、コントロールに対応する *PropertyName* `Changed` イベントがあり <xref:System.Windows.Forms.DataGridView> ます。 行、列、およびセルの各プロパティの場合、イベントの名前は " `Row` "、" `Column` "、または " `Cell` " (など) で始まり <xref:System.Windows.Forms.DataGridView.RowDefaultCellStyleChanged> ます。 これらの各イベントは、対応するスタイルプロパティが別のオブジェクトに設定されている場合に発生し <xref:System.Windows.Forms.DataGridViewCellStyle> ます。 これらのイベントは、 <xref:System.Windows.Forms.DataGridViewCellStyle> スタイルプロパティからオブジェクトを取得し、そのプロパティ値を変更したときには発生しません。 セルスタイルオブジェクト自体への変更に応答するには、イベントを処理し <xref:System.Windows.Forms.DataGridView.CellStyleContentChanged> ます。  
  
## <a name="style-inheritance"></a>スタイルの継承  
 各は、その <xref:System.Windows.Forms.DataGridViewCell> プロパティから外観を取得し <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> ます。 <xref:System.Windows.Forms.DataGridViewCellStyle>このプロパティによって返されるオブジェクトは、型のプロパティの階層から値を継承し <xref:System.Windows.Forms.DataGridViewCellStyle> ます。 これらのプロパティは、 <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> ヘッダー以外のセルのが値を取得する順序で下に一覧表示されます。  
  
1. <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>  
  
2. <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
3. <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType> (インデックス番号が奇数の行のセルのみ)  
  
4. <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
  
5. <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
6. <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 行と列のヘッダーセルの場合、 <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> プロパティは、指定された順序で、次のソースプロパティのリストの値によって設定されます。  
  
1. <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>  
  
2. <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A?displayProperty=nameWithType> または <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A?displayProperty=nameWithType>  
  
3. <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 このプロセスを説明する図を次に示します。  
  
 ![DataGridViewCellStyle 型のプロパティ](./media/cell-styles-in-the-windows-forms-datagridview-control/datagridviewcells-inheritance-diagram.gif "DataGridViewCells 継承ダイアグラム")  
  
 また、特定の行と列によって継承されたスタイルにアクセスすることもできます。 Column プロパティは、 <xref:System.Windows.Forms.DataGridViewColumn.InheritedStyle%2A> 次のプロパティからその値を継承します。  
  
1. <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
2. <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 Row プロパティは、 <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A> 次のプロパティからその値を継承します。  
  
1. <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
2. <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType> (インデックス番号が奇数の行のセルのみ)  
  
3. <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
  
4. <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
  
 プロパティ <xref:System.Windows.Forms.DataGridViewCellStyle> によって返されるオブジェクトの各プロパティについて `InheritedStyle` 、プロパティ値は、対応するプロパティがクラスの既定値以外の値に設定されている、適切なリストの最初のセルスタイルから取得され <xref:System.Windows.Forms.DataGridViewCellStyle> ます。  
  
 次の表は、 <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> 例のセルのプロパティ値が、その親列から継承される方法を示しています。  
  
|型のプロパティ `DataGridViewCellStyle`|取得した `ForeColor` オブジェクトの値の例|  
|----------------------------------------------|----------------------------------------------------|  
|<xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Red%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Empty?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.DarkBlue%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>|<xref:System.Drawing.Color.Black%2A?displayProperty=nameWithType>|  
  
 この場合、 <xref:System.Drawing.Color.Red%2A?displayProperty=nameWithType> セルの行の値は、リストの最初の実際の値になります。 これは、 <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> セルののプロパティ値になり <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> ます。  
  
 次の図は、さまざまな <xref:System.Windows.Forms.DataGridViewCellStyle> プロパティが異なる場所から値を継承する方法を示しています。  
  
 ![DataGridView プロパティ&#45;値の継承](./media/cell-styles-in-the-windows-forms-datagridview-control/datagridviewcells-value-inheritance-diagram.gif "DataGridViewCells 値の継承ダイアグラム")  
  
 スタイルの継承を利用することで、複数の場所で同じ情報を指定しなくても、コントロール全体に適したスタイルを提供できます。  
  
 ヘッダーセルは、説明のとおりスタイル継承に参加しますが、コントロールのプロパティとプロパティによって返されるオブジェクトには、 <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> <xref:System.Windows.Forms.DataGridView> プロパティによって返されるオブジェクトのプロパティ値をオーバーライドする初期プロパティ値があり <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> ます。 プロパティによって返されるオブジェクトに対して設定されたプロパティを <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> 行ヘッダーおよび列ヘッダーに適用する場合は、プロパティおよびプロパティによって返されるオブジェクトの対応するプロパティを、クラスに指定されている <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> 既定値に設定する必要があり <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> <xref:System.Windows.Forms.DataGridViewCellStyle> ます。  
  
> [!NOTE]
> 視覚スタイルが有効になっている場合、行ヘッダーと列ヘッダー (を除く <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A> ) は、現在のテーマによって自動的にスタイルが設定され、これらのプロパティによって指定されたすべてのスタイルがオーバーライドされます。  
  
 <xref:System.Windows.Forms.DataGridViewButtonColumn>型、 <xref:System.Windows.Forms.DataGridViewImageColumn> 型、および <xref:System.Windows.Forms.DataGridViewCheckBoxColumn> 型も、column プロパティによって返されるオブジェクトの一部の値を初期化し <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> ます。 詳細については、これらの型のリファレンスドキュメントを参照してください。  
  
## <a name="setting-styles-dynamically"></a>動的なスタイル設定  
 特定の値を持つセルのスタイルをカスタマイズするには、イベントのハンドラーを実装し <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> ます。 このイベントのハンドラーは、型の引数を受け取り <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> ます。 このオブジェクトには、書式設定されているセルの値をコントロール内のその位置と共に判断するためのプロパティが含まれてい <xref:System.Windows.Forms.DataGridView> ます。 このオブジェクトには、 <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.CellStyle%2A> <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> 書式設定されるセルのプロパティの値に初期化されるプロパティも含まれています。 セルスタイルのプロパティを変更して、セルの値と場所に適したスタイル情報を指定できます。  
  
> [!NOTE]
> <xref:System.Windows.Forms.DataGridView.RowPrePaint>イベントと <xref:System.Windows.Forms.DataGridView.RowPostPaint> イベントは、 <xref:System.Windows.Forms.DataGridViewCellStyle> イベントデータ内でもオブジェクトを受け取りますが、その場合は読み取り専用の行プロパティのコピーであるため、 <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A> 変更内容はコントロールに影響しません。  
  
 イベントやイベントなどのイベントに応じて、個々のセルのスタイルを動的に変更することもでき <xref:System.Windows.Forms.DataGridView.CellMouseEnter?displayProperty=nameWithType> <xref:System.Windows.Forms.DataGridView.CellMouseLeave> ます。 たとえば、イベントのハンドラーで、 <xref:System.Windows.Forms.DataGridView.CellMouseEnter> セルの背景色の現在の値 (セルのプロパティを通じて取得される) を格納 <xref:System.Windows.Forms.DataGridViewCell.Style%2A> し、マウスをポイントしたときにセルを強調表示する新しい色に設定することができます。 イベントのハンドラーでは、 <xref:System.Windows.Forms.DataGridView.CellMouseLeave> 背景色を元の値に戻すことができます。  
  
> [!NOTE]
> <xref:System.Windows.Forms.DataGridViewCell.Style%2A>特定のスタイル値が設定されているかどうかに関係なく、セルのプロパティに格納されている値をキャッシュすることが重要です。 スタイル設定を一時的に置き換える場合は、元の "設定なし" の状態に復元することで、そのセルが上位レベルからスタイル設定を継承するようになります。 スタイルが継承されているかどうかに関係なく、セルに対して実際に有効なスタイルを決定する必要がある場合は、セルのプロパティを使用し <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A> ます。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.InheritedStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewRow.InheritedStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.InheritedStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellStyleContentChanged?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>
- [Windows フォームの DataGridView コントロールの基本的な書式設定およびスタイル設定](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [方法: Windows フォーム DataGridView コントロールの既定のセル スタイルを設定する](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)
- [Windows フォーム DataGridView コントロールでのデータの書式設定](data-formatting-in-the-windows-forms-datagridview-control.md)
