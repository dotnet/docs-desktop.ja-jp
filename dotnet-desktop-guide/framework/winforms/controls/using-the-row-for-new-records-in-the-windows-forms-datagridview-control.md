---
title: DataGridView コントロールの新しいレコードに対して行を使用する
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], adding rows for new records
- rows [Windows Forms], new records
- DataGridView control [Windows Forms], data entry
ms.assetid: 6110f1ea-9794-442c-a98a-f104a1feeaf4
ms.openlocfilehash: 2fcd35f8c4d04909cdbc26f6a4293fdd570385b8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983927"
---
# <a name="using-the-row-for-new-records-in-the-windows-forms-datagridview-control"></a>Windows フォーム DataGridView コントロールにおける新規レコード行の使用
アプリケーションのデータを編集するためにを使用する場合は、多くの場合、データ <xref:System.Windows.Forms.DataGridView> ストアに新しいデータ行を追加する機能をユーザーに提供することをお勧めします。 コントロールは、 <xref:System.Windows.Forms.DataGridView> 新しいレコードの行を提供することによって、この機能をサポートします。これは常に最後の行として表示されます。 行ヘッダーにアスタリスク (*) 記号が付いています。 次のセクションでは、新しいレコードを有効にする行をプログラミングするときに考慮する必要がある事項について説明します。  
  
## <a name="displaying-the-row-for-new-records"></a>新しいレコードの行を表示する  
 <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A>新しいレコードの行を表示するかどうかを示すには、プロパティを使用します。 このプロパティの既定値は `true` です。  
  
 データバインドの場合、 <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> コントロールのプロパティと <xref:System.ComponentModel.IBindingList.AllowNew%2A?displayProperty=nameWithType> データソースのプロパティが両方とも、新しいレコードの行が表示され `true` ます。 どちらかがの場合 `false` 、行は表示されません。  
  
## <a name="populating-the-row-for-new-records-with-default-data"></a>既定のデータを使用して新しいレコードの行を設定する  
 ユーザーが新しいレコードの行を現在の行として選択すると、コントロールによって <xref:System.Windows.Forms.DataGridView> イベントが発生し <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> ます。  
  
 このイベントは、新しいへのアクセスを提供 <xref:System.Windows.Forms.DataGridViewRow> し、新しい行に既定のデータを設定できるようにします。 詳細については、「[方法: Windows フォーム DataGridView コントロールで新しい行の既定値を指定する](specify-default-values-for-new-rows-in-the-datagrid.md)」を参照してください。  
  
## <a name="the-rows-collection"></a>Rows コレクション  
 新しいレコードの行はコントロールのコレクションに格納され <xref:System.Windows.Forms.DataGridView> <xref:System.Windows.Forms.DataGridView.Rows%2A> ますが、次の2つの点で動作が異なります。  
  
- 新しいレコードの行は、プログラムによってコレクションから削除することはできません <xref:System.Windows.Forms.DataGridView.Rows%2A> 。 このような場合は、が <xref:System.InvalidOperationException> スローされます。 ユーザーは、新しいレコードの行を削除することもできません。 メソッドは、 <xref:System.Windows.Forms.DataGridViewRowCollection.Clear%2A?displayProperty=nameWithType> この行をコレクションから削除 <xref:System.Windows.Forms.DataGridView.Rows%2A> しません。  
  
- 新しいレコードの行の後に行を追加することはできません。 <xref:System.InvalidOperationException>このような場合は、が発生します。 その結果、新しいレコードの行は常にコントロールの最後の行になり <xref:System.Windows.Forms.DataGridView> ます。 <xref:System.Windows.Forms.DataGridViewRowCollection>行を追加するのメソッド ( <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> 、 <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopy%2A> 、および <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopies%2A> ) はすべて、新しいレコードの行が存在する場合に、挿入メソッドを内部的に呼び出します。  
  
## <a name="visual-customization-of-the-row-for-new-records"></a>新しいレコードの行のビジュアルカスタマイズ  
 新しいレコードの行が作成されると、プロパティによって指定された行に基づいて作成され <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> ます。 この行に対して指定されていないセルスタイルは、他のプロパティから継承されます。 セルスタイルの継承の詳細については、「 [Windows フォーム DataGridView コントロールのセルのスタイル](cell-styles-in-the-windows-forms-datagridview-control.md)」を参照してください。  
  
 新しいレコードの行のセルによって表示される初期値は、各セルのプロパティから取得され <xref:System.Windows.Forms.DataGridViewCell.DefaultNewRowValue%2A> ます。 型のセルの場合 <xref:System.Windows.Forms.DataGridViewImageCell> 、このプロパティはプレースホルダーイメージを返します。 それ以外の場合は、`null` を返します。 このプロパティをオーバーライドして、カスタム値を返すことができます。 ただし、これらの初期値は、 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> 新しいレコードの行にフォーカスが入ったときにイベントハンドラーによって置き換えられます。  
  
 この行のヘッダーの標準アイコン (矢印またはアスタリスク) は、一般公開されていません。 アイコンをカスタマイズする場合は、カスタムクラスを作成する必要があり <xref:System.Windows.Forms.DataGridViewRowHeaderCell> ます。  
  
 標準アイコンでは <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> 、 <xref:System.Windows.Forms.DataGridViewCellStyle> 行ヘッダーセルによって使用されているのプロパティが使用されます。 標準アイコンは、完全に表示するための十分な領域がない場合はレンダリングされません。  
  
 行ヘッダーセルに文字列値が設定されていて、テキストとアイコンの両方に十分な領域がない場合は、まずアイコンがドロップされます。  
  
## <a name="sorting"></a>並べ替え  
 非バインドモードでは、ユーザーがの <xref:System.Windows.Forms.DataGridView> コンテンツを並べ替えた場合でも、の末尾には常に新しいレコードが追加され <xref:System.Windows.Forms.DataGridView> ます。 ユーザーは、行を正しい位置に並べ替えるために並べ替えを再度適用する必要があります。この動作は、コントロールの動作と似てい <xref:System.Windows.Forms.ListView> ます。  
  
 データバインドモードと仮想モードでは、並べ替えが適用されるときの挿入動作は、データモデルの実装に依存します。 ADO.NET の場合、行はすぐに正しい位置に並べ替えられます。  
  
## <a name="other-notes-on-the-row-for-new-records"></a>新しいレコードの行に関するその他のメモ  
 <xref:System.Windows.Forms.DataGridViewRow.Visible%2A>この行のプロパティをに設定することはできません `false` 。 <xref:System.InvalidOperationException>このような場合は、が発生します。  
  
 新しいレコードの行は、常に選択されていない状態で作成されます。  
  
## <a name="virtual-mode"></a>仮想モード  
 仮想モードを実装する場合は、データモデルで新しいレコードの行が必要になるタイミングと、行の追加をロールバックするタイミングを追跡する必要があります。 この機能の正確な実装は、データモデルの実装とそのトランザクションセマンティクスによって異なります。たとえば、コミットスコープがセルレベルまたは行レベルのどちらであるかなどです。 詳細については、「 [Windows フォーム DataGridView コントロールでの仮想モード](virtual-mode-in-the-windows-forms-datagridview-control.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>
- [Windows フォーム DataGridView コントロールでのデータ入力](data-entry-in-the-windows-forms-datagridview-control.md)
- [方法: Windows フォーム DataGridView コントロールの新しい行に既定値を指定する](specify-default-values-for-new-rows-in-the-datagrid.md)
