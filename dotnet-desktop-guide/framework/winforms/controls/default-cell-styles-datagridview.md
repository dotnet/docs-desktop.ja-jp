---
title: デザイナーを使用して DataGridView コントロールの既定のセルスタイルとデータ形式を設定する
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], setting styles
- data formats
- data [Windows Forms], setting formats
ms.assetid: fc6da49f-8942-41da-b49f-b2afc38cc656
ms.openlocfilehash: ca602fa15e4648550bfa171a9c3abd057e930eca
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974205"
---
# <a name="how-to-set-default-cell-styles-and-data-formats-for-the-windows-forms-datagridview-control-using-the-designer"></a>方法: デザイナーを使用して Windows フォーム DataGridView コントロールの既定のセル スタイルとデータ形式を設定する

コントロールを使用すると、 <xref:System.Windows.Forms.DataGridView> コントロール全体、特定の列、行ヘッダー、列ヘッダー、および行と列のヘッダーに対して既定のセルスタイルとセルデータ形式を指定できます。また、行を交互に使用して、元帳効果を作成することもできます。 コントロール全体に対して設定されている既定のスタイルは、列および交互の行に対して設定された既定のスタイルによって上書きされます。 また、個々の行およびセルのコードで設定したスタイルは、既定のスタイルを上書きします。

セルスタイルの詳細については、「 [Windows フォーム DataGridView コントロールのセルのスタイル](cell-styles-in-the-windows-forms-datagridview-control.md)」を参照してください。 交互の行のスタイルを設定する方法については、「 [方法: デザイナーを使用して Windows フォーム DataGridView コントロールに交互の行のスタイルを設定](set-alternating-row-styles-for-the-datagrid-using-the-designer.md)する」を参照してください。

また、プロパティを使用してスタイルを設定し、 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> コントロールに追加されるすべての行に影響を与えることもできます。 行テンプレートの詳細については、「 [方法: 行テンプレートを使用して Windows フォーム DataGridView コントロールで行をカスタマイズする](use-the-row-template-to-customize-rows-in-the-datagrid.md)」を参照してください。

次の手順では、コントロールを含むフォームを含む **Windows アプリケーション** プロジェクトが必要 <xref:System.Windows.Forms.DataGridView> です。 このようなプロジェクトの設定の詳細については、「 [方法: Windows フォームアプリケーションプロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project) する」および「 [方法: Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)する」を参照してください。

### <a name="to-set-default-styles-for-all-cells-in-the-control"></a>コントロール内のすべてのセルに既定のスタイルを設定するには

1. <xref:System.Windows.Forms.DataGridView>デザイナーでコントロールを選択します。

2. [ **プロパティ** ] ウィンドウで、 ![ 、、 ](./media/visual-studio-ellipsis-button.png) <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> またはの各 <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> プロパティの横 <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> にある省略記号ボタン ([...] プロパティウィンドウ) をクリックします。 [ **CellStyle ビルダー** ] ダイアログボックスが表示されます。

3. **プレビュー** ウィンドウを使用して選択内容を確認し、プロパティを設定してスタイルを定義します。

> [!NOTE]
> 視覚スタイルが有効になっている場合、行ヘッダーと列ヘッダー (を除く <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A> ) は、現在のテーマによって自動的にスタイルが設定され、 <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> プロパティ値とプロパティ値はオーバーライドされ <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> ます。
>
> デザイナーを使用して、複数の選択したコントロールのセルスタイルを設定でき <xref:System.Windows.Forms.DataGridView> ますが、変更するセルスタイルプロパティの値が同じである場合に限られます。 そのプロパティのセルスタイルが異なる場合、[ **CellStyle ビルダー** ] ダイアログボックスの [**プロパティ**] ウィンドウは空白になります。

### <a name="to-set-default-styles-for-cells-in-individual-columns"></a>個々の列のセルに既定のスタイルを設定するには

1. デザイナーでコントロールを右クリックし、[ <xref:System.Windows.Forms.DataGridView> **列の編集**] を選択します。

2. [ **選択された列** ] ボックスの一覧から列を選択します。

3. [ **列のプロパティ** ] グリッドで、プロパティの横にある省略記号ボタン ( ![ Visual Studio のプロパティウィンドウの省略記号ボタン (...)) をクリックし ](./media/visual-studio-ellipsis-button.png) <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> ます。 [ **CellStyle ビルダー** ] ダイアログボックスが表示されます。

4. **プレビュー** ウィンドウを使用して選択内容を確認し、プロパティを設定してスタイルを定義します。

### <a name="to-format-data-in-cells"></a>セルのデータの書式を設定するには

1. 前の手順のいずれかを使用して、既定のセルスタイルプロパティに関連する [ **CellStyle ビルダー** ] ダイアログボックスを表示します。

2. [ **CellStyle ビルダー** ] ダイアログボックスで、プロパティの横にある省略記号ボタン ( ![ Visual Studio のプロパティウィンドウの省略記号ボタン ([...]) をクリックし ](./media/visual-studio-ellipsis-button.png) <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> ます。 [ **書式文字列** ] ダイアログボックスが表示されます。

3. 書式の種類を選択してから、[ **サンプル** ] ボックスを使用して選択内容を確認し、種類の詳細 (表示する小数点以下の桁数など) を変更します。

4. <xref:System.Windows.Forms.DataGridView>Null 値が含まれる可能性のあるデータソースにコントロールをバインドする場合は、[ **null 値**] ボックスに入力します。 この値は、セルの値が null 参照 ( `Nothing` Visual Basic) またはである場合に表示され <xref:System.DBNull.Value?displayProperty=nameWithType> ます。

## <a name="see-also"></a>関連項目

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A?displayProperty=nameWithType>
- [Windows フォーム DataGridView コントロールでのセルのスタイル](cell-styles-in-the-windows-forms-datagridview-control.md)
- [方法: デザイナーを使用して Windows フォーム DataGridView コントロールに交互の行のスタイルを設定する](set-alternating-row-styles-for-the-datagrid-using-the-designer.md)
- [方法: Windows フォームアプリケーションプロジェクトを作成する](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [方法: Windows フォームにコントロールを追加する](how-to-add-controls-to-windows-forms.md)
